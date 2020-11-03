---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/13/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: c89f7351e9c874cea2cc0cd5e0912e3ca0d8b0bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197891"
---
# Invoke-RestMethod

## 摘要
将 HTTP 或 HTTPS 请求发送到 RESTful Web 服务。

## 语法

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## 说明

`Invoke-RestMethod`Cmdlet 将 HTTP 和 HTTPS 请求发送到具象状态传输 (REST) web 服务返回丰富的结构化数据。

Windows PowerShell 基于数据类型设置响应的格式。 对于 RSS 或 ATOM 源，Windows PowerShell 返回项或条目 XML 节点。 对于 JavaScript 对象表示法 (JSON) 或 XML，Windows PowerShell 将内容转换（或反序列化）为对象。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

> [!NOTE]
> 默认情况下，在分析页时，可能会运行网页中的脚本代码来填充 `ParsedHtml` 属性。 使用 **UseBasicParsing** 开关来禁止显示此情况。

## 示例

### 示例1：获取 PowerShell RSS 源

```powershell
Invoke-RestMethod -Uri https://devblogs.microsoft.com/powershell/feed/ |
  Format-Table -Property Title, pubDate
```

```Output
Title                                                                pubDate
-----                                                                -------
Join the PowerShell 10th Anniversary Celebration!                    Tue, 08 Nov 2016 23:00:04 +0000
DSC Resource Kit November 2016 Release                               Thu, 03 Nov 2016 00:19:07 +0000
PSScriptAnalyzer Community Call - Oct 18, 2016                       Thu, 13 Oct 2016 17:52:35 +0000
New Home for In-Box DSC Resources                                    Sat, 08 Oct 2016 07:13:10 +0000
New Social Features on Gallery                                       Fri, 30 Sep 2016 23:04:34 +0000
PowerShellGet and PackageManagement in PowerShell Gallery and GitHub Thu, 29 Sep 2016 22:21:42 +0000
PowerShell Security at DerbyCon                                      Wed, 28 Sep 2016 01:13:19 +0000
DSC Resource Kit September Release                                   Thu, 22 Sep 2016 00:25:37 +0000
PowerShell DSC and implicit remoting broken in KB3176934             Tue, 23 Aug 2016 15:07:50 +0000
PowerShell on Linux and Open Source!                                 Thu, 18 Aug 2016 15:32:02 +0000
```

此命令使用 `Invoke-RestMethod` cmdlet 从 PowerShell 博客 rss 源获取信息。 该命令使用 `Format-Table` cmdlet 来显示表中每个博客的 **Title** 和 **e** 属性的值。

### 示例 2

在下面的示例中，用户运行 `Invoke-RestMethod` 以在用户组织中的 intranet 网站上执行 POST 请求。

```powershell
$Cred = Get-Credential

# Next, allow the use of self-signed SSL certificates.

[System.Net.ServicePointManager]::ServerCertificateValidationCallback = { $True }

# Create variables to store the values consumed by the Invoke-RestMethod command.
# The search variable contents are later embedded in the body variable.

$Server = 'server.contoso.com'
$Url = "https://${server}:8089/services/search/jobs/export"
$Search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"

# The cmdlet handles URL encoding. The body variable describes the search criteria, specifies CSV as
# the output mode, and specifies a time period for returned data that starts two days ago and ends
# one day ago. The body variable specifies values for parameters that apply to the particular REST
# API with which Invoke-RestMethod is communicating.

$Body = @{
    search = $Search
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}

# Now, run the Invoke-RestMethod command with all variables in place, specifying a path and file
# name for the resulting CSV output file.

Invoke-RestMethod -Method Post -Uri $url -Credential $Cred -Body $body -OutFile output.csv

{"preview":true,"offset":0,"result":{"sourcetype":"contoso1","count":"9624"}}

{"preview":true,"offset":1,"result":{"sourcetype":"contoso2","count":"152"}}

{"preview":true,"offset":2,"result":{"sourcetype":"contoso3","count":"88494"}}

{"preview":true,"offset":3,"result":{"sourcetype":"contoso4","count":"15277"}}
```

### 示例3：传递多个标头

此示例演示如何将中的多个标头传递 `hash-table` 到 REST API。

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

Api 通常要求传递的标头用于身份验证、验证等。

### 示例3：提交窗体数据

如果正文为窗体，或者它是另一个调用的输出 `Invoke-WebRequest` ，则 PowerShell 会将请求内容设置为窗体字段。

例如：

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## parameters

### -Body

指定请求的正文。 正文是请求的内容，位于标头之后。
还可以通过管道将正文值传递给 `Invoke-RestMethod` 。

可以将 **Body** 参数用于指定查询参数的列表，或用于指定响应的内容。

当输入是一个 GET 请求且正文是 IDictionary（通常情况下是一个哈希表）时，会将正文作为查询参数添加到 URI 中。 对于其他请求类型（如 POST），将正文按标准的“名称=值”格式设置为请求正文的值。

> [!WARNING]
> POST 正文的详细输出将以结尾 `with -1-byte payload` ，即使正文的大小是已知的，也是在 `Content-Length` HTTP 标头中发送的。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Certificate

指定用于安全的 Web 请求的客户端证书。 输入一个包含证书的变量，或可获取该证书的命令或表达式。

若要查找证书，请使用 `Get-PfxCertificate` 或使用 `Get-ChildItem` 证书 () 驱动器中的 cmdlet `Cert:` 。 如果证书无效或不具有足够的权限，则该命令将失败。

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

指定有权发送请求的用户帐户的数字公钥证书 (X509)。 输入证书的证书指纹。

在基于客户端证书的身份验证中使用证书。 证书只能映射到本地用户帐户，而不适用于域帐户。

若要获取证书指纹，请使用 `Get-Item` `Get-ChildItem` Windows PowerShell () 驱动器中的或命令 `Cert:` 。

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

### -ContentType

指定 Web 请求的内容类型。

如果省略此参数且请求方法为 POST，则 `Invoke-RestMethod` 将内容类型设置为 "application/x-url 编码"。 否则，将不会在调用中指定内容类型。

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

### -Credential

指定有权发送请求的用户帐户。 默认为当前用户。

键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableKeepAlive

将 HTTP 标头中的 **KeepAlive** 值设置为 False。 默认情况下， **KeepAlive** 为 True。
**KeepAlive** 建立到服务器的持续性连接，以促进后续请求。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: KeepAlive
Accept pipeline input: False
Accept wildcard characters: False
```

### -标头

指定 Web 请求的标头。 输入哈希表或字典。

若要设置 UserAgent 标头，请使用 **UserAgent** 参数。 不能使用此参数指定 UserAgent 或 cookie 标头。

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InFile

从文件中获取 Web 请求的内容。

请输入路径和文件名。 如果省略路径，则默认路径为当前位置。

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

### -MaximumRedirection

确定在连接失败之前，Windows PowerShell 将该连接重定向到备用统一资源标识符 (URI) 的次数。 默认值为 5。 值为 0（零）将阻止所有重定向。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -方法

指定用于 Web 请求的方法。 此参数的可接受值为：

- 默认
- 删除
- 获取
- Head
- 合并
- 选项
- 修补程序
- 邮递
- Put
- 跟踪

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutFile

将响应正文保存在指定的输出文件中。 请输入路径和文件名。 如果省略路径，则默认路径为当前位置。

默认情况下，将 `Invoke-RestMethod` 结果返回到管道。 若要将这些结果发送到文件和管道，请使用 **Passthru** 参数。

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

### -PassThru

除了将结果写入文件外，还将返回结果。 仅当命令中还使用了 **OutFile** 参数时，此参数才有效。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No output
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy

使用该请求的代理服务器，而不是直接连接到 Internet 资源。 输入网络代理服务器的 URI。

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential

指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。 默认为当前用户。

键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。

仅当命令中还使用了 **代理** 参数时，此参数才有效。 不能在同一命令中使用 **ProxyCredential** 参数和 **ProxyUseDefaultCredentials** 参数。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyUseDefaultCredentials

使用当前用户的凭据来访问由 **Proxy** 参数指定的代理服务器。

仅当命令中还使用了 **代理** 参数时，此参数才有效。 不能在同一命令中使用 **ProxyCredential** 参数和 **ProxyUseDefaultCredentials** 参数。

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

### -SessionVariable

创建一个 Web 请求会话，并将其保存在指定变量的值中。 输入一个不带美元符号 () 符号的变量名称 `$` 。

指定会话变量时，将 `Invoke-RestMethod` 创建一个 web 请求会话对象，并将其分配给 PowerShell 会话中具有指定名称的变量。 命令完成后可以立即在会话中使用该变量。

与远程会话不同，Web 请求会话不是持续性连接。 它是一个包含有关连接和请求的信息的对象，包括 Cookie、凭据、最大重定向值和用户代理字符串。 可用于共享 Web 请求之间的状态和数据。

若要在后续的 Web 请求中使用 Web 请求会话，请在 **WebSession** 参数的值中指定会话变量。 在建立新连接时，Windows PowerShell 将使用 Web 请求会话对象中的数据。 若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。 参数值优先于 Web 请求会话中的值。

不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSec

指定在超时之前请求可以挂起多长时间。输入一个值（以秒为单位）。 默认值 0 指定无限超时。

域名系统 (DNS) 查询可能需要长达15秒钟的时间来返回或超时。如果你的请求包含需要解析的主机名，并将 TimeoutSec 设置为大于零的值，但不超过15秒，则在引发 WebException 之前可能需要15秒或更长时间，并且你的请求会超时。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferEncoding

指定传输编码 HTTP 响应头的值。 此参数的可接受值为：

- 块
- 压缩
- Deflate
- GZip
- 标识

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri

指定将 Web 请求发送到的 Internet 资源的统一资源标识符 (URI)。 此参数支持 HTTP、HTTPS、FTP 和 FILE 值。

此参数是必需的。  ( **Uri** ) 的参数名称是可选的。

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseBasicParsing

指示 cmdlet 使用基本分析。 Cmdlet 返回 **String** 对象中的原始 HTML。

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

### -UseDefaultCredentials

使用当前用户的凭据来发送 Web 请求。

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

### -UserAgent

指定 Web 请求的用户代理字符串。

默认的用户代理类似于“Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0”，针对每个操作系统和平台稍有不同。

若要使用大多数 Internet 浏览器使用的标准用户代理字符串测试网站，请使用 [PSUserAgent](/dotnet/api/microsoft.powershell.commands) 类的属性，例如 Chrome、FireFox、Internet Explorer、Opera 和 Safari。

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

### -WebSession

指定一个 Web 请求会话。 输入变量名称，包括美元符号 (`$`) 。

若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。 参数值优先于 Web 请求会话中的值。

与远程会话不同，Web 请求会话不是持续性连接。 它是一个包含有关连接和请求的信息的对象，包括 Cookie、凭据、最大重定向值和用户代理字符串。 可用于共享 Web 请求之间的状态和数据。

若要创建 web 请求会话，请在命令的 **SessionVariable** 参数的值中输入一个不带美元符号)  (的变量名称 `Invoke-RestMethod` 。 `Invoke-RestMethod` 创建会话并将其保存在变量中。 在后续命令中，将该变量用作 **WebSession** 参数的值。

不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestSession
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

### System.Object

你可以通过管道将 web 请求的正文传递给 `Invoke-RestMethod` 。

## Outputs

### System.Xml.Xml文档，Microsoft.PowerShell.Commands.HtmlWebResponseObject

此 cmdlet 的输出取决于检索内容的格式。

### PSObject

如果请求返回 JSON 字符串，则 `Invoke-RestMethod` 返回表示字符串的 PSObject。

## 注释

## 相关链接

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)
