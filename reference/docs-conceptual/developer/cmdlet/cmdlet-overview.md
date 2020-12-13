---
ms.date: 06/11/2020
ms.topic: reference
title: Cmdlet 概述
description: Cmdlet 概述
ms.openlocfilehash: ed3082e1a821bb9643ea2eef13b7348eb48488e4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653232"
---
# <a name="cmdlet-overview"></a>Cmdlet 概述

Cmdlet 是在 PowerShell 环境中使用的轻量命令。 PowerShell 运行时在命令行中提供的自动化脚本的上下文中调用这些 cmdlet。 PowerShell 运行时还通过 PowerShell Api 以编程方式调用它们。

## <a name="cmdlets"></a>Cmdlet

Cmdlet 执行操作，通常会将 Microsoft .NET 对象返回到管道中的下一个命令。 Cmdlet 是参与 PowerShell 管道语义的单个命令。
这包括二进制 (C#) cmdlet、高级脚本函数、CDXML 和工作流。

此 SDK 文档介绍如何创建用 c # 编写的二进制 cmdlet。 有关基于脚本的 cmdlet 的信息，请参阅：

- [about_Functions_Advanced](/powershell/module/microsoft.powershell.core/about/about_functions_advanced)
- [about_Functions_CmdletBindingAttribute](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)
- [about_Functions_Advanced_Methods](/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods)

若要创建二进制 cmdlet，必须实现一个派生自两个专用 cmdlet 基类之一的 cmdlet 类。 派生类必须：

- 声明一个将派生类标识为 cmdlet 的特性。
- 定义用特性修饰的公共属性，这些属性将公共属性标识为 cmdlet 参数。
- 重写一个或多个输入处理方法来处理记录。

您可以通过使用 [import-module](/powershell/module/microsoft.powershell.core/import-module) cmdlet 直接加载包含该类的程序集，也可以创建一个主机应用程序，用于通过使用 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) API 加载该程序集。 这两种方法都提供对 cmdlet 功能的编程和命令行访问。

## <a name="cmdlet-terms"></a>Cmdlet 术语

PowerShell cmdlet 文档中经常使用以下术语：

### <a name="cmdlet-attribute"></a>Cmdlet 特性

用于将 cmdlet 类声明为 cmdlet 的 .NET 特性。 尽管 PowerShell 使用几个可选的其他属性，但 Cmdlet 属性是必需的。 有关此属性的详细信息，请参阅 [Cmdlet 特性声明](cmdlet-attribute-declaration.md)。

### <a name="cmdlet-parameter"></a>Cmdlet 参数

公共属性，用于定义可用于用户的参数或运行 cmdlet 的应用程序。 Cmdlet 可以有必需的、命名的、位置参数和 *开关* 参数。 通过开关参数可以定义仅当在调用中指定了参数时才计算的参数。 有关不同类型的参数的详细信息，请参阅 [Cmdlet 参数](cmdlet-parameters.md)。

### <a name="parameter-set"></a>参数集

可用于相同的命令中以执行特定操作的一组参数。 一个 cmdlet 可以具有多个参数集，但是每个参数集必须至少具有一个唯一的参数。 良好的 cmdlet 设计强烈意味着 unique 参数也是必需的参数。
有关参数集的详细信息，请参阅 [Cmdlet 参数集](cmdlet-parameter-sets.md)。

### <a name="dynamic-parameter"></a>动态参数

在运行时添加到 cmdlet 的参数。 通常，当另一个参数设置为特定值时，会将动态参数添加到 cmdlet。 有关动态参数的详细信息，请参阅 [Cmdlet 动态参数](cmdlet-dynamic-parameters.md)。

### <a name="input-processing-methods"></a>输入处理方法

[System.web](/dotnet/api/System.Management.Automation.Cmdlet)类提供了以下用于处理记录的虚方法：。 所有派生的 cmdlet 类必须重写前三个方法中的一个或多个：

- [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)：用于为 Cmdlet 提供可选的一次性预处理功能（& e）。
- [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)：用于为 Cmdlet 提供按记录处理的功能的处理功能。 根据 Cmdlet 的输入， [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法可能会被调用任意次数（或根本不会进行调用）。
- [System.web. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)：用于为 Cmdlet 提供可选的一次性处理后的功能，。
- [StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing)：用于在用户以异步方式停止 Cmdlet 时停止处理 (例如，按<kbd>CTRL</kbd> + <kbd>C</kbd>) 。

有关这些方法的详细信息，请参阅 [Cmdlet 输入处理方法](./cmdlet-input-processing-methods.md)。

实现 cmdlet 时，必须重写这些输入处理方法中的至少一个。
通常， **ProcessRecord ( # B1** 是重写的方法，因为它是为该 cmdlet 处理的每条记录调用的。 与此相反， **BeginProcessing ( # B1** 方法和 **EndProcessing ( # B3** 方法被调用一次来执行记录的预处理或后期处理。 有关这些方法的详细信息，请参阅 [输入处理方法](cmdlet-input-processing-methods.md)。

### <a name="shouldprocess-feature"></a>ShouldProcess 功能

通过 PowerShell，你可以创建在 cmdlet 对系统进行更改之前提示用户提供反馈的 cmdlet。 若要使用此功能，该 cmdlet 必须声明它 `ShouldProcess` 在声明 cmdlet 属性时支持该功能，并且该 cmdlet 必须从输入处理方法中调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 和 [ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 方法，然后才能使用此功能。 有关如何支持该功能的详细信息 `ShouldProcess` ，请参阅 [请求确认](requesting-confirmation-from-cmdlets.md)。

### <a name="transaction"></a>事务

被视为单个任务的一组命令逻辑组。 如果组中的任何命令失败，并且用户可以选择接受或拒绝在事务中执行的操作，则任务将自动失败。 若要参与事务，cmdlet 必须在声明 Cmdlet 属性时声明它支持事务。 Windows PowerShell 2.0 中引入了对事务的支持。 有关事务的详细信息，请参阅 [如何支持事务](how-to-support-transactions.md)。

## <a name="how-cmdlets-differ-from-commands"></a>Cmdlet 与命令的区别

Cmdlet 在以下方面与其他命令 shell 环境中的命令不同：

- Cmdlet 是 .NET 类的实例;它们不是独立的可执行文件。
- 可以从多达十二行代码创建 cmdlet。
- Cmdlet 通常不会执行自己的分析、错误演示或输出格式设置。 分析、错误演示和输出格式由 PowerShell 运行时处理。
- Cmdlet 从管道（而不是从文本流）处理输入对象，而 cmdlet 通常将对象作为输出传递到管道。
- Cmdlet 是面向记录的，因为它们一次处理一个对象。

## <a name="cmdlet-base-classes"></a>Cmdlet 基类

Windows PowerShell 支持从以下两个基类派生的 cmdlet。

- 大多数 cmdlet 都以派生自 [system.object](/dotnet/api/System.Management.Automation.Cmdlet) 基类的 .net 类为基础。
  从此类派生允许 cmdlet 使用 Windows PowerShell 运行时上的最小依赖项集。 这带来了两个好处。 第一个优点是，cmdlet 对象更小，不太可能受到对 PowerShell 运行时所做的更改的影响。 第二个优点是，如果你需要，可以直接创建 cmdlet 对象的实例，然后直接调用它，而不是通过 PowerShell 运行时调用它。

- 更复杂的 cmdlet 以派生自 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 基类的 .net 类为基础。 从此类派生，可以更好地访问 PowerShell 运行时。 此访问权限允许 cmdlet 调用脚本、访问提供程序和访问当前会话状态。
   (访问当前会话状态时，你将获取并设置会话变量和首选项。 ) 不过，从此类派生将增加 cmdlet 对象的大小，这意味着你的 cmdlet 更紧密地耦合到最新版本的 PowerShell 运行时。

通常情况下，除非你需要对 PowerShell 运行时的扩展访问权限，否则你应该从 [system.web](/dotnet/api/System.Management.Automation.Cmdlet) 类派生。
但是，PowerShell 运行时具有广泛的日志记录功能，可以执行 cmdlet。 如果审核模型依赖于此日志记录，则可以通过从 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 类派生来阻止从另一个 cmdlet 中执行 cmdlet。

## <a name="cmdlet-attributes"></a>Cmdlet 属性

PowerShell 定义多个 .NET 属性，这些属性用于管理 cmdlet，并用于指定 PowerShell 提供的和 cmdlet 可能需要的常用功能。 例如，特性用于将类指定为 cmdlet、指定 cmdlet 的参数，并请求验证输入，以便 cmdlet 开发人员无需在其 cmdlet 代码中实现该功能。 有关特性的详细信息，请参阅 [PowerShell 特性](./cmdlet-attributes.md)。

## <a name="cmdlet-names"></a>Cmdlet 名称

PowerShell 使用动词和-名词名称对来命名 cmdlet。 例如， `Get-Command` PowerShell 中包含的 cmdlet 用于获取在命令外壳中注册的所有 cmdlet。 谓词标识 cmdlet 执行的操作，名词标识该 cmdlet 执行其操作的资源。

在将 .NET 类声明为 cmdlet 时指定这些名称。 有关如何将 .NET 类声明为 cmdlet 的详细信息，请参阅 [Cmdlet 特性声明](./cmdlet-class-declaration.md)。

## <a name="writing-cmdlet-code"></a>编写 Cmdlet 代码

本文档提供了两种方法来了解如何编写 cmdlet 代码。 如果更喜欢查看代码而不做很多解释，请参阅 [Cmdlet 代码示例](./examples-of-cmdlet-code.md)。 如需更多有关代码的说明，请参阅 [GetProc 教程](./getproc-tutorial.md)、 [StopProc 教程](./stopproc-tutorial.md)或 [SelectStr 教程](./selectstr-tutorial.md) 主题。

有关编写 cmdlet 的准则的详细信息，请参阅 [Cmdlet 开发指南](./cmdlet-development-guidelines.md)。

## <a name="see-also"></a>另请参阅

[PowerShell Cmdlet 概念](./windows-powershell-cmdlet-concepts.md)

[写入 PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

[PowerShell SDK](../windows-powershell-reference.md)
