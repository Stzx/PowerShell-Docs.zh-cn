---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198014"
---
# <span data-ttu-id="c44fc-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="c44fc-103">Test-Connection</span></span>

## <span data-ttu-id="c44fc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c44fc-104">SYNOPSIS</span></span>
<span data-ttu-id="c44fc-105">将 ICMP 回显请求数据包或 ping 发送到一台或多台计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="c44fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c44fc-106">SYNTAX</span></span>

### <span data-ttu-id="c44fc-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="c44fc-107">Default (Default)</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="c44fc-108">源</span><span class="sxs-lookup"><span data-stu-id="c44fc-108">Source</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="c44fc-109">Quiet</span><span class="sxs-lookup"><span data-stu-id="c44fc-109">Quiet</span></span>

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## <span data-ttu-id="c44fc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c44fc-110">DESCRIPTION</span></span>

<span data-ttu-id="c44fc-111">`Test-Connection`Cmdlet 将 Internet 控制消息协议 () ICMP 发送到一台或多台远程计算机并返回回显响应回复。</span><span class="sxs-lookup"><span data-stu-id="c44fc-111">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="c44fc-112">可以使用此 cmdlet 来确定是否可以通过 IP 网络联系特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-112">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="c44fc-113">您可以使用的参数 `Test-Connection` 同时指定发送计算机和接收计算机，将该命令作为后台作业运行，设置超时和 ping 数目，以及配置连接和身份验证。</span><span class="sxs-lookup"><span data-stu-id="c44fc-113">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="c44fc-114">与熟悉的 **ping** 命令不同， `Test-Connection` 返回可以在 PowerShell 中调查的 **Win32_PingStatus** 对象。</span><span class="sxs-lookup"><span data-stu-id="c44fc-114">Unlike the familiar **ping** command, `Test-Connection` returns a **Win32_PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="c44fc-115">**Quiet** 参数为每个已测试的连接返回 **system.object** 对象中的 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="c44fc-115">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="c44fc-116">如果测试了多个连接，则返回 **布尔** 值的数组。</span><span class="sxs-lookup"><span data-stu-id="c44fc-116">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="c44fc-117">示例</span><span class="sxs-lookup"><span data-stu-id="c44fc-117">EXAMPLES</span></span>

### <span data-ttu-id="c44fc-118">示例1：向远程计算机发送回显请求</span><span class="sxs-lookup"><span data-stu-id="c44fc-118">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="c44fc-119">此示例将来自本地计算机的回显请求数据包发送到 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-119">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

<span data-ttu-id="c44fc-120">`Test-Connection` 使用 **ComputerName** 参数指定 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-120">`Test-Connection` uses the **ComputerName** parameter to specify the Server01 computer.</span></span>

### <span data-ttu-id="c44fc-121">示例2：将回显请求发送到多台计算机</span><span class="sxs-lookup"><span data-stu-id="c44fc-121">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="c44fc-122">此示例将来自本地计算机的 ping 发送到多台远程计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-122">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### <span data-ttu-id="c44fc-123">示例3：从多台计算机向计算机发送回显请求</span><span class="sxs-lookup"><span data-stu-id="c44fc-123">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="c44fc-124">此示例将来自不同源计算机的 ping 发送到一台远程计算机 Server01。</span><span class="sxs-lookup"><span data-stu-id="c44fc-124">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="c44fc-125">`Test-Connection` 使用 **Credential** 参数指定有权从源计算机发送 ping 请求的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="c44fc-125">`Test-Connection` uses the **Credential** parameter to specify the credentials of a user who has permission to send a ping request from the source computers.</span></span> <span data-ttu-id="c44fc-126">使用此命令格式可从多个点来测试连接的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="c44fc-126">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="c44fc-127">示例4：使用参数自定义测试命令</span><span class="sxs-lookup"><span data-stu-id="c44fc-127">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="c44fc-128">此示例使用的参数 `Test-Connection` 自定义命令。</span><span class="sxs-lookup"><span data-stu-id="c44fc-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="c44fc-129">本地计算机将 ping 测试发送到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

<span data-ttu-id="c44fc-130">`Test-Connection` 使用 **ComputerName** 参数指定 Server01。</span><span class="sxs-lookup"><span data-stu-id="c44fc-130">`Test-Connection` uses the **ComputerName** parameter to specify Server01.</span></span> <span data-ttu-id="c44fc-131">**Count** 参数指定三个 ping 发送到 Server01 计算机， **延迟** 为2秒的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c44fc-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="c44fc-132">当 ping 响应预计需要比平时更长的时间（因为有扩展的跃点数或高流量网络条件）时，可以使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="c44fc-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="c44fc-133">示例5：将测试作为后台作业运行</span><span class="sxs-lookup"><span data-stu-id="c44fc-133">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="c44fc-134">此示例演示如何将 `Test-Connection` 命令作为 PowerShell 后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="c44fc-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

<span data-ttu-id="c44fc-135">`Test-Connection`命令对企业中的多台计算机执行 ping 操作。</span><span class="sxs-lookup"><span data-stu-id="c44fc-135">The `Test-Connection` command pings many computers in an enterprise.</span></span> <span data-ttu-id="c44fc-136">**ComputerName** 参数的值是一个 `Get-Content` 命令，该命令从中读取计算机名称的列表 `Servers.txt file` 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-136">The value of the **ComputerName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt file`.</span></span> <span data-ttu-id="c44fc-137">该命令使用 **AsJob** 参数将命令作为后台作业运行，并将作业保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c44fc-137">The command uses the **AsJob** parameter to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="c44fc-138">此 `if` 命令会检查该作业是否仍在运行。</span><span class="sxs-lookup"><span data-stu-id="c44fc-138">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="c44fc-139">如果该作业未运行， `Receive-Job` 将获取结果并将其存储在 `$Results` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c44fc-139">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="c44fc-140">示例6：使用凭据对远程计算机执行 Ping 操作</span><span class="sxs-lookup"><span data-stu-id="c44fc-140">Example 6: Ping a remote computer with credentials</span></span>

<span data-ttu-id="c44fc-141">此命令使用 `Test-Connection` cmdlet 对远程计算机执行 ping 操作。</span><span class="sxs-lookup"><span data-stu-id="c44fc-141">This command uses the `Test-Connection` cmdlet to ping a remote computer.</span></span>

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

<span data-ttu-id="c44fc-142">该命令使用 **Credential** 参数指定有权对远程计算机执行 ping 操作的用户帐户，以及用于将模拟级别更改为 **标识** 的 **模拟** 参数。</span><span class="sxs-lookup"><span data-stu-id="c44fc-142">The command uses the **Credential** parameter to specify a user account that has permission to ping the remote computer and the **Impersonation** parameter to change the impersonation level to **Identify** .</span></span>

### <span data-ttu-id="c44fc-143">示例7：仅在连接测试成功时创建会话</span><span class="sxs-lookup"><span data-stu-id="c44fc-143">Example 7: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="c44fc-144">仅当至少一个发送到计算机的 ping 成功时，此示例才会在 Server01 计算机上创建一个会话。</span><span class="sxs-lookup"><span data-stu-id="c44fc-144">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="c44fc-145">该 `if` 命令使用 `Test-Connection` Cmdlet 对 Server01 计算机进行 ping 操作。</span><span class="sxs-lookup"><span data-stu-id="c44fc-145">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="c44fc-146">该命令使用 **Quiet** 参数，该参数将返回一个 **布尔** 值，而不是 **Win32_PingStatus** 的对象。</span><span class="sxs-lookup"><span data-stu-id="c44fc-146">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **Win32_PingStatus** object.</span></span> <span data-ttu-id="c44fc-147">`$True`如果四个 ping 中有任何 ping 成功，则该值为，否则为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-147">The value is `$True` if any of the four pings succeed and is, otherwise, `$False`.</span></span>

<span data-ttu-id="c44fc-148">如果 `Test-Connection` 命令返回的值 `$True` ，则该命令将使用 `New-PSSession` cmdlet 创建 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-148">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

## <span data-ttu-id="c44fc-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c44fc-149">PARAMETERS</span></span>

### <span data-ttu-id="c44fc-150">-AsJob</span><span class="sxs-lookup"><span data-stu-id="c44fc-150">-AsJob</span></span>

<span data-ttu-id="c44fc-151">指示此 cmdlet 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="c44fc-151">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="c44fc-152">若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 和更高版本的 Windows 操作系统上，必须使用 "以 **管理员身份运行** " 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c44fc-152">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="c44fc-153">有关详细信息，请参阅 [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c44fc-153">For more information, see [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="c44fc-154">指定 AsJob  参数时，该命令立即返回代表后台作业的对象。</span><span class="sxs-lookup"><span data-stu-id="c44fc-154">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="c44fc-155">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="c44fc-155">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="c44fc-156">作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-156">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="c44fc-157">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c44fc-157">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="c44fc-158">有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="c44fc-158">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-159">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="c44fc-159">-BufferSize</span></span>

<span data-ttu-id="c44fc-160">指定使用此命令发送的缓冲区的大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="c44fc-160">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="c44fc-161">默认值为 32。</span><span class="sxs-lookup"><span data-stu-id="c44fc-161">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c44fc-162">-ComputerName</span></span>

<span data-ttu-id="c44fc-163">指定要对其执行 ping 操作的计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-163">Specifies the computers to ping.</span></span> <span data-ttu-id="c44fc-164">请键入计算机名称或者以 IPv4 或 IPv6 格式键入 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c44fc-164">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="c44fc-165">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c44fc-165">Wildcard characters are not permitted.</span></span> <span data-ttu-id="c44fc-166">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="c44fc-166">This parameter is required.</span></span>

<span data-ttu-id="c44fc-167">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="c44fc-167">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="c44fc-168">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="c44fc-168">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

> [!NOTE]
> <span data-ttu-id="c44fc-169">**ComputerName** 参数重命名为 PowerShell 6.0 及更高版本中的 **TargetName** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-169">The **ComputerName** parameter is renamed to **TargetName** in PowerShell 6.0 and above.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-170">-Count</span><span class="sxs-lookup"><span data-stu-id="c44fc-170">-Count</span></span>

<span data-ttu-id="c44fc-171">指定要发送的回显请求数。</span><span class="sxs-lookup"><span data-stu-id="c44fc-171">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="c44fc-172">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="c44fc-172">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="c44fc-173">-Credential</span></span>

<span data-ttu-id="c44fc-174">指定有权从源计算机发送 ping 请求的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c44fc-174">Specifies a user account that has permission to send a ping request from the source computer.</span></span> <span data-ttu-id="c44fc-175">键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如来自 cmdlet 的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-175">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="c44fc-176">仅当该命令中使用了 **Source** 参数时， **Credential** 参数才有效。</span><span class="sxs-lookup"><span data-stu-id="c44fc-176">The **Credential** parameter is valid only when the **Source** parameter is used in the command.</span></span> <span data-ttu-id="c44fc-177">凭据不会影响目标计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-177">The credentials don't affect the destination computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-178">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="c44fc-178">-DcomAuthentication</span></span>

<span data-ttu-id="c44fc-179">指定此 cmdlet 用于 WMI 的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="c44fc-179">Specifies the authentication level that this cmdlet uses with WMI.</span></span>
<span data-ttu-id="c44fc-180">`Test-Connection` 使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="c44fc-180">`Test-Connection` uses WMI.</span></span>
<span data-ttu-id="c44fc-181">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="c44fc-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c44fc-182">**Default** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-182">**Default** .</span></span> <span data-ttu-id="c44fc-183">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-183">Windows Authentication</span></span>
- <span data-ttu-id="c44fc-184">**无** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-184">**None** .</span></span> <span data-ttu-id="c44fc-185">无 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-185">No COM authentication</span></span>
- <span data-ttu-id="c44fc-186">**连接** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-186">**Connect** .</span></span> <span data-ttu-id="c44fc-187">连接级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-187">Connect-level COM authentication</span></span>
- <span data-ttu-id="c44fc-188">**调用** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-188">**Call** .</span></span> <span data-ttu-id="c44fc-189">调用级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-189">Call-level COM authentication</span></span>
- <span data-ttu-id="c44fc-190">**数据包** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-190">**Packet** .</span></span> <span data-ttu-id="c44fc-191">数据包级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-191">Packet-level COM authentication</span></span>
- <span data-ttu-id="c44fc-192">**PacketIntegrity** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-192">**PacketIntegrity** .</span></span> <span data-ttu-id="c44fc-193">数据包完整性级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-193">Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="c44fc-194">**PacketPrivacy** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-194">**PacketPrivacy** .</span></span> <span data-ttu-id="c44fc-195">数据包隐私级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="c44fc-195">Packet Privacy-level COM authentication</span></span>
- <span data-ttu-id="c44fc-196">**保持不变** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-196">**Unchanged** .</span></span> <span data-ttu-id="c44fc-197">与前一个命令相同</span><span class="sxs-lookup"><span data-stu-id="c44fc-197">Same as the previous command</span></span>

<span data-ttu-id="c44fc-198">默认值为具有枚举值 **4** 的 **数据包** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-198">The default value is **Packet** that has an enumerated value of **4** .</span></span> <span data-ttu-id="c44fc-199">有关此参数的值的详细信息，请参阅 [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) 枚举。</span><span class="sxs-lookup"><span data-stu-id="c44fc-199">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) enumeration.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-200">-Delay</span><span class="sxs-lookup"><span data-stu-id="c44fc-200">-Delay</span></span>

<span data-ttu-id="c44fc-201">指定两次 ping 操作之间的间隔时间，以秒为单位。</span><span class="sxs-lookup"><span data-stu-id="c44fc-201">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-202">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="c44fc-202">-Impersonation</span></span>

<span data-ttu-id="c44fc-203">指定此 cmdlet 调用 WMI 时使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="c44fc-203">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="c44fc-204">`Test-Connection` 使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="c44fc-204">`Test-Connection` uses WMI.</span></span>

<span data-ttu-id="c44fc-205">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="c44fc-205">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c44fc-206">**Default** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-206">**Default** .</span></span> <span data-ttu-id="c44fc-207">默认模拟。</span><span class="sxs-lookup"><span data-stu-id="c44fc-207">Default impersonation.</span></span>
- <span data-ttu-id="c44fc-208">**匿名** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-208">**Anonymous** .</span></span> <span data-ttu-id="c44fc-209">隐藏调用方的身份。</span><span class="sxs-lookup"><span data-stu-id="c44fc-209">Hides the identity of the caller.</span></span>
- <span data-ttu-id="c44fc-210">**确定** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-210">**Identify** .</span></span> <span data-ttu-id="c44fc-211">允许对象查询调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="c44fc-211">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="c44fc-212">**模拟** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-212">**Impersonate** .</span></span> <span data-ttu-id="c44fc-213">允许对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="c44fc-213">Allows objects to use the credentials of the caller.</span></span>

<span data-ttu-id="c44fc-214">默认值为 " **模拟** "。</span><span class="sxs-lookup"><span data-stu-id="c44fc-214">The default value is **Impersonate** .</span></span>

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

### <span data-ttu-id="c44fc-215">-Protocol</span><span class="sxs-lookup"><span data-stu-id="c44fc-215">-Protocol</span></span>

<span data-ttu-id="c44fc-216">指定协议。</span><span class="sxs-lookup"><span data-stu-id="c44fc-216">Specifies a protocol.</span></span> <span data-ttu-id="c44fc-217">此参数可接受的值为 DCOM 和 WSMan。</span><span class="sxs-lookup"><span data-stu-id="c44fc-217">The acceptable values for this parameter are DCOM and WSMan.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-218">-Quiet</span><span class="sxs-lookup"><span data-stu-id="c44fc-218">-Quiet</span></span>

<span data-ttu-id="c44fc-219">**Quiet** 参数返回 **system.object** 对象中的 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="c44fc-219">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="c44fc-220">使用此参数将取消所有错误。</span><span class="sxs-lookup"><span data-stu-id="c44fc-220">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="c44fc-221">所测试的每个连接都将返回一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="c44fc-221">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="c44fc-222">如果 **ComputerName** 参数指定了多台计算机，则返回 **布尔** 值的数组。</span><span class="sxs-lookup"><span data-stu-id="c44fc-222">If the **ComputerName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="c44fc-223">如果 **任何** ping 成功， `$True` 则返回。</span><span class="sxs-lookup"><span data-stu-id="c44fc-223">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="c44fc-224">如果 **所有** ping `$False` 操作都失败，则返回。</span><span class="sxs-lookup"><span data-stu-id="c44fc-224">If **all** pings fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-225">-Source</span><span class="sxs-lookup"><span data-stu-id="c44fc-225">-Source</span></span>

<span data-ttu-id="c44fc-226">指定发出 ping 请求的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="c44fc-226">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="c44fc-227">请输入以逗号分隔的计算机名称的列表。</span><span class="sxs-lookup"><span data-stu-id="c44fc-227">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="c44fc-228">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-228">The default is the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-229">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="c44fc-229">-ThrottleLimit</span></span>

<span data-ttu-id="c44fc-230">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="c44fc-230">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="c44fc-231">如果省略此参数或输入 0 值，则使用默认值 32。</span><span class="sxs-lookup"><span data-stu-id="c44fc-231">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="c44fc-232">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="c44fc-232">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-233">-TimeToLive</span><span class="sxs-lookup"><span data-stu-id="c44fc-233">-TimeToLive</span></span>

<span data-ttu-id="c44fc-234">指定数据包可被转发的最大次数。</span><span class="sxs-lookup"><span data-stu-id="c44fc-234">Specifies the maximum times a packet can be forwarded.</span></span> <span data-ttu-id="c44fc-235">对于网关和路由器等中的每个跃点， **TimeToLive** 值减少1。</span><span class="sxs-lookup"><span data-stu-id="c44fc-235">For every hop in gateways, routers etc. the **TimeToLive** value is decreased by one.</span></span> <span data-ttu-id="c44fc-236">如果为0，则丢弃数据包并返回错误。</span><span class="sxs-lookup"><span data-stu-id="c44fc-236">At zero the packet is discarded and an error is returned.</span></span>
<span data-ttu-id="c44fc-237">在 **Windows** 中，默认值为 **128** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-237">In **Windows** , The default value is **128** .</span></span> <span data-ttu-id="c44fc-238">**TimeToLive** 参数的别名是 **TTL** 。</span><span class="sxs-lookup"><span data-stu-id="c44fc-238">The alias of the **TimeToLive** parameter is **TTL** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c44fc-239">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="c44fc-239">-WsmanAuthentication</span></span>

<span data-ttu-id="c44fc-240">指定此 cmdlet 使用 WSMan 协议时用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="c44fc-240">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span>
<span data-ttu-id="c44fc-241">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="c44fc-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c44fc-242">基本</span><span class="sxs-lookup"><span data-stu-id="c44fc-242">Basic</span></span>
- <span data-ttu-id="c44fc-243">CredSSP</span><span class="sxs-lookup"><span data-stu-id="c44fc-243">CredSSP</span></span>
- <span data-ttu-id="c44fc-244">默认</span><span class="sxs-lookup"><span data-stu-id="c44fc-244">Default</span></span>
- <span data-ttu-id="c44fc-245">摘要</span><span class="sxs-lookup"><span data-stu-id="c44fc-245">Digest</span></span>
- <span data-ttu-id="c44fc-246">Kerberos</span><span class="sxs-lookup"><span data-stu-id="c44fc-246">Kerberos</span></span>
- <span data-ttu-id="c44fc-247">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="c44fc-247">Negotiate.</span></span>

<span data-ttu-id="c44fc-248">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="c44fc-248">The default value is Default.</span></span>

<span data-ttu-id="c44fc-249">有关此参数的值的详细信息，请参阅 [System.management.automation.runspaces.authenticationmechanism 枚举](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0)。</span><span class="sxs-lookup"><span data-stu-id="c44fc-249">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span></span>

<span data-ttu-id="c44fc-250">注意：在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。</span><span class="sxs-lookup"><span data-stu-id="c44fc-250">Caution: Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="c44fc-251">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="c44fc-251">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="c44fc-252">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="c44fc-252">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="c44fc-253">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="c44fc-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c44fc-254">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c44fc-254">CommonParameters</span></span>

<span data-ttu-id="c44fc-255">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c44fc-255">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c44fc-256">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c44fc-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c44fc-257">输入</span><span class="sxs-lookup"><span data-stu-id="c44fc-257">INPUTS</span></span>

### <span data-ttu-id="c44fc-258">无</span><span class="sxs-lookup"><span data-stu-id="c44fc-258">None</span></span>

<span data-ttu-id="c44fc-259">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c44fc-259">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c44fc-260">输出</span><span class="sxs-lookup"><span data-stu-id="c44fc-260">OUTPUTS</span></span>

### <span data-ttu-id="c44fc-261">System.Management.ManagementObject#root\cimv2\Win32_PingStatus、System.Management.Automation.RemotingJob、System.Boolean</span><span class="sxs-lookup"><span data-stu-id="c44fc-261">System.Management.ManagementObject#root\cimv2\Win32_PingStatus, System.Management.Automation.RemotingJob, System.Boolean</span></span>

<span data-ttu-id="c44fc-262">如果指定 **AsJob** 参数，则此 cmdlet 将返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="c44fc-262">This cmdlet returns a job object, if you specify the **AsJob** parameter.</span></span>

<span data-ttu-id="c44fc-263">如果指定 **Quiet** 参数，则它将返回一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="c44fc-263">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="c44fc-264">如果测试了多个连接，则返回 **布尔** 值的数组。</span><span class="sxs-lookup"><span data-stu-id="c44fc-264">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="c44fc-265">否则， `Test-Connection` 将为每个 ping 返回一个 **Win32_PingStatus** 对象。</span><span class="sxs-lookup"><span data-stu-id="c44fc-265">Otherwise, `Test-Connection` returns a **Win32_PingStatus** object for each ping.</span></span>

## <span data-ttu-id="c44fc-266">注释</span><span class="sxs-lookup"><span data-stu-id="c44fc-266">NOTES</span></span>

<span data-ttu-id="c44fc-267">此 cmdlet 使用 **Win32_PingStatus** 类。</span><span class="sxs-lookup"><span data-stu-id="c44fc-267">This cmdlet uses the **Win32_PingStatus** class.</span></span> <span data-ttu-id="c44fc-268">`Get-WMIObject Win32_PingStatus`命令等效于 `Test-Connection` 命令。</span><span class="sxs-lookup"><span data-stu-id="c44fc-268">A `Get-WMIObject Win32_PingStatus` command is equivalent to a `Test-Connection` command.</span></span>

<span data-ttu-id="c44fc-269">在 PowerShell 3.0 中引入了 **Source** 参数集。</span><span class="sxs-lookup"><span data-stu-id="c44fc-269">The **Source** parameter set was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="c44fc-270">相关链接</span><span class="sxs-lookup"><span data-stu-id="c44fc-270">RELATED LINKS</span></span>

[<span data-ttu-id="c44fc-271">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="c44fc-271">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="c44fc-272">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="c44fc-272">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="c44fc-273">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="c44fc-273">Stop-Computer</span></span>](Stop-Computer.md)
