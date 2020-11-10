---
description: 介绍 Windows PowerShell 工作流添加到活动中的参数。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_ActivityCommonParameters
ms.openlocfilehash: 93fdcdb9c5afe0b73e843baf2474ec7d3f96a6cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387798"
---
# <a name="about-activitycommonparameters"></a>关于 ActivityCommonParameters

## <a name="short-description"></a>简短说明

介绍 Windows PowerShell 工作流添加到活动中的参数。

## <a name="long-description"></a>详细说明

Windows PowerShell 工作流将活动通用参数添加到从 PSActivity 基类派生的活动。 此类别包括 InlineScript 活动以及作为活动实现的 Windows PowerShell cmdlet，例如 Get-Process 和 Get-winevent。

活动通用参数在 Suspend-Workflow 和 Checkpoint-Workflow 活动中无效，它们不会添加到 Windows PowerShell 工作流在 InlineScript 脚本块或类似活动中自动运行的 cmdlet 或表达式中。 活动通用参数在 InlineScript 活动上可用，但在 InlineScript 脚本块中的命令上不可用。

某些活动通用参数也是工作流通用参数或 Windows PowerShell 通用参数。 其他活动通用参数对于活动是唯一的。

有关工作流通用参数的信息，请参阅 about_WorkflowCommonParameters。 有关 Windows PowerShell 通用参数的信息，请参阅 about_CommonParameters。

### <a name="list-of-activity-common-parameters"></a>活动通用参数的列表

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a>参数说明

本部分介绍活动通用参数。

#### <a name="appendoutput-boolean"></a>AppendOutput \<Boolean\>

值为 `$True` 将活动的输出添加到变量的值。
值 `$False` 不起作用。 默认情况下，向变量分配值会替换变量值。

例如，以下命令将进程对象添加到变量中的服务对象 `$x` 。

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

此参数适用于基于 XAML 的工作流。 在脚本工作流中，还可以使用 + = 赋值运算符将输出添加到变量的值，如下面的示例中所示。

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a>Debug.exe \<SwitchParameter\>

显示有关命令所执行操作的程序员级别的详细信息。
Debug 参数重写当前命令的 $DebugPreference 变量的值。 仅当命令生成调试消息时，此参数才有效。 此参数也是 Windows PowerShell 通用参数。

#### <a name="displayname-string"></a>DisplayName \<String\>

为活动指定友好名称。 在工作流运行时，"显示名称" 值显示在进度栏中，在工作流作业的 "进度" 属性值中显示。 如果命令中还包含 PSProgressMessage 参数，则进度栏内容将以 \<DisplayName\> ： \<PSProgressMessage\> 格式显示。

#### <a name="erroraction-actionpreference"></a>ErrorAction \<ActionPreference\>

确定活动如何响应命令中的非终止错误。 它不会影响终止错误。 此参数仅在命令生成非终止错误（如 Write-Error cmdlet 中的错误）时才起作用。 ErrorAction 参数重写当前命令的 $ErrorActionPreference 变量的值。 此参数也是 Windows PowerShell 通用参数。

有效值：

- 仍. 显示错误消息并继续执行命令。 默认值为 "Continue"。

- 忽略。 禁止显示错误消息并继续执行命令。
  与 SilentlyContinue 不同，Ignore 不会将错误消息添加到 $Error 自动变量中。 忽略值在 Windows PowerShell 3.0 中引入。

- 时刻表. 显示错误消息并提示您进行确认，然后再继续执行。 此值很少使用。

- 休眠. 自动挂起工作流作业以便进一步进行调查。 调查后，工作流可以恢复。

- SilentlyContinue. 禁止显示错误消息并继续执行命令。

- 停止。 显示错误消息并停止执行命令。

#### <a name="input-object"></a>送 \<Object[]\>

将对象的集合提交到活动。 这是将对象一次一个地通过管道传递给活动的替代方法。

#### <a name="mergeerrortooutput-boolean"></a>MergeErrorToOutput \<Boolean\>

值 `$True` 将错误添加到输出流中。 值 `$False` 无效。 将此参数与并行和关键字一起使用， `ForEach -Parallel` 可从单个集合中的多个并行命令收集错误和输出。

#### <a name="psactionretrycount-int32"></a>PSActionRetryCount \<Int32\>

如果首次尝试失败，则反复尝试运行活动。 默认值 0 表示不重试。

#### <a name="psactionretryintervalsec-int32"></a>PSActionRetryIntervalSec \<Int32\>

确定操作重试之间的间隔（以秒为单位）。 默认值 0 表示立即重试操作。 仅当命令中还使用了 PSActionRetryCount 参数时，此参数才有效。

#### <a name="psactionrunningtimeoutsec-int32"></a>PSActionRunningTimeoutSec \<Int32\>

确定活动每台目标计算机上可以运行的时间长度。 如果在超时过期之前没有完成该活动，则 Windows PowerShell 工作流将生成一个终止错误并停止处理受影响的目标计算机上的工作流。

#### <a name="psallowredirection-boolean"></a>PSAllowRedirection \<Boolean\>

值 $True 允许将连接重定向到目标计算机。
值 $False 不起作用。 此活动通用参数也是工作流通用参数。

使用 PSConnectionURI 参数时，远程目标将返回一个指令，以重定向到不同的 URI。 默认情况下，Windows PowerShell 不会重定向连接，但你可以使用值为 $True 的 PSAllowRedirection 参数，以允许将连接重定向到目标计算机。

你还可以通过设置 `$PSSessionOption` 首选项变量的 MaximumConnectionRedirectionCount 属性，或创建会话的 cmdlet 的 SSessionOption 参数值的 MaximumConnectionRedirectionCount 属性来限制重定向连接的次数。 默认值为 5。

#### <a name="psapplicationname-string"></a>PSApplicationName \<String\>

指定连接 URI 的应用程序名称段，该连接 URI 用于连接到目标计算机。 当命令中未使用 ConnectionURI 参数时，请使用此参数指定应用程序名称。 此活动通用参数也是工作流通用参数。

默认值是 `$PSSessionApplicationName` 目标计算机上首选项变量的值。 如果未定义此首选项变量，则默认值为 WSMAN。 该值适用于大多数使用情况。 有关详细信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。

WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。 此参数的值应与远程计算机上的侦听器的 URLPrefix 属性值相匹配。

#### <a name="psauthentication-authenticationmechanism"></a>PSAuthentication \<AuthenticationMechanism\>

指定在连接到目标计算机时用于对用户的凭据进行身份验证的机制。 有效值为 Default、Basic、Credssp、Digest、Kerberos、Negotiate 和 NegotiateWithImplicitCredential。 默认值为 Default。 此活动通用参数也是工作流通用参数。

有关此参数的值的信息，请参阅 PowerShell SDK 中的 **system.management.automation.runspaces.authenticationmechanism** 枚举的说明。

> [!WARNING]
> 在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。 此机制增加了远程操作的安全风险。 如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

#### <a name="pscertificatethumbprint-string"></a>PSCertificateThumbprint \<String\>

指定有权执行此操作的用户帐户的数字公钥证书 (X509)。 输入证书的证书指纹。 此活动通用参数也是工作流通用参数。

在基于客户端证书的身份验证中使用证书。 证书只能映射到本地用户帐户，而不适用于域帐户。

若要获取证书，请使用 Windows PowerShell Cert：驱动器中的 [Get 项](xref:Microsoft.PowerShell.Management.Get-Item) 或 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlet。

#### <a name="pscomputername-string"></a>PSComputerName \<String[]\>

指定运行活动的目标计算机。 默认为本地计算机。 此活动通用参数也是工作流通用参数。

在以逗号分隔的列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入该计算机名称、“localhost”或句点 (.)。

若要将本地计算机包含在 PSComputerName 参数的值中，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。

如果从命令中省略此参数，或该值 $null 或空字符串，则工作流目标为本地计算机，并且不使用 Windows PowerShell 远程处理来运行该命令。

若要在 ComputerName 参数的值中使用 IP 地址，该命令必须包含 PSCredential 参数。 此外，必须为计算机配置 HTTPS 传输，或者必须在本地计算机上的 WinRM TrustedHosts 列表中包含远程计算机的 IP 地址。 有关将计算机名称添加到 TrustedHosts 列表的说明，请参阅 [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)中的 "如何将计算机添加到受信任的主机列表中"。

#### <a name="psconfigurationname-string"></a>PSConfigurationName \<String\>

指定用于在目标计算机上创建会话的会话配置。 在运行工作流的计算机上 (不在目标计算机上输入会话配置的名称。 默认值为 "Microsoft PowerShell"。 此活动通用参数也是工作流通用参数。

#### <a name="psconnectionretrycount-uint"></a>PSConnectionRetryCount \<UInt\>

指定第一次连接尝试失败时连接到每台目标计算机的最大尝试次数。 输入介于1到 4294967295 (UInt) 之间的数字。 默认值为零 (0) 表示不重试尝试。
此活动通用参数也是工作流通用参数。

#### <a name="psconnectionretryintervalsec-uint"></a>PSConnectionRetryIntervalSec \<UInt\>

指定连接重试尝试之间的延迟（以秒为单位）。 默认值为零 (0)。 仅当 PSConnectionRetryCount 的值为1时，此参数才有效。 此活动通用参数也是工作流通用参数。

#### <a name="psconnectionuri-systemuri"></a>PSConnectionURI \<System.Uri\>

指定 (URI) 的统一资源标识符，该标识符定义目标计算机上的活动的连接终结点。 URI 必须完全限定。 此活动通用参数也是工作流通用参数。

此字符串的格式如下：

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

默认值为 `http://localhost:5985/WSMAN`。

如果未指定 PSConnectionURI，则可以使用 PSUseSSL、PSComputerName、PSPort 和 PSApplicationName 参数来指定 PSConnectionURI 值。

URI 的 Transport 段的有效值为 HTTP 和 HTTPS。 如果使用 Transport 段指定连接 URI，但不指定端口，将使用以下标准端口来创建会话：80 用于 HTTP，443 用于 HTTPS。 若要使用 Windows PowerShell 远程处理的默认端口，请指定 HTTP 端口 5985 或 HTTPS 端口 5986。

#### <a name="pscredential-pscredential"></a>PSCredential \<PSCredential\>

指定有权在目标计算机上运行活动的用户帐户。 默认为当前用户。 仅当命令中包括 PSComputerName 参数时，此参数才有效。 此活动通用参数也是工作流通用参数。

键入用户名，如 "User01" 或 "Domain01\User01"，或输入包含 PSCredential 对象（例如 Get-Credential cmdlet 返回的一个 PSCredential 对象）的变量。 如果仅输入用户名，则将提示你输入密码。

#### <a name="psdebug-psdatacollectiondebugrecord"></a>Set-psdebug \<PSDataCollection[DebugRecord]\>

将活动中的调试消息添加到指定的调试记录集合，而不是将调试消息写入控制台或工作流作业的 "调试" 属性的值。 可以将来自多个活动的调试消息添加到同一个调试记录集合对象中。

若要使用此活动通用参数，请使用 New-Object cmdlet 创建具有 DebugRecord 类型的 C o 对象，并将该对象保存在变量中。 然后，将变量用作一个或多个活动的 Set-psdebug 参数的值，如下面的示例中所示。

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a>PSDisableSerialization \<Boolean\>

指示活动将“实时”（未序列化）对象返回给工作流。
得到的对象具有方法以及属性，但它们无法在采用检查点时进行保存。

#### <a name="psdisableserializationpreference-boolean"></a>PSDisableSerializationPreference \<Boolean\>

将 PSDisableSerialization 参数的等效项应用于整个工作流，而不仅仅是活动。 通常不建议添加此参数，因为不序列化其对象的工作流无法恢复或保持。

有效值：

-  (默认值) 如果省略，并且还没有向活动中添加 PSDisableSerialization 参数，则会序列化对象。

- `$True`. 指示工作流中的所有活动返回“实时”（未序列化）对象。 得到的对象具有方法以及属性，但它们无法在采用检查点时进行保存。
- `$False`. 工作流对象进行序列化。

#### <a name="pserror-psdatacollectionerrorrecord"></a>PSError \<PSDataCollection[ErrorRecord]\>

将活动中的错误消息添加到指定的错误记录集合，而不是将错误消息写入控制台或工作流作业的 Error 属性的值。 可以将来自多个活动的错误消息添加到同一个错误记录集合对象中。

若要使用此活动通用参数，请使用 `New-Object` cmdlet 创建类型为 ErrorRecord 的 c o 对象，并将该对象保存在变量中。 然后，将变量用作一个或多个活动的 PSError 参数的值，如下面的示例中所示。

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a>PSPersist \<Boolean\>

在活动后使用一个检查点。 除了工作流中指定的任何检查点之外，此检查点也是如此。 此活动通用参数也是工作流通用参数。

"检查点" 或 "持久性点" 是工作流状态和工作流运行时捕获的数据的快照，并保存到磁盘上的持久性存储中。 Windows PowerShell 工作流使用保存的数据从最后一个暂留点恢复挂起或中断的工作流，而不是重新启动工作流。

有效值：

-  (默认值) 如果省略此参数，则不会添加任何检查点。 检查点基于工作流的设置。

- `$True`. 在活动完成后使用一个检查点。
  除了工作流中指定的任何检查点之外，此检查点也是如此。

- `$False`. 不添加任何检查点。 仅在工作流中指定了检查点。

#### <a name="psport-int32"></a>PSPort \<Int32\>

指定目标计算机上的网络端口。 默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。 此活动通用参数也是工作流通用参数。

请勿使用 PSPort 参数，除非你必须这样做。 命令中设置的端口适用于运行该命令的所有计算机或会话。 备用端口设置可能会阻止在所有计算机上运行该命令。 使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。

#### <a name="psprogress-psdatacollectionprogressrecord"></a>PSProgress \<PSDataCollection[ProgressRecord]\>

将活动中的进度消息添加到指定的进度记录集合，而不是将进度消息写入控制台或工作流作业的进度属性值。 可以将来自多个活动的进度消息添加到同一个进度记录集合对象中。

#### <a name="psprogressmessage-string"></a>PSProgressMessage \<String\>

指定活动的易懂描述。 工作流运行时，PSProgressMessage 值会显示在进度栏中。 如果该显示名称也包含在命令中，则进度栏内容将以 \<DisplayName\> ： \<PSProgressMessage\> 格式显示。

此参数对于标识 ForEach 并行脚本块中的活动特别有用。 没有此消息时，所有并行分支中的活动都通过相同名称进行标识。

#### <a name="psremotingbehavior-remotingbehavior"></a>PSRemotingBehavior \<RemotingBehavior\>

指定活动在目标计算机上运行时的远程处理管理方式。
默认值为 PowerShell。

有效值是：

- 无：活动不在远程计算机上运行。

- PowerShell：使用 Windows PowerShell 远程处理在目标计算机上运行活动。

- 自定义：活动支持其自己的远程处理类型。 当作为活动实现的 cmdlet 将 RemotingCapability 属性的值设置为 SupportedByCommand，并且该命令包含 ComputerName 参数时，此值有效。

#### <a name="psrequiredmodules-string"></a>PSRequiredModules \<String[]\>

在运行命令之前导入指定模块。 输入模块名。 该模块必须安装在目标计算机上。

当首次使用模块中的任何命令时，将自动导入在 PSModulePath 环境变量中指定的路径中安装的模块。
使用此参数可导入不在 PSModulePath 位置中的模块。

因为工作流中的每个活动都在其自己的会话中运行，所以 Import-Module 命令仅将模块导入运行它的会话中。 它不将模块导入运行其他活动的会话中。

#### <a name="pssessionoption-pssessionoption"></a>PSSessionOption \<PSSessionOption\>

为目标计算机的会话设置高级选项。 输入一个 PSSessionOption 对象，例如使用 New-PSSessionOption cmdlet 创建的对象。 此活动通用参数也是工作流通用参数。

会话选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。 否则，会话将使用在会话配置中指定的值。

有关会话选项（包括默认值）的说明，请参阅 New-PSSessionOption cmdlet [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)的帮助主题。

有关 $PSSessionOption 首选项变量的详细信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。

#### <a name="psusessl-boolean"></a>PSUseSSL \<Boolean\>

值 $True 使用安全套接字层 (SSL) 协议建立与目标计算机的连接。 默认情况下，不使用 SSL。 值 $False 不起作用。 此活动通用参数也是工作流通用参数。

WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。 UseSSL 是一种额外的保护措施，它通过 HTTPS 而不是 HTTP 来发送数据。 如果你使用此参数，但 SSL 在用于此命令的端口上不可用，则命令将失败。

#### <a name="psverbose-psdatacollectionverboserecord"></a>PSVerbose \<PSDataCollection[VerboseRecord]\>

将来自活动的详细消息添加到指定的详细记录集合，而不是将详细消息写入控制台或工作流作业的详细属性值。 可以将来自多个活动的详细消息添加到同一个详细记录集合对象中。

#### <a name="pswarning-psdatacollectionwarningrecord"></a>PSWarning \<PSDataCollection[WarningRecord]\>

将来自活动的警告消息添加到指定的警告记录集合，而不是将警告消息写入控制台或工作流作业的 Warning 属性的值。 可以将来自多个活动的警告消息添加到同一个警告记录集合对象中。

#### <a name="result"></a>结果

此参数仅在 XAML 工作流中有效。

#### <a name="usedefaultinput-boolean"></a>UseDefaultInput \<Boolean\>

按值接受所有工作流输入作为活动的输入。

例如，以下示例工作流中的 Get-Process 活动使用 UseDefaultInput 活动通用参数获取传递给工作流的输入。 使用输入运行工作流时，活动会使用该输入。

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a>详细 \<SwitchParameter\>

显示有关命令所执行操作的详细信息。
此信息类似于跟踪或事务日志中的信息。
Verbose 参数重写当前命令的 $VerbosePreference 变量的值。 仅当命令生成详细消息时，此参数才有效。 此参数也是 Windows PowerShell 通用参数。

#### <a name="warningaction-actionpreference"></a>WarningAction \<ActionPreference\>

确定活动如何响应警告。 默认值为 "Continue"。 WarningAction 参数重写当前命令的 $WarningPreference 变量的值。 仅当命令生成警告消息时，此参数才有效。 此参数也是 Windows PowerShell 通用参数。

有效值：

- SilentlyContinue. 禁止显示警告消息并继续执行命令。

- 仍. 显示警告消息并继续执行命令。
  默认值为 "Continue"。

- 时刻表. 显示警告消息并提示您进行确认，然后再继续执行。 此值很少使用。

- 停止。 显示警告消息，并停止执行命令。

> [!NOTE]
> 当在命令中使用参数运行脚本或函数时，WarningAction 参数不会重写 $WarningAction 首选项变量的值。

### <a name="examples"></a>示例

活动通用参数非常有用。 例如，你可以使用 PSComputerName 参数来仅对目标计算机的一个子集运行特定活动。

或者，你可以使用 PSConnectionRetryCount 和 PSConnectionRetryIntervalSec 参数来调整特定活动的重试值。

下面的示例演示如何使用 PSComputerName 活动通用参数仅在其特定域的计算机上运行 Get-EventLog 活动。

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a>另请参阅

[about_Workflows](about_workflows.md) 
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)
