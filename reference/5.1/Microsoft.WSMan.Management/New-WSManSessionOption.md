---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: f32b9300fddcf9086bc670912931001557b91cd8
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200620"
---
# <span data-ttu-id="b07d4-103">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b07d4-103">New-WSManSessionOption</span></span>

## <span data-ttu-id="b07d4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b07d4-104">SYNOPSIS</span></span>
<span data-ttu-id="b07d4-105">创建要用作 WS-Management cmdlet 的输入参数的会话选项哈希表。</span><span class="sxs-lookup"><span data-stu-id="b07d4-105">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="b07d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b07d4-106">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="b07d4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b07d4-107">DESCRIPTION</span></span>
<span data-ttu-id="b07d4-108">**New-wsmansessionoption** cmdlet 创建可传递到 wsman Cmdlet 的 WSMan 会话选项哈希表：</span><span class="sxs-lookup"><span data-stu-id="b07d4-108">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="b07d4-109">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b07d4-109">Get-WSManInstance</span></span>
- <span data-ttu-id="b07d4-110">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b07d4-110">Set-WSManInstance</span></span>
- <span data-ttu-id="b07d4-111">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b07d4-111">Invoke-WSManAction</span></span>
- <span data-ttu-id="b07d4-112">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b07d4-112">Connect-WSMan</span></span>

## <span data-ttu-id="b07d4-113">示例</span><span class="sxs-lookup"><span data-stu-id="b07d4-113">EXAMPLES</span></span>

### <span data-ttu-id="b07d4-114">示例1：创建使用连接选项的连接</span><span class="sxs-lookup"><span data-stu-id="b07d4-114">Example 1: Create a connection that uses connection options</span></span>

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

<span data-ttu-id="b07d4-115">此示例使用由 **new-wsmansessionoption** 定义的连接选项创建与远程 server01 计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="b07d4-115">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption** .</span></span>

<span data-ttu-id="b07d4-116">第一个命令使用 **new-wsmansessionoption** 将一组连接设置选项存储在 $a 变量中。</span><span class="sxs-lookup"><span data-stu-id="b07d4-116">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="b07d4-117">在此情况下，这些会话选项将连接超时设置为 30 秒（30,000 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="b07d4-117">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="b07d4-118">第二个命令使用 *SessionOption* 参数将存储在 $a 变量中的凭据传递到 **连接-WSMan** 。</span><span class="sxs-lookup"><span data-stu-id="b07d4-118">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan** .</span></span>
<span data-ttu-id="b07d4-119">然后，使用指定的会话选项 **连接-WSMan** 连接到远程 server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="b07d4-119">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="b07d4-120">**连接-wsman** 通常用于 wsman 提供程序的上下文中，用于连接到远程计算机（在本例中为 server01 计算机）。</span><span class="sxs-lookup"><span data-stu-id="b07d4-120">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="b07d4-121">但是，你可以在更改为 WSMan 提供程序之前，使用该 cmdlet 建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="b07d4-121">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="b07d4-122">这些连接将出现在 **ComputerName** 列表中。</span><span class="sxs-lookup"><span data-stu-id="b07d4-122">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="b07d4-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b07d4-123">PARAMETERS</span></span>

### <span data-ttu-id="b07d4-124">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="b07d4-124">-NoEncryption</span></span>
<span data-ttu-id="b07d4-125">指示连接不将加密用于通过 HTTP 进行的远程操作。</span><span class="sxs-lookup"><span data-stu-id="b07d4-125">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="b07d4-126">默认情况下，不会启用未加密的流量。</span><span class="sxs-lookup"><span data-stu-id="b07d4-126">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="b07d4-127">它必须在本地配置中启用。</span><span class="sxs-lookup"><span data-stu-id="b07d4-127">It must be enabled in the local configuration.</span></span>

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

### <span data-ttu-id="b07d4-128">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="b07d4-128">-OperationTimeout</span></span>
<span data-ttu-id="b07d4-129">指定 WS-Management 操作的超时时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="b07d4-129">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b07d4-130">-ProxyAccessType</span><span class="sxs-lookup"><span data-stu-id="b07d4-130">-ProxyAccessType</span></span>
<span data-ttu-id="b07d4-131">指定代理服务器定位所依据的机制。</span><span class="sxs-lookup"><span data-stu-id="b07d4-131">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="b07d4-132">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="b07d4-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b07d4-133">ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="b07d4-133">ProxyIEConfig.</span></span>
<span data-ttu-id="b07d4-134">为当前用户使用 Internet Explorer 代理配置。</span><span class="sxs-lookup"><span data-stu-id="b07d4-134">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="b07d4-135">ProxyWinHttpConfig.</span><span class="sxs-lookup"><span data-stu-id="b07d4-135">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="b07d4-136">WSMan 客户端使用 ProxyCfg.exe 实用程序为 WinHTTP 配置的代理设置。</span><span class="sxs-lookup"><span data-stu-id="b07d4-136">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="b07d4-137">ProxyAutoDetect.</span><span class="sxs-lookup"><span data-stu-id="b07d4-137">ProxyAutoDetect.</span></span>
<span data-ttu-id="b07d4-138">强制自动检测代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b07d4-138">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="b07d4-139">ProxyNoProxyServer.</span><span class="sxs-lookup"><span data-stu-id="b07d4-139">ProxyNoProxyServer.</span></span>
<span data-ttu-id="b07d4-140">“不使用代理服务器”。</span><span class="sxs-lookup"><span data-stu-id="b07d4-140">Do not use a proxy server.</span></span>
<span data-ttu-id="b07d4-141">在本地解析所有主机名。</span><span class="sxs-lookup"><span data-stu-id="b07d4-141">Resolve all host names locally.</span></span>

<span data-ttu-id="b07d4-142">默认值为 ProxyIEConfig。</span><span class="sxs-lookup"><span data-stu-id="b07d4-142">The default value is ProxyIEConfig.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b07d4-143">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="b07d4-143">-ProxyAuthentication</span></span>
<span data-ttu-id="b07d4-144">指定要在代理中使用的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="b07d4-144">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="b07d4-145">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="b07d4-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b07d4-146">基本。</span><span class="sxs-lookup"><span data-stu-id="b07d4-146">Basic.</span></span>
<span data-ttu-id="b07d4-147">Basic 是一种将用户名和密码以明文形式发送到服务器或代理的方案。</span><span class="sxs-lookup"><span data-stu-id="b07d4-147">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="b07d4-148">摘要。</span><span class="sxs-lookup"><span data-stu-id="b07d4-148">Digest.</span></span>
<span data-ttu-id="b07d4-149">Digest 是一种质询响应方案，该方案将服务器指定的数据字符串用于质询。</span><span class="sxs-lookup"><span data-stu-id="b07d4-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="b07d4-150">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="b07d4-150">Negotiate.</span></span>
<span data-ttu-id="b07d4-151">Negotiate 是一种质询响应方案，该方案与服务器或代理协商以确定要用于身份验证的方案。</span><span class="sxs-lookup"><span data-stu-id="b07d4-151">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="b07d4-152">例如，Kerberos 协议和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="b07d4-152">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="b07d4-153">默认值为 "协商"。</span><span class="sxs-lookup"><span data-stu-id="b07d4-153">The default value is Negotiate.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b07d4-154">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="b07d4-154">-ProxyCredential</span></span>
<span data-ttu-id="b07d4-155">指定有权通过中间 Web 代理获得访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b07d4-155">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

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

### <span data-ttu-id="b07d4-156">-SPNPort</span><span class="sxs-lookup"><span data-stu-id="b07d4-156">-SPNPort</span></span>
<span data-ttu-id="b07d4-157">指定要追加到远程服务器的连接服务主体名称 (SPN) 的端口号。</span><span class="sxs-lookup"><span data-stu-id="b07d4-157">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="b07d4-158">当身份验证机制是 Kerberos 或 Negotiate 时，使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="b07d4-158">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

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

### <span data-ttu-id="b07d4-159">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="b07d4-159">-SkipCACheck</span></span>
<span data-ttu-id="b07d4-160">指定当通过 HTTPS 进行连接时，客户端不会验证服务器证书是否由受信任的证书颁发机构签名 (CA) 。</span><span class="sxs-lookup"><span data-stu-id="b07d4-160">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="b07d4-161">仅当远程计算机受另一种方法的信任时（例如，如果远程计算机是物理安全和隔离的网络的一部分，或者远程计算机在 WS-Management 配置中列为受信任主机），则使用此选项。</span><span class="sxs-lookup"><span data-stu-id="b07d4-161">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

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

### <span data-ttu-id="b07d4-162">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="b07d4-162">-SkipCNCheck</span></span>
<span data-ttu-id="b07d4-163">指定服务器的证书公用名 (CN) 不必与服务器的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="b07d4-163">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="b07d4-164">这仅用于使用 HTTPS 的远程操作。</span><span class="sxs-lookup"><span data-stu-id="b07d4-164">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="b07d4-165">此选项应仅用于受信任的计算机。</span><span class="sxs-lookup"><span data-stu-id="b07d4-165">This option should only be used for trusted computers.</span></span>

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

### <span data-ttu-id="b07d4-166">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="b07d4-166">-SkipRevocationCheck</span></span>
<span data-ttu-id="b07d4-167">指示连接不验证服务器证书上的吊销状态。</span><span class="sxs-lookup"><span data-stu-id="b07d4-167">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

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

### <span data-ttu-id="b07d4-168">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="b07d4-168">-UseUTF16</span></span>
<span data-ttu-id="b07d4-169">指示连接以 UTF16 格式而不是 UTF8 格式对请求进行编码。</span><span class="sxs-lookup"><span data-stu-id="b07d4-169">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="b07d4-170">默认值为 UTF8 编码。</span><span class="sxs-lookup"><span data-stu-id="b07d4-170">The default is UTF8 encoding.</span></span>

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

### <span data-ttu-id="b07d4-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b07d4-171">CommonParameters</span></span>
<span data-ttu-id="b07d4-172">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b07d4-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b07d4-173">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b07d4-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b07d4-174">输入</span><span class="sxs-lookup"><span data-stu-id="b07d4-174">INPUTS</span></span>

## <span data-ttu-id="b07d4-175">输出</span><span class="sxs-lookup"><span data-stu-id="b07d4-175">OUTPUTS</span></span>

### <span data-ttu-id="b07d4-176">SessionOption</span><span class="sxs-lookup"><span data-stu-id="b07d4-176">SessionOption</span></span>

## <span data-ttu-id="b07d4-177">注释</span><span class="sxs-lookup"><span data-stu-id="b07d4-177">NOTES</span></span>

## <span data-ttu-id="b07d4-178">相关链接</span><span class="sxs-lookup"><span data-stu-id="b07d4-178">RELATED LINKS</span></span>

[<span data-ttu-id="b07d4-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b07d4-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b07d4-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b07d4-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="b07d4-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b07d4-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b07d4-182">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b07d4-182">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="b07d4-183">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b07d4-183">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b07d4-184">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b07d4-184">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="b07d4-185">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b07d4-185">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="b07d4-186">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b07d4-186">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="b07d4-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b07d4-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="b07d4-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b07d4-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b07d4-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b07d4-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b07d4-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b07d4-190">Test-WSMan</span></span>](Test-WSMan.md)
