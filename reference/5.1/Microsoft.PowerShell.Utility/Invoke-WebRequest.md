---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 25da6262e93be3e3749aabaf4950e2fbcd91ff5c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "93199237"
---
# <span data-ttu-id="3bcbc-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="3bcbc-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="3bcbc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3bcbc-104">SYNOPSIS</span></span>
<span data-ttu-id="3bcbc-105">从 Internet 上的网页中获取内容。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-105">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="3bcbc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3bcbc-106">SYNTAX</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="3bcbc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3bcbc-107">DESCRIPTION</span></span>

<span data-ttu-id="3bcbc-108">`Invoke-WebRequest`Cmdlet 可将 HTTP、HTTPS、FTP 和文件请求发送到网页或 web 服务。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-108">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="3bcbc-109">它将分析该响应并返回表单、链接、图像和其他重要的 HTML 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-109">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="3bcbc-110">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="3bcbc-111">默认情况下，在分析页时，可能会运行网页中的脚本代码来填充 `ParsedHtml` 属性。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-111">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span>
> <span data-ttu-id="3bcbc-112">使用 `-UseBasicParsing` 开关可取消显示此选项。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-112">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="3bcbc-113">示例</span><span class="sxs-lookup"><span data-stu-id="3bcbc-113">EXAMPLES</span></span>

### <span data-ttu-id="3bcbc-114">示例1：发送 web 请求</span><span class="sxs-lookup"><span data-stu-id="3bcbc-114">Example 1: Send a web request</span></span>

<span data-ttu-id="3bcbc-115">此命令使用 `Invoke-WebRequest` cmdlet 向 Bing.com 站点发送 web 请求。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-115">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$R = Invoke-WebRequest -URI https://www.bing.com?q=how+many+feet+in+a+mile
$R.AllElements | Where-Object {
    $_.name -like "* Value" -and $_.tagName -eq "INPUT"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="3bcbc-116">第一个命令发出请求，并将响应保存在 `$R` 变量中。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-116">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="3bcbc-117">第二个命令筛选 **大于** 属性中的对象，其中 **name** 属性类似于 "\* Value"， **tagName** 为 "INPUT"。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-117">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="3bcbc-118">筛选后的结果将通过管道传递到 `Select-Object` ，以选择 **名称** 和 **值** 属性。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-118">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="3bcbc-119">示例2：使用有状态 web 服务</span><span class="sxs-lookup"><span data-stu-id="3bcbc-119">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="3bcbc-120">此示例演示如何将 `Invoke-WebRequest` cmdlet 与有状态 web 服务（如 Facebook）结合使用。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-120">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

```powershell
$R = Invoke-WebRequest https://www.facebook.com/login.php -SessionVariable fb
# This command stores the first form in the Forms property of the $R variable in the $Form variable.
$Form = $R.Forms[0]
# This command shows the fields available in the Form.
$Form.fields
```

```Output
Key                     Value
---                     -----
...
email
pass
...
```

```powershell
# These commands populate the username and password of the respective Form fields.
$Form.Fields["email"]="User01@Fabrikam.com"
$Form.Fields["pass"]="P@ssw0rd"
# This command creates the Uri that will be used to log in to facebook.
# The value of the Uri parameter is the value of the Action property of the form.
$Uri = "https://www.facebook.com" + $Form.Action
# Now the Invoke-WebRequest cmdlet is used to sign into the Facebook web service.
# The WebRequestSession object in the $FB variable is passed as the value of the WebSession parameter.
# The value of the Body parameter is the hash table in the Fields property of the form.
# The value of the *Method* parameter is POST. The command saves the output in the $R variable.
$R = Invoke-WebRequest -Uri $Uri -WebSession $FB -Method POST -Body $Form.Fields
$R.StatusDescription
```

<span data-ttu-id="3bcbc-121">第一个命令使用 `Invoke-WebRequest` cmdlet 发送登录请求。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-121">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="3bcbc-122">该命令为 **SessionVariable** 参数的值指定值 "FB"，并将结果保存在 `$R` 变量中。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-122">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="3bcbc-123">当该命令完成时， `$R` 变量将包含一个 **HtmlWebResponseObject** ，该 `$FB` 变量将包含一个 **WebRequestSession** 对象。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-123">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="3bcbc-124">Cmdlet 登录 `Invoke-WebRequest` 到 facebook 后，变量中的 web 响应对象的 **StatusDescription** 属性 `$R` 指示用户已成功登录。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-124">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="3bcbc-125">示例3：获取网页中的链接</span><span class="sxs-lookup"><span data-stu-id="3bcbc-125">Example 3: Get links from a web page</span></span>

<span data-ttu-id="3bcbc-126">此命令将获取网页中的链接。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-126">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="3bcbc-127">`Invoke-WebRequest`Cmdlet 将获取网页内容。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-127">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="3bcbc-128">然后，返回的 **HtmlWebResponseObject** 的 **Links** 属性用于显示每个链接的 **Href** 属性。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-128">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="3bcbc-129">示例4：捕获 Invoke-WebRequest 中的非成功消息</span><span class="sxs-lookup"><span data-stu-id="3bcbc-129">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="3bcbc-130">如果 `Invoke-WebRequest` 遇到非成功 HTTP 消息 (404、500等 ) ，它将不返回任何输出，并引发终止错误。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-130">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="3bcbc-131">若要捕获错误并查看 **StatusCode** ，可以在块中包含执行 `try/catch` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-131">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="3bcbc-132">下面的示例演示如何实现此目的。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-132">The following example shows how to accomplish this.</span></span>

```powershell
try
{
    $response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
    # This will only execute if the Invoke-WebRequest is successful.
    $StatusCode = $Response.StatusCode
}
catch
{
    $StatusCode = $_.Exception.Response.StatusCode.value__
}
$StatusCode
```

```Output
404
```

<span data-ttu-id="3bcbc-133">第一条命令调用 `Invoke-WebRequest` ， **ErrorAction** 为 **Stop** ，这会强制 `Invoke-WebRequest` 引发任何失败请求时的终止错误。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-133">The first command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="3bcbc-134">终止错误由 `catch` 从 **异常** 对象检索 **StatusCode** 的块捕获。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-134">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="3bcbc-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3bcbc-135">PARAMETERS</span></span>

### <span data-ttu-id="3bcbc-136">-Body</span><span class="sxs-lookup"><span data-stu-id="3bcbc-136">-Body</span></span>

<span data-ttu-id="3bcbc-137">指定请求的正文。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-137">Specifies the body of the request.</span></span>
<span data-ttu-id="3bcbc-138">正文是请求的内容，位于标头之后。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-138">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="3bcbc-139">还可以通过管道将正文值传递给 `Invoke-WebRequest` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-139">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="3bcbc-140">可以将 **Body** 参数用于指定查询参数的列表，或用于指定响应的内容。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-140">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="3bcbc-141">当输入是一个 GET 请求且正文是一个 **IDictionary** (通常情况下) 哈希表中，主体将作为查询参数添加到 URI 中。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-141">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="3bcbc-142">对于其他 GET 请求，主体将设置为标准格式的请求正文的值 `name=value` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-142">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="3bcbc-143">当正文是窗体或调用的输出时 `Invoke-WebRequest` ，PowerShell 会将请求内容设置为窗体字段。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-143">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="3bcbc-144">例如：</span><span class="sxs-lookup"><span data-stu-id="3bcbc-144">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="3bcbc-145">或 -</span><span class="sxs-lookup"><span data-stu-id="3bcbc-145">or -</span></span>

`Invoke-RestMethod https://website.com/service.aspx -Body $r.Forms\[0\]`

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

### <span data-ttu-id="3bcbc-146">-Certificate</span><span class="sxs-lookup"><span data-stu-id="3bcbc-146">-Certificate</span></span>

<span data-ttu-id="3bcbc-147">指定用于安全的 Web 请求的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-147">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="3bcbc-148">输入一个包含证书的变量，或可获取该证书的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-148">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="3bcbc-149">若要查找证书，请使用 `Get-PfxCertificate` 或使用 `Get-ChildItem` **证书** () 驱动器中的 cmdlet `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-149">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="3bcbc-150">如果证书无效或不具有足够的权限，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-150">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="3bcbc-151">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="3bcbc-151">-CertificateThumbprint</span></span>

<span data-ttu-id="3bcbc-152">指定有权发送请求的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-152">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="3bcbc-153">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-153">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="3bcbc-154">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-154">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="3bcbc-155">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-155">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="3bcbc-156">若要获取证书指纹，请使用 `Get-Item` `Get-ChildItem` PowerShell 驱动器中的或命令 `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-156">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

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

### <span data-ttu-id="3bcbc-157">-ContentType</span><span class="sxs-lookup"><span data-stu-id="3bcbc-157">-ContentType</span></span>

<span data-ttu-id="3bcbc-158">指定 Web 请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-158">Specifies the content type of the web request.</span></span>

<span data-ttu-id="3bcbc-159">如果省略此参数且请求方法为 POST，则 `Invoke-WebRequest` 将内容类型设置为 application/x-url 编码。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-159">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="3bcbc-160">否则，将不会在调用中指定内容类型。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-160">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="3bcbc-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="3bcbc-161">-Credential</span></span>

<span data-ttu-id="3bcbc-162">指定有权发送请求的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-162">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="3bcbc-163">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-163">The default is the current user.</span></span>

<span data-ttu-id="3bcbc-164">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="3bcbc-165">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-165">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="3bcbc-166">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-166">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="3bcbc-167">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="3bcbc-167">-DisableKeepAlive</span></span>

<span data-ttu-id="3bcbc-168">指示该 cmdlet 将 HTTP 头中的 **KeepAlive** 值设置为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-168">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False** .</span></span> <span data-ttu-id="3bcbc-169">默认情况下， **KeepAlive** 为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-169">By default, **KeepAlive** is **True** .</span></span> <span data-ttu-id="3bcbc-170">**KeepAlive** 建立到服务器的持续性连接，以促进后续请求。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-170">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="3bcbc-171">-标头</span><span class="sxs-lookup"><span data-stu-id="3bcbc-171">-Headers</span></span>

<span data-ttu-id="3bcbc-172">指定 Web 请求的标头。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-172">Specifies the headers of the web request.</span></span> <span data-ttu-id="3bcbc-173">输入哈希表或字典。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-173">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="3bcbc-174">若要设置 **UserAgent** 标头，请使用 **UserAgent** 参数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-174">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="3bcbc-175">不能使用此参数指定 **UserAgent** 或 cookie 标头。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-175">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

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

### <span data-ttu-id="3bcbc-176">-InFile</span><span class="sxs-lookup"><span data-stu-id="3bcbc-176">-InFile</span></span>

<span data-ttu-id="3bcbc-177">从文件中获取 Web 请求的内容。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-177">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="3bcbc-178">请输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-178">Enter a path and file name.</span></span> <span data-ttu-id="3bcbc-179">如果省略路径，则默认路径为当前位置。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-179">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="3bcbc-180">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="3bcbc-180">-MaximumRedirection</span></span>

<span data-ttu-id="3bcbc-181">指定在连接失败之前，PowerShell 将连接重定向到备用统一资源标识符 (URI) 的次数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-181">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="3bcbc-182">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-182">The default value is 5.</span></span> <span data-ttu-id="3bcbc-183">值为 0（零）将阻止所有重定向。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-183">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="3bcbc-184">-方法</span><span class="sxs-lookup"><span data-stu-id="3bcbc-184">-Method</span></span>

<span data-ttu-id="3bcbc-185">指定用于 Web 请求的方法。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-185">Specifies the method used for the web request.</span></span> <span data-ttu-id="3bcbc-186">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="3bcbc-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3bcbc-187">默认</span><span class="sxs-lookup"><span data-stu-id="3bcbc-187">Default</span></span>
- <span data-ttu-id="3bcbc-188">删除</span><span class="sxs-lookup"><span data-stu-id="3bcbc-188">Delete</span></span>
- <span data-ttu-id="3bcbc-189">获取</span><span class="sxs-lookup"><span data-stu-id="3bcbc-189">Get</span></span>
- <span data-ttu-id="3bcbc-190">Head</span><span class="sxs-lookup"><span data-stu-id="3bcbc-190">Head</span></span>
- <span data-ttu-id="3bcbc-191">合并</span><span class="sxs-lookup"><span data-stu-id="3bcbc-191">Merge</span></span>
- <span data-ttu-id="3bcbc-192">选项</span><span class="sxs-lookup"><span data-stu-id="3bcbc-192">Options</span></span>
- <span data-ttu-id="3bcbc-193">修补程序</span><span class="sxs-lookup"><span data-stu-id="3bcbc-193">Patch</span></span>
- <span data-ttu-id="3bcbc-194">邮递</span><span class="sxs-lookup"><span data-stu-id="3bcbc-194">Post</span></span>
- <span data-ttu-id="3bcbc-195">Put</span><span class="sxs-lookup"><span data-stu-id="3bcbc-195">Put</span></span>
- <span data-ttu-id="3bcbc-196">跟踪</span><span class="sxs-lookup"><span data-stu-id="3bcbc-196">Trace</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3bcbc-197">-OutFile</span><span class="sxs-lookup"><span data-stu-id="3bcbc-197">-OutFile</span></span>

<span data-ttu-id="3bcbc-198">指定此 cmdlet 为其保存响应正文的输出文件。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-198">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="3bcbc-199">请输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-199">Enter a path and file name.</span></span>
<span data-ttu-id="3bcbc-200">如果省略路径，则默认路径为当前位置。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-200">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="3bcbc-201">默认情况下，将 `Invoke-WebRequest` 结果返回到管道。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-201">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="3bcbc-202">若要将这些结果发送到文件和管道，请使用 **Passthru** 参数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-202">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="3bcbc-203">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3bcbc-203">-PassThru</span></span>

<span data-ttu-id="3bcbc-204">指示除了将结果写入文件外，该 cmdlet 还会返回结果。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-204">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="3bcbc-205">仅当命令中还使用了 **OutFile** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-205">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="3bcbc-206">-Proxy</span><span class="sxs-lookup"><span data-stu-id="3bcbc-206">-Proxy</span></span>

<span data-ttu-id="3bcbc-207">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-207">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="3bcbc-208">输入网络代理服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-208">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="3bcbc-209">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="3bcbc-209">-ProxyCredential</span></span>

<span data-ttu-id="3bcbc-210">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-210">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="3bcbc-211">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-211">The default is the current user.</span></span>

<span data-ttu-id="3bcbc-212">键入用户名（如 `User01` 或 `Domain01\User01` ），或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-212">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="3bcbc-213">仅当命令中还使用了 **代理** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-213">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="3bcbc-214">不能在同一命令中使用 **ProxyCredential** 参数和 **ProxyUseDefaultCredentials** 参数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-214">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="3bcbc-215">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="3bcbc-215">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="3bcbc-216">指示该 cmdlet 使用当前用户的凭据来访问 **代理** 参数指定的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-216">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="3bcbc-217">仅当命令中还使用了 **代理** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-217">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="3bcbc-218">不能在同一命令中使用 **ProxyCredential** 参数和 **ProxyUseDefaultCredentials** 参数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-218">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="3bcbc-219">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="3bcbc-219">-SessionVariable</span></span>

<span data-ttu-id="3bcbc-220">指定此 cmdlet 为其创建 web 请求会话的变量，并将其保存在值中。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-220">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="3bcbc-221">输入一个不带美元符号 () 符号的变量名称 `$` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-221">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="3bcbc-222">指定会话变量时，将 `Invoke-WebRequest` 创建一个 web 请求会话对象，并将其分配给 PowerShell 会话中具有指定名称的变量。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-222">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="3bcbc-223">命令完成后可以立即在会话中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-223">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="3bcbc-224">与远程会话不同，Web 请求会话不是持续性连接。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-224">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="3bcbc-225">它是一个包含有关连接和请求的信息的对象，包括 Cookie、凭据、最大重定向值和用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-225">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="3bcbc-226">可用于共享 Web 请求之间的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-226">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="3bcbc-227">若要在后续的 Web 请求中使用 Web 请求会话，请在 **WebSession** 参数的值中指定会话变量。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-227">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="3bcbc-228">PowerShell 在建立新连接时使用 web 请求会话对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-228">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="3bcbc-229">若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-229">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="3bcbc-230">参数值优先于 Web 请求会话中的值。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-230">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="3bcbc-231">不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-231">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="3bcbc-232">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="3bcbc-232">-TimeoutSec</span></span>

<span data-ttu-id="3bcbc-233">指定在超时之前请求可以挂起多长时间。输入一个值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-233">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="3bcbc-234">默认值 0 指定无限超时。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-234">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="3bcbc-235">域名系统 (DNS) 查询可能需要长达15秒钟的时间来返回或超时。如果你的请求包含需要解析的主机名，并将 **TimeoutSec** 设置为大于零的值，但不超过15秒，则在引发 **WebException** 之前可能需要15秒或更长时间，并且你的请求会超时。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-235">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="3bcbc-236">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="3bcbc-236">-TransferEncoding</span></span>

<span data-ttu-id="3bcbc-237">指定传输编码 HTTP 响应头的值。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-237">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="3bcbc-238">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="3bcbc-238">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3bcbc-239">块</span><span class="sxs-lookup"><span data-stu-id="3bcbc-239">Chunked</span></span>
- <span data-ttu-id="3bcbc-240">压缩</span><span class="sxs-lookup"><span data-stu-id="3bcbc-240">Compress</span></span>
- <span data-ttu-id="3bcbc-241">Deflate</span><span class="sxs-lookup"><span data-stu-id="3bcbc-241">Deflate</span></span>
- <span data-ttu-id="3bcbc-242">GZip</span><span class="sxs-lookup"><span data-stu-id="3bcbc-242">GZip</span></span>
- <span data-ttu-id="3bcbc-243">标识</span><span class="sxs-lookup"><span data-stu-id="3bcbc-243">Identity</span></span>

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

### <span data-ttu-id="3bcbc-244">-Uri</span><span class="sxs-lookup"><span data-stu-id="3bcbc-244">-Uri</span></span>

<span data-ttu-id="3bcbc-245">指定将 Web 请求发送到的 Internet 资源的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-245">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="3bcbc-246">输入 URI。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-246">Enter a URI.</span></span> <span data-ttu-id="3bcbc-247">此参数支持 HTTP、HTTPS、FTP 和 FILE 值。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-247">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="3bcbc-248">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-248">This parameter is required.</span></span>

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

### <span data-ttu-id="3bcbc-249">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="3bcbc-249">-UseBasicParsing</span></span>

<span data-ttu-id="3bcbc-250">指示 cmdlet 使用 HTML 内容的响应对象，而不文档对象模型 (DOM) 进行分析。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-250">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="3bcbc-251">当 Internet Explorer 未安装在计算机上（例如在 Windows Server 操作系统安装 Server Core）时，此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-251">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="3bcbc-252">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="3bcbc-252">-UseDefaultCredentials</span></span>

<span data-ttu-id="3bcbc-253">指示 cmdet 使用当前用户的凭据来发送 web 请求。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-253">Indicates that the cmdet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="3bcbc-254">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="3bcbc-254">-UserAgent</span></span>

<span data-ttu-id="3bcbc-255">指定 Web 请求的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-255">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="3bcbc-256">默认的用户代理类似于 `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` 每个操作系统和平台稍有不同。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-256">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="3bcbc-257">若要使用大多数 Internet 浏览器使用的标准用户代理字符串测试网站，请使用 [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) 类的属性，例如 Chrome、FireFox、Microsoft-windows-ie-internetexplorer、Opera 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-257">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="3bcbc-258">例如，以下命令使用 Internet Explorer 的用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="3bcbc-258">For example, the following command uses the user agent string for Internet Explorer</span></span>

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

### <span data-ttu-id="3bcbc-259">-WebSession</span><span class="sxs-lookup"><span data-stu-id="3bcbc-259">-WebSession</span></span>

<span data-ttu-id="3bcbc-260">指定一个 Web 请求会话。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-260">Specifies a web request session.</span></span> <span data-ttu-id="3bcbc-261">输入变量名称，包括美元符号 (`$`) 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-261">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="3bcbc-262">若要在 Web 请求会话中重写某个值，请使用 cmdlet 参数，如 **UserAgent** 或 **Credential** 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-262">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="3bcbc-263">参数值优先于 Web 请求会话中的值。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-263">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="3bcbc-264">与远程会话不同，Web 请求会话不是持续性连接。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-264">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="3bcbc-265">它是一个包含有关连接和请求的信息的对象，包括 Cookie、凭据、最大重定向值和用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-265">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="3bcbc-266">可用于共享 Web 请求之间的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-266">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="3bcbc-267">若要创建 web 请求会话，请在命令的 **SessionVariable** 参数的值中输入一个不带美元符号)  (的变量名称 `Invoke-WebRequest` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-267">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="3bcbc-268">`Invoke-WebRequest` 创建会话并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-268">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="3bcbc-269">在后续命令中，将该变量用作 **WebSession** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-269">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="3bcbc-270">不能在同一命令中使用 **SessionVariable** 和 **WebSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-270">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="3bcbc-271">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3bcbc-271">CommonParameters</span></span>

<span data-ttu-id="3bcbc-272">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-272">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="3bcbc-273">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3bcbc-274">输入</span><span class="sxs-lookup"><span data-stu-id="3bcbc-274">INPUTS</span></span>

### <span data-ttu-id="3bcbc-275">System.Object</span><span class="sxs-lookup"><span data-stu-id="3bcbc-275">System.Object</span></span>

<span data-ttu-id="3bcbc-276">你可以通过管道将 web 请求的正文传递给 `Invoke-WebRequest` 。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-276">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="3bcbc-277">输出</span><span class="sxs-lookup"><span data-stu-id="3bcbc-277">OUTPUTS</span></span>

### <span data-ttu-id="3bcbc-278">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="3bcbc-278">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="3bcbc-279">注释</span><span class="sxs-lookup"><span data-stu-id="3bcbc-279">NOTES</span></span>

## <span data-ttu-id="3bcbc-280">相关链接</span><span class="sxs-lookup"><span data-stu-id="3bcbc-280">RELATED LINKS</span></span>

[<span data-ttu-id="3bcbc-281">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="3bcbc-281">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="3bcbc-282">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="3bcbc-282">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="3bcbc-283">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="3bcbc-283">ConvertTo-Json</span></span>](ConvertTo-Json.md)
