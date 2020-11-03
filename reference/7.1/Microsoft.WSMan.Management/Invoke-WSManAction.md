---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 112b4a1e0a790c32b6a3ea2011fbc72ec86a0324
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199109"
---
# <span data-ttu-id="28b71-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="28b71-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="28b71-104">摘要</span><span class="sxs-lookup"><span data-stu-id="28b71-104">SYNOPSIS</span></span>
<span data-ttu-id="28b71-105">对由资源 URI 和选择器指定的对象调用操作。</span><span class="sxs-lookup"><span data-stu-id="28b71-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="28b71-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28b71-106">SYNTAX</span></span>

### <span data-ttu-id="28b71-107">URI (默认值) </span><span class="sxs-lookup"><span data-stu-id="28b71-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="28b71-108">计算机名</span><span class="sxs-lookup"><span data-stu-id="28b71-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="28b71-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28b71-109">DESCRIPTION</span></span>
<span data-ttu-id="28b71-110">**Invoke-wsmanaction** 对 RESOURCE_URI 指定的对象运行操作，其中的参数由键值对指定。</span><span class="sxs-lookup"><span data-stu-id="28b71-110">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="28b71-111">此 cmdlet 使用 WSMan 连接/传输层来运行操作。</span><span class="sxs-lookup"><span data-stu-id="28b71-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="28b71-112">示例</span><span class="sxs-lookup"><span data-stu-id="28b71-112">EXAMPLES</span></span>

### <span data-ttu-id="28b71-113">示例1：调用方法</span><span class="sxs-lookup"><span data-stu-id="28b71-113">Example 1: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="28b71-114">此命令调用对应于后台处理程序服务 Win32_Service WMI 类实例的 **StartService** 方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-114">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="28b71-115">返回值指示操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="28b71-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="28b71-116">在这种情况下，返回值 0 指示成功。</span><span class="sxs-lookup"><span data-stu-id="28b71-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="28b71-117">返回值 5 指示该服务已启动。</span><span class="sxs-lookup"><span data-stu-id="28b71-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="28b71-118">示例2：调用方法</span><span class="sxs-lookup"><span data-stu-id="28b71-118">Example 2: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="28b71-119">此命令通过使用来自文件的输入对后台处理程序服务调用 **StopService** 方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-119">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="28b71-120">文件 Input.xml 包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="28b71-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="28b71-121">示例3：使用指定的参数值调用方法</span><span class="sxs-lookup"><span data-stu-id="28b71-121">Example 3: Invoke a method with specified parameter values</span></span>

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

<span data-ttu-id="28b71-122">此命令调用 Win32_Process 类的 **Create** 方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-122">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="28b71-123">它将方法传递两个参数值，Notepad.exe 和 C:\</span><span class="sxs-lookup"><span data-stu-id="28b71-123">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="28b71-124">因此，将创建一个新进程来运行记事本，新进程的当前目录将设置为 C:\。</span><span class="sxs-lookup"><span data-stu-id="28b71-124">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="28b71-125">示例4：在远程计算机上调用方法</span><span class="sxs-lookup"><span data-stu-id="28b71-125">Example 4: Invoke a method on a remote computer</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="28b71-126">此命令调用对应于后台处理程序服务 Win32_Service WMI 类实例的 **StartService** 方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-126">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="28b71-127">由于指定了 *ComputerName* 参数，因此该命令针对远程 server01 计算机运行。</span><span class="sxs-lookup"><span data-stu-id="28b71-127">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="28b71-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28b71-128">PARAMETERS</span></span>

### <span data-ttu-id="28b71-129">-Action</span><span class="sxs-lookup"><span data-stu-id="28b71-129">-Action</span></span>
<span data-ttu-id="28b71-130">指定要在由 ResourceURI 和选择器指定的管理对象上运行的方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-130">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-131">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="28b71-131">-ApplicationName</span></span>
<span data-ttu-id="28b71-132">指定连接中的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="28b71-132">Specifies the application name in the connection.</span></span>
<span data-ttu-id="28b71-133">*ApplicationName* 参数的默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="28b71-133">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="28b71-134">远程终结点的完整标识符采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="28b71-134">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="28b71-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="28b71-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="28b71-136">例如：`http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="28b71-136">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="28b71-137">托管该会话的 Internet Information Services (IIS) 将带有此终结点的请求转发到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="28b71-137">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="28b71-138">默认设置 WSMAN 适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="28b71-138">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="28b71-139">如果许多计算机建立了与运行 PowerShell 的一台计算机的远程连接，则可以使用此参数。</span><span class="sxs-lookup"><span data-stu-id="28b71-139">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="28b71-140">在此情况下，IIS 将托管 Web Services for Management (WS-Management) 以提高效率。</span><span class="sxs-lookup"><span data-stu-id="28b71-140">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="28b71-141">-Authentication</span><span class="sxs-lookup"><span data-stu-id="28b71-141">-Authentication</span></span>
<span data-ttu-id="28b71-142">指定服务器上要使用的身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="28b71-142">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="28b71-143">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="28b71-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="28b71-144">基本。</span><span class="sxs-lookup"><span data-stu-id="28b71-144">Basic.</span></span>
<span data-ttu-id="28b71-145">Basic 是一种将用户名和密码以明文形式发送到服务器或代理的方案。</span><span class="sxs-lookup"><span data-stu-id="28b71-145">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="28b71-146">默认。</span><span class="sxs-lookup"><span data-stu-id="28b71-146">Default.</span></span>
<span data-ttu-id="28b71-147">使用由 WS-Management 协议实现的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-147">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="28b71-148">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="28b71-148">This is the default.</span></span>
- <span data-ttu-id="28b71-149">摘要。</span><span class="sxs-lookup"><span data-stu-id="28b71-149">Digest.</span></span>
<span data-ttu-id="28b71-150">Digest 是一种质询响应方案，该方案将服务器指定的数据字符串用于质询。</span><span class="sxs-lookup"><span data-stu-id="28b71-150">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="28b71-151">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="28b71-151">Kerberos.</span></span>
<span data-ttu-id="28b71-152">客户端计算机和服务器通过使用 Kerberos 证书相互进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="28b71-152">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="28b71-153">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="28b71-153">Negotiate.</span></span>
<span data-ttu-id="28b71-154">Negotiate 是一种质询响应方案，该方案与服务器或代理协商以确定要用于身份验证的方案。</span><span class="sxs-lookup"><span data-stu-id="28b71-154">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="28b71-155">例如，此参数值允许协商以确定是使用 Kerberos 协议还是 NTLM。</span><span class="sxs-lookup"><span data-stu-id="28b71-155">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="28b71-156">CredSSP。</span><span class="sxs-lookup"><span data-stu-id="28b71-156">CredSSP.</span></span>
<span data-ttu-id="28b71-157">使用凭据安全支持提供程序 (CredSSP) 身份验证，可允许用户委派凭据。</span><span class="sxs-lookup"><span data-stu-id="28b71-157">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="28b71-158">此选项专门用于这样的命令：在一台远程计算机上运行，但从其他远程计算机收集数据或在其他远程计算机上运行其他命令。</span><span class="sxs-lookup"><span data-stu-id="28b71-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="28b71-159">注意：CredSSP 将用户凭据从本地计算机委派给远程计算机。</span><span class="sxs-lookup"><span data-stu-id="28b71-159">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="28b71-160">此做法增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="28b71-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="28b71-161">如果远程计算机的安全受到威胁，则在向该计算机传递凭据时，可使用这些凭据来控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="28b71-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="28b71-162">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="28b71-162">-CertificateThumbprint</span></span>
<span data-ttu-id="28b71-163">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="28b71-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="28b71-164">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="28b71-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="28b71-165">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="28b71-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="28b71-166">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="28b71-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="28b71-167">若要获取证书指纹，请使用 PowerShell Cert：驱动器中的 Get-Item 或 Get-ChildItem 命令。</span><span class="sxs-lookup"><span data-stu-id="28b71-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="28b71-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="28b71-168">-ComputerName</span></span>
<span data-ttu-id="28b71-169">指定要对其运行管理操作的计算机。</span><span class="sxs-lookup"><span data-stu-id="28b71-169">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="28b71-170">该值可以是完全限定的域名、NetBIOS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="28b71-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="28b71-171">使用本地计算机名称、localhost 或点 (.) 指定本地计算机。</span><span class="sxs-lookup"><span data-stu-id="28b71-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="28b71-172">默认值为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="28b71-172">The local computer is the default.</span></span>
<span data-ttu-id="28b71-173">当远程计算机与用户位于不同的域时，必须使用完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="28b71-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="28b71-174">可以通过管道将此参数的值传递给 cmdle。</span><span class="sxs-lookup"><span data-stu-id="28b71-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="28b71-175">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="28b71-175">-ConnectionURI</span></span>
<span data-ttu-id="28b71-176">指定连接终结点。</span><span class="sxs-lookup"><span data-stu-id="28b71-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="28b71-177">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="28b71-177">The format of this string is as follows:</span></span>

<span data-ttu-id="28b71-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="28b71-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="28b71-179">以下字符串是此参数的格式正确的值：</span><span class="sxs-lookup"><span data-stu-id="28b71-179">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="28b71-180">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="28b71-180">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="28b71-181">-Credential</span></span>
<span data-ttu-id="28b71-182">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="28b71-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="28b71-183">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="28b71-183">The default is the current user.</span></span>
<span data-ttu-id="28b71-184">键入用户名，如 User01、Domain01\User01 或 User@Domain.com 。</span><span class="sxs-lookup"><span data-stu-id="28b71-184">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="28b71-185">或者输入一个 PSCredential 对象，例如 Get-Credential cmdlet 返回的一个 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="28b71-185">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="28b71-186">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="28b71-186">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="28b71-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="28b71-187">-FilePath</span></span>
<span data-ttu-id="28b71-188">指定用于更新管理资源的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="28b71-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="28b71-189">通过使用 *ResourceURI* 参数和 *SelectorSet* 参数来指定管理资源。</span><span class="sxs-lookup"><span data-stu-id="28b71-189">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="28b71-190">例如，以下命令使用 *FilePath* 参数：</span><span class="sxs-lookup"><span data-stu-id="28b71-190">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="28b71-191">此命令通过使用来自文件的输入对 **后台处理程序** 服务调用 **StopService** 方法。</span><span class="sxs-lookup"><span data-stu-id="28b71-191">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="28b71-192">文件 Input.xml 包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="28b71-192">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="28b71-193">-OptionSet</span></span>
<span data-ttu-id="28b71-194">将一组开关指定到某个服务以修改或优化请求的性质。</span><span class="sxs-lookup"><span data-stu-id="28b71-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="28b71-195">这些开关类似于命令行 shell 中使用的开关，因为它们也特定于服务。</span><span class="sxs-lookup"><span data-stu-id="28b71-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="28b71-196">可以指定任何数量的选项。</span><span class="sxs-lookup"><span data-stu-id="28b71-196">Any number of options can be specified.</span></span>

<span data-ttu-id="28b71-197">以下示例演示为 a、b 和 c 参数传递值 1、2 和 3 的语法：</span><span class="sxs-lookup"><span data-stu-id="28b71-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-198">-Port</span><span class="sxs-lookup"><span data-stu-id="28b71-198">-Port</span></span>
<span data-ttu-id="28b71-199">指定要在客户端连接到 WinRM 服务时使用的端口。</span><span class="sxs-lookup"><span data-stu-id="28b71-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="28b71-200">当传输为 HTTP 时，默认端口为 80。</span><span class="sxs-lookup"><span data-stu-id="28b71-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="28b71-201">当传输为 HTTPS 时，默认端口为 443。</span><span class="sxs-lookup"><span data-stu-id="28b71-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="28b71-202">使用 HTTPS 作为传输协议时， *ComputerName* 参数的值必须与服务器的证书公用名 (CN) 相匹配。</span><span class="sxs-lookup"><span data-stu-id="28b71-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="28b71-203">但是，如果将 SkipCNCheck  参数指定为 SessionOption  参数的一部分，则服务器的证书公用名无需与服务器的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="28b71-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="28b71-204">SkipCNCheck  参数应仅用于受信任的计算机。</span><span class="sxs-lookup"><span data-stu-id="28b71-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="28b71-205">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="28b71-205">-ResourceURI</span></span>
<span data-ttu-id="28b71-206">指定资源类或实例的 URI。</span><span class="sxs-lookup"><span data-stu-id="28b71-206">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="28b71-207">URI 用于标识计算机上特定类型的资源，例如磁盘或进程。</span><span class="sxs-lookup"><span data-stu-id="28b71-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="28b71-208">URI 由资源的前缀和路径组成。</span><span class="sxs-lookup"><span data-stu-id="28b71-208">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="28b71-209">例如：</span><span class="sxs-lookup"><span data-stu-id="28b71-209">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-210">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="28b71-210">-SelectorSet</span></span>
<span data-ttu-id="28b71-211">指定一组用于选择特定管理资源实例的值对。</span><span class="sxs-lookup"><span data-stu-id="28b71-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="28b71-212">当存在多个资源实例时，将使用 *SelectorSet* 。</span><span class="sxs-lookup"><span data-stu-id="28b71-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="28b71-213">SelectorSet  的值必须为哈希表。</span><span class="sxs-lookup"><span data-stu-id="28b71-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="28b71-214">以下示例显示如何为此参数输入值：</span><span class="sxs-lookup"><span data-stu-id="28b71-214">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-215">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="28b71-215">-SessionOption</span></span>
<span data-ttu-id="28b71-216">为 WS-Management 会话指定扩展选项。</span><span class="sxs-lookup"><span data-stu-id="28b71-216">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="28b71-217">输入使用 New-WSManSessionOption cmdlet 创建的 **SessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="28b71-217">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="28b71-218">有关可用选项的详细信息，请键入 `Get-Help New-WSManSessionOption`。</span><span class="sxs-lookup"><span data-stu-id="28b71-218">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="28b71-219">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="28b71-219">-UseSSL</span></span>
<span data-ttu-id="28b71-220">指定使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="28b71-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="28b71-221">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="28b71-221">By default, SSL is not used.</span></span>

<span data-ttu-id="28b71-222">WS-Management 加密通过网络传输的所有 PowerShell 内容。</span><span class="sxs-lookup"><span data-stu-id="28b71-222">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="28b71-223">*UseSSL* 参数允许你指定 HTTPS 的额外保护，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="28b71-223">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="28b71-224">如果 SSL 在用于连接的端口上不可用，并且指定了此参数，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="28b71-224">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="28b71-225">-ValueSet</span><span class="sxs-lookup"><span data-stu-id="28b71-225">-ValueSet</span></span>
<span data-ttu-id="28b71-226">指定可帮助修改管理资源的哈希表。</span><span class="sxs-lookup"><span data-stu-id="28b71-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="28b71-227">使用 *ResourceURI* 和 *SelectorSet* 指定管理资源。</span><span class="sxs-lookup"><span data-stu-id="28b71-227">You specify the management resource by using *ResourceURI* and *SelectorSet* .</span></span>
<span data-ttu-id="28b71-228">*ValueSet* 参数的值必须为哈希表。</span><span class="sxs-lookup"><span data-stu-id="28b71-228">The value of the *ValueSet* parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28b71-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28b71-229">CommonParameters</span></span>
<span data-ttu-id="28b71-230">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="28b71-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28b71-231">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="28b71-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28b71-232">输入</span><span class="sxs-lookup"><span data-stu-id="28b71-232">INPUTS</span></span>

### <span data-ttu-id="28b71-233">无</span><span class="sxs-lookup"><span data-stu-id="28b71-233">None</span></span>
<span data-ttu-id="28b71-234">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="28b71-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="28b71-235">输出</span><span class="sxs-lookup"><span data-stu-id="28b71-235">OUTPUTS</span></span>

### <span data-ttu-id="28b71-236">无</span><span class="sxs-lookup"><span data-stu-id="28b71-236">None</span></span>
<span data-ttu-id="28b71-237">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="28b71-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="28b71-238">注释</span><span class="sxs-lookup"><span data-stu-id="28b71-238">NOTES</span></span>

## <span data-ttu-id="28b71-239">相关链接</span><span class="sxs-lookup"><span data-stu-id="28b71-239">RELATED LINKS</span></span>

[<span data-ttu-id="28b71-240">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="28b71-240">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="28b71-241">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="28b71-241">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="28b71-242">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="28b71-242">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="28b71-243">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="28b71-243">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="28b71-244">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="28b71-244">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="28b71-245">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28b71-245">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="28b71-246">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28b71-246">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="28b71-247">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="28b71-247">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="28b71-248">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28b71-248">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="28b71-249">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28b71-249">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="28b71-250">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="28b71-250">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="28b71-251">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="28b71-251">Test-WSMan</span></span>](Test-WSMan.md)

