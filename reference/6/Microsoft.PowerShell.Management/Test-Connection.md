---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197479"
---
# <span data-ttu-id="716bd-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="716bd-103">Test-Connection</span></span>

## <span data-ttu-id="716bd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="716bd-104">SYNOPSIS</span></span>
<span data-ttu-id="716bd-105">将 ICMP 回显请求数据包或 ping 发送到一台或多台计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="716bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="716bd-106">SYNTAX</span></span>

### <span data-ttu-id="716bd-107">PingCount (默认值) </span><span class="sxs-lookup"><span data-stu-id="716bd-107">PingCount (Default)</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="716bd-108">PingContinues</span><span class="sxs-lookup"><span data-stu-id="716bd-108">PingContinues</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="716bd-109">DetectionOfMTUSize</span><span class="sxs-lookup"><span data-stu-id="716bd-109">DetectionOfMTUSize</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="716bd-110">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="716bd-110">TraceRoute</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="716bd-111">ConnectionByTCPPort</span><span class="sxs-lookup"><span data-stu-id="716bd-111">ConnectionByTCPPort</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="716bd-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="716bd-112">DESCRIPTION</span></span>

<span data-ttu-id="716bd-113">`Test-Connection`Cmdlet 将 Internet 控制消息协议 () ICMP 发送到一台或多台远程计算机并返回回显响应回复。</span><span class="sxs-lookup"><span data-stu-id="716bd-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="716bd-114">可以使用此 cmdlet 来确定是否可以通过 IP 网络联系特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="716bd-115">您可以使用的参数 `Test-Connection` 同时指定发送计算机和接收计算机，将该命令作为后台作业运行，设置超时和 ping 数目，以及配置连接和身份验证。</span><span class="sxs-lookup"><span data-stu-id="716bd-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="716bd-116">与熟悉的 **ping** 命令不同， `Test-Connection` 返回可以在 PowerShell 中调查的 **TestConnectionCommand + PingReport** 对象。</span><span class="sxs-lookup"><span data-stu-id="716bd-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingReport** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="716bd-117">**Quiet** 参数为每个已测试的连接返回 **system.object** 对象中的 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="716bd-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="716bd-118">如果测试了多个连接，则返回 **布尔** 值的数组。</span><span class="sxs-lookup"><span data-stu-id="716bd-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="716bd-119">示例</span><span class="sxs-lookup"><span data-stu-id="716bd-119">EXAMPLES</span></span>

### <span data-ttu-id="716bd-120">示例1：向远程计算机发送回显请求</span><span class="sxs-lookup"><span data-stu-id="716bd-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="716bd-121">此示例将来自本地计算机的回显请求数据包发送到 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

<span data-ttu-id="716bd-122">`Test-Connection` 使用 **TargetName** 参数指定 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="716bd-123">**IPv4** 参数指定测试的协议。</span><span class="sxs-lookup"><span data-stu-id="716bd-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="716bd-124">在发送到 **成功** 流的 **TestConnectionCommand + PingReport** 对象时，会将 Ping 输出发送到 **信息流** 。</span><span class="sxs-lookup"><span data-stu-id="716bd-124">The ping output is sent to the **Information** stream while the **TestConnectionCommand+PingReport** object sent to the **Success** stream.</span></span> <span data-ttu-id="716bd-125">有关输出流的详细信息，请参阅 [about_Redirection](../microsoft.powershell.core/about/about_redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="716bd-125">For more information about the output streams, see [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span></span>

### <span data-ttu-id="716bd-126">示例2：将回显请求发送到多台计算机</span><span class="sxs-lookup"><span data-stu-id="716bd-126">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="716bd-127">此示例将来自本地计算机的 ping 发送到多台远程计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-127">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="716bd-128">示例3：从多台计算机向计算机发送回显请求</span><span class="sxs-lookup"><span data-stu-id="716bd-128">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="716bd-129">此示例将来自不同源计算机的 ping 发送到一台远程计算机 Server01。</span><span class="sxs-lookup"><span data-stu-id="716bd-129">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

<span data-ttu-id="716bd-130">使用此命令格式可从多个点来测试连接的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="716bd-130">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="716bd-131">示例4：使用参数自定义测试命令</span><span class="sxs-lookup"><span data-stu-id="716bd-131">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="716bd-132">此示例使用的参数 `Test-Connection` 自定义命令。</span><span class="sxs-lookup"><span data-stu-id="716bd-132">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="716bd-133">本地计算机将 ping 测试发送到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-133">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="716bd-134">`Test-Connection` 使用 **TargetName** 参数指定 Server01。</span><span class="sxs-lookup"><span data-stu-id="716bd-134">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="716bd-135">**Count** 参数指定三个 ping 发送到 Server01 计算机， **延迟** 为2秒的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="716bd-135">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="716bd-136">当 ping 响应预计需要比平时更长的时间（因为有扩展的跃点数或高流量网络条件）时，可以使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="716bd-136">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="716bd-137">示例5：将测试作为后台作业运行</span><span class="sxs-lookup"><span data-stu-id="716bd-137">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="716bd-138">此示例演示如何将 `Test-Connection` 命令作为 PowerShell 后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="716bd-138">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

<span data-ttu-id="716bd-139">该 `Start-Job` 命令使用 `Test-Connection` cmdlet 对企业中的多台计算机执行 ping 操作。</span><span class="sxs-lookup"><span data-stu-id="716bd-139">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="716bd-140">**TargetName** 参数的值是一个 `Get-Content` 命令，该命令从文件中读取计算机名称的列表 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="716bd-140">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="716bd-141">该命令使用 `Start-Job` cmdlet 将命令作为后台作业运行，并将作业保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="716bd-141">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="716bd-142">此 `if` 命令会检查该作业是否仍在运行。</span><span class="sxs-lookup"><span data-stu-id="716bd-142">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="716bd-143">如果该作业未运行， `Receive-Job` 将获取结果并将其存储在 `$Results` 变量中。</span><span class="sxs-lookup"><span data-stu-id="716bd-143">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="716bd-144">示例6：仅在连接测试成功时创建会话</span><span class="sxs-lookup"><span data-stu-id="716bd-144">Example 6: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="716bd-145">仅当至少一个发送到计算机的 ping 成功时，此示例才会在 Server01 计算机上创建一个会话。</span><span class="sxs-lookup"><span data-stu-id="716bd-145">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="716bd-146">该 `if` 命令使用 `Test-Connection` Cmdlet 对 Server01 计算机进行 ping 操作。</span><span class="sxs-lookup"><span data-stu-id="716bd-146">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="716bd-147">该命令使用 **Quiet** 参数，该参数将返回一个 **布尔** 值，而不是 **TestConnectionCommand + PingReport** 对象。</span><span class="sxs-lookup"><span data-stu-id="716bd-147">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **TestConnectionCommand+PingReport** object.</span></span>

<span data-ttu-id="716bd-148">`$True`如果四个 ping 中有任何一个成功，则值为。</span><span class="sxs-lookup"><span data-stu-id="716bd-148">The value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="716bd-149">如果没有任何 ping 成功，则该值为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="716bd-149">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="716bd-150">如果 `Test-Connection` 命令返回的值 `$True` ，则该命令将使用 `New-PSSession` cmdlet 创建 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="716bd-150">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

### <span data-ttu-id="716bd-151">示例7：使用 Traceroute 参数</span><span class="sxs-lookup"><span data-stu-id="716bd-151">Example 7: Use the Traceroute parameter</span></span>

<span data-ttu-id="716bd-152">从 PowerShell 6.0 开始， **Traceroute** 参数会在本地计算机与你指定的远程目标与 **TargetName** 参数之间映射路由。</span><span class="sxs-lookup"><span data-stu-id="716bd-152">Beginning in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

<span data-ttu-id="716bd-153">该 `Test-Connection` 命令使用 **Traceroute** 参数。</span><span class="sxs-lookup"><span data-stu-id="716bd-153">The `Test-Connection` command uses the **Traceroute** parameter.</span></span> <span data-ttu-id="716bd-154">结果（是 `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` 对象）将通过管道传递给 `ForEach-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="716bd-154">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objects, are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="716bd-155">`ForEach-Object` 创建包含的 `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` 对象和后续对象的结构化的输出 `[System.Net.NetworkInformation.PingReply]` 。</span><span class="sxs-lookup"><span data-stu-id="716bd-155">`ForEach-Object` creates a structured output of the contained `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objects and subsequent `[System.Net.NetworkInformation.PingReply]` objects.</span></span>

## <span data-ttu-id="716bd-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="716bd-156">PARAMETERS</span></span>

### <span data-ttu-id="716bd-157">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="716bd-157">-BufferSize</span></span>

<span data-ttu-id="716bd-158">指定使用此命令发送的缓冲区的大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="716bd-158">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="716bd-159">默认值为 32。</span><span class="sxs-lookup"><span data-stu-id="716bd-159">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-160">-Count</span><span class="sxs-lookup"><span data-stu-id="716bd-160">-Count</span></span>

<span data-ttu-id="716bd-161">指定要发送的回显请求数。</span><span class="sxs-lookup"><span data-stu-id="716bd-161">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="716bd-162">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="716bd-162">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-163">-Delay</span><span class="sxs-lookup"><span data-stu-id="716bd-163">-Delay</span></span>

<span data-ttu-id="716bd-164">指定两次 ping 操作之间的间隔时间，以秒为单位。</span><span class="sxs-lookup"><span data-stu-id="716bd-164">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-165">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="716bd-165">-DontFragment</span></span>

<span data-ttu-id="716bd-166">此参数设置 IP 标头中的 " **不分段** " 标志。</span><span class="sxs-lookup"><span data-stu-id="716bd-166">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="716bd-167">可以将此参数与 **BufferSize** 参数一起使用来测试路径 MTU 大小。</span><span class="sxs-lookup"><span data-stu-id="716bd-167">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="716bd-168">有关路径 MTU 的详细信息，请参阅维基百科中的 [PATH Mtu 发现](https://wikipedia.org/wiki/Path_MTU_Discovery) 文章。</span><span class="sxs-lookup"><span data-stu-id="716bd-168">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-169">-IPv4</span><span class="sxs-lookup"><span data-stu-id="716bd-169">-IPv4</span></span>

<span data-ttu-id="716bd-170">强制 cmdlet 使用 IPv4 协议进行测试。</span><span class="sxs-lookup"><span data-stu-id="716bd-170">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

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

### <span data-ttu-id="716bd-171">-IPv6</span><span class="sxs-lookup"><span data-stu-id="716bd-171">-IPv6</span></span>

<span data-ttu-id="716bd-172">强制 cmdlet 使用 IPv6 协议进行测试。</span><span class="sxs-lookup"><span data-stu-id="716bd-172">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

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

### <span data-ttu-id="716bd-173">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="716bd-173">-MaxHops</span></span>

<span data-ttu-id="716bd-174">设置可发送 ICMP 请求消息的最大跃点数。</span><span class="sxs-lookup"><span data-stu-id="716bd-174">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="716bd-175">默认值由操作系统控制。</span><span class="sxs-lookup"><span data-stu-id="716bd-175">The default value is controlled by the operating system.</span></span> <span data-ttu-id="716bd-176">Windows 10 的默认值为128跃点。</span><span class="sxs-lookup"><span data-stu-id="716bd-176">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-177">-Ping</span><span class="sxs-lookup"><span data-stu-id="716bd-177">-Ping</span></span>

<span data-ttu-id="716bd-178">使 cmdlet 执行 ping 测试，这是默认操作。</span><span class="sxs-lookup"><span data-stu-id="716bd-178">Causes the cmdlet to do a ping test, which is the default action.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-179">-Quiet</span><span class="sxs-lookup"><span data-stu-id="716bd-179">-Quiet</span></span>

<span data-ttu-id="716bd-180">**Quiet** 参数返回 **system.object** 对象中的 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="716bd-180">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="716bd-181">使用此参数将取消所有错误。</span><span class="sxs-lookup"><span data-stu-id="716bd-181">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="716bd-182">所测试的每个连接都将返回一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="716bd-182">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="716bd-183">如果 **TargetName** 参数指定了多台计算机，则返回 **布尔** 值的数组。</span><span class="sxs-lookup"><span data-stu-id="716bd-183">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="716bd-184">如果 **任何** ping 成功， `$True` 则返回。</span><span class="sxs-lookup"><span data-stu-id="716bd-184">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="716bd-185">如果 **所有** ping `$False` 操作都失败，则返回。</span><span class="sxs-lookup"><span data-stu-id="716bd-185">If **all** pings fail, `$False` is returned.</span></span>

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

### <span data-ttu-id="716bd-186">-ResolveDestination</span><span class="sxs-lookup"><span data-stu-id="716bd-186">-ResolveDestination</span></span>

<span data-ttu-id="716bd-187">导致 cmdlet 尝试解析目标的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="716bd-187">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span>

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

### <span data-ttu-id="716bd-188">-Source</span><span class="sxs-lookup"><span data-stu-id="716bd-188">-Source</span></span>

<span data-ttu-id="716bd-189">指定发出 ping 请求的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="716bd-189">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="716bd-190">请输入以逗号分隔的计算机名称的列表。</span><span class="sxs-lookup"><span data-stu-id="716bd-190">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="716bd-191">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-191">The default is the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="716bd-192">-TargetName</span></span>

<span data-ttu-id="716bd-193">指定要测试的计算机。</span><span class="sxs-lookup"><span data-stu-id="716bd-193">Specifies the computers to test.</span></span> <span data-ttu-id="716bd-194">请键入计算机名称或者以 IPv4 或 IPv6 格式键入 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="716bd-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="716bd-195">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="716bd-195">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="716bd-196">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="716bd-196">This parameter is required.</span></span> <span data-ttu-id="716bd-197">**ComputerName** 是此参数的别名。</span><span class="sxs-lookup"><span data-stu-id="716bd-197">**ComputerName** is an alias for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-198">-TCPPort</span><span class="sxs-lookup"><span data-stu-id="716bd-198">-TCPPort</span></span>

<span data-ttu-id="716bd-199">指定要在 TCP 连接测试中使用的目标上的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="716bd-199">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="716bd-200">Cmdlet 将尝试与目标上的指定端口建立 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="716bd-200">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-201">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="716bd-201">-TimeoutSeconds</span></span>

<span data-ttu-id="716bd-202">设置测试的超时值。</span><span class="sxs-lookup"><span data-stu-id="716bd-202">Sets the timeout value for the test.</span></span> <span data-ttu-id="716bd-203">如果在超时过期之前未收到响应，则测试失败。</span><span class="sxs-lookup"><span data-stu-id="716bd-203">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="716bd-204">默认值为 5 秒。</span><span class="sxs-lookup"><span data-stu-id="716bd-204">The default is five seconds.</span></span>

<span data-ttu-id="716bd-205">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="716bd-205">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-206">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="716bd-206">-Traceroute</span></span>

<span data-ttu-id="716bd-207">导致 cmdlet 执行 traceroute 测试。</span><span class="sxs-lookup"><span data-stu-id="716bd-207">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="716bd-208">使用此参数时，该 cmdlet 将返回一个 `TestConnectionCommand+TraceRouteResult` 对象。</span><span class="sxs-lookup"><span data-stu-id="716bd-208">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceRouteResult` object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-209">-继续</span><span class="sxs-lookup"><span data-stu-id="716bd-209">-Continues</span></span>

<span data-ttu-id="716bd-210">使 cmdlet 持续发送 ping 请求。</span><span class="sxs-lookup"><span data-stu-id="716bd-210">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="716bd-211">此参数不能与 **Count** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="716bd-211">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-212">-MTUSizeDetect</span><span class="sxs-lookup"><span data-stu-id="716bd-212">-MTUSizeDetect</span></span>

<span data-ttu-id="716bd-213">此参数用于发现路径 MTU 大小。</span><span class="sxs-lookup"><span data-stu-id="716bd-213">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="716bd-214">Cmdlet 将返回 **PingReply # MTUSize** 对象，其中包含目标的路径 MTU 大小。</span><span class="sxs-lookup"><span data-stu-id="716bd-214">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="716bd-215">有关路径 MTU 的详细信息，请参阅维基百科中的 [PATH Mtu 发现](https://wikipedia.org/wiki/Path_MTU_Discovery) 文章。</span><span class="sxs-lookup"><span data-stu-id="716bd-215">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="716bd-216">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="716bd-216">CommonParameters</span></span>

<span data-ttu-id="716bd-217">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="716bd-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="716bd-218">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="716bd-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="716bd-219">输入</span><span class="sxs-lookup"><span data-stu-id="716bd-219">INPUTS</span></span>

### <span data-ttu-id="716bd-220">无</span><span class="sxs-lookup"><span data-stu-id="716bd-220">None</span></span>

<span data-ttu-id="716bd-221">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="716bd-221">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="716bd-222">输出</span><span class="sxs-lookup"><span data-stu-id="716bd-222">OUTPUTS</span></span>

### <span data-ttu-id="716bd-223">TestConnectionCommand + PingReport、TestConnectionCommand + TraceRouteResult、Boolean、PingReply # MTUSize</span><span class="sxs-lookup"><span data-stu-id="716bd-223">TestConnectionCommand+PingReport, TestConnectionCommand+TraceRouteResult, Boolean, PingReply#MTUSize</span></span>

<span data-ttu-id="716bd-224">如果指定 **Quiet** 参数，则它将返回一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="716bd-224">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="716bd-225">如果测试了多个连接，则返回 **布尔** 值的数组。</span><span class="sxs-lookup"><span data-stu-id="716bd-225">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="716bd-226">否则， `Test-Connection` 将为每个 ping 返回一个 **TestConnectionCommand + PingReport** 对象。</span><span class="sxs-lookup"><span data-stu-id="716bd-226">Otherwise, `Test-Connection` returns a **TestConnectionCommand+PingReport** object for each ping.</span></span>

## <span data-ttu-id="716bd-227">注释</span><span class="sxs-lookup"><span data-stu-id="716bd-227">NOTES</span></span>

## <span data-ttu-id="716bd-228">相关链接</span><span class="sxs-lookup"><span data-stu-id="716bd-228">RELATED LINKS</span></span>

[<span data-ttu-id="716bd-229">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="716bd-229">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="716bd-230">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="716bd-230">Stop-Computer</span></span>](Stop-Computer.md)
