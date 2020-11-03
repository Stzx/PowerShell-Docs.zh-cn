---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: eaf64fd0cbd8d0bcac5e77a72a51b2d2657a3c12
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198885"
---
# <span data-ttu-id="3d915-103">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="3d915-103">New-CimSession</span></span>

## <span data-ttu-id="3d915-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3d915-104">SYNOPSIS</span></span>

<span data-ttu-id="3d915-105">创建 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-105">Creates a CIM session.</span></span>

## <span data-ttu-id="3d915-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d915-106">SYNTAX</span></span>

### <span data-ttu-id="3d915-107">CredentialParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="3d915-107">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="3d915-108">CertificateParameterSet</span><span class="sxs-lookup"><span data-stu-id="3d915-108">CertificateParameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="3d915-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d915-109">DESCRIPTION</span></span>

<span data-ttu-id="3d915-110">`New-CimSession`Cmdlet 将创建一个 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-110">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="3d915-111">CIM 会话是表示与本地计算机或远程计算机的连接的客户端对象。</span><span class="sxs-lookup"><span data-stu-id="3d915-111">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="3d915-112">CIM 会话包含有关连接的信息，例如 **ComputerName** 、使用的协议或各种标识符。</span><span class="sxs-lookup"><span data-stu-id="3d915-112">The CIM session contains information about the connection, such as **ComputerName** , the protocol used, or various identifiers.</span></span>

<span data-ttu-id="3d915-113">此 cmdlet 将返回可供所有其他 CIM cmdlet 使用的 CIM 会话对象。</span><span class="sxs-lookup"><span data-stu-id="3d915-113">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="3d915-114">示例</span><span class="sxs-lookup"><span data-stu-id="3d915-114">EXAMPLES</span></span>

### <span data-ttu-id="3d915-115">示例1：使用默认选项创建 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-115">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="3d915-116">此示例使用默认选项创建本地 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-116">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="3d915-117">如果未指定 **ComputerName** ，则会 `New-CimSession` 创建与本地计算机的 DCOM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-117">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="3d915-118">示例2：创建特定计算机的 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-118">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="3d915-119">此示例为 **ComputerName** 指定的计算机创建 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-119">This example creates a CIM session to the computer specified by **ComputerName** .</span></span>
<span data-ttu-id="3d915-120">默认情况下， `New-CimSession` 在指定 **ComputerName** 时创建 WSMan 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-120">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="3d915-121">示例3：创建多台计算机的 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-121">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="3d915-122">此示例将在以逗号分隔的列表中为 **ComputerName** 指定的每台计算机创建一个 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-122">This example creates a CIM session to each of the computers specified by **ComputerName** , in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="3d915-123">示例4：使用友好名称创建 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-123">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="3d915-124">此示例将为 **ComputerName** 指定的每台计算机创建一个远程 CIM 会话，以逗号分隔的列表形式创建，并通过指定 **名称** 为新会话分配一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="3d915-124">This example creates a remote CIM session to each of the computers specified by **ComputerName** , in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name** .</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="3d915-125">可以使用 CIM 会话的友好名称在其他 CIM cmdlet 中引用会话，例如， [CimSession](Get-CimSession.md)。</span><span class="sxs-lookup"><span data-stu-id="3d915-125">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="3d915-126">示例5：使用 PSCredential 对象创建到计算机的 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-126">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="3d915-127">此示例使用由 **Credential** 指定的 **PSCredential** 对象和 **身份验证** 指定的身份验证类型，为 **ComputerName** 指定的计算机创建 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-127">This example creates a CIM session to the computer specified by **ComputerName** , using the **PSCredential** object specified by **Credential** , and the authentication type specified by **Authentication** .</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="3d915-128">可以使用 cmdlet 创建 **PSCredential** 对象 [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d915-128">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="3d915-129">示例6：使用特定端口创建到计算机的 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-129">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="3d915-130">此示例使用由 **端口** 指定的 TCP 端口，为 **ComputerName** 指定的计算机创建 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-130">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port** .</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="3d915-131">示例7：使用 DCOM 创建 CIM 会话</span><span class="sxs-lookup"><span data-stu-id="3d915-131">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="3d915-132">此示例使用分布式 COM (DCOM) 协议而不是 WSMan 创建 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-132">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="3d915-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d915-133">PARAMETERS</span></span>

### <span data-ttu-id="3d915-134">-Authentication</span><span class="sxs-lookup"><span data-stu-id="3d915-134">-Authentication</span></span>

<span data-ttu-id="3d915-135">指定用于用户凭据的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3d915-135">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="3d915-136">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="3d915-136">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3d915-137">默认</span><span class="sxs-lookup"><span data-stu-id="3d915-137">Default</span></span>
- <span data-ttu-id="3d915-138">摘要</span><span class="sxs-lookup"><span data-stu-id="3d915-138">Digest</span></span>
- <span data-ttu-id="3d915-139">Negotiate</span><span class="sxs-lookup"><span data-stu-id="3d915-139">Negotiate</span></span>
- <span data-ttu-id="3d915-140">基本</span><span class="sxs-lookup"><span data-stu-id="3d915-140">Basic</span></span>
- <span data-ttu-id="3d915-141">Kerberos</span><span class="sxs-lookup"><span data-stu-id="3d915-141">Kerberos</span></span>
- <span data-ttu-id="3d915-142">NtlmDomain</span><span class="sxs-lookup"><span data-stu-id="3d915-142">NtlmDomain</span></span>
- <span data-ttu-id="3d915-143">CredSsp</span><span class="sxs-lookup"><span data-stu-id="3d915-143">CredSsp</span></span>

<span data-ttu-id="3d915-144">不能将 **NtlmDomain** 身份验证类型用于连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3d915-144">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="3d915-145">**CredSSP** 身份验证仅在 windows Vista、windows Server 2008 和更高版本的 windows 中可用。</span><span class="sxs-lookup"><span data-stu-id="3d915-145">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="3d915-146">凭据安全服务提供程序 (CredSSP) 身份验证专用于要求对多个资源（例如访问远程网络共享）进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="3d915-146">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="3d915-147">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="3d915-147">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="3d915-148">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-148">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="3d915-149">-CertificateThumbprint</span></span>

<span data-ttu-id="3d915-150">指定有权执行此操作的用户帐户的数字公钥证书 (x.509) 。</span><span class="sxs-lookup"><span data-stu-id="3d915-150">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="3d915-151">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="3d915-151">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="3d915-152">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="3d915-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="3d915-153">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="3d915-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="3d915-154">若要获取证书指纹，请使用 [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) PowerShell 证书提供程序中的或 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d915-154">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="3d915-155">有关详细信息，请参阅 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3d915-155">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-156">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3d915-156">-ComputerName</span></span>

<span data-ttu-id="3d915-157">指定要为其创建 CIM 会话的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="3d915-157">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="3d915-158">指定单个计算机名称或用逗号分隔的多个计算机名称。</span><span class="sxs-lookup"><span data-stu-id="3d915-158">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="3d915-159">如果未指定 **ComputerName** ，则会创建到本地计算机的 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-159">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="3d915-160">可以采用以下格式之一指定 "计算机名称" 的值：</span><span class="sxs-lookup"><span data-stu-id="3d915-160">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="3d915-161">一个或多个 NetBIOS 名称</span><span class="sxs-lookup"><span data-stu-id="3d915-161">One or more NetBIOS names</span></span>
- <span data-ttu-id="3d915-162">一个或多个 IP 地址</span><span class="sxs-lookup"><span data-stu-id="3d915-162">One or more IP addresses</span></span>
- <span data-ttu-id="3d915-163">一个或多个完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="3d915-163">One or more fully qualified domain names.</span></span>

<span data-ttu-id="3d915-164">如果计算机与用户位于不同的域中，则必须指定完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="3d915-164">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="3d915-165">-Credential</span></span>

<span data-ttu-id="3d915-166">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3d915-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="3d915-167">如果未指定 **凭据** ，则使用当前用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3d915-167">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="3d915-168">使用以下格式之一指定 **Credential** 的值：</span><span class="sxs-lookup"><span data-stu-id="3d915-168">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="3d915-169">用户名： "User01"</span><span class="sxs-lookup"><span data-stu-id="3d915-169">A user name: "User01"</span></span>
- <span data-ttu-id="3d915-170">域名和用户名： "Domain01\User01"</span><span class="sxs-lookup"><span data-stu-id="3d915-170">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="3d915-171">用户主体名称： " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="3d915-171">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="3d915-172">一个 PSCredential 对象，例如 cmdlet 返回的一个 PSCredential 对象 [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d915-172">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="3d915-173">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="3d915-173">When you type a user name, you are prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-174">-Name</span><span class="sxs-lookup"><span data-stu-id="3d915-174">-Name</span></span>

<span data-ttu-id="3d915-175">指定 CIM 会话的友好名称。</span><span class="sxs-lookup"><span data-stu-id="3d915-175">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="3d915-176">使用其他 cmdlet （如 [CimSession](Get-CimSession.md) cmdlet）时，可以使用该名称来引用 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-176">You can use the name to refer to the CIM session when using other cmdlets, such as the [Get-CimSession](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="3d915-177">对于计算机或当前会话，该名称无需是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3d915-177">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-178">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="3d915-178">-OperationTimeoutSec</span></span>

<span data-ttu-id="3d915-179">Cmdlet 等待服务器响应的持续时间。</span><span class="sxs-lookup"><span data-stu-id="3d915-179">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="3d915-180">默认情况下，此参数的值为0，表示该 cmdlet 使用服务器的默认超时值。</span><span class="sxs-lookup"><span data-stu-id="3d915-180">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="3d915-181">如果 **OperationTimeoutSec** 参数设置为小于3分钟的稳定连接重试超时值，则不能恢复最后超过 **OperationTimeoutSec** 参数值的网络故障，因为在客户端重新连接之前，服务器上的操作将超时。</span><span class="sxs-lookup"><span data-stu-id="3d915-181">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-182">-Port</span><span class="sxs-lookup"><span data-stu-id="3d915-182">-Port</span></span>

<span data-ttu-id="3d915-183">指定远程计算机上用于此连接的网络端口。</span><span class="sxs-lookup"><span data-stu-id="3d915-183">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="3d915-184">若要连接到一台远程计算机，则必须在该连接所用的端口上侦听远程计算机。</span><span class="sxs-lookup"><span data-stu-id="3d915-184">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="3d915-185">默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。</span><span class="sxs-lookup"><span data-stu-id="3d915-185">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="3d915-186">使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="3d915-186">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="3d915-187">使用以下命令配置侦听器：</span><span class="sxs-lookup"><span data-stu-id="3d915-187">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="3d915-188">除非必要，否则不要使用 **Port** 参数。</span><span class="sxs-lookup"><span data-stu-id="3d915-188">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="3d915-189">命令中的端口设置适用于运行该命令的所有计算机或会话。</span><span class="sxs-lookup"><span data-stu-id="3d915-189">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="3d915-190">备用端口设置可能会阻止在所有计算机上运行该命令。</span><span class="sxs-lookup"><span data-stu-id="3d915-190">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-191">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="3d915-191">-SessionOption</span></span>

<span data-ttu-id="3d915-192">为新的 CIM 会话设置高级选项。</span><span class="sxs-lookup"><span data-stu-id="3d915-192">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="3d915-193">输入使用 cmdlet 创建的 **CimSessionOption** 对象的名称 [`New-CimSessionOption`](New-CimSessionOption.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d915-193">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-194">-SkipTestConnection</span><span class="sxs-lookup"><span data-stu-id="3d915-194">-SkipTestConnection</span></span>

<span data-ttu-id="3d915-195">默认情况下，由于 `New-CimSession` 以下两个原因，该 cmdlet 将与远程 WS-Management 终结点建立连接：验证远程服务器是否正在侦听使用 **port** 参数指定的端口号，并验证指定的帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="3d915-195">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="3d915-196">使用标准 WS-Identity 操作完成验证。</span><span class="sxs-lookup"><span data-stu-id="3d915-196">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="3d915-197">如果远程 WS-Management 终结点不能使用 WS 标识，则可以添加 **SkipTestConnection** 开关参数，或减少某些数据传输时间。</span><span class="sxs-lookup"><span data-stu-id="3d915-197">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d915-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3d915-198">CommonParameters</span></span>

<span data-ttu-id="3d915-199">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3d915-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d915-200">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="3d915-200">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3d915-201">输入</span><span class="sxs-lookup"><span data-stu-id="3d915-201">INPUTS</span></span>

### <span data-ttu-id="3d915-202">无</span><span class="sxs-lookup"><span data-stu-id="3d915-202">None</span></span>

<span data-ttu-id="3d915-203">此 cmdlet 不接受输入。</span><span class="sxs-lookup"><span data-stu-id="3d915-203">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="3d915-204">输出</span><span class="sxs-lookup"><span data-stu-id="3d915-204">OUTPUTS</span></span>

### <span data-ttu-id="3d915-205">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="3d915-205">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="3d915-206">注释</span><span class="sxs-lookup"><span data-stu-id="3d915-206">NOTES</span></span>

## <span data-ttu-id="3d915-207">相关链接</span><span class="sxs-lookup"><span data-stu-id="3d915-207">RELATED LINKS</span></span>

[<span data-ttu-id="3d915-208">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="3d915-208">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="3d915-209">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="3d915-209">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="3d915-210">Get-Item</span><span class="sxs-lookup"><span data-stu-id="3d915-210">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="3d915-211">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="3d915-211">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="3d915-212">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="3d915-212">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="3d915-213">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="3d915-213">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="3d915-214">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="3d915-214">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

