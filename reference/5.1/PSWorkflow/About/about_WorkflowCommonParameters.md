---
description: 本主题介绍对所有 Windows PowerShell 工作流命令有效的参数。 由于 Windows PowerShell 引擎会将它们添加到工作流，因此你可以在任何工作流上使用这些参数，并且这些参数会在你创作的工作流上自动启用。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflowcommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WorkflowCommonParameters
ms.openlocfilehash: c371666d4f58386848e7ef715b7c804dc1e8f28e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387781"
---
# <a name="about-workflowcommonparameters"></a><span data-ttu-id="aaa62-105">关于 WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="aaa62-105">About WorkflowCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="aaa62-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="aaa62-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="aaa62-107">本主题介绍对所有 Windows PowerShell 工作流命令有效的参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-107">This topic describes the parameters that are valid on all Windows PowerShell workflow commands.</span></span> <span data-ttu-id="aaa62-108">由于 Windows PowerShell 引擎会将它们添加到工作流，因此你可以在任何工作流上使用这些参数，并且这些参数会在你创作的工作流上自动启用。</span><span class="sxs-lookup"><span data-stu-id="aaa62-108">Because the Windows PowerShell engine adds them to workflows, you can use these parameters on any workflow and they are automatically enabled on the workflows that you author.</span></span>

## <a name="long-description"></a><span data-ttu-id="aaa62-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="aaa62-109">LONG DESCRIPTION</span></span>

<span data-ttu-id="aaa62-110">Windows PowerShell 工作流通用参数是一组可用于所有 Windows PowerShell 工作流和活动的 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-110">Windows PowerShell Workflow common parameters are a set of cmdlet parameters that you can use with all Windows PowerShell workflows and activities.</span></span> <span data-ttu-id="aaa62-111">它们是由 Windows PowerShell 工作流引擎添加的，而不是由工作流作者添加的，它们会自动提供工作流和活动。</span><span class="sxs-lookup"><span data-stu-id="aaa62-111">They are added by the Windows PowerShell Workflow engine, not by the workflow author, and they are automatically available on workflows and activities.</span></span> <span data-ttu-id="aaa62-112">但是，嵌套三个层次的工作流不支持任何通用参数，包括工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-112">However, workflows that are nested three levels deep do not support any common parameters, including workflow common parameters.</span></span>

<span data-ttu-id="aaa62-113">所有工作流参数均为可选且命名 (不是位置) 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-113">All workflow parameters are optional and named (not positional).</span></span> <span data-ttu-id="aaa62-114">它们不从管道中获取输入。</span><span class="sxs-lookup"><span data-stu-id="aaa62-114">They do not take input from the pipeline.</span></span>

<span data-ttu-id="aaa62-115">大多数工作流通用参数都有 PS 前缀，例如 `PSComputerName` 和 `PSCredential` 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-115">Most of the workflow common parameters have a PS prefix, such as `PSComputerName` and `PSCredential`.</span></span> <span data-ttu-id="aaa62-116">PS 前缀参数配置目标计算机的连接和执行环境，也称为 "远程节点"。</span><span class="sxs-lookup"><span data-stu-id="aaa62-116">The PS-prefixed parameters configure the connection and the execution environment for the target computers, also known as "remote nodes."</span></span>

<span data-ttu-id="aaa62-117">许多工作流常见参数（例如 `PSAllowRedirection` 和）的 `AsJob` 名称类似于 Windows PowerShell 远程处理和后台作业中使用的参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-117">Many of the workflow common parameters, such as `PSAllowRedirection` and `AsJob`, have names that are similar to parameters used in Windows PowerShell remoting and background jobs.</span></span> <span data-ttu-id="aaa62-118">这些参数的工作方式与名称类似的远程处理和作业参数的工作方式相同，因此你可以使用在远程处理和作业中开发的知识来管理工作流。</span><span class="sxs-lookup"><span data-stu-id="aaa62-118">These parameters work in the same way as the similarly-named remoting and job parameters, so you can use the knowledge that you developed in remoting and jobs to manage workflows.</span></span>

<span data-ttu-id="aaa62-119">工作流在 Windows PowerShell 3.0 中引入。</span><span class="sxs-lookup"><span data-stu-id="aaa62-119">Workflows are introduced in Windows PowerShell 3.0.</span></span>

### <a name="parameter-descriptions"></a><span data-ttu-id="aaa62-120">参数说明</span><span class="sxs-lookup"><span data-stu-id="aaa62-120">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="aaa62-121">本节介绍工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-121">This section describes the workflow common parameters.</span></span>

#### <a name="-asjob-switchparameter"></a><span data-ttu-id="aaa62-122">-AsJob \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="aaa62-122">-AsJob \<SwitchParameter\></span></span>

<span data-ttu-id="aaa62-123">将工作流作为工作流作业运行。</span><span class="sxs-lookup"><span data-stu-id="aaa62-123">Runs the workflow as a workflow job.</span></span> <span data-ttu-id="aaa62-124">工作流命令立即返回表示父作业的对象。</span><span class="sxs-lookup"><span data-stu-id="aaa62-124">The workflow command immediately returns an object that represents a parent job.</span></span> <span data-ttu-id="aaa62-125">父作业包含在每台目标计算机上运行的子作业。</span><span class="sxs-lookup"><span data-stu-id="aaa62-125">The parent job contains the child jobs that are running on each of the target computers.</span></span> <span data-ttu-id="aaa62-126">若要管理作业，请使用 Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aaa62-126">To manage the job, use the Job cmdlets.</span></span> <span data-ttu-id="aaa62-127">若要获取作业结果，请使用 [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-127">To get the job results, use [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job).</span></span>

#### <a name="-jobname-string"></a><span data-ttu-id="aaa62-128">-JobName \<String\></span><span class="sxs-lookup"><span data-stu-id="aaa62-128">-JobName \<String\></span></span>

<span data-ttu-id="aaa62-129">指定工作流作业的友好名称。</span><span class="sxs-lookup"><span data-stu-id="aaa62-129">Specifies a friendly name for the workflow job.</span></span> <span data-ttu-id="aaa62-130">默认情况下，作业将命名为“Job\<n\>”，其中 \<n\> 是一个序号。</span><span class="sxs-lookup"><span data-stu-id="aaa62-130">By default, jobs are named "Job\<n\>", where \<n\> is an ordinal number.</span></span>

<span data-ttu-id="aaa62-131">如果在工作流命令中使用 JobName 参数，则工作流将作为作业运行，并且工作流命令返回一个作业对象，即使未 `AsJob` 在该命令中包含参数也是如此。</span><span class="sxs-lookup"><span data-stu-id="aaa62-131">If you use the JobName parameter in a workflow command, the workflow is run as a job and the workflow command returns a job object, even if you do not include the `AsJob` parameter in the command.</span></span>

<span data-ttu-id="aaa62-132">有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-132">For more information about Windows PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

#### <a name="-psallowredirection-switchparameter"></a><span data-ttu-id="aaa62-133">-PSAllowRedirection \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="aaa62-133">-PSAllowRedirection \<SwitchParameter\></span></span>

<span data-ttu-id="aaa62-134">允许将连接重定向到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="aaa62-134">Allows redirection of the connection to the target computers.</span></span>

<span data-ttu-id="aaa62-135">使用 `PSConnectionURI` 参数时，远程目标将返回一个指令，以重定向到不同的 URI。</span><span class="sxs-lookup"><span data-stu-id="aaa62-135">When you use the `PSConnectionURI` parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="aaa62-136">默认情况下，Windows PowerShell 不会重定向连接，但你可以使用 `PSAllowRedirection` 参数来允许将连接重定向到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="aaa62-136">By default, Windows PowerShell does not redirect connections, but you can use the `PSAllowRedirection` parameter to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="aaa62-137">还可以通过设置 `MaximumConnectionRedirectionCount` `$PSSessionOption` 首选项变量的属性或的值的属性，限制重定向连接的次数 `MaximumConnectionRedirectionCount` `PSSessionOption parameter` 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-137">You can also limit the number of times that the connection is redirected by setting the `MaximumConnectionRedirectionCount` property of the `$PSSessionOption` preference variable, or the `MaximumConnectionRedirectionCount` property of the value of the `PSSessionOption parameter`.</span></span> <span data-ttu-id="aaa62-138">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="aaa62-138">The default value is 5.</span></span> <span data-ttu-id="aaa62-139">有关详细信息，请参阅参数的说明 `PSSessionOption` 和 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-139">For more information, see the description of the `PSSessionOption` parameter and [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

#### <a name="-psapplicationname-string"></a><span data-ttu-id="aaa62-140">-PSApplicationName \<String\></span><span class="sxs-lookup"><span data-stu-id="aaa62-140">-PSApplicationName \<String\></span></span>

<span data-ttu-id="aaa62-141">指定连接 URI 的应用程序名称段，该连接 URI 用于连接到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="aaa62-141">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="aaa62-142">当你未在命令中使用参数时，请使用此参数指定应用程序名称 `ConnectionURI` 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-142">Use this parameter to specify the application name when you are not using the `ConnectionURI` parameter in the command.</span></span>

<span data-ttu-id="aaa62-143">默认值为 `$PSSessionApplicationName` 本地计算机上首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-143">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="aaa62-144">如果未定义此首选项变量，则默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="aaa62-144">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="aaa62-145">该值适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="aaa62-145">This value is appropriate for most uses.</span></span> <span data-ttu-id="aaa62-146">有关详细信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-146">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="aaa62-147">WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。</span><span class="sxs-lookup"><span data-stu-id="aaa62-147">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="aaa62-148">此参数的值应与 `URLPrefix` 远程计算机上侦听器的属性的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="aaa62-148">The value of this parameter should match the value of the `URLPrefix` property of a listener on the remote computer.</span></span>

#### <a name="-psauthentication-authenticationmechanism"></a><span data-ttu-id="aaa62-149">-PSAuthentication \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="aaa62-149">-PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="aaa62-150">指定在连接到目标计算机时用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="aaa62-150">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span>

<span data-ttu-id="aaa62-151">有效值是：</span><span class="sxs-lookup"><span data-stu-id="aaa62-151">Valid values are:</span></span>

- <span data-ttu-id="aaa62-152">**默认**</span><span class="sxs-lookup"><span data-stu-id="aaa62-152">**Default**</span></span>
- <span data-ttu-id="aaa62-153">**基本**</span><span class="sxs-lookup"><span data-stu-id="aaa62-153">**Basic**</span></span>
- <span data-ttu-id="aaa62-154">**Credssp**</span><span class="sxs-lookup"><span data-stu-id="aaa62-154">**Credssp**</span></span>
- <span data-ttu-id="aaa62-155">摘要式</span><span class="sxs-lookup"><span data-stu-id="aaa62-155">**Digest**</span></span>
- <span data-ttu-id="aaa62-156">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="aaa62-156">**Kerberos**</span></span>
- <span data-ttu-id="aaa62-157">**沟通**</span><span class="sxs-lookup"><span data-stu-id="aaa62-157">**Negotiate**</span></span>
- <span data-ttu-id="aaa62-158">**NegotiateWithImplicitCredential**</span><span class="sxs-lookup"><span data-stu-id="aaa62-158">**NegotiateWithImplicitCredential**</span></span>

<span data-ttu-id="aaa62-159">默认值为 **Default** 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-159">The default value is **Default**.</span></span>

<span data-ttu-id="aaa62-160">有关此参数的值的信息，请参阅 `System.Management.Automation.Runspaces.AuthenticationMechanism` POWERSHELL SDK 中枚举的说明。</span><span class="sxs-lookup"><span data-stu-id="aaa62-160">For information about the values of this parameter, see the description of the `System.Management.Automation.Runspaces.AuthenticationMechanism` enumeration in the PowerShell SDK.</span></span>

> [!WARNING]
> <span data-ttu-id="aaa62-161">在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。</span><span class="sxs-lookup"><span data-stu-id="aaa62-161">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="aaa62-162">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="aaa62-162">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="aaa62-163">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="aaa62-163">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="-psauthenticationlevel-authenticationlevel"></a><span data-ttu-id="aaa62-164">-PSAuthenticationLevel \<AuthenticationLevel\></span><span class="sxs-lookup"><span data-stu-id="aaa62-164">-PSAuthenticationLevel \<AuthenticationLevel\></span></span>

<span data-ttu-id="aaa62-165">指定与目标计算机的连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="aaa62-165">Specifies the authentication level for the connections to the target computers.</span></span>
<span data-ttu-id="aaa62-166">默认值为 **Default** 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-166">The default value is **Default**.</span></span>

<span data-ttu-id="aaa62-167">有效值是：</span><span class="sxs-lookup"><span data-stu-id="aaa62-167">Valid values are:</span></span>

|<span data-ttu-id="aaa62-168">名称</span><span class="sxs-lookup"><span data-stu-id="aaa62-168">Name</span></span> |<span data-ttu-id="aaa62-169">说明</span><span class="sxs-lookup"><span data-stu-id="aaa62-169">Description</span></span> |
|---------|---------|
|<span data-ttu-id="aaa62-170">**不变**</span><span class="sxs-lookup"><span data-stu-id="aaa62-170">**Unchanged**</span></span> | <span data-ttu-id="aaa62-171">身份验证级别与前一个命令相同。</span><span class="sxs-lookup"><span data-stu-id="aaa62-171">The authentication level is the same as the previous command.</span></span> |
|<span data-ttu-id="aaa62-172">**默认**</span><span class="sxs-lookup"><span data-stu-id="aaa62-172">**Default**</span></span> | <span data-ttu-id="aaa62-173">Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-173">Windows Authentication.</span></span> |
|<span data-ttu-id="aaa62-174">**无**</span><span class="sxs-lookup"><span data-stu-id="aaa62-174">**None**</span></span> | <span data-ttu-id="aaa62-175">没有 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-175">No COM authentication.</span></span>   |
|<span data-ttu-id="aaa62-176">**“连接”**</span><span class="sxs-lookup"><span data-stu-id="aaa62-176">**Connect**</span></span> | <span data-ttu-id="aaa62-177">连接级的 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-177">Connect-level COM authentication.</span></span>|
|<span data-ttu-id="aaa62-178">**调用**</span><span class="sxs-lookup"><span data-stu-id="aaa62-178">**Call**</span></span> | <span data-ttu-id="aaa62-179">调用级的 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-179">Call-level COM authentication.</span></span>   |
|<span data-ttu-id="aaa62-180">**数据包**</span><span class="sxs-lookup"><span data-stu-id="aaa62-180">**Packet**</span></span> | <span data-ttu-id="aaa62-181">数据包级的 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-181">Packet-level COM authentication.</span></span>|
|<span data-ttu-id="aaa62-182">**PacketIntegrity**</span><span class="sxs-lookup"><span data-stu-id="aaa62-182">**PacketIntegrity**</span></span> | <span data-ttu-id="aaa62-183">数据包完整性级别的 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-183">Packet Integrity-level COM authentication.</span></span>  |
|<span data-ttu-id="aaa62-184">**PacketPrivacy**</span><span class="sxs-lookup"><span data-stu-id="aaa62-184">**PacketPrivacy**</span></span> | <span data-ttu-id="aaa62-185">数据包保密性级别的 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aaa62-185">Packet Privacy-level COM authentication.</span></span> |

#### <a name="-pscertificatethumbprint-string"></a><span data-ttu-id="aaa62-186">-PSCertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="aaa62-186">-PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="aaa62-187">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-187">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="aaa62-188">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="aaa62-188">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="aaa62-189">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="aaa62-189">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="aaa62-190">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="aaa62-190">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="aaa62-191">若要获取证书，请使用 [Get 项](xref:Microsoft.PowerShell.Management.Get-Item) 或 [get-childitem] (。/../Microsoft.PowerShell.Management/Get-Childitem.md) Windows PowerShell Cert：驱动器中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aaa62-191">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem] (../../Microsoft.PowerShell.Management/Get-Childitem.md) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="-pscomputername-string"></a><span data-ttu-id="aaa62-192">-PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="aaa62-192">-PSComputerName \<String[]\></span></span>

<span data-ttu-id="aaa62-193">指定作为工作流目标节点的计算机的列表。</span><span class="sxs-lookup"><span data-stu-id="aaa62-193">Specifies the list of computers that are the target nodes of the workflow.</span></span>
<span data-ttu-id="aaa62-194">工作流中的命令或活动在使用此参数指定的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="aaa62-194">Commands or activities in a workflow are run on the computers that are specified by using this parameter.</span></span> <span data-ttu-id="aaa62-195">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="aaa62-195">The default is the local computer.</span></span>

<span data-ttu-id="aaa62-196">在以逗号分隔的列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="aaa62-196">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="aaa62-197">若要指定本地计算机，请键入该计算机名称、“localhost”或句点 (.)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-197">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="aaa62-198">若要将本地计算机包含在参数的值中 `PSComputerName` ，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="aaa62-198">To include the local computer in the value of the `PSComputerName` parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="aaa62-199">如果从命令中省略此参数，或值为 `$null` 或空字符串，则工作流目标为本地计算机，并且不使用 Windows PowerShell 远程处理来运行命令。</span><span class="sxs-lookup"><span data-stu-id="aaa62-199">If this parameter is omitted from the command, or it value is `$null` or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="aaa62-200">若要在参数的值中使用 IP 地址 `ComputerName` ，该命令必须包含 `PSCredential` 参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-200">To use an IP address in the value of the `ComputerName` parameter, the command must include the `PSCredential` parameter.</span></span> <span data-ttu-id="aaa62-201">此外，必须为计算机配置 HTTPS 传输，或者必须在本地计算机上的 WinRM TrustedHosts 列表中包含远程计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="aaa62-201">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="aaa62-202">有关将计算机名称添加到 TrustedHosts 列表的说明，请参阅 [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)中的 *"如何将计算机添加到受信任的主机列表中"* 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-202">For instructions for adding a computer name to the TrustedHosts list, see *"How to Add a Computer to the Trusted Host List"* in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="-psconfigurationname-string"></a><span data-ttu-id="aaa62-203">-PSConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="aaa62-203">-PSConfigurationName \<String\></span></span>

<span data-ttu-id="aaa62-204">指定用于在目标计算机上配置会话的会话配置。</span><span class="sxs-lookup"><span data-stu-id="aaa62-204">Specifies the session configurations that are used to configure sessions on the target computers.</span></span> <span data-ttu-id="aaa62-205">在目标计算机上输入会话配置， (不是工作流服务器计算机) 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-205">Enter a session configuration on the target computers (not the workflow server computer).</span></span> <span data-ttu-id="aaa62-206">默认值为 `Microsoft.PowerShell.Workflow`。</span><span class="sxs-lookup"><span data-stu-id="aaa62-206">The default is `Microsoft.PowerShell.Workflow`.</span></span>

#### <a name="-psconnectionretrycount-uint"></a><span data-ttu-id="aaa62-207">-PSConnectionRetryCount \<UInt\></span><span class="sxs-lookup"><span data-stu-id="aaa62-207">-PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="aaa62-208">指定第一次连接尝试失败时连接到每台目标计算机的最大尝试次数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-208">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="aaa62-209">输入介于1到 4294967295 (UInt) 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="aaa62-209">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="aaa62-210">默认值为零 (0) 表示不重试尝试。</span><span class="sxs-lookup"><span data-stu-id="aaa62-210">The default value, zero (0), represents no retry attempts.</span></span>

#### <a name="-psconnectionretryintervalsec-uint"></a><span data-ttu-id="aaa62-211">-PSConnectionRetryIntervalSec \<UInt\></span><span class="sxs-lookup"><span data-stu-id="aaa62-211">-PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="aaa62-212">指定连接重试尝试之间的延迟（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="aaa62-212">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="aaa62-213">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-213">The default value is zero (0).</span></span> <span data-ttu-id="aaa62-214">仅当 PSConnectionRetryCount 的值为1时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="aaa62-214">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span>

#### <a name="-psconnectionuri-systemuri"></a><span data-ttu-id="aaa62-215">-PSConnectionURI \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="aaa62-215">-PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="aaa62-216">指定 (URI) 的统一资源标识符，该标识符定义目标计算机上的工作流的连接终结点。</span><span class="sxs-lookup"><span data-stu-id="aaa62-216">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the workflow on the target computer.</span></span> <span data-ttu-id="aaa62-217">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="aaa62-217">The URI must be fully qualified.</span></span>

<span data-ttu-id="aaa62-218">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="aaa62-218">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="aaa62-219">默认值为 `http://localhost:5985/WSMAN`。</span><span class="sxs-lookup"><span data-stu-id="aaa62-219">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="aaa62-220">如果未指定 `PSConnectionURI` ，则可以使用 `PSUseSSL` 、 `PSComputerName` 、 `PSPort` 和 `PSApplicationName` 参数指定 `PSConnectionURI` 值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-220">If you do not specify a `PSConnectionURI`, you can use the `PSUseSSL`, `PSComputerName`, `PSPort`, and `PSApplicationName` parameters to specify the `PSConnectionURI` values.</span></span>

<span data-ttu-id="aaa62-221">URI 的传输段的有效值为 **HTTP** 和 **HTTPS** 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-221">Valid values for the Transport segment of the URI are **HTTP** and **HTTPS**.</span></span>
<span data-ttu-id="aaa62-222">如果使用 Transport 段指定连接 URI，但不指定端口，将使用以下标准端口来创建会话：80 用于 HTTP，443 用于 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="aaa62-222">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="aaa62-223">若要使用 Windows PowerShell 远程处理的默认端口，请指定 HTTP 端口 5985 或 HTTPS 端口 5986。</span><span class="sxs-lookup"><span data-stu-id="aaa62-223">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="-pscredential-pscredential"></a><span data-ttu-id="aaa62-224">-PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="aaa62-224">-PSCredential \<PSCredential\></span></span>

<span data-ttu-id="aaa62-225">指定有权在目标计算机上运行工作流的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aaa62-225">Specifies a user account that has permission to run a workflow on the target computer.</span></span> <span data-ttu-id="aaa62-226">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="aaa62-226">The default is the current user.</span></span> <span data-ttu-id="aaa62-227">仅当命令中包括 PSComputerName 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="aaa62-227">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span>

<span data-ttu-id="aaa62-228">键入用户名，如 "User01" 或 "Domain01\User01"，或输入一个包含对象的变量 `PSCredential` ，如 cmdlet 返回的一个对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-228">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a `PSCredential` object, such as one that the `Get-Credential` cmdlet returns.</span></span> <span data-ttu-id="aaa62-229">如果仅输入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="aaa62-229">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="-pselapsedtimeoutsec-uint32"></a><span data-ttu-id="aaa62-230">-PSElapsedTimeoutSec \<UInt32\></span><span class="sxs-lookup"><span data-stu-id="aaa62-230">-PSElapsedTimeoutSec \<UInt32\></span></span>

<span data-ttu-id="aaa62-231">确定在系统中维护工作流和所有相关资源的时间长度。</span><span class="sxs-lookup"><span data-stu-id="aaa62-231">Determines how long the workflow and all related resources are maintained in the system.</span></span> <span data-ttu-id="aaa62-232">当超时到期时，即使工作流仍在进行处理，也会将其删除。</span><span class="sxs-lookup"><span data-stu-id="aaa62-232">When the timeout expires, the workflow is deleted, even if it is still processing.</span></span> <span data-ttu-id="aaa62-233">输入一个介于10和4294967295之间的值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-233">Enter a value between 10 and 4,294,967,295.</span></span> <span data-ttu-id="aaa62-234">默认值 0 (零) ，表示没有超时。</span><span class="sxs-lookup"><span data-stu-id="aaa62-234">The default value, 0 (zero), means that there is no elapsed timeout.</span></span>

#### <a name="-psparametercollection-hashtable"></a><span data-ttu-id="aaa62-235">-PSParameterCollection \<Hashtable[]\></span><span class="sxs-lookup"><span data-stu-id="aaa62-235">-PSParameterCollection \<Hashtable[]\></span></span>

<span data-ttu-id="aaa62-236">为不同的目标计算机指定不同的工作流公用参数值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-236">Specifies different workflow common parameter values for different target computers.</span></span>

<span data-ttu-id="aaa62-237">输入一个以逗号分隔的哈希表列表，其中每个目标计算机有一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="aaa62-237">Enter a comma-separated list of hash tables with one hash table for each target computer.</span></span> <span data-ttu-id="aaa62-238">在每个哈希表中，第一个键为 `PSComputerName` ，其值是目标计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="aaa62-238">In each hash table, the first key is `PSComputerName` and its value is the name of the target computer.</span></span> <span data-ttu-id="aaa62-239">计算机名称中允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aaa62-239">Wildcard characters are permitted in the computer name.</span></span> <span data-ttu-id="aaa62-240">对于哈希表中的剩余键，键是参数名称，值是参数值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-240">For the remaining keys in the hash table, the key is the parameter name and the value is the parameter value.</span></span>

<span data-ttu-id="aaa62-241">例如：</span><span class="sxs-lookup"><span data-stu-id="aaa62-241">For example:</span></span>

```powershell
-PSParameterCollection @{PSComputerName="*"; PSElapsedTimeoutSec=20},
@{PSComputerName="Server02"},
@{PSComputerName="Server03"},
@{PSComputerName="Server01"; PSElapsedTimeoutSec=10}
```

<span data-ttu-id="aaa62-242">在上面的示例中，所有连接的默认 PSElapsedTimeoutSec 均为20秒，Server01 除外，它通过指定其自己的超时值10秒，来覆盖默认值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-242">In the above example, all connections will have a default PSElapsedTimeoutSec of 20 seconds, except for Server01 which overrides the default value by specifying its own timeout of 10 seconds.</span></span>

#### <a name="-pspersist-boolean"></a><span data-ttu-id="aaa62-243">-PSPersist \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="aaa62-243">-PSPersist \<Boolean\></span></span>

<span data-ttu-id="aaa62-244">除了工作流中指定的任何检查点之外，还向工作流添加检查点。</span><span class="sxs-lookup"><span data-stu-id="aaa62-244">Adds checkpoints to the workflow, in addition to any checkpoints that are specified in the workflow.</span></span>

<span data-ttu-id="aaa62-245">此参数无法禁止工作流中的检查点，如使用 `PSPersist` 活动通用参数、 `Checkpoint-Workflow` 活动或变量指定的检查点 `$PSPersistPreference` 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-245">This parameter cannot suppress the checkpoints in a workflow, such as those specified by using the `PSPersist` activity common parameter, the `Checkpoint-Workflow` activity, or the `$PSPersistPreference` variable.</span></span>

<span data-ttu-id="aaa62-246">"检查点" 或 "持久性点" 是工作流状态和工作流运行时捕获的数据的快照，并保存到磁盘或 SQL 数据库中的持久性存储中。</span><span class="sxs-lookup"><span data-stu-id="aaa62-246">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk or in a SQL database.</span></span> <span data-ttu-id="aaa62-247">Windows PowerShell 工作流使用保存的数据从最后一个暂留点恢复挂起或中断的工作流，而不是重新启动工作流。</span><span class="sxs-lookup"><span data-stu-id="aaa62-247">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="aaa62-248">有效值：</span><span class="sxs-lookup"><span data-stu-id="aaa62-248">Valid values:</span></span>

- <span data-ttu-id="aaa62-249"> ( *默认值* ) 如果省略此参数，则除了工作流中指定的任何检查点之外，还会在工作流的开头和末尾添加一个检查点。</span><span class="sxs-lookup"><span data-stu-id="aaa62-249">( *Default* ) If you omit this parameter, a checkpoint is added to the beginning and end of the workflow, in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="aaa62-250">`$True`.</span><span class="sxs-lookup"><span data-stu-id="aaa62-250">`$True`.</span></span> <span data-ttu-id="aaa62-251">除了工作流中指定的任何检查点，还在工作流的开始和结束以及每个活动之后添加一个检查点。</span><span class="sxs-lookup"><span data-stu-id="aaa62-251">Adds a checkpoint to the beginning and end of the workflow and a checkpoint after each activity, in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="aaa62-252">`$False`.</span><span class="sxs-lookup"><span data-stu-id="aaa62-252">`$False`.</span></span> <span data-ttu-id="aaa62-253">不添加任何检查点。</span><span class="sxs-lookup"><span data-stu-id="aaa62-253">No checkpoints are added.</span></span> <span data-ttu-id="aaa62-254">仅在工作流中指定了检查点。</span><span class="sxs-lookup"><span data-stu-id="aaa62-254">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="-psport-int32"></a><span data-ttu-id="aaa62-255">-PSPort \<Int32\></span><span class="sxs-lookup"><span data-stu-id="aaa62-255">-PSPort \<Int32\></span></span>

<span data-ttu-id="aaa62-256">指定目标计算机上的网络端口。</span><span class="sxs-lookup"><span data-stu-id="aaa62-256">Specifies the network port on the target computers.</span></span> <span data-ttu-id="aaa62-257">默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。</span><span class="sxs-lookup"><span data-stu-id="aaa62-257">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="aaa62-258">请勿使用 PSPort 参数，除非你必须这样做。</span><span class="sxs-lookup"><span data-stu-id="aaa62-258">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="aaa62-259">命令中设置的端口适用于运行该命令的所有计算机或会话。</span><span class="sxs-lookup"><span data-stu-id="aaa62-259">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="aaa62-260">备用端口设置可能会阻止在所有计算机上运行该命令。</span><span class="sxs-lookup"><span data-stu-id="aaa62-260">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="aaa62-261">使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="aaa62-261">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="-psprivatemetadata-hashtable"></a><span data-ttu-id="aaa62-262">-PSPrivateMetadata \<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="aaa62-262">-PSPrivateMetadata \<Hashtable\></span></span>

<span data-ttu-id="aaa62-263">向工作流作业提供自定义信息。</span><span class="sxs-lookup"><span data-stu-id="aaa62-263">Provides customized information to workflow jobs.</span></span> <span data-ttu-id="aaa62-264">输入一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="aaa62-264">Enter a hash table.</span></span> <span data-ttu-id="aaa62-265">为每个工作流自定义键和值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-265">The keys and values are customized for each workflow.</span></span> <span data-ttu-id="aaa62-266">有关工作流的专用元数据的信息，请参阅工作流的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aaa62-266">For information about the private metadata of a workflow, see the help topic for the workflow.</span></span>

<span data-ttu-id="aaa62-267">Windows PowerShell 工作流引擎不处理此参数。</span><span class="sxs-lookup"><span data-stu-id="aaa62-267">This parameter is not processed by the Windows PowerShell Workflow engine.</span></span>
<span data-ttu-id="aaa62-268">相反，引擎会将哈希表直接传递到工作流。</span><span class="sxs-lookup"><span data-stu-id="aaa62-268">Instead, the engine passes the hash table directly to the workflow.</span></span>

#### <a name="-psrunningtimeoutsec-uint32"></a><span data-ttu-id="aaa62-269">-PSRunningTimeoutSec \<UInt32\></span><span class="sxs-lookup"><span data-stu-id="aaa62-269">-PSRunningTimeoutSec \<UInt32\></span></span>

<span data-ttu-id="aaa62-270">指定工作流的运行时间（以秒为单位），不包括任何挂起工作流的时间。</span><span class="sxs-lookup"><span data-stu-id="aaa62-270">Specifies the running time of the workflow in seconds, excluding any time that the workflow is suspended.</span></span> <span data-ttu-id="aaa62-271">如果工作流在时间到期时未完成，则 Windows PowerShell 工作流引擎会强行停止执行工作流。</span><span class="sxs-lookup"><span data-stu-id="aaa62-271">If workflow execution is not complete when the time expires, the Windows PowerShell Workflow engine forcibly stops the execution of the workflow.</span></span>

#### <a name="-pssessionoption-pssessionoption"></a><span data-ttu-id="aaa62-272">-PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="aaa62-272">-PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="aaa62-273">为目标计算机的会话设置高级选项。</span><span class="sxs-lookup"><span data-stu-id="aaa62-273">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="aaa62-274">输入一个 `PSSessionOption` 对象，如使用 cmdlet 创建的对象 `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-274">Enter a `PSSessionOption` object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="aaa62-275">会话选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。</span><span class="sxs-lookup"><span data-stu-id="aaa62-275">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="aaa62-276">否则，会话将使用在会话配置中指定的值。</span><span class="sxs-lookup"><span data-stu-id="aaa62-276">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="aaa62-277">有关会话选项（包括默认值）的说明，请参阅 cmdlet 的帮助主题 `New-PSSessionOption` (。/../Microsoft.PowerShell.Core/New-PSSessionOption.md) 。</span><span class="sxs-lookup"><span data-stu-id="aaa62-277">For a description of the session options, including the default values, see the help topic for the `New-PSSessionOption` cmdlet (../../Microsoft.PowerShell.Core/New-PSSessionOption.md).</span></span> <span data-ttu-id="aaa62-278">有关 `$PSSessionOption` 首选项变量的信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa62-278">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="-psusessl-switchparameter"></a><span data-ttu-id="aaa62-279">-PSUseSSL \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="aaa62-279">-PSUseSSL \<SwitchParameter\></span></span>

<span data-ttu-id="aaa62-280">使用安全套接字层 (SSL) 协议建立与目标计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="aaa62-280">Uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="aaa62-281">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="aaa62-281">By default, SSL is not used.</span></span>

<span data-ttu-id="aaa62-282">WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="aaa62-282">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="aaa62-283">UseSSL 是一种额外的保护措施，它通过 HTTPS 而不是 HTTP 来发送数据。</span><span class="sxs-lookup"><span data-stu-id="aaa62-283">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="aaa62-284">如果你使用此参数，但 SSL 在用于此命令的端口上不可用，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="aaa62-284">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaa62-285">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa62-285">SEE ALSO</span></span>

- [<span data-ttu-id="aaa62-286">about_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="aaa62-286">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)
- [<span data-ttu-id="aaa62-287">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="aaa62-287">about_Workflows</span></span>](about_Workflows.md)
- [<span data-ttu-id="aaa62-288">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="aaa62-288">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)
- [<span data-ttu-id="aaa62-289">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="aaa62-289">New-PSWorkflowExecutionOption</span></span>](xref:PSWorkflow.New-PSWorkflowExecutionOption)
- [<span data-ttu-id="aaa62-290">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="aaa62-290">New-PSWorkflowSession</span></span>](xref:PSWorkflow.New-PSWorkflowSession)
