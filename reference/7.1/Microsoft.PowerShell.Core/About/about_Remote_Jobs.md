---
description: 描述如何在远程计算机上运行后台作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: fb2270ea5c0acdcf2c506e687787d22c73e2cb2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200152"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="1954a-104">关于远程作业</span><span class="sxs-lookup"><span data-stu-id="1954a-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="1954a-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="1954a-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1954a-106">描述如何在远程计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-106">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="1954a-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="1954a-107">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="1954a-108">后台作业是异步运行的命令，不与当前会话交互。</span><span class="sxs-lookup"><span data-stu-id="1954a-108">A background job is a command that runs asynchronously without interacting with the current session.</span></span> <span data-ttu-id="1954a-109">命令提示符会立即返回，你可以在运行作业时继续使用会话。</span><span class="sxs-lookup"><span data-stu-id="1954a-109">The command prompt returns immediately, and you can continue to use the session while the job runs.</span></span>

<span data-ttu-id="1954a-110">默认情况下，后台作业在本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="1954a-110">By default, background jobs run on the local computer.</span></span> <span data-ttu-id="1954a-111">但是，您可以使用几个不同的过程在远程计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-111">However, you can use several different procedures to run background jobs on remote computers.</span></span>

<span data-ttu-id="1954a-112">本主题说明如何在远程计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-112">This topic explains how to run a background job on a remote computer.</span></span> <span data-ttu-id="1954a-113">有关如何在本地计算机上运行后台作业的信息，请参阅 [about_Jobs](about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="1954a-113">For information about how to run background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span> <span data-ttu-id="1954a-114">有关后台作业的详细信息，请参阅 [about_Job_Details](about_Job_Details.md)。</span><span class="sxs-lookup"><span data-stu-id="1954a-114">For more information about background jobs, see [about_Job_Details](about_Job_Details.md).</span></span>

## <a name="remote-background-jobs"></a><span data-ttu-id="1954a-115">远程后台作业</span><span class="sxs-lookup"><span data-stu-id="1954a-115">REMOTE BACKGROUND JOBS</span></span>

<span data-ttu-id="1954a-116">您可以使用三种不同的方法在远程计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-116">You can run background jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="1954a-117">启动与远程计算机的交互式会话，并在交互式会话中启动作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-117">Start an interactive session with a remote computer, and start a job in the interactive session.</span></span> <span data-ttu-id="1954a-118">尽管所有操作都是在远程计算机上执行的，但过程与运行本地作业相同。</span><span class="sxs-lookup"><span data-stu-id="1954a-118">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="1954a-119">在将其结果返回到本地计算机的远程计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-119">Run a background job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="1954a-120">如果要收集后台作业的结果并在本地计算机上的中央位置维护这些作业的结果，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="1954a-120">Use this method when you want to collect the results of background jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="1954a-121">在远程计算机上运行后台作业，以在远程计算机上维护其结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-121">Run a background job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="1954a-122">在源计算机上更安全地维护作业数据时使用此方法。</span><span class="sxs-lookup"><span data-stu-id="1954a-122">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-background-job-in-an-interactive-session"></a><span data-ttu-id="1954a-123">在交互式会话中启动后台作业</span><span class="sxs-lookup"><span data-stu-id="1954a-123">START A BACKGROUND JOB IN AN INTERACTIVE SESSION</span></span>

<span data-ttu-id="1954a-124">您可以启动与远程计算机的交互式会话，然后在交互式会话过程中启动后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-124">You can start an interactive session with a remote computer and then start a background job during the interactive session.</span></span> <span data-ttu-id="1954a-125">有关交互式会话的详细信息，请参阅 about_Remote，并参阅 Enter-PSSession。</span><span class="sxs-lookup"><span data-stu-id="1954a-125">For more information about interactive sessions, see about_Remote, and see Enter-PSSession.</span></span>

<span data-ttu-id="1954a-126">在交互式会话中启动后台作业的过程与在本地计算机上启动后台作业的过程几乎相同。</span><span class="sxs-lookup"><span data-stu-id="1954a-126">The procedure for starting a background job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="1954a-127">但是，所有操作都在远程计算机上执行，而不是在本地计算机上进行。</span><span class="sxs-lookup"><span data-stu-id="1954a-127">However, all of the operations occur on the remote computer, not the local computer.</span></span>

#### <a name="step-1-enter-pssession"></a><span data-ttu-id="1954a-128">步骤1：输入-PSSESSION</span><span class="sxs-lookup"><span data-stu-id="1954a-128">STEP 1: ENTER-PSSESSION</span></span>

<span data-ttu-id="1954a-129">使用 Enter-PSSession cmdlet 来启动与远程计算机的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="1954a-129">Use the Enter-PSSession cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="1954a-130">可以使用 Enter-PSSession 的 ComputerName 参数为交互式会话建立临时连接。</span><span class="sxs-lookup"><span data-stu-id="1954a-130">You can use the ComputerName parameter of Enter-PSSession to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="1954a-131">或者，可以使用 Session 参数 (PSSession) 在 PowerShell 会话中运行交互式会话。</span><span class="sxs-lookup"><span data-stu-id="1954a-131">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

<span data-ttu-id="1954a-132">以下命令在 Server01 计算机上启动交互式会话。</span><span class="sxs-lookup"><span data-stu-id="1954a-132">The following command starts an interactive session on the Server01 computer.</span></span>

```powershell
C:\PS> Enter-PSSession -computername Server01
```

<span data-ttu-id="1954a-133">命令提示符更改为显示你现在已连接到 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="1954a-133">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

```
Server01\C:>
```

#### <a name="step-2-start-job"></a><span data-ttu-id="1954a-134">步骤2：启动-作业</span><span class="sxs-lookup"><span data-stu-id="1954a-134">STEP 2: START-JOB</span></span>

<span data-ttu-id="1954a-135">若要在会话中启动后台作业，请使用 Start-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-135">To start a background job in the session, use the Start-Job cmdlet.</span></span>

<span data-ttu-id="1954a-136">以下命令运行一个后台作业，该作业将获取 Server01 计算机上的 Windows PowerShell 事件日志中的事件。</span><span class="sxs-lookup"><span data-stu-id="1954a-136">The following command runs a background job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="1954a-137">Start-Job cmdlet 返回一个表示作业的对象。</span><span class="sxs-lookup"><span data-stu-id="1954a-137">The Start-Job cmdlet returns an object that represents the job.</span></span>

<span data-ttu-id="1954a-138">此命令将作业对象保存在 \$ job 变量中。</span><span class="sxs-lookup"><span data-stu-id="1954a-138">This command saves the job object in the \$job variable.</span></span>

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

<span data-ttu-id="1954a-139">作业运行时，可以使用交互式会话来运行其他命令，包括其他后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-139">While the job runs, you can use the interactive session to run other commands, including other background jobs.</span></span> <span data-ttu-id="1954a-140">但是，必须在作业完成之前使交互式会话保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="1954a-140">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="1954a-141">如果结束该会话，则该作业将中断，结果将丢失。</span><span class="sxs-lookup"><span data-stu-id="1954a-141">If you end the session, the job is interrupted, and the results are lost.</span></span>

#### <a name="step-3-get-job"></a><span data-ttu-id="1954a-142">步骤3：获取工作</span><span class="sxs-lookup"><span data-stu-id="1954a-142">STEP 3: GET-JOB</span></span>

<span data-ttu-id="1954a-143">若要查看作业是否已完成，请显示作业变量的值 \$ ，或使用 Get-Job cmdlet 获取作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-143">To find out if the job is complete, display the value of the \$job variable, or use the Get-Job cmdlet to get the job.</span></span> <span data-ttu-id="1954a-144">以下命令使用 Get-Job cmdlet 显示作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-144">The following command uses the Get-Job cmdlet to display the job.</span></span>

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

<span data-ttu-id="1954a-145">Get-Job 输出显示作业正在 "localhost" 计算机上运行，因为该作业已在同一台计算机上启动并且正在运行 (在这种情况下，Server01) 。</span><span class="sxs-lookup"><span data-stu-id="1954a-145">The Get-Job output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

#### <a name="step-4-receive-job"></a><span data-ttu-id="1954a-146">步骤4：接收作业</span><span class="sxs-lookup"><span data-stu-id="1954a-146">STEP 4: RECEIVE-JOB</span></span>

<span data-ttu-id="1954a-147">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-147">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="1954a-148">可以在交互式会话中显示结果，也可以将结果保存到远程计算机上的文件中。</span><span class="sxs-lookup"><span data-stu-id="1954a-148">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="1954a-149">下面的命令获取 $job 变量中的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-149">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="1954a-150">该命令使用重定向运算符 ( # A0) 将作业的结果保存到 Server01 计算机上的 PsLog.txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="1954a-150">The command uses the redirection operator (>) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a><span data-ttu-id="1954a-151">步骤5：退出-PSSESSION</span><span class="sxs-lookup"><span data-stu-id="1954a-151">STEP 5: EXIT-PSSESSION</span></span>

<span data-ttu-id="1954a-152">若要结束交互式会话，请使用 Exit-PSSession cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-152">To end the interactive session, use the Exit-PSSession cmdlet.</span></span> <span data-ttu-id="1954a-153">命令提示符将更改为显示您返回到本地计算机上的原始会话中。</span><span class="sxs-lookup"><span data-stu-id="1954a-153">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a><span data-ttu-id="1954a-154">步骤6：调用命令：获取内容</span><span class="sxs-lookup"><span data-stu-id="1954a-154">STEP 6: INVOKE-COMMAND: GET-CONTENT</span></span>

<span data-ttu-id="1954a-155">若要随时查看 Server01 计算机上的 PsLog.txt 文件的内容，请启动另一交互式会话或运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-155">To view the contents of the PsLog.txt file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="1954a-156">如果要使用多个命令来调查和管理 PsLog.txt 文件中的数据，这种类型的命令最好在 PSSession (持久性连接) 中运行。</span><span class="sxs-lookup"><span data-stu-id="1954a-156">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the PsLog.txt file.</span></span> <span data-ttu-id="1954a-157">有关 Pssession 的详细信息，请参阅 about_PSSessions。</span><span class="sxs-lookup"><span data-stu-id="1954a-157">For more information about PSSessions, see about_PSSessions.</span></span>

<span data-ttu-id="1954a-158">以下命令使用 New-PSSession cmdlet 来创建连接到 Server01 计算机的 PSSession，并使用 Invoke-Command cmdlet 在 PSSession 中运行 Get-Content 命令以查看文件的内容。</span><span class="sxs-lookup"><span data-stu-id="1954a-158">The following commands use the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer, and they use the Invoke-Command cmdlet to run a Get-Content command in the PSSession to view the contents of the file.</span></span>

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="1954a-159">启动将结果返回到本地计算机 ASJOB 的远程作业 \(\)</span><span class="sxs-lookup"><span data-stu-id="1954a-159">START A REMOTE JOB THAT RETURNS THE RESULTS TO THE LOCAL COMPUTER \(ASJOB\)</span></span>

<span data-ttu-id="1954a-160">若要在将命令结果返回到本地计算机的远程计算机上启动后台作业，请使用 cmdlet 的 AsJob 参数，如 Invoke-Command cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-160">To start a background job on a remote computer that returns the command results to the local computer, use the AsJob parameter of a cmdlet such as the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="1954a-161">使用 AsJob 参数时，实际上会在本地计算机上创建作业对象，即使该作业在远程计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="1954a-161">When you use the AsJob parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="1954a-162">完成作业后，结果将返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="1954a-162">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="1954a-163">你可以使用包含 job 名词的 cmdlet (作业 cmdlet) 管理任何 cmdlet 创建的任何作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-163">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="1954a-164">许多具有 AsJob 参数的 cmdlet 不使用 PowerShell 远程处理，因此您甚至可以在未配置为进行远程处理并且不满足远程处理要求的计算机上使用它们。</span><span class="sxs-lookup"><span data-stu-id="1954a-164">Many of the cmdlets that have AsJob parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

#### <a name="step-1-invoke-command--asjob"></a><span data-ttu-id="1954a-165">步骤1：调用命令-ASJOB</span><span class="sxs-lookup"><span data-stu-id="1954a-165">STEP 1: INVOKE-COMMAND -ASJOB</span></span>

<span data-ttu-id="1954a-166">以下命令使用 Invoke-Command 的 AsJob 参数在 Server01 计算机上启动后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-166">The following command uses the AsJob parameter of Invoke-Command to start a background job on the Server01 computer.</span></span> <span data-ttu-id="1954a-167">该作业运行可获取系统日志中的事件的 Get-Eventlog 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-167">The job runs a Get-Eventlog command that gets the events in the System log.</span></span> <span data-ttu-id="1954a-168">可以使用 JobName 参数为作业指定显示名称。</span><span class="sxs-lookup"><span data-stu-id="1954a-168">You can use the JobName parameter to assign a display name to the job.</span></span>

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

<span data-ttu-id="1954a-169">命令的结果类似于以下示例输出。</span><span class="sxs-lookup"><span data-stu-id="1954a-169">The results of the command resemble the following sample output.</span></span>

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

<span data-ttu-id="1954a-170">使用 AsJob 参数时，Invoke-Command 返回 Start-Job 返回的相同类型的作业对象。</span><span class="sxs-lookup"><span data-stu-id="1954a-170">When the AsJob parameter is used, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="1954a-171">可以将作业对象保存在变量中，也可以使用 Get-Job 命令来获取作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-171">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="1954a-172">请注意，Location 属性的值显示作业在 Server01 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="1954a-172">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

#### <a name="step-2-get-job"></a><span data-ttu-id="1954a-173">步骤2：获取工作</span><span class="sxs-lookup"><span data-stu-id="1954a-173">STEP 2: GET-JOB</span></span>

<span data-ttu-id="1954a-174">若要管理使用 Invoke-Command cmdlet 的 AsJob 参数启动的作业，请使用作业 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-174">To manage a job started by using the AsJob parameter of the Invoke-Command cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="1954a-175">由于表示远程作业的作业对象位于本地计算机上，因此无需运行远程命令来管理该作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-175">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

<span data-ttu-id="1954a-176">若要确定作业是否已完成，请使用 Get-Job 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-176">To determine whether the job is complete, use a Get-Job command.</span></span> <span data-ttu-id="1954a-177">以下命令将获取在当前会话中启动的所有作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-177">The following command gets all of the jobs that were started in the current session.</span></span>

```powershell
get-job
```

<span data-ttu-id="1954a-178">由于远程作业已在当前会话中启动，因此本地 Get-Job 命令将获取该作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-178">Because the remote job was started in the current session, a local Get-Job command gets the job.</span></span> <span data-ttu-id="1954a-179">作业对象的 State 属性显示该命令已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1954a-179">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a><span data-ttu-id="1954a-180">步骤3：接收作业</span><span class="sxs-lookup"><span data-stu-id="1954a-180">STEP 3: RECEIVE-JOB</span></span>

<span data-ttu-id="1954a-181">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-181">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="1954a-182">由于作业结果会自动返回到作业对象所在的计算机，因此你可以使用本地 Receive-Job 命令获取结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-182">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local Receive-Job command.</span></span>

<span data-ttu-id="1954a-183">以下命令使用 Receive-Job cmdlet 获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-183">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="1954a-184">它使用会话 ID 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-184">It uses the session ID to identify the job.</span></span> <span data-ttu-id="1954a-185">此命令将作业结果保存在 $results 变量中。</span><span class="sxs-lookup"><span data-stu-id="1954a-185">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="1954a-186">你还可以将结果重定向到文件。</span><span class="sxs-lookup"><span data-stu-id="1954a-186">You can also redirect the results to a file.</span></span>

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="1954a-187">启动远程作业以在远程计算机上保留结果</span><span class="sxs-lookup"><span data-stu-id="1954a-187">START A REMOTE JOB THAT KEEPS THE RESULTS ON THE REMOTE COMPUTER</span></span>

<span data-ttu-id="1954a-188">若要在远程计算机上启动后台作业，以在远程计算机上保留命令结果，请使用 Invoke-Command cmdlet 在远程计算机上运行 Start-Job 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-188">To start a background job on a remote computer that keeps the command results on the remote computer, use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span> <span data-ttu-id="1954a-189">您可以使用此方法在多台计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-189">You can use this method to run background jobs on multiple computers.</span></span>

<span data-ttu-id="1954a-190">远程运行 Start-Job 命令时，将在远程计算机上创建作业对象，并在远程计算机上维护作业结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-190">When you run a Start-Job command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="1954a-191">从作业的角度来看，所有操作都是本地的。</span><span class="sxs-lookup"><span data-stu-id="1954a-191">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="1954a-192">你只需远程运行命令来管理远程计算机上的本地作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-192">You are just running commands remotely to manage a local job on the remote computer.</span></span>

#### <a name="step-1-invoke-command-start-job"></a><span data-ttu-id="1954a-193">步骤1：调用-命令启动-作业</span><span class="sxs-lookup"><span data-stu-id="1954a-193">STEP 1: INVOKE-COMMAND START-JOB</span></span>

<span data-ttu-id="1954a-194">使用 Invoke-Command cmdlet 在远程计算机上运行 Start-Job 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-194">Use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span>

<span data-ttu-id="1954a-195">此命令需要 PSSession (持久性连接) 。</span><span class="sxs-lookup"><span data-stu-id="1954a-195">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="1954a-196">如果使用 Invoke-Command 的 ComputerName 参数建立临时连接，则在返回作业对象时，Invoke-Command 命令会被视为已完成。</span><span class="sxs-lookup"><span data-stu-id="1954a-196">If you use the ComputerName parameter of Invoke-Command to establish a temporary connection, the Invoke-Command command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="1954a-197">因此，临时连接将关闭，并且该作业将被取消。</span><span class="sxs-lookup"><span data-stu-id="1954a-197">As a result, the temporary connection is closed, and the job is canceled.</span></span>

<span data-ttu-id="1954a-198">以下命令使用 New-PSSession cmdlet 来创建连接到 Server01 计算机的 PSSession。</span><span class="sxs-lookup"><span data-stu-id="1954a-198">The following command uses the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="1954a-199">该命令将 PSSession 保存在 \$ s 变量中。</span><span class="sxs-lookup"><span data-stu-id="1954a-199">The command saves the PSSession in the \$s variable.</span></span>

```powershell
$s = new-pssession -computername Server01
```

<span data-ttu-id="1954a-200">下一个命令使用 Invoke-Command cmdlet 在 PSSession 中运行 Start-Job 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-200">The next command uses the Invoke-Command cmdlet to run a Start-Job command in the PSSession.</span></span> <span data-ttu-id="1954a-201">Start-Job 命令和 Get-Eventlog 命令括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="1954a-201">The Start-Job command and the Get-Eventlog command are enclosed in braces.</span></span>

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

<span data-ttu-id="1954a-202">结果类似于以下示例输出。</span><span class="sxs-lookup"><span data-stu-id="1954a-202">The results resemble the following sample output.</span></span>

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

<span data-ttu-id="1954a-203">远程运行 Start-Job 命令时，Invoke-Command 返回 Start-Job 返回的相同类型的作业对象。</span><span class="sxs-lookup"><span data-stu-id="1954a-203">When you run a Start-Job command remotely, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="1954a-204">可以将作业对象保存在变量中，也可以使用 Get-Job 命令来获取作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-204">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="1954a-205">请注意，Location 属性的值显示作业在本地计算机上运行，也称为 "LocalHost"，即使该作业在 Server01 计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="1954a-205">Note that the value of the Location property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="1954a-206">由于作业对象是在 Server01 计算机上创建的，并且作业在同一台计算机上运行，因此将其视为本地后台作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-206">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

#### <a name="step-2-invoke-command-get-job"></a><span data-ttu-id="1954a-207">步骤2：调用-命令获取</span><span class="sxs-lookup"><span data-stu-id="1954a-207">STEP 2: INVOKE-COMMAND GET-JOB</span></span>

<span data-ttu-id="1954a-208">若要管理远程后台作业，请使用作业 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1954a-208">To manage a remote background job, use the Job cmdlets.</span></span> <span data-ttu-id="1954a-209">由于作业对象位于远程计算机上，因此您需要运行远程命令来获取、停止、等待或检索作业结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-209">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

<span data-ttu-id="1954a-210">若要查看作业是否已完成，请使用 Invoke-Command 命令在连接到 Server01 计算机的 PSSession 中运行 Get-Job 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-210">To see if the job is complete, use an Invoke-Command command to run a Get-Job command in the PSSession that is connected to the Server01 computer.</span></span>

```powershell
invoke-command -session $s -scriptblock {get-job}
```

<span data-ttu-id="1954a-211">该命令返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="1954a-211">The command returns a job object.</span></span> <span data-ttu-id="1954a-212">作业对象的 State 属性显示该命令已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1954a-212">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a><span data-ttu-id="1954a-213">步骤3：调用-命令接收-作业</span><span class="sxs-lookup"><span data-stu-id="1954a-213">STEP 3: INVOKE-COMMAND RECEIVE-JOB</span></span>

<span data-ttu-id="1954a-214">若要获取作业结果，请使用 Invoke-Command cmdlet 在连接到 Server01 计算机的 PSSession 中运行 Receive-Job 命令。</span><span class="sxs-lookup"><span data-stu-id="1954a-214">To get the results of the job, use the Invoke-Command cmdlet to run a Receive-Job command in the PSSession that is connected to the Server01 computer.</span></span>

<span data-ttu-id="1954a-215">以下命令使用 Receive-Job cmdlet 获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="1954a-215">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="1954a-216">它使用会话 ID 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="1954a-216">It uses the session ID to identify the job.</span></span> <span data-ttu-id="1954a-217">此命令将作业结果保存在 \$ 结果变量中。</span><span class="sxs-lookup"><span data-stu-id="1954a-217">This command saves the job results in the \$results variable.</span></span> <span data-ttu-id="1954a-218">它使用 Receive-Job 的 Keep 参数将结果保存在远程计算机上的作业缓存中。</span><span class="sxs-lookup"><span data-stu-id="1954a-218">It uses the Keep parameter of Receive-Job to keep the result in the job cache on the remote computer.</span></span>

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

<span data-ttu-id="1954a-219">你还可以将结果重定向到本地或远程计算机上的文件。</span><span class="sxs-lookup"><span data-stu-id="1954a-219">You can also redirect the results to a file on the local or remote computer.</span></span>
<span data-ttu-id="1954a-220">以下命令使用重定向运算符将结果保存到 Server01 计算机上的文件中。</span><span class="sxs-lookup"><span data-stu-id="1954a-220">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a><span data-ttu-id="1954a-221">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1954a-221">SEE ALSO</span></span>

[<span data-ttu-id="1954a-222">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="1954a-222">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="1954a-223">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="1954a-223">about_Job_Details</span></span>](about_Job_Details.md)

[<span data-ttu-id="1954a-224">about_Remote</span><span class="sxs-lookup"><span data-stu-id="1954a-224">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="1954a-225">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="1954a-225">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="1954a-226">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="1954a-226">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="1954a-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="1954a-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)

[<span data-ttu-id="1954a-228">Get-Job</span><span class="sxs-lookup"><span data-stu-id="1954a-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)

[<span data-ttu-id="1954a-229">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="1954a-229">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)

[<span data-ttu-id="1954a-230">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="1954a-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)

[<span data-ttu-id="1954a-231">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="1954a-231">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)

[<span data-ttu-id="1954a-232">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="1954a-232">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="1954a-233">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="1954a-233">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="1954a-234">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="1954a-234">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

