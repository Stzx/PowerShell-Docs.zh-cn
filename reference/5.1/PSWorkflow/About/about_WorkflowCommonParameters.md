---
description: 本主题介绍对所有 Windows PowerShell 工作流命令有效的参数。 由于 Windows PowerShell 引擎会将它们添加到工作流，因此你可以在任何工作流上使用这些参数，并且这些参数会在你创作的工作流上自动启用。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflowcommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WorkflowCommonParameters
ms.openlocfilehash: 386200475c1dab9735921edd60abbde20ee354c4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199894"
---
# <a name="about-workflowcommonparameters"></a>关于 WorkflowCommonParameters

## <a name="short-description"></a>简短说明

本主题介绍对所有 Windows PowerShell 工作流命令有效的参数。 由于 Windows PowerShell 引擎会将它们添加到工作流，因此你可以在任何工作流上使用这些参数，并且这些参数会在你创作的工作流上自动启用。

## <a name="long-description"></a>详细说明

Windows PowerShell 工作流通用参数是一组可用于所有 Windows PowerShell 工作流和活动的 cmdlet 参数。 它们是由 Windows PowerShell 工作流引擎添加的，而不是由工作流作者添加的，它们会自动提供工作流和活动。 但是，嵌套三个层次的工作流不支持任何通用参数，包括工作流通用参数。

所有工作流参数均为可选且命名 (不是位置) 。 它们不从管道中获取输入。

大多数工作流通用参数都有 PS 前缀，例如 `PSComputerName` 和 `PSCredential` 。 PS 前缀参数配置目标计算机的连接和执行环境，也称为 "远程节点"。

许多工作流常见参数（例如 `PSAllowRedirection` 和）的 `AsJob` 名称类似于 Windows PowerShell 远程处理和后台作业中使用的参数。 这些参数的工作方式与名称类似的远程处理和作业参数的工作方式相同，因此你可以使用在远程处理和作业中开发的知识来管理工作流。

工作流在 Windows PowerShell 3.0 中引入。

### <a name="parameter-descriptions"></a>参数说明

本节介绍工作流通用参数。

#### <a name="-asjob-switchparameter"></a>-AsJob \<SwitchParameter\>

将工作流作为工作流作业运行。 工作流命令立即返回表示父作业的对象。 父作业包含在每台目标计算机上运行的子作业。 若要管理作业，请使用 Job cmdlet。 若要获取作业结果，请使用 [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job)。

#### <a name="-jobname-string"></a>-JobName \<String\>

指定工作流作业的友好名称。 默认情况下，作业将命名为“Job\<n\>”，其中 \<n\> 是一个序号。

如果在工作流命令中使用 JobName 参数，则工作流将作为作业运行，并且工作流命令返回一个作业对象，即使未 `AsJob` 在该命令中包含参数也是如此。

有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)。

#### <a name="-psallowredirection-switchparameter"></a>-PSAllowRedirection \<SwitchParameter\>

允许将连接重定向到目标计算机。

使用 `PSConnectionURI` 参数时，远程目标将返回一个指令，以重定向到不同的 URI。 默认情况下，Windows PowerShell 不会重定向连接，但你可以使用 `PSAllowRedirection` 参数来允许将连接重定向到目标计算机。

还可以通过设置 `MaximumConnectionRedirectionCount` `$PSSessionOption` 首选项变量的属性或的值的属性，限制重定向连接的次数 `MaximumConnectionRedirectionCount` `PSSessionOption parameter` 。 默认值为 5。 有关详细信息，请参阅参数的说明 `PSSessionOption` 和 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。

#### <a name="-psapplicationname-string"></a>-PSApplicationName \<String\>

指定连接 URI 的应用程序名称段，该连接 URI 用于连接到目标计算机。 当你未在命令中使用参数时，请使用此参数指定应用程序名称 `ConnectionURI` 。

默认值为 `$PSSessionApplicationName` 本地计算机上首选项变量的值。 如果未定义此首选项变量，则默认值为 WSMAN。 该值适用于大多数使用情况。 有关详细信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。

WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。 此参数的值应与 `URLPrefix` 远程计算机上侦听器的属性的值相匹配。

#### <a name="-psauthentication-authenticationmechanism"></a>-PSAuthentication \<AuthenticationMechanism\>

指定在连接到目标计算机时用于对用户的凭据进行身份验证的机制。

有效值是：

- **默认**
- **基本**
- **Credssp**
- 摘要式
- **Kerberos**
- **沟通**
- **NegotiateWithImplicitCredential**

默认值为 **Default** 。

有关此参数的值的信息，请参阅 `System.Management.Automation.Runspaces.AuthenticationMechanism` MSDN 中枚举的说明。

> [!WARNING]
> 在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。 此机制增加了远程操作的安全风险。 如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

#### <a name="-psauthenticationlevel-authenticationlevel"></a>-PSAuthenticationLevel \<AuthenticationLevel\>

指定与目标计算机的连接的身份验证级别。
默认值为 **Default** 。

有效值是：

|名称 |说明 |
|---------|---------|
|**不变** | 身份验证级别与前一个命令相同。 |
|**默认** | Windows 身份验证。 |
|无  | 没有 COM 身份验证。   |
|**“连接”** | 连接级的 COM 身份验证。|
|**调用** | 调用级的 COM 身份验证。   |
|**数据包** | 数据包级的 COM 身份验证。|
|**PacketIntegrity** | 数据包完整性级别的 COM 身份验证。  |
|**PacketPrivacy** | 数据包保密性级别的 COM 身份验证。 |

#### <a name="-pscertificatethumbprint-string"></a>-PSCertificateThumbprint \<String\>

指定有权执行此操作的用户帐户的数字公钥证书 (X509)。 输入证书的证书指纹。

在基于客户端证书的身份验证中使用证书。 证书只能映射到本地用户帐户，而不适用于域帐户。

若要获取证书，请使用 [Get 项](xref:Microsoft.PowerShell.Management.Get-Item) 或 [get-childitem] (。/../Microsoft.PowerShell.Management/Get-Childitem.md) Windows PowerShell Cert：驱动器中的 cmdlet。

#### <a name="-pscomputername-string"></a>-PSComputerName \<String[]\>

指定作为工作流目标节点的计算机的列表。
工作流中的命令或活动在使用此参数指定的计算机上运行。 默认为本地计算机。

在以逗号分隔的列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入该计算机名称、“localhost”或句点 (.)。

若要将本地计算机包含在参数的值中 `PSComputerName` ，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。

如果从命令中省略此参数，或值为 `$null` 或空字符串，则工作流目标为本地计算机，并且不使用 Windows PowerShell 远程处理来运行命令。

若要在参数的值中使用 IP 地址 `ComputerName` ，该命令必须包含 `PSCredential` 参数。 此外，必须为计算机配置 HTTPS 传输，或者必须在本地计算机上的 WinRM TrustedHosts 列表中包含远程计算机的 IP 地址。 有关将计算机名称添加到 TrustedHosts 列表的说明，请参阅 [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)中的 *"如何将计算机添加到受信任的主机列表中"* 。

#### <a name="-psconfigurationname-string"></a>-PSConfigurationName \<String\>

指定用于在目标计算机上配置会话的会话配置。 在目标计算机上输入会话配置， (不是工作流服务器计算机) 。 默认值为 `Microsoft.PowerShell.Workflow`。

#### <a name="-psconnectionretrycount-uint"></a>-PSConnectionRetryCount \<UInt\>

指定第一次连接尝试失败时连接到每台目标计算机的最大尝试次数。 输入介于1到 4294967295 (UInt) 之间的数字。 默认值为零 (0) 表示不重试尝试。

#### <a name="-psconnectionretryintervalsec-uint"></a>-PSConnectionRetryIntervalSec \<UInt\>

指定连接重试尝试之间的延迟（以秒为单位）。 默认值为零 (0)。 仅当 PSConnectionRetryCount 的值为1时，此参数才有效。

#### <a name="-psconnectionuri-systemuri"></a>-PSConnectionURI \<System.Uri\>

指定 (URI) 的统一资源标识符，该标识符定义目标计算机上的工作流的连接终结点。 URI 必须完全限定。

此字符串的格式如下：

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

默认值是 `http://localhost:5985/WSMAN`。

如果未指定 `PSConnectionURI` ，则可以使用 `PSUseSSL` 、 `PSComputerName` 、 `PSPort` 和 `PSApplicationName` 参数指定 `PSConnectionURI` 值。

URI 的传输段的有效值为 **HTTP** 和 **HTTPS** 。
如果使用 Transport 段指定连接 URI，但不指定端口，将使用以下标准端口来创建会话：80 用于 HTTP，443 用于 HTTPS。 若要使用 Windows PowerShell 远程处理的默认端口，请指定 HTTP 端口 5985 或 HTTPS 端口 5986。

#### <a name="-pscredential-pscredential"></a>-PSCredential \<PSCredential\>

指定有权在目标计算机上运行工作流的用户帐户。 默认为当前用户。 仅当命令中包括 PSComputerName 参数时，此参数才有效。

键入用户名，如 "User01" 或 "Domain01\User01"，或输入一个包含对象的变量 `PSCredential` ，如 cmdlet 返回的一个对象 `Get-Credential` 。 如果仅输入用户名，则将提示你输入密码。

#### <a name="-pselapsedtimeoutsec-uint32"></a>-PSElapsedTimeoutSec \<UInt32\>

确定在系统中维护工作流和所有相关资源的时间长度。 当超时到期时，即使工作流仍在进行处理，也会将其删除。 输入一个介于10和4294967295之间的值。 默认值 0 (零) ，表示没有超时。

#### <a name="-psparametercollection-hashtable"></a>-PSParameterCollection \<Hashtable[]\>

为不同的目标计算机指定不同的工作流公用参数值。

输入一个以逗号分隔的哈希表列表，其中每个目标计算机有一个哈希表。 在每个哈希表中，第一个键为 `PSComputerName` ，其值是目标计算机的名称。 计算机名称中允许使用通配符。 对于哈希表中的剩余键，键是参数名称，值是参数值。

例如：

```powershell
-PSParameterCollection @{PSComputerName="*"; PSElapsedTimeoutSec=20},
@{PSComputerName="Server02"},
@{PSComputerName="Server03"},
@{PSComputerName="Server01"; PSElapsedTimeoutSec=10}
```

在上面的示例中，所有连接的默认 PSElapsedTimeoutSec 均为20秒，Server01 除外，它通过指定其自己的超时值10秒，来覆盖默认值。

#### <a name="-pspersist-boolean"></a>-PSPersist \<Boolean\>

除了工作流中指定的任何检查点之外，还向工作流添加检查点。

此参数无法禁止工作流中的检查点，如使用 `PSPersist` 活动通用参数、 `Checkpoint-Workflow` 活动或变量指定的检查点 `$PSPersistPreference` 。

"检查点" 或 "持久性点" 是工作流状态和工作流运行时捕获的数据的快照，并保存到磁盘或 SQL 数据库中的持久性存储中。 Windows PowerShell 工作流使用保存的数据从最后一个暂留点恢复挂起或中断的工作流，而不是重新启动工作流。

有效值：

-  ( *默认值* ) 如果省略此参数，则除了工作流中指定的任何检查点之外，还会在工作流的开头和末尾添加一个检查点。

- `$True`. 除了工作流中指定的任何检查点，还在工作流的开始和结束以及每个活动之后添加一个检查点。

- `$False`. 不添加任何检查点。 仅在工作流中指定了检查点。

#### <a name="-psport-int32"></a>-PSPort \<Int32\>

指定目标计算机上的网络端口。 默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。

请勿使用 PSPort 参数，除非你必须这样做。 命令中设置的端口适用于运行该命令的所有计算机或会话。 备用端口设置可能会阻止在所有计算机上运行该命令。 使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。

#### <a name="-psprivatemetadata-hashtable"></a>-PSPrivateMetadata \<Hashtable\>

向工作流作业提供自定义信息。 输入一个哈希表。 为每个工作流自定义键和值。 有关工作流的专用元数据的信息，请参阅工作流的帮助主题。

Windows PowerShell 工作流引擎不处理此参数。
相反，引擎会将哈希表直接传递到工作流。

#### <a name="-psrunningtimeoutsec-uint32"></a>-PSRunningTimeoutSec \<UInt32\>

指定工作流的运行时间（以秒为单位），不包括任何挂起工作流的时间。 如果工作流在时间到期时未完成，则 Windows PowerShell 工作流引擎会强行停止执行工作流。

#### <a name="-pssessionoption-pssessionoption"></a>-PSSessionOption \<PSSessionOption\>

为目标计算机的会话设置高级选项。 输入一个 `PSSessionOption` 对象，如使用 cmdlet 创建的对象 `New-PSSessionOption` 。

会话选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。 否则，会话将使用在会话配置中指定的值。

有关会话选项（包括默认值）的说明，请参阅 cmdlet 的帮助主题 `New-PSSessionOption` (。/../Microsoft.PowerShell.Core/New-PSSessionOption.md) 。 有关 `$PSSessionOption` 首选项变量的信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。

#### <a name="-psusessl-switchparameter"></a>-PSUseSSL \<SwitchParameter\>

使用安全套接字层 (SSL) 协议建立与目标计算机的连接。 默认情况下，不使用 SSL。

WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。 UseSSL 是一种额外的保护措施，它通过 HTTPS 而不是 HTTP 来发送数据。 如果你使用此参数，但 SSL 在用于此命令的端口上不可用，则命令将失败。

## <a name="see-also"></a>另请参阅

- [about_ActivityCommonParameters](about_ActivityCommonParameters.md)
- [about_Workflows](about_Workflows.md)
- [Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)
- [New-PSWorkflowExecutionOption](xref:PSWorkflow.New-PSWorkflowExecutionOption)
- [New-PSWorkflowSession](xref:PSWorkflow.New-PSWorkflowSession)
