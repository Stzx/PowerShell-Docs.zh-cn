---
description: 提供有关 PowerShell 后台作业如何在后台运行命令或表达式，而不与当前会话交互的信息。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: b28eb480e3f994696738d6053ea7e2622a743ce5
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "93200575"
---
# <a name="about-jobs"></a><span data-ttu-id="28a36-104">关于作业</span><span class="sxs-lookup"><span data-stu-id="28a36-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="28a36-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="28a36-105">Short description</span></span>
<span data-ttu-id="28a36-106">提供有关 PowerShell 后台作业如何在后台运行命令或表达式，而不与当前会话交互的信息。</span><span class="sxs-lookup"><span data-stu-id="28a36-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="28a36-107">长说明</span><span class="sxs-lookup"><span data-stu-id="28a36-107">Long description</span></span>

<span data-ttu-id="28a36-108">PowerShell 并发运行命令，并通过作业编写脚本。</span><span class="sxs-lookup"><span data-stu-id="28a36-108">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="28a36-109">PowerShell 提供了三个基于作业的解决方案来支持并发。</span><span class="sxs-lookup"><span data-stu-id="28a36-109">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="28a36-110">作业</span><span class="sxs-lookup"><span data-stu-id="28a36-110">Job</span></span>            |<span data-ttu-id="28a36-111">说明</span><span class="sxs-lookup"><span data-stu-id="28a36-111">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="28a36-112">命令和脚本在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="28a36-112">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="28a36-113">命令和脚本在本地的单独进程中运行</span><span class="sxs-lookup"><span data-stu-id="28a36-113">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="28a36-114">虚拟 CPU。</span><span class="sxs-lookup"><span data-stu-id="28a36-114">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="28a36-115">命令和脚本在同一内的单独线程中运行</span><span class="sxs-lookup"><span data-stu-id="28a36-115">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="28a36-116">在本地计算机上进行处理。</span><span class="sxs-lookup"><span data-stu-id="28a36-116">process on the local machine.</span></span>                                |

<span data-ttu-id="28a36-117">每种类型的作业都有其优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="28a36-117">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="28a36-118">在单独的计算机上或在单独的进程中远程运行脚本具有很好的隔离。</span><span class="sxs-lookup"><span data-stu-id="28a36-118">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="28a36-119">任何错误不会影响其他正在运行的作业或启动该作业的客户端。</span><span class="sxs-lookup"><span data-stu-id="28a36-119">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="28a36-120">但远程处理层增加了开销，包括对象序列化。</span><span class="sxs-lookup"><span data-stu-id="28a36-120">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="28a36-121">所有传递到远程会话的对象都必须进行序列化，然后在客户端与目标会话之间传递时进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="28a36-121">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="28a36-122">对于大型复杂数据对象，序列化操作可以使用很多计算资源和内存资源。</span><span class="sxs-lookup"><span data-stu-id="28a36-122">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

<span data-ttu-id="28a36-123">本主题说明如何在本地计算机上的 PowerShell 中运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-123">This topic explains how to run background jobs in PowerShell on a local computer.</span></span> <span data-ttu-id="28a36-124">有关在远程计算机上运行后台作业的信息，请参阅 [about_Remote_Jobs](about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="28a36-124">For information about running background jobs on remote computers, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span> <span data-ttu-id="28a36-125">有关线程作业的详细信息，请参阅 [about_Thread_Jobs](about_Thread_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="28a36-125">For more information about thread jobs, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="28a36-126">启动后台作业时，命令提示符会立即返回，即使作业需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="28a36-126">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="28a36-127">当该作业运行时，你可以继续在此会话中工作而不会发生中断。</span><span class="sxs-lookup"><span data-stu-id="28a36-127">You can continue to work in the session without interruption while the job runs.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="28a36-128">作业 cmdlet</span><span class="sxs-lookup"><span data-stu-id="28a36-128">The job cmdlets</span></span>

|<span data-ttu-id="28a36-129">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="28a36-129">Cmdlet</span></span>          |<span data-ttu-id="28a36-130">说明</span><span class="sxs-lookup"><span data-stu-id="28a36-130">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="28a36-131">在本地计算机上启动后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-131">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="28a36-132">获取在中启动的后台作业</span><span class="sxs-lookup"><span data-stu-id="28a36-132">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="28a36-133">当前会话。</span><span class="sxs-lookup"><span data-stu-id="28a36-133">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="28a36-134">获取后台作业的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-134">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="28a36-135">停止后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-135">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="28a36-136">禁止显示命令提示符，直到其中一个或所有作业都为</span><span class="sxs-lookup"><span data-stu-id="28a36-136">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="28a36-137">完成.</span><span class="sxs-lookup"><span data-stu-id="28a36-137">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="28a36-138">删除后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-138">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="28a36-139">**AsJob** 参数在上创建后台作业</span><span class="sxs-lookup"><span data-stu-id="28a36-139">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="28a36-140">远程计算机。</span><span class="sxs-lookup"><span data-stu-id="28a36-140">remote computer.</span></span> <span data-ttu-id="28a36-141">你可以使用 `Invoke-Command` 运行</span><span class="sxs-lookup"><span data-stu-id="28a36-141">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="28a36-142">任何远程作业命令，包括 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="28a36-142">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="28a36-143">如何在本地计算机上启动作业</span><span class="sxs-lookup"><span data-stu-id="28a36-143">How to start a job on the local computer</span></span>

<span data-ttu-id="28a36-144">若要在本地计算机上启动后台作业，请使用 `Start-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28a36-144">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="28a36-145">若要编写 `Start-Job` 命令，请将作业运行的命令括在大括号中， (`{}`) 。</span><span class="sxs-lookup"><span data-stu-id="28a36-145">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="28a36-146">使用 **ScriptBlock** 参数来指定命令。</span><span class="sxs-lookup"><span data-stu-id="28a36-146">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="28a36-147">下面的命令启动在 `Get-Process` 本地计算机上运行命令的后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-147">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="28a36-148">`Start-Job`命令返回一个表示作业的对象。</span><span class="sxs-lookup"><span data-stu-id="28a36-148">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="28a36-149">作业对象包含有关该作业的有用信息，但是不包含作业结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-149">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="28a36-150">将作业对象保存在变量中，然后将其与其他作业 cmdlet 一起使用来管理后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-150">Save the job object in a variable, and then use it with the other Job cmdlets to manage the background job.</span></span> <span data-ttu-id="28a36-151">下面的命令启动作业对象并将生成的作业对象保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="28a36-151">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="28a36-152">从 PowerShell 6.0 开始，可以在 `&` 管道的末尾使用 amersand () 来启动后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-152">Beginning in PowerShell 6.0, you can use an amersand (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="28a36-153">以下命令在功能上等效于上述命令。</span><span class="sxs-lookup"><span data-stu-id="28a36-153">The following command is functionally equivalent to the command above.</span></span>

```powershell
$job = Get-Process &
```

<span data-ttu-id="28a36-154">与号 `&`)  (称为后台运算符。</span><span class="sxs-lookup"><span data-stu-id="28a36-154">The ampersand (`&`) is called the background operator.</span></span> <span data-ttu-id="28a36-155">有关详细信息，请参阅 [背景运算符](about_Operators.md#background-operator-)。</span><span class="sxs-lookup"><span data-stu-id="28a36-155">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="28a36-156">你还可以使用 `Get-Job` cmdlet 来获取表示在当前会话中启动的作业的对象。</span><span class="sxs-lookup"><span data-stu-id="28a36-156">You can also use the `Get-Job` cmdlet to get objects that represent the jobs started in the current session.</span></span> <span data-ttu-id="28a36-157">`Get-Job` 返回返回的同一作业对象 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="28a36-157">`Get-Job` returns the same job object that `Start-Job` returns.</span></span>

## <a name="getting-job-objects"></a><span data-ttu-id="28a36-158">正在获取作业对象</span><span class="sxs-lookup"><span data-stu-id="28a36-158">Getting job objects</span></span>

<span data-ttu-id="28a36-159">若要获取表示在当前会话中启动的后台作业的对象，请使用 `Get-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28a36-159">To get object that represent the background jobs that were started in the current session, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="28a36-160">如果没有参数，则 `Get-Job` 返回在当前会话中启动的所有作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-160">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

<span data-ttu-id="28a36-161">例如，以下命令将获取当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-161">For example, the following command gets the jobs in the current session.</span></span>

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

<span data-ttu-id="28a36-162">你还可以将作业对象保存在变量中，并在后面的命令中使用它来表示作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-162">You can also save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="28a36-163">以下命令获取 ID 为1的作业，并将其保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="28a36-163">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

<span data-ttu-id="28a36-164">作业对象包含作业的状态，该状态指示作业是否已完成。</span><span class="sxs-lookup"><span data-stu-id="28a36-164">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="28a36-165">已完成的作业的状态为 " **完成** " 或 " **失败** "。</span><span class="sxs-lookup"><span data-stu-id="28a36-165">A finished job has a state of **Complete** or **Failed** .</span></span> <span data-ttu-id="28a36-166">作业也可能被 **阻止** 或 **正在运行** 。</span><span class="sxs-lookup"><span data-stu-id="28a36-166">A job might also be **blocked** or **running** .</span></span>

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="28a36-167">获取作业的结果</span><span class="sxs-lookup"><span data-stu-id="28a36-167">Getting the results of a job</span></span>

<span data-ttu-id="28a36-168">运行后台作业时，结果不会立即显示。</span><span class="sxs-lookup"><span data-stu-id="28a36-168">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="28a36-169">相反，该 `Start-Job` cmdlet 将返回表示该作业的作业对象，但该对象不包含结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-169">Instead, the `Start-Job` cmdlet returns a job object that represents the job, but it does not contain the results.</span></span> <span data-ttu-id="28a36-170">若要获取后台作业的结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28a36-170">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="28a36-171">以下命令使用 `Receive-Job` cmdlet 来获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-171">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="28a36-172">它使用保存在变量中的作业对象 `$job` 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-172">It uses a job object saved in the `$job` variable to identify the job.</span></span>

```powershell
Receive-Job -Job $job
```

<span data-ttu-id="28a36-173">`Receive-Job`Cmdlet 将返回作业的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-173">The `Receive-Job` cmdlet returns the results of the job.</span></span>

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

<span data-ttu-id="28a36-174">您还可以将作业的结果保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="28a36-174">You can also save the results of a job in a variable.</span></span> <span data-ttu-id="28a36-175">以下命令将变量中的作业结果保存 `$job` 到 `$results` 变量中。</span><span class="sxs-lookup"><span data-stu-id="28a36-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

<span data-ttu-id="28a36-176">而且，你可以通过使用) 或 cmdlet (重定向运算符将作业的结果保存到文件中 `>` `Out-File` 。</span><span class="sxs-lookup"><span data-stu-id="28a36-176">And, you can save the results of the job in a file by using the redirection operator (`>`) or the `Out-File` cmdlet.</span></span> <span data-ttu-id="28a36-177">以下命令使用重定向运算符将作业的结果保存到文件的变量中 `$job` `Results.txt` 。</span><span class="sxs-lookup"><span data-stu-id="28a36-177">The following command uses the redirection operator to save the results of the job in the `$job` variable in the `Results.txt` file.</span></span>

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="28a36-178">获取并保留部分作业结果</span><span class="sxs-lookup"><span data-stu-id="28a36-178">Getting and keeping partial job results</span></span>

<span data-ttu-id="28a36-179">`Receive-Job`Cmdlet 将获取后台作业的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-179">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="28a36-180">如果作业已完成，则 `Receive-Job` 获取所有作业结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-180">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="28a36-181">如果作业仍在运行，将 `Receive-Job` 获取迄今为止生成的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-181">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="28a36-182">可以再次运行 `Receive-Job` 命令来获取剩余结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-182">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="28a36-183">`Receive-Job`返回结果时，默认情况下，它将从存储作业结果的缓存中删除这些结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-183">When `Receive-Job` returns results, by default, it deletes those results from the cache where job results are stored.</span></span> <span data-ttu-id="28a36-184">如果运行另一个 `Receive-Job` 命令，则只会获得尚未收到的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-184">If you run another `Receive-Job` command, you get only the results that are not yet received.</span></span>

<span data-ttu-id="28a36-185">以下命令显示在 `Receive-Job` 作业完成之前运行的命令的结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-185">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

<span data-ttu-id="28a36-186">若要阻止 `Receive-Job` 删除已返回的作业结果，请使用 **Keep** 参数。</span><span class="sxs-lookup"><span data-stu-id="28a36-186">To prevent `Receive-Job` from deleting the job results that it has returned, use the **Keep** parameter.</span></span> <span data-ttu-id="28a36-187">因此，会 `Receive-Job` 返回在该时间之前生成的所有结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-187">As a result, `Receive-Job` returns all of the results that have been generated until that time.</span></span>

<span data-ttu-id="28a36-188">以下命令显示对尚未完成的作业使用 **Keep** 参数的效果。</span><span class="sxs-lookup"><span data-stu-id="28a36-188">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

## <a name="waiting-for-the-results"></a><span data-ttu-id="28a36-189">正在等待结果</span><span class="sxs-lookup"><span data-stu-id="28a36-189">Waiting for the results</span></span>

<span data-ttu-id="28a36-190">如果运行需要很长时间才能完成的命令，则可以使用作业对象的属性来确定作业的完成时间。</span><span class="sxs-lookup"><span data-stu-id="28a36-190">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="28a36-191">以下命令使用 `Get-Job` 对象获取当前会话中的所有后台作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-191">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="28a36-192">结果将显示在表中。</span><span class="sxs-lookup"><span data-stu-id="28a36-192">The results appear in a table.</span></span> <span data-ttu-id="28a36-193">作业的状态显示在 " **状态** " 列中。</span><span class="sxs-lookup"><span data-stu-id="28a36-193">The status of the job appears in the **State** column.</span></span>

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="28a36-194">在这种情况下，"状态" 属性显示 "作业 2" 仍在运行。</span><span class="sxs-lookup"><span data-stu-id="28a36-194">In this case, the State property reveals that Job 2 is still running.</span></span> <span data-ttu-id="28a36-195">如果你 `Receive-Job` 现在使用 cmdlet 来获取作业结果，结果将不完整。</span><span class="sxs-lookup"><span data-stu-id="28a36-195">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="28a36-196">可以重复使用此 `Receive-Job` cmdlet 来获取所有结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-196">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="28a36-197">默认情况下，每次使用该方法时，只会获得尚未收到的结果，但你可以使用该 cmdlet 的 **Keep** 参数 `Receive-Job` 保留结果，即使已收到这些结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-197">By default, each time you use it, you get only the results that were not already received, but you can use the **Keep** parameter of the `Receive-Job` cmdlet to retain the results, even though they were already received.</span></span>

<span data-ttu-id="28a36-198">您可以将部分结果写入文件，然后在其到达时追加新的结果，也可以稍后等待并检查作业的状态。</span><span class="sxs-lookup"><span data-stu-id="28a36-198">You can write the partial results to a file and then append newer results as they arrive or you can wait and check the state of the job later.</span></span>

<span data-ttu-id="28a36-199">你可以使用 cmdlet 的 **Wait** 参数 `Receive-Job` ，该参数在作业完成并且所有结果都可用之前，不会返回命令提示符。</span><span class="sxs-lookup"><span data-stu-id="28a36-199">You can use the **Wait** parameter of the `Receive-Job` cmdlet, which does not return the command prompt until the job is complete and all results are available.</span></span>

<span data-ttu-id="28a36-200">你还可以使用 `Wait-Job` cmdlet 等待作业的任何或所有结果。</span><span class="sxs-lookup"><span data-stu-id="28a36-200">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="28a36-201">`Wait-Job` 允许您等待特定作业、所有作业或任何作业完成。</span><span class="sxs-lookup"><span data-stu-id="28a36-201">`Wait-Job` lets you wait for a particular job, for all jobs, or for any of the jobs to be completed.</span></span>

<span data-ttu-id="28a36-202">以下命令使用 `Wait-Job` cmdlet 等待 **ID** 为的作业</span><span class="sxs-lookup"><span data-stu-id="28a36-202">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="28a36-203">因此，在作业完成之前，会禁止 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="28a36-203">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="28a36-204">还可以等待预先确定的时间段。</span><span class="sxs-lookup"><span data-stu-id="28a36-204">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="28a36-205">此命令使用 **Timeout** 参数将等待时间限制为120秒。</span><span class="sxs-lookup"><span data-stu-id="28a36-205">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="28a36-206">当时间到期时，命令提示符会返回，但作业将继续在后台运行。</span><span class="sxs-lookup"><span data-stu-id="28a36-206">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="28a36-207">停止作业</span><span class="sxs-lookup"><span data-stu-id="28a36-207">Stopping a job</span></span>

<span data-ttu-id="28a36-208">若要停止后台作业，请使用 `Stop-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28a36-208">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="28a36-209">下面的命令启动一个作业以获取系统事件日志中的每个条目。</span><span class="sxs-lookup"><span data-stu-id="28a36-209">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="28a36-210">它将作业对象保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="28a36-210">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="28a36-211">以下命令停止作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-211">The following command stops the job.</span></span> <span data-ttu-id="28a36-212">它使用管道运算符 (`|`) 将变量中的作业发送 `$job` 到 `Stop-Job` 。</span><span class="sxs-lookup"><span data-stu-id="28a36-212">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="28a36-213">删除作业</span><span class="sxs-lookup"><span data-stu-id="28a36-213">Deleting a job</span></span>

<span data-ttu-id="28a36-214">若要删除后台作业，请使用 `Remove-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28a36-214">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="28a36-215">以下命令删除变量中的作业 `$job` 。</span><span class="sxs-lookup"><span data-stu-id="28a36-215">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="28a36-216">调查失败的作业</span><span class="sxs-lookup"><span data-stu-id="28a36-216">Investigating a failed job</span></span>

<span data-ttu-id="28a36-217">若要确定作业失败的原因，请使用作业对象的 **Reason** 属性。</span><span class="sxs-lookup"><span data-stu-id="28a36-217">To find out why a job failed, use the **Reason** property of the job object.</span></span>

<span data-ttu-id="28a36-218">下面的命令启动不包含所需凭据的作业。</span><span class="sxs-lookup"><span data-stu-id="28a36-218">The following command starts a job without the required credentials.</span></span> <span data-ttu-id="28a36-219">它将作业对象保存在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="28a36-219">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="28a36-220">以下命令使用 Reason 属性查找导致作业失败的错误。</span><span class="sxs-lookup"><span data-stu-id="28a36-220">The following command uses the Reason property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="28a36-221">在这种情况下，作业失败，因为远程计算机需要显式凭据才能运行该命令。</span><span class="sxs-lookup"><span data-stu-id="28a36-221">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="28a36-222">**Reason** 属性的值为：</span><span class="sxs-lookup"><span data-stu-id="28a36-222">The value of the **Reason** property is:</span></span>

<span data-ttu-id="28a36-223">连接到远程服务器失败，出现以下错误消息： "访问被拒绝"。</span><span class="sxs-lookup"><span data-stu-id="28a36-223">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="28a36-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28a36-224">See also</span></span>

- [<span data-ttu-id="28a36-225">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="28a36-225">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="28a36-226">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="28a36-226">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="28a36-227">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="28a36-227">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="28a36-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="28a36-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="28a36-229">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="28a36-229">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="28a36-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="28a36-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="28a36-231">Get-Job</span><span class="sxs-lookup"><span data-stu-id="28a36-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="28a36-232">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="28a36-232">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="28a36-233">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="28a36-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="28a36-234">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="28a36-234">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="28a36-235">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="28a36-235">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="28a36-236">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="28a36-236">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
