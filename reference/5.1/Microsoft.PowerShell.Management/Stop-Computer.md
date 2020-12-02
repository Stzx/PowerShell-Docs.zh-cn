---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198994"
---
# <span data-ttu-id="788df-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-103">Stop-Computer</span></span>

## <span data-ttu-id="788df-104">摘要</span><span class="sxs-lookup"><span data-stu-id="788df-104">SYNOPSIS</span></span>
<span data-ttu-id="788df-105">停止（关闭）本地和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="788df-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="788df-106">SYNTAX</span></span>

### <span data-ttu-id="788df-107">全部</span><span class="sxs-lookup"><span data-stu-id="788df-107">All</span></span>

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="788df-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="788df-108">DESCRIPTION</span></span>

<span data-ttu-id="788df-109">Cmdlet 将关闭 `Stop-Computer` 本地计算机和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="788df-110">您可以使用的参数将 `Stop-Computer` 关闭操作作为后台作业运行，指定身份验证级别和备用凭据，限制为运行该命令而创建的并发连接，以及强制立即关闭。</span><span class="sxs-lookup"><span data-stu-id="788df-110">You can use the parameters of `Stop-Computer` to run the shutdown operations as a background job, to specify the authentication levels and alternate credentials, to limit the concurrent connections that are created to run the command, and to force an immediate shut down.</span></span>

<span data-ttu-id="788df-111">除非你使用 **AsJob** 参数，否则此 cmdlet 不需要 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="788df-111">This cmdlet doesn't require PowerShell remoting unless you use the **AsJob** parameter.</span></span>

## <span data-ttu-id="788df-112">示例</span><span class="sxs-lookup"><span data-stu-id="788df-112">EXAMPLES</span></span>

### <span data-ttu-id="788df-113">示例 1：关闭本地计算机</span><span class="sxs-lookup"><span data-stu-id="788df-113">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="788df-114">此示例关闭本地计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-114">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="788df-115">示例 2：关闭两台远程计算机和本地计算机</span><span class="sxs-lookup"><span data-stu-id="788df-115">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="788df-116">此示例将停止两台远程计算机和本地计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-116">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="788df-117">`Stop-Computer` 使用 **ComputerName** 参数指定两台远程计算机和本地计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-117">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="788df-118">每台计算机都已关闭。</span><span class="sxs-lookup"><span data-stu-id="788df-118">Each computer is shut down.</span></span>

### <span data-ttu-id="788df-119">示例 3：关闭远程计算机，作为后台作业运行</span><span class="sxs-lookup"><span data-stu-id="788df-119">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="788df-120">在此示例中，在 `Stop-Computer` 两台远程计算机上作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="788df-120">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

<span data-ttu-id="788df-121">`Stop-Computer` 使用 **ComputerName** 参数指定两台远程计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-121">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="788df-122">**AsJob** 参数将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="788df-122">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="788df-123">作业对象存储在 `$j` 变量中。</span><span class="sxs-lookup"><span data-stu-id="788df-123">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="788df-124">变量中的作业对象 `$j` 会向下发送到 `Receive-Job` ，后者将获取作业结果。</span><span class="sxs-lookup"><span data-stu-id="788df-124">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="788df-125">这些对象存储在变量中 `$results` 。</span><span class="sxs-lookup"><span data-stu-id="788df-125">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="788df-126">此 `$results` 变量在 PowerShell 控制台中显示作业信息。</span><span class="sxs-lookup"><span data-stu-id="788df-126">The `$results` variable displays the job information in the PowerShell console.</span></span>

<span data-ttu-id="788df-127">由于 **AsJob** 在本地计算机上创建作业，并自动将结果返回到本地计算机，因此你可以 `Receive-Job` 将其作为本地命令运行。</span><span class="sxs-lookup"><span data-stu-id="788df-127">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

### <span data-ttu-id="788df-128">示例 4：关闭远程计算机</span><span class="sxs-lookup"><span data-stu-id="788df-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="788df-129">此示例使用指定的身份验证关闭远程计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="788df-130">`Stop-Computer` 使用 **ComputerName** 参数来指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="788df-131">**模拟** 参数指定自定义模拟， **DcomAuthentication** 参数指定身份验证级别设置。</span><span class="sxs-lookup"><span data-stu-id="788df-131">The **Impersonation** parameter specifies a customized impersonation and the **DcomAuthentication** parameter specifies authentication-level settings.</span></span>

### <span data-ttu-id="788df-132">示例5：关闭域中的计算机</span><span class="sxs-lookup"><span data-stu-id="788df-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="788df-133">在此示例中，这些命令强制立即关闭指定域中的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

<span data-ttu-id="788df-134">`Get-Content` 使用 **Path** 参数获取当前目录中包含域计算机列表的文件。</span><span class="sxs-lookup"><span data-stu-id="788df-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="788df-135">这些对象存储在变量中 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="788df-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="788df-136">`Get-Credential` 使用 **Credential** 参数指定域管理员的凭据。</span><span class="sxs-lookup"><span data-stu-id="788df-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="788df-137">凭据存储在 `$c` 变量中。</span><span class="sxs-lookup"><span data-stu-id="788df-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="788df-138">`Stop-Computer` 关闭在变量中用 **ComputerName** 参数的计算机列表指定的计算机 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="788df-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="788df-139">**Force** 参数强制立即关闭。</span><span class="sxs-lookup"><span data-stu-id="788df-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="788df-140">**ThrottleLimit** 参数将该命令限制为10个并发连接。</span><span class="sxs-lookup"><span data-stu-id="788df-140">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span> <span data-ttu-id="788df-141">**Credential** 参数提交保存在变量中的凭据 `$c` 。</span><span class="sxs-lookup"><span data-stu-id="788df-141">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="788df-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="788df-142">PARAMETERS</span></span>

### <span data-ttu-id="788df-143">-AsJob</span><span class="sxs-lookup"><span data-stu-id="788df-143">-AsJob</span></span>

<span data-ttu-id="788df-144">指示此 cmdlet 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="788df-144">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="788df-145">若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 和更高版本的 Windows 操作系统上，必须使用 "以 **管理员身份运行** " 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="788df-145">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="788df-146">有关详细信息，请参阅 [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="788df-146">For more information, see [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="788df-147">指定 AsJob 参数时，该命令立即返回代表后台作业的对象。</span><span class="sxs-lookup"><span data-stu-id="788df-147">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="788df-148">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="788df-148">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="788df-149">作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-149">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="788df-150">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="788df-150">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="788df-151">有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) 和 [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="788df-151">For more information about PowerShell background jobs, see [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) and [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="788df-152">-ComputerName</span></span>

<span data-ttu-id="788df-153">指定要停止的计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-153">Specifies the computers to stop.</span></span> <span data-ttu-id="788df-154">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-154">The default is the local computer.</span></span>

<span data-ttu-id="788df-155">在一个逗号分隔列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="788df-155">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="788df-156">若要指定本地计算机，请键入计算机名称或“localhost”。</span><span class="sxs-lookup"><span data-stu-id="788df-156">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="788df-157">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="788df-157">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="788df-158">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="788df-158">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="788df-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="788df-159">-Confirm</span></span>

<span data-ttu-id="788df-160">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="788df-160">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="788df-161">-Credential</span></span>

<span data-ttu-id="788df-162">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="788df-162">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="788df-163">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="788df-163">The default is the current user.</span></span>

<span data-ttu-id="788df-164">键入用户名（如 **User01** 或 **Domain01\User01**），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="788df-164">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="788df-165">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="788df-165">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="788df-166">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="788df-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="788df-167">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="788df-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-168">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="788df-168">-DcomAuthentication</span></span>

<span data-ttu-id="788df-169">指定此 cmdlet 用于 WMI 的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="788df-169">Specifies the authentication level that this cmdlet uses with WMI.</span></span> <span data-ttu-id="788df-170">`Stop-Computer` 使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="788df-170">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="788df-171">默认值为 **Packet**。</span><span class="sxs-lookup"><span data-stu-id="788df-171">The default value is **Packet**.</span></span>

<span data-ttu-id="788df-172">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="788df-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="788df-173">**默认**： Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-173">**Default**: Windows Authentication.</span></span>
- <span data-ttu-id="788df-174">**None**：无 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-174">**None**: No COM authentication.</span></span>
- <span data-ttu-id="788df-175">**Connect**：连接级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-175">**Connect**: Connect-level COM authentication.</span></span>
- <span data-ttu-id="788df-176">**Call**：调用级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-176">**Call**: Call-level COM authentication.</span></span>
- <span data-ttu-id="788df-177">**Packet**：数据包级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-177">**Packet**: Packet-level COM authentication.</span></span>
- <span data-ttu-id="788df-178">**PacketIntegrity**：数据包完整性级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-178">**PacketIntegrity**: Packet Integrity-level COM authentication.</span></span>
- <span data-ttu-id="788df-179">**PacketPrivacy**：数据包隐私级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="788df-179">**PacketPrivacy**: Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="788df-180">**保持不变**：与前一个命令相同。</span><span class="sxs-lookup"><span data-stu-id="788df-180">**Unchanged**: Same as the previous command.</span></span>

<span data-ttu-id="788df-181">有关此参数的值的详细信息，请参阅 [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel)。</span><span class="sxs-lookup"><span data-stu-id="788df-181">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-182">-Force</span><span class="sxs-lookup"><span data-stu-id="788df-182">-Force</span></span>

<span data-ttu-id="788df-183">强制立即关闭计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-183">Forces an immediate shut down of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-184">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="788df-184">-Impersonation</span></span>

<span data-ttu-id="788df-185">指定此 cmdlet 调用 WMI 时使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="788df-185">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="788df-186">默认值为 " **模拟**"。</span><span class="sxs-lookup"><span data-stu-id="788df-186">The default value is **Impersonate**.</span></span>

<span data-ttu-id="788df-187">`Stop-Computer` 使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="788df-187">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="788df-188">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="788df-188">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="788df-189">**默认值**：默认模拟。</span><span class="sxs-lookup"><span data-stu-id="788df-189">**Default**: Default impersonation.</span></span>
- <span data-ttu-id="788df-190">**Anonymous**：隐藏调用方的标识。</span><span class="sxs-lookup"><span data-stu-id="788df-190">**Anonymous**: Hides the identity of the caller.</span></span>
- <span data-ttu-id="788df-191">**标识**：允许对象查询调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="788df-191">**Identify**: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="788df-192">**模拟**：允许对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="788df-192">**Impersonate**: Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-193">-Protocol</span><span class="sxs-lookup"><span data-stu-id="788df-193">-Protocol</span></span>

<span data-ttu-id="788df-194">指定重新启动计算机要使用的协议。</span><span class="sxs-lookup"><span data-stu-id="788df-194">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="788df-195">此参数可接受的值包括： **WSMan** 和 **DCOM**。</span><span class="sxs-lookup"><span data-stu-id="788df-195">The acceptable values for this parameter are: **WSMan** and **DCOM**.</span></span> <span data-ttu-id="788df-196">默认值为 **DCOM**。</span><span class="sxs-lookup"><span data-stu-id="788df-196">The default value is **DCOM**.</span></span>

<span data-ttu-id="788df-197">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="788df-197">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-198">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="788df-198">-ThrottleLimit</span></span>

<span data-ttu-id="788df-199">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="788df-199">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="788df-200">如果省略此参数或输入 0 值，则使用默认值 32。</span><span class="sxs-lookup"><span data-stu-id="788df-200">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="788df-201">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="788df-201">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="788df-202">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="788df-202">-WsmanAuthentication</span></span>

<span data-ttu-id="788df-203">指定此 cmdlet 使用 WSMan 协议时用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="788df-203">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="788df-204">默认值为 **Default**。</span><span class="sxs-lookup"><span data-stu-id="788df-204">The default value is **Default**.</span></span>

<span data-ttu-id="788df-205">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="788df-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="788df-206">基本</span><span class="sxs-lookup"><span data-stu-id="788df-206">Basic</span></span>
- <span data-ttu-id="788df-207">CredSSP</span><span class="sxs-lookup"><span data-stu-id="788df-207">CredSSP</span></span>
- <span data-ttu-id="788df-208">默认</span><span class="sxs-lookup"><span data-stu-id="788df-208">Default</span></span>
- <span data-ttu-id="788df-209">摘要</span><span class="sxs-lookup"><span data-stu-id="788df-209">Digest</span></span>
- <span data-ttu-id="788df-210">Kerberos</span><span class="sxs-lookup"><span data-stu-id="788df-210">Kerberos</span></span>
- <span data-ttu-id="788df-211">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="788df-211">Negotiate.</span></span>

<span data-ttu-id="788df-212">有关此参数的值的详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="788df-212">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="788df-213">凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="788df-213">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="788df-214">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="788df-214">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="788df-215">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="788df-215">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="788df-216">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="788df-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-217">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="788df-217">-WhatIf</span></span>

<span data-ttu-id="788df-218">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="788df-218">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="788df-219">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="788df-219">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="788df-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="788df-220">CommonParameters</span></span>

<span data-ttu-id="788df-221">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="788df-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="788df-222">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="788df-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="788df-223">输入</span><span class="sxs-lookup"><span data-stu-id="788df-223">INPUTS</span></span>

### <span data-ttu-id="788df-224">无</span><span class="sxs-lookup"><span data-stu-id="788df-224">None</span></span>

<span data-ttu-id="788df-225">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="788df-225">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="788df-226">输出</span><span class="sxs-lookup"><span data-stu-id="788df-226">OUTPUTS</span></span>

### <span data-ttu-id="788df-227">无或 System.Management.Automation.RemotingJob</span><span class="sxs-lookup"><span data-stu-id="788df-227">None or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="788df-228">如果指定 AsJob 参数，该 cmdlet 将返回 **System.Management.Automation.RemotingJob** 对象。</span><span class="sxs-lookup"><span data-stu-id="788df-228">The cmdlet returns a **System.Management.Automation.RemotingJob** object, if you specify the **AsJob** parameter.</span></span> <span data-ttu-id="788df-229">否则，不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="788df-229">Otherwise, it doesn't generate any output.</span></span>

## <span data-ttu-id="788df-230">注释</span><span class="sxs-lookup"><span data-stu-id="788df-230">NOTES</span></span>

<span data-ttu-id="788df-231">此 cmdlet 使用 **Win32_OperatingSystem** WMI 类的 **Win32Shutdown** 方法。</span><span class="sxs-lookup"><span data-stu-id="788df-231">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="788df-232">此方法需要为用于重新启动计算机的用户帐户启用 **SeShutdownPrivilege** 特权。</span><span class="sxs-lookup"><span data-stu-id="788df-232">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="788df-233">相关链接</span><span class="sxs-lookup"><span data-stu-id="788df-233">RELATED LINKS</span></span>

[<span data-ttu-id="788df-234">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-234">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="788df-235">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-235">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="788df-236">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-236">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="788df-237">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-237">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="788df-238">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-238">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="788df-239">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="788df-239">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="788df-240">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="788df-240">Test-Connection</span></span>](Test-Connection.md)
