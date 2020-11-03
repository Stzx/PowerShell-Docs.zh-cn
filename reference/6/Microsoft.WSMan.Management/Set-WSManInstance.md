---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 3f4ee9edf6e8dfce21a51ff9c055fe56a0cbef3c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199067"
---
# <span data-ttu-id="919be-103">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="919be-103">Set-WSManInstance</span></span>

## <span data-ttu-id="919be-104">摘要</span><span class="sxs-lookup"><span data-stu-id="919be-104">SYNOPSIS</span></span>
<span data-ttu-id="919be-105">修改与某个资源相关的管理信息。</span><span class="sxs-lookup"><span data-stu-id="919be-105">Modifies the management information that is related to a resource.</span></span>

## <span data-ttu-id="919be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="919be-106">SYNTAX</span></span>

### <span data-ttu-id="919be-107">ComputerName（默认值）</span><span class="sxs-lookup"><span data-stu-id="919be-107">ComputerName (Default)</span></span>

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="919be-108">URI</span><span class="sxs-lookup"><span data-stu-id="919be-108">URI</span></span>

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="919be-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="919be-109">DESCRIPTION</span></span>

<span data-ttu-id="919be-110">Set-WSManInstance cmdlet 可修改与某个资源相关的管理信息。</span><span class="sxs-lookup"><span data-stu-id="919be-110">The Set-WSManInstance cmdlet modifies the management information that is related to a resource.</span></span>

<span data-ttu-id="919be-111">此 cmdlet 使用 WinRM 连接/传输层来修改这些信息。</span><span class="sxs-lookup"><span data-stu-id="919be-111">This cmdlet uses the WinRM connection/transport layer to modify the information.</span></span>

## <span data-ttu-id="919be-112">示例</span><span class="sxs-lookup"><span data-stu-id="919be-112">EXAMPLES</span></span>

### <span data-ttu-id="919be-113">示例1：禁用本地计算机上的侦听器</span><span class="sxs-lookup"><span data-stu-id="919be-113">Example 1: Disable a listener on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

<span data-ttu-id="919be-114">此命令可禁用本地计算机上的 https 侦听器。</span><span class="sxs-lookup"><span data-stu-id="919be-114">This command disables the https listener on the local computer.</span></span>

<span data-ttu-id="919be-115">重要提示：当匹配指定的属性时， *ValueSet* 参数区分大小写。</span><span class="sxs-lookup"><span data-stu-id="919be-115">Important: The *ValueSet* parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="919be-116">例如，在此命令中，</span><span class="sxs-lookup"><span data-stu-id="919be-116">For example, in this command,</span></span>

<span data-ttu-id="919be-117">这会失败： `-ValueSet @{enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="919be-117">This fails: `-ValueSet @{enabled="False"}`</span></span>

<span data-ttu-id="919be-118">这会成功： `-ValueSet @{Enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="919be-118">This succeeds: `-ValueSet @{Enabled="False"}`</span></span>

### <span data-ttu-id="919be-119">示例2：在本地计算机上设置最大信封大小</span><span class="sxs-lookup"><span data-stu-id="919be-119">Example 2: Set the maximum envelope size on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

<span data-ttu-id="919be-120">此命令在本地计算机上将 MaxEnvelopeSizekb 值设置为 200。</span><span class="sxs-lookup"><span data-stu-id="919be-120">This command sets the MaxEnvelopeSizekb value to 200 on the local computer.</span></span>

<span data-ttu-id="919be-121">重要信息：在与指定的属性进行匹配时，ValueSet 参数区分大小写。</span><span class="sxs-lookup"><span data-stu-id="919be-121">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="919be-122">例如，使用上面的命令时，</span><span class="sxs-lookup"><span data-stu-id="919be-122">For example, using the above command.</span></span>

<span data-ttu-id="919be-123">这会失败：-ValueSet @ {MaxEnvelopeSizeKB = "200"}</span><span class="sxs-lookup"><span data-stu-id="919be-123">This fails:     -ValueSet @{MaxEnvelopeSizeKB ="200"}</span></span>

<span data-ttu-id="919be-124">这会成功：-ValueSet @ {MaxEnvelopeSizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="919be-124">This succeeds:  -ValueSet @{MaxEnvelopeSizekb ="200"}</span></span>

### <span data-ttu-id="919be-125">示例3：禁用远程计算机上的侦听器</span><span class="sxs-lookup"><span data-stu-id="919be-125">Example 3: Disable a listener on a remote computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

<span data-ttu-id="919be-126">此命令可禁用远程计算机 SERVER02 上的 https 侦听器。</span><span class="sxs-lookup"><span data-stu-id="919be-126">This command disables the https listener on the remote computer SERVER02.</span></span>

<span data-ttu-id="919be-127">重要信息：在与指定的属性进行匹配时，ValueSet 参数区分大小写。</span><span class="sxs-lookup"><span data-stu-id="919be-127">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="919be-128">例如，使用上面的命令时，</span><span class="sxs-lookup"><span data-stu-id="919be-128">For example, using the above command.</span></span>

<span data-ttu-id="919be-129">这会失败：-ValueSet @ {enabled = "False"}</span><span class="sxs-lookup"><span data-stu-id="919be-129">This fails:     -ValueSet @{enabled="False"}</span></span>

<span data-ttu-id="919be-130">这会成功：-ValueSet @ {Enabled = "False"}</span><span class="sxs-lookup"><span data-stu-id="919be-130">This succeeds:  -ValueSet @{Enabled="False"}</span></span>

## <span data-ttu-id="919be-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="919be-131">PARAMETERS</span></span>

### <span data-ttu-id="919be-132">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="919be-132">-ApplicationName</span></span>

<span data-ttu-id="919be-133">指定连接中的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="919be-133">Specifies the application name in the connection.</span></span>
<span data-ttu-id="919be-134">ApplicationName 参数的默认值为“WSMAN”。</span><span class="sxs-lookup"><span data-stu-id="919be-134">The default value of the ApplicationName parameter is "WSMAN".</span></span>
<span data-ttu-id="919be-135">远程终结点的完整标识符采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="919be-135">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="919be-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="919be-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="919be-137">例如：</span><span class="sxs-lookup"><span data-stu-id="919be-137">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="919be-138">托管该会话的 Internet Information Services (IIS) 将带有此终结点的请求转发到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="919be-138">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="919be-139">默认设置“WSMAN”适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="919be-139">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="919be-140">当有许多计算机建立了与运行 Windows PowerShell 的一台计算机的远程连接时，需要使用此参数。</span><span class="sxs-lookup"><span data-stu-id="919be-140">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="919be-141">在此情况下，IIS 将托管 Web Services for Management (WS-Management) 以提高效率。</span><span class="sxs-lookup"><span data-stu-id="919be-141">In this case, IIS hosts Web Services for Management (WS-Management ) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-142">-Authentication</span><span class="sxs-lookup"><span data-stu-id="919be-142">-Authentication</span></span>

<span data-ttu-id="919be-143">指定服务器上要使用的身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="919be-143">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="919be-144">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="919be-144">Possible values are:</span></span>

- <span data-ttu-id="919be-145">Basic：Basic 是一种将用户名和密码以明文形式发送到服务器或代理的方案。</span><span class="sxs-lookup"><span data-stu-id="919be-145">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="919be-146">Default：使用由 WS-Management 协议实现的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="919be-146">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="919be-147">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="919be-147">This is the default.</span></span>
- <span data-ttu-id="919be-148">Digest：Digest 是一种质询响应方案，该方案将服务器指定的数据字符串用于质询。</span><span class="sxs-lookup"><span data-stu-id="919be-148">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="919be-149">Kerberos：客户端计算机和服务器通过使用 Kerberos 证书相互进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="919be-149">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="919be-150">Negotiate：Negotiate 是一种质询响应方案，该方案与服务器或代理协商以确定要用于身份验证的方案。</span><span class="sxs-lookup"><span data-stu-id="919be-150">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="919be-151">例如，此参数值允许协商以确定是使用 Kerberos 协议还是 NTLM。</span><span class="sxs-lookup"><span data-stu-id="919be-151">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="919be-152">CredSSP：使用凭据安全支持提供程序 (CredSSP) 身份验证，可允许用户委派凭据。</span><span class="sxs-lookup"><span data-stu-id="919be-152">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="919be-153">此选项专门用于这样的命令：在一台远程计算机上运行，但从其他远程计算机收集数据或在其他远程计算机上运行其他命令。</span><span class="sxs-lookup"><span data-stu-id="919be-153">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="919be-154">注意：CredSSP 将用户的凭据从本地计算机委派给远程计算机。</span><span class="sxs-lookup"><span data-stu-id="919be-154">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="919be-155">此做法增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="919be-155">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="919be-156">如果远程计算机的安全受到威胁，则在向该计算机传递凭据时，可使用这些凭据来控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="919be-156">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-157">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="919be-157">-CertificateThumbprint</span></span>

<span data-ttu-id="919be-158">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="919be-158">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="919be-159">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="919be-159">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="919be-160">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="919be-160">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="919be-161">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="919be-161">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="919be-162">若要获取证书指纹，请使用 PowerShell Cert：驱动器中的 Get-Item 或 Get-ChildItem 命令。</span><span class="sxs-lookup"><span data-stu-id="919be-162">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="919be-163">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="919be-163">-ComputerName</span></span>

<span data-ttu-id="919be-164">指定要对其运行管理操作的计算机。</span><span class="sxs-lookup"><span data-stu-id="919be-164">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="919be-165">该值可以是完全限定的域名、NetBIOS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="919be-165">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="919be-166">使用本地计算机名称、localhost 或点 (.) 指定本地计算机。</span><span class="sxs-lookup"><span data-stu-id="919be-166">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="919be-167">默认值为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="919be-167">The local computer is the default.</span></span>
<span data-ttu-id="919be-168">当远程计算机与用户位于不同的域时，必须使用完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="919be-168">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="919be-169">可以通过管道将此参数的值传递给 cmdle。</span><span class="sxs-lookup"><span data-stu-id="919be-169">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-170">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="919be-170">-ConnectionURI</span></span>

<span data-ttu-id="919be-171">指定连接终结点。</span><span class="sxs-lookup"><span data-stu-id="919be-171">Specifies the connection endpoint.</span></span>
<span data-ttu-id="919be-172">此字符串的格式为：</span><span class="sxs-lookup"><span data-stu-id="919be-172">The format of this string is:</span></span>

<span data-ttu-id="919be-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="919be-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="919be-174">以下字符串是此参数的格式正确的值：</span><span class="sxs-lookup"><span data-stu-id="919be-174">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="919be-175">该 URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="919be-175">The URI must be fully qualified .</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="919be-176">-Credential</span></span>

<span data-ttu-id="919be-177">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="919be-177">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="919be-178">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="919be-178">The default is the current user.</span></span>
<span data-ttu-id="919be-179">键入用户名，如 "User01"、"Domain01\User01" 或 " User@Domain.com "。</span><span class="sxs-lookup"><span data-stu-id="919be-179">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span>
<span data-ttu-id="919be-180">或者，输入 PSCredential 对象，例如由 Get-Credential cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="919be-180">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="919be-181">键入用户名时，将会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="919be-181">When you type a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="919be-182">-Dialect</span><span class="sxs-lookup"><span data-stu-id="919be-182">-Dialect</span></span>

<span data-ttu-id="919be-183">指定要在筛选器谓词中使用的方言。</span><span class="sxs-lookup"><span data-stu-id="919be-183">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="919be-184">这可以是远程服务支持的任何方言。</span><span class="sxs-lookup"><span data-stu-id="919be-184">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="919be-185">以下别名可用于方言 URI：</span><span class="sxs-lookup"><span data-stu-id="919be-185">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="919be-186">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="919be-186">WQL: `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="919be-187">选取 `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="919be-187">Selector: `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="919be-188">关联 `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="919be-188">Association: `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-189">-FilePath</span><span class="sxs-lookup"><span data-stu-id="919be-189">-FilePath</span></span>

<span data-ttu-id="919be-190">指定用于更新管理资源的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="919be-190">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="919be-191">通过使用 ResourceURI 参数和 SelectorSet 参数来指定管理资源。</span><span class="sxs-lookup"><span data-stu-id="919be-191">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter .</span></span>
<span data-ttu-id="919be-192">例如，以下命令使用 FilePath 参数：</span><span class="sxs-lookup"><span data-stu-id="919be-192">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

<span data-ttu-id="919be-193">此命令通过使用来自文件的输入对后台处理程序服务调用 StopService 方法。</span><span class="sxs-lookup"><span data-stu-id="919be-193">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="919be-194">文件 Input.xml 包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="919be-194">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="919be-195">-Fragment</span><span class="sxs-lookup"><span data-stu-id="919be-195">-Fragment</span></span>

<span data-ttu-id="919be-196">指定实例内要针对指定操作更新或检索的部分。</span><span class="sxs-lookup"><span data-stu-id="919be-196">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="919be-197">例如，若要获取后台处理程序服务的状态，请指定“-Fragment Status”。</span><span class="sxs-lookup"><span data-stu-id="919be-197">For example, to get the status of a spooler service, specify "-Fragment Status".</span></span>

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

### <span data-ttu-id="919be-198">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="919be-198">-OptionSet</span></span>

<span data-ttu-id="919be-199">将一组开关传递到某个服务以修改或优化请求的性质。</span><span class="sxs-lookup"><span data-stu-id="919be-199">Passes a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="919be-200">这些开关与命令行 shell 中使用的开关相似，因为它们也是特定于服务的。</span><span class="sxs-lookup"><span data-stu-id="919be-200">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="919be-201">可以指定任何数量的选项。</span><span class="sxs-lookup"><span data-stu-id="919be-201">Any number of options can be specified.</span></span>

<span data-ttu-id="919be-202">以下示例演示为 a、b 和 c 参数传递值 1、2 和 3 的语法：</span><span class="sxs-lookup"><span data-stu-id="919be-202">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

<span data-ttu-id="919be-203">-OptionSet @{a=1;b=2;c=3}</span><span class="sxs-lookup"><span data-stu-id="919be-203">-OptionSet @{a=1;b=2;c=3}</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-204">-Port</span><span class="sxs-lookup"><span data-stu-id="919be-204">-Port</span></span>

<span data-ttu-id="919be-205">指定要在客户端连接到 WinRM 服务时使用的端口。</span><span class="sxs-lookup"><span data-stu-id="919be-205">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="919be-206">当传输为 HTTP 时，默认端口为 80。</span><span class="sxs-lookup"><span data-stu-id="919be-206">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="919be-207">当传输为 HTTPS 时，默认端口为 443。</span><span class="sxs-lookup"><span data-stu-id="919be-207">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="919be-208">当你使用 HTTPS 作为传输协议时，ComputerName 参数的值必须与服务器的证书公用名 (CN) 匹配。</span><span class="sxs-lookup"><span data-stu-id="919be-208">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="919be-209">但是，如果将 SkipCNCheck 参数指定为 SessionOption 参数的一部分，则服务器的证书公用名无需与服务器的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="919be-209">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="919be-210">SkipCNCheck 参数应该仅用于受信任的计算机。</span><span class="sxs-lookup"><span data-stu-id="919be-210">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-211">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="919be-211">-ResourceURI</span></span>

<span data-ttu-id="919be-212">包含资源类或实例的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="919be-212">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="919be-213">URI 用于标识计算机上特定类型的资源，例如磁盘或进程。</span><span class="sxs-lookup"><span data-stu-id="919be-213">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="919be-214">URI 由前缀和指向资源的路径组成。</span><span class="sxs-lookup"><span data-stu-id="919be-214">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="919be-215">例如：</span><span class="sxs-lookup"><span data-stu-id="919be-215">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-216">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="919be-216">-SelectorSet</span></span>

<span data-ttu-id="919be-217">指定一组用于选择特定管理资源实例的值对。</span><span class="sxs-lookup"><span data-stu-id="919be-217">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="919be-218">当相应资源存在多个实例时，将使用 SelectorSet 参数。</span><span class="sxs-lookup"><span data-stu-id="919be-218">The SelectorSet parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="919be-219">SelectorSet 参数的值必须为哈希表。</span><span class="sxs-lookup"><span data-stu-id="919be-219">The value of the SelectorSet parameter must be a hash table.</span></span>
<span data-ttu-id="919be-220">以下示例显示如何为此参数输入值：</span><span class="sxs-lookup"><span data-stu-id="919be-220">The following example shows how to enter a value for this parameter:</span></span>

<span data-ttu-id="919be-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span><span class="sxs-lookup"><span data-stu-id="919be-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="919be-222">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="919be-222">-SessionOption</span></span>

<span data-ttu-id="919be-223">为 WS-Management 会话定义一组扩展选项。</span><span class="sxs-lookup"><span data-stu-id="919be-223">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="919be-224">输入你使用 New-WSManSessionOption cmdlet 创建的 SessionOption 对象。</span><span class="sxs-lookup"><span data-stu-id="919be-224">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="919be-225">有关可用选项的详细信息，请参阅 New-WSManSessionOption。</span><span class="sxs-lookup"><span data-stu-id="919be-225">For more information about the options that are available, see New-WSManSessionOption.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-226">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="919be-226">-UseSSL</span></span>

<span data-ttu-id="919be-227">指定应使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="919be-227">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="919be-228">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="919be-228">By default, SSL is not used.</span></span>

<span data-ttu-id="919be-229">WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="919be-229">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="919be-230">利用 UseSSL 参数，你可以指定 HTTPS（而非 HTTP）的额外保护措施。</span><span class="sxs-lookup"><span data-stu-id="919be-230">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="919be-231">如果 SSL 在用于连接的端口上不可用，并且指定了此参数，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="919be-231">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="919be-232">-ValueSet</span><span class="sxs-lookup"><span data-stu-id="919be-232">-ValueSet</span></span>

<span data-ttu-id="919be-233">指定可帮助修改管理资源的哈希表。</span><span class="sxs-lookup"><span data-stu-id="919be-233">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="919be-234">通过使用 ResourceURI 参数和 SelectorSet 参数来指定管理资源。</span><span class="sxs-lookup"><span data-stu-id="919be-234">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="919be-235">ValueSet 参数的值必须为哈希表。</span><span class="sxs-lookup"><span data-stu-id="919be-235">The value of the ValueSet parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="919be-236">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="919be-236">CommonParameters</span></span>

<span data-ttu-id="919be-237">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="919be-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="919be-238">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="919be-238">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="919be-239">输入</span><span class="sxs-lookup"><span data-stu-id="919be-239">INPUTS</span></span>

### <span data-ttu-id="919be-240">无</span><span class="sxs-lookup"><span data-stu-id="919be-240">None</span></span>

<span data-ttu-id="919be-241">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="919be-241">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="919be-242">输出</span><span class="sxs-lookup"><span data-stu-id="919be-242">OUTPUTS</span></span>

### <span data-ttu-id="919be-243">无</span><span class="sxs-lookup"><span data-stu-id="919be-243">None</span></span>

<span data-ttu-id="919be-244">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="919be-244">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="919be-245">注释</span><span class="sxs-lookup"><span data-stu-id="919be-245">NOTES</span></span>

## <span data-ttu-id="919be-246">相关链接</span><span class="sxs-lookup"><span data-stu-id="919be-246">RELATED LINKS</span></span>

[<span data-ttu-id="919be-247">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="919be-247">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="919be-248">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="919be-248">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="919be-249">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="919be-249">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="919be-250">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="919be-250">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="919be-251">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="919be-251">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="919be-252">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="919be-252">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="919be-253">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="919be-253">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="919be-254">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="919be-254">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="919be-255">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="919be-255">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="919be-256">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="919be-256">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="919be-257">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="919be-257">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="919be-258">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="919be-258">Test-WSMan</span></span>](Test-WSMan.md)
