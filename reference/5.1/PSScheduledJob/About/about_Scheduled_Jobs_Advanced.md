---
description: 说明高级计划作业主题，包括构成计划作业的基础的文件结构。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199914"
---
# <a name="about-scheduled-jobs-advanced"></a><span data-ttu-id="c59c8-104">关于计划作业高级</span><span class="sxs-lookup"><span data-stu-id="c59c8-104">About Scheduled Jobs Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="c59c8-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="c59c8-105">Short description</span></span>

<span data-ttu-id="c59c8-106">说明高级计划作业主题，包括构成计划作业的基础的文件结构。</span><span class="sxs-lookup"><span data-stu-id="c59c8-106">Explains advanced scheduled job topics, including the file structure that underlies scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="c59c8-107">长说明</span><span class="sxs-lookup"><span data-stu-id="c59c8-107">Long description</span></span>

<span data-ttu-id="c59c8-108">有关 **PSScheduledJob** 模块中包含的 cmdlet 的详细信息，请参阅 [PSScheduledJob](xref:PSScheduledJob)。</span><span class="sxs-lookup"><span data-stu-id="c59c8-108">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="scheduled-job-directories-and-files"></a><span data-ttu-id="c59c8-109">计划的作业目录和文件</span><span class="sxs-lookup"><span data-stu-id="c59c8-109">Scheduled job directories and files</span></span>

<span data-ttu-id="c59c8-110">PowerShell 计划作业既是 PowerShell 作业，又是任务计划程序任务。</span><span class="sxs-lookup"><span data-stu-id="c59c8-110">PowerShell scheduled jobs are both PowerShell jobs and Task Scheduler tasks.</span></span>
<span data-ttu-id="c59c8-111">每个计划作业都在任务计划程序中注册，并保存在磁盘上，Microsoft .NET 框架序列化 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="c59c8-111">Each scheduled job is registered in Task Scheduler and saved on disk in Microsoft .NET Framework Serialization XML format.</span></span>

<span data-ttu-id="c59c8-112">在创建计划作业时，PowerShell 会在本地计算机上的目录中为计划作业创建一个目录 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-112">When you create a scheduled job, PowerShell creates a directory for the scheduled job in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span> <span data-ttu-id="c59c8-113">目录名称与作业名称相同。</span><span class="sxs-lookup"><span data-stu-id="c59c8-113">The directory name is the same as the job name.</span></span>

<span data-ttu-id="c59c8-114">下面是一个示例 **ScheduledJobs** 目录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-114">The following is a sample **ScheduledJobs** directory.</span></span>

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

<span data-ttu-id="c59c8-115">每个计划作业都有其自己的目录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-115">Each scheduled job has its own directory.</span></span> <span data-ttu-id="c59c8-116">目录包含计划的作业 XML 文件和 **输出** 子目录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-116">The directory contains the scheduled job XML file and an **Output** subdirectory.</span></span>

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

<span data-ttu-id="c59c8-117">计划作业的 **输出** 目录包含其执行历史记录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-117">The **Output** directory for a scheduled job contains its execution history.</span></span>
<span data-ttu-id="c59c8-118">每次作业触发器启动计划作业时，PowerShell 都会在输出目录中创建一个时间戳名称的目录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-118">Each time a job trigger starts a scheduled job, PowerShell creates a timestamp-named directory in the output directory.</span></span> <span data-ttu-id="c59c8-119">Timestamp 目录包含 **Results.xml** 文件中的作业结果和 **Status.xml** 文件中的作业状态。</span><span class="sxs-lookup"><span data-stu-id="c59c8-119">The timestamp directory contains the results of the job in a **Results.xml** file and the job status in a **Status.xml** file.</span></span>

<span data-ttu-id="c59c8-120">以下命令显示 **ProcessJob** 计划作业的执行历史记录目录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-120">The following command shows the execution history directories for the **ProcessJob** scheduled job.</span></span>

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

<span data-ttu-id="c59c8-121">您可以打开并检查 **ScheduledJobDefinition.xml** 、 **Results.xml** 和 **Status.xml** 文件，或使用 `Select-XML` cmdlet 分析文件。</span><span class="sxs-lookup"><span data-stu-id="c59c8-121">You can open and examine the **ScheduledJobDefinition.xml** , **Results.xml** and **Status.xml** files or use the `Select-XML` cmdlet to parse the files.</span></span>

> [!WARNING]
> <span data-ttu-id="c59c8-122">不要编辑 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="c59c8-122">Do not edit the XML files.</span></span> <span data-ttu-id="c59c8-123">如果任何 XML 文件包含无效的 XML，则 PowerShell 会删除计划的作业及其执行历史记录（包括作业结果）。</span><span class="sxs-lookup"><span data-stu-id="c59c8-123">If any XML file contains invalid XML, PowerShell deletes the scheduled job and its execution history, including job results.</span></span>

## <a name="start-a-scheduled-job-immediately"></a><span data-ttu-id="c59c8-124">立即启动计划作业</span><span class="sxs-lookup"><span data-stu-id="c59c8-124">Start a scheduled job immediately</span></span>

<span data-ttu-id="c59c8-125">可以通过以下两种方式之一立即启动计划作业：</span><span class="sxs-lookup"><span data-stu-id="c59c8-125">You can start a scheduled job immediately in one of two ways:</span></span>

- <span data-ttu-id="c59c8-126">运行 `Start-Job` cmdlet 以启动任何计划作业。</span><span class="sxs-lookup"><span data-stu-id="c59c8-126">Run the `Start-Job` cmdlet to start any scheduled job.</span></span>
- <span data-ttu-id="c59c8-127">将 **RunNow** 参数添加到 `Register-ScheduledJob` 命令，以便在命令运行后立即启动作业。</span><span class="sxs-lookup"><span data-stu-id="c59c8-127">Add the **RunNow** parameter to your `Register-ScheduledJob` command to start the job as soon as the command is run.</span></span>

<span data-ttu-id="c59c8-128">使用 cmdlet 启动的作业 `Start-Job` 是标准 PowerShell 后台作业，而不是计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="c59c8-128">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="c59c8-129">与所有后台作业一样，这些作业会立即启动，它们不受作业选项的影响，也不受作业触发器的影响。</span><span class="sxs-lookup"><span data-stu-id="c59c8-129">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers.</span></span> <span data-ttu-id="c59c8-130">作业输出不会保存在计划作业目录的 **输出** 目录中。</span><span class="sxs-lookup"><span data-stu-id="c59c8-130">The job output isn't saved in the **Output** directory of the scheduled job directory.</span></span>

<span data-ttu-id="c59c8-131">以下命令使用 cmdlet 的 **DefinitionName** 参数 `Start-Job` 来启动 ProcessJob 计划作业。</span><span class="sxs-lookup"><span data-stu-id="c59c8-131">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the ProcessJob scheduled job.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="c59c8-132">若要管理作业并获取作业结果，请使用作业 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c59c8-132">To manage the job and get the job results, use the job cmdlets.</span></span> <span data-ttu-id="c59c8-133">有关作业 cmdlet 的详细信息，请参阅 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="c59c8-133">For more information about the job cmdlets, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c59c8-134">若要在计划作业的实例上使用作业 cmdlet，则必须将 **PSScheduledJob** 模块导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="c59c8-134">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="c59c8-135">若要导入 **PSScheduledJob** 模块，请键入 `Import-Module PSScheduledJob` 或使用任何计划的作业 cmdlet，例如 `Get-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-135">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

## <a name="rename-a-scheduled-job"></a><span data-ttu-id="c59c8-136">重命名计划作业</span><span class="sxs-lookup"><span data-stu-id="c59c8-136">Rename a scheduled job</span></span>

<span data-ttu-id="c59c8-137">若要重命名计划作业，请使用该 cmdlet 的 Name 参数 `Set-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-137">To rename a scheduled job, use the Name parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="c59c8-138">重命名计划作业时，PowerShell 会更改计划作业的名称和计划作业目录。</span><span class="sxs-lookup"><span data-stu-id="c59c8-138">When you rename a scheduled job, PowerShell changes the name of the scheduled job and the scheduled job directory.</span></span> <span data-ttu-id="c59c8-139">但是，它不会更改已运行的计划作业的实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c59c8-139">However, it doesn't change the names of instances of the scheduled job that have already run.</span></span>

## <a name="get-start-and-end-times"></a><span data-ttu-id="c59c8-140">获取开始时间和结束时间</span><span class="sxs-lookup"><span data-stu-id="c59c8-140">Get start and end times</span></span>

<span data-ttu-id="c59c8-141">若要获取作业实例开始和结束的日期和时间，请使用 **PSBeginTime** 为计划作业返回的 get-scheduledjob 对象的 PSBeginTime 和 **PSEndTime** 属性 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-141">To get the dates and times that job instances started and ended, use the **PSBeginTime** and **PSEndTime** properties of the ScheduledJob object that `Get-Job` returns for scheduled jobs.</span></span>

<span data-ttu-id="c59c8-142">下面的示例使用 cmdlet 的 **Property** 参数 `Format-Table` 来显示表中每个作业实例的 **PSBeginTime** 和 **PSEndTime** 属性。</span><span class="sxs-lookup"><span data-stu-id="c59c8-142">The following example uses the **Property** parameter of the `Format-Table` cmdlet to display the **PSBeginTime** and **PSEndTime** properties of each job instance in a table.</span></span> <span data-ttu-id="c59c8-143">名为 **Label** 的计算属性显示每个作业实例的运行时间。</span><span class="sxs-lookup"><span data-stu-id="c59c8-143">A calculated property named **Label** displays the elapsed time of each job instance.</span></span>

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a><span data-ttu-id="c59c8-144">管理执行历史记录</span><span class="sxs-lookup"><span data-stu-id="c59c8-144">Manage execution history</span></span>

<span data-ttu-id="c59c8-145">您可以确定为每个计划作业保存的作业实例结果数，并删除任何计划作业的执行历史记录和保存的作业结果。</span><span class="sxs-lookup"><span data-stu-id="c59c8-145">You can determine the number of job instance results that are saved for each scheduled job and delete the execution history and saved job results of any scheduled job.</span></span>

<span data-ttu-id="c59c8-146">计划作业的 **ExecutionHistoryLength** 属性决定为计划作业保存的作业实例结果数。</span><span class="sxs-lookup"><span data-stu-id="c59c8-146">The **ExecutionHistoryLength** property of a scheduled job determines how many job instance results are saved for the scheduled job.</span></span> <span data-ttu-id="c59c8-147">当保存的结果数超过 **ExecutionHistoryLength** 属性的值时，PowerShell 会删除最旧实例的结果，以便为最新实例的结果腾出空间。</span><span class="sxs-lookup"><span data-stu-id="c59c8-147">When the number of saved results exceeds the value of the **ExecutionHistoryLength** property, PowerShell deletes the results of the oldest instance to make room for the results of the newest instance.</span></span>

<span data-ttu-id="c59c8-148">默认情况下，PowerShell 会保存每个计划作业的执行历史记录和32实例的结果。</span><span class="sxs-lookup"><span data-stu-id="c59c8-148">By default, PowerShell saves the execution history and results of 32 instances of each scheduled job.</span></span> <span data-ttu-id="c59c8-149">若要更改该值，请使用 **MaxResultCount** 或 Cmdlet 的 MaxResultCount `Register-ScheduledJob` 参数 `Set-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-149">To change that value, use the **MaxResultCount** parameters of the `Register-ScheduledJob` or `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="c59c8-150">若要删除计划作业的执行历史记录和所有结果，请使用 cmdlet 的 **ClearExecutionHistory** 参数 `Set-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-150">To delete the execution history and all results for a scheduled job, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="c59c8-151">删除此执行历史记录不会阻止 PowerShell 保存计划作业的新实例的结果。</span><span class="sxs-lookup"><span data-stu-id="c59c8-151">Deleting this execution history does not prevent PowerShell from saving the results of new instances of the scheduled job.</span></span>

<span data-ttu-id="c59c8-152">下面的示例使用展开来创建 `$JobParms` 传递到 cmdlet 的参数值 `Register-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="c59c8-152">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="c59c8-153">有关详细信息，请参阅[about_Splatting。](../../Microsoft.PowerShell.Core/About/about_Splatting.md)</span><span class="sxs-lookup"><span data-stu-id="c59c8-153">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="c59c8-154">用于 `Register-ScheduledJob` `@JobParms` 创建计划作业的。</span><span class="sxs-lookup"><span data-stu-id="c59c8-154">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="c59c8-155">该命令使用值为12的 **MaxResultCount** 参数来仅保存计划作业的12个最新的作业实例结果。</span><span class="sxs-lookup"><span data-stu-id="c59c8-155">The command uses the **MaxResultCount** parameter with a value of 12 to save only the 12 newest job instance results of the scheduled job.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="c59c8-156">以下命令使用 cmdlet 的 **MaxResultCount** 参数将 `Set-ScheduledJob` 保存的实例结果的数目增加到</span><span class="sxs-lookup"><span data-stu-id="c59c8-156">The following command uses the **MaxResultCount** parameter of the `Set-ScheduledJob` cmdlet to increase the number of saved instance results to</span></span>
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

<span data-ttu-id="c59c8-157">以下命令删除 **ProcessJob** 计划作业的执行历史记录和当前保存的结果。</span><span class="sxs-lookup"><span data-stu-id="c59c8-157">The following command deletes the execution history and the current saved results of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="c59c8-158">以下命令将获取计算机上所有计划作业的 name 和 **ExecutionHistoryLength** 属性的值，并将它们显示在一个表中。</span><span class="sxs-lookup"><span data-stu-id="c59c8-158">The following command gets the values of the name and **ExecutionHistoryLength** properties of all scheduled jobs on the computer and displays them in a table.</span></span>

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a><span data-ttu-id="c59c8-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c59c8-159">See also</span></span>

[<span data-ttu-id="c59c8-160">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="c59c8-160">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="c59c8-161">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="c59c8-161">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="c59c8-162">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="c59c8-162">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="c59c8-163">about_Splatting md</span><span class="sxs-lookup"><span data-stu-id="c59c8-163">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="c59c8-164">[PSScheduledJob](xref:PSScheduledJob) 模块 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c59c8-164">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="c59c8-165">任务计划程序</span><span class="sxs-lookup"><span data-stu-id="c59c8-165">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
