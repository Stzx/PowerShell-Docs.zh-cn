---
ms.date: 05/14/2020
keywords: powershell,cmdlet
title: 在 PowerShell 远程处理中形成第二个跃点
ms.openlocfilehash: 3a9db11726d4c02dc69e52c45da304f7422def39
ms.sourcegitcommit: 843756c8277e7afb874867703963248abc8a6c91
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83439370"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="7b04b-103">在 PowerShell 远程处理中形成第二个跃点</span><span class="sxs-lookup"><span data-stu-id="7b04b-103">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="7b04b-104">“第二个跃点问题”是指如下所示的情况：</span><span class="sxs-lookup"><span data-stu-id="7b04b-104">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="7b04b-105">已登录到 _ServerA_。</span><span class="sxs-lookup"><span data-stu-id="7b04b-105">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="7b04b-106">在 _ServerA_ 中，启动远程 PowerShell 会话，以连接到 _ServerB_。</span><span class="sxs-lookup"><span data-stu-id="7b04b-106">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="7b04b-107">通过 PowerShell 远程处理会话在 _ServerB_ 上运行的命令尝试访问 _ServerC_ 上的资源。</span><span class="sxs-lookup"><span data-stu-id="7b04b-107">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="7b04b-108">已拒绝访问 _ServerC_ 上的资源，因为用于创建 PowerShell 远程处理会话的凭据未从 _ServerB_ 传递到 _ServerC_。</span><span class="sxs-lookup"><span data-stu-id="7b04b-108">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="7b04b-109">有几种方法可以解决此问题：</span><span class="sxs-lookup"><span data-stu-id="7b04b-109">There are several ways to address this problem.</span></span> <span data-ttu-id="7b04b-110">下表按优先级列出了方法。</span><span class="sxs-lookup"><span data-stu-id="7b04b-110">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="7b04b-111">配置</span><span class="sxs-lookup"><span data-stu-id="7b04b-111">Configuration</span></span>                       |                                  <span data-ttu-id="7b04b-112">注意</span><span class="sxs-lookup"><span data-stu-id="7b04b-112">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="7b04b-113">CredSSP</span><span class="sxs-lookup"><span data-stu-id="7b04b-113">CredSSP</span></span>                                                  | <span data-ttu-id="7b04b-114">在易用性和安全性之间达到平衡</span><span class="sxs-lookup"><span data-stu-id="7b04b-114">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="7b04b-115">基于资源的 Kerberos 约束委派</span><span class="sxs-lookup"><span data-stu-id="7b04b-115">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="7b04b-116">增强安全性并简化配置</span><span class="sxs-lookup"><span data-stu-id="7b04b-116">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="7b04b-117">Kerberos 约束委派</span><span class="sxs-lookup"><span data-stu-id="7b04b-117">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="7b04b-118">高安全性，但需要域管理员</span><span class="sxs-lookup"><span data-stu-id="7b04b-118">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="7b04b-119">Kerberos 委派（非约束）</span><span class="sxs-lookup"><span data-stu-id="7b04b-119">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="7b04b-120">不推荐</span><span class="sxs-lookup"><span data-stu-id="7b04b-120">Not recommended</span></span>                                                        |
| <span data-ttu-id="7b04b-121">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="7b04b-121">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="7b04b-122">可提供最佳安全性，但需要更详细的配置</span><span class="sxs-lookup"><span data-stu-id="7b04b-122">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="7b04b-123">使用 RunAs 的 PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b04b-123">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="7b04b-124">配置更简单，但需要管理凭据</span><span class="sxs-lookup"><span data-stu-id="7b04b-124">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="7b04b-125">在 `Invoke-Command` 脚本块内传递凭据</span><span class="sxs-lookup"><span data-stu-id="7b04b-125">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="7b04b-126">最易操作，但必须提供凭据</span><span class="sxs-lookup"><span data-stu-id="7b04b-126">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="7b04b-127">CredSSP</span><span class="sxs-lookup"><span data-stu-id="7b04b-127">CredSSP</span></span>

<span data-ttu-id="7b04b-128">可以使用[凭据安全支持提供程序(CredSSP)][credssp] 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7b04b-128">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="7b04b-129">CredSSP 会将凭据缓存在远程服务器 (_ServerB_) 上，因此使用它会给你带来凭据被盗攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="7b04b-129">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="7b04b-130">如果远程计算机被攻破，攻击者将有权访问用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="7b04b-130">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="7b04b-131">默认情况下，CredSSP 在客户端和服务器计算机上都处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7b04b-131">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="7b04b-132">应该仅在最受信任的环境中启用 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="7b04b-132">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="7b04b-133">例如，连接到域控制器的域管理员，因为域控制器是高度可信任的。</span><span class="sxs-lookup"><span data-stu-id="7b04b-133">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="7b04b-134">若要详细了解在使用 CredSSP 进行 PowerShell 远程处理时需要注意的安全问题，请参阅[非蓄意破坏：当心 CredSSP][beware]。</span><span class="sxs-lookup"><span data-stu-id="7b04b-134">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="7b04b-135">有关凭据被盗攻击的详细信息，请参阅[缓解哈希传递 (PtH) 攻击和其他凭据被盗][pth]。</span><span class="sxs-lookup"><span data-stu-id="7b04b-135">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="7b04b-136">有关如何启用和使用 CredSSP 进行 PowerShell 远程处理的示例，请参阅[使用 CredSSP 启用 PowerShell“第二个跃点”功能][credssp-psblog]。</span><span class="sxs-lookup"><span data-stu-id="7b04b-136">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="7b04b-137">**优点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-137">**Pros**</span></span>

- <span data-ttu-id="7b04b-138">它适用于运行 Windows Server 2008 或更高版本的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="7b04b-138">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="7b04b-139">**缺点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-139">**Cons**</span></span>

- <span data-ttu-id="7b04b-140">可能会造成安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="7b04b-140">Has security vulnerabilities.</span></span>
- <span data-ttu-id="7b04b-141">需要客户端和服务器角色的配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-141">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="7b04b-142">不适用于受保护的用户组。</span><span class="sxs-lookup"><span data-stu-id="7b04b-142">Does not work with the Protected Users group.</span></span> <span data-ttu-id="7b04b-143">有关详细信息，请参阅[受保护的用户安全组][protected-users]。</span><span class="sxs-lookup"><span data-stu-id="7b04b-143">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="7b04b-144">Kerberos 约束委派</span><span class="sxs-lookup"><span data-stu-id="7b04b-144">Kerberos constrained delegation</span></span>

<span data-ttu-id="7b04b-145">可以使用旧的约束委派（而非基于资源的委派）形成第二个跃点。</span><span class="sxs-lookup"><span data-stu-id="7b04b-145">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="7b04b-146">“使用任何身份验证协议”选项配置 Kerberos 约束委派以允许协议转换。</span><span class="sxs-lookup"><span data-stu-id="7b04b-146">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="7b04b-147">**优点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-147">**Pros**</span></span>

- <span data-ttu-id="7b04b-148">无需特殊编码</span><span class="sxs-lookup"><span data-stu-id="7b04b-148">Requires no special coding</span></span>
- <span data-ttu-id="7b04b-149">不存储凭据。</span><span class="sxs-lookup"><span data-stu-id="7b04b-149">Credentials are not stored.</span></span>

<span data-ttu-id="7b04b-150">**缺点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-150">**Cons**</span></span>

- <span data-ttu-id="7b04b-151">不支持 WinRM 的第二个跃点。</span><span class="sxs-lookup"><span data-stu-id="7b04b-151">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="7b04b-152">需要域管理员访问权限才能配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-152">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="7b04b-153">必须对远程服务器 (ServerB) 的 Active Directory 对象进行配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-153">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="7b04b-154">限于一个域。</span><span class="sxs-lookup"><span data-stu-id="7b04b-154">Limited to one domain.</span></span> <span data-ttu-id="7b04b-155">不能跨域或林。</span><span class="sxs-lookup"><span data-stu-id="7b04b-155">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="7b04b-156">需要权限才能更新对象和服务主体名称 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="7b04b-156">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="7b04b-157">ServerB 可代表用户获取针对 ServerC 的 Kerberos 票证，而不需用户干预 。</span><span class="sxs-lookup"><span data-stu-id="7b04b-157">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="7b04b-158">无法委派具有“敏感帐户，不能被委派”属性集的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="7b04b-158">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="7b04b-159">有关详细信息，请参阅[安全聚焦：对特权帐户分析“敏感帐户，不能被委派”][blog]和 [Kerberos 身份验证工具和设置][ktools]。</span><span class="sxs-lookup"><span data-stu-id="7b04b-159">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="7b04b-160">基于资源的 Kerberos 约束委派</span><span class="sxs-lookup"><span data-stu-id="7b04b-160">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="7b04b-161">通过使用（Windows Server 2012 中引入的）基于资源的 Kerberos 约束委派，在资源驻留的服务器对象上配置凭据委派。</span><span class="sxs-lookup"><span data-stu-id="7b04b-161">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="7b04b-162">在上述第二个跃点场景中，配置 ServerC 以指定从何处接受委派凭据。</span><span class="sxs-lookup"><span data-stu-id="7b04b-162">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="7b04b-163">**优点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-163">**Pros**</span></span>

- <span data-ttu-id="7b04b-164">不存储凭据。</span><span class="sxs-lookup"><span data-stu-id="7b04b-164">Credentials are not stored.</span></span>
- <span data-ttu-id="7b04b-165">已使用 PowerShell cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-165">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="7b04b-166">无需特殊编码。</span><span class="sxs-lookup"><span data-stu-id="7b04b-166">No special coding required.</span></span>
- <span data-ttu-id="7b04b-167">无需域管理员访问权限就能配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-167">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="7b04b-168">可跨域和林使用。</span><span class="sxs-lookup"><span data-stu-id="7b04b-168">Works across domains and forests.</span></span>

<span data-ttu-id="7b04b-169">**缺点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-169">**Cons**</span></span>

- <span data-ttu-id="7b04b-170">要求 Windows Server 2012 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7b04b-170">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="7b04b-171">不支持 WinRM 的第二个跃点。</span><span class="sxs-lookup"><span data-stu-id="7b04b-171">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="7b04b-172">需要权限才能更新对象和服务主体名称 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="7b04b-172">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="7b04b-173">无法委派具有“敏感帐户，不能被委派”属性集的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="7b04b-173">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="7b04b-174">有关详细信息，请参阅[安全聚焦：对特权帐户分析“敏感帐户，不能被委派”][blog]和 [Kerberos 身份验证工具和设置][ktools]。</span><span class="sxs-lookup"><span data-stu-id="7b04b-174">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="7b04b-175">示例</span><span class="sxs-lookup"><span data-stu-id="7b04b-175">Example</span></span>

<span data-ttu-id="7b04b-176">让我们看看 PowerShell 示例，它在 ServerC 上配置基于资源的约束委派，以允许来自 ServerB 的委派凭据 。</span><span class="sxs-lookup"><span data-stu-id="7b04b-176">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="7b04b-177">此示例假定所有服务器都运行 Windows Server 2012 或更高版本，并且任一服务器所属的每个域具有至少一个 Windows Server 2012 域控制器。</span><span class="sxs-lookup"><span data-stu-id="7b04b-177">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="7b04b-178">在配置约束委派前，必须先添加 `RSAT-AD-PowerShell` 功能以安装 Active Directory PowerShell 模块，然后将该模块导入会话：</span><span class="sxs-lookup"><span data-stu-id="7b04b-178">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="7b04b-179">现在多个可用的 cmdlet 具有 **PrincipalsAllowedToDelegateToAccount** 参数：</span><span class="sxs-lookup"><span data-stu-id="7b04b-179">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

<span data-ttu-id="7b04b-180">PrincipalsAllowedToDelegateToAccount 参数可设置 Active Directory 对象属性 msDS-AllowedToActOnBehalfOfOtherIdentity，其中包含一份访问控制列表 (ACL)，指定了哪些帐户有权向关联帐户委派凭据（在本示例中，该帐户为 ServerA 的计算机帐户） 。</span><span class="sxs-lookup"><span data-stu-id="7b04b-180">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_).</span></span>

<span data-ttu-id="7b04b-181">现在，我们来设置用于表示服务器的变量：</span><span class="sxs-lookup"><span data-stu-id="7b04b-181">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="7b04b-182">默认情况下，WinRM（由此还有 PowerShell 远程处理）作为计算机帐户运行。</span><span class="sxs-lookup"><span data-stu-id="7b04b-182">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="7b04b-183">可通过查看 `winrm` 服务的 **StartName** 属性看到：</span><span class="sxs-lookup"><span data-stu-id="7b04b-183">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="7b04b-184">为使 ServerC 允许来自 ServerB 上的 PowerShell 远程处理会话的委派，我们必须将 ServerC 上的 PrincipalsAllowedToDelegateToAccount 参数设置为 ServerB 的计算机对象  ：</span><span class="sxs-lookup"><span data-stu-id="7b04b-184">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="7b04b-185">Kerberos [密钥分发中心 (KDC)](/windows/win32/secauthn/key-distribution-center) 将拒绝访问尝试（负缓存）缓存保留 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="7b04b-185">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="7b04b-186">如果 _ServerB_ 先前已尝试访问 _ServerC_，则需要通过调用以下命令清除 _ServerB_ 上的缓存：</span><span class="sxs-lookup"><span data-stu-id="7b04b-186">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="7b04b-187">还可以重启计算机，或等待至少 15 分钟，以清除缓存。</span><span class="sxs-lookup"><span data-stu-id="7b04b-187">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="7b04b-188">清除缓存之后，可以通过 _ServerB_ 到 _ServerC_成功运行来自 _ServerA_ 的代码：</span><span class="sxs-lookup"><span data-stu-id="7b04b-188">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

<span data-ttu-id="7b04b-189">在本示例中，`$using` 变量用于使 `$ServerC` 变量对 _ServerB_ 可见。</span><span class="sxs-lookup"><span data-stu-id="7b04b-189">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="7b04b-190">有关 `$using` 变量的详细信息，请参阅 [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables)。</span><span class="sxs-lookup"><span data-stu-id="7b04b-190">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="7b04b-191">若要允许多个服务器向 _ServerC_ 委派凭据，在 _ServerC_ 上将 **PrincipalsAllowedToDelegateToAccount** 参数的值设为数组：</span><span class="sxs-lookup"><span data-stu-id="7b04b-191">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

<span data-ttu-id="7b04b-192">如果想要跨域形成第二个跃点，添加 _ServerB_ 所属域的域控制器的完全限定域名 (FQDN)：</span><span class="sxs-lookup"><span data-stu-id="7b04b-192">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="7b04b-193">若要删除向 ServerC 委派凭据的功能，在 _ServerC_ 上将 **PrincipalsAllowedToDelegateToAccount** 参数的值设为 `$null`：</span><span class="sxs-lookup"><span data-stu-id="7b04b-193">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="7b04b-194">基于资源的 Kerberos 约束委派的相关信息</span><span class="sxs-lookup"><span data-stu-id="7b04b-194">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="7b04b-195">[Kerberos 身份验证的中的新功能][whats-new]</span><span class="sxs-lookup"><span data-stu-id="7b04b-195">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="7b04b-196">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]（Windows Server 2012 如何缓解 Kerberos 约束委派的痛苦，第 1 部分）</span><span class="sxs-lookup"><span data-stu-id="7b04b-196">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="7b04b-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]（Windows Server 2012 如何缓解 Kerberos 约束委派的痛苦，第 2 部分）</span><span class="sxs-lookup"><span data-stu-id="7b04b-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="7b04b-198">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]（了解 Kerberos 约束委派，以使用集成的 Windows 身份验证进行 Azure Active Directory 应用程序代理部署）</span><span class="sxs-lookup"><span data-stu-id="7b04b-198">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="7b04b-199">[[MS-ADA2] Active Directory 架构属性 M2.210 属性 msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="7b04b-199">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="7b04b-200">[[MS-SFU] Kerberos 协议扩展：用户服务和约束委派协议 1.3.2 S4U2proxy][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="7b04b-200">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="7b04b-201">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]（在不使用约束委派的情况下，使用 PrincipalsAllowedToDelegateToAccount 进行远程管理）</span><span class="sxs-lookup"><span data-stu-id="7b04b-201">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="7b04b-202">Kerberos 委派（非约束）</span><span class="sxs-lookup"><span data-stu-id="7b04b-202">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="7b04b-203">还可以使用 Kerberos 非约束委派来形成第二个跃点。</span><span class="sxs-lookup"><span data-stu-id="7b04b-203">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="7b04b-204">与所有 Kerberos 方案一样，不会存储凭据。</span><span class="sxs-lookup"><span data-stu-id="7b04b-204">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="7b04b-205">此方法不支持 WinRM 的第二个跃点。</span><span class="sxs-lookup"><span data-stu-id="7b04b-205">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="7b04b-206">此方法无法控制使用委派凭据的位置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-206">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="7b04b-207">它的安全性比 CredSSP 低。</span><span class="sxs-lookup"><span data-stu-id="7b04b-207">It is less secure than CredSSP.</span></span> <span data-ttu-id="7b04b-208">此方法应仅用于测试方案。</span><span class="sxs-lookup"><span data-stu-id="7b04b-208">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="7b04b-209">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="7b04b-209">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="7b04b-210">JEA 允许限制管理员在 PowerShell 会话期间可以运行的命令。</span><span class="sxs-lookup"><span data-stu-id="7b04b-210">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="7b04b-211">它可用于解决第二个跃点问题。</span><span class="sxs-lookup"><span data-stu-id="7b04b-211">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="7b04b-212">有关 JEA 的信息，请参阅 [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview)。</span><span class="sxs-lookup"><span data-stu-id="7b04b-212">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="7b04b-213">**优点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-213">**Pros**</span></span>

- <span data-ttu-id="7b04b-214">使用虚拟帐户时无需密码维护。</span><span class="sxs-lookup"><span data-stu-id="7b04b-214">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="7b04b-215">**缺点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-215">**Cons**</span></span>

- <span data-ttu-id="7b04b-216">需要 WMF 5.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7b04b-216">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="7b04b-217">需要在每个中间服务器 (_ServerB_) 上进行配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-217">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="7b04b-218">使用 RunAs 的 PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b04b-218">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="7b04b-219">可以在 _ServerB_ 上创建会话配置并设置其 **RunAsCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="7b04b-219">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="7b04b-220">要了解如何结合使用 PSSessionConfiguration 和 RunAs 来解决第二个跃点问题，请参阅[多跃点 PowerShell 远程处理的另一种解决方案][pssessionconfig] 。</span><span class="sxs-lookup"><span data-stu-id="7b04b-220">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="7b04b-221">**优点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-221">**Pros**</span></span>

- <span data-ttu-id="7b04b-222">兼容任何运行 WMF 3.0 或更高版本的服务器。</span><span class="sxs-lookup"><span data-stu-id="7b04b-222">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="7b04b-223">**缺点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-223">**Cons**</span></span>

- <span data-ttu-id="7b04b-224">需要在每个中间服务器 (_ServerB_) 上配置 **PSSessionConfiguration** 和 **RunAs**。</span><span class="sxs-lookup"><span data-stu-id="7b04b-224">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="7b04b-225">使用域 **RunAs** 帐户时要求密码维护</span><span class="sxs-lookup"><span data-stu-id="7b04b-225">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="7b04b-226">在 Invoke-Command 脚本块内传递凭据</span><span class="sxs-lookup"><span data-stu-id="7b04b-226">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="7b04b-227">可以在对 [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet 的调用的 **ScriptBlock** 参数内传递凭据。</span><span class="sxs-lookup"><span data-stu-id="7b04b-227">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="7b04b-228">**优点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-228">**Pros**</span></span>

- <span data-ttu-id="7b04b-229">无需特殊服务器配置。</span><span class="sxs-lookup"><span data-stu-id="7b04b-229">Does not require special server configuration.</span></span>
- <span data-ttu-id="7b04b-230">适用于任何运行 WMF 2.0 或更高版本的服务器。</span><span class="sxs-lookup"><span data-stu-id="7b04b-230">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="7b04b-231">**缺点**</span><span class="sxs-lookup"><span data-stu-id="7b04b-231">**Cons**</span></span>

- <span data-ttu-id="7b04b-232">需要繁琐的代码技术。</span><span class="sxs-lookup"><span data-stu-id="7b04b-232">Requires an awkward code technique.</span></span>
- <span data-ttu-id="7b04b-233">运行 WMF 2.0 时，需要不同的语法将参数传递到远程会话。</span><span class="sxs-lookup"><span data-stu-id="7b04b-233">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="7b04b-234">示例</span><span class="sxs-lookup"><span data-stu-id="7b04b-234">Example</span></span>

<span data-ttu-id="7b04b-235">以下示例演示了如何在 **Invoke-command** 脚本块中传递凭据：</span><span class="sxs-lookup"><span data-stu-id="7b04b-235">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="7b04b-236">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b04b-236">See also</span></span>

[<span data-ttu-id="7b04b-237">PowerShell 远程处理安全注意事项</span><span class="sxs-lookup"><span data-stu-id="7b04b-237">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group
