---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197771"
---
# <span data-ttu-id="665cb-103">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="665cb-103">New-PSWorkflowSession</span></span>

## <span data-ttu-id="665cb-104">摘要</span><span class="sxs-lookup"><span data-stu-id="665cb-104">SYNOPSIS</span></span>
<span data-ttu-id="665cb-105">创建工作流会话。</span><span class="sxs-lookup"><span data-stu-id="665cb-105">Creates a workflow session.</span></span>

## <span data-ttu-id="665cb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="665cb-106">SYNTAX</span></span>

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## <span data-ttu-id="665cb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="665cb-107">DESCRIPTION</span></span>

<span data-ttu-id="665cb-108">`New-PSWorkflowSession`Cmdlet 将创建一个用户管理的会话 ( **PSSession** ) ，该会话特别设计用于运行 Windows PowerShell 工作流。</span><span class="sxs-lookup"><span data-stu-id="665cb-108">The `New-PSWorkflowSession` cmdlet creates a user-managed session ( **PSSession** ) that is especially designed for running Windows PowerShell workflows.</span></span> <span data-ttu-id="665cb-109">它使用 Microsoft.PowerShell.Workflow 会话配置，其中包括脚本、类型和格式设置文件，以及工作流所需的选项。</span><span class="sxs-lookup"><span data-stu-id="665cb-109">It uses the Microsoft.PowerShell.Workflow session configuration, which includes scripts, type and formatting files, and options that are required for workflows.</span></span>

<span data-ttu-id="665cb-110">可以使用 `New-PSWorkflowSession` 或其别名 `nwsn` 。</span><span class="sxs-lookup"><span data-stu-id="665cb-110">You can use `New-PSWorkflowSession` or its alias, `nwsn`.</span></span>

<span data-ttu-id="665cb-111">你还可以将工作流通用参数添加到此命令。</span><span class="sxs-lookup"><span data-stu-id="665cb-111">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="665cb-112">有关工作流通用参数的详细信息，请参阅 [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="665cb-112">For more information about workflow common parameters, see [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="665cb-113">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="665cb-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="665cb-114">示例</span><span class="sxs-lookup"><span data-stu-id="665cb-114">EXAMPLES</span></span>

### <span data-ttu-id="665cb-115">示例 1：在远程计算机上创建工作流会话</span><span class="sxs-lookup"><span data-stu-id="665cb-115">Example 1: Create a workflow session on a remote computer</span></span>

<span data-ttu-id="665cb-116">此示例在 ServerNode01 远程计算机上创建 **WorkflowTests** 会话。</span><span class="sxs-lookup"><span data-stu-id="665cb-116">This example creates the **WorkflowTests** session on the ServerNode01 remote computer.</span></span>

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

<span data-ttu-id="665cb-117">**SessionOption** 参数的值是一个 `New-PSSessionOption` 命令，用于将会话中的输出缓冲模式设置为 **丢弃** 。</span><span class="sxs-lookup"><span data-stu-id="665cb-117">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that sets the output buffering mode in the session to **Drop** .</span></span>

### <span data-ttu-id="665cb-118">示例 2：在多台远程计算机上创建工作流会话</span><span class="sxs-lookup"><span data-stu-id="665cb-118">Example 2: Create workflow sessions on multiple remote computers</span></span>

<span data-ttu-id="665cb-119">此示例在 ServerNode01 和 Server12 计算机上创建工作流会话。</span><span class="sxs-lookup"><span data-stu-id="665cb-119">This example creates workflow sessions on the ServerNode01 and Server12 computers.</span></span> <span data-ttu-id="665cb-120">该命令使用 **Credential** 参数以通过域管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="665cb-120">The command uses the **Credential** parameter to run with the permissions of the domain administrator.</span></span>

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

<span data-ttu-id="665cb-121">该命令使用 **ThrottleLimit** 参数以将每个命令的中止值增加到 150。</span><span class="sxs-lookup"><span data-stu-id="665cb-121">The command uses the **ThrottleLimit** parameter to increase the per-command throttle limit to 150.</span></span>
<span data-ttu-id="665cb-122">此值优先于在 **Microsoft. Workflow** 会话配置中设置的默认限制（100）。</span><span class="sxs-lookup"><span data-stu-id="665cb-122">This value takes precedence over the default throttle limit of 100 that is set in the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

## <span data-ttu-id="665cb-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="665cb-123">PARAMETERS</span></span>

### <span data-ttu-id="665cb-124">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="665cb-124">-ApplicationName</span></span>

<span data-ttu-id="665cb-125">指定连接 URI 的应用程序名称段。</span><span class="sxs-lookup"><span data-stu-id="665cb-125">Specifies the application name segment of the connection URI.</span></span>

<span data-ttu-id="665cb-126">默认值为 `$PSSessionApplicationName` 本地计算机上首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="665cb-126">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="665cb-127">如果未定义此首选项变量，则默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="665cb-127">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="665cb-128">该值适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="665cb-128">This value is appropriate for most uses.</span></span> <span data-ttu-id="665cb-129">有关详细信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="665cb-129">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="665cb-130">WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。</span><span class="sxs-lookup"><span data-stu-id="665cb-130">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="665cb-131">此参数的值应与远程计算机上的侦听器的 **URLPrefix** 属性值匹配。</span><span class="sxs-lookup"><span data-stu-id="665cb-131">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="665cb-132">-Authentication</span><span class="sxs-lookup"><span data-stu-id="665cb-132">-Authentication</span></span>

<span data-ttu-id="665cb-133">指定用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="665cb-133">Specifies the mechanism that is used to authenticate the user credentials.</span></span>
<span data-ttu-id="665cb-134">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="665cb-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="665cb-135">默认</span><span class="sxs-lookup"><span data-stu-id="665cb-135">Default</span></span>
- <span data-ttu-id="665cb-136">基本</span><span class="sxs-lookup"><span data-stu-id="665cb-136">Basic</span></span>
- <span data-ttu-id="665cb-137">Credssp</span><span class="sxs-lookup"><span data-stu-id="665cb-137">Credssp</span></span>
- <span data-ttu-id="665cb-138">摘要</span><span class="sxs-lookup"><span data-stu-id="665cb-138">Digest</span></span>
- <span data-ttu-id="665cb-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="665cb-139">Kerberos</span></span>
- <span data-ttu-id="665cb-140">Negotiate</span><span class="sxs-lookup"><span data-stu-id="665cb-140">Negotiate</span></span>
- <span data-ttu-id="665cb-141">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="665cb-141">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="665cb-142">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="665cb-142">The default value is Default.</span></span>

<span data-ttu-id="665cb-143">CredSSP 身份验证仅在 Windows Vista、Windows Server 2008 和更高版本的 Windows 操作系统中可用。</span><span class="sxs-lookup"><span data-stu-id="665cb-143">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="665cb-144">有关此参数的值的详细信息，请参阅 [System.management.automation.runspaces.authenticationmechanism 枚举](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="665cb-144">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="665cb-145">凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="665cb-145">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="665cb-146">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="665cb-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="665cb-147">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="665cb-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="665cb-148">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="665cb-148">-CertificateThumbprint</span></span>

<span data-ttu-id="665cb-149">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="665cb-149">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="665cb-150">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="665cb-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="665cb-151">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="665cb-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="665cb-152">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="665cb-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="665cb-153">若要获取证书指纹，请 `Get-Item` `Get-ChildItem` 在 Windows PowerShell Cert：驱动器中使用 cmdlet 或 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="665cb-153">To get a certificate thumbprint, use the `Get-Item` cmdlet or the `Get-ChildItem` cmdlet in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="665cb-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="665cb-154">-ComputerName</span></span>

<span data-ttu-id="665cb-155">创建 ( **PSSession** ) 到指定计算机的持续性连接。</span><span class="sxs-lookup"><span data-stu-id="665cb-155">Creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="665cb-156">如果输入多个计算机名称，Windows PowerShell 将创建多个 **pssession** ，每台计算机一个。</span><span class="sxs-lookup"><span data-stu-id="665cb-156">If you enter multiple computer names, Windows PowerShell creates multiple **PSSessions** , one for each computer.</span></span> <span data-ttu-id="665cb-157">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="665cb-157">The default is the local computer.</span></span>

<span data-ttu-id="665cb-158">键入一台或多台远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="665cb-158">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="665cb-159">若要指定本地计算机，请键入该计算机名称、localhost 或句点 (.)。</span><span class="sxs-lookup"><span data-stu-id="665cb-159">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="665cb-160">当计算机与用户处于不同的域中时，必须使用完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="665cb-160">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="665cb-161">还可以通过管道将计算机名称传递给 `New-PSWorkflowSession` 。</span><span class="sxs-lookup"><span data-stu-id="665cb-161">You can also pipe a computer name, in quotation marks to `New-PSWorkflowSession`.</span></span>

<span data-ttu-id="665cb-162">若要在 **ComputerName** 参数的值中使用 IP 地址，该命令必须包括 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="665cb-162">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="665cb-163">此外，必须为计算机配置 HTTPS 传输，或者必须在本地计算机上的 WinRM TrustedHosts 列表中包含远程计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="665cb-163">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="665cb-164">有关将计算机名称添加到 TrustedHosts 列表的说明，请参阅 [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)中的 "如何将计算机添加到受信任的主机列表中"。</span><span class="sxs-lookup"><span data-stu-id="665cb-164">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="665cb-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="665cb-165">-Credential</span></span>

<span data-ttu-id="665cb-166">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="665cb-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="665cb-167">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="665cb-167">The default is the current user.</span></span> <span data-ttu-id="665cb-168">键入用户名，如 User01、Domain01\User01 或 User@Domain.com ，或输入 **PSCredential** 对象，如 cmdlet 返回的一个 PSCredential 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="665cb-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com, or enter a **PSCredential** object, such as one returned by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="665cb-169">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="665cb-169">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="665cb-170">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="665cb-170">-EnableNetworkAccess</span></span>

<span data-ttu-id="665cb-171">指示此 cmdlet 将交互式安全令牌添加到环回会话。</span><span class="sxs-lookup"><span data-stu-id="665cb-171">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="665cb-172">通过交互式令牌，你可以在环回会话中运行用于获取其他计算机中的数据的命令。</span><span class="sxs-lookup"><span data-stu-id="665cb-172">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="665cb-173">例如，你可以在该会话中运行用于将 XML 文件从远程计算机复制到本地计算机的命令。</span><span class="sxs-lookup"><span data-stu-id="665cb-173">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="665cb-174">环回会话是在同一计算机上开始并终止的 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="665cb-174">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="665cb-175">若要创建环回会话，请不要指定 ComputerName  参数，或将其值设置为“.”、localhost 或本地计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="665cb-175">To create a loopback session, do not specify the **ComputerName** parameter or set its value to dot, localhost, or the name of the local computer.</span></span>

<span data-ttu-id="665cb-176">默认情况下，创建的环回会话具有网络令牌，该令牌提供的权限可能不足以对远程计算机进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="665cb-176">By default, loopback sessions are created that have a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="665cb-177">**EnableNetworkAccess** 参数仅在环回会话中有效。</span><span class="sxs-lookup"><span data-stu-id="665cb-177">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="665cb-178">如果在远程计算机上创建会话时指定 EnableNetworkAccess  参数，该命令将成功，但会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="665cb-178">If you specify the **EnableNetworkAccess** parameter when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="665cb-179">通过用于将会话凭据委派给其他计算机的 **CredSSP** 参数的 **Authentication** 值，你还可以在环回会话中进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="665cb-179">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="665cb-180">若要保护计算机免受恶意访问，断开连接的具有交互式令牌（使用 **EnableNetworkAccess** 参数创建）的环回会话只能通过创建该会话的计算机重新连接。</span><span class="sxs-lookup"><span data-stu-id="665cb-180">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="665cb-181">断开连接的使用 CredSSP 身份验证的会话可通过其他计算机重新连接。</span><span class="sxs-lookup"><span data-stu-id="665cb-181">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="665cb-182">有关详细信息，请参阅 `Disconnect-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="665cb-182">For more information, see the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="665cb-183">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="665cb-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="665cb-184">-Name</span><span class="sxs-lookup"><span data-stu-id="665cb-184">-Name</span></span>

<span data-ttu-id="665cb-185">指定工作流会话的友好名称。</span><span class="sxs-lookup"><span data-stu-id="665cb-185">Specifies a friendly name for the workflow session.</span></span> <span data-ttu-id="665cb-186">可以将该名称与其他 cmdlet （例如和）一起使用 `Get-PSSession` `Enter-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="665cb-186">You can use the name with other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="665cb-187">对于计算机或当前会话，该名称无需是唯一的。</span><span class="sxs-lookup"><span data-stu-id="665cb-187">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="665cb-188">-Port</span><span class="sxs-lookup"><span data-stu-id="665cb-188">-Port</span></span>

<span data-ttu-id="665cb-189">指定远程计算机上用于此连接的网络端口。</span><span class="sxs-lookup"><span data-stu-id="665cb-189">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="665cb-190">若要连接到一台远程计算机，则必须在该连接所用的端口上侦听远程计算机。</span><span class="sxs-lookup"><span data-stu-id="665cb-190">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="665cb-191">对于 HTTP) ，默认端口为 5985 (WinRM 端口5986， (HTTPS 的 WinRM 端口) 。</span><span class="sxs-lookup"><span data-stu-id="665cb-191">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="665cb-192">使用其他端口之前，必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="665cb-192">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="665cb-193">使用以下命令配置侦听器：</span><span class="sxs-lookup"><span data-stu-id="665cb-193">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="665cb-194">除非必要，否则不要使用 **Port** 参数。</span><span class="sxs-lookup"><span data-stu-id="665cb-194">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="665cb-195">命令中的端口设置适用于运行该命令的所有计算机或会话。</span><span class="sxs-lookup"><span data-stu-id="665cb-195">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="665cb-196">备用端口设置可能会阻止在所有计算机上运行该命令。</span><span class="sxs-lookup"><span data-stu-id="665cb-196">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="665cb-197">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="665cb-197">-SessionOption</span></span>

<span data-ttu-id="665cb-198">为该会话指定高级选项。</span><span class="sxs-lookup"><span data-stu-id="665cb-198">Specifies advanced options for the session.</span></span> <span data-ttu-id="665cb-199">输入一个 **SessionOption** 对象，例如使用 cmdlet 创建的对象 `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="665cb-199">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="665cb-200">选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。</span><span class="sxs-lookup"><span data-stu-id="665cb-200">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="665cb-201">否则，通过在会话配置中设置的选项创建默认值。</span><span class="sxs-lookup"><span data-stu-id="665cb-201">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="665cb-202">会话选项值优先于在 `$PSSessionOption` 首选项变量和会话配置中设置的会话的默认值。</span><span class="sxs-lookup"><span data-stu-id="665cb-202">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="665cb-203">但是，它们不优先于在会话配置中设置的最大值、配额或限制。</span><span class="sxs-lookup"><span data-stu-id="665cb-203">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="665cb-204">有关会话配置的详细信息，请参阅 [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="665cb-204">For more information about session configurations, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="665cb-205">有关会话选项（包括默认值）的说明，请参阅 `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="665cb-205">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="665cb-206">有关 `$PSSessionOption` 首选项变量的信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="665cb-206">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="665cb-207">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="665cb-207">-ThrottleLimit</span></span>

<span data-ttu-id="665cb-208">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="665cb-208">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="665cb-209">如果省略此参数或输入值 0 (零) ，则使用 **microsoft.powershellworkflow** 会话配置的默认值100。</span><span class="sxs-lookup"><span data-stu-id="665cb-209">If you omit this parameter or enter a value of 0 (zero), the default value for the **Microsoft.PowerShellWorkflow** session configuration, 100, is used.</span></span>

<span data-ttu-id="665cb-210">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="665cb-210">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="665cb-211">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="665cb-211">-UseSSL</span></span>

<span data-ttu-id="665cb-212">指示此 cmdlet 使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="665cb-212">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="665cb-213">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="665cb-213">By default, SSL is not used.</span></span>

<span data-ttu-id="665cb-214">WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="665cb-214">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="665cb-215">**UseSSL** 参数是一种额外的保护措施，它通过 HTTPS 连接而不是 HTTP 连接来发送数据。</span><span class="sxs-lookup"><span data-stu-id="665cb-215">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="665cb-216">如果指定此参数，但 SSL 在用于命令的端口上不可用，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="665cb-216">If you specify this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="665cb-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="665cb-217">CommonParameters</span></span>

<span data-ttu-id="665cb-218">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="665cb-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="665cb-219">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="665cb-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="665cb-220">输入</span><span class="sxs-lookup"><span data-stu-id="665cb-220">INPUTS</span></span>

### <span data-ttu-id="665cb-221">System.Management.Automation.Runspaces.PSSession[]、System.String</span><span class="sxs-lookup"><span data-stu-id="665cb-221">System.Management.Automation.Runspaces.PSSession[], System.String</span></span>

<span data-ttu-id="665cb-222">可以通过管道将会话或计算机名称传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="665cb-222">You can pipe a session or a computer name to this cmdlet.</span></span>

## <span data-ttu-id="665cb-223">输出</span><span class="sxs-lookup"><span data-stu-id="665cb-223">OUTPUTS</span></span>

### <span data-ttu-id="665cb-224">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="665cb-224">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="665cb-225">注释</span><span class="sxs-lookup"><span data-stu-id="665cb-225">NOTES</span></span>

<span data-ttu-id="665cb-226">`New-PSWorkflowSession`命令等效于以下命令：</span><span class="sxs-lookup"><span data-stu-id="665cb-226">A `New-PSWorkflowSession` command is equivalent to the following command:</span></span>

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## <span data-ttu-id="665cb-227">相关链接</span><span class="sxs-lookup"><span data-stu-id="665cb-227">RELATED LINKS</span></span>

[<span data-ttu-id="665cb-228">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="665cb-228">Disconnect-PSSession</span></span>](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[<span data-ttu-id="665cb-229">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="665cb-229">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="665cb-230">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="665cb-230">New-PSTransportOption</span></span>](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[<span data-ttu-id="665cb-231">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="665cb-231">Register-PSSessionConfiguration</span></span>](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[<span data-ttu-id="665cb-232">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="665cb-232">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="665cb-233">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="665cb-233">about_Session_Configurations</span></span>](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[<span data-ttu-id="665cb-234">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="665cb-234">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="665cb-235">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="665cb-235">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
