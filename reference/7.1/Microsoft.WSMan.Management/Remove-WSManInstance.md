---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 6bd166942551671c581c04cb611c222378caeba1
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199007"
---
# <span data-ttu-id="e6c51-103">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e6c51-103">Remove-WSManInstance</span></span>

## <span data-ttu-id="e6c51-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e6c51-104">SYNOPSIS</span></span>
<span data-ttu-id="e6c51-105">删除管理资源实例。</span><span class="sxs-lookup"><span data-stu-id="e6c51-105">Deletes a management resource instance.</span></span>

## <span data-ttu-id="e6c51-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6c51-106">SYNTAX</span></span>

### <span data-ttu-id="e6c51-107">ComputerName（默认值）</span><span class="sxs-lookup"><span data-stu-id="e6c51-107">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="e6c51-108">URI</span><span class="sxs-lookup"><span data-stu-id="e6c51-108">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="e6c51-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6c51-109">DESCRIPTION</span></span>

<span data-ttu-id="e6c51-110"> 和 SelectorSet  参数中指定的管理资源的实例。</span><span class="sxs-lookup"><span data-stu-id="e6c51-110">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="e6c51-111">此 cmdlet 使用 WinRM 连接/传输层来删除管理资源实例。</span><span class="sxs-lookup"><span data-stu-id="e6c51-111">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="e6c51-112">示例</span><span class="sxs-lookup"><span data-stu-id="e6c51-112">EXAMPLES</span></span>

### <span data-ttu-id="e6c51-113">示例 1：删除侦听器</span><span class="sxs-lookup"><span data-stu-id="e6c51-113">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="e6c51-114">此命令删除计算机上的 WS-Management HTTP 侦听器。</span><span class="sxs-lookup"><span data-stu-id="e6c51-114">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="e6c51-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6c51-115">PARAMETERS</span></span>

### <span data-ttu-id="e6c51-116">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="e6c51-116">-ApplicationName</span></span>

<span data-ttu-id="e6c51-117">指定连接中的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="e6c51-117">Specifies the application name in the connection.</span></span>
<span data-ttu-id="e6c51-118">*ApplicationName* 参数的默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="e6c51-118">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="e6c51-119">远程终结点的完整标识符采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="e6c51-119">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="e6c51-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="e6c51-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="e6c51-121">例如：`http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="e6c51-121">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="e6c51-122">托管该会话的 Internet Information Services (IIS) 将带有此终结点的请求转发到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6c51-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="e6c51-123">默认设置 WSMAN 适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="e6c51-123">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="e6c51-124">如果许多计算机建立了与运行 PowerShell 的一台计算机的远程连接，则可以使用此参数。</span><span class="sxs-lookup"><span data-stu-id="e6c51-124">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="e6c51-125">在此情况下，IIS 将托管 Web Services for Management (WS-Management) 以提高效率。</span><span class="sxs-lookup"><span data-stu-id="e6c51-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c51-126">-Authentication</span><span class="sxs-lookup"><span data-stu-id="e6c51-126">-Authentication</span></span>

<span data-ttu-id="e6c51-127">指定服务器上要使用的身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="e6c51-127">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="e6c51-128">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="e6c51-128">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e6c51-129">基本。</span><span class="sxs-lookup"><span data-stu-id="e6c51-129">Basic.</span></span>
<span data-ttu-id="e6c51-130">Basic 是一种将用户名和密码以明文形式发送到服务器或代理的方案。</span><span class="sxs-lookup"><span data-stu-id="e6c51-130">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="e6c51-131">默认。</span><span class="sxs-lookup"><span data-stu-id="e6c51-131">Default.</span></span>
<span data-ttu-id="e6c51-132">使用由 WS-Management 协议实现的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="e6c51-132">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="e6c51-133">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="e6c51-133">This is the default.</span></span>
- <span data-ttu-id="e6c51-134">摘要。</span><span class="sxs-lookup"><span data-stu-id="e6c51-134">Digest.</span></span>
<span data-ttu-id="e6c51-135">Digest 是一种质询响应方案，该方案将服务器指定的数据字符串用于质询。</span><span class="sxs-lookup"><span data-stu-id="e6c51-135">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="e6c51-136">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="e6c51-136">Kerberos.</span></span>
<span data-ttu-id="e6c51-137">客户端计算机和服务器通过使用 Kerberos 证书相互进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e6c51-137">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="e6c51-138">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="e6c51-138">Negotiate.</span></span>
<span data-ttu-id="e6c51-139">Negotiate 是一种质询响应方案，该方案与服务器或代理协商以确定要用于身份验证的方案。</span><span class="sxs-lookup"><span data-stu-id="e6c51-139">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="e6c51-140">例如，此参数值允许协商以确定是使用 Kerberos 协议还是 NTLM。</span><span class="sxs-lookup"><span data-stu-id="e6c51-140">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="e6c51-141">CredSSP。</span><span class="sxs-lookup"><span data-stu-id="e6c51-141">CredSSP.</span></span>
<span data-ttu-id="e6c51-142">使用凭据安全支持提供程序 (CredSSP) 身份验证，可允许用户委派凭据。</span><span class="sxs-lookup"><span data-stu-id="e6c51-142">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="e6c51-143">此选项专门用于这样的命令：在一台远程计算机上运行，但从其他远程计算机收集数据或在其他远程计算机上运行其他命令。</span><span class="sxs-lookup"><span data-stu-id="e6c51-143">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="e6c51-144">注意：CredSSP 将用户凭据从本地计算机委派给远程计算机。</span><span class="sxs-lookup"><span data-stu-id="e6c51-144">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="e6c51-145">此做法增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="e6c51-145">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="e6c51-146">如果远程计算机的安全受到威胁，则在向该计算机传递凭据时，可使用这些凭据来控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="e6c51-146">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c51-147">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="e6c51-147">-CertificateThumbprint</span></span>

<span data-ttu-id="e6c51-148">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="e6c51-148">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="e6c51-149">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="e6c51-149">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="e6c51-150">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="e6c51-150">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="e6c51-151">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="e6c51-151">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="e6c51-152">若要获取证书指纹，请使用 PowerShell Cert：驱动器中的 Get-Item 或 Get-ChildItem 命令。</span><span class="sxs-lookup"><span data-stu-id="e6c51-152">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="e6c51-153">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e6c51-153">-ComputerName</span></span>

<span data-ttu-id="e6c51-154">指定要对其运行管理操作的计算机。</span><span class="sxs-lookup"><span data-stu-id="e6c51-154">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="e6c51-155">该值可以是完全限定的域名、NetBIOS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e6c51-155">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="e6c51-156">使用本地计算机名称、localhost 或点 (.) 指定本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e6c51-156">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="e6c51-157">默认值为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e6c51-157">The local computer is the default.</span></span>
<span data-ttu-id="e6c51-158">当远程计算机与用户位于不同的域时，必须使用完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="e6c51-158">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="e6c51-159">可以通过管道将此参数的值传递给 cmdle。</span><span class="sxs-lookup"><span data-stu-id="e6c51-159">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c51-160">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="e6c51-160">-ConnectionURI</span></span>

<span data-ttu-id="e6c51-161">指定连接终结点。</span><span class="sxs-lookup"><span data-stu-id="e6c51-161">Specifies the connection endpoint.</span></span>
<span data-ttu-id="e6c51-162">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="e6c51-162">The format of this string is as follows:</span></span>

<span data-ttu-id="e6c51-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="e6c51-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="e6c51-164">以下字符串是此参数的格式正确的值：</span><span class="sxs-lookup"><span data-stu-id="e6c51-164">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="e6c51-165">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="e6c51-165">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="e6c51-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="e6c51-166">-Credential</span></span>

<span data-ttu-id="e6c51-167">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e6c51-167">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="e6c51-168">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="e6c51-168">The default is the current user.</span></span>
<span data-ttu-id="e6c51-169">键入用户名，如 User01、Domain01\User01 或 User@Domain.com 。</span><span class="sxs-lookup"><span data-stu-id="e6c51-169">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="e6c51-170">或者输入一个 PSCredential 对象，例如 Get-Credential cmdlet 返回的一个 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="e6c51-170">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="e6c51-171">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="e6c51-171">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="e6c51-172">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="e6c51-172">-OptionSet</span></span>

<span data-ttu-id="e6c51-173">将一组开关指定到某个服务以修改或优化请求的性质。</span><span class="sxs-lookup"><span data-stu-id="e6c51-173">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="e6c51-174">这些开关类似于命令行 shell 中使用的开关，因为它们也特定于服务。</span><span class="sxs-lookup"><span data-stu-id="e6c51-174">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="e6c51-175">可以指定任何数量的选项。</span><span class="sxs-lookup"><span data-stu-id="e6c51-175">Any number of options can be specified.</span></span>

<span data-ttu-id="e6c51-176">以下示例演示为 a、b 和 c 参数传递值 1、2 和 3 的语法：</span><span class="sxs-lookup"><span data-stu-id="e6c51-176">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

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

### <span data-ttu-id="e6c51-177">-Port</span><span class="sxs-lookup"><span data-stu-id="e6c51-177">-Port</span></span>

<span data-ttu-id="e6c51-178">指定要在客户端连接到 WinRM 服务时使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e6c51-178">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="e6c51-179">当传输为 HTTP 时，默认端口为 80。</span><span class="sxs-lookup"><span data-stu-id="e6c51-179">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="e6c51-180">当传输为 HTTPS 时，默认端口为 443。</span><span class="sxs-lookup"><span data-stu-id="e6c51-180">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="e6c51-181">使用 HTTPS 作为传输协议时， *ComputerName* 参数的值必须与服务器的证书公用名 (CN) 相匹配。</span><span class="sxs-lookup"><span data-stu-id="e6c51-181">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="e6c51-182">但是，如果将 SkipCNCheck  参数指定为 SessionOption  参数的一部分，则服务器的证书公用名无需与服务器的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="e6c51-182">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="e6c51-183">SkipCNCheck  参数应仅用于受信任的计算机。</span><span class="sxs-lookup"><span data-stu-id="e6c51-183">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="e6c51-184">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="e6c51-184">-ResourceURI</span></span>

<span data-ttu-id="e6c51-185">指定资源类或实例的 URI。</span><span class="sxs-lookup"><span data-stu-id="e6c51-185">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="e6c51-186">URI 用于标识计算机上特定类型的资源，例如磁盘或进程。</span><span class="sxs-lookup"><span data-stu-id="e6c51-186">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="e6c51-187">URI 由资源的前缀和路径组成。</span><span class="sxs-lookup"><span data-stu-id="e6c51-187">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="e6c51-188">例如：</span><span class="sxs-lookup"><span data-stu-id="e6c51-188">For example:</span></span>

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

### <span data-ttu-id="e6c51-189">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="e6c51-189">-SelectorSet</span></span>

<span data-ttu-id="e6c51-190">指定一组用于选择特定管理资源实例的值对。</span><span class="sxs-lookup"><span data-stu-id="e6c51-190">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="e6c51-191">当存在多个资源实例时，将使用 *SelectorSet* 参数。</span><span class="sxs-lookup"><span data-stu-id="e6c51-191">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="e6c51-192">SelectorSet  的值必须为哈希表。</span><span class="sxs-lookup"><span data-stu-id="e6c51-192">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="e6c51-193">以下示例显示如何为此参数输入值：</span><span class="sxs-lookup"><span data-stu-id="e6c51-193">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c51-194">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="e6c51-194">-SessionOption</span></span>

<span data-ttu-id="e6c51-195">为 WS-Management 会话指定扩展选项。</span><span class="sxs-lookup"><span data-stu-id="e6c51-195">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="e6c51-196">输入使用 New-WSManSessionOption cmdlet 创建的 **SessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="e6c51-196">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="e6c51-197">有关可用选项的详细信息，请键入 `Get-Help New-WSManSessionOption`。</span><span class="sxs-lookup"><span data-stu-id="e6c51-197">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="e6c51-198">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="e6c51-198">-UseSSL</span></span>

<span data-ttu-id="e6c51-199">指定使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="e6c51-199">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="e6c51-200">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="e6c51-200">By default, SSL is not used.</span></span>

<span data-ttu-id="e6c51-201">WS-Management 加密通过网络传输的所有 PowerShell 内容。</span><span class="sxs-lookup"><span data-stu-id="e6c51-201">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="e6c51-202">*UseSSL* 参数允许你指定 HTTPS 的额外保护，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="e6c51-202">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="e6c51-203">如果 SSL 在用于连接的端口上不可用，并且指定了此参数，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="e6c51-203">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="e6c51-204">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e6c51-204">CommonParameters</span></span>

<span data-ttu-id="e6c51-205">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e6c51-205">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6c51-206">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e6c51-206">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6c51-207">输入</span><span class="sxs-lookup"><span data-stu-id="e6c51-207">INPUTS</span></span>

### <span data-ttu-id="e6c51-208">无</span><span class="sxs-lookup"><span data-stu-id="e6c51-208">None</span></span>

<span data-ttu-id="e6c51-209">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="e6c51-209">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="e6c51-210">输出</span><span class="sxs-lookup"><span data-stu-id="e6c51-210">OUTPUTS</span></span>

### <span data-ttu-id="e6c51-211">无</span><span class="sxs-lookup"><span data-stu-id="e6c51-211">None</span></span>

<span data-ttu-id="e6c51-212">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="e6c51-212">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e6c51-213">注释</span><span class="sxs-lookup"><span data-stu-id="e6c51-213">NOTES</span></span>

* <span data-ttu-id="e6c51-214">Windows Management Instrumentation (WMI) cmdlet 类似于 Remove-WmiObject cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c51-214">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="e6c51-215">**Get-wmiobject** 使用 DCOM 连接/传输层来创建或更新 WMI 实例。</span><span class="sxs-lookup"><span data-stu-id="e6c51-215">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="e6c51-216">相关链接</span><span class="sxs-lookup"><span data-stu-id="e6c51-216">RELATED LINKS</span></span>

[<span data-ttu-id="e6c51-217">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e6c51-217">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="e6c51-218">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e6c51-218">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="e6c51-219">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e6c51-219">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="e6c51-220">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e6c51-220">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="e6c51-221">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e6c51-221">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="e6c51-222">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e6c51-222">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="e6c51-223">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="e6c51-223">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="e6c51-224">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e6c51-224">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="e6c51-225">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="e6c51-225">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="e6c51-226">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e6c51-226">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="e6c51-227">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="e6c51-227">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="e6c51-228">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="e6c51-228">Test-WSMan</span></span>](Test-WSMan.md)

