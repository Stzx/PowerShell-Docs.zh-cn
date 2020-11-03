---
description: 提供有关基于 PowerShell 线程的作业的信息。 线程作业是一种后台作业，它在当前会话进程中的单独线程中运行命令或表达式。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 4951ac2c14c0685fbf2ead16bc52c64096231260
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "93200579"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="92282-105">关于线程作业</span><span class="sxs-lookup"><span data-stu-id="92282-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="92282-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="92282-106">Short description</span></span>

<span data-ttu-id="92282-107">提供有关基于 PowerShell 线程的作业的信息。</span><span class="sxs-lookup"><span data-stu-id="92282-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="92282-108">线程作业是一种后台作业，它在当前会话进程中的单独线程中运行命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="92282-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="92282-109">长说明</span><span class="sxs-lookup"><span data-stu-id="92282-109">Long description</span></span>

<span data-ttu-id="92282-110">本文介绍如何在本地计算机上的 PowerShell 中运行线程作业。</span><span class="sxs-lookup"><span data-stu-id="92282-110">This article explains how to run thread jobs in PowerShell on a local computer.</span></span>
<span data-ttu-id="92282-111">有关在本地计算机上运行后台作业的信息，请参阅 [about_Jobs](about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="92282-111">For information about running background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span>

<span data-ttu-id="92282-112">使用 cmdlet 启动线程作业 `Start-ThreadJob` 。</span><span class="sxs-lookup"><span data-stu-id="92282-112">Start a thread job by using the `Start-ThreadJob` cmdlet.</span></span> <span data-ttu-id="92282-113">此 cmdlet 在 PowerShell 随附的 **ThreadJob** 模块中提供。</span><span class="sxs-lookup"><span data-stu-id="92282-113">This cmdlet is available in the **ThreadJob** module that ships with PowerShell.</span></span>
<span data-ttu-id="92282-114">`Start-ThreadJob` 返回一个作业对象，该对象封装正在运行的命令或脚本，可与所有 PowerShell 作业操作 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="92282-114">`Start-ThreadJob` returns a single job object that encapsulates the running command or script, and can be used with all PowerShell job manipulating cmdlets.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="92282-115">作业 cmdlet</span><span class="sxs-lookup"><span data-stu-id="92282-115">The job cmdlets</span></span>

|<span data-ttu-id="92282-116">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="92282-116">Cmdlet</span></span>           |<span data-ttu-id="92282-117">说明</span><span class="sxs-lookup"><span data-stu-id="92282-117">Description</span></span>                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|<span data-ttu-id="92282-118">在本地计算机上启动线程作业。</span><span class="sxs-lookup"><span data-stu-id="92282-118">Starts a thread job on a local computer.</span></span>               |
|`Get-Job`        |<span data-ttu-id="92282-119">获取在当前会话中启动的作业。</span><span class="sxs-lookup"><span data-stu-id="92282-119">Gets the jobs that were started in the current session.</span></span>|
|`Receive-Job`    |<span data-ttu-id="92282-120">获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="92282-120">Gets the results of jobs.</span></span>                              |
|`Stop-Job`       |<span data-ttu-id="92282-121">停止正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="92282-121">Stops a running job.</span></span>                                   |
|`Wait-Job`       |<span data-ttu-id="92282-122">禁止显示命令提示符，直到其中一个或所有作业都为</span><span class="sxs-lookup"><span data-stu-id="92282-122">Suppresses the command prompt until one or all jobs are</span></span>|
|                 |<span data-ttu-id="92282-123">完成.</span><span class="sxs-lookup"><span data-stu-id="92282-123">complete.</span></span>                                              |
|`Remove-Job`     |<span data-ttu-id="92282-124">删除作业。</span><span class="sxs-lookup"><span data-stu-id="92282-124">Deletes a job.</span></span>                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a><span data-ttu-id="92282-125">如何在本地计算机上启动线程作业</span><span class="sxs-lookup"><span data-stu-id="92282-125">How to start a thread job on the local computer</span></span>

<span data-ttu-id="92282-126">若要在本地计算机上启动线程作业，请使用 `Start-ThreadJob` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92282-126">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet.</span></span>

<span data-ttu-id="92282-127">若要编写 `Start-ThreadJob` 命令，请将该命令或脚本括在大括号中， (`{ }`) 。</span><span class="sxs-lookup"><span data-stu-id="92282-127">To write a `Start-ThreadJob` command, enclose the command or script the job runs in curly braces (`{ }`).</span></span>

<span data-ttu-id="92282-128">下面的命令启动在 `Get-Process` 本地计算机上运行命令的线程作业。</span><span class="sxs-lookup"><span data-stu-id="92282-128">The following command starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="92282-129">该 `Start-ThreadJob` 命令将返回一个 `ThreadJob` 对象，该对象表示正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="92282-129">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="92282-130">作业对象包含有关作业的有用信息，包括作业的当前运行状态。</span><span class="sxs-lookup"><span data-stu-id="92282-130">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="92282-131">它在生成结果时收集作业的结果。</span><span class="sxs-lookup"><span data-stu-id="92282-131">It collects the results of the job as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="92282-132">如何等待作业完成并检索作业结果</span><span class="sxs-lookup"><span data-stu-id="92282-132">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="92282-133">你可以使用 PowerShell 作业 cmdlet （如 `Wait-Job` 和） `Receive-Job` 等待作业完成，然后返回作业生成的所有结果。</span><span class="sxs-lookup"><span data-stu-id="92282-133">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="92282-134">下面的命令启动一个运行命令的线程作业 `Get-Process` ，然后等待该命令完成，最后返回该命令生成的所有数据结果。</span><span class="sxs-lookup"><span data-stu-id="92282-134">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

## <a name="powershell-concurrency-and-jobs"></a><span data-ttu-id="92282-135">PowerShell 并发和作业</span><span class="sxs-lookup"><span data-stu-id="92282-135">PowerShell concurrency and jobs</span></span>

<span data-ttu-id="92282-136">PowerShell 并发运行命令，并通过作业编写脚本。</span><span class="sxs-lookup"><span data-stu-id="92282-136">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="92282-137">PowerShell 提供了三个基于作业的解决方案来支持并发。</span><span class="sxs-lookup"><span data-stu-id="92282-137">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="92282-138">作业</span><span class="sxs-lookup"><span data-stu-id="92282-138">Job</span></span>            |<span data-ttu-id="92282-139">说明</span><span class="sxs-lookup"><span data-stu-id="92282-139">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="92282-140">命令和脚本在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="92282-140">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="92282-141">命令和脚本在本地的单独进程中运行</span><span class="sxs-lookup"><span data-stu-id="92282-141">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="92282-142">虚拟 CPU。</span><span class="sxs-lookup"><span data-stu-id="92282-142">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="92282-143">命令和脚本在同一内的单独线程中运行</span><span class="sxs-lookup"><span data-stu-id="92282-143">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="92282-144">在本地计算机上进行处理。</span><span class="sxs-lookup"><span data-stu-id="92282-144">process on the local machine.</span></span>                                |

<span data-ttu-id="92282-145">每种类型的作业都有其优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="92282-145">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="92282-146">在单独的计算机上或在单独的进程中远程运行脚本具有很好的隔离。</span><span class="sxs-lookup"><span data-stu-id="92282-146">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="92282-147">任何错误不会影响其他正在运行的作业或启动该作业的客户端。</span><span class="sxs-lookup"><span data-stu-id="92282-147">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="92282-148">但远程处理层增加了开销，包括对象序列化。</span><span class="sxs-lookup"><span data-stu-id="92282-148">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="92282-149">所有传递到远程会话的对象都必须进行序列化，然后在客户端与目标会话之间传递时进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="92282-149">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="92282-150">对于大型复杂数据对象，序列化操作可以使用很多计算资源和内存资源。</span><span class="sxs-lookup"><span data-stu-id="92282-150">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

## <a name="powershell-thread-based-jobs"></a><span data-ttu-id="92282-151">基于 PowerShell 线程的作业</span><span class="sxs-lookup"><span data-stu-id="92282-151">PowerShell thread based jobs</span></span>

<span data-ttu-id="92282-152">基于线程的作业不像远程和后台作业那样可靠，因为它们在不同线程上的同一进程中运行。</span><span class="sxs-lookup"><span data-stu-id="92282-152">Thread based jobs are not as robust as Remote and Background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="92282-153">如果一个作业发生了导致进程崩溃的严重错误，则该进程中的所有其他作业也会失败。</span><span class="sxs-lookup"><span data-stu-id="92282-153">If one job has a critical error that crashes the process, then all other jobs in the process will also fail.</span></span>

<span data-ttu-id="92282-154">但是，基于线程的作业的开销更少。</span><span class="sxs-lookup"><span data-stu-id="92282-154">However, thread-based jobs have much less overhead.</span></span> <span data-ttu-id="92282-155">它们不需要使用远程层或序列化。</span><span class="sxs-lookup"><span data-stu-id="92282-155">They don't need to use the remoting layer or serialization.</span></span> <span data-ttu-id="92282-156">结果是基于线程的作业的运行速度要快得多，且使用的资源比其他作业类型要少得多。</span><span class="sxs-lookup"><span data-stu-id="92282-156">The result is that thread-based jobs tend to run much faster and use far less resources than the other job types.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="92282-157">线程作业性能</span><span class="sxs-lookup"><span data-stu-id="92282-157">Thread job performance</span></span>

<span data-ttu-id="92282-158">与其他类型的作业相比，线程作业的权重更快且更轻。</span><span class="sxs-lookup"><span data-stu-id="92282-158">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="92282-159">但与作业正在进行的工作相比，它们的开销可能会很大。</span><span class="sxs-lookup"><span data-stu-id="92282-159">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="92282-160">PowerShell 在会话中运行命令和脚本。</span><span class="sxs-lookup"><span data-stu-id="92282-160">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="92282-161">会话中一次只能运行一个命令或脚本。</span><span class="sxs-lookup"><span data-stu-id="92282-161">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="92282-162">因此，在运行多个作业时，每个作业都在单独的会话中运行。</span><span class="sxs-lookup"><span data-stu-id="92282-162">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="92282-163">每个会话都可提供开销。</span><span class="sxs-lookup"><span data-stu-id="92282-163">Each session contributes to the overhead.</span></span>

<span data-ttu-id="92282-164">当执行的工作大于用于运行作业的会话的开销时，线程作业可提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="92282-164">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="92282-165">满足此条件的情况有两种情况。</span><span class="sxs-lookup"><span data-stu-id="92282-165">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="92282-166">工作是计算密集型-在多个线程作业上运行脚本可充分利用多个处理器核心并更快完成。</span><span class="sxs-lookup"><span data-stu-id="92282-166">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="92282-167">工作包括大量等待时间的脚本，该脚本花费时间等待 i/o 或远程调用结果。</span><span class="sxs-lookup"><span data-stu-id="92282-167">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="92282-168">并行运行通常比按顺序运行快。</span><span class="sxs-lookup"><span data-stu-id="92282-168">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

<span data-ttu-id="92282-169">上面的第一个示例显示了一个 foreach 循环，该循环创建1000线程作业来编写简单的字符串。</span><span class="sxs-lookup"><span data-stu-id="92282-169">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="92282-170">由于作业开销，需要超过33秒钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="92282-170">Due to job overhead, it takes over 33 seconds to complete.</span></span>

<span data-ttu-id="92282-171">第二个示例运行 `ForEach` cmdlet 来执行相同的1000操作，并按顺序执行每个字符串写入，无需任何作业开销。</span><span class="sxs-lookup"><span data-stu-id="92282-171">The second example runs the `ForEach` cmdlet to do the same 1000 operations and each string write is executed sequentially without any job overhead.</span></span> <span data-ttu-id="92282-172">它只会在25毫秒内完成。</span><span class="sxs-lookup"><span data-stu-id="92282-172">It completes in a mere 25 milliseconds.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

<span data-ttu-id="92282-173">在上面的示例中，最多可以为10个单独的系统日志收集5000个条目。</span><span class="sxs-lookup"><span data-stu-id="92282-173">In the above example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="92282-174">由于脚本涉及到读取多个日志，因此有必要并行执行操作。</span><span class="sxs-lookup"><span data-stu-id="92282-174">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span> <span data-ttu-id="92282-175">并且作业的完成时间比脚本按顺序运行的时间快两倍。</span><span class="sxs-lookup"><span data-stu-id="92282-175">And the job completes over twice as fast as when the script is run sequentially.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="92282-176">线程作业和变量</span><span class="sxs-lookup"><span data-stu-id="92282-176">Thread jobs and variables</span></span>

<span data-ttu-id="92282-177">变量以各种方式传递到线程作业中。</span><span class="sxs-lookup"><span data-stu-id="92282-177">Variables are passed into thread jobs in various ways.</span></span>

<span data-ttu-id="92282-178">`Start-ThreadJob` 可以接受通过管道传递给脚本块的、通过关键字传递到脚本块的变量， `$using` 也可以通过 **ArgumentList** 参数传入。</span><span class="sxs-lookup"><span data-stu-id="92282-178">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

<span data-ttu-id="92282-179">由于线程作业在同一进程中运行，因此必须仔细对待传入作业的任何变量引用类型。</span><span class="sxs-lookup"><span data-stu-id="92282-179">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="92282-180">如果它不是线程安全对象，则绝不应将其分配给，并且永远不应在其上调用方法和属性。</span><span class="sxs-lookup"><span data-stu-id="92282-180">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

<span data-ttu-id="92282-181">上面的示例将一个线程安全的 dotNet `ConcurrentDictionary` 对象传递给所有子作业，以收集唯一命名的进程对象。</span><span class="sxs-lookup"><span data-stu-id="92282-181">The above example passes a thread safe dotNet `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="92282-182">由于它是线程安全对象，因此可以安全地使用该对象，同时在进程中同时运行作业。</span><span class="sxs-lookup"><span data-stu-id="92282-182">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

## <a name="see-also"></a><span data-ttu-id="92282-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92282-183">See also</span></span>

- [<span data-ttu-id="92282-184">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="92282-184">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="92282-185">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="92282-185">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="92282-186">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="92282-186">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="92282-187">about_Remote</span><span class="sxs-lookup"><span data-stu-id="92282-187">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="92282-188">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="92282-188">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="92282-189">Start-Job</span><span class="sxs-lookup"><span data-stu-id="92282-189">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="92282-190">Get-Job</span><span class="sxs-lookup"><span data-stu-id="92282-190">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="92282-191">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="92282-191">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="92282-192">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="92282-192">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="92282-193">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="92282-193">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="92282-194">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="92282-194">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
