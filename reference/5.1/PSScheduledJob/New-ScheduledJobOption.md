---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197785"
---
# <span data-ttu-id="d016a-103">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d016a-103">New-ScheduledJobOption</span></span>

## <span data-ttu-id="d016a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d016a-104">SYNOPSIS</span></span>
<span data-ttu-id="d016a-105">为计划作业创建包含高级选项的对象。</span><span class="sxs-lookup"><span data-stu-id="d016a-105">Creates an object that contains advanced options for a scheduled job.</span></span>

## <span data-ttu-id="d016a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d016a-106">SYNTAX</span></span>

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="d016a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d016a-107">DESCRIPTION</span></span>
<span data-ttu-id="d016a-108">**New-ScheduledJobOption** cmdlet 可为计划作业创建包含高级选项的对象。</span><span class="sxs-lookup"><span data-stu-id="d016a-108">The **New-ScheduledJobOption** cmdlet creates an object that contains advanced options for a scheduled job.</span></span>

<span data-ttu-id="d016a-109">你可以使用 **New-ScheduledJobOption** 返回的 **ScheduledJobOptions** 对象，为新的或现有的计划作业设置作业选项。</span><span class="sxs-lookup"><span data-stu-id="d016a-109">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set job options for a new or existing scheduled job.</span></span>
<span data-ttu-id="d016a-110">或者，你可以使用 Get-ScheduledJobOption cmdlet 来设置作业选项，以获取现有计划作业的作业选项，或使用哈希表值来表示作业选项。</span><span class="sxs-lookup"><span data-stu-id="d016a-110">Alternatively, you can set job options by using the Get-ScheduledJobOption cmdlet to get the job options of an existing scheduled job or by using a hash table value to represent the job options.</span></span>

<span data-ttu-id="d016a-111">如果没有参数，则 **get-scheduledjoboption** 将生成一个对象，该对象包含所有选项的默认值。</span><span class="sxs-lookup"><span data-stu-id="d016a-111">Without parameters, **New-ScheduledJobOption** generates an object that contains the default values for all of the options.</span></span>
<span data-ttu-id="d016a-112">由于所有属性都是可编辑的（JobDefinition 属性除外），因此你可以将生成的对象用作模板，并为你的企业创建标准选项对象。</span><span class="sxs-lookup"><span data-stu-id="d016a-112">Because all of the properties except for the JobDefinition property can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="d016a-113">当创建计划作业并设置计划作业选项时，应检查所有计划作业选项的默认值。</span><span class="sxs-lookup"><span data-stu-id="d016a-113">When creating scheduled jobs and setting scheduled job options, review the default values of all scheduled job options.</span></span>
<span data-ttu-id="d016a-114">仅在满足为其执行所设置的所有条件时才运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-114">Scheduled jobs run only when all conditions set for their execution are satisfied.</span></span>

<span data-ttu-id="d016a-115">**Get-scheduledjoboption** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。</span><span class="sxs-lookup"><span data-stu-id="d016a-115">**New-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="d016a-116">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="d016a-116">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="d016a-117">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="d016a-117">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="d016a-118">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d016a-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d016a-119">示例</span><span class="sxs-lookup"><span data-stu-id="d016a-119">EXAMPLES</span></span>

### <span data-ttu-id="d016a-120">示例1：创建具有默认值的计划作业选项对象</span><span class="sxs-lookup"><span data-stu-id="d016a-120">Example 1: Create a scheduled job option object with default values</span></span>

```
PS C:\> New-ScheduledJobOption
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="d016a-121">此命令创建具有所有默认值的计划作业选项对象。</span><span class="sxs-lookup"><span data-stu-id="d016a-121">This command creates a scheduled job option object that has all of the default values.</span></span>

### <span data-ttu-id="d016a-122">示例2：使用自定义值创建计划作业选项对象</span><span class="sxs-lookup"><span data-stu-id="d016a-122">Example 2: Create a scheduled job option object with custom values</span></span>

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="d016a-123">以下命令将创建一个计划作业对象，该对象需要网络并运行该计划作业，即使计算机未连接到交流电源也是如此。</span><span class="sxs-lookup"><span data-stu-id="d016a-123">The following command creates a scheduled job object that requires the network and runs the scheduled job even if the computer is not connected to AC power.</span></span>

<span data-ttu-id="d016a-124">输出显示 *RequireNetwork* 参数已将 RunWithoutNetwork 属性的值更改为 $False，而 *StartIfOnBattery* 参数将 StartIfOnBatteries 属性的值更改为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-124">The output shows that the *RequireNetwork* parameter changed the value of the RunWithoutNetwork property to $False and the *StartIfOnBattery* parameter changed the value of the StartIfOnBatteries property to $True.</span></span>

### <span data-ttu-id="d016a-125">示例3：设置新计划作业的选项</span><span class="sxs-lookup"><span data-stu-id="d016a-125">Example 3: Set options for a new scheduled job</span></span>

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : True
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="d016a-126">此示例显示了如何使用 **New-ScheduledJobOption** 返回的 **ScheduledJobOptions** 对象为新的计划作业设置选项。</span><span class="sxs-lookup"><span data-stu-id="d016a-126">This example shows how to use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set the options for a new scheduled job.</span></span>

### <span data-ttu-id="d016a-127">示例4：对计划作业选项对象的属性进行排序</span><span class="sxs-lookup"><span data-stu-id="d016a-127">Example 4: Sort the properties of a scheduled job option object</span></span>

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

<span data-ttu-id="d016a-128">此示例显示了如何按字母顺序对 **ScheduledJobOptions** 对象的属性进行排序以供轻松阅读。</span><span class="sxs-lookup"><span data-stu-id="d016a-128">This example shows how to sort the properties of a **ScheduledJobOptions** object in alphabetical order for easy reading.</span></span>

<span data-ttu-id="d016a-129">第一个命令使用 **New-ScheduledJobOption** cmdlet 创建 **ScheduledJobOptions** 对象。</span><span class="sxs-lookup"><span data-stu-id="d016a-129">The first command uses the **New-ScheduledJobOption** cmdlet to create a **ScheduledJobOptions** object.</span></span>
<span data-ttu-id="d016a-130">此命令使用 *WakeToRun* 参数并将生成的对象保存在 $Options 变量中。</span><span class="sxs-lookup"><span data-stu-id="d016a-130">The command uses the *WakeToRun* parameter and saves the resulting object in the $Options variable.</span></span>

<span data-ttu-id="d016a-131">若要以对象的形式获取 $Options 的属性，第二个命令使用所有 Windows PowerShell 对象的 **PSObject** 属性及其 properties 属性。</span><span class="sxs-lookup"><span data-stu-id="d016a-131">To get the properties of $Options as objects, the second command uses the **PSObject** property of all Windows PowerShell objects and its Properties property.</span></span>
<span data-ttu-id="d016a-132">然后，该命令将属性对象通过管道传递给 Sort-Object cmdlet，该 cmdlet 将按名称的字母顺序对属性进行排序，然后指向 Format-Table cmdlet，后者将在表中显示属性的名称和值。</span><span class="sxs-lookup"><span data-stu-id="d016a-132">The command then pipes the property objects to the Sort-Object cmdlet, which sorts the properties in alphabetical order by name, and then to the Format-Table cmdlet, which displays the names and values of the properties in a table.</span></span>

<span data-ttu-id="d016a-133">这种格式使你可以更轻松地在 $Options 中查找 **ScheduledJobOptions** 对象的 WakeToRun 属性，并验证其值是否已从 "$False" 更改为 "$True"。</span><span class="sxs-lookup"><span data-stu-id="d016a-133">This format makes it much easier to find the WakeToRun property of the **ScheduledJobOptions** object in $Options and to verify that its value was changed from $False to $True.</span></span>

## <span data-ttu-id="d016a-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d016a-134">PARAMETERS</span></span>

### <span data-ttu-id="d016a-135">-ContinueIfGoingOnBattery</span><span class="sxs-lookup"><span data-stu-id="d016a-135">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="d016a-136">如果计算机在正在运行计划作业时切换到电池电源（断开交流电源），请不要停止运行该作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-136">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="d016a-137">默认情况下，计划作业在计算机断开交流电源时将停止运行。</span><span class="sxs-lookup"><span data-stu-id="d016a-137">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="d016a-138">*ContinueIfGoingOnBattery* 参数将计划作业的 StopIfGoingOnBatteries 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-138">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-139">-DoNotAllowDemandStart</span><span class="sxs-lookup"><span data-stu-id="d016a-139">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="d016a-140">仅在触发作业时它才启动。</span><span class="sxs-lookup"><span data-stu-id="d016a-140">Start the job only when it is triggered.</span></span>
<span data-ttu-id="d016a-141">用户无法手动启动作业，例如通过使用任务计划程序中的 Run 功能。</span><span class="sxs-lookup"><span data-stu-id="d016a-141">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="d016a-142">此参数仅影响任务计划程序。</span><span class="sxs-lookup"><span data-stu-id="d016a-142">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="d016a-143">它不会阻止用户使用 Start-Job cmdlet 来启动作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-143">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="d016a-144">*DoNotAllowDemandStart* 参数将计划作业的 DoNotAllowDemandStart 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-144">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-145">-HideInTaskScheduler</span><span class="sxs-lookup"><span data-stu-id="d016a-145">-HideInTaskScheduler</span></span>
<span data-ttu-id="d016a-146">不会在任务计划程序中显示作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-146">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="d016a-147">此值仅影响运行该作业的计算机。</span><span class="sxs-lookup"><span data-stu-id="d016a-147">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="d016a-148">默认情况下，计划任务将显示在任务计划程序中。</span><span class="sxs-lookup"><span data-stu-id="d016a-148">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="d016a-149">即使某个任务处于隐藏状态，用户也可以通过选择 "任务计划程序中的" 显示隐藏的任务 "视图选项来显示该任务。</span><span class="sxs-lookup"><span data-stu-id="d016a-149">Even if a task is hidden, users can display the task by selecting the Show hidden tasks view option in Task Scheduler.</span></span>

<span data-ttu-id="d016a-150">*HideInTaskScheduler* 参数将计划作业的 ShowInTaskScheduler 属性值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="d016a-150">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="d016a-151">-IdleDuration</span><span class="sxs-lookup"><span data-stu-id="d016a-151">-IdleDuration</span></span>
<span data-ttu-id="d016a-152">指定在启动作业之前计算机必须处于空闲状态的时长。</span><span class="sxs-lookup"><span data-stu-id="d016a-152">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="d016a-153">默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="d016a-153">The default value is 10 minutes.</span></span>
<span data-ttu-id="d016a-154">如果在 *IdleTimeout* 的值过期前，计算机在指定的持续时间内不处于空闲状态，则在下一个计划时间（如果有）之前计划作业不会启动。</span><span class="sxs-lookup"><span data-stu-id="d016a-154">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="d016a-155">输入一个 **TimeSpan** 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **TimeSpan** 对象的值。</span><span class="sxs-lookup"><span data-stu-id="d016a-155">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format  that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="d016a-156">若要启用此值，请使用 *StartIfIdle* 参数。</span><span class="sxs-lookup"><span data-stu-id="d016a-156">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="d016a-157">默认情况下，计划作业的 StartIfNotIdle 属性设置为 $True，Windows PowerShell 将忽略 *IdleDuration* 和 *IdleTimeout* 值。</span><span class="sxs-lookup"><span data-stu-id="d016a-157">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="d016a-158">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="d016a-158">-IdleTimeout</span></span>
<span data-ttu-id="d016a-159">指定计划作业等待计算机进入空闲状态的时长。</span><span class="sxs-lookup"><span data-stu-id="d016a-159">Specifies how long the scheduled job waits for the computer to be idle.</span></span>
<span data-ttu-id="d016a-160">如果超过此超时而计算机仍未在 *IdleDuration* 参数指定的时间段保持空闲状态，则在下一个计划时间（如果有）之前该作业不会运行。</span><span class="sxs-lookup"><span data-stu-id="d016a-160">If this timeout expires before the computer remains idle for the time period that is specified by the *IdleDuration* parameter, the job does not run until the next scheduled time, if any.</span></span>
<span data-ttu-id="d016a-161">默认值为 1 小时。</span><span class="sxs-lookup"><span data-stu-id="d016a-161">The default value is one hour.</span></span>

<span data-ttu-id="d016a-162">输入一个 **TimeSpan** 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **TimeSpan** 对象的值。</span><span class="sxs-lookup"><span data-stu-id="d016a-162">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="d016a-163">若要启用此值，请使用 *StartIfIdle* 参数。</span><span class="sxs-lookup"><span data-stu-id="d016a-163">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="d016a-164">默认情况下，计划作业的 StartIfNotIdle 属性设置为 $True，Windows PowerShell 将忽略 *IdleDuration* 和 *IdleTimeout* 值。</span><span class="sxs-lookup"><span data-stu-id="d016a-164">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="d016a-165">-MultipleInstancePolicy</span><span class="sxs-lookup"><span data-stu-id="d016a-165">-MultipleInstancePolicy</span></span>
<span data-ttu-id="d016a-166">确定系统如何在计划作业的某个实例正在运行时响应启动该作业的其他实例。</span><span class="sxs-lookup"><span data-stu-id="d016a-166">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="d016a-167">默认值为 IgnoreNew。</span><span class="sxs-lookup"><span data-stu-id="d016a-167">The default value is IgnoreNew.</span></span>
<span data-ttu-id="d016a-168">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="d016a-168">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d016a-169">IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="d016a-169">IgnoreNew.</span></span>
<span data-ttu-id="d016a-170">忽略新的作业实例。</span><span class="sxs-lookup"><span data-stu-id="d016a-170">The new job instance is ignored.</span></span>
- <span data-ttu-id="d016a-171">并行。</span><span class="sxs-lookup"><span data-stu-id="d016a-171">Parallel.</span></span>
<span data-ttu-id="d016a-172">立即启动新的作业实例。</span><span class="sxs-lookup"><span data-stu-id="d016a-172">The new job instance starts immediately.</span></span>
- <span data-ttu-id="d016a-173">队列。</span><span class="sxs-lookup"><span data-stu-id="d016a-173">Queue.</span></span>
<span data-ttu-id="d016a-174">在当前实例完成后立即启动新的作业实例。</span><span class="sxs-lookup"><span data-stu-id="d016a-174">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="d016a-175">StopExisting.</span><span class="sxs-lookup"><span data-stu-id="d016a-175">StopExisting.</span></span>
<span data-ttu-id="d016a-176">作业的当前实例将停止并启动新实例。</span><span class="sxs-lookup"><span data-stu-id="d016a-176">The current instance of the job stops and the new instance starts.</span></span>

<span data-ttu-id="d016a-177">若要运行该作业，必须满足作业计划的所有条件。</span><span class="sxs-lookup"><span data-stu-id="d016a-177">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="d016a-178">例如，如果不满足 *RequireNetwork* 、 *IdleDuration* 和 *IdleTimeout* 参数设置的条件，则不会启动作业实例，无论此参数的值如何。</span><span class="sxs-lookup"><span data-stu-id="d016a-178">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

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

### <span data-ttu-id="d016a-179">-RequireNetwork</span><span class="sxs-lookup"><span data-stu-id="d016a-179">-RequireNetwork</span></span>
<span data-ttu-id="d016a-180">仅在网络连接可用时才运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-180">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="d016a-181">如果指定了此参数，但网络在计划开始时间不可用，则在下一个计划开始时间（如果有）之前该作业不会运行。</span><span class="sxs-lookup"><span data-stu-id="d016a-181">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="d016a-182">*RequireNetwork* 参数将计划作业的 RunWithoutNetwork 属性值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="d016a-182">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="d016a-183">-RestartOnIdleResume</span><span class="sxs-lookup"><span data-stu-id="d016a-183">-RestartOnIdleResume</span></span>
<span data-ttu-id="d016a-184">在计算机处于空闲状态后重新启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-184">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="d016a-185">在计算机处于活动状态（退出空闲状态）后，将此参数与可挂起正在运行的计划作业的 *StopIfGoingOffIdle* 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="d016a-185">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="d016a-186">*RestartOnIdleResume* 参数将计划作业的 RestartOnIdleResume 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-186">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-187">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="d016a-187">-RunElevated</span></span>
<span data-ttu-id="d016a-188">使用运行计划作业的计算机上 Administrators 组成员权限来运行该作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-188">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="d016a-189">若要使用管理员权限启用计划作业，请使用 Register-ScheduledJob 的 *Credential* 参数为作业提供显式凭据。</span><span class="sxs-lookup"><span data-stu-id="d016a-189">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="d016a-190">*RunElevated* 参数将计划作业的 RunElevated 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-190">The *RunElevated* parameter sets the value of the RunElevated property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-191">-StartIfIdle</span><span class="sxs-lookup"><span data-stu-id="d016a-191">-StartIfIdle</span></span>
<span data-ttu-id="d016a-192">如果在 *IdleDuration* 参数指定的时间到期之前，计算机在 *IdleTimeout* 参数指定的时间内已处于空闲状态，将启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-192">Starts the scheduled job if the computer has been idle for the time specified by the *IdleDuration* parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="d016a-193">默认情况下，将忽略 *IdleDuration* 和 *IdleTimeout* 参数，并且作业将在计划开始时间启动，即使计算机处于繁忙状态也是如此。</span><span class="sxs-lookup"><span data-stu-id="d016a-193">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="d016a-194">如果指定了此参数，但计算机在计划开始时间处于繁忙状态（不空闲），则在下一个计划开始时间（如果有）之前该作业不会运行。</span><span class="sxs-lookup"><span data-stu-id="d016a-194">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="d016a-195">*StartIfIdle* 参数将计划作业的 StartIfNotIdle 属性值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="d016a-195">The *StartIfIdle* parameter sets the value of the StartIfNotIdle property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="d016a-196">-StartIfOnBattery</span><span class="sxs-lookup"><span data-stu-id="d016a-196">-StartIfOnBattery</span></span>
<span data-ttu-id="d016a-197">在计划开始时间启动计划作业，即使计算机使用电池电源运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="d016a-197">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="d016a-198">默认值为 $False。</span><span class="sxs-lookup"><span data-stu-id="d016a-198">The default value is $False.</span></span>

<span data-ttu-id="d016a-199">*StartIfOnBattery* 参数将计划作业的 StartIfOnBatteries 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-199">The *StartIfOnBattery* parameter sets the value of the StartIfOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-200">-StopIfGoingOffIdle</span><span class="sxs-lookup"><span data-stu-id="d016a-200">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="d016a-201">如果计算机在计划作业正在运行时处于活动状态（不空闲），则挂起运行的作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-201">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="d016a-202">默认情况下，计划作业将在计算机处于活动状态时挂起，而在计算机再次处于空闲状态时恢复运行。</span><span class="sxs-lookup"><span data-stu-id="d016a-202">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="d016a-203">若要更改该默认行为，请使用 *RestartOnIdleResume* 参数。</span><span class="sxs-lookup"><span data-stu-id="d016a-203">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="d016a-204">*StopIfGoingOffIdle* 参数将计划作业的 StopIfGoingOffIdle 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-204">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-205">-WakeToRun</span><span class="sxs-lookup"><span data-stu-id="d016a-205">-WakeToRun</span></span>
<span data-ttu-id="d016a-206">在计划开始时间，将计算机从休眠或睡眠状态唤醒，以便它可以运行该作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-206">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="d016a-207">默认情况下，如果计算机在计划开始时间处于休眠或睡眠状态，则不会运行该作业。</span><span class="sxs-lookup"><span data-stu-id="d016a-207">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="d016a-208">*WakeToRun* 参数将计划作业的 WakeToRun 属性值设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d016a-208">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="d016a-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d016a-209">CommonParameters</span></span>
<span data-ttu-id="d016a-210">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d016a-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d016a-211">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d016a-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d016a-212">输入</span><span class="sxs-lookup"><span data-stu-id="d016a-212">INPUTS</span></span>

### <span data-ttu-id="d016a-213">无</span><span class="sxs-lookup"><span data-stu-id="d016a-213">None</span></span>
<span data-ttu-id="d016a-214">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d016a-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d016a-215">输出</span><span class="sxs-lookup"><span data-stu-id="d016a-215">OUTPUTS</span></span>

### <span data-ttu-id="d016a-216">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="d016a-216">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="d016a-217">注释</span><span class="sxs-lookup"><span data-stu-id="d016a-217">NOTES</span></span>

* <span data-ttu-id="d016a-218">你可以使用 **get-scheduledjoboption** 创建的 **ScheduledJobOptions** 对象作为 Register-ScheduledJob cmdlet 的 *get-scheduledjoboption* 参数的值。</span><span class="sxs-lookup"><span data-stu-id="d016a-218">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** creates as the value of the *ScheduledJobOption* parameter of the Register-ScheduledJob cmdlet.</span></span> <span data-ttu-id="d016a-219">但是， *get-scheduledjoboption* 参数也可以采用哈希表值来指定 **ScheduledJobOptions** 对象的属性及其值，例如：</span><span class="sxs-lookup"><span data-stu-id="d016a-219">However, the *ScheduledJobOption* parameter can also take a hash table value that specifies the properties of the **ScheduledJobOptions** object and their values, such as:</span></span>

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

## <span data-ttu-id="d016a-220">相关链接</span><span class="sxs-lookup"><span data-stu-id="d016a-220">RELATED LINKS</span></span>

[<span data-ttu-id="d016a-221">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-221">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="d016a-222">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-222">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="d016a-223">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d016a-223">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="d016a-224">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-224">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="d016a-225">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d016a-225">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="d016a-226">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-226">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="d016a-227">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d016a-227">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="d016a-228">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d016a-228">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="d016a-229">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-229">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="d016a-230">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d016a-230">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="d016a-231">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d016a-231">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="d016a-232">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-232">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="d016a-233">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d016a-233">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="d016a-234">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d016a-234">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="d016a-235">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d016a-235">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="d016a-236">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d016a-236">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
