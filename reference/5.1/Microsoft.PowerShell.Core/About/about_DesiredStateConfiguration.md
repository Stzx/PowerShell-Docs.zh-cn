---
description: 简要介绍了 PowerShell 所需状态配置 (DSC) 功能。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 2f043104c67078b98355b3e54171a8993e534837
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200652"
---
# <a name="about_desiredstateconfiguration"></a>about_DesiredStateConfiguration

## <a name="short-description"></a>简短说明

简要介绍了 PowerShell 所需状态配置 (DSC) 功能。

## <a name="long-description"></a>详细说明

DSC 是 PowerShell 中的一个管理平台，可用于部署和管理软件服务的配置数据，并管理这些服务的运行环境。

DSC 提供了一组 PowerShell 语言扩展、新的 cmdlet 和资源，你可以使用它以声明方式指定你希望配置软件环境状态的方式。 它还提供了维护和管理现有配置的方法。

PowerShell 4.0 中引入了 DSC。

有关 DSC 的详细信息，请参阅 TechNet 库中的 [PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/overview) 。

## <a name="developing-dsc-resources-with-classes"></a>用类开发 DSC 资源

从 PowerShell 5.0 开始，可以使用类开发 DSC 资源。
有关详细信息，请参阅 Microsoft TechNet 上的 [about_Classes](about_Classes.md)和 [使用 PowerShell 类编写自定义 DSC 资源](/previous-versions//dn948461(v=technet.10)) 。

## <a name="using-dsc"></a>使用 DSC

要使用 DSC 配置你的环境，请先使用配置关键字来定义一个 PowerShell 脚本块，后跟一个标识符，该标识符后面跟着分隔块的大括号对。 在配置块中，你可以定义节点块，以便为环境中 (计算机) 的每个节点指定所需的配置状态。 节点块以 Node 关键字开头，后跟目标计算机的名称，可以是变量。 在计算机名称后，出现用于分隔节点块的大括号。 在节点块内，可以定义用于配置特定资源的资源块。 资源块以资源的类型名称开头，后跟要为该块指定的标识符，后跟分隔块的大括号，如下面的示例中所示。

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

若要创建配置，请使用与调用 PowerShell 函数相同的方式来调用配置块，并传入您在上面的示例中定义的任何所需参数 (两个) 。 例如，在这种情况下：

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

这会在你指定的路径下为每个节点生成一个 MOF 文件。 这些 MOF 文件指定每个节点所需的配置。 接下来，使用以下 cmdlet 分析配置 MOF 文件，发送每个节点的相应配置，并制定这些配置。 请注意，不需要为基于类的 DSC 资源创建单独的 MOF 文件。

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a>使用 DSC 维护配置状态

对于 DSC，配置是幂等的。 这意味着，如果你使用 DSC 来多次执行相同的配置，则生成的配置状态将始终相同。 因此，如果您怀疑您的环境中的任何节点可能会从所需的配置状态偏移，则可以再次执行相同的 DSC 配置，使其返回到所需状态。 不需要修改配置脚本来仅对状态与所需状态为 "偏移" 的资源进行寻址。

下面的示例演示了如何验证给定节点上的实际配置状态是否与该节点上代理的上一个 DSC 配置偏移。 在此示例中，我们将检查本地计算机的配置。

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a>内置 DSC 资源

你可以在配置脚本中使用下列内置资源：

|名称                  |属性                                         |
|----------------------|---------------------------------------------------|
|文件                  |{DestinationPath，属性，Checksum，Content ...}|
|存档               |{Destination，路径，校验和，Credential ...}       |
|环境           |{Name，DependsOn，请确保，Path ...}                 |
|组                 |{DependsOn，Credential，，"Description ...}" |
|日志                   |{Message，DependsOn，PsDscRunAsCredential}         |
|包               |{Name、Path、ProductId、Arguments ...}              |
|注册表              |{Key，ValueName，DependsOn，请确保 ...}             |
|脚本                |{GetScript，SetScript，TestScript，Credential ...}  |
|服务               |{Name，与 builtinaccount，Credential，依存关系 ...}|
|用户                  |{UserName、DependsOn、Description、Disabled ...}    |
|WaitForAll            |{NodeName，Context.resourcename，DependsOn，PsDscRunAsC ...}|
|WaitForAny            |{NodeName，Context.resourcename，DependsOn，PsDscRunAsC ...}|
|WaitForSome           |{NodeCount，NodeName，Context.resourcename，DependsOn ...}  |
|WindowsFeature        |{Name，Credential，DependsOn，请确保 ...}           |
|WindowsOptionalFeature|{Name，DependsOn，请确保，LogLevel ...}             |
|WindowsProcess        |{Arguments，Path，Credential，DependsOn ...}        |

若要获取系统上可用 DSC 资源的列表，请运行 `Get-DscResource` cmdlet。

> [!NOTE]
> 在低于 7.0 的 PowerShell 版本中，`Get-DscResource` 找不到基于类的 DSC 资源。

本主题中的示例演示如何使用 File 和 node.js 资源。 若要查看可用于资源的所有属性，请在资源关键字中插入光标 (例如，在 PowerShell ISE 中的配置脚本内) 文件，然后按住<kbd>CTRL</kbd> + <kbd>空格键</kbd>

## <a name="find-more-resources"></a>查找更多资源

您可以下载、安装并了解由 PowerShell 和 DSC 用户社区和 Microsoft 创建的许多其他可用 DSC 资源。 请访问 [PowerShell 库](https://www.powershellgallery.com/) ，浏览并了解可用的 DSC 资源。

## <a name="see-also"></a>另请参阅

[PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/overview)

[内置 PowerShell 所需状态配置资源](/powershell/scripting/dsc/resources/resources)

[构建自定义 PowerShell 所需状态配置资源](/powershell/scripting/dsc/resources/authoringResource)
