---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 26c4f8c8dcc1fbd56e29f55a6a8c2e6aa37a2842
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "93200731"
---
# Get-Credential

## 摘要
获取基于用户名和密码的凭据对象。

## SYNTAX

### CredentialSet（默认值）

```
Get-Credential [-Credential] <PSCredential> [<CommonParameters>]
```

### MessageSet

```
Get-Credential -Message <String> [[-UserName] <String>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Credential`Cmdlet 将为指定的用户名和密码创建凭据对象。 你可以在安全操作中使用凭据对象。

从 PowerShell 3.0 开始，可以使用 **Message** 参数在提示用户输入其名称和密码的对话框中指定自定义消息。

该 `Get-Credential` cmdlet 会提示用户输入密码或用户名和密码。 默认情况下，将显示一个身份验证对话框来提示用户。 但是，在某些主机程序（例如 PowerShell 控制台）中，你可以通过更改注册表项来在命令行处提示用户。 有关此注册表项的详细信息，请参阅说明和示例。

## 示例

### 示例 1

```powershell
$c = Get-Credential
```

此命令将获取凭据对象，并将其保存在 `$c` 变量中。

当你输入命令时，将显示一个请求输入用户名和密码的对话框。 输入所需的信息时，该 cmdlet 将创建一个表示用户凭据的 **PSCredential** 对象，并将其保存在 `$c` 变量中。

你可以将对象用作请求用户身份验证的 cmdlet（例如，具有 **Credential** 参数的 cmdlet）的输入。 但是，某些随 PowerShell 一起安装的提供程序不支持 **Credential** 参数。

### 示例 2

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

这些命令使用 cmdlet 返回的凭据对象对 `Get-Credential` 远程计算机上的用户进行身份验证，以便它们可以使用 Windows Management Instrumentation (WMI) 来管理计算机。

第一个命令将获取凭据对象，并将其保存在 `$c` 变量中。 第二个命令使用命令中的凭据对象 `Get-CimInstance` 。 此命令将获取 Server01 计算机上有关磁盘驱动器的信息。

### 示例 3

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

此命令显示如何将命令包含 `Get-Credential` 在命令中  `Get-CimInstance` 。

此命令使用 `Get-CimInstance` cmdlet 来获取有关 Server01 计算机上的 BIOS 的信息。 它使用 **credential** 参数对 user、Domain01\User01 和 `Get-Credential` command 作为 **Credential** 参数的值进行身份验证。

### 示例 4

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

此示例将创建一个包含用户名（不带域名）的凭据。

第一个命令获取用户名为 User01 的凭据，并将其存储在 `$c` 变量中。
第二个命令将显示生成的凭据对象的 **Username** 属性值。

### 示例 5

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

此命令使用 **PromptForCredential** 方法提示用户输入其用户名和密码。 该命令将生成的凭据保存在 `$Credential` 变量中。

**PromptForCredential** 方法是使用 cmdlet 的替代方法 `Get-Credential` 。 使用 **PromptForCredential** 时，你可以指定要在消息框中显示的标题、消息和用户名。

有关详细信息，请参阅 SDK 中的 [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) 文档。

### 示例 6

```powershell
Set-ItemProperty "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds" -Name ConsolePrompting -Value $true
```

此示例显示了如何修改注册表，以便在命令行处（而不是使用对话框）提示用户。

该命令将创建 **ConsolePrompting** 注册表项，并将其值设置为 True。 若要运行此命令，请以 "以管理员身份运行" 选项启动 PowerShell。

若要将对话框用于提示，请将 ConsolePrompting 的值设置为 false ($false) 或使用 cmdlet 将 `Remove-ItemProperty` 其删除。

ConsolePrompting 注册表项在某些主机程序（例如 PowerShell 控制台）中有效。 它并非在所有主机程序中都有效。

### 示例 7

此示例演示如何创建一个与不提示用户就返回的对象完全相同的凭据对象 `Get-Credential` 。 此方法要求输入纯文本密码，这可能会违反某些企业内的安全标准。

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

第一个命令将用户帐户名称保存在 `$User` 参数中。 该值必须具有“Domain\User”或“ComputerName\User”格式。

第二个命令使用 `ConvertTo-SecureString` cmdlet 从纯文本密码创建一个安全字符串。 该命令使用 **AsPlainText** 参数来指示该字符串为纯文本，并使用 **Force** 参数来确认你了解使用纯文本的风险。

第三个命令使用 `New-Object` cmdlet 从和变量中的值创建 **PSCredential** 对象 `$User` `$PWord` 。

### 示例 8

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

此命令使用 cmdlet 的 **Message** 和 **UserName** 参数 `Get-Credential` 。 此命令格式旨在用于共享的脚本和函数。 在此示例中，消息将告知用户为何需要凭据，并使他们能够确信此请求是合法的。

### 示例 9

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

此命令将从 Server01 远程计算机获取凭据。 该命令使用 `Invoke-Command` cmdlet `Get-Credential` 在远程计算机上运行命令。 输出显示 `Get-Credential` 在身份验证提示中包含的远程安全消息。

## PARAMETERS

### -Credential

指定凭据的用户名，例如 **User01** 或 **Domain01\User01** 。 参数名称 `-Credential` 是可选的。

提交该命令并指定用户名时，系统将提示你输入密码。 如果省略此参数，系统会提示输入用户名和密码。

从 PowerShell 3.0 开始，如果输入的用户名没有域，则不再在 `Get-Credential` 名称之前插入反斜杠。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Message

指定将在身份验证提示中显示的消息。 此参数旨在用于函数或脚本。 你可以使用该消息向用户说明你为什么要请求凭据以及将如何使用它们。

此参数是在 PowerShell 3.0 中引入的。

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

指定用户名。 身份验证提示要求输入该用户名对应的密码。 默认情况下，用户名为空并且身份验证提示将请求输入用户名和密码。

如果身份验证提示显示在对话框中，用户可以编辑指定的用户名。
但是，如果提示显示在命令行处，则用户不能更改用户名。 在共享的函数或脚本中使用此参数时，请考虑所有可能的显示情况。

此参数是在 PowerShell 3.0 中引入的。

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给此 cmdlet。

## 输出

### System.Management.Automation.PSCredential

`Get-Credential` 返回凭据对象。

## 注释

你可以使用 **PSCredential** `Get-Credential` 在请求用户身份验证的 cmdlet （例如，具有 **Credential** 参数的 Cmdlet）中创建的 PSCredential 对象。

默认情况下，身份验证提示显示在对话框中。 若要在命令行处显示身份验证提示，请添加 **ConsolePrompting** 注册表条目 (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) 并将其值设置为 **True** 。
如果 **ConsolePrompting** 注册表项不存在或者如果其值为 False，则身份验证提示将显示在对话框中。 有关说明，请参阅示例。

**ConsolePrompting** 注册表项在 PowerShell 控制台中运行，但在所有主机程序中都不起作用。

例如， (ISE) ，它在 PowerShell 集成脚本环境中不起作用。 有关 **ConsolePrompting** 注册表项的影响的信息，请参阅主机程序的帮助主题。

与 PowerShell 一起安装的所有提供程序都不支持 **Credential** 参数。
从 PowerShell 3.0 开始，在 select cmdlet （如和 cmdlet）上受 `Get-Content` 支持 `New-PSDrive` 。

## 相关链接

[PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
