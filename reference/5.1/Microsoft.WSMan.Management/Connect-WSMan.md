---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: aec1bff3fabc0556f533392e9f535e4cda78a97f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200638"
---
# <span data-ttu-id="93424-103">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="93424-103">Connect-WSMan</span></span>

## <span data-ttu-id="93424-104">摘要</span><span class="sxs-lookup"><span data-stu-id="93424-104">SYNOPSIS</span></span>
<span data-ttu-id="93424-105">连接到远程计算机上的 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="93424-105">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="93424-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93424-106">SYNTAX</span></span>

### <span data-ttu-id="93424-107">ComputerName（默认值）</span><span class="sxs-lookup"><span data-stu-id="93424-107">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="93424-108">URI</span><span class="sxs-lookup"><span data-stu-id="93424-108">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="93424-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="93424-109">DESCRIPTION</span></span>
<span data-ttu-id="93424-110">**Connect-WSMan** cmdlet 连接到远程计算机上的 WinRM 服务，并建立与远程计算机的持久连接。</span><span class="sxs-lookup"><span data-stu-id="93424-110">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="93424-111">可以在 WSMan 提供程序的上下文中使用此 cmdlet 连接到远程计算机上的 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="93424-111">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="93424-112">但是，你还可以在更改为 WSMan 提供程序之前，使用此 cmdlet 连接到远程计算机上的 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="93424-112">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="93424-113">远程计算机将出现在 WSMan 提供程序的根目录中。</span><span class="sxs-lookup"><span data-stu-id="93424-113">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="93424-114">当客户端和服务器计算机位于不同的域或工作组中时，需要使用显式凭据。</span><span class="sxs-lookup"><span data-stu-id="93424-114">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="93424-115">有关如何断开与远程计算机上的 WinRM 服务的连接的信息，请参阅 Disconnect-WSMan cmdlet。</span><span class="sxs-lookup"><span data-stu-id="93424-115">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="93424-116">示例</span><span class="sxs-lookup"><span data-stu-id="93424-116">EXAMPLES</span></span>

### <span data-ttu-id="93424-117">示例1：连接到远程计算机</span><span class="sxs-lookup"><span data-stu-id="93424-117">Example 1: Connect to a remote computer</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="93424-118">此命令创建一个与 server01 远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="93424-118">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="93424-119">通常在 WSMan 提供程序的上下文中使用 **connect-wsman** cmdlet 连接到远程计算机（在本例中为 server01 计算机）。</span><span class="sxs-lookup"><span data-stu-id="93424-119">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="93424-120">但是，你可以在更改为 WSMan 提供程序之前，使用该 cmdlet 建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="93424-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="93424-121">这些连接将出现在 **ComputerName** 列表中。</span><span class="sxs-lookup"><span data-stu-id="93424-121">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="93424-122">示例2：使用管理员凭据连接到远程计算机</span><span class="sxs-lookup"><span data-stu-id="93424-122">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="93424-123">此命令使用管理员帐户凭据创建一个与远程系统 server01 的连接。</span><span class="sxs-lookup"><span data-stu-id="93424-123">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="93424-124">第一个命令使用 Get-Credential cmdlet 来获取管理员凭据，然后将齐存储在 $cred 变量中。</span><span class="sxs-lookup"><span data-stu-id="93424-124">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="93424-125">**Get-Credential** 会提示你输入用户名和密码，具体取决于系统注册表设置。</span><span class="sxs-lookup"><span data-stu-id="93424-125">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="93424-126">第二个命令使用 *Credential* 参数将 $cred 中存储的凭据传递到 **连接-WSMan** 。</span><span class="sxs-lookup"><span data-stu-id="93424-126">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan** .</span></span>
<span data-ttu-id="93424-127">**接** 下来，使用管理员凭据连接到远程系统 server01。</span><span class="sxs-lookup"><span data-stu-id="93424-127">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="93424-128">示例3：通过指定端口连接到远程计算机</span><span class="sxs-lookup"><span data-stu-id="93424-128">Example 3: Connect to a remote computer over a specified port</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="93424-129">此命令通过端口 80 创建一个与 server01 远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="93424-129">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="93424-130">示例4：使用连接选项连接到远程计算机</span><span class="sxs-lookup"><span data-stu-id="93424-130">Example 4: Connect to a remote computer by using connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="93424-131">此示例使用在 **new-wsmansessionoption** 命令中定义的连接选项创建与远程 server01 计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="93424-131">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="93424-132">第一个命令使用 **new-wsmansessionoption** 将一组连接设置选项存储在 $a 变量中。</span><span class="sxs-lookup"><span data-stu-id="93424-132">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="93424-133">在此情况下，这些会话选项将连接超时设置为 30 秒（30,000 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="93424-133">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="93424-134">第二个命令使用 *SessionOption* 参数将存储在 $a 变量中的凭据传递到 **连接-WSMan** 。</span><span class="sxs-lookup"><span data-stu-id="93424-134">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan** .</span></span>
<span data-ttu-id="93424-135">然后，使用指定的会话选项 **连接-WSMan** 连接到远程 server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="93424-135">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="93424-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93424-136">PARAMETERS</span></span>

### <span data-ttu-id="93424-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="93424-137">-ApplicationName</span></span>
<span data-ttu-id="93424-138">指定连接中的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="93424-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="93424-139">*ApplicationName* 参数的默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="93424-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="93424-140">远程终结点的完整标识符采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="93424-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="93424-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="93424-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="93424-142">例如：`http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="93424-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="93424-143">托管该会话的 Internet Information Services (IIS) 将带有此终结点的请求转发到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="93424-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="93424-144">默认设置 WSMAN 适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="93424-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="93424-145">如果许多计算机建立了与运行 Windows PowerShell 的一台计算机的远程连接，则需要使用此参数。</span><span class="sxs-lookup"><span data-stu-id="93424-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="93424-146">在此情况下，IIS 将托管 Web Services for Management (WS-Management) 以提高效率。</span><span class="sxs-lookup"><span data-stu-id="93424-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="93424-147">-Authentication</span><span class="sxs-lookup"><span data-stu-id="93424-147">-Authentication</span></span>
<span data-ttu-id="93424-148">指定服务器上要使用的身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="93424-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="93424-149">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="93424-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="93424-150">基本。</span><span class="sxs-lookup"><span data-stu-id="93424-150">Basic.</span></span>
<span data-ttu-id="93424-151">Basic 是一种将用户名和密码以明文形式发送到服务器或代理的方案。</span><span class="sxs-lookup"><span data-stu-id="93424-151">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="93424-152">默认。</span><span class="sxs-lookup"><span data-stu-id="93424-152">Default.</span></span>
<span data-ttu-id="93424-153">使用由 WS-Management 协议实现的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="93424-153">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="93424-154">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="93424-154">This is the default.</span></span>
- <span data-ttu-id="93424-155">摘要。</span><span class="sxs-lookup"><span data-stu-id="93424-155">Digest.</span></span>
<span data-ttu-id="93424-156">Digest 是一种质询响应方案，该方案将服务器指定的数据字符串用于质询。</span><span class="sxs-lookup"><span data-stu-id="93424-156">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="93424-157">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="93424-157">Kerberos.</span></span>
<span data-ttu-id="93424-158">客户端计算机和服务器通过使用 Kerberos 证书相互进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="93424-158">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="93424-159">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="93424-159">Negotiate.</span></span>
<span data-ttu-id="93424-160">Negotiate 是一种质询响应方案，该方案与服务器或代理协商以确定要用于身份验证的方案。</span><span class="sxs-lookup"><span data-stu-id="93424-160">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="93424-161">例如，此参数值允许协商以确定是使用 Kerberos 协议还是 NTLM。</span><span class="sxs-lookup"><span data-stu-id="93424-161">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="93424-162">CredSSP。</span><span class="sxs-lookup"><span data-stu-id="93424-162">CredSSP.</span></span>
<span data-ttu-id="93424-163">使用凭据安全支持提供程序 (CredSSP) 身份验证，可允许用户委派凭据。</span><span class="sxs-lookup"><span data-stu-id="93424-163">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="93424-164">此选项专门用于这样的命令：在一台远程计算机上运行，但从其他远程计算机收集数据或在其他远程计算机上运行其他命令。</span><span class="sxs-lookup"><span data-stu-id="93424-164">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="93424-165">注意：CredSSP 将用户凭据从本地计算机委派给远程计算机。</span><span class="sxs-lookup"><span data-stu-id="93424-165">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="93424-166">此做法增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="93424-166">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="93424-167">如果远程计算机的安全受到威胁，则在向该计算机传递凭据时，可使用这些凭据来控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="93424-167">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="93424-168">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="93424-168">-CertificateThumbprint</span></span>
<span data-ttu-id="93424-169">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="93424-169">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="93424-170">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="93424-170">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="93424-171">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="93424-171">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="93424-172">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="93424-172">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="93424-173">若要获取证书指纹，请在 Windows PowerShell Cert: 驱动器中使用 Get-Item 或 Get-ChildItem 命令。</span><span class="sxs-lookup"><span data-stu-id="93424-173">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="93424-174">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="93424-174">-ComputerName</span></span>
<span data-ttu-id="93424-175">指定要对其运行管理操作的计算机。</span><span class="sxs-lookup"><span data-stu-id="93424-175">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="93424-176">该值可以是完全限定的域名、NetBIOS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="93424-176">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="93424-177">使用本地计算机名称、localhost 或点 (.) 指定本地计算机。</span><span class="sxs-lookup"><span data-stu-id="93424-177">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="93424-178">默认值为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="93424-178">The local computer is the default.</span></span>
<span data-ttu-id="93424-179">当远程计算机与用户位于不同的域时，必须使用完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="93424-179">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="93424-180">可以通过管道将此参数的值传递给 cmdle。</span><span class="sxs-lookup"><span data-stu-id="93424-180">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93424-181">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="93424-181">-ConnectionURI</span></span>
<span data-ttu-id="93424-182">指定连接终结点。</span><span class="sxs-lookup"><span data-stu-id="93424-182">Specifies the connection endpoint.</span></span>
<span data-ttu-id="93424-183">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="93424-183">The format of this string is as follows:</span></span>

<span data-ttu-id="93424-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="93424-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="93424-185">以下字符串是此参数的格式正确的值：</span><span class="sxs-lookup"><span data-stu-id="93424-185">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="93424-186">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="93424-186">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="93424-187">-Credential</span><span class="sxs-lookup"><span data-stu-id="93424-187">-Credential</span></span>
<span data-ttu-id="93424-188">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="93424-188">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="93424-189">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="93424-189">The default is the current user.</span></span>
<span data-ttu-id="93424-190">键入用户名，如 User01、Domain01\User01 或 User@Domain.com 。</span><span class="sxs-lookup"><span data-stu-id="93424-190">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="93424-191">或者输入一个 PSCredential 对象，例如 Get-Credential cmdlet 返回的一个 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="93424-191">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="93424-192">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="93424-192">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="93424-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="93424-193">-OptionSet</span></span>
<span data-ttu-id="93424-194">将一组开关指定到某个服务以修改或优化请求的性质。</span><span class="sxs-lookup"><span data-stu-id="93424-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="93424-195">这些开关类似于命令行 shell 中使用的开关，因为它们也特定于服务。</span><span class="sxs-lookup"><span data-stu-id="93424-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="93424-196">可以指定任何数量的选项。</span><span class="sxs-lookup"><span data-stu-id="93424-196">Any number of options can be specified.</span></span>

<span data-ttu-id="93424-197">以下示例演示为 a、b 和 c 参数传递值 1、2 和 3 的语法：</span><span class="sxs-lookup"><span data-stu-id="93424-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="93424-198">-Port</span><span class="sxs-lookup"><span data-stu-id="93424-198">-Port</span></span>
<span data-ttu-id="93424-199">指定要在客户端连接到 WinRM 服务时使用的端口。</span><span class="sxs-lookup"><span data-stu-id="93424-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="93424-200">当传输为 HTTP 时，默认端口为 80。</span><span class="sxs-lookup"><span data-stu-id="93424-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="93424-201">当传输为 HTTPS 时，默认端口为 443。</span><span class="sxs-lookup"><span data-stu-id="93424-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="93424-202">使用 HTTPS 作为传输协议时， *ComputerName* 参数的值必须与服务器的证书公用名 (CN) 相匹配。</span><span class="sxs-lookup"><span data-stu-id="93424-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="93424-203">但是，如果将 SkipCNCheck  参数指定为 SessionOption  参数的一部分，则服务器的证书公用名无需与服务器的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="93424-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="93424-204">SkipCNCheck  参数应仅用于受信任的计算机。</span><span class="sxs-lookup"><span data-stu-id="93424-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="93424-205">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="93424-205">-SessionOption</span></span>
<span data-ttu-id="93424-206">为 WS-Management 会话指定扩展选项。</span><span class="sxs-lookup"><span data-stu-id="93424-206">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="93424-207">输入使用 New-WSManSessionOption cmdlet 创建的 **SessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="93424-207">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="93424-208">有关可用选项的详细信息，请键入 `Get-Help New-WSManSessionOption`。</span><span class="sxs-lookup"><span data-stu-id="93424-208">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="93424-209">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="93424-209">-UseSSL</span></span>
<span data-ttu-id="93424-210">指定使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="93424-210">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="93424-211">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="93424-211">By default, SSL is not used.</span></span>

<span data-ttu-id="93424-212">WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="93424-212">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="93424-213">*UseSSL* 参数允许你指定 HTTPS 的额外保护，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="93424-213">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="93424-214">如果 SSL 在用于连接的端口上不可用，并且指定了此参数，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="93424-214">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93424-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="93424-215">CommonParameters</span></span>
<span data-ttu-id="93424-216">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="93424-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93424-217">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="93424-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="93424-218">输入</span><span class="sxs-lookup"><span data-stu-id="93424-218">INPUTS</span></span>

### <span data-ttu-id="93424-219">无</span><span class="sxs-lookup"><span data-stu-id="93424-219">None</span></span>
<span data-ttu-id="93424-220">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="93424-220">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="93424-221">输出</span><span class="sxs-lookup"><span data-stu-id="93424-221">OUTPUTS</span></span>

### <span data-ttu-id="93424-222">无</span><span class="sxs-lookup"><span data-stu-id="93424-222">None</span></span>
<span data-ttu-id="93424-223">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="93424-223">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="93424-224">注释</span><span class="sxs-lookup"><span data-stu-id="93424-224">NOTES</span></span>

* <span data-ttu-id="93424-225">你可以在远程计算机上运行管理命令或查询管理数据，而无需创建 WS-Management 会话。</span><span class="sxs-lookup"><span data-stu-id="93424-225">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="93424-226">为此，可以使用 Invoke-WSManAction 和 Get-wsmaninstance 的 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="93424-226">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="93424-227">当你使用 *ComputerName* 参数时，Windows PowerShell 将创建一个用于单个命令的临时连接。</span><span class="sxs-lookup"><span data-stu-id="93424-227">When you use the *ComputerName* parameter, Windows PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="93424-228">在命令运行完后，该连接即会关闭。</span><span class="sxs-lookup"><span data-stu-id="93424-228">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="93424-229">相关链接</span><span class="sxs-lookup"><span data-stu-id="93424-229">RELATED LINKS</span></span>

[<span data-ttu-id="93424-230">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="93424-230">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="93424-231">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="93424-231">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="93424-232">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="93424-232">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="93424-233">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="93424-233">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="93424-234">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="93424-234">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="93424-235">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="93424-235">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="93424-236">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="93424-236">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="93424-237">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="93424-237">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="93424-238">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="93424-238">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="93424-239">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="93424-239">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="93424-240">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="93424-240">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="93424-241">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="93424-241">Test-WSMan</span></span>](Test-WSMan.md)
