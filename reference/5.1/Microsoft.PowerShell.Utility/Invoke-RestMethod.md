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
# <span data-ttu-id="392a7-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="392a7-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="392a7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="392a7-104">Synopsis</span></span>
<span data-ttu-id="392a7-105">将 HTTP 或 HTTPS 请求发送到 RESTful Web 服务。</span><span class="sxs-lookup"><span data-stu-id="392a7-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="392a7-106">语法</span><span class="sxs-lookup"><span data-stu-id="392a7-106">Syntax</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="392a7-107">说明</span><span class="sxs-lookup"><span data-stu-id="392a7-107">Description</span></span>

<span data-ttu-id="392a7-108">`Invoke-RestMethod`Cmdlet 将 HTTP 和 HTTPS 请求发送到具象状态传输 (REST) web 服务返回丰富的结构化数据。</span><span class="sxs-lookup"><span data-stu-id="392a7-108">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that returns richly structured data.</span></span>

<span data-ttu-id="392a7-109">Windows PowerShell 基于数据类型设置响应的格式。</span><span class="sxs-lookup"><span data-stu-id="392a7-109">Windows PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="392a7-110">对于 RSS 或 ATOM 源，Windows PowerShell 返回项或条目 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="392a7-110">For an RSS or ATOM feed, Windows PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="392a7-111">对于 JavaScript 对象表示法 (JSON) 或 XML，Windows PowerShell 将内容转换（或反序列化）为对象。</span><span class="sxs-lookup"><span data-stu-id="392a7-111">For JavaScript Object Notation (JSON) or XML, Windows PowerShell converts (or deserializes) the content into objects.</span></span>

<span data-ttu-id="392a7-112">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="392a7-112">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="392a7-113">默认情况下，在分析页时，可能会运行网页中的脚本代码来填充 `ParsedHtml` 属性。</span><span class="sxs-lookup"><span data-stu-id="392a7-113">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="392a7-114">使用 **UseBasicParsing** 开关来禁止显示此情况。</span><span class="sxs-lookup"><span data-stu-id="392a7-114">Use the **UseBasicParsing** switch to suppress this.</span></span>

## <span data-ttu-id="392a7-115">示例</span><span class="sxs-lookup"><span data-stu-id="392a7-115">Examples</span></span>

### <span data-ttu-id="392a7-116">示例1：获取 PowerShell RSS 源</span><span class="sxs-lookup"><span data-stu-id="392a7-116">Example 1: Get the PowerShell RSS feed</span></span>

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

<span data-ttu-id="392a7-117">此命令使用 `Invoke-RestMethod` cmdlet 从 PowerShell 博客 rss 源获取信息。</span><span class="sxs-lookup"><span data-stu-id="392a7-117">This command uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="392a7-118">该命令使用 `Format-Table` cmdlet 来显示表中每个博客的 **Title** 和 **e** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="392a7-118">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

### <span data-ttu-id="392a7-119">示例 2</span><span class="sxs-lookup"><span data-stu-id="392a7-119">Example 2</span></span>

<span data-ttu-id="392a7-120">在下面的示例中，用户运行 `Invoke-RestMethod` 以在用户组织中的 intranet 网站上执行 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="392a7-120">In the following example, a user runs `Invoke-RestMethod` to perform a POST request on an intranet website in the user's organization.</span></span>

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

### <span data-ttu-id="392a7-121">示例3：传递多个标头</span><span class="sxs-lookup"><span data-stu-id="392a7-121">Example 3: Pass multiple headers</span></span>

<span data-ttu-id="392a7-122">此示例演示如何将中的多个标头传递 `hash-table` 到 REST API。</span><span class="sxs-lookup"><span data-stu-id="392a7-122">This example demonstrates, how to pass multiple headers in from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

<span data-ttu-id="392a7-123">Api 通常要求传递的标头用于身份验证、验证等。</span><span class="sxs-lookup"><span data-stu-id="392a7-123">APIs often require passed headers for authentication, validation etc.</span></span>

### <span data-ttu-id="392a7-124">示例3：提交窗体数据</span><span class="sxs-lookup"><span data-stu-id="392a7-124">Example 3: Submitting form data</span></span>

<span data-ttu-id="392a7-125">如果正文为窗体，或者它是另一个调用的输出 `Invoke-WebRequest` ，则 PowerShell 会将请求内容设置为窗体字段。</span><span class="sxs-lookup"><span data-stu-id="392a7-125">When the body is a form, or it is the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="392a7-126">例如：</span><span class="sxs-lookup"><span data-stu-id="392a7-126">For example:</span></span>

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## <span data-ttu-id="392a7-127">parameters</span><span class="sxs-lookup"><span data-stu-id="392a7-127">Parameters</span></span>

### <span data-ttu-id="392a7-128">-Body</span><span class="sxs-lookup"><span data-stu-id="392a7-128">-Body</span></span>

<span data-ttu-id="392a7-129">指定请求的正文。</span><span class="sxs-lookup"><span data-stu-id="392a7-129">Specifies the body of the request.</span></span> <span data-ttu-id="392a7-130">正文是请求的内容，位于标头之后。</span><span class="sxs-lookup"><span data-stu-id="392a7-130">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="392a7-131">还可以通过管道将正文值传递给 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-131">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="392a7-132">可以将 **Body** 参数用于指定查询参数的列表，或用于指定响应的内容。</span><span class="sxs-lookup"><span data-stu-id="392a7-132">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="392a7-133">当输入是一个 GET 请求且正文是 IDictionary（通常情况下是一个哈希表）时，会将正文作为查询参数添加到 URI 中。</span><span class="sxs-lookup"><span data-stu-id="392a7-133">When the input is a GET request, and the body is an IDictionary (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="392a7-134">对于其他请求类型（如 POST），将正文按标准的“名称=值”格式设置为请求正文的值。</span><span class="sxs-lookup"><span data-stu-id="392a7-134">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

> [!WARNING]
> <span data-ttu-id="392a7-135">POST 正文的详细输出将以结尾 `with -1-byte payload` ，即使正文的大小是已知的，也是在 `Content-Length` HTTP 标头中发送的。</span><span class="sxs-lookup"><span data-stu-id="392a7-135">The verbose output of a POST body will end with `with -1-byte payload`, even though the size of the body is both known and sent in the `Content-Length` HTTP header.</span></span>

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

### <span data-ttu-id="392a7-136">-Certificate</span><span class="sxs-lookup"><span data-stu-id="392a7-136">-Certificate</span></span>

<span data-ttu-id="392a7-137">指定用于安全的 Web 请求的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="392a7-137">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="392a7-138">输入一个包含证书的变量，或可获取该证书的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="392a7-138">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="392a7-139">若要查找证书，请使用 `Get-PfxCertificate` 或使用 `Get-ChildItem` 证书 () 驱动器中的 cmdlet `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-139">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="392a7-140">如果证书无效或不具有足够的权限，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="392a7-140">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="392a7-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="392a7-141">-CertificateThumbprint</span></span>

<span data-ttu-id="392a7-142">指定有权发送请求的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="392a7-142">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="392a7-143">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="392a7-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="392a7-144">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="392a7-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="392a7-145">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="392a7-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="392a7-146">若要获取证书指纹，请使用 `Get-Item` `Get-ChildItem` Windows PowerShell () 驱动器中的或命令 `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell (`Cert:`) drive.</span></span>

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

### <span data-ttu-id="392a7-147">-ContentType</span><span class="sxs-lookup"><span data-stu-id="392a7-147">-ContentType</span></span>

<span data-ttu-id="392a7-148">指定 Web 请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="392a7-148">Specifies the content type of the web request.</span></span>

<span data-ttu-id="392a7-149">如果省略此参数且请求方法为 POST，则 `Invoke-RestMethod` 将内容类型设置为 "application/x-url 编码"。</span><span class="sxs-lookup"><span data-stu-id="392a7-149">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to "application/x-www-form-urlencoded".</span></span> <span data-ttu-id="392a7-150">否则，将不会在调用中指定内容类型。</span><span class="sxs-lookup"><span data-stu-id="392a7-150">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="392a7-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="392a7-151">-Credential</span></span>

<span data-ttu-id="392a7-152">指定有权发送请求的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="392a7-152">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="392a7-153">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="392a7-153">The default is the current user.</span></span>

<span data-ttu-id="392a7-154">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-154">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="392a7-155">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="392a7-155">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="392a7-156">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="392a7-156">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="392a7-157">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="392a7-157">-DisableKeepAlive</span></span>

<span data-ttu-id="392a7-158">将 HTTP 标头中的 **KeepAlive** 值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="392a7-158">Sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="392a7-159">默认情况下， **KeepAlive** 为 True。</span><span class="sxs-lookup"><span data-stu-id="392a7-159">By default, **KeepAlive** is True.</span></span>
<span data-ttu-id="392a7-160">**KeepAlive** 建立到服务器的持续性连接，以促进后续请求。</span><span class="sxs-lookup"><span data-stu-id="392a7-160">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="392a7-161">-标头</span><span class="sxs-lookup"><span data-stu-id="392a7-161">-Headers</span></span>

<span data-ttu-id="392a7-162">指定 Web 请求的标头。</span><span class="sxs-lookup"><span data-stu-id="392a7-162">Specifies the headers of the web request.</span></span> <span data-ttu-id="392a7-163">输入哈希表或字典。</span><span class="sxs-lookup"><span data-stu-id="392a7-163">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="392a7-164">若要设置 UserAgent 标头，请使用 **UserAgent** 参数。</span><span class="sxs-lookup"><span data-stu-id="392a7-164">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="392a7-165">不能使用此参数指定 UserAgent 或 cookie 标头。</span><span class="sxs-lookup"><span data-stu-id="392a7-165">You cannot use this parameter to specify UserAgent or cookie headers.</span></span>

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

### <span data-ttu-id="392a7-166">-InFile</span><span class="sxs-lookup"><span data-stu-id="392a7-166">-InFile</span></span>

<span data-ttu-id="392a7-167">从文件中获取 Web 请求的内容。</span><span class="sxs-lookup"><span data-stu-id="392a7-167">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="392a7-168">请输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="392a7-168">Enter a path and file name.</span></span> <span data-ttu-id="392a7-169">如果省略路径，则默认路径为当前位置。</span><span class="sxs-lookup"><span data-stu-id="392a7-169">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="392a7-170">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="392a7-170">-MaximumRedirection</span></span>

<span data-ttu-id="392a7-171">确定在连接失败之前，Windows PowerShell 将该连接重定向到备用统一资源标识符 (URI) 的次数。</span><span class="sxs-lookup"><span data-stu-id="392a7-171">Determines how many times Windows PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="392a7-172">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="392a7-172">The default value is 5.</span></span> <span data-ttu-id="392a7-173">值为 0（零）将阻止所有重定向。</span><span class="sxs-lookup"><span data-stu-id="392a7-173">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="392a7-174">-方法</span><span class="sxs-lookup"><span data-stu-id="392a7-174">-Method</span></span>

<span data-ttu-id="392a7-175">指定用于 Web 请求的方法。</span><span class="sxs-lookup"><span data-stu-id="392a7-175">Specifies the method used for the web request.</span></span> <span data-ttu-id="392a7-176">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="392a7-176">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="392a7-177">默认</span><span class="sxs-lookup"><span data-stu-id="392a7-177">Default</span></span>
- <span data-ttu-id="392a7-178">删除</span><span class="sxs-lookup"><span data-stu-id="392a7-178">Delete</span></span>
- <span data-ttu-id="392a7-179">获取</span><span class="sxs-lookup"><span data-stu-id="392a7-179">Get</span></span>
- <span data-ttu-id="392a7-180">Head</span><span class="sxs-lookup"><span data-stu-id="392a7-180">Head</span></span>
- <span data-ttu-id="392a7-181">合并</span><span class="sxs-lookup"><span data-stu-id="392a7-181">Merge</span></span>
- <span data-ttu-id="392a7-182">选项</span><span class="sxs-lookup"><span data-stu-id="392a7-182">Options</span></span>
- <span data-ttu-id="392a7-183">修补程序</span><span class="sxs-lookup"><span data-stu-id="392a7-183">Patch</span></span>
- <span data-ttu-id="392a7-184">邮递</span><span class="sxs-lookup"><span data-stu-id="392a7-184">Post</span></span>
- <span data-ttu-id="392a7-185">Put</span><span class="sxs-lookup"><span data-stu-id="392a7-185">Put</span></span>
- <span data-ttu-id="392a7-186">跟踪</span><span class="sxs-lookup"><span data-stu-id="392a7-186">Trace</span></span>

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

### <span data-ttu-id="392a7-187">-OutFile</span><span class="sxs-lookup"><span data-stu-id="392a7-187">-OutFile</span></span>

<span data-ttu-id="392a7-188">将响应正文保存在指定的输出文件中。</span><span class="sxs-lookup"><span data-stu-id="392a7-188">Saves the response body in the specified output file.</span></span> <span data-ttu-id="392a7-189">请输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="392a7-189">Enter a path and file name.</span></span> <span data-ttu-id="392a7-190">如果省略路径，则默认路径为当前位置。</span><span class="sxs-lookup"><span data-stu-id="392a7-190">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="392a7-191">默认情况下，将 `Invoke-RestMethod` 结果返回到管道。</span><span class="sxs-lookup"><span data-stu-id="392a7-191">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="392a7-192">若要将这些结果发送到文件和管道，请使用 **Passthru** 参数。</span><span class="sxs-lookup"><span data-stu-id="392a7-192">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="392a7-193">-PassThru</span><span class="sxs-lookup"><span data-stu-id="392a7-193">-PassThru</span></span>

<span data-ttu-id="392a7-194">除了将结果写入文件外，还将返回结果。</span><span class="sxs-lookup"><span data-stu-id="392a7-194">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="392a7-195">仅当命令中还使用了 **OutFile** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="392a7-195">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="392a7-196">-Proxy</span><span class="sxs-lookup"><span data-stu-id="392a7-196">-Proxy</span></span>

<span data-ttu-id="392a7-197">使用该请求的代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="392a7-197">Uses a proxy server for the request, rather than connecting directly to the Internet resource.</span></span> <span data-ttu-id="392a7-198">输入网络代理服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="392a7-198">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="392a7-199">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="392a7-199">-ProxyCredential</span></span>

<span data-ttu-id="392a7-200">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="392a7-200">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="392a7-201">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="392a7-201">The default is the current user.</span></span>

<span data-ttu-id="392a7-202">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="392a7-202">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="392a7-203">仅当命令中还使用了 **代理** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="392a7-203">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="392a7-204">不能在同一命令中使用 **ProxyCredential** 参数和 **ProxyUseDefaultCredentials** 参数。</span><span class="sxs-lookup"><span data-stu-id="392a7-204">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="392a7-205">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="392a7-205">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="392a7-206">使用当前用户的凭据来访问由 **Proxy** 参数指定的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="392a7-206">Uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="392a7-207">仅当命令中还使用了 **代理** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="392a7-207">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="392a7-208">不能在同一命令中使用 **ProxyCredential** 参数和 **ProxyUseDefaultCredentials** 参数。</span><span class="sxs-lookup"><span data-stu-id="392a7-208">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="392a7-209">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="392a7-209">-SessionVariable</span></span>

<span data-ttu-id="392a7-210">创建一个 Web 请求会话，并将其保存在指定变量的值中。</span><span class="sxs-lookup"><span data-stu-id="392a7-210">Creates a web request session and saves it in the value of the specified variable.</span></span> <span data-ttu-id="392a7-211">输入一个不带美元符号 () 符号的变量名称 `$` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-211">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="392a7-212">指定会话变量时，将 `Invoke-RestMethod` 创建一个 web 请求会话对象，并将其分配给 PowerShell 会话中具有指定名称的变量。</span><span class="sxs-lookup"><span data-stu-id="392a7-212">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="392a7-213">命令完成后可以立即在会话中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="392a7-213">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="392a7-214">与远程会话不同，Web 请求会话不是持续性连接。</span><span class="sxs-lookup"><span data-stu-id="392a7-214">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="392a7-215">它是一个包含有关连接和请求的信息的对象，包括 Cookie、凭据、最大重定向值和用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="392a7-215">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="392a7-216">可用于共享 Web 请求之间的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="392a7-216">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="392a7-217">若要在后续的 Web 请求中使用 Web 请求会话，请在 **WebSession** 参数的值中指定会话变量。</span><span class="sxs-lookup"><span data-stu-id="392a7-217">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="392a7-218">在建立新连接时，Windows PowerShell 将使用 Web 请求会话对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="392a7-218">Windows PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="392a7-219">若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。</span><span class="sxs-lookup"><span data-stu-id="392a7-219">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="392a7-220">参数值优先于 Web 请求会话中的值。</span><span class="sxs-lookup"><span data-stu-id="392a7-220">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="392a7-221">不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="392a7-221">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="392a7-222">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="392a7-222">-TimeoutSec</span></span>

<span data-ttu-id="392a7-223">指定在超时之前请求可以挂起多长时间。输入一个值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="392a7-223">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="392a7-224">默认值 0 指定无限超时。</span><span class="sxs-lookup"><span data-stu-id="392a7-224">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="392a7-225">域名系统 (DNS) 查询可能需要长达15秒钟的时间来返回或超时。如果你的请求包含需要解析的主机名，并将 TimeoutSec 设置为大于零的值，但不超过15秒，则在引发 WebException 之前可能需要15秒或更长时间，并且你的请求会超时。</span><span class="sxs-lookup"><span data-stu-id="392a7-225">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set TimeoutSec to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="392a7-226">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="392a7-226">-TransferEncoding</span></span>

<span data-ttu-id="392a7-227">指定传输编码 HTTP 响应头的值。</span><span class="sxs-lookup"><span data-stu-id="392a7-227">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="392a7-228">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="392a7-228">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="392a7-229">块</span><span class="sxs-lookup"><span data-stu-id="392a7-229">Chunked</span></span>
- <span data-ttu-id="392a7-230">压缩</span><span class="sxs-lookup"><span data-stu-id="392a7-230">Compress</span></span>
- <span data-ttu-id="392a7-231">Deflate</span><span class="sxs-lookup"><span data-stu-id="392a7-231">Deflate</span></span>
- <span data-ttu-id="392a7-232">GZip</span><span class="sxs-lookup"><span data-stu-id="392a7-232">GZip</span></span>
- <span data-ttu-id="392a7-233">标识</span><span class="sxs-lookup"><span data-stu-id="392a7-233">Identity</span></span>

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

### <span data-ttu-id="392a7-234">-Uri</span><span class="sxs-lookup"><span data-stu-id="392a7-234">-Uri</span></span>

<span data-ttu-id="392a7-235">指定将 Web 请求发送到的 Internet 资源的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="392a7-235">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="392a7-236">此参数支持 HTTP、HTTPS、FTP 和 FILE 值。</span><span class="sxs-lookup"><span data-stu-id="392a7-236">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="392a7-237">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="392a7-237">This parameter is required.</span></span> <span data-ttu-id="392a7-238"> ( **Uri** ) 的参数名称是可选的。</span><span class="sxs-lookup"><span data-stu-id="392a7-238">The parameter name ( **Uri** ) is optional.</span></span>

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

### <span data-ttu-id="392a7-239">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="392a7-239">-UseBasicParsing</span></span>

<span data-ttu-id="392a7-240">指示 cmdlet 使用基本分析。</span><span class="sxs-lookup"><span data-stu-id="392a7-240">Indicates that the cmdlet uses basic parsing.</span></span> <span data-ttu-id="392a7-241">Cmdlet 返回 **String** 对象中的原始 HTML。</span><span class="sxs-lookup"><span data-stu-id="392a7-241">The cmdlet returns the raw HTML in a **String** object.</span></span>

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

### <span data-ttu-id="392a7-242">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="392a7-242">-UseDefaultCredentials</span></span>

<span data-ttu-id="392a7-243">使用当前用户的凭据来发送 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="392a7-243">Uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="392a7-244">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="392a7-244">-UserAgent</span></span>

<span data-ttu-id="392a7-245">指定 Web 请求的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="392a7-245">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="392a7-246">默认的用户代理类似于“Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0”，针对每个操作系统和平台稍有不同。</span><span class="sxs-lookup"><span data-stu-id="392a7-246">The default user agent is similar to "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0" with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="392a7-247">若要使用大多数 Internet 浏览器使用的标准用户代理字符串测试网站，请使用 [PSUserAgent](/dotnet/api/microsoft.powershell.commands) 类的属性，例如 Chrome、FireFox、Internet Explorer、Opera 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="392a7-247">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands) class, such as Chrome, FireFox, Internet Explorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="392a7-248">-WebSession</span><span class="sxs-lookup"><span data-stu-id="392a7-248">-WebSession</span></span>

<span data-ttu-id="392a7-249">指定一个 Web 请求会话。</span><span class="sxs-lookup"><span data-stu-id="392a7-249">Specifies a web request session.</span></span> <span data-ttu-id="392a7-250">输入变量名称，包括美元符号 (`$`) 。</span><span class="sxs-lookup"><span data-stu-id="392a7-250">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="392a7-251">若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。</span><span class="sxs-lookup"><span data-stu-id="392a7-251">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="392a7-252">参数值优先于 Web 请求会话中的值。</span><span class="sxs-lookup"><span data-stu-id="392a7-252">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="392a7-253">与远程会话不同，Web 请求会话不是持续性连接。</span><span class="sxs-lookup"><span data-stu-id="392a7-253">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="392a7-254">它是一个包含有关连接和请求的信息的对象，包括 Cookie、凭据、最大重定向值和用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="392a7-254">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="392a7-255">可用于共享 Web 请求之间的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="392a7-255">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="392a7-256">若要创建 web 请求会话，请在命令的 **SessionVariable** 参数的值中输入一个不带美元符号)  (的变量名称 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-256">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="392a7-257">`Invoke-RestMethod` 创建会话并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="392a7-257">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="392a7-258">在后续命令中，将该变量用作 **WebSession** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="392a7-258">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="392a7-259">不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="392a7-259">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="392a7-260">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="392a7-260">CommonParameters</span></span>

<span data-ttu-id="392a7-261">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="392a7-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="392a7-262">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="392a7-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="392a7-263">输入</span><span class="sxs-lookup"><span data-stu-id="392a7-263">Inputs</span></span>

### <span data-ttu-id="392a7-264">System.Object</span><span class="sxs-lookup"><span data-stu-id="392a7-264">System.Object</span></span>

<span data-ttu-id="392a7-265">你可以通过管道将 web 请求的正文传递给 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="392a7-265">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="392a7-266">Outputs</span><span class="sxs-lookup"><span data-stu-id="392a7-266">Outputs</span></span>

### <span data-ttu-id="392a7-267">System.Xml.Xml文档，Microsoft.PowerShell.Commands.HtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="392a7-267">System.Xml.XmlDocument, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System.String</span></span>

<span data-ttu-id="392a7-268">此 cmdlet 的输出取决于检索内容的格式。</span><span class="sxs-lookup"><span data-stu-id="392a7-268">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="392a7-269">PSObject</span><span class="sxs-lookup"><span data-stu-id="392a7-269">PSObject</span></span>

<span data-ttu-id="392a7-270">如果请求返回 JSON 字符串，则 `Invoke-RestMethod` 返回表示字符串的 PSObject。</span><span class="sxs-lookup"><span data-stu-id="392a7-270">If the request returns JSON strings, `Invoke-RestMethod` returns a PSObject that represents the strings.</span></span>

## <span data-ttu-id="392a7-271">注释</span><span class="sxs-lookup"><span data-stu-id="392a7-271">Notes</span></span>

## <span data-ttu-id="392a7-272">相关链接</span><span class="sxs-lookup"><span data-stu-id="392a7-272">Related Links</span></span>

[<span data-ttu-id="392a7-273">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="392a7-273">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="392a7-274">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="392a7-274">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="392a7-275">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="392a7-275">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
