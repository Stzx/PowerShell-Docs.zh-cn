---
description: 介绍计划作业并说明如何在 PowerShell 和任务计划程序中使用和管理计划作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199915"
---
# <a name="about-scheduled-jobs"></a><span data-ttu-id="712b7-104">关于计划作业</span><span class="sxs-lookup"><span data-stu-id="712b7-104">About Scheduled Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="712b7-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="712b7-105">Short description</span></span>

<span data-ttu-id="712b7-106">介绍计划作业并说明如何在 PowerShell 和任务计划程序中使用和管理计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-106">Describes scheduled jobs and explains how to use and manage scheduled jobs in PowerShell and in Task Scheduler.</span></span>

## <a name="long-description"></a><span data-ttu-id="712b7-107">长说明</span><span class="sxs-lookup"><span data-stu-id="712b7-107">Long description</span></span>

<span data-ttu-id="712b7-108">PowerShell 计划作业是 PowerShell 后台作业和任务计划程序任务的有用混合。</span><span class="sxs-lookup"><span data-stu-id="712b7-108">PowerShell scheduled jobs are a useful hybrid of PowerShell background jobs and Task Scheduler tasks.</span></span>

<span data-ttu-id="712b7-109">与 PowerShell 后台作业一样，计划作业在后台以异步方式运行。</span><span class="sxs-lookup"><span data-stu-id="712b7-109">Like PowerShell background jobs, scheduled jobs run asynchronously in the background.</span></span> <span data-ttu-id="712b7-110">可以使用作业 cmdlet （如、、和）管理已运行的计划作业的实例 `Start-Job` `Get-Job` `Stop-Job` `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="712b7-110">Instances of scheduled jobs that have run can be managed by using the job cmdlets, such as `Start-Job`, `Get-Job`, `Stop-Job`, and `Receive-Job`.</span></span>

<span data-ttu-id="712b7-111">与任务计划程序任务一样，计划作业保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="712b7-111">Like Task Scheduler tasks, scheduled jobs are saved to disk.</span></span> <span data-ttu-id="712b7-112">可以在任务计划程序中查看和管理作业，根据需要启用和禁用这些作业，运行这些作业，或将其用作模板，建立用于启动作业的一次性或重复计划，或设置作业的开始时间。</span><span class="sxs-lookup"><span data-stu-id="712b7-112">You can view and manage the jobs in Task Scheduler, enable and disable them as needed, run them or use them as templates, establish a one-time or recurring schedules for starting the jobs, or set conditions under which the jobs start.</span></span>

<span data-ttu-id="712b7-113">此外，计划作业实例的结果将以易于访问的格式保存到磁盘，同时提供作业输出的运行日志。</span><span class="sxs-lookup"><span data-stu-id="712b7-113">In addition, the results of scheduled job instances are saved to disk in an easily accessible format, providing a running log of job output.</span></span> <span data-ttu-id="712b7-114">计划作业附带一组用于管理它们的自定义 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="712b7-114">Scheduled jobs come with a customized set of cmdlets for managing them.</span></span> <span data-ttu-id="712b7-115">Cmdlet 可用于创建、编辑、管理、禁用和重新启用计划作业、作业触发器和作业选项。</span><span class="sxs-lookup"><span data-stu-id="712b7-115">The cmdlets let you create, edit, manage, disable, and re-enable scheduled jobs, job triggers and job options.</span></span>

<span data-ttu-id="712b7-116">这一套全面的灵活的工具使计划的作业成为许多专业 PowerShell IT 解决方案的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="712b7-116">This comprehensive and flexible set of tools make scheduled jobs an essential component of many professional PowerShell IT solutions.</span></span>

<span data-ttu-id="712b7-117">计划的作业 cmdlet 包含在随 PowerShell 一起安装的 **PSScheduledJob** 模块中。</span><span class="sxs-lookup"><span data-stu-id="712b7-117">The scheduled job cmdlets are included in the **PSScheduledJob** module that is installed with PowerShell.</span></span> <span data-ttu-id="712b7-118">此模块是在 PowerShell 3.0 中引入的，并且适用于 powershell 3.0 和更高版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="712b7-118">This module was introduced in PowerShell 3.0 and works in PowerShell 3.0 and later versions of PowerShell.</span></span> <span data-ttu-id="712b7-119">有关 **PSScheduledJob** 模块中包含的 cmdlet 的详细信息，请参阅 [PSScheduledJob](xref:PSScheduledJob)。</span><span class="sxs-lookup"><span data-stu-id="712b7-119">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

<span data-ttu-id="712b7-120">有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="712b7-120">For more information about PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

<span data-ttu-id="712b7-121">有关任务计划程序的详细信息，请参阅 [任务计划程序](/windows/desktop/TaskSchd/task-scheduler-reference)。</span><span class="sxs-lookup"><span data-stu-id="712b7-121">For more information about Task Scheduler, see [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-reference).</span></span>

> [!NOTE]
> <span data-ttu-id="712b7-122">可以在任务计划程序中查看和管理 PowerShell 计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-122">You can view and manage PowerShell scheduled jobs in Task Scheduler.</span></span> <span data-ttu-id="712b7-123">PowerShell 作业和计划作业 cmdlet 仅适用于在 PowerShell 中创建的计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-123">The PowerShell jobs and scheduled job cmdlets work only on scheduled jobs that are created in PowerShell.</span></span>

## <a name="quick-start"></a><span data-ttu-id="712b7-124">快速入门</span><span class="sxs-lookup"><span data-stu-id="712b7-124">Quick start</span></span>

<span data-ttu-id="712b7-125">此示例将创建一个计划作业，该作业在每天凌晨3:00 开始，并运行 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="712b7-125">This example creates a scheduled job that starts every day at 3:00 AM and runs the `Get-Process` cmdlet.</span></span> <span data-ttu-id="712b7-126">即使计算机在电池上运行，也会启动该作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-126">The job starts even if the computer is running on batteries.</span></span>

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

<span data-ttu-id="712b7-127">`Get-ScheduledJob`Cmdlet 将获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-127">The `Get-ScheduledJob` cmdlet gets the scheduled jobs on the local computer.</span></span>

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

<span data-ttu-id="712b7-128">`Get-JobTrigger` 获取 **ProcessJob** 的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="712b7-128">`Get-JobTrigger` gets the job triggers of **ProcessJob** .</span></span> <span data-ttu-id="712b7-129">输入参数指定计划的作业，而不是触发器，因为触发器保存在计划作业中。</span><span class="sxs-lookup"><span data-stu-id="712b7-129">The input parameters specify the scheduled job, not the trigger, because triggers are saved in a scheduled job.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

<span data-ttu-id="712b7-130">此示例使用 cmdlet 的 **ContinueIfGoingOnBattery** 参数 `Set-ScheduledJob` 将 **ProcessJob** 的 **StopIfGoingOnBatteries** 属性更改为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="712b7-130">This example uses the **ContinueIfGoingOnBattery** parameter of the `Set-ScheduledJob` cmdlet to change the **StopIfGoingOnBatteries** property of **ProcessJob** to **False** .</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="712b7-131">`Get-ScheduledJob`Cmdlet 将获取 **ProcessJob** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-131">The `Get-ScheduledJob` cmdlet gets the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

<span data-ttu-id="712b7-132">该 `Get-Job` cmdlet 将获取 **ProcessJob** 计划作业的所有已运行的实例。</span><span class="sxs-lookup"><span data-stu-id="712b7-132">The `Get-Job` cmdlet gets all instances of the **ProcessJob** scheduled job that have run thus far.</span></span> <span data-ttu-id="712b7-133">`Get-Job`仅当 **PSScheduledJob** 模块导入到当前会话中时，cmdlet 才会获取计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-133">The `Get-Job` cmdlet gets scheduled jobs only when the **PSScheduledJob** module is imported into the current session.</span></span>

> [!TIP]
> <span data-ttu-id="712b7-134">请注意，使用计划作业 cmdlet 来管理计划作业，但使用作业 cmdlet 来管理计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="712b7-134">Notice that you use the scheduled job cmdlets to manage scheduled jobs, but you use the job cmdlets to manage instances of scheduled jobs.</span></span>

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

<span data-ttu-id="712b7-135">该 `Receive-Job` cmdlet 将获取 **ProcessJob** 计划作业的最新实例的结果 (ID = 51) 。</span><span class="sxs-lookup"><span data-stu-id="712b7-135">The `Receive-Job` cmdlet gets the results of the most recent instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Receive-Job -ID 51
```

<span data-ttu-id="712b7-136">即使该 `Receive-Job` 命令不包含 **Keep** 参数，该作业的结果也将保存在磁盘上，直到您删除它们或超出最大结果数。</span><span class="sxs-lookup"><span data-stu-id="712b7-136">Even though the `Receive-Job` command did not include the **Keep** parameter, the results of the job are saved on disk until you delete them or the maximum number of results are exceeded.</span></span>

<span data-ttu-id="712b7-137">作业结果在此会话中不再可用，但如果你启动新会话或打开新的 PowerShell 窗口，则该作业的结果将再次可用。</span><span class="sxs-lookup"><span data-stu-id="712b7-137">The job results are no longer available in this session, but if you start a new session or open a new PowerShell window, the results of the job are available again.</span></span>

<span data-ttu-id="712b7-138">以下命令使用 cmdlet 的 **DefinitionName** 参数 `Start-Job` 来启动 **ProcessJob** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-138">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the **ProcessJob** scheduled job.</span></span>

<span data-ttu-id="712b7-139">使用 cmdlet 启动的作业 `Start-Job` 是标准 PowerShell 后台作业，而不是计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="712b7-139">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="712b7-140">与所有后台作业一样，这些作业会立即启动，它们不受作业选项的影响，也不受作业触发器的影响，并且其输出不会保存在计划的作业目录的输出目录中。</span><span class="sxs-lookup"><span data-stu-id="712b7-140">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers, and their output is not saved in the output directory of the scheduled job directory.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="712b7-141">`Unregister-ScheduledJob`Cmdlet 将删除 **ProcessJob** 计划作业及其所有已保存的作业实例结果。</span><span class="sxs-lookup"><span data-stu-id="712b7-141">The `Unregister-ScheduledJob` cmdlet deletes the **ProcessJob** scheduled job and all saved results of its job instances.</span></span>

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a><span data-ttu-id="712b7-142">计划的作业概念</span><span class="sxs-lookup"><span data-stu-id="712b7-142">Scheduled jobs concepts</span></span>

<span data-ttu-id="712b7-143">计划作业运行命令或脚本。</span><span class="sxs-lookup"><span data-stu-id="712b7-143">A scheduled job runs commands or a script.</span></span> <span data-ttu-id="712b7-144">计划作业可以包括启动作业的作业触发器，以及用于设置运行作业的条件的作业选项。</span><span class="sxs-lookup"><span data-stu-id="712b7-144">A scheduled job can include job triggers that start the job and job options that set conditions for running the job.</span></span>

<span data-ttu-id="712b7-145">作业触发器会自动启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-145">A job trigger starts a scheduled job automatically.</span></span> <span data-ttu-id="712b7-146">作业触发器可以包含一次性或定期计划，或者指定事件，例如当用户登录或 Windows 启动时。</span><span class="sxs-lookup"><span data-stu-id="712b7-146">A job trigger can include a one-time or recurring schedule or specify an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="712b7-147">计划作业可以有一个或多个作业触发器，你可以创建、添加、启用、禁用和获取作业触发器。</span><span class="sxs-lookup"><span data-stu-id="712b7-147">A scheduled job can have one or more job triggers, and you can create, add, enable, disable, and get job triggers.</span></span>

<span data-ttu-id="712b7-148">作业触发器是可选的。</span><span class="sxs-lookup"><span data-stu-id="712b7-148">Job triggers are optional.</span></span> <span data-ttu-id="712b7-149">可以通过使用 `Start-Job cmdlet` 或将 **RunNow** 参数添加到命令，来立即启动计划作业 `Register-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="712b7-149">You can start scheduled jobs immediately by using the `Start-Job cmdlet`, or by adding the **RunNow** parameter to your `Register-ScheduledJob` command.</span></span>

<span data-ttu-id="712b7-150">作业选项设置运行计划作业的条件。</span><span class="sxs-lookup"><span data-stu-id="712b7-150">Job options set the conditions for running a scheduled job.</span></span> <span data-ttu-id="712b7-151">每个计划作业都有一个作业选项对象。</span><span class="sxs-lookup"><span data-stu-id="712b7-151">Every scheduled job has one job options object.</span></span> <span data-ttu-id="712b7-152">你可以创建和编辑作业选项对象，并将其添加到一个或多个计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-152">You can create and edit job options objects and add them to one or more scheduled jobs.</span></span>

<span data-ttu-id="712b7-153">每次启动计划作业时，将创建一个作业实例。</span><span class="sxs-lookup"><span data-stu-id="712b7-153">Each time a scheduled job starts, a job instance is created.</span></span> <span data-ttu-id="712b7-154">使用 PowerShell 作业 cmdlet 查看和管理作业实例。</span><span class="sxs-lookup"><span data-stu-id="712b7-154">Use the PowerShell job cmdlets to view and manage the job instance.</span></span>

<span data-ttu-id="712b7-155">计划作业保存到磁盘并使用 cmdlet 谓词， `Register` 而不是 `New` 。</span><span class="sxs-lookup"><span data-stu-id="712b7-155">Scheduled jobs are saved to disk and use the cmdlet verb, `Register`, instead of `New`.</span></span> <span data-ttu-id="712b7-156">XML 文件位于本地计算机上的目录中 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` 。</span><span class="sxs-lookup"><span data-stu-id="712b7-156">The XML files are located on the local computer in the directory `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

<span data-ttu-id="712b7-157">PowerShell 为每个计划作业创建一个目录，并将作业命令、作业触发器、作业选项和作业结果保存在计划的作业目录中。</span><span class="sxs-lookup"><span data-stu-id="712b7-157">PowerShell creates a directory for each scheduled job and saves the job commands, job triggers, job options and job results in the scheduled job directory.</span></span> <span data-ttu-id="712b7-158">不会单独将作业触发器和作业选项保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="712b7-158">Job triggers and job options aren't saved to disk independently.</span></span>
<span data-ttu-id="712b7-159">它们保存在与它们关联的每个计划作业的计划作业 XML 中。</span><span class="sxs-lookup"><span data-stu-id="712b7-159">They are saved in the scheduled job XML of each scheduled job with which they are associated.</span></span>

<span data-ttu-id="712b7-160">计划作业、作业触发器和作业选项在 PowerShell 中显示为对象。</span><span class="sxs-lookup"><span data-stu-id="712b7-160">Scheduled jobs, job triggers, and job options appear in PowerShell as objects.</span></span>
<span data-ttu-id="712b7-161">对象是了的，这使它们可以在命令和脚本中轻松发现和使用。</span><span class="sxs-lookup"><span data-stu-id="712b7-161">The objects are interlinked, which makes them easy to discover and use in commands and scripts.</span></span>

<span data-ttu-id="712b7-162">计划作业显示为 **ScheduledJobDefinition** 对象。</span><span class="sxs-lookup"><span data-stu-id="712b7-162">Scheduled jobs appear as **ScheduledJobDefinition** objects.</span></span> <span data-ttu-id="712b7-163">**ScheduledJobDefinition** 对象包含一个 **JobTriggers** 属性，该属性包含计划作业的作业触发器和一个包含作业选项的 **Options** 属性。</span><span class="sxs-lookup"><span data-stu-id="712b7-163">The **ScheduledJobDefinition** object has a **JobTriggers** property that contains the job triggers of the scheduled job and an **Options** property that contains the job options.</span></span> <span data-ttu-id="712b7-164">分别表示作业触发器和作业选项的 **ScheduledJobTriggers** 和 **ScheduledJobOptions** 对象，每个对象都有一个 **JobDefinition** 属性，其中包含关联的计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-164">The **ScheduledJobTriggers** and **ScheduledJobOptions** objects that represent job triggers and job options, respectively, each have a **JobDefinition** property that contains the scheduled job with which they are associated.</span></span> <span data-ttu-id="712b7-165">利用这种递归互连，可以轻松查找计划作业的触发器和选项，查找、编写脚本，并显示与任何作业触发器或作业选项关联的计划作业。</span><span class="sxs-lookup"><span data-stu-id="712b7-165">This recursive interconnection makes it easy to find the triggers and options of a scheduled job and to find, script, and display the scheduled job to which any job trigger or job option is associated.</span></span>

## <a name="see-also"></a><span data-ttu-id="712b7-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="712b7-166">See also</span></span>

[<span data-ttu-id="712b7-167">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="712b7-167">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="712b7-168">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="712b7-168">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="712b7-169">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="712b7-169">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

<span data-ttu-id="712b7-170">[PSScheduledJob](xref:PSScheduledJob) 模块 cmdlet</span><span class="sxs-lookup"><span data-stu-id="712b7-170">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="712b7-171">任务计划程序</span><span class="sxs-lookup"><span data-stu-id="712b7-171">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
