---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: c917e9256d49e9af70f35914a27e204a4f6efd15
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197623"
---
# Save-Help

## 摘要
下载最新的帮助文件，并将其保存到文件系统目录。

## SYNTAX

### Path（默认值）

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [<CommonParameters>]
```

### LiteralPath

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION

**Save-Help** Cmdlet 下载 PowerShell 模块的最新帮助文件，并将其保存到指定的目录。
此功能允许你更新不能访问 Internet 的计算机上的帮助文件，并使得更新多台计算机上的帮助文件更加方便。

在 Windows PowerShell 3.0 中， **Save-Help** 仅适用于在本地计算机上安装的模块。
尽管可以从远程计算机导入模块，或通过使用 PowerShell 远程处理从远程计算机获取对 **PSModuleInfo** 对象的引用，但不会保留 **HelpInfoUri** 属性，并且 **保存-帮助** 不适用于远程模块帮助。

在 Windows PowerShell 4.0 中， **HelpInfoUri** 属性通过 PowerShell 远程处理保留，这使得 **Save Help** 可用于远程计算机上安装的模块。
还可以通过在无法访问 Internet 的计算机上运行 Export-Clixml 将 **PSModuleInfo** 对象保存到磁盘或可移动媒体中，在具有 internet 访问权限的计算机上导入该对象，然后在 **PSModuleInfo** 对象上运行 **save-Help** 。
通过使用可移动存储媒体（例如 USB 驱动器），可以将保存的帮助传输到远程计算机。
可以通过运行 **update-help** 在远程计算机上安装帮助。
此过程可用于在不具有任何类型的网络访问的计算机上安装帮助。

若要安装保存的帮助文件，请运行 Update-Help cmdlet。
添加其 *SourcePath* 参数以指定保存帮助文件的文件夹。

在没有参数的情况下， **Save-Help** 命令将为会话中的所有模块和在计算机（位于 **PSModulePath** 环境变量中列出的位置内）上安装的模块下载最新的帮助。
此操作跳过不支持可更新帮助的模块，而不发出警告。

**Save-Help** cmdlet 检查目标文件夹中任何帮助文件的版本。
如果有较新的帮助文件，则此 cmdlet 将从 Internet 下载最新的帮助文件，然后将它们保存在文件夹中。
**Save-Help** cmdlet 的工作方式与 Update-Help cmdlet 相同，不同之处在于它将下载的 cab 文件保存 ( .cab) 文件，而不是从 cabinet 文件中提取帮助文件并将其安装在计算机上。

为每个模块保存的帮助都包括一个帮助信息 (HelpInfo XML) 文件和一个适用于帮助文件各种 UI 区域性的 Cabinet (.cab) 文件。
你不必从 cabinet 文件中提取帮助文件。
**Update-help** cmdlet 将提取帮助文件、验证 XML 以确保安全，然后将帮助文件和帮助信息文件安装在 module 文件夹的特定于语言的子文件夹中。

若要将模块的帮助文件保存在 PowerShell 安装文件夹中 ($pshome \Modules) ，请使用 "以管理员身份运行" 选项启动 PowerShell。
你必须是计算机上 Administrators 组的成员，才能为这些模块下载帮助文件。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：为 DhcpServer 模块保存帮助

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module, save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

此示例显示了使用 **Save help** 保存连接到 Internet 的客户端计算机的 **DhcpServer** 模块帮助，而无需在本地计算机上安装 **DhcpServer** 模块或 DHCP 服务器角色的三种不同方法。

### 示例 2：为 DhcpServer 模块安装帮助

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

此示例演示如何在不能访问 Internet 的计算机上为 **DhcpServer** 模块安装你在示例1中保存的帮助。

### 示例 3：为所有模块保存帮助

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

此命令将为本地计算机上针对 Windows 所设置的 UI 区域性中的所有模块下载最新的帮助文件。
它将帮助文件保存在 \\ \\ Server01\Fileshare01 文件夹中。

### 示例 4：为计算机上的模块保存帮助

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

此命令将为 **ServerManager** 模块下载最新的帮助文件，然后将它们保存在 \\ \\ Server01\Fileshare01 文件夹中。

如果模块已安装在计算机上，你可以键入该模块名称作为 *Module* 参数的值，即使该模块未导入到当前会话中也是如此。

该命令使用 *Credential* 参数来提供有权写入文件共享的用户的凭据。

### 示例 5：为其他计算机上的模块保存帮助

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

这些命令将为 **CustomSQL** 模块下载最新的帮助文件，并将它们保存在 \\ \\ Server01\Fileshare01 文件夹中。

由于 **CustomSQL** 模块未安装在计算机上，因此序列包含一个 Invoke-Command 命令，该命令从 Server02 计算机获取 CustomSQL 模块的模块对象，然后通过管道将模块对象传递给 **cmdlet。**

如果模块未安装在计算机上， **Save-Help** 将需要模块对象，其中包括有关最新帮助文件的位置的信息。

### 示例 6：为采用多种语言的模块保存帮助

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

此命令在四个不同的 UI 区域性中为 PowerShell Core 模块保存帮助。
这些区域设置的语言包不必安装在计算机上。

仅当模块所有者在 Internet 上提供了翻译文件时， **Save-Help** 才可以为不同的 UI 区域性中的模块下载帮助文件。

### 示例7：每天保存帮助一次以上

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

此命令将为安装在计算机上的所有模块保存帮助。
命令指定 *Force* 参数以替代规则，该规则阻止在每24小时的时间段内阻止 **保存帮助** cmdlet 下载帮助。

*Force* 参数还会重写 1 GB 限制并绕过版本检查。
因此，你可以下载文件，即使版本不高于目标文件夹中的版本。

该命令使用 get-help **cmdlet 将** 帮助文件下载并保存到指定的文件夹。
如果每日需要多次运行一个 **Save-Help** 命令，则需要使用 *Force* 参数。

## PARAMETERS

### -Credential

指定用户凭据。 此 cmdlet 使用有权访问 **DestinationPath** 参数指定的文件系统位置的用户的凭据运行该命令。 仅当命令中使用了 **DestinationPath** 或 **LiteralPath** 参数时，此参数才有效。

此参数使你可以 `Save-Help` 在远程计算机上运行使用 **DestinationPath** 参数的命令。 通过提供显式凭据，你可以在远程计算机上运行该命令并访问第三台计算机上的文件共享，而不会遇到 "拒绝访问" 错误或使用 CredSSP 身份验证委派凭据。

键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。 如果键入用户名，系统会提示输入密码。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath

指定保存帮助文件的文件夹的路径。
不要指定文件名或文件扩展名。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

指示此 cmdlet 不遵循每日一次的限制，跳过版本检查，并下载超出 1 GB 限制的文件。

在没有此参数的情况下，每个模块每天只允许运行一次 **Save-Help** 命令，下载限制为每个模块 1 GB 的未压缩内容，并且用于模块的帮助文件仅在比计算机上的文件更新时才进行安装。

每日一次限制会保护托管帮助文件的服务器，并使你能够将 **Save-help** 命令添加到 PowerShell 配置文件。

若要在没有 *Force* 参数的情况下，为多个 UI 区域性中的模块保存帮助，请将所有 UI 区域性包括在同一命令中，例如：`Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedModule

指定名称以 ModuleSpecification 对象的形式指定的模块。
MSDN library 中的 [ModuleSpecification 构造函数 (哈希表) ](https://msdn.microsoft.com/library/jj136290) 的 "备注" 部分对此进行了说明。
例如， *FullyQualifiedModule* 参数接受以 @ {ModuleName = "ModuleName" 格式指定的模块名称;ModuleVersion = "version_number"} 或 @ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}。
**ModuleName** 和 **ModuleVersion** 是必需的，但 **Guid** 是可选的。

不能在与 *Module* 参数相同的命令中指定 *FullyQualifiedModule* 参数。

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

指定目标文件夹的路径。
与 *DestinationPath* 参数的值不同， *LiteralPath* 参数的值严格按照所键入的形式使用。
不会将任何字符解释为通配字符。
如果路径包括转义符，请将其括在单引号中。
单引号指示 PowerShell 不要将任何字符解释为转义序列。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module

指定此 cmdlet 为其下载帮助的模块。
在以逗号分隔的列表中输入一个或多个模块名称或名称模式，或在每行上有一个模块名称的文件中输入。
允许使用通配符。
还可以通过管道将模块对象从 Get-Module cmdlet 传递到 **Save-Help** 。

默认情况下， **Save-Help** 将为支持可更新帮助的所有模块以及安装在本地计算机（位于在 **PSModulePath** 环境变量中列出的某个位置内）上的模块下载帮助。

若要为未安装在计算机上的模块保存帮助，请在远程计算机上运行 **get-help** 命令。
然后，通过管道将生成的模块对象传递给 **Save-Help** cmdlet 或作为 *Module* 或 *InputObject* 参数的值提交模块对象。

如果你指定的模块安装在计算机上，你可以输入模块名称或模块对象。
如果该模块未安装在计算机上，则必须输入一个模块对象，例如由 **Get-Module** cmdlet 返回的一个对象。

**Get-help** Cmdlet 的 *module* 参数不接受模块文件或模块清单文件的完整路径。
若要为不在 **PSModulePath** 位置的模块保存帮助，请将模块导入到当前会话中，然后运行 **save-help** 命令。

值为 "*" (所有) 尝试为计算机上安装的所有模块更新帮助。
这包括不支持可更新帮助的模块。
当该命令遇到不支持可更新帮助的模块时，此值可能会生成错误。

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UICulture

指定此 cmdlet 为其获取更新的帮助文件的 UI 区域性值。
输入一个或多个语言代码，例如 es、包含区域性对象的变量或用于获取区域性对象的命令，如 Get-Culture 或 Get-UICulture 命令。

不允许使用通配符。
不要指定部分语言代码，例如 "de"。

默认情况下， **Save-Help** 在为 Windows 设置的 UI 区域性或其回退区域性中获取帮助文件。
如果指定 *UICulture* 参数，则 " **保存帮助" 将** 仅为指定的 UI 区域性查找帮助，而不会在任何回退区域性中查找帮助。

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredentials

指示此 cmdlet 用当前用户的凭据运行命令，包括 web 下载。
默认情况下，在没有显式凭据的情况下运行该命令。

仅当 Web 下载使用 NTLM、协商或基于 Kerberos 的身份验证时，此参数才有效。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.Management.Automation.PSModuleInfo

可以通过管道将模块对象从 **get-help** cmdlet 传递给 **Save-Help** 的 *module* 参数。

## 输出

### 无

此 cmdlet 将不生成任何输出。

## 注释

* 若要为 $pshome \Modules 文件夹中的模块保存帮助，请使用 "以管理员身份运行" 选项启动 PowerShell。 只有计算机上 Administrators 组的成员才能为 $pshome \Modules 文件夹中的模块下载帮助。
* 为每个模块保存的帮助都包括一个帮助信息 (HelpInfo XML) 文件和一个适用于帮助文件各种 UI 区域性的 Cabinet (.cab) 文件。 你不必从 cabinet 文件中提取帮助文件。 Update-Help cmdlet 将提取帮助文件、验证 XML，然后将帮助文件和帮助信息文件安装在 module 文件夹的特定于语言的子文件夹中。
* **Save-Help** cmdlet 可以为未安装在计算机上的模块保存帮助。 但是，由于帮助文件安装在模块文件夹中，因此 **update-help** cmdlet 仅可为计算机上安装的模块安装更新的帮助文件。
* 如果 **Save-Help** 找不到模块的更新帮助文件，或者找不到指定语言的更新帮助文件，它将继续以静默方式显示，而不会显示错误消息。 若要查看命令保存了哪些文件，请指定 *详细* 参数。
* 模块是可更新帮助的最小单位。 不能为特定 cmdlet 保存帮助，只保存模块中的所有 cmdlet。 若要查找包含特定 cmdlet 的模块，请结合使用 **ModuleName** 属性和 Get-Command cmdlet，例如 `(Get-Command \<cmdlet-name\>).ModuleName`
* **Save-Help** 支持所有模块和 PowerShell Core 管理单元。它不支持任何其他管理单元。
* **Update-help** 和 **Save-help** cmdlet 使用以下端口下载帮助文件：用于 HTTP 的端口80和用于 HTTPS 的端口443。
* **Update-Help** 和 **Save-Help** cmdlet 在 Windows 预安装环境 (Windows PE) 上不受支持。

## 相关链接

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Update-Help](Update-Help.md)
