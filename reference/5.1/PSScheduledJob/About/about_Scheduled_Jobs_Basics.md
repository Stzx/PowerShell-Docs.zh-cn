---
description: 说明如何创建和管理计划作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199912"
---
# <a name="about-scheduled-jobs-basics"></a><span data-ttu-id="7fdb4-104">关于计划作业基础知识</span><span class="sxs-lookup"><span data-stu-id="7fdb4-104">About Scheduled Jobs Basics</span></span>

## <a name="short-description"></a><span data-ttu-id="7fdb4-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="7fdb4-105">Short description</span></span>

<span data-ttu-id="7fdb4-106">说明如何创建和管理计划作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-106">Explains how to create and manage scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="7fdb4-107">长说明</span><span class="sxs-lookup"><span data-stu-id="7fdb4-107">Long description</span></span>

<span data-ttu-id="7fdb4-108">本文档介绍如何执行创建和管理计划作业的基本任务。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-108">This document shows how to perform basic tasks of creating and managing scheduled jobs.</span></span> <span data-ttu-id="7fdb4-109">有关更高级任务的信息，请参阅 [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-109">For information about more advanced tasks, see [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span></span>

<span data-ttu-id="7fdb4-110">有关 **PSScheduledJob** 模块中包含的 cmdlet 的详细信息，请参阅 [PSScheduledJob](xref:PSScheduledJob)。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="how-to-create-a-scheduled-job"></a><span data-ttu-id="7fdb4-111">如何创建计划作业</span><span class="sxs-lookup"><span data-stu-id="7fdb4-111">How to create a scheduled job</span></span>

<span data-ttu-id="7fdb4-112">若要创建计划作业，请使用 `Register-ScheduledJob` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-112">To create a scheduled job, use the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="7fdb4-113">该 cmdlet 需要一个名称以及该作业运行的命令或脚本。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-113">The cmdlet requires a name and the commands or script that the job runs.</span></span> <span data-ttu-id="7fdb4-114">您可以通过添加 **RunNow** 参数来立即运行作业，也可以在创建作业时创建作业触发器并设置作业选项，或者编辑现有作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-114">You can either run the job immediately by adding the **RunNow** parameter, or create a job trigger and set job options when you create the job, or edit an existing job.</span></span>

<span data-ttu-id="7fdb4-115">若要创建运行脚本的作业，请使用 **FilePath** 参数指定脚本文件的路径。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-115">To create a job that runs a script, use the **FilePath** parameter to specify the path to the script file.</span></span> <span data-ttu-id="7fdb4-116">若要创建运行命令的作业，请使用 **ScriptBlock** 参数。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-116">To create a job that runs commands, use the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="7fdb4-117">`Register-ScheduledJob`Cmdlet 将创建用于运行命令的 **ProcessJob** `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-117">The `Register-ScheduledJob` cmdlet creates the **ProcessJob** , which runs a `Get-Process` command.</span></span> <span data-ttu-id="7fdb4-118">此计划作业有默认作业选项，没有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-118">This scheduled job has the default job options and no job trigger.</span></span>

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a><span data-ttu-id="7fdb4-119">如何创建作业触发器</span><span class="sxs-lookup"><span data-stu-id="7fdb4-119">How to create a job trigger</span></span>

<span data-ttu-id="7fdb4-120">作业触发器会自动启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-120">Job triggers start a scheduled job automatically.</span></span> <span data-ttu-id="7fdb4-121">作业触发器可以是一次性或定期计划或事件，例如当用户登录或 Windows 启动时。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-121">A job trigger can be one-time or recurring schedule or an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="7fdb4-122">每个作业可以有零个、一个或多个作业触发器。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-122">Each job can have zero, one, or multiple job triggers.</span></span>

<span data-ttu-id="7fdb4-123">若要创建作业触发器，请使用 `New-JobTrigger` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-123">To create a job trigger, use the `New-JobTrigger` cmdlet.</span></span> <span data-ttu-id="7fdb4-124">下面的命令创建一个作业触发器，该触发器在每星期一和星期四的上午5:00 启动作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-124">The following command creates a job trigger that starts a job every Monday and Thursday at 5:00 AM.</span></span>
<span data-ttu-id="7fdb4-125">该命令将作业触发器保存在 `$T` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-125">The command saves the job trigger in the `$T` variable.</span></span>

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

<span data-ttu-id="7fdb4-126">作业触发器是可选的。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-126">Job triggers are optional.</span></span> <span data-ttu-id="7fdb4-127">你可以随时通过将 **RunNow** 参数添加到 `Register-ScheduledJob` 命令或使用 cmdlet 来启动计划的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-127">You can start a scheduled job at any time by adding the **RunNow** parameter to your `Register-ScheduledJob` command, or by using the `Start-Job` cmdlets.</span></span>

## <a name="how-to-add-a-job-trigger"></a><span data-ttu-id="7fdb4-128">如何添加作业触发器</span><span class="sxs-lookup"><span data-stu-id="7fdb4-128">How to add a job trigger</span></span>

<span data-ttu-id="7fdb4-129">将作业触发器添加到计划作业时，会将作业触发器添加到计划作业的计划作业 XML 文件中，并成为计划作业的一部分。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-129">When you add a job trigger to a scheduled job, the job trigger is added to the scheduled job XML file for the scheduled job and becomes part of the scheduled job.</span></span>

<span data-ttu-id="7fdb4-130">你可以在创建计划作业时向计划作业添加作业触发器，或者编辑现有作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-130">You can add a job trigger to a scheduled job when you create the scheduled job, or edit an existing job.</span></span> <span data-ttu-id="7fdb4-131">你可以随时更改计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-131">You can change the job trigger of a scheduled job at any time.</span></span>

<span data-ttu-id="7fdb4-132">PowerShell 使用任务计划程序使用的一些相同的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-132">PowerShell uses some of the same job triggers that Task Scheduler uses.</span></span> <span data-ttu-id="7fdb4-133">有关作业触发器的详细信息，请参阅 [get-jobtrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-133">For detailed information about job triggers, see the help topic for the [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet.</span></span>

<span data-ttu-id="7fdb4-134">下面的示例使用展开来创建 `$JobParms` 传递到 cmdlet 的参数值 `Register-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-134">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="7fdb4-135">有关详细信息，请参阅[about_Splatting。](../../Microsoft.PowerShell.Core/About/about_Splatting.md)</span><span class="sxs-lookup"><span data-stu-id="7fdb4-135">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="7fdb4-136">用于 `Register-ScheduledJob` `@JobParms` 创建计划作业的。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-136">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="7fdb4-137">它使用 **Trigger** 参数在变量中指定作业触发器 `$T` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-137">It uses the **Trigger** parameter to specify the job trigger in the `$T` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="7fdb4-138">你还可以随时将作业触发器添加到现有的计划作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-138">You can also add a job trigger to an existing scheduled job at any time.</span></span> <span data-ttu-id="7fdb4-139">`Add-JobTrigger`Cmdlet 会将变量中的作业触发器添加 `$T` 到 **ProcessJob** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-139">The `Add-JobTrigger` cmdlet adds the job trigger in the `$T` variable to the **ProcessJob** scheduled job.</span></span>

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

<span data-ttu-id="7fdb4-140">因此，作业触发器将在每星期一和星期四的上午5:00 自动启动 **ProcessJob** 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-140">As a result, the job trigger starts the **ProcessJob** automatically every Monday and Thursday at 5:00 AM.</span></span>

## <a name="how-to-get-a-job-trigger"></a><span data-ttu-id="7fdb4-141">如何获取作业触发器</span><span class="sxs-lookup"><span data-stu-id="7fdb4-141">How to get a job trigger</span></span>

<span data-ttu-id="7fdb4-142">若要获取计划作业的作业触发器，请使用 `Get-JobTrigger` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-142">To get the job trigger of a scheduled job, use the `Get-JobTrigger` cmdlet.</span></span> <span data-ttu-id="7fdb4-143">使用 " **名称** "、" **ID** " 和 " **InputObject** " 参数指定计划的作业，而不指定作业触发器。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-143">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job trigger.</span></span>

<span data-ttu-id="7fdb4-144">`Get-JobTrigger` 获取 **ProcessJob** 的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-144">`Get-JobTrigger` gets the job trigger of the **ProcessJob** .</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a><span data-ttu-id="7fdb4-145">如何创建作业选项</span><span class="sxs-lookup"><span data-stu-id="7fdb4-145">How to create job options</span></span>

<span data-ttu-id="7fdb4-146">作业选项用于建立启动和运行作业的条件。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-146">Job options establish conditions for starting and running the job.</span></span> <span data-ttu-id="7fdb4-147">每个作业都有默认作业选项，除非您更改它们。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-147">Every job has the default job options unless you change them.</span></span> <span data-ttu-id="7fdb4-148">由于作业选项可以阻止作业在计划的时间运行，因此了解作业选项并仔细使用这些选项非常重要。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-148">Because job options can prevent a job from running at the scheduled time, it is important to understand the job options and use them carefully.</span></span>

<span data-ttu-id="7fdb4-149">PowerShell 使用任务计划程序使用的相同作业选项。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-149">PowerShell uses the same job options that Task Scheduler uses.</span></span> <span data-ttu-id="7fdb4-150">有关作业选项的详细信息，请参阅 [get-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption)的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-150">For detailed information about the job options, see the help topic for [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

<span data-ttu-id="7fdb4-151">作业选项存储在计划的作业 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-151">Job options are stored in the scheduled job XML file.</span></span> <span data-ttu-id="7fdb4-152">你可以在创建计划作业时设置作业选项，或者随时对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-152">You can set job options when you create a scheduled job or change them at any time.</span></span>

<span data-ttu-id="7fdb4-153">`New-ScheduledJobOption`Cmdlet 将创建一个计划作业选项，其中 **WakeToRun** 计划作业选项设置为 True。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-153">The `New-ScheduledJobOption` cmdlet creates a scheduled job option in which the **WakeToRun** scheduled job option is set to True.</span></span> <span data-ttu-id="7fdb4-154">即使在计划的开始时间计算机处于睡眠或休眠状态， **WakeToRun** 选项也会运行该计划作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-154">The **WakeToRun** option runs the scheduled job even if the computer is in the Sleep or Hibernate state at the scheduled start time.</span></span> <span data-ttu-id="7fdb4-155">该命令将作业选项保存在 `$O` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-155">The command saves the job options in the `$O` variable.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a><span data-ttu-id="7fdb4-156">如何获取作业选项</span><span class="sxs-lookup"><span data-stu-id="7fdb4-156">How to get job options</span></span>

<span data-ttu-id="7fdb4-157">若要获取计划作业的作业选项，请使用 `Get-ScheduledJobOption` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-157">To get the job options of a scheduled job, use the `Get-ScheduledJobOption` cmdlet.</span></span> <span data-ttu-id="7fdb4-158">使用 " **名称** "、" **ID** " 和 " **InputObject** " 参数指定计划的作业，而不是作业选项。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-158">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job options.</span></span>

<span data-ttu-id="7fdb4-159">`Get-ScheduledJobOption` 获取 **ProcessJob** 的作业选项。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-159">`Get-ScheduledJobOption` gets the job options of the **ProcessJob** .</span></span>

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
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

## <a name="how-to-change-job-options"></a><span data-ttu-id="7fdb4-160">如何更改作业选项</span><span class="sxs-lookup"><span data-stu-id="7fdb4-160">How to change job options</span></span>

<span data-ttu-id="7fdb4-161">你可以在创建计划作业时更改计划作业的作业选项，或者编辑现有作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-161">You can change the job options of a scheduled job when you create a scheduled job or edit an existing job.</span></span>

<span data-ttu-id="7fdb4-162">Splatted `$JobParms` 传递给 `Add-JobTrigger` cmdlet 来创建进程作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-162">The splatted `$JobParms` are passed to the `Add-JobTrigger` cmdlet to create the process job.</span></span> <span data-ttu-id="7fdb4-163">它使用 **get-scheduledjoboption** 参数来指定变量中的作业选项 `$O` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-163">It uses the **ScheduledJobOption** parameter to specify the job options in the `$O` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

<span data-ttu-id="7fdb4-164">你还可以随时将作业选项更改为现有的计划作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-164">You can also change the job options to an existing scheduled job at any time.</span></span>
<span data-ttu-id="7fdb4-165">以下命令使用 cmdlet 将 `Set-ScheduledJobOption` **ProcessJob** get-scheduledjob 的 **WakeToRun** 选项的值更改为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-165">The following command uses the `Set-ScheduledJobOption` cmdlet to change the value of the **WakeToRun** option of the **ProcessJob** scheduledJob to **True** .</span></span>

<span data-ttu-id="7fdb4-166">`Set` **PSScheduledJob** 模块中的 cmdlet （如 `Set-ScheduledJobOption` cmdlet）没有 **Name** 或 **ID** 参数。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-166">The `Set` cmdlets in the **PSScheduledJob** module, such as the `Set-ScheduledJobOption` cmdlet, don't have **Name** or **ID** parameters.</span></span> <span data-ttu-id="7fdb4-167">可以使用 **InputObject** 参数指定计划作业选项，或通过管道将计划作业从 cmdlet 传递 `Get-ScheduledJobOption` 给 `Set-ScheduledJobOption` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-167">You can use the **InputObject** parameter to specify the scheduled job options or pipe a scheduled job from `Get-ScheduledJobOption` cmdlet to `Set-ScheduledJobOption`.</span></span>

<span data-ttu-id="7fdb4-168">此示例使用 `Get-ScheduledJob` cmdlet 获取 ProcessJob。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-168">This example uses the `Get-ScheduledJob` cmdlet to get the ProcessJob.</span></span> <span data-ttu-id="7fdb4-169">它使用 `Get-ScheduledJobOption` cmdlet 获取 **ProcessJob** 中的作业选项，并使用 cmdlet 将 `Set-ScheduledJobOption` ProcessJob 中的 **WakeToRun** 作业选项更改为 True。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-169">It uses the `Get-ScheduledJobOption` cmdlet to get the job options in the **ProcessJob** and the `Set-ScheduledJobOption` cmdlet to change the **WakeToRun** job option in the ProcessJob to True.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a><span data-ttu-id="7fdb4-170">如何获取计划的作业实例</span><span class="sxs-lookup"><span data-stu-id="7fdb4-170">How to get scheduled job instances</span></span>

<span data-ttu-id="7fdb4-171">启动计划的作业时，PowerShell 会创建类似于标准 PowerShell 后台作业的作业实例。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-171">When a scheduled job is started, PowerShell creates a job instance that is similar to a standard PowerShell background job.</span></span> <span data-ttu-id="7fdb4-172">可以使用作业 cmdlet （如 `Get-Job` ） `Stop-Job` 和 `Receive-Job` 管理作业实例。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-172">You can use the job cmdlets, such as `Get-Job`, `Stop-Job` and `Receive-Job` to manage the job instances.</span></span>

> [!NOTE]
> <span data-ttu-id="7fdb4-173">若要在计划作业的实例上使用作业 cmdlet，则必须将 **PSScheduledJob** 模块导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-173">To use the job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="7fdb4-174">若要导入 **PSScheduledJob** 模块，请键入 `Import-Module PSScheduledJob` 或使用任何计划的作业 cmdlet，例如 `Get-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-174">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="7fdb4-175">若要获取 PowerShell 计划作业的所有实例和所有活动的标准作业，请使用 `Get-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-175">To get all instances of PowerShell scheduled jobs, and all active standard jobs, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="7fdb4-176">`Import-Module`Cmdlet 将导入 **PSScheduledJob** 模块，并 `Get-Job` 获取本地计算机上的作业。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-176">The `Import-Module` cmdlet imports the **PSScheduledJob** module and `Get-Job` gets the jobs on the local computer.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job
```

<span data-ttu-id="7fdb4-177">`Get-Job` 获取本地计算机上的 **ProcessJob** 的实例。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-177">`Get-Job` gets instances of **ProcessJob** on the local computer.</span></span>

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

<span data-ttu-id="7fdb4-178">默认显示不显示开始时间，这通常会区分同一计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-178">The default display does not show the start time, which typically distinguishes instances of the same scheduled job.</span></span>

<span data-ttu-id="7fdb4-179">`Get-Job`Cmdlet 沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-179">The `Get-Job` cmdlet sends objects down the pipeline.</span></span> <span data-ttu-id="7fdb4-180">`Format-Table`Cmdlet 显示计划作业的 **名称** 、 **ID** 和 **system.windows.media.animation.timeline.begintime** 属性。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-180">The `Format-Table` cmdlet displays the **Name** , **ID** , and **BeginTime** properties of the scheduled job.</span></span>

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

## <a name="get-scheduled-job-results"></a><span data-ttu-id="7fdb4-181">获取计划作业结果</span><span class="sxs-lookup"><span data-stu-id="7fdb4-181">Get scheduled job results</span></span>

<span data-ttu-id="7fdb4-182">若要获取某个计划作业的实例的结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-182">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7fdb4-183">若要在计划作业的实例上使用作业 cmdlet，则必须将 **PSScheduledJob** 模块导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-183">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="7fdb4-184">若要导入 **PSScheduledJob** 模块，请键入 `Import-Module PSScheduledJob` 或使用任何计划的作业 cmdlet，例如 `Get-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-184">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="7fdb4-185">此示例将获取 **ProcessJob** 计划作业的最新实例的结果 (ID = 51) 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-185">This examples gets the results of the newest instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

<span data-ttu-id="7fdb4-186">计划作业的结果保存在磁盘上，因此不需要 **Keep** 参数 `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-186">The results of scheduled jobs are saved on disk, so the **Keep** parameter of `Receive-Job` is not required.</span></span> <span data-ttu-id="7fdb4-187">但是，如果不使用 **Keep** 参数，只需在每个 PowerShell 会话中获得一次计划作业的结果。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-187">However, without the **Keep** parameter, you can get the results of a scheduled job only once in each PowerShell session.</span></span> <span data-ttu-id="7fdb4-188">若要启动新的 PowerShell 会话，请键入 `PowerShell` 或打开一个新的 powershell 窗口。</span><span class="sxs-lookup"><span data-stu-id="7fdb4-188">To start a new PowerShell session, type `PowerShell` or open a new PowerShell window.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fdb4-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fdb4-189">See also</span></span>

[<span data-ttu-id="7fdb4-190">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="7fdb4-190">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="7fdb4-191">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="7fdb4-191">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="7fdb4-192">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="7fdb4-192">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="7fdb4-193">about_Splatting md</span><span class="sxs-lookup"><span data-stu-id="7fdb4-193">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="7fdb4-194">[PSScheduledJob](xref:PSScheduledJob) 模块 cmdlet</span><span class="sxs-lookup"><span data-stu-id="7fdb4-194">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="7fdb4-195">任务计划程序</span><span class="sxs-lookup"><span data-stu-id="7fdb4-195">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
