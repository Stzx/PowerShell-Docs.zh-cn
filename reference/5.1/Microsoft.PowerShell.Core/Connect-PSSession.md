---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: d4f071b4c106735e622281f728b8632c211a813d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198992"
---
# Connect-PSSession

## 摘要
重新连接到已断开连接的会话。

## SYNTAX

### Name（默认值）

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 会话

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 计算机名

```
Connect-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerNameGuid

```
Connect-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUri

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUriGuid

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ID

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

**Connect-PSSession** cmdlet 可重新连接到已断开连接 ( **pssession** ) 的用户管理的 Windows PowerShell 会话。
它可以在有意断开连接的会话（例如通过使用 Disconnect-PSSession cmdlet 或 Invoke-Command cmdlet 的 *InDisconnectedSession* 参数）和无意断开连接的会话（例如由于临时网络故障）上运行。

**Connect-PSSession** 可以连接到由同一用户启动的任何已断开连接的会话。
其中包括通过其他计算机上的其他会话启动或断开连接。

但是， **Connect-PSSession** 无法连接到已损坏的或已关闭的会话或者通过使用 Enter-PSSession cmdlet 启动的交互式会话。
此外，也无法将会话连接到由其他用户启动的会话，除非你能提供创建会话的用户的凭据。

有关断开连接会话的功能的详细信息，请参阅 [about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md)。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：重新连接到会话

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

此命令重新连接到 Server01 计算机上的 ITTask 会话。

该输出显示此命令已成功。
此时将打开会话的 **状态** ，并且 **可用性** 可用，这表示你可以在该会话中运行命令。

### 示例2：断开连接和重新连接的影响

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

此示例显示了断开某一会话的连接又重新连接到该会话的效果。

第一个命令使用 Get-PSSession cmdlet。
在没有 *ComputerName* 参数的情况下，该命令仅获取已在当前会话中创建的会话。

该输出显示此命令可获取本地计算机上的 Backup 会话。
会话 **状态** 已打开且 **可用性** 可用。

第二个命令使用 **get-help** cmdlet 获取在当前会话中创建的 **PSSession** 对象，并使用 **disconnect-pssession** cmdlet 断开这些会话的连接。
该输出显示 Backup 会话已断开连接。
会话的 **状态** 为 "已断开连接" 且 **可用性** 为 "无"。

第三个命令使用 **get-help** cmdlet 获取在当前会话中创建的 **PSSession** 对象，并使用 **Connect-pssession** cmdlet 来重新连接会话。
该输出显示 Backup 会话已重新连接。
会话 **状态** 已打开且 **可用性** 可用。

如果在未断开连接的会话上使用 **Connect-PSSession** cmdlet，则该命令不会影响会话，并且不会生成任何错误。

### 示例3：企业方案中的一系列命令

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts Windows PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes Windows PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

这一系列的命令演示 **Connect-PSSession** cmdlet 在企业方案中的可能的使用方式。
在此示例中，系统管理员将在远程计算机上的会话中启动长时间运行的作业。
启动该作业后，管理员将断开与该会话的连接，然后下班回家。
在晚上晚，管理员登录到她的家庭计算机，并验证作业是否已完成。

## PARAMETERS

### -AllowRedirection

指示此 cmdlet 允许将此连接重定向到备用 URI。

使用 *ConnectionURI* 参数时，远程目标将返回一个指令，以重定向到不同的 URI。
默认情况下，Windows PowerShell 不会重定向连接，但你可以使用此参数允许它重定向连接。

你也可以通过更改 **MaximumConnectionRedirectionCount** 会话选项值，限制重定向连接的次数。
使用 New-PSSessionOption cmdlet 的 *MaximumRedirection* 参数或设置 **$PSSessionOption** 首选项变量的 **MaximumConnectionRedirectionCount** 属性。
默认值为 5。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

指定应用程序的名称。
此 cmdlet 仅连接到使用指定应用程序的会话。

输入连接 URI 的应用程序名称段。
例如，在以下连接 URI 中，应用程序名称为 WSMan：`http://localhost:5985/WSMAN`。
会话的应用程序名称存储在该会话的 **Runspace.ConnectionInfo.AppName** 属性中。

此参数的值用于选择和筛选会话。
它不会更改会话使用的应用程序。

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentication

指定用于对命令中的用户凭据进行身份验证的机制，以便重新连接到断开连接的会话。 此参数的可接受值为：

- 默认
- 基本
- Credssp
- 摘要
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

默认值为 Default。

有关此参数的值的详细信息，请参阅 MSDN 库中的 [System.management.automation.runspaces.authenticationmechanism 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 。

警告：凭据安全支持提供程序 (CredSSP) 身份验证，其中用户的凭据将传递给要进行身份验证的远程计算机，其适用于需要在多个资源（例如访问远程网络共享）上进行身份验证的命令。
此机制增加了远程操作的安全风险。
如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

指定有权连接到断开连接的会话的用户帐户的数字公钥证书 (X509)。 输入证书的证书指纹。

在基于客户端证书的身份验证中使用证书。
它们只能映射到本地用户帐户。
它们不适用于域帐户。

若要获取证书指纹，请在 Windows PowerShell Cert: 驱动器中使用 Get-Item 或 Get-ChildItem 命令。

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

指定在其中存储断开连接的会话的计算机。
会话存储在位于连接的服务器端或接收端的计算机上。
默认为本地计算机。

键入计算机的 NetBIOS 名称、IP 地址或完全限定的域名。
不允许使用通配符。
若要指定本地计算机，请键入计算机名称、localhost 或点 (。 ) 

```yaml
Type: System.String[]
Parameter Sets: ComputerName, ComputerNameGuid
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

只连接到使用指定会话配置的会话。

输入会话配置的配置名称或完全限定的资源 URI。
如果只指定配置名称，则会预置以下架构 URI： `http://schemas.microsoft.com/powershell` 。
会话的配置名称存储在该会话的 **ConfigurationName** 属性中。

此参数的值用于选择和筛选会话。
它不会更改会话使用的会话配置。

有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

为断开连接的会话指定连接终结点的 Uri。

URI 必须完全限定。
此字符串的格式如下：

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

默认值如下：

`http://localhost:5985/WSMAN`

如果未指定连接 URI，则可以使用 *UseSSL* 和 *Port* 参数指定连接 uri 值。

URI 的 **Transport** 段的有效值为 HTTP 和 HTTPS。
如果使用 Transport 段指定连接 URI，但不指定端口，将使用以下标准端口来创建会话：80 用于 HTTP，443 用于 HTTPS。
若要使用 Windows PowerShell 远程处理的默认端口，请指定 HTTP 端口 5985 或 HTTPS 端口 5986。

如果目标计算机将连接重定向到另一个 URI，Windows PowerShell 将阻止重定向，除非你在命令中使用了 *AllowRedirection* 参数。

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

指定有权连接到断开连接的会话的用户帐户。
默认为当前用户。

键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。 如果键入用户名，系统会提示输入密码。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

指定断开连接的会话的 ID。
仅当断开连接的会话之前已连接到当前会话时， *Id* 参数才有效。

如果会话存储在本地计算机上，但未连接到当前会话，则此参数是有效的，但并未生效。

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

指定断开连接的会话的实例 ID。

实例 ID 是一个 GUID，用于在本地或远程计算机上唯一标识 **PSSession** 。

实例 ID 存储在 **PSSession** 的 **InstanceID** 属性中。

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

指定断开连接的会话的友好名称。

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

指定远程计算机上用于重新连接到会话的网络端口。
若要连接到一台远程计算机，则必须在该连接所用的端口上侦听远程计算机。
默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。

使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。
若要配置侦听器，请在 Windows PowerShell 提示符下键入以下两个命令：

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

除非必要，否则不要使用 *Port* 参数。
在命令中设置的端口适用于运行该命令的所有计算机或会话。
备用端口设置可能会阻止在所有计算机上运行该命令。

```yaml
Type: System.Int32
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

指定断开连接的会话。
输入包含 **pssession** 对象的变量或创建或获取 **pssession** 对象的命令，如 Get-PSSession 命令。

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

为该会话指定高级选项。
输入 **SessionOption** 对象（例如使用 New-PSSessionOption cmdlet 创建的对象），或输入哈希表，其中的键是会话选项名称，而值是会话选项值。

这些选项的默认值由 $PSSessionOption 首选项变量的值（如果已设置）确定。
否则，通过在会话配置中设置的选项创建默认值。

会话选项值优先于在 $PSSessionOption 首选项变量和会话配置中设置的会话的默认值。
但是，它们不优先于在会话配置中设置的最大值、配额或限制。

有关包括默认值的会话选项的说明，请参阅 PSSessionOption。
有关 **$PSSessionOption** 首选项变量的信息，请参阅 [about_Preference_Variables](About/about_Preference_Variables.md)。
有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定为运行此命令可建立的并发连接的最大数目。
如果省略此参数或输入 0 值，则使用默认值 32。

节流限制仅适用于当前命令，而不适用于会话或计算机。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

指示此 cmdlet 使用安全套接字层 (SSL) 协议连接到断开连接的会话。 默认情况下，不使用 SSL。

WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。
*UseSSL* 参数是一种额外的保护措施，它通过 HTTPS 连接而不是 HTTP 连接来发送数据。

如果使用此参数，但 SSL 在用于此命令的端口上不可用，则该命令将失败。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

提示你在运行 cmdlet 之前进行确认。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。
此 cmdlet 未运行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216) 。

## 输入

### System.Management.Automation.Runspaces.PSSession

可以通过管道将会话 ( **PSSession** ) 传递给此 cmdlet。

## 输出

### System.Management.Automation.Runspaces.PSSession

此 cmdlet 将返回一个对象，该对象表示其重新连接到的会话。

## 注释

* **Connect-PSSession** 仅重新连接到已断开连接的会话，即， **状态** 属性的值为 "已断开连接" 的会话。 只有连接到或结束运行 Windows PowerShell 3.0 或更高版本的计算机的会话才能断开和重新连接。
* 如果在未断开连接的会话上使用 **Connect-PSSession** ，则该命令不会影响会话，并且不会生成错误。
* 与使用 *EnableNetworkAccess* 参数创建的交互式令牌断开连接的环回会话只能通过创建该会话的计算机重新连接。 此限制可使计算机免遭恶意访问。
* **PSSession** 的 **State** 属性值相对于当前会话。
因此，值 "已 **断开连接** " 意味着 **PSSession** 未连接到当前会话。 但是，它并不意味着 **PSSession** 会与所有会话断开连接。 它可能连接到另一个会话。 若要确定是否可以连接或重新连接到该会话，请使用 **Availability** 属性。

  **Availability** 的 None 值指示可连接会话。
值为 "忙碌" 指示你无法连接到 **PSSession** ，因为它已连接到另一个会话。

  有关会话 **状态** 属性的值的详细信息，请参阅 MSDN library 中的 [RunspaceState 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) 。

  有关会话的 **可用性** 属性值的详细信息，请参阅 MSDN 库中的 [runspacestate 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) 。

* 当你连接到 **pssession** 时，你无法更改 **PSSession** 的空闲超时值。 **Connect-PSSession** 的 *SessionOption* 参数采用值为 **IdleTimeout** 的 **SessionOption** 对象。 但是，在连接到 **PSSession** 时，将忽略 **SessionOption** 对象的 **idletimeout** 值和 $PSSessionOption 变量的 **idletimeout** 值。

  您可以在创建 **pssession** 时，通过使用 **新的 Pssession** 或 **调用命令** cmdlet 以及从 **PSSession** 断开连接来设置和更改 **pssession** 的空闲超时。

  **PSSession** 的 **IdleTimeout** 属性对断开连接的会话至关重要，因为它确定断开连接的会话在远程计算机上保留的时间。
断开连接的会话从其断开连接的时刻起就被视为空闲，即使命令正在断开连接的会话中运行也是如此。

## 相关链接

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)
