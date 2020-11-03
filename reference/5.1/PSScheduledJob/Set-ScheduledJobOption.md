---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197774"
---
# <span data-ttu-id="b8eb7-103">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b8eb7-103">Set-ScheduledJobOption</span></span>

## <span data-ttu-id="b8eb7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b8eb7-104">SYNOPSIS</span></span>
<span data-ttu-id="b8eb7-105">更改计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-105">Changes the job options of a scheduled job.</span></span>

## <span data-ttu-id="b8eb7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8eb7-106">SYNTAX</span></span>

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="b8eb7-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8eb7-107">DESCRIPTION</span></span>
<span data-ttu-id="b8eb7-108">**Set-ScheduledJobOptions** cmdlet 可更改计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-108">The **Set-ScheduledJobOptions** cmdlet changes the job options of scheduled jobs.</span></span>

<span data-ttu-id="b8eb7-109">若要更改计划作业的选项，请首先使用 Get-ScheduledJobOption cmdlet 来获取计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-109">To change the options of a scheduled job, begin by using the Get-ScheduledJobOption cmdlet to get the job options of a scheduled job.</span></span>
<span data-ttu-id="b8eb7-110">然后，通过管道将这些选项传递给 **Set-ScheduledJobOption** 或将其保存在某个变量中，并且使用 *Set-ScheduledJobOption* cmdlet 的 **InputObject** 参数来标识这些选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-110">Then, pipe the options to **Set-ScheduledJobOption** or save the options in a variable and use the *InputObject* parameter of **Set-ScheduledJobOption** cmdlet to identify the options.</span></span>
<span data-ttu-id="b8eb7-111">使用 **Set-ScheduledJobOption** 的剩余参数来更改作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-111">Use the remaining parameters of **Set-ScheduledJobOption** to change the job options.</span></span>

<span data-ttu-id="b8eb7-112">若要启用作业选项，请使用设置该选项的参数。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-112">To turn on a job option, use the parameter that sets that option.</span></span>
<span data-ttu-id="b8eb7-113">若要关闭某个选项，请键入参数名称、冒号 (： ) 和 $False。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-113">To turn off an option, type the parameter name, a colon (:), and $False.</span></span>
<span data-ttu-id="b8eb7-114">例如，若要关闭 *RunElevated* 选项，请键入 `-RunElevated:$False` 。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-114">For example, to turn off the *RunElevated* option, type `-RunElevated:$False`.</span></span>

<span data-ttu-id="b8eb7-115">每个作业选项对象都包括 JobDefinition 属性，该属性包含计划作业，以便在作业选项发生更改后保留计划作业的关联内容。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-115">Each job options object includes a JobDefinition property that contains the scheduled job, so the association with the scheduled job is retained when the job options are changed.</span></span>

<span data-ttu-id="b8eb7-116">计划作业选项确定作业在由任务计划程序启动后的运行方式。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-116">The scheduled job options determine how the job runs when it is started by Task Scheduler.</span></span>
<span data-ttu-id="b8eb7-117">这些选项不适用于在使用 Start-Job cmdlet 启动计划作业时使用。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-117">These options to not apply when you use the Start-Job cmdlet to start a scheduled job.</span></span>

<span data-ttu-id="b8eb7-118">**Get-scheduledjoboption** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-118">**Set-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="b8eb7-119">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="b8eb7-120">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="b8eb7-121">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b8eb7-122">示例</span><span class="sxs-lookup"><span data-stu-id="b8eb7-122">EXAMPLES</span></span>

### <span data-ttu-id="b8eb7-123">示例1：更改作业选项</span><span class="sxs-lookup"><span data-stu-id="b8eb7-123">Example 1: Change job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
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
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

<span data-ttu-id="b8eb7-124">此示例显示了如何更改本地计算机上的计划作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-124">This example shows how to change the options of a scheduled job on the local computer.</span></span>

<span data-ttu-id="b8eb7-125">第一个命令使用 Get-ScheduledJobOption cmdlet 来获取 DeployPackage 计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-125">The first command uses the Get-ScheduledJobOption cmdlet to get the job options of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="b8eb7-126">输出显示 "WakeToRun" 和 "RunElevated" 属性设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-126">The output shows that the WakeToRun and RunElevated properties are set to $False.</span></span>

<span data-ttu-id="b8eb7-127">此命令不是必需的；包含它只是为了显示选项更改的效果。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-127">This command is not required; it is included only to show the effect of the option change.</span></span>

### <span data-ttu-id="b8eb7-128">示例2：更改所有远程计划作业的选项</span><span class="sxs-lookup"><span data-stu-id="b8eb7-128">Example 2: Change an option on all remote scheduled jobs</span></span>

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

<span data-ttu-id="b8eb7-129">此命令会将 *IdleTimeout* 的值从一个小时更改 (默认值) 为 Server01 计算机上所有计划作业的两个小时。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-129">This command changes the value of the *IdleTimeout* from one hour (the default value) to two hours on all scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="b8eb7-130">该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-130">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="b8eb7-131">远程命令以获取计算机上所有计划作业的 Get-ScheduledJob 命令开头。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-131">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="b8eb7-132">计划作业将通过管道传递给 Get-ScheduledJobOption cmdlet，该 cmdlet 可获取计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-132">The scheduled jobs are piped to the Get-ScheduledJobOption cmdlet, which gets the job options of the scheduled jobs.</span></span>
<span data-ttu-id="b8eb7-133">每个作业选项对象都包含 JobDefinition 属性，该属性包括计划作业，因此选项对象与计划作业保持关联，即使该作业出现更改也是如此。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-133">Each job options object contains a JobDefinition property that contains the scheduled job, so the options object remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="b8eb7-134">将作业触发器传递给 **get-scheduledjoboption** cmdlet，该 cmdlet 会将 *IdleTimeout* 选项的值更改为两个小时 (2:00:00) 。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-134">The job triggers are piped to the **Set-ScheduledJobOption** cmdlet, which changes the value of the *IdleTimeout* option to two hours (2:00:00).</span></span>

## <span data-ttu-id="b8eb7-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8eb7-135">PARAMETERS</span></span>

### <span data-ttu-id="b8eb7-136">-ContinueIfGoingOnBattery</span><span class="sxs-lookup"><span data-stu-id="b8eb7-136">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="b8eb7-137">如果计算机在正在运行计划作业时切换到电池电源（断开交流电源），请不要停止运行该作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-137">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="b8eb7-138">默认情况下，计划作业在计算机断开交流电源时将停止运行。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-138">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="b8eb7-139">*ContinueIfGoingOnBattery* 参数将计划作业的 StopIfGoingOnBatteries 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-139">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-140">-DoNotAllowDemandStart</span><span class="sxs-lookup"><span data-stu-id="b8eb7-140">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="b8eb7-141">仅在触发作业时它才启动。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-141">Start the job only when it is triggered.</span></span>
<span data-ttu-id="b8eb7-142">用户无法手动启动作业，例如通过使用任务计划程序中的 Run 功能。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-142">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="b8eb7-143">此参数仅影响任务计划程序。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-143">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="b8eb7-144">它不会阻止用户使用 Start-Job cmdlet 来启动作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-144">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="b8eb7-145">*DoNotAllowDemandStart* 参数将计划作业的 DoNotAllowDemandStart 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-145">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-146">-HideInTaskScheduler</span><span class="sxs-lookup"><span data-stu-id="b8eb7-146">-HideInTaskScheduler</span></span>
<span data-ttu-id="b8eb7-147">不会在任务计划程序中显示作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-147">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="b8eb7-148">此值仅影响运行该作业的计算机。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-148">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="b8eb7-149">默认情况下，计划任务将显示在任务计划程序中。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-149">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="b8eb7-150">即使某个任务处于隐藏状态，用户也可以通过选择 "任务计划程序中的" **显示隐藏的任务** "视图选项来显示该任务。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-150">Even if a task is hidden, users can display the task by selecting the **Show hidden tasks** view option in Task Scheduler.</span></span>

<span data-ttu-id="b8eb7-151">*HideInTaskScheduler* 参数将计划作业的 ShowInTaskScheduler 属性值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-151">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-152">-IdleDuration</span><span class="sxs-lookup"><span data-stu-id="b8eb7-152">-IdleDuration</span></span>
<span data-ttu-id="b8eb7-153">指定在启动作业之前计算机必须处于空闲状态的时长。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-153">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="b8eb7-154">默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-154">The default value is 10 minutes.</span></span>
<span data-ttu-id="b8eb7-155">如果在 *IdleTimeout* 的值过期前，计算机在指定的持续时间内不处于空闲状态，则在下一个计划时间（如果有）之前计划作业不会启动。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-155">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="b8eb7-156">输入一个 timespan 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **timespan** 对象的值。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-156">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="b8eb7-157">若要启用此值，请使用 *StartIfIdle* 参数。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-157">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="b8eb7-158">默认情况下，计划作业的 StartIfNotIdle 属性设置为 $True，Windows PowerShell 将忽略 *IdleDuration* 和 *IdleTimeout* 值。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-158">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-159">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="b8eb7-159">-IdleTimeout</span></span>
<span data-ttu-id="b8eb7-160">指定在启动作业之前计算机必须处于空闲状态的时长。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-160">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="b8eb7-161">默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-161">The default value is 10 minutes.</span></span>
<span data-ttu-id="b8eb7-162">如果在 **IdleTimeout** 的值过期前，计算机在指定的持续时间内不处于空闲状态，则在下一个计划时间（如果有）之前计划作业不会启动。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-162">If the computer is not idle for the specified duration before the value of **IdleTimeout** expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="b8eb7-163">输入一个 timespan 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **timespan** 对象的值。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-163">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="b8eb7-164">若要启用此值，请使用 *StartIfIdle* 参数。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-164">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="b8eb7-165">默认情况下，计划作业的 StartIfNotIdle 属性设置为 $True，Windows PowerShell 将忽略 *IdleDuration* 和 *IdleTimeout* 值。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-165">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b8eb7-166">-InputObject</span></span>
<span data-ttu-id="b8eb7-167">指定作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-167">Specifies the job options.</span></span>
<span data-ttu-id="b8eb7-168">输入包含 **ScheduledJobOptions** 对象的变量，或者键入获取 **ScheduledJobOptions** 对象的命令或表达式，如 Get-ScheduledJobOption 命令。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-168">Enter a variable that contains **ScheduledJobOptions** objects or type a command or expression that gets **ScheduledJobOptions** objects, such as a Get-ScheduledJobOption command.</span></span>
<span data-ttu-id="b8eb7-169">还可以通过管道将 **ScheduledJobOptions** 对象传递给 **get-scheduledjoboption** 。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-169">You can also pipe a **ScheduledJobOptions** object to **Set-ScheduledJobOption** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-170">-MultipleInstancePolicy</span><span class="sxs-lookup"><span data-stu-id="b8eb7-170">-MultipleInstancePolicy</span></span>
<span data-ttu-id="b8eb7-171">确定系统如何在计划作业的某个实例正在运行时响应启动该作业的其他实例。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-171">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="b8eb7-172">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="b8eb7-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b8eb7-173">IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="b8eb7-173">IgnoreNew.</span></span>
<span data-ttu-id="b8eb7-174">忽略新的作业实例。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-174">The new job instance is ignored.</span></span>
<span data-ttu-id="b8eb7-175">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-175">This is the default value.</span></span>
- <span data-ttu-id="b8eb7-176">并行。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-176">Parallel.</span></span>
<span data-ttu-id="b8eb7-177">立即启动新的作业实例。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-177">The new job instance starts immediately.</span></span>
- <span data-ttu-id="b8eb7-178">队列。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-178">Queue.</span></span>
<span data-ttu-id="b8eb7-179">在当前实例完成后立即启动新的作业实例。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-179">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="b8eb7-180">StopExisting.</span><span class="sxs-lookup"><span data-stu-id="b8eb7-180">StopExisting.</span></span>
<span data-ttu-id="b8eb7-181">停止当前的作业实例，并启动新的实例。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-181">The current instance of the job stop and the new instance starts.</span></span>

<span data-ttu-id="b8eb7-182">若要运行该作业，必须满足作业计划的所有条件。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-182">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="b8eb7-183">例如，如果不满足 *RequireNetwork* 、 *IdleDuration* 和 *IdleTimeout* 参数设置的条件，则不会启动作业实例，无论此参数的值如何。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-183">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-184">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b8eb7-184">-PassThru</span></span>
<span data-ttu-id="b8eb7-185">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-185">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b8eb7-186">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-186">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-187">-RequireNetwork</span><span class="sxs-lookup"><span data-stu-id="b8eb7-187">-RequireNetwork</span></span>
<span data-ttu-id="b8eb7-188">仅在网络连接可用时才运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-188">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="b8eb7-189">如果指定了此参数，但网络在计划开始时间不可用，则在下一个计划开始时间（如果有）之前该作业不会运行。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-189">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="b8eb7-190">*RequireNetwork* 参数将计划作业的 RunWithoutNetwork 属性值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-190">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-191">-RestartOnIdleResume</span><span class="sxs-lookup"><span data-stu-id="b8eb7-191">-RestartOnIdleResume</span></span>
<span data-ttu-id="b8eb7-192">在计算机处于空闲状态后重新启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-192">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="b8eb7-193">在计算机处于活动状态（退出空闲状态）后，将此参数与可挂起正在运行的计划作业的 *StopIfGoingOffIdle* 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-193">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="b8eb7-194">*RestartOnIdleResume* 参数将计划作业的 RestartOnIdleResume 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-194">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-195">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="b8eb7-195">-RunElevated</span></span>
<span data-ttu-id="b8eb7-196">使用运行计划作业的计算机上 Administrators 组成员权限来运行该作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-196">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="b8eb7-197">若要使用管理员权限启用计划作业，请使用 Register-ScheduledJob 的 *Credential* 参数为作业提供显式凭据。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-197">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="b8eb7-198">**RunElevated** 参数将计划作业的 **RunElevated** 属性值设置为 True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-198">The **RunElevated** parameter sets the value of the **RunElevated** property of scheduled jobs to True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-199">-StartIfIdle</span><span class="sxs-lookup"><span data-stu-id="b8eb7-199">-StartIfIdle</span></span>
<span data-ttu-id="b8eb7-200">如果在 **IdleDuration** 参数指定的时间到期之前，计算机在 *IdleTimeout* 参数指定的时间内已处于空闲状态，将启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-200">Starts the scheduled job if the computer has been idle for the time specified by the **IdleDuration** parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="b8eb7-201">默认情况下，将忽略 *IdleDuration* 和 *IdleTimeout* 参数，并且作业将在计划开始时间启动，即使计算机处于繁忙状态也是如此。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-201">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="b8eb7-202">如果指定了此参数，但计算机在计划开始时间处于繁忙状态（不空闲），则在下一个计划开始时间（如果有）之前该作业不会运行。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-202">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="b8eb7-203">*StartIfIdle* 参数将计划作业的 **StartIfNotIdle** 属性值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-203">The *StartIfIdle* parameter sets the value of the **StartIfNotIdle** property of scheduled jobs to False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-204">-StartIfOnBattery</span><span class="sxs-lookup"><span data-stu-id="b8eb7-204">-StartIfOnBattery</span></span>
<span data-ttu-id="b8eb7-205">在计划开始时间启动计划作业，即使计算机使用电池电源运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-205">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="b8eb7-206">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-206">The default value is False.</span></span>

<span data-ttu-id="b8eb7-207">*StartIfOnBattery* 参数将计划作业的 **StartIfOnBatteries** 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-207">The *StartIfOnBattery* parameter sets the value of the **StartIfOnBatteries** property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-208">-StopIfGoingOffIdle</span><span class="sxs-lookup"><span data-stu-id="b8eb7-208">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="b8eb7-209">如果计算机在计划作业正在运行时处于活动状态（不空闲），则挂起运行的作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-209">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="b8eb7-210">默认情况下，计划作业将在计算机处于活动状态时挂起，而在计算机再次处于空闲状态时恢复运行。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-210">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="b8eb7-211">若要更改该默认行为，请使用 *RestartOnIdleResume* 参数。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-211">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="b8eb7-212">*StopIfGoingOffIdle* 参数将计划作业的 StopIfGoingOffIdle 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-212">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-213">-WakeToRun</span><span class="sxs-lookup"><span data-stu-id="b8eb7-213">-WakeToRun</span></span>
<span data-ttu-id="b8eb7-214">在计划开始时间，将计算机从休眠或睡眠状态唤醒，以便它可以运行该作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-214">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="b8eb7-215">默认情况下，如果计算机在计划开始时间处于休眠或睡眠状态，则不会运行该作业。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-215">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="b8eb7-216">*WakeToRun* 参数将计划作业的 WakeToRun 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-216">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8eb7-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b8eb7-217">CommonParameters</span></span>
<span data-ttu-id="b8eb7-218">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8eb7-219">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8eb7-220">输入</span><span class="sxs-lookup"><span data-stu-id="b8eb7-220">INPUTS</span></span>

### <span data-ttu-id="b8eb7-221">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="b8eb7-221">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="b8eb7-222">你可以通过管道将计划作业选项对象传递给 **Set-ScheduledJobOption** 。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-222">You can pipe a scheduled job options object to **Set-ScheduledJobOption** .</span></span>

## <span data-ttu-id="b8eb7-223">输出</span><span class="sxs-lookup"><span data-stu-id="b8eb7-223">OUTPUTS</span></span>

### <span data-ttu-id="b8eb7-224">None 或 Get-scheduledjob。 ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="b8eb7-224">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="b8eb7-225">当使用 *Passthru* 参数时， **Set-ScheduledJobOption** 将返回已更改的作业选项。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-225">When you use the *Passthru* parameter, **Set-ScheduledJobOption** returns the job options that were changed.</span></span>
<span data-ttu-id="b8eb7-226">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="b8eb7-226">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b8eb7-227">注释</span><span class="sxs-lookup"><span data-stu-id="b8eb7-227">NOTES</span></span>

## <span data-ttu-id="b8eb7-228">相关链接</span><span class="sxs-lookup"><span data-stu-id="b8eb7-228">RELATED LINKS</span></span>

[<span data-ttu-id="b8eb7-229">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-229">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="b8eb7-230">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-230">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="b8eb7-231">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b8eb7-231">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="b8eb7-232">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-232">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="b8eb7-233">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b8eb7-233">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="b8eb7-234">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-234">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="b8eb7-235">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b8eb7-235">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="b8eb7-236">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b8eb7-236">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="b8eb7-237">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-237">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="b8eb7-238">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b8eb7-238">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="b8eb7-239">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b8eb7-239">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="b8eb7-240">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-240">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="b8eb7-241">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b8eb7-241">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="b8eb7-242">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b8eb7-242">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="b8eb7-243">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b8eb7-243">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="b8eb7-244">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b8eb7-244">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
