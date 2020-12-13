---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 提供程序概述
description: Windows PowerShell 提供程序概述
ms.openlocfilehash: 2f1c5f5991a64fb2b85ece7feba915164ebd34ee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355504"
---
# <a name="windows-powershell-provider-overview"></a>Windows PowerShell 提供程序概述

Windows PowerShell 提供程序允许像文件系统一样公开任何数据存储，就像它是装入的驱动器一样。 例如，内置的注册表提供程序允许你在注册表中导航，就像浏览 `c` 计算机驱动器一样。 提供程序还可以重写 `Item` cmdlet (例如，、等） `Get-Item` `Set-Item` ) 这样可以处理数据存储区中的数据，如在导航文件系统时处理文件和目录。 有关提供程序和驱动器以及 Windows PowerShell 中的内置提供程序的详细信息，请参阅 [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)。

## <a name="providers-and-drives"></a>提供商和驱动器

提供程序定义用于访问、导航和编辑数据存储区的逻辑，而驱动器则指定数据存储的特定入口点 (或数据存储区的某个部分) 此访问接口定义的类型。 例如，注册表提供程序允许访问注册表中的配置单元和密钥，并且 HKLM 和 HKCU 驱动器指定注册表中的相应配置单元。 HKLM 和 HKCU 驱动器都使用注册表提供程序。

当你编写提供程序时，可以指定默认驱动器-在提供程序可用时自动创建的驱动器。 还定义了一个方法来创建使用该提供程序的新驱动器。

## <a name="type-of-providers"></a>提供程序的类型

提供了几种类型的提供程序，每种类型提供不同的功能级别。 提供程序作为从[SessionStateCategory](/dotnet/api/system.management.automation.sessionstatecategory) 
 **CmdletProvider** 类的其中一个子代派生的类来实现。 有关不同类型的提供程序的信息，请参阅 [提供程序类型](./provider-types.md)。

## <a name="provider-cmdlets"></a>提供程序 cmdlet

提供程序可以实现与 cmdlet 相对应的方法，并在该提供程序的驱动器中使用时为这些 cmdlet 创建自定义行为。 根据提供程序的类型，有不同的 cmdlet 集可用。 有关提供程序中可供自定义的 cmdlet 的完整列表，请参阅 [提供程序 cmdlet](./provider-cmdlets.md)。

## <a name="provider-paths"></a>提供程序路径

用户浏览提供商驱动器，如文件系统。 因此，它们期望路径的语法对应于文件系统导航中使用的路径。 用户运行提供程序 cmdlet 时，将指定要访问的项的路径。 可以通过多种方式解释指定的路径。 提供程序应支持以下一个或多个路径类型。

### <a name="drive-qualified-paths"></a>驱动器限定路径

驱动器限定路径是项名称、项所在的容器和子容器的组合，以及通过其访问该项的 Windows PowerShell 驱动器。  (驱动器由用于访问数据存储的提供程序定义。 此路径以驱动器名称开头，后面跟一个冒号 (： ) 。 例如： `get-childitem C:`

### <a name="provider-qualified-paths"></a>提供程序限定路径

若要允许 Windows PowerShell 引擎初始化和取消初始化提供程序，提供程序必须支持提供程序限定的路径。 例如，用户可以初始化和取消初始化 FileSystem 提供程序，因为它定义以下提供程序限定路径： `FileSystem::\\uncshare\abc\bar` 。

### <a name="provider-direct-paths"></a>提供程序-直接路径

若要允许远程访问你的 Windows PowerShell 提供程序，它应该支持直接传递到 Windows PowerShell 提供程序以获取当前位置的提供程序直接路径。 例如，Windows PowerShell 提供程序的注册表可以用作 `\\server\regkeypath` 提供程序-直接路径。

### <a name="provider-internal-paths"></a>提供程序-内部路径

若要允许提供程序 cmdlet 使用非 Windows PowerShell 应用程序编程接口访问数据 (Api) ，你的 Windows PowerShell 提供程序应支持提供程序内部路径。 此路径在提供程序限定的路径中的 "：：" 后指示。 例如，filesystem Windows PowerShell 提供程序的提供程序内部路径为 `\\uncshare\abc\bar` 。

## <a name="overriding-cmdlet-parameters"></a>重写 cmdlet 参数

某些特定于提供程序的 cmdlet 的行为可由提供程序重写。 有关可以重写的参数的列表，以及如何在提供程序类中重写这些参数的列表，请参阅 [提供程序 cmdlet 参数](./provider-cmdlet-parameters.md)

## <a name="dynamic-parameters"></a>动态参数

当用户为 cmdlet 的一个静态参数指定特定值时，提供程序可以定义添加到提供程序 cmdlet 的动态参数。 提供程序通过实现一个或多个动态参数方法来实现此功能。 有关可用于添加动态参数的 cmdlet 参数的列表，以及用于实现它们的方法，请参阅 [提供程序 cmdlet 动态参数](./provider-cmdlet-dynamic-parameters.md)。

## <a name="provider-capabilities"></a>提供程序功能

[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举定义了提供程序可支持的多个功能。 其中包括使用通配符、筛选项和支持事务的功能。 若要为提供程序指定功能，请添加[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举值的列表，并将其与逻辑操作组合在一起，并将其与 `OR` [Cmdletproviderattribute. Providercapabilities *](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities)属性组合在一起， (提供程序类的特性的) 属性的第二个参数。） [](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 。 例如，下面的特性指定提供程序支持[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 
 **ShouldProcess** 和[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 
 **事务** 功能的访问器的支持程序管理器。

```csharp
[CmdletProvider(RegistryProvider.ProviderName, ProviderCapabilities.ShouldProcess | ProviderCapabilities.Transactions)]

```

## <a name="provider-cmdlet-help"></a>提供程序 cmdlet 帮助

编写提供程序时，可以为所支持的提供程序 cmdlet 实现自己的帮助。
这包括针对每个提供程序 cmdlet 的单个帮助主题，或者针对提供程序 cmdlet 根据动态参数使用方式不同的情况的多个帮助主题版本。 若要支持特定于提供程序 cmdlet 的帮助，提供程序必须实现 [Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp) 接口。

Windows PowerShell 引擎调用 [Icmdletprovidersupportshelp. Gethelpmaml *](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml) 方法，以显示提供程序 Cmdlet 的帮助主题。 引擎提供用户在运行 cmdlet 时指定的 cmdlet 的名称 `Get-Help` ，以及用户的当前路径。
如果提供程序为不同的驱动器实现相同的提供程序 cmdlet 的不同版本，则当前路径是必需的。 此方法必须返回一个字符串，其中包含用于 cmdlet 的 XML 帮助。

使用 PSMAML XML 编写帮助文件的内容。 这是用于写入独立 cmdlet 的帮助内容的相同 XML 架构。 在元素下，将自定义 cmdlet 帮助的内容添加到提供程序的帮助文件 `CmdletHelpPaths` 。 下面的示例演示 `command` 单个提供程序 cmdlet 的元素，并演示如何指定提供程序的提供程序 cmdlet 的名称。 支持

```xml
<CmdletHelpPaths>
  <command:command>
    <command:details>
      <command:name>ProviderCmdletName</command:name>
      <command:verb>Verb</command:verb>
      <command:noun>Noun</command:noun>
    <command:details>
  </command:command>
<CmdletHelpPath>
```

## <a name="see-also"></a>另请参阅

[Windows PowerShell 提供程序功能](./provider-types.md)

[提供程序 Cmdlet](./provider-cmdlets.md)

[编写 Windows PowerShell 提供程序](./writing-a-windows-powershell-provider.md)
