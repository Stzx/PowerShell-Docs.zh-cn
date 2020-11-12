---
description: 描述如何在远程计算机上运行作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 71f59fcb8e656e4ac439028507f15cf36b8402f6
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524920"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="746ae-104">关于远程作业</span><span class="sxs-lookup"><span data-stu-id="746ae-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="746ae-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="746ae-105">Short Description</span></span>
<span data-ttu-id="746ae-106">描述如何在远程计算机上运行作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-106">Describes how to run jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="746ae-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="746ae-107">Detailed Description</span></span>

<span data-ttu-id="746ae-108">PowerShell 通过作业并发运行命令和脚本。</span><span class="sxs-lookup"><span data-stu-id="746ae-108">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="746ae-109">PowerShell 提供三种作业类型来支持并发。</span><span class="sxs-lookup"><span data-stu-id="746ae-109">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="746ae-110">`RemoteJob` -命令和脚本在远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="746ae-110">`RemoteJob` - Commands and scripts run in a remote session.</span></span>
- <span data-ttu-id="746ae-111">`BackgroundJob` -命令和脚本在本地计算机上的单独进程中运行。</span><span class="sxs-lookup"><span data-stu-id="746ae-111">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="746ae-112">有关详细信息，请参阅 [about_Jobs](about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="746ae-112">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="746ae-113">`PSTaskJob` 或 `ThreadJob` -命令和脚本在本地计算机上的同一进程内的单独线程中运行。</span><span class="sxs-lookup"><span data-stu-id="746ae-113">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="746ae-114">有关详细信息，请参阅 [about_Thread_Jobs](about_Thread_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="746ae-114">For more information, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="746ae-115">在单独的计算机上或在单独的进程中远程运行脚本可提供强大的隔离。</span><span class="sxs-lookup"><span data-stu-id="746ae-115">Running scripts remotely, on a separate machine or in a separate process, provide great isolation.</span></span> <span data-ttu-id="746ae-116">远程作业中发生的任何错误都不会影响其他正在运行的作业或启动作业的父会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-116">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="746ae-117">但是，远程处理层增加了开销，包括对象序列化。</span><span class="sxs-lookup"><span data-stu-id="746ae-117">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="746ae-118">所有对象都将进行序列化和反序列化，因为在父会话与远程 (作业) 会话之间传递它们。</span><span class="sxs-lookup"><span data-stu-id="746ae-118">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="746ae-119">大型复杂数据对象的序列化会消耗大量的计算和内存资源，并跨网络传输大量数据。</span><span class="sxs-lookup"><span data-stu-id="746ae-119">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="746ae-120">创建作业的父会话还会监视作业状态和收集管道数据。</span><span class="sxs-lookup"><span data-stu-id="746ae-120">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="746ae-121">作业到达完成状态后，父进程终止了作业子进程。</span><span class="sxs-lookup"><span data-stu-id="746ae-121">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="746ae-122">如果终止了父会话，则所有正在运行的子作业都将与其子进程一起终止。</span><span class="sxs-lookup"><span data-stu-id="746ae-122">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="746ae-123">可通过两种方法解决此问题：</span><span class="sxs-lookup"><span data-stu-id="746ae-123">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="746ae-124">用于 `Invoke-Command` 创建在断开连接的会话中运行的作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-124">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="746ae-125">请参阅本文中的 [分离进程](#how-to-run-as-a-detached-process) 部分。</span><span class="sxs-lookup"><span data-stu-id="746ae-125">See the [detached processes](#how-to-run-as-a-detached-process) section of this article.</span></span>
1. <span data-ttu-id="746ae-126">使用 `Start-Process` 创建新进程，而不是作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-126">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="746ae-127">有关详细信息，请参阅 [开始处理](xref:Microsoft.PowerShell.Management.Start-Process)。</span><span class="sxs-lookup"><span data-stu-id="746ae-127">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="remote-jobs"></a><span data-ttu-id="746ae-128">远程作业</span><span class="sxs-lookup"><span data-stu-id="746ae-128">Remote Jobs</span></span>

<span data-ttu-id="746ae-129">您可以使用三种不同的方法在远程计算机上运行作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-129">You can run jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="746ae-130">在远程计算机上启动交互式会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-130">Start an interactive session on a remote computer.</span></span> <span data-ttu-id="746ae-131">然后在交互式会话中启动作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-131">Then start a job in the interactive session.</span></span> <span data-ttu-id="746ae-132">尽管所有操作都是在远程计算机上执行的，但过程与运行本地作业相同。</span><span class="sxs-lookup"><span data-stu-id="746ae-132">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="746ae-133">在将其结果返回到本地计算机的远程计算机上运行作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-133">Run a job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="746ae-134">如果要收集作业的结果并在本地计算机上的一个中心位置维护这些作业的结果，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="746ae-134">Use this method when you want to collect the results of jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="746ae-135">在远程计算机上运行作业，该作业在远程计算机上维护其结果。</span><span class="sxs-lookup"><span data-stu-id="746ae-135">Run a job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="746ae-136">在源计算机上更安全地维护作业数据时使用此方法。</span><span class="sxs-lookup"><span data-stu-id="746ae-136">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-job-in-an-interactive-session"></a><span data-ttu-id="746ae-137">在交互式会话中启动作业</span><span class="sxs-lookup"><span data-stu-id="746ae-137">Start a job in an interactive session</span></span>

<span data-ttu-id="746ae-138">您可以启动与远程计算机的交互式会话，然后在交互式会话过程中启动作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-138">You can start an interactive session with a remote computer and then start a job during the interactive session.</span></span> <span data-ttu-id="746ae-139">有关交互式会话的详细信息，请参阅 about_Remote，并参阅 `Enter-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="746ae-139">For more information about interactive sessions, see about_Remote, and see `Enter-PSSession`.</span></span>

<span data-ttu-id="746ae-140">在交互式会话中启动作业的过程与在本地计算机上启动后台作业的过程几乎相同。</span><span class="sxs-lookup"><span data-stu-id="746ae-140">The procedure for starting a job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="746ae-141">但是，所有操作都在远程计算机上执行，而不是在本地计算机上进行。</span><span class="sxs-lookup"><span data-stu-id="746ae-141">However, all of the operations occur on the remote computer, not the local computer.</span></span>

1. <span data-ttu-id="746ae-142">使用 `Enter-PSSession` cmdlet 来启动与远程计算机的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-142">Use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="746ae-143">您可以使用 ComputerName 参数 `Enter-PSSession` 为交互式会话建立临时连接。</span><span class="sxs-lookup"><span data-stu-id="746ae-143">You can use the ComputerName parameter of `Enter-PSSession` to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="746ae-144">或者，可以使用 Session 参数 (PSSession) 在 PowerShell 会话中运行交互式会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-144">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

   <span data-ttu-id="746ae-145">以下命令在 Server01 计算机上启动交互式会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-145">The following command starts an interactive session on the Server01 computer.</span></span>

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   <span data-ttu-id="746ae-146">命令提示符更改为显示你现在已连接到 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="746ae-146">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

   ```
   Server01\C:>
   ```

1. <span data-ttu-id="746ae-147">若要在会话中启动远程作业，请使用 `Start-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-147">To start a remote job in the session, use the `Start-Job` cmdlet.</span></span> <span data-ttu-id="746ae-148">以下命令运行远程作业，该作业获取 Server01 计算机上的 Windows PowerShell 事件日志中的事件。</span><span class="sxs-lookup"><span data-stu-id="746ae-148">The following command runs a remote job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="746ae-149">`Start-Job`Cmdlet 将返回表示作业的对象。</span><span class="sxs-lookup"><span data-stu-id="746ae-149">The `Start-Job` cmdlet returns an object that represents the job.</span></span>

   <span data-ttu-id="746ae-150">此命令将作业对象保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="746ae-150">This command saves the job object in the `$job` variable.</span></span>

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   <span data-ttu-id="746ae-151">作业运行时，可以使用交互式会话来运行其他命令，包括其他作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-151">While the job runs, you can use the interactive session to run other commands, including other jobs.</span></span> <span data-ttu-id="746ae-152">但是，必须在作业完成之前使交互式会话保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="746ae-152">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="746ae-153">如果结束该会话，则该作业将中断，结果将丢失。</span><span class="sxs-lookup"><span data-stu-id="746ae-153">If you end the session, the job is interrupted, and the results are lost.</span></span>

1. <span data-ttu-id="746ae-154">若要查看作业是否已完成，请显示变量的值 `$job` ，或使用 `Get-Job` cmdlet 来获取作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-154">To find out if the job is complete, display the value of the `$job` variable, or use the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="746ae-155">以下命令使用 `Get-Job` cmdlet 来显示作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-155">The following command uses the `Get-Job` cmdlet to display the job.</span></span>

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   <span data-ttu-id="746ae-156">`Get-Job`此输出显示作业正在 "localhost" 计算机上运行，因为该作业已在同一台计算机上运行， (在这种情况下，Server01) 。</span><span class="sxs-lookup"><span data-stu-id="746ae-156">The `Get-Job` output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

1. <span data-ttu-id="746ae-157">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-157">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="746ae-158">可以在交互式会话中显示结果，也可以将结果保存到远程计算机上的文件中。</span><span class="sxs-lookup"><span data-stu-id="746ae-158">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="746ae-159">下面的命令获取 $job 变量中的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="746ae-159">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="746ae-160">该命令使用重定向运算符 (`>`) 将作业结果保存到 Server01 计算机上的 PsLog.txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="746ae-160">The command uses the redirection operator (`>`) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. <span data-ttu-id="746ae-161">若要结束交互式会话，请使用 `Exit-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-161">To end the interactive session, use the `Exit-PSSession` cmdlet.</span></span> <span data-ttu-id="746ae-162">命令提示符将更改为显示您返回到本地计算机上的原始会话中。</span><span class="sxs-lookup"><span data-stu-id="746ae-162">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. <span data-ttu-id="746ae-163">若要随时查看 `PsLog.txt` Server01 计算机上文件的内容，请启动另一交互式会话或运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-163">To view the contents of the `PsLog.txt` file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="746ae-164">如果要使用多个命令来调查和管理文件中的数据，这种类型的命令最好在 PSSession (持久性连接) 中运行 `PsLog.txt` 。</span><span class="sxs-lookup"><span data-stu-id="746ae-164">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the `PsLog.txt` file.</span></span> <span data-ttu-id="746ae-165">有关 Pssession 的详细信息，请参阅 [about_PSSessions](about_PSSessions.md)。</span><span class="sxs-lookup"><span data-stu-id="746ae-165">For more information about PSSessions, see [about_PSSessions](about_PSSessions.md).</span></span>

   <span data-ttu-id="746ae-166">以下命令使用 `New-PSSession` cmdlet 创建连接到 Server01 计算机的 **PSSession** ，并使用 `Invoke-Command` cmdlet `Get-Content` 在 pssession 中运行命令，以查看文件的内容。</span><span class="sxs-lookup"><span data-stu-id="746ae-166">The following commands use the `New-PSSession` cmdlet to create a **PSSession** that is connected to the Server01 computer, and they use the `Invoke-Command` cmdlet to run a `Get-Content` command in the PSSession to view the contents of the file.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="746ae-167">启动将结果返回到本地计算机的远程作业 (AsJob) </span><span class="sxs-lookup"><span data-stu-id="746ae-167">Start a remote job that returns the results to the local computer (AsJob)</span></span>

<span data-ttu-id="746ae-168">若要在将命令结果返回到本地计算机的远程计算机上启动作业，请使用 cmdlet 的 **AsJob** 参数，如 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-168">To start a job on a remote computer that returns the command results to the local computer, use the **AsJob** parameter of a cmdlet such as the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="746ae-169">使用 **AsJob** 参数时，实际上会在本地计算机上创建作业对象，即使该作业在远程计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="746ae-169">When you use the **AsJob** parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="746ae-170">完成作业后，结果将返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="746ae-170">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="746ae-171">你可以使用包含 job 名词的 cmdlet (作业 cmdlet) 管理任何 cmdlet 创建的任何作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-171">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="746ae-172">许多具有 **AsJob** 参数的 cmdlet 不使用 PowerShell 远程处理，因此您甚至可以在未配置为进行远程处理并且不满足远程处理要求的计算机上使用它们。</span><span class="sxs-lookup"><span data-stu-id="746ae-172">Many of the cmdlets that have **AsJob** parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

1. <span data-ttu-id="746ae-173">以下命令使用的 **AsJob** 参数 `Invoke-Command` 在 Server01 计算机上启动作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-173">The following command uses the **AsJob** parameter of `Invoke-Command` to start a job on the Server01 computer.</span></span> <span data-ttu-id="746ae-174">作业运行 `Get-Eventlog` 可获取系统日志中的事件的命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-174">The job runs a `Get-Eventlog` command that gets the events in the System log.</span></span> <span data-ttu-id="746ae-175">可以使用 JobName 参数为作业指定显示名称。</span><span class="sxs-lookup"><span data-stu-id="746ae-175">You can use the JobName parameter to assign a display name to the job.</span></span>

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   <span data-ttu-id="746ae-176">命令的结果类似于以下示例输出。</span><span class="sxs-lookup"><span data-stu-id="746ae-176">The results of the command resemble the following sample output.</span></span>

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   <span data-ttu-id="746ae-177">使用 **AsJob** 参数时， `Invoke-Command` 将返回返回的相同类型的作业对象 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="746ae-177">When the **AsJob** parameter is used, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="746ae-178">可以将作业对象保存在变量中，也可以使用 `Get-Job` 命令来获取作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-178">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="746ae-179">请注意，Location 属性的值显示作业在 Server01 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="746ae-179">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

1. <span data-ttu-id="746ae-180">若要管理使用 cmdlet 的 **AsJob** 参数启动的作业 `Invoke-Command` ，请使用作业 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-180">To manage a job started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="746ae-181">由于表示远程作业的作业对象位于本地计算机上，因此无需运行远程命令来管理该作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-181">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

   <span data-ttu-id="746ae-182">若要确定作业是否已完成，请使用 `Get-Job` 命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-182">To determine whether the job is complete, use a `Get-Job` command.</span></span> <span data-ttu-id="746ae-183">以下命令将获取在当前会话中启动的所有作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-183">The following command gets all of the jobs that were started in the current session.</span></span>

   ```powershell
   Get-Job
   ```

   <span data-ttu-id="746ae-184">由于远程作业是在当前会话中启动的，因此本地 `Get-Job` 命令会获取该作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-184">Because the remote job was started in the current session, a local `Get-Job` command gets the job.</span></span> <span data-ttu-id="746ae-185">作业对象的 State 属性显示该命令已成功完成。</span><span class="sxs-lookup"><span data-stu-id="746ae-185">The State property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. <span data-ttu-id="746ae-186">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-186">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="746ae-187">由于作业结果会自动返回到作业对象所在的计算机，因此你可以使用本地命令获取结果 `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="746ae-187">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local `Receive-Job` command.</span></span>

   <span data-ttu-id="746ae-188">以下命令使用 `Receive-Job` cmdlet 来获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="746ae-188">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="746ae-189">它使用会话 ID 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-189">It uses the session ID to identify the job.</span></span> <span data-ttu-id="746ae-190">此命令将作业结果保存在 $results 变量中。</span><span class="sxs-lookup"><span data-stu-id="746ae-190">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="746ae-191">你还可以将结果重定向到文件。</span><span class="sxs-lookup"><span data-stu-id="746ae-191">You can also redirect the results to a file.</span></span>

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="746ae-192">启动远程作业以在远程计算机上保留结果</span><span class="sxs-lookup"><span data-stu-id="746ae-192">Start a remote job that keeps the results on the remote computer</span></span>

<span data-ttu-id="746ae-193">若要在远程计算机上启动将命令结果保存在远程计算机上的作业，请使用 `Invoke-Command` cmdlet `Start-Job` 在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-193">To start a job on a remote computer that keeps the command results on the remote computer, use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="746ae-194">您可以使用此方法在多台计算机上运行作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-194">You can use this method to run jobs on multiple computers.</span></span>

<span data-ttu-id="746ae-195">远程运行命令时 `Start-Job` ，将在远程计算机上创建作业对象，并在远程计算机上维护作业结果。</span><span class="sxs-lookup"><span data-stu-id="746ae-195">When you run a `Start-Job` command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="746ae-196">从作业的角度来看，所有操作都是本地的。</span><span class="sxs-lookup"><span data-stu-id="746ae-196">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="746ae-197">你只需远程运行命令来管理远程计算机上的本地作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-197">You are just running commands remotely to manage a local job on the remote computer.</span></span>

1. <span data-ttu-id="746ae-198">使用 `Invoke-Command` cmdlet `Start-Job` 在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-198">Use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span>

   <span data-ttu-id="746ae-199">此命令需要 PSSession (持久性连接) 。</span><span class="sxs-lookup"><span data-stu-id="746ae-199">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="746ae-200">如果使用 ComputerName 参数 `Invoke-Command` 来建立临时连接，则在 `Invoke-Command` 返回作业对象时，该命令被视为已完成。</span><span class="sxs-lookup"><span data-stu-id="746ae-200">If you use the ComputerName parameter of `Invoke-Command` to establish a temporary connection, the `Invoke-Command` command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="746ae-201">因此，临时连接将关闭，并且该作业将被取消。</span><span class="sxs-lookup"><span data-stu-id="746ae-201">As a result, the temporary connection is closed, and the job is canceled.</span></span>

   <span data-ttu-id="746ae-202">以下命令使用 `New-PSSession` cmdlet 创建连接到 Server01 计算机的 PSSession。</span><span class="sxs-lookup"><span data-stu-id="746ae-202">The following command uses the `New-PSSession` cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="746ae-203">该命令将 PSSession 保存在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="746ae-203">The command saves the PSSession in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   <span data-ttu-id="746ae-204">下一个命令使用 `Invoke-Command` cmdlet `Start-Job` 在 PSSession 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-204">The next command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the PSSession.</span></span> <span data-ttu-id="746ae-205">`Start-Job`命令和 `Get-Eventlog` 命令括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="746ae-205">The `Start-Job` command and the `Get-Eventlog` command are enclosed in braces.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   <span data-ttu-id="746ae-206">结果类似于以下示例输出。</span><span class="sxs-lookup"><span data-stu-id="746ae-206">The results resemble the following sample output.</span></span>

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   <span data-ttu-id="746ae-207">远程运行命令时 `Start-Job` ， `Invoke-Command` 将返回返回的相同类型的作业对象 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="746ae-207">When you run a `Start-Job` command remotely, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="746ae-208">可以将作业对象保存在变量中，也可以使用 `Get-Job` 命令来获取作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-208">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="746ae-209">请注意， **Location** 属性的值显示作业在本地计算机上运行，也称为 "LocalHost"，即使该作业在 Server01 计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="746ae-209">Note that the value of the **Location** property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="746ae-210">由于作业对象是在 Server01 计算机上创建的，并且作业在同一台计算机上运行，因此将其视为本地后台作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-210">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

1. <span data-ttu-id="746ae-211">若要管理远程作业，请使用 **作业** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="746ae-211">To manage a remote job, use the **Job** cmdlets.</span></span> <span data-ttu-id="746ae-212">由于作业对象位于远程计算机上，因此您需要运行远程命令来获取、停止、等待或检索作业结果。</span><span class="sxs-lookup"><span data-stu-id="746ae-212">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

   <span data-ttu-id="746ae-213">若要查看作业是否已完成，请使用 `Invoke-Command` 命令 `Get-Job` 在连接到 Server01 计算机的 PSSession 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-213">To see if the job is complete, use an `Invoke-Command` command to run a `Get-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   <span data-ttu-id="746ae-214">该命令返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="746ae-214">The command returns a job object.</span></span> <span data-ttu-id="746ae-215">作业对象的 **State** 属性显示该命令已成功完成。</span><span class="sxs-lookup"><span data-stu-id="746ae-215">The **State** property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. <span data-ttu-id="746ae-216">若要获取作业结果，请使用 `Invoke-Command` cmdlet `Receive-Job` 在已连接到 Server01 计算机的 PSSession 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="746ae-216">To get the results of the job, use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   <span data-ttu-id="746ae-217">以下命令使用 `Receive-Job` cmdlet 来获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="746ae-217">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="746ae-218">它使用会话 ID 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-218">It uses the session ID to identify the job.</span></span> <span data-ttu-id="746ae-219">此命令将作业结果保存在 `$results` 变量中。</span><span class="sxs-lookup"><span data-stu-id="746ae-219">This command saves the job results in the `$results` variable.</span></span> <span data-ttu-id="746ae-220">它使用 Keep 参数将 `Receive-Job` 结果保存在远程计算机上的作业缓存中。</span><span class="sxs-lookup"><span data-stu-id="746ae-220">It uses the Keep parameter of `Receive-Job` to keep the result in the job cache on the remote computer.</span></span>

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   <span data-ttu-id="746ae-221">你还可以将结果重定向到本地或远程计算机上的文件。</span><span class="sxs-lookup"><span data-stu-id="746ae-221">You can also redirect the results to a file on the local or remote computer.</span></span>
   <span data-ttu-id="746ae-222">以下命令使用重定向运算符将结果保存到 Server01 计算机上的文件中。</span><span class="sxs-lookup"><span data-stu-id="746ae-222">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a><span data-ttu-id="746ae-223">如何作为分离的进程运行</span><span class="sxs-lookup"><span data-stu-id="746ae-223">How to run as a detached process</span></span>

<span data-ttu-id="746ae-224">如前所述，当终止父会话时，所有正在运行的子作业都将与其子进程一起终止。</span><span class="sxs-lookup"><span data-stu-id="746ae-224">As previously mentioned, when the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span> <span data-ttu-id="746ae-225">你可以使用本地计算机上的远程处理来运行未附加到当前 PowerShell 会话的作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-225">You can use remoting on the local machine to run jobs that are not attached to the current PowerShell session.</span></span>

<span data-ttu-id="746ae-226">在本地计算机上创建新的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-226">Create a new PowerShell session on the local machine.</span></span> <span data-ttu-id="746ae-227">用于 `Invoke-Command` 在此会话中启动作业的。</span><span class="sxs-lookup"><span data-stu-id="746ae-227">The use `Invoke-Command` to start a job in this session.</span></span> <span data-ttu-id="746ae-228">`Invoke-Command` 允许您断开远程会话的连接，并终止父会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-228">`Invoke-Command` allows you to disconnect a remote session and terminate the parent session.</span></span> <span data-ttu-id="746ae-229">稍后，可以启动新的 PowerShell 会话并连接到之前断开连接的会话，以恢复监视作业。</span><span class="sxs-lookup"><span data-stu-id="746ae-229">Later, you can start a new PowerShell session and connect to the previously disconnected session to resume monitoring the job.</span></span> <span data-ttu-id="746ae-230">但是，当终止该会话时，返回到原始 PowerShell 会话的任何数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="746ae-230">However, any data that was returned to the original PowerShell session is lost when that session is terminated.</span></span> <span data-ttu-id="746ae-231">重新连接后，只会返回断开连接后生成的新数据对象。</span><span class="sxs-lookup"><span data-stu-id="746ae-231">Only new data objects generated after the disconnect are returned when re-connected.</span></span>

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

<span data-ttu-id="746ae-232">在此示例中，作业仍附加到父 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="746ae-232">For this example, the jobs are still attached to a parent PowerShell session.</span></span>
<span data-ttu-id="746ae-233">但是，父会话并不是运行的原始 PowerShell 会话 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="746ae-233">However, the parent session is not the original PowerShell session where `Invoke-Command` was run.</span></span>

## <a name="see-also"></a><span data-ttu-id="746ae-234">另请参阅</span><span class="sxs-lookup"><span data-stu-id="746ae-234">See also</span></span>

- [<span data-ttu-id="746ae-235">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="746ae-235">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="746ae-236">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="746ae-236">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="746ae-237">about_Remote</span><span class="sxs-lookup"><span data-stu-id="746ae-237">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="746ae-238">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="746ae-238">about_Remote_Variables</span></span>](about_Remote_Variables.md)
- [<span data-ttu-id="746ae-239">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="746ae-239">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="746ae-240">Start-Job</span><span class="sxs-lookup"><span data-stu-id="746ae-240">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="746ae-241">Get-Job</span><span class="sxs-lookup"><span data-stu-id="746ae-241">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="746ae-242">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="746ae-242">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="746ae-243">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="746ae-243">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="746ae-244">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="746ae-244">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="746ae-245">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="746ae-245">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="746ae-246">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="746ae-246">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="746ae-247">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="746ae-247">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
