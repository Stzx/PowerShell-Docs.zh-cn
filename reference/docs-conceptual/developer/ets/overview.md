---
ms.date: 07/09/2020
ms.topic: reference
title: 扩展类型系统概述
description: 扩展类型系统概述
ms.openlocfilehash: f4a789f779fa8a52f0fe524abff7ec3311e93b6c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655723"
---
# <a name="extended-type-system-overview"></a>扩展类型系统概述

PowerShell 使用其 **PSObject** 对象通过两种方式来扩展对象的类型。 首先， **PSObject** 对象提供一种方法来显示特定对象类型的不同视图。 这称为 "显示对象的改编视图"。 其次， **PSObject** 对象提供将成员添加到现有对象的方法。 通过包装现有对象（称为基对象）， **PSObject** 对象提供扩展类型系统 (ETS) ，脚本和 cmdlet 开发人员可以使用该系统在 shell 中操作 .net 对象。

## <a name="cmdlet-and-script-development-issues"></a>Cmdlet 和脚本开发问题

ETS 解决了两个基本问题：

首先，某些 .NET 对象没有在 cmdlet 之间充当数据所必需的默认行为。

- 某些 .NET 对象是 "meta" 对象 (例如： WMI 对象、ADO 对象和 XML 对象) 其成员描述它们所包含的数据。 但是，在脚本环境中，它是最值得注意的包含数据，而不是包含数据的说明。 ETS 通过引入用于使基础 .NET 对象适应所需默认语义的适配器的概念来解决此问题。
- 某些 .NET 对象成员的名称不一致，提供的公共成员集不足，或提供的功能不足。 ETS 通过引入使用其他成员扩展 .NET 对象的功能来解决此问题。

其次，PowerShell 脚本 _语言是无类型的，_ 因为无需声明特定类型的变量。 也就是说，脚本开发人员创建的变量 _是本质上_ 无类型。 但是，PowerShell 系统是 "类型驱动的"，因为它依赖于对基本操作（如输出结果或排序）进行操作时所使用的类型名称。

因此，脚本开发人员必须能够声明其中一个变量的类型，并构建自己的一组动态类型化 "对象"，其中包含属性和方法，并可参与到类型驱动的系统中。 ETS 解决了此问题的方法是，提供一种脚本语言的通用对象，使其能够动态地声明其类型并动态添加成员。

从根本上讲，ETS 通过提供 **PSObject** 对象来解决前面提到的问题，该对象用作脚本语言的所有对象访问的基础，并为 cmdlet 开发人员提供标准抽象。

### <a name="cmdlet-developers"></a>Cmdlet 开发人员

对于 cmdlet 开发人员，ETS 提供了以下支持：

- 使用 **PSObject** 对象，以一般方式使用对象的抽象。 ETS 还提供了在需要时钻取这些抽象的功能。
- 使用一组已知的扩展成员为其对象类型创建格式设置、排序、序列化和其他系统操作的机制。
- 对任何使用与使用 Languageprimitives.physicalequality 对象的脚本语言相同的语义的对象操作的方法。
- 这种方法动态 "键入" 哈希表，以便系统的其余部分能够有效地执行操作。

### <a name="script-developers"></a>编写开发人员脚本

对于脚本开发人员而言，ETS 提供了以下支持：

- 能够使用相同的语法 () 引用任何基础对象类型 `$a.x` 。
- 访问 **PSObject** 对象提供的抽象之外的功能 (例如仅访问改编的成员或访问基对象本身) 。
- 定义用于控制对象实例或类型的格式设置、排序、序列化和其他操作的已知成员的功能。
- 指将对象命名为特定类型，从而控制其基于类型的成员的继承。
- 添加、删除和修改扩展成员的功能。
- 如果需要，可以操作 **PSObject** 对象本身。

## <a name="the-psobject-class"></a>PSObject 类

**PSObject** 对象是从脚本语言进行的所有对象访问的基础，并为 cmdlet 开发人员提供了标准抽象。 它包含一个 (.NET 对象的基对象) ，以及在特定对象实例上存在的任何实例成员 (成员（尤其是扩展成员），而不一定在) 相同类型的其他对象上。 根据基对象的类型， **PSObject** 对象还可以提供对改编成员以及任何基于类型的扩展成员的隐式和显式访问。

**PSObject** 对象提供以下机制：

- 使用或不使用基对象构造 **PSObject** 的能力。
- 能够通过常见的查找算法访问每个构造的 **PSObject** 对象的所有成员，并在需要时重写该算法。
- 获取和设置构造的 **PSObject** 对象的类型名称的功能，使脚本和 cmdlet 可以通过相同的类型名称引用类似的 **PSObject** 对象，而不考虑其基对象的类型。

### <a name="how-to-construct-a-psobject"></a>如何构造 PSObject

以下列表描述了创建 **PSObject** 对象的方法：

- 调用 **PSObject** . #ctor 构造函数将创建一个新的 **PSObject** 对象，该对象具有 PSCustomObject 的基对象。 此类型的基对象指示 **PSObject** 对象没有有意义的基对象。 但是，具有这种类型的基对象的 **PSObject** 对象的确提供了一个属性包，该属性包由 cmdlet 开发人员通过添加扩展成员来找到帮助。

开发人员还可以指定对象类型名称，该名称允许此对象与具有相同类型名称的其他 **PSObject** 对象共享其扩展成员。

-  (System.object #ctor 调用 **psobject**) 构造函数将创建一个新的 **PSObject** 对象，其中包含类型为 system.object 的基对象。

  在这种情况下，所创建的对象的类型名称是基对象的派生层次结构的集合。 例如，包含 ProcessInfo 基对象的 **PSObject** 的类型名称将包含以下名称：

  - System.Diagnostics.Process
  - System.componentmodel
  - System.MarshalByRefObject
  - System.Object

- 调用 **PSObject** 。AsPSObject (System.object) 方法基于提供的对象创建新的 **PSObject** 对象。

  如果提供的对象的类型为 System.object，则提供的对象将用作新 **PSObject** 对象的基对象。 如果提供的对象已是 **PSObject** 对象，则提供的对象将按原样返回。

### <a name="base-adapted-and-extended-members"></a>基本、改编和扩展成员

从概念上讲，ETS 使用以下术语来显示基本对象的原始成员与 PowerShell 添加的成员之间的关系。 有关 **psobject** 对象使用的特定成员类型的详细信息，请参阅 [psobject class](/dotnet/api/system.management.automation.psobject)。

#### <a name="base-object-members"></a>基对象成员

如果在构造 **PSObject** 对象时指定了基对象，则可以通过 members 属性使用基对象的成员。

#### <a name="adapted-members"></a>改编成员

当基对象是一个元对象时，其中一个对象的属性 "描述" 其包含数据的一般方式中包含数据，ETS 将这些对象调整为一个视图，该视图允许通过已改编的 **PSObject** 对象成员直接访问数据。 可通过 Members 属性访问改编成员和基对象成员。

#### <a name="extended-members"></a>扩展成员

除了通过基对象或 PowerShell 创建的那些改编成员提供的成员以外， **PSObject** 还可以定义扩展成员，这些扩展成员用脚本环境中有用的附加信息来扩展原始的基本对象。

例如，PowerShell 提供的所有核心 cmdlet （如 Get-Content 和 Set-Content cmdlet）都采用 path 参数。 若要确保这些 cmdlet 以及其他 cmdlet 可对不同类型的对象进行操作，可以将路径成员添加到这些对象，以便它们都以常见方式为其信息。 此扩展路径成员可确保 cmdlet 可对所有这些类型进行操作，即使基类可能不具有路径成员也是如此。

扩展成员、改编成员和基本对象成员均通过 Members 属性进行访问。
