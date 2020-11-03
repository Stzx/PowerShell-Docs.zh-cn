---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 541cceacab7462cc66483a2b75abedcd5c8abb7d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198170"
---
# <span data-ttu-id="64b25-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="64b25-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="64b25-104">摘要</span><span class="sxs-lookup"><span data-stu-id="64b25-104">SYNOPSIS</span></span>
<span data-ttu-id="64b25-105">将 HTTP 或 HTTPS 请求发送到 RESTful Web 服务。</span><span class="sxs-lookup"><span data-stu-id="64b25-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="64b25-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64b25-106">SYNTAX</span></span>

### <span data-ttu-id="64b25-107">StandardMethod (默认值) </span><span class="sxs-lookup"><span data-stu-id="64b25-107">StandardMethod (Default)</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="64b25-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="64b25-108">StandardMethodNoProxy</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="64b25-109">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="64b25-109">CustomMethod</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="64b25-110">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="64b25-110">CustomMethodNoProxy</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="64b25-111">说明</span><span class="sxs-lookup"><span data-stu-id="64b25-111">Description</span></span>

<span data-ttu-id="64b25-112">`Invoke-RestMethod`Cmdlet 将 HTTP 和 HTTPS 请求发送到具象状态传输 (REST) web 服务返回丰富的结构化数据。</span><span class="sxs-lookup"><span data-stu-id="64b25-112">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="64b25-113">PowerShell 基于数据类型设置响应的格式。</span><span class="sxs-lookup"><span data-stu-id="64b25-113">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="64b25-114">对于 RSS 或 ATOM 源，PowerShell 返回项或条目 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="64b25-114">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="64b25-115">对于 JavaScript 对象表示法 (JSON) 或 XML，PowerShell 将内容转换或反序列化为对象。</span><span class="sxs-lookup"><span data-stu-id="64b25-115">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="64b25-116">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="64b25-116">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="64b25-117">示例</span><span class="sxs-lookup"><span data-stu-id="64b25-117">EXAMPLES</span></span>

### <span data-ttu-id="64b25-118">示例1：获取 PowerShell RSS 源</span><span class="sxs-lookup"><span data-stu-id="64b25-118">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="64b25-119">此示例使用 `Invoke-RestMethod` cmdlet 从 PowerShell 博客 rss 源获取信息。</span><span class="sxs-lookup"><span data-stu-id="64b25-119">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="64b25-120">该命令使用 `Format-Table` cmdlet 来显示表中每个博客的 **Title** 和 **e** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-120">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

```powershell
Invoke-RestMethod -Uri https://blogs.msdn.microsoft.com/powershell/feed/ |
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

### <span data-ttu-id="64b25-121">示例2：运行 POST 请求</span><span class="sxs-lookup"><span data-stu-id="64b25-121">Example 2: Run a POST request</span></span>

<span data-ttu-id="64b25-122">在此示例中，用户运行 `Invoke-RestMethod` 以在用户组织中的 intranet 网站上执行 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="64b25-122">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential
$Url = "https://server.contoso.com:8089/services/search/jobs/export"
$Body = @{
    search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}
Invoke-RestMethod -Method 'Post' -Uri $url -Credential $Cred -Body $body -OutFile output.csv
```

<span data-ttu-id="64b25-123">系统会提示输入凭据，然后将其存储在中 `$Cred` ，并在中定义要访问的 URL `$Url` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-123">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="64b25-124">`$Body`变量描述搜索条件，将 CSV 指定为输出模式，并指定从两天前开始到一天结束的返回数据的时间段。</span><span class="sxs-lookup"><span data-stu-id="64b25-124">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="64b25-125">Body 变量指定适用于与之通信的特定 REST API 的参数的值 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-125">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="64b25-126">`Invoke-RestMethod`使用所有变量运行命令，并为生成的 CSV 输出文件指定路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="64b25-126">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="64b25-127">示例3：跟随关系链接</span><span class="sxs-lookup"><span data-stu-id="64b25-127">Example 3: Follow relation links</span></span>

<span data-ttu-id="64b25-128">某些 REST Api 支持通过每个 [RFC5988](https://tools.ietf.org/html/rfc5988#page-6)的关系链接进行分页。</span><span class="sxs-lookup"><span data-stu-id="64b25-128">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="64b25-129">你可以让 cmdlet 为你执行此操作，而不是分析标头以获取下一页的 URL。</span><span class="sxs-lookup"><span data-stu-id="64b25-129">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="64b25-130">此示例返回 PowerShell GitHub 存储库中的前两页问题。</span><span class="sxs-lookup"><span data-stu-id="64b25-130">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="64b25-131">示例4：简化的多部分/表单数据提交</span><span class="sxs-lookup"><span data-stu-id="64b25-131">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="64b25-132">某些 Api 需要 `multipart/form-data` 提交来上传文件和混合内容。</span><span class="sxs-lookup"><span data-stu-id="64b25-132">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="64b25-133">此示例演示如何更新用户的配置文件。</span><span class="sxs-lookup"><span data-stu-id="64b25-133">This example demonstrates how to update a user's profile.</span></span>

```powershell
$Uri = 'https://api.contoso.com/v2/profile'
$Form = @{
    firstName  = 'John'
    lastName   = 'Doe'
    email      = 'john.doe@contoso.com'
    avatar     = Get-Item -Path 'c:\Pictures\jdoe.png'
    birthday   = '1980-10-15'
    hobbies    = 'Hiking','Fishing','Jogging'
}
$Result = Invoke-RestMethod -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="64b25-134">配置文件窗体需要以下字段： `firstName` 、 `lastName` 、、、 `email` `avatar` `birthday` 和 `hobbies` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-134">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="64b25-135">该 API 需要在字段中提供用户配置文件 pic 的映像 `avatar` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-135">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="64b25-136">该 API 还将接受 `hobbies` 同一窗体中提交的多个条目。</span><span class="sxs-lookup"><span data-stu-id="64b25-136">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="64b25-137">创建 `$Form` 哈希表时，键名称将用作窗体字段名称。</span><span class="sxs-lookup"><span data-stu-id="64b25-137">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="64b25-138">默认情况下，哈希表的值将转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="64b25-138">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="64b25-139">如果 `System.IO.FileInfo` 存在值，将提交文件内容。</span><span class="sxs-lookup"><span data-stu-id="64b25-139">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="64b25-140">如果存在诸如数组或列表这样的集合，则将多次提交窗体字段。</span><span class="sxs-lookup"><span data-stu-id="64b25-140">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="64b25-141">通过 `Get-Item` 对键使用 `avatar` ，将 `FileInfo` 对象设置为值。</span><span class="sxs-lookup"><span data-stu-id="64b25-141">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="64b25-142">结果是将提交的图像数据 `jdoe.png` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-142">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="64b25-143">通过向键提供一个列表 `hobbies` ， `hobbies` 每个列表项的提交将会出现一次该字段。</span><span class="sxs-lookup"><span data-stu-id="64b25-143">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="64b25-144">示例5：传递多个标头</span><span class="sxs-lookup"><span data-stu-id="64b25-144">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="64b25-145">Api 通常要求传递的标头用于身份验证或验证。</span><span class="sxs-lookup"><span data-stu-id="64b25-145">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="64b25-146">此示例演示如何将多个标头从传递 `hash-table` 到 REST API。</span><span class="sxs-lookup"><span data-stu-id="64b25-146">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="64b25-147">parameters</span><span class="sxs-lookup"><span data-stu-id="64b25-147">Parameters</span></span>

### <span data-ttu-id="64b25-148">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="64b25-148">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="64b25-149">允许通过未加密的连接发送凭据和密码。</span><span class="sxs-lookup"><span data-stu-id="64b25-149">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="64b25-150">默认情况下，如果提供 **凭据** 或任何具有不以开头的 **Uri** 的 **身份验证** 选项，则 `https://` 会导致错误，请求将中止，以防止无意中以纯文本方式传递未加密连接的机密。</span><span class="sxs-lookup"><span data-stu-id="64b25-150">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="64b25-151">若要重写此行为，需自行承担相应的风险，请提供 **AllowUnencryptedAuthentication** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-151">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="64b25-152">使用此参数并不安全，不建议使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-152">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="64b25-153">提供它只是为了与无法提供加密连接的旧系统兼容。</span><span class="sxs-lookup"><span data-stu-id="64b25-153">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="64b25-154">使用自己的风险。</span><span class="sxs-lookup"><span data-stu-id="64b25-154">Use at your own risk.</span></span>

<span data-ttu-id="64b25-155">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-155">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="64b25-156">-Authentication</span><span class="sxs-lookup"><span data-stu-id="64b25-156">-Authentication</span></span>

<span data-ttu-id="64b25-157">指定要用于请求的显式身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="64b25-157">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="64b25-158">默认值为“无”。</span><span class="sxs-lookup"><span data-stu-id="64b25-158">The default is **None** .</span></span>
<span data-ttu-id="64b25-159">**身份验证** 不能与 **UseDefaultCredentials** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-159">**Authentication** can't be used with **UseDefaultCredentials** .</span></span>

<span data-ttu-id="64b25-160">可用的身份验证选项：</span><span class="sxs-lookup"><span data-stu-id="64b25-160">Available Authentication Options:</span></span>

- <span data-ttu-id="64b25-161">**无** ：这是未提供 **身份验证** 时的默认选项。</span><span class="sxs-lookup"><span data-stu-id="64b25-161">**None** : This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="64b25-162">不会使用显式身份验证。</span><span class="sxs-lookup"><span data-stu-id="64b25-162">No explicit authentication will be used.</span></span>
- <span data-ttu-id="64b25-163">**基本** ：需要 **凭据** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-163">**Basic** : Requires **Credential** .</span></span> <span data-ttu-id="64b25-164">凭据将用于以格式发送 RFC 7617 基本身份验证 `Authorization: Basic` 标头 `base64(user:password)` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-164">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="64b25-165">**持有** 者：需要 **标记** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-165">**Bearer** : Requires **Token** .</span></span> <span data-ttu-id="64b25-166">将 `Authorization: Bearer` 随提供的令牌一起发送和 RFC 6750 标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-166">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="64b25-167">这是 **OAuth** 的别名</span><span class="sxs-lookup"><span data-stu-id="64b25-167">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="64b25-168">**OAuth** ：需要 **标记** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-168">**OAuth** : Requires **Token** .</span></span> <span data-ttu-id="64b25-169">将 `Authorization: Bearer` 使用提供的令牌发送 RFC 6750 标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-169">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="64b25-170">这是 **持有** 者的别名</span><span class="sxs-lookup"><span data-stu-id="64b25-170">This is an alias for **Bearer**</span></span>

<span data-ttu-id="64b25-171">提供 **身份验证** 将覆盖 `Authorization` 提供给 **标头** 或包含在 **WebSession** 中的任何标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-171">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession** .</span></span>

<span data-ttu-id="64b25-172">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-172">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebAuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Bearer, OAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-173">-Body</span><span class="sxs-lookup"><span data-stu-id="64b25-173">-Body</span></span>

<span data-ttu-id="64b25-174">指定请求的正文。</span><span class="sxs-lookup"><span data-stu-id="64b25-174">Specifies the body of the request.</span></span> <span data-ttu-id="64b25-175">正文是请求的内容，位于标头之后。</span><span class="sxs-lookup"><span data-stu-id="64b25-175">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="64b25-176">还可以通过管道将正文值传递给 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-176">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="64b25-177">可以将 **Body** 参数用于指定查询参数的列表，或用于指定响应的内容。</span><span class="sxs-lookup"><span data-stu-id="64b25-177">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="64b25-178">如果输入是 GET 请求，且正文是 `IDictionary` (通常是) 哈希表，则主体将添加到统一资源标识符 (URI) 作为查询参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-178">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="64b25-179">对于其他请求类型（如 POST），将正文按标准的“名称=值”格式设置为请求正文的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-179">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="64b25-180">如果正文为窗体，或者它是另一个调用的输出 `Invoke-WebRequest` ，则 PowerShell 会将请求内容设置为窗体字段。</span><span class="sxs-lookup"><span data-stu-id="64b25-180">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="64b25-181">**Body** 参数还可以接受 **系统 MultipartFormDataContent** 对象。</span><span class="sxs-lookup"><span data-stu-id="64b25-181">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="64b25-182">这将简化 `multipart/form-data` 请求。</span><span class="sxs-lookup"><span data-stu-id="64b25-182">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="64b25-183">为 **正文** 提供 **MultipartFormDataContent** 对象时，提供给 **ContentType** 、 **标头** 或 **WebSession** 参数的任何与内容相关的标头都将被对象的内容标头重写 `MultipartFormDataContent` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-183">When a **MultipartFormDataContent** object is supplied for **Body** , any content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="64b25-184">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-184">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="64b25-185">-Certificate</span><span class="sxs-lookup"><span data-stu-id="64b25-185">-Certificate</span></span>

<span data-ttu-id="64b25-186">指定用于安全的 Web 请求的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="64b25-186">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="64b25-187">输入一个包含证书的变量，或可获取该证书的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="64b25-187">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="64b25-188">若要查找证书，请使用 `Get-PfxCertificate` 或使用 `Get-ChildItem` 证书 () 驱动器中的 cmdlet `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-188">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="64b25-189">如果证书无效或没有足够的权限，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="64b25-189">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="64b25-190">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="64b25-190">-CertificateThumbprint</span></span>

<span data-ttu-id="64b25-191">指定有权发送请求的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="64b25-191">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="64b25-192">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="64b25-192">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="64b25-193">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="64b25-193">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="64b25-194">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="64b25-194">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="64b25-195">若要获取证书指纹，请使用 `Get-Item` `Get-ChildItem` PowerShell 驱动器中的或命令 `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-195">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="64b25-196">目前只有 Windows 操作系统平台支持此功能。</span><span class="sxs-lookup"><span data-stu-id="64b25-196">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="64b25-197">-ContentType</span><span class="sxs-lookup"><span data-stu-id="64b25-197">-ContentType</span></span>

<span data-ttu-id="64b25-198">指定 Web 请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="64b25-198">Specifies the content type of the web request.</span></span>

<span data-ttu-id="64b25-199">如果省略此参数且请求方法为 POST，则 `Invoke-RestMethod` 将内容类型设置为 `application/x-www-form-urlencoded` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-199">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="64b25-200">否则，不会在调用中指定内容类型。</span><span class="sxs-lookup"><span data-stu-id="64b25-200">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="64b25-201">**ContentType** 为 `MultipartFormDataContent` **正文** 提供对象时，将覆盖 ContentType。</span><span class="sxs-lookup"><span data-stu-id="64b25-201">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="64b25-202">-Credential</span><span class="sxs-lookup"><span data-stu-id="64b25-202">-Credential</span></span>

<span data-ttu-id="64b25-203">指定有权发送请求的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="64b25-203">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="64b25-204">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="64b25-204">The default is the current user.</span></span>

<span data-ttu-id="64b25-205">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-205">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="64b25-206">**凭据** 可以单独使用，也可以与某些 **身份验证** 参数选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-206">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="64b25-207">单独使用时，如果远程服务器发送身份验证质询请求，则仅向远程服务器提供凭据。</span><span class="sxs-lookup"><span data-stu-id="64b25-207">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="64b25-208">与 **身份验证** 选项一起使用时，将显式发送凭据。</span><span class="sxs-lookup"><span data-stu-id="64b25-208">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="64b25-209">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="64b25-209">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="64b25-210">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="64b25-210">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="64b25-211">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="64b25-211">-CustomMethod</span></span>

<span data-ttu-id="64b25-212">指定用于 web 请求的自定义方法。</span><span class="sxs-lookup"><span data-stu-id="64b25-212">Specifies custom method used for the web request.</span></span> <span data-ttu-id="64b25-213">这可以与终结点所需的请求方法一起使用，而不是 **方法** 上的可用选项。</span><span class="sxs-lookup"><span data-stu-id="64b25-213">This can be used with the Request Method required by the endpoint is not an available option on the **Method** .</span></span> <span data-ttu-id="64b25-214">**方法** 和 **CustomMethod** 不能一起使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-214">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="64b25-215">示例：</span><span class="sxs-lookup"><span data-stu-id="64b25-215">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="64b25-216">这会 `TEST` 向 API 发出 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="64b25-216">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="64b25-217">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-217">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethodNoProxy, CustomMethod
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-218">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="64b25-218">-DisableKeepAlive</span></span>

<span data-ttu-id="64b25-219">指示该 cmdlet 将 HTTP 头中的 **KeepAlive** 值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="64b25-219">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="64b25-220">默认情况下， **KeepAlive** 为 True。</span><span class="sxs-lookup"><span data-stu-id="64b25-220">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="64b25-221">**KeepAlive** 建立到服务器的持续性连接，以促进后续请求。</span><span class="sxs-lookup"><span data-stu-id="64b25-221">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="64b25-222">-FollowRelLink</span><span class="sxs-lookup"><span data-stu-id="64b25-222">-FollowRelLink</span></span>

<span data-ttu-id="64b25-223">指示 cmdlet 应遵循关系链接。</span><span class="sxs-lookup"><span data-stu-id="64b25-223">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="64b25-224">某些 REST Api 支持通过每个 [RFC5988](https://tools.ietf.org/html/rfc5988#page-6)的关系链接进行分页。</span><span class="sxs-lookup"><span data-stu-id="64b25-224">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="64b25-225">你可以让 cmdlet 为你执行此操作，而不是分析标头以获取下一页的 URL。</span><span class="sxs-lookup"><span data-stu-id="64b25-225">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="64b25-226">若要设置跟踪关系链接的次数，请使用 **MaximumFollowRelLink** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-226">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="64b25-227">使用此开关时，cmdlet 将返回结果页的集合。</span><span class="sxs-lookup"><span data-stu-id="64b25-227">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="64b25-228">每页结果可能包含多个结果项。</span><span class="sxs-lookup"><span data-stu-id="64b25-228">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="64b25-229">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-229">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-230">-窗体</span><span class="sxs-lookup"><span data-stu-id="64b25-230">-Form</span></span>

<span data-ttu-id="64b25-231">将字典转换为 `multipart/form-data` 提交。</span><span class="sxs-lookup"><span data-stu-id="64b25-231">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="64b25-232">**窗体** 不能与 **正文** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-232">**Form** may not be used with **Body** .</span></span>
<span data-ttu-id="64b25-233">如果将忽略 **ContentType** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-233">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="64b25-234">字典的键将用作窗体字段名称。</span><span class="sxs-lookup"><span data-stu-id="64b25-234">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="64b25-235">默认情况下，窗体值将转换为字符串值。</span><span class="sxs-lookup"><span data-stu-id="64b25-235">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="64b25-236">如果值是 **FileInfo** 对象，则将提交二进制文件内容。</span><span class="sxs-lookup"><span data-stu-id="64b25-236">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="64b25-237">文件的名称将作为进行提交 `filename` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-237">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="64b25-238">MIME 将设置为 `application/octet-stream` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-238">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="64b25-239">`Get-Item` 可用于简化 **FileInfo** 对象的提供。</span><span class="sxs-lookup"><span data-stu-id="64b25-239">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="64b25-240">如果值是集合类型（如数组或列表），则将多次提交 for 字段。</span><span class="sxs-lookup"><span data-stu-id="64b25-240">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="64b25-241">默认情况下，列表的值将作为字符串处理。</span><span class="sxs-lookup"><span data-stu-id="64b25-241">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="64b25-242">如果值是 **FileInfo** 对象，则将提交二进制文件内容。</span><span class="sxs-lookup"><span data-stu-id="64b25-242">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="64b25-243">嵌套集合不受支持。</span><span class="sxs-lookup"><span data-stu-id="64b25-243">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="64b25-244">在上面的示例中，该 `tags` 字段将在窗体中提供三次，一次针对每个 `Vacation` 、 `Italy` 和 `2017` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-244">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="64b25-245">`pictures`对于文件夹中的每个文件，该字段也会提交一次 `2017-Italy` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-245">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="64b25-246">该文件夹中的文件的二进制内容将提交为值。</span><span class="sxs-lookup"><span data-stu-id="64b25-246">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="64b25-247">此功能已添加到 PowerShell 6.1.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-247">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="64b25-248">-标头</span><span class="sxs-lookup"><span data-stu-id="64b25-248">-Headers</span></span>

<span data-ttu-id="64b25-249">指定 Web 请求的标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-249">Specifies the headers of the web request.</span></span> <span data-ttu-id="64b25-250">输入哈希表或字典。</span><span class="sxs-lookup"><span data-stu-id="64b25-250">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="64b25-251">若要设置 UserAgent 标头，请使用 **UserAgent** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-251">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="64b25-252">不能使用此参数来指定 `User-Agent` 或 cookie 标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-252">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="64b25-253">`Content-Type`当为 `MultipartFormDataContent` **正文** 提供对象时，将重写与内容相关的标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-253">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="64b25-254">-InFile</span><span class="sxs-lookup"><span data-stu-id="64b25-254">-InFile</span></span>

<span data-ttu-id="64b25-255">从文件中获取 Web 请求的内容。</span><span class="sxs-lookup"><span data-stu-id="64b25-255">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="64b25-256">请输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="64b25-256">Enter a path and file name.</span></span> <span data-ttu-id="64b25-257">如果省略路径，则默认路径为当前位置。</span><span class="sxs-lookup"><span data-stu-id="64b25-257">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="64b25-258">-MaximumFollowRelLink</span><span class="sxs-lookup"><span data-stu-id="64b25-258">-MaximumFollowRelLink</span></span>

<span data-ttu-id="64b25-259">如果使用了 **FollowRelLink** ，则指定跟踪关系链接的次数。</span><span class="sxs-lookup"><span data-stu-id="64b25-259">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="64b25-260">如果 REST api 由于请求过多而受到限制，则可能需要较小的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-260">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="64b25-261">默认值是 `[Int32]::MaxValue`。</span><span class="sxs-lookup"><span data-stu-id="64b25-261">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="64b25-262">值 0 (零) 阻止以下关系链接。</span><span class="sxs-lookup"><span data-stu-id="64b25-262">A value of 0 (zero) prevents following relation links.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ML

Required: False
Position: Named
Default value: Int32.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-263">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="64b25-263">-MaximumRedirection</span></span>

<span data-ttu-id="64b25-264">指定在连接失败之前，PowerShell 将连接重定向到备用统一资源标识符 (URI) 的次数。</span><span class="sxs-lookup"><span data-stu-id="64b25-264">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="64b25-265">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="64b25-265">The default value is 5.</span></span> <span data-ttu-id="64b25-266">值为 0（零）将阻止所有重定向。</span><span class="sxs-lookup"><span data-stu-id="64b25-266">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="64b25-267">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="64b25-267">-MaximumRetryCount</span></span>

<span data-ttu-id="64b25-268">指定在收到400与599（含）或304之间的失败代码时，PowerShell 重试连接的次数。</span><span class="sxs-lookup"><span data-stu-id="64b25-268">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="64b25-269">另请参阅 **RetryIntervalSec** 参数以指定重试次数。</span><span class="sxs-lookup"><span data-stu-id="64b25-269">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="64b25-270">-方法</span><span class="sxs-lookup"><span data-stu-id="64b25-270">-Method</span></span>

<span data-ttu-id="64b25-271">指定用于 Web 请求的方法。</span><span class="sxs-lookup"><span data-stu-id="64b25-271">Specifies the method used for the web request.</span></span> <span data-ttu-id="64b25-272">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="64b25-272">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="64b25-273">默认</span><span class="sxs-lookup"><span data-stu-id="64b25-273">Default</span></span>
- <span data-ttu-id="64b25-274">删除</span><span class="sxs-lookup"><span data-stu-id="64b25-274">Delete</span></span>
- <span data-ttu-id="64b25-275">获取</span><span class="sxs-lookup"><span data-stu-id="64b25-275">Get</span></span>
- <span data-ttu-id="64b25-276">Head</span><span class="sxs-lookup"><span data-stu-id="64b25-276">Head</span></span>
- <span data-ttu-id="64b25-277">合并</span><span class="sxs-lookup"><span data-stu-id="64b25-277">Merge</span></span>
- <span data-ttu-id="64b25-278">选项</span><span class="sxs-lookup"><span data-stu-id="64b25-278">Options</span></span>
- <span data-ttu-id="64b25-279">修补程序</span><span class="sxs-lookup"><span data-stu-id="64b25-279">Patch</span></span>
- <span data-ttu-id="64b25-280">邮递</span><span class="sxs-lookup"><span data-stu-id="64b25-280">Post</span></span>
- <span data-ttu-id="64b25-281">Put</span><span class="sxs-lookup"><span data-stu-id="64b25-281">Put</span></span>
- <span data-ttu-id="64b25-282">跟踪</span><span class="sxs-lookup"><span data-stu-id="64b25-282">Trace</span></span>

<span data-ttu-id="64b25-283">**CustomMethod** 参数可用于上面未列出的请求方法。</span><span class="sxs-lookup"><span data-stu-id="64b25-283">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: StandardMethod, StandardMethodNoProxy
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-284">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="64b25-284">-NoProxy</span></span>

<span data-ttu-id="64b25-285">指示该 cmdlet 将不使用代理来访问目标。</span><span class="sxs-lookup"><span data-stu-id="64b25-285">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="64b25-286">如果需要跳过在 Internet Explorer 中配置的代理，或在环境中指定的代理，则使用此开关。</span><span class="sxs-lookup"><span data-stu-id="64b25-286">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="64b25-287">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="64b25-287">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethodNoProxy, CustomMethodNoProxy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-288">-OutFile</span><span class="sxs-lookup"><span data-stu-id="64b25-288">-OutFile</span></span>

<span data-ttu-id="64b25-289">将响应正文保存在指定的输出文件中。</span><span class="sxs-lookup"><span data-stu-id="64b25-289">Saves the response body in the specified output file.</span></span> <span data-ttu-id="64b25-290">请输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="64b25-290">Enter a path and file name.</span></span> <span data-ttu-id="64b25-291">如果省略路径，则默认路径为当前位置。</span><span class="sxs-lookup"><span data-stu-id="64b25-291">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="64b25-292">默认情况下，将 `Invoke-RestMethod` 结果返回到管道。</span><span class="sxs-lookup"><span data-stu-id="64b25-292">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="64b25-293">若要将这些结果发送到文件和管道，请使用 **Passthru** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-293">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="64b25-294">-PassThru</span><span class="sxs-lookup"><span data-stu-id="64b25-294">-PassThru</span></span>

<span data-ttu-id="64b25-295">除了将结果写入文件外，还将返回结果。</span><span class="sxs-lookup"><span data-stu-id="64b25-295">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="64b25-296">仅当命令中还使用了 **OutFile** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="64b25-296">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="64b25-297">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="64b25-297">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="64b25-298">指示 cmdlet 应在重定向中保留 `Authorization` 标头（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="64b25-298">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="64b25-299">默认情况下，该 cmdlet 会 `Authorization` 在重定向前去除标头。</span><span class="sxs-lookup"><span data-stu-id="64b25-299">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="64b25-300">如果指定此参数，则会在需要将标头发送到重定向位置的情况下禁用此逻辑。</span><span class="sxs-lookup"><span data-stu-id="64b25-300">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="64b25-301">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-301">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="64b25-302">-Proxy</span><span class="sxs-lookup"><span data-stu-id="64b25-302">-Proxy</span></span>

<span data-ttu-id="64b25-303">为请求使用代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="64b25-303">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="64b25-304">输入网络代理服务器 (URI) 的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="64b25-304">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="64b25-305">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-305">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-306">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="64b25-306">-ProxyCredential</span></span>

<span data-ttu-id="64b25-307">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="64b25-307">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="64b25-308">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="64b25-308">The default is the current user.</span></span>

<span data-ttu-id="64b25-309">键入用户名（如 **User01** 或 **Domain01\User01** ）， **User@Domain.Com** 或输入一个 `PSCredential` 对象，例如由 cmdlet 生成的对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-309">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="64b25-310">仅当命令中还使用了 **代理** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="64b25-310">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="64b25-311">不能在同一命令中使用 **ProxyCredential** 和 **ProxyUseDefaultCredentials** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-311">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-312">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="64b25-312">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="64b25-313">指示该 cmdlet 使用当前用户的凭据来访问 **代理** 参数指定的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="64b25-313">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="64b25-314">仅当命令中还使用了 **代理** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="64b25-314">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="64b25-315">不能在同一命令中使用 **ProxyCredential** 和 **ProxyUseDefaultCredentials** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-315">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-316">-ResponseHeadersVariable</span><span class="sxs-lookup"><span data-stu-id="64b25-316">-ResponseHeadersVariable</span></span>

<span data-ttu-id="64b25-317">创建响应标头字典，并将其保存在指定变量的值中。</span><span class="sxs-lookup"><span data-stu-id="64b25-317">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="64b25-318">字典的键将包含 web 服务器返回的响应标头的字段名称，并且值将是各自的字段值。</span><span class="sxs-lookup"><span data-stu-id="64b25-318">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="64b25-319">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-319">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RHV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-320">-Resume</span><span class="sxs-lookup"><span data-stu-id="64b25-320">-Resume</span></span>

<span data-ttu-id="64b25-321">尽力尝试恢复下载部分文件。</span><span class="sxs-lookup"><span data-stu-id="64b25-321">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="64b25-322">**Resume** 参数需要 **OutFile** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-322">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="64b25-323">**Resume** 仅对本地文件和远程文件的大小进行操作，并且不执行本地文件和远程文件相同的其他验证。</span><span class="sxs-lookup"><span data-stu-id="64b25-323">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="64b25-324">如果本地文件的大小小于远程文件大小，则该 cmdlet 将尝试继续下载文件，并将剩余字节追加到文件末尾。</span><span class="sxs-lookup"><span data-stu-id="64b25-324">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="64b25-325">如果本地文件大小与远程文件大小相同，则不会执行任何操作，并且该 cmdlet 会假设已完成下载。</span><span class="sxs-lookup"><span data-stu-id="64b25-325">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="64b25-326">如果本地文件大小大于远程文件大小，则本地文件将被覆盖，整个远程文件将被完全下载。</span><span class="sxs-lookup"><span data-stu-id="64b25-326">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="64b25-327">此行为与在不 **恢复** 的情况下使用 **OutFile** 相同。</span><span class="sxs-lookup"><span data-stu-id="64b25-327">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="64b25-328">如果远程服务器不支持下载恢复，则本地文件将被覆盖，整个远程文件将被完全重新下载。</span><span class="sxs-lookup"><span data-stu-id="64b25-328">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="64b25-329">此行为与在不 **恢复** 的情况下使用 **OutFile** 相同。</span><span class="sxs-lookup"><span data-stu-id="64b25-329">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="64b25-330">如果本地文件不存在，则将创建本地文件并完全下载整个远程文件。</span><span class="sxs-lookup"><span data-stu-id="64b25-330">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="64b25-331">此行为与在不 **恢复** 的情况下使用 **OutFile** 相同。</span><span class="sxs-lookup"><span data-stu-id="64b25-331">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="64b25-332">此功能已添加到 PowerShell 6.1.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-332">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="64b25-333">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="64b25-333">-RetryIntervalSec</span></span>

<span data-ttu-id="64b25-334">指定在收到400与599（含）或304之间的失败代码时，连接的重试间隔。</span><span class="sxs-lookup"><span data-stu-id="64b25-334">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="64b25-335">另请参阅 **MaximumRetryCount** 参数以指定重试次数。</span><span class="sxs-lookup"><span data-stu-id="64b25-335">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="64b25-336">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="64b25-336">-SessionVariable</span></span>

<span data-ttu-id="64b25-337">指定此 cmdlet 为其创建 web 请求会话的变量，并将其保存在值中。</span><span class="sxs-lookup"><span data-stu-id="64b25-337">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="64b25-338">输入一个不带美元符号 () 符号的变量名称 `$` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-338">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="64b25-339">指定会话变量时，将 `Invoke-RestMethod` 创建一个 web 请求会话对象，并将其分配给 PowerShell 会话中具有指定名称的变量。</span><span class="sxs-lookup"><span data-stu-id="64b25-339">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="64b25-340">命令完成后可以立即在会话中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="64b25-340">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="64b25-341">与远程会话不同，web 请求会话不是持续性连接。</span><span class="sxs-lookup"><span data-stu-id="64b25-341">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="64b25-342">它是一个包含有关连接和请求的信息的对象，包括 cookie、凭据、最大重定向值和用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="64b25-342">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="64b25-343">可用于共享 Web 请求之间的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="64b25-343">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="64b25-344">若要在后续的 Web 请求中使用 Web 请求会话，请在 **WebSession** 参数的值中指定会话变量。</span><span class="sxs-lookup"><span data-stu-id="64b25-344">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="64b25-345">PowerShell 在建立新连接时使用 web 请求会话对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="64b25-345">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="64b25-346">若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-346">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="64b25-347">参数值优先于 Web 请求会话中的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-347">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="64b25-348">不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-348">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="64b25-349">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="64b25-349">-SkipCertificateCheck</span></span>

<span data-ttu-id="64b25-350">跳过证书验证检查，其中包括所有验证，如过期、吊销、受信任的根证书颁发机构等。</span><span class="sxs-lookup"><span data-stu-id="64b25-350">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="64b25-351">使用此参数并不安全，不建议使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-351">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="64b25-352">此开关仅用于用于测试目的的已知主机使用自签名证书。</span><span class="sxs-lookup"><span data-stu-id="64b25-352">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="64b25-353">使用自己的风险。</span><span class="sxs-lookup"><span data-stu-id="64b25-353">Use at your own risk.</span></span>

<span data-ttu-id="64b25-354">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-354">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="64b25-355">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="64b25-355">-SkipHeaderValidation</span></span>

<span data-ttu-id="64b25-356">指示 cmdlet 应将标头添加到无验证的请求。</span><span class="sxs-lookup"><span data-stu-id="64b25-356">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="64b25-357">此开关适用于需要不符合标准的标头值的站点。</span><span class="sxs-lookup"><span data-stu-id="64b25-357">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="64b25-358">如果指定此开关，则将禁用验证以允许取消选中值。</span><span class="sxs-lookup"><span data-stu-id="64b25-358">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="64b25-359">指定时，将添加所有标头，而不进行验证。</span><span class="sxs-lookup"><span data-stu-id="64b25-359">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="64b25-360">这将禁止验证传递到 **ContentType** 、 **标头** 和 **UserAgent** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-360">This will disable validation for values passed to the **ContentType** , **Headers** , and **UserAgent** parameters.</span></span>

<span data-ttu-id="64b25-361">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-361">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="64b25-362">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="64b25-362">-SslProtocol</span></span>

<span data-ttu-id="64b25-363">设置允许用于 web 请求的 SSL/TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="64b25-363">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="64b25-364">默认情况下，允许系统支持的 SSL/TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="64b25-364">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="64b25-365">**SslProtocol** 允许出于符合性目的限制特定协议。</span><span class="sxs-lookup"><span data-stu-id="64b25-365">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="64b25-366">**SslProtocol** 使用 `WebSslProtocol` 标志 Enum。</span><span class="sxs-lookup"><span data-stu-id="64b25-366">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="64b25-367">可以使用标志表示法来提供多个协议，也可以将多个 `WebSslProtocol` 选项与结合使用 `-bor` ，但是不支持在所有平台上提供多个协议。</span><span class="sxs-lookup"><span data-stu-id="64b25-367">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="64b25-368">在非 Windows 平台上，可能无法将其 `'Tls, Tls12'` 作为选项提供。</span><span class="sxs-lookup"><span data-stu-id="64b25-368">On non-Windows platforms it may not be possible to supply `'Tls, Tls12'` as an option.</span></span>

<span data-ttu-id="64b25-369">此功能已添加到 PowerShell 6.0.0。</span><span class="sxs-lookup"><span data-stu-id="64b25-369">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-370">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="64b25-370">-TimeoutSec</span></span>

<span data-ttu-id="64b25-371">指定在超时之前请求可以挂起多长时间。输入一个值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="64b25-371">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="64b25-372">默认值 0 指定无限超时。</span><span class="sxs-lookup"><span data-stu-id="64b25-372">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="64b25-373">域名系统 (DNS) 查询可能需要长达15秒钟的时间来返回或超时。如果你的请求包含需要解析的主机名，并将 **TimeoutSec** 设置为大于零的值，但不超过15秒，则在引发 WebException 之前可能需要15秒或更长时间，并且你的请求会超时。</span><span class="sxs-lookup"><span data-stu-id="64b25-373">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-374">-Token</span><span class="sxs-lookup"><span data-stu-id="64b25-374">-Token</span></span>

<span data-ttu-id="64b25-375">要包含在请求中的 OAuth 或持有者令牌。</span><span class="sxs-lookup"><span data-stu-id="64b25-375">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="64b25-376">某些 **身份验证** 选项需要 **标记** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-376">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="64b25-377">不能单独使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-377">It can't be used independently.</span></span>

<span data-ttu-id="64b25-378">**令牌** 采用 `SecureString` 包含标记的。</span><span class="sxs-lookup"><span data-stu-id="64b25-378">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="64b25-379">若要提供令牌，请手动使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="64b25-379">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="64b25-380">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="64b25-380">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-381">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="64b25-381">-TransferEncoding</span></span>

<span data-ttu-id="64b25-382">指定传输编码 HTTP 响应头的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-382">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="64b25-383">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="64b25-383">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="64b25-384">块</span><span class="sxs-lookup"><span data-stu-id="64b25-384">Chunked</span></span>
- <span data-ttu-id="64b25-385">压缩</span><span class="sxs-lookup"><span data-stu-id="64b25-385">Compress</span></span>
- <span data-ttu-id="64b25-386">Deflate</span><span class="sxs-lookup"><span data-stu-id="64b25-386">Deflate</span></span>
- <span data-ttu-id="64b25-387">GZip</span><span class="sxs-lookup"><span data-stu-id="64b25-387">GZip</span></span>
- <span data-ttu-id="64b25-388">标识</span><span class="sxs-lookup"><span data-stu-id="64b25-388">Identity</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-389">-Uri</span><span class="sxs-lookup"><span data-stu-id="64b25-389">-Uri</span></span>

<span data-ttu-id="64b25-390">指定将 web 请求发送到的 internet 资源 (URI) 的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="64b25-390">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="64b25-391">此参数支持 HTTP、HTTPS、FTP 和 FILE 值。</span><span class="sxs-lookup"><span data-stu-id="64b25-391">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="64b25-392">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="64b25-392">This parameter is required.</span></span> <span data-ttu-id="64b25-393"> ( **Uri** ) 的参数名称是可选的。</span><span class="sxs-lookup"><span data-stu-id="64b25-393">The parameter name ( **Uri** ) is optional.</span></span>

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-394">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="64b25-394">-UseBasicParsing</span></span>

<span data-ttu-id="64b25-395">此参数已弃用。</span><span class="sxs-lookup"><span data-stu-id="64b25-395">This parameter has been deprecated.</span></span> <span data-ttu-id="64b25-396">从 PowerShell 6.0.0 开始，所有 Web 请求仅使用基本分析。</span><span class="sxs-lookup"><span data-stu-id="64b25-396">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="64b25-397">提供此参数只是为了实现向后兼容性，并且对此参数的任何使用都不会影响 cmdlet 的操作。</span><span class="sxs-lookup"><span data-stu-id="64b25-397">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-398">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="64b25-398">-UseDefaultCredentials</span></span>

<span data-ttu-id="64b25-399">指示该 cmdlet 使用当前用户的凭据来发送 web 请求。</span><span class="sxs-lookup"><span data-stu-id="64b25-399">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="64b25-400">这不能用于 **身份验证** 或 **凭据** ，并且可能在所有平台上都不受支持。</span><span class="sxs-lookup"><span data-stu-id="64b25-400">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-401">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="64b25-401">-UserAgent</span></span>

<span data-ttu-id="64b25-402">指定 Web 请求的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="64b25-402">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="64b25-403">默认的用户代理类似于 `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` 每个操作系统和平台稍有不同。</span><span class="sxs-lookup"><span data-stu-id="64b25-403">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="64b25-404">若要使用大多数 internet 浏览器使用的标准用户代理字符串测试网站，请使用 [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) 类的属性，例如 Chrome、FireFox、Microsoft-windows-ie-internetexplorer、Opera 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="64b25-404">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-405">-WebSession</span><span class="sxs-lookup"><span data-stu-id="64b25-405">-WebSession</span></span>

<span data-ttu-id="64b25-406">指定一个 Web 请求会话。</span><span class="sxs-lookup"><span data-stu-id="64b25-406">Specifies a web request session.</span></span> <span data-ttu-id="64b25-407">输入变量名称，包括美元符号 (`$`) 。</span><span class="sxs-lookup"><span data-stu-id="64b25-407">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="64b25-408">若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-408">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="64b25-409">参数值优先于 Web 请求会话中的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-409">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="64b25-410">为 `Content-Type` **正文** 提供 **MultipartFormDataContent** 对象时，也会重写与内容相关的标头（例如）。</span><span class="sxs-lookup"><span data-stu-id="64b25-410">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

<span data-ttu-id="64b25-411">与远程会话不同，web 请求会话不是持续性连接。</span><span class="sxs-lookup"><span data-stu-id="64b25-411">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="64b25-412">它是一个包含有关连接和请求的信息的对象，包括 cookie、凭据、最大重定向值和用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="64b25-412">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="64b25-413">可用于共享 Web 请求之间的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="64b25-413">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="64b25-414">若要创建 web 请求会话，请在命令的 **SessionVariable** 参数的值中输入一个不带美元符号的变量名称 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-414">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="64b25-415">`Invoke-RestMethod` 创建会话并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="64b25-415">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="64b25-416">在后续命令中，将该变量用作 **WebSession** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="64b25-416">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="64b25-417">不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="64b25-417">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b25-418">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="64b25-418">CommonParameters</span></span>

<span data-ttu-id="64b25-419">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="64b25-419">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64b25-420">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="64b25-420">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64b25-421">输入</span><span class="sxs-lookup"><span data-stu-id="64b25-421">INPUTS</span></span>

### <span data-ttu-id="64b25-422">System.Object</span><span class="sxs-lookup"><span data-stu-id="64b25-422">System.Object</span></span>

<span data-ttu-id="64b25-423">你可以通过管道将 web 请求的正文传递给 `Invoke-RestMethod` 。</span><span class="sxs-lookup"><span data-stu-id="64b25-423">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="64b25-424">输出</span><span class="sxs-lookup"><span data-stu-id="64b25-424">OUTPUTS</span></span>

### <span data-ttu-id="64b25-425">System.object、System.string System.Xml.Xml文档</span><span class="sxs-lookup"><span data-stu-id="64b25-425">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="64b25-426">此 cmdlet 的输出取决于检索内容的格式。</span><span class="sxs-lookup"><span data-stu-id="64b25-426">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="64b25-427">PSObject</span><span class="sxs-lookup"><span data-stu-id="64b25-427">PSObject</span></span>

<span data-ttu-id="64b25-428">如果请求返回 JSON 字符串，则 `Invoke-RestMethod` 返回表示字符串的 **PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="64b25-428">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="64b25-429">注释</span><span class="sxs-lookup"><span data-stu-id="64b25-429">NOTES</span></span>

<span data-ttu-id="64b25-430">某些功能可能无法在所有平台上使用。</span><span class="sxs-lookup"><span data-stu-id="64b25-430">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="64b25-431">有关 .NET 如何向 PowerShell 提供代理服务的详细信息，请参阅 [通过代理访问 Internet](/dotnet/framework/network-programming/accessing-the-internet-through-a-proxy)。</span><span class="sxs-lookup"><span data-stu-id="64b25-431">For more information about how .NET provides proxy services to PowerShell, see [Accessing the Internet Through a Proxy](/dotnet/framework/network-programming/accessing-the-internet-through-a-proxy).</span></span>

## <span data-ttu-id="64b25-432">相关链接</span><span class="sxs-lookup"><span data-stu-id="64b25-432">RELATED LINKS</span></span>

[<span data-ttu-id="64b25-433">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="64b25-433">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="64b25-434">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="64b25-434">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="64b25-435">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="64b25-435">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
