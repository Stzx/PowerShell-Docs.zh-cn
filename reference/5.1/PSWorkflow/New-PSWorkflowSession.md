---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197771"
---
# New-PSWorkflowSession

## 摘要
创建工作流会话。

## SYNTAX

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## DESCRIPTION

`New-PSWorkflowSession`Cmdlet 将创建一个用户管理的会话 ( **PSSession** ) ，该会话特别设计用于运行 Windows PowerShell 工作流。 它使用 Microsoft.PowerShell.Workflow 会话配置，其中包括脚本、类型和格式设置文件，以及工作流所需的选项。

可以使用 `New-PSWorkflowSession` 或其别名 `nwsn` 。

你还可以将工作流通用参数添加到此命令。 有关工作流通用参数的详细信息，请参阅 [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：在远程计算机上创建工作流会话

此示例在 ServerNode01 远程计算机上创建 **WorkflowTests** 会话。

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

**SessionOption** 参数的值是一个 `New-PSSessionOption` 命令，用于将会话中的输出缓冲模式设置为 **丢弃** 。

### 示例 2：在多台远程计算机上创建工作流会话

此示例在 ServerNode01 和 Server12 计算机上创建工作流会话。 该命令使用 **Credential** 参数以通过域管理员权限运行。

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

该命令使用 **ThrottleLimit** 参数以将每个命令的中止值增加到 150。
此值优先于在 **Microsoft. Workflow** 会话配置中设置的默认限制（100）。

## PARAMETERS

### -ApplicationName

指定连接 URI 的应用程序名称段。

默认值为 `$PSSessionApplicationName` 本地计算机上首选项变量的值。 如果未定义此首选项变量，则默认值为 WSMAN。 该值适用于大多数使用情况。 有关详细信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。

WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。
此参数的值应与远程计算机上的侦听器的 **URLPrefix** 属性值匹配。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentication

指定用于对用户的凭据进行身份验证的机制。
此参数的可接受值为：

- 默认
- 基本
- Credssp
- 摘要
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

默认值为 Default。

CredSSP 身份验证仅在 Windows Vista、Windows Server 2008 和更高版本的 Windows 操作系统中可用。

有关此参数的值的详细信息，请参阅 [System.management.automation.runspaces.authenticationmechanism 枚举](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。

> [!CAUTION]
> 凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。 此机制增加了远程操作的安全风险。 如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

指定有权执行此操作的用户帐户的数字公钥证书 (X509)。 输入证书的证书指纹。

在基于客户端证书的身份验证中使用证书。 证书只能映射到本地用户帐户，而不适用于域帐户。

若要获取证书指纹，请 `Get-Item` `Get-ChildItem` 在 Windows PowerShell Cert：驱动器中使用 cmdlet 或 cmdlet。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

创建 ( **PSSession** ) 到指定计算机的持续性连接。 如果输入多个计算机名称，Windows PowerShell 将创建多个 **pssession** ，每台计算机一个。 默认为本地计算机。

键入一台或多台远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入该计算机名称、localhost 或句点 (.)。 当计算机与用户处于不同的域中时，必须使用完全限定的域名。 还可以通过管道将计算机名称传递给 `New-PSWorkflowSession` 。

若要在 **ComputerName** 参数的值中使用 IP 地址，该命令必须包括 **Credential** 参数。 此外，必须为计算机配置 HTTPS 传输，或者必须在本地计算机上的 WinRM TrustedHosts 列表中包含远程计算机的 IP 地址。 有关将计算机名称添加到 TrustedHosts 列表的说明，请参阅 [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)中的 "如何将计算机添加到受信任的主机列表中"。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认为当前用户。 键入用户名，如 User01、Domain01\User01 或 User@Domain.com ，或输入 **PSCredential** 对象，如 cmdlet 返回的一个 PSCredential 对象 `Get-Credential` 。

键入用户名时，此 cmdlet 会提示输入密码。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

指示此 cmdlet 将交互式安全令牌添加到环回会话。 通过交互式令牌，你可以在环回会话中运行用于获取其他计算机中的数据的命令。 例如，你可以在该会话中运行用于将 XML 文件从远程计算机复制到本地计算机的命令。

环回会话是在同一计算机上开始并终止的 **PSSession** 。 若要创建环回会话，请不要指定 ComputerName  参数，或将其值设置为“.”、localhost 或本地计算机的名称。

默认情况下，创建的环回会话具有网络令牌，该令牌提供的权限可能不足以对远程计算机进行身份验证。

**EnableNetworkAccess** 参数仅在环回会话中有效。 如果在远程计算机上创建会话时指定 EnableNetworkAccess  参数，该命令将成功，但会忽略此参数。

通过用于将会话凭据委派给其他计算机的 **CredSSP** 参数的 **Authentication** 值，你还可以在环回会话中进行远程访问。

若要保护计算机免受恶意访问，断开连接的具有交互式令牌（使用 **EnableNetworkAccess** 参数创建）的环回会话只能通过创建该会话的计算机重新连接。 断开连接的使用 CredSSP 身份验证的会话可通过其他计算机重新连接。 有关详细信息，请参阅 `Disconnect-PSSession` cmdlet。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

指定工作流会话的友好名称。 可以将该名称与其他 cmdlet （例如和）一起使用 `Get-PSSession` `Enter-PSSession` 。 对于计算机或当前会话，该名称无需是唯一的。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

指定远程计算机上用于此连接的网络端口。 若要连接到一台远程计算机，则必须在该连接所用的端口上侦听远程计算机。 对于 HTTP) ，默认端口为 5985 (WinRM 端口5986， (HTTPS 的 WinRM 端口) 。

使用其他端口之前，必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。 使用以下命令配置侦听器：

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

除非必要，否则不要使用 **Port** 参数。 命令中的端口设置适用于运行该命令的所有计算机或会话。 备用端口设置可能会阻止在所有计算机上运行该命令。

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

### -SessionOption

为该会话指定高级选项。 输入一个 **SessionOption** 对象，例如使用 cmdlet 创建的对象 `New-PSSessionOption` 。

选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。 否则，通过在会话配置中设置的选项创建默认值。

会话选项值优先于在 `$PSSessionOption` 首选项变量和会话配置中设置的会话的默认值。 但是，它们不优先于在会话配置中设置的最大值、配额或限制。 有关会话配置的详细信息，请参阅 [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)。

有关会话选项（包括默认值）的说明，请参阅 `New-PSSessionOption` 。
有关 `$PSSessionOption` 首选项变量的信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定为运行此命令可建立的并发连接的最大数目。
如果省略此参数或输入值 0 (零) ，则使用 **microsoft.powershellworkflow** 会话配置的默认值100。

节流限制仅适用于当前命令，而不适用于会话或计算机。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

指示此 cmdlet 使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。 默认情况下，不使用 SSL。

WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。 **UseSSL** 参数是一种额外的保护措施，它通过 HTTPS 连接而不是 HTTP 连接来发送数据。

如果指定此参数，但 SSL 在用于命令的端口上不可用，则命令将失败。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.Management.Automation.Runspaces.PSSession[]、System.String

可以通过管道将会话或计算机名称传递给此 cmdlet。

## 输出

### System.Management.Automation.Runspaces.PSSession

## 注释

`New-PSWorkflowSession`命令等效于以下命令：

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## 相关链接

[Disconnect-PSSession](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSTransportOption](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[Register-PSSessionConfiguration](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
