---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197786"
---
# <span data-ttu-id="0e394-103">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-103">New-JobTrigger</span></span>

## <span data-ttu-id="0e394-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0e394-104">SYNOPSIS</span></span>
<span data-ttu-id="0e394-105">为计划作业创建作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-105">Creates a job trigger for a scheduled job.</span></span>

## <span data-ttu-id="0e394-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e394-106">SYNTAX</span></span>

### <span data-ttu-id="0e394-107"> (默认值一次) </span><span class="sxs-lookup"><span data-stu-id="0e394-107">Once (Default)</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### <span data-ttu-id="0e394-108">每日</span><span class="sxs-lookup"><span data-stu-id="0e394-108">Daily</span></span>

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### <span data-ttu-id="0e394-109">每周</span><span class="sxs-lookup"><span data-stu-id="0e394-109">Weekly</span></span>

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### <span data-ttu-id="0e394-110">AtStartup</span><span class="sxs-lookup"><span data-stu-id="0e394-110">AtStartup</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### <span data-ttu-id="0e394-111">AtLogon</span><span class="sxs-lookup"><span data-stu-id="0e394-111">AtLogon</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## <span data-ttu-id="0e394-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e394-112">DESCRIPTION</span></span>
<span data-ttu-id="0e394-113">**Get-jobtrigger** cmdlet 创建一个作业触发器，该触发器在一次性或循环计划或事件发生时启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-113">The **New-JobTrigger** cmdlet creates a job trigger that starts a scheduled job on a one-time or recurring schedule, or when an event occurs.</span></span>

<span data-ttu-id="0e394-114">你可以使用 **New-JobTrigger** 返回的 **ScheduledJobTrigger** 对象，为新的或现有的计划作业设置作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-114">You can use the **ScheduledJobTrigger** object that **New-JobTrigger** returns to set a job trigger for a new or existing scheduled job.</span></span>
<span data-ttu-id="0e394-115">你还可以使用 Get-JobTrigger cmdlet 来创建作业触发器，以获取现有计划作业的作业触发器，或使用哈希表值来表示作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-115">You can also create a job trigger by using the Get-JobTrigger cmdlet to get the job trigger of an existing scheduled job, or by using a hash table value to represent a job trigger.</span></span>

<span data-ttu-id="0e394-116">创建作业触发器时，请查看 New-ScheduledJobOption cmdlet 指定的选项的默认值。</span><span class="sxs-lookup"><span data-stu-id="0e394-116">When creating a job trigger, review the default values of the options specified by the New-ScheduledJobOption cmdlet.</span></span>
<span data-ttu-id="0e394-117">这些选项具有与 **Task Scheduler** 中相应选项相同的有效值和默认值，这将影响计划作业的计划和时间。</span><span class="sxs-lookup"><span data-stu-id="0e394-117">These options, which have the same valid and default values as the corresponding options in **Task Scheduler** , affect the scheduling and timing of scheduled jobs.</span></span>

<span data-ttu-id="0e394-118">**Get-jobtrigger** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。</span><span class="sxs-lookup"><span data-stu-id="0e394-118">**New-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="0e394-119">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="0e394-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="0e394-120">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="0e394-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="0e394-121">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="0e394-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0e394-122">示例</span><span class="sxs-lookup"><span data-stu-id="0e394-122">EXAMPLES</span></span>

### <span data-ttu-id="0e394-123">示例1：一旦计划</span><span class="sxs-lookup"><span data-stu-id="0e394-123">Example 1: Once Schedule</span></span>

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

<span data-ttu-id="0e394-124">此命令使用 **New-JobTrigger** cmdlet 来创建只能启动计划作业一次的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-124">This command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a scheduled job only one time.</span></span>
<span data-ttu-id="0e394-125">*At* 参数值是一个可借助 Windows PowerShell 转换为 **DateTime** 对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e394-125">The value of the *At* parameter is a string that Windows PowerShell converts into a **DateTime** object.</span></span>
<span data-ttu-id="0e394-126">*At* 参数值包含一个显式日期，而不仅仅是某个时间。</span><span class="sxs-lookup"><span data-stu-id="0e394-126">The *At* parameter value includes an explicit date, not just a time.</span></span>
<span data-ttu-id="0e394-127">如果省略了日期，将使用当前日期和上午 3:00（这可能表示过去的某个时间）来创建该触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-127">If the date were omitted, the trigger would be created with the current date and 3:00 AM time, which is likely to represent a time in the past.</span></span>

### <span data-ttu-id="0e394-128">示例2：每日计划</span><span class="sxs-lookup"><span data-stu-id="0e394-128">Example 2: Daily Schedule</span></span>

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

<span data-ttu-id="0e394-129">此命令创建可在每隔 3 天的上午 4:15 启动计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-129">This command creates a job trigger that starts a scheduled job every 3 days at 4:15 a.m.</span></span>

<span data-ttu-id="0e394-130">由于 *At* 参数值不包含某个日期，因此当前日期将用作 **DateTime** 对象中的日期值。</span><span class="sxs-lookup"><span data-stu-id="0e394-130">Because the value of the *At* parameter does not include a date, the current date is used as the date value in the **DateTime** object.</span></span>
<span data-ttu-id="0e394-131">如果该日期和时间是过去的日期和时间，则计划作业将在下次开始时间之前启动，开始时间为从 *At* 参数值起第 3 天。</span><span class="sxs-lookup"><span data-stu-id="0e394-131">If the date and time is in the past, the scheduled job is started at the next occurrence, which is 3 days later from the *At* parameter value.</span></span>

### <span data-ttu-id="0e394-132">示例3：每周计划</span><span class="sxs-lookup"><span data-stu-id="0e394-132">Example 3: Weekly Schedule</span></span>

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

<span data-ttu-id="0e394-133">此命令创建一个作业触发器，该触发器将在每 4 个星期的星期一、星期三和星期五的 23:00（下午 11:00）启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-133">This command creates a job trigger that starts a scheduled job every 4 weeks on Monday, Wednesday, and Friday at 2300 hours (11:00 PM).</span></span>

<span data-ttu-id="0e394-134">还可以输入整数中的 *DaysOfWeek* 参数值，例如 `-DaysOfWeek 1, 5` 。</span><span class="sxs-lookup"><span data-stu-id="0e394-134">You can also enter the *DaysOfWeek* parameter value in integers, such as `-DaysOfWeek 1, 5`.</span></span>

### <span data-ttu-id="0e394-135">示例4：登录计划</span><span class="sxs-lookup"><span data-stu-id="0e394-135">Example 4: Logon Schedule</span></span>

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

<span data-ttu-id="0e394-136">此命令创建一个作业触发器，该触发器将在每次域管理员登录到计算机时启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-136">This command creates a job trigger that starts a scheduled job whenever the domain administrator logs onto the computer.</span></span>

### <span data-ttu-id="0e394-137">示例5：使用随机延迟</span><span class="sxs-lookup"><span data-stu-id="0e394-137">Example 5: Using a Random Delay</span></span>

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

<span data-ttu-id="0e394-138">此命令创建一个作业触发器，该触发器将在每天凌晨 1:00 启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-138">This command creates a job trigger that starts a scheduled job every day at 1:00 in the morning.</span></span>
<span data-ttu-id="0e394-139">此命令使用 *RandomDelay* 参数将最大延迟设置为 20 分钟。</span><span class="sxs-lookup"><span data-stu-id="0e394-139">The command uses the *RandomDelay* parameter to set the maximum delay to 20 minutes.</span></span>
<span data-ttu-id="0e394-140">因此，该作业将以伪随机地方式在每天凌晨 1:00 至凌晨 1:20（随间隔值变化而变化）之间运行。</span><span class="sxs-lookup"><span data-stu-id="0e394-140">As a result, the job runs every day between 1:00 AM and 1:20 AM, with the interval varying pseudo-randomly.</span></span>

<span data-ttu-id="0e394-141">你可以将随机延迟用于采样、负载平衡以及其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="0e394-141">You can use a random delay for sampling, load balancing, and other administrative tasks.</span></span>
<span data-ttu-id="0e394-142">设置延迟值时，请查看 New-ScheduledJobOption cmdlet 的有效和默认值，并将延迟与选项设置进行协调。</span><span class="sxs-lookup"><span data-stu-id="0e394-142">When setting the delay value, review the effective and default values of the New-ScheduledJobOption cmdlet and coordinate the delay with the option settings.</span></span>

### <span data-ttu-id="0e394-143">示例6：为新的计划作业创建作业触发器</span><span class="sxs-lookup"><span data-stu-id="0e394-143">Example 6: Create a Job Trigger for a New Scheduled Job</span></span>

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

<span data-ttu-id="0e394-144">以下命令使用作业触发器来创建新的计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-144">These commands use a job trigger to create a new scheduled job.</span></span>

### <span data-ttu-id="0e394-145">示例7：将作业触发器添加到计划作业</span><span class="sxs-lookup"><span data-stu-id="0e394-145">Example 7: Add a Job Trigger to a Scheduled Job</span></span>

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

<span data-ttu-id="0e394-146">此示例显示了如何将作业触发器添加到现有的计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-146">This example shows how to add a job trigger to an existing scheduled job.</span></span>
<span data-ttu-id="0e394-147">你可以将多个作业触发器添加到任何计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-147">You can add multiple job triggers to any scheduled job.</span></span>

<span data-ttu-id="0e394-148">该命令使用 Add-JobTrigger cmdlet 将作业触发器添加到 Synchronizeapps 将计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-148">The command uses the Add-JobTrigger cmdlet to add the job trigger to the SynchronizeApps scheduled job.</span></span>
<span data-ttu-id="0e394-149">*Trigger* 参数值是在每天上午 3:10 运行该作业的 **New-JobTrigger** 命令。</span><span class="sxs-lookup"><span data-stu-id="0e394-149">The value of the *Trigger* parameter is a **New-JobTrigger** command that runs the job every day at 3:10 AM.</span></span>

<span data-ttu-id="0e394-150">完成此命令后，SynchronizeApps 将是一个在该作业触发器指定的时间运行的计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-150">When the command completes, SynchronizeApps is a scheduled job that runs at the times specified by the job trigger.</span></span>

### <span data-ttu-id="0e394-151">示例8：创建重复作业触发器</span><span class="sxs-lookup"><span data-stu-id="0e394-151">Example 8: Create a repeating job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

<span data-ttu-id="0e394-152">此命令创建一个作业触发器，该触发器每隔60分钟运行一次作业，每隔分钟运行一次，48小时从2013上午1:00 的开始。</span><span class="sxs-lookup"><span data-stu-id="0e394-152">This command creates a job trigger that runs a job every 60 minutes for 48 hours beginning on September 12, 2013 at 1:00 AM.</span></span>

### <span data-ttu-id="0e394-153">示例9：停止重复作业触发器</span><span class="sxs-lookup"><span data-stu-id="0e394-153">Example 9: Stop a repeating job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

<span data-ttu-id="0e394-154">此命令强制停止 SecurityCheck 作业，该作业触发后将在其作业触发器到期之前每 60 分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="0e394-154">This command forcibly stops the SecurityCheck job, which is triggered to run every 60 minutes until its job trigger expires.</span></span>

<span data-ttu-id="0e394-155">若要防止作业重复，此命令使用 Get-JobTrigger 获取 SecurityCheck 作业的作业触发器，并使用 Set-JobTrigger cmdlet 将作业触发器的重复间隔和重复持续时间更改为零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="0e394-155">To prevent the job from repeating, the command uses the Get-JobTrigger to get the job trigger of the SecurityCheck job and the Set-JobTrigger cmdlet to change the repetition interval and repetition duration of the job trigger to zero (0).</span></span>

### <span data-ttu-id="0e394-156">示例10：创建每小时作业触发器</span><span class="sxs-lookup"><span data-stu-id="0e394-156">Example 10: Create an hourly job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

<span data-ttu-id="0e394-157">以下命令创建一个作业触发器，该触发器将无限期地每 12 个小时运行计划作业一次。</span><span class="sxs-lookup"><span data-stu-id="0e394-157">The following command creates a job trigger that runs a scheduled job once every 12 hours for an indefinite period of time.</span></span>
<span data-ttu-id="0e394-158">该计划从明日 (9/21/2012) 午夜（凌晨 0:00）开始运行。</span><span class="sxs-lookup"><span data-stu-id="0e394-158">The schedule begins tomorrow (9/21/2012) at midnight (0:00 AM).</span></span>

## <span data-ttu-id="0e394-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e394-159">PARAMETERS</span></span>

### <span data-ttu-id="0e394-160">-At</span><span class="sxs-lookup"><span data-stu-id="0e394-160">-At</span></span>
<span data-ttu-id="0e394-161">在指定的日期和时间启动作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-161">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="0e394-162">输入一个 **DateTime** 对象（例如 Get-Date cmdlet 返回的）或一个可以转换为日期和时间的字符串，例如 "April 19，2012 15:00"、"12/31" 或 "3am"。</span><span class="sxs-lookup"><span data-stu-id="0e394-162">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a date and time, such as "April 19, 2012 15:00", "12/31", or "3am".</span></span>
<span data-ttu-id="0e394-163">如果没有指定日期的元素（例如年份），则触发器中的日期将具有当前日期中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="0e394-163">If you don't specify an element of the date, such as the year, the date in the trigger has the corresponding element from the current date.</span></span>

<span data-ttu-id="0e394-164">使用 *Once* 参数时，应将 *At* 参数值设置为未来某个日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0e394-164">When using the *Once* parameter, set the value of the *At* parameter to a future date and time.</span></span>
<span data-ttu-id="0e394-165">由于 **DateTime** 对象中的默认日期为当前日期，因此在没有显式日期的情况下指定当前时间之前的某个时间时，将针对过去的某个时间创建作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-165">Because the default date in a **DateTime** object is the current date, if you specify a time before the current time without an explicit date, the job trigger is created for a time in the past.</span></span>

<span data-ttu-id="0e394-166">**DateTime** 对象以及可转换为 **DateTime** 对象的字符串将自动调整为与在“控制面板”的“区域和语言”中为本地计算机选择的日期和时间格式兼容。</span><span class="sxs-lookup"><span data-stu-id="0e394-166">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-167">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="0e394-167">-AtLogOn</span></span>
<span data-ttu-id="0e394-168">在指定的用户登录到计算机时，启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-168">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="0e394-169">若要指定某个用户，请使用 *User* 参数。</span><span class="sxs-lookup"><span data-stu-id="0e394-169">To specify a user, use the *User* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-170">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="0e394-170">-AtStartup</span></span>
<span data-ttu-id="0e394-171">在 Windows 启动时，启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-171">Starts the scheduled job when Windows starts.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-172">-Daily</span><span class="sxs-lookup"><span data-stu-id="0e394-172">-Daily</span></span>
<span data-ttu-id="0e394-173">指定一个循环的每日作业计划。</span><span class="sxs-lookup"><span data-stu-id="0e394-173">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="0e394-174">使用 *每日* 参数集中的其他参数来指定计划详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e394-174">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-175">-DaysInterval</span><span class="sxs-lookup"><span data-stu-id="0e394-175">-DaysInterval</span></span>
<span data-ttu-id="0e394-176">指定启动每日计划之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="0e394-176">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="0e394-177">例如，值为 3 时将在第 1 天、第 4 天、第 7 天（依此类推）启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-177">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="0e394-178">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="0e394-178">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-179">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="0e394-179">-DaysOfWeek</span></span>
<span data-ttu-id="0e394-180">指定在星期几运行每周计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-180">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="0e394-181">输入星期几名称，例如“Monday”或整数 0-6，其中 0 表示星期天。</span><span class="sxs-lookup"><span data-stu-id="0e394-181">Enter day names, such as "Monday" or integers 0-6, where 0 represents Sunday.</span></span>
<span data-ttu-id="0e394-182">在 Weekly 参数集中需要此参数。</span><span class="sxs-lookup"><span data-stu-id="0e394-182">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="0e394-183">在作业触发器中，应将星期几名称转换为其对应的整数值。</span><span class="sxs-lookup"><span data-stu-id="0e394-183">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="0e394-184">在某个命令中将星期几名称括在引号中时，应单独将每个星期几名称括在引号中，例如“Monday”、“Tuesday”。</span><span class="sxs-lookup"><span data-stu-id="0e394-184">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="0e394-185">如果将多个星期几名称括在一对引号中，则应合计相应的整数值。</span><span class="sxs-lookup"><span data-stu-id="0e394-185">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="0e394-186">例如，“Monday, Tuesday”(1, 2) 将生成一个“Wednesday”(3) 值。</span><span class="sxs-lookup"><span data-stu-id="0e394-186">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-187">-Once</span><span class="sxs-lookup"><span data-stu-id="0e394-187">-Once</span></span>
<span data-ttu-id="0e394-188">指定非循环（一次性）计划或自定义的重复计划。</span><span class="sxs-lookup"><span data-stu-id="0e394-188">Specifies a non-recurring (one time) or custom repeating schedule.</span></span>
<span data-ttu-id="0e394-189">若要创建重复计划，请使用 *Once* 参数以及 *RepetitionDuration* 和 *RepetitionInterval* 参数。</span><span class="sxs-lookup"><span data-stu-id="0e394-189">To create a repeating schedule, use the *Once* parameter with the *RepetitionDuration* and *RepetitionInterval* parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-190">-RandomDelay</span><span class="sxs-lookup"><span data-stu-id="0e394-190">-RandomDelay</span></span>
<span data-ttu-id="0e394-191">启用从计划开始时间开始的随机延迟，并设置最大延迟值。</span><span class="sxs-lookup"><span data-stu-id="0e394-191">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="0e394-192">针对每次启动以伪随机地方式设置延迟的长度，该长度可从无延迟变化到由此参数值指定的时间。</span><span class="sxs-lookup"><span data-stu-id="0e394-192">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="0e394-193">默认值为零 (00:00:00) 时将禁用随机延迟。</span><span class="sxs-lookup"><span data-stu-id="0e394-193">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="0e394-194">输入 timespan 对象（如 New-TimeSpan cmdlet 返回的对象），或输入 \<hours\> ：： format 形式的值 \<minutes\> ，该对象会 \<seconds\> 自动转换为 **timespan** 对象。</span><span class="sxs-lookup"><span data-stu-id="0e394-194">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a **TimeSpan** object.</span></span>

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

### <span data-ttu-id="0e394-195">-RepeatIndefinitely</span><span class="sxs-lookup"><span data-stu-id="0e394-195">-RepeatIndefinitely</span></span>
<span data-ttu-id="0e394-196">使用此参数（可在 Windows PowerShell 4.0 中启动），可在不指定 **RepetitionDuration** 参数的 *TimeSpan.MaxValue* 值的情况下无限期重复运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-196">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-197">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="0e394-197">-RepetitionDuration</span></span>
<span data-ttu-id="0e394-198">重复运行该作业，直到指定时间到期为止。</span><span class="sxs-lookup"><span data-stu-id="0e394-198">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="0e394-199">重复频率由 *RepetitionInterval* 参数值确定。</span><span class="sxs-lookup"><span data-stu-id="0e394-199">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="0e394-200">例如，如果 **RepetitionInterval** 的值为 5 分钟且 **RepetitionDuration** 的值为 2 小时，将在两小时内每 5 分钟触发一次该作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-200">For example, if the value of **RepetitionInterval** is 5 minutes and the value of **RepetitionDuration** is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="0e394-201">输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。</span><span class="sxs-lookup"><span data-stu-id="0e394-201">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="0e394-202">若要无限期地运行作业，请改为添加 *RepeatIndefinitely* 参数。</span><span class="sxs-lookup"><span data-stu-id="0e394-202">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="0e394-203">若要在作业触发器重复持续时间到期之前停止作业，请使用 Set-JobTrigger cmdlet 将 *RepetitionDuration* 值设置为 0 () 。</span><span class="sxs-lookup"><span data-stu-id="0e394-203">To stop a job before the job trigger repetition duration expires, use the Set-JobTrigger cmdlet to set the *RepetitionDuration* value to zero (0).</span></span>

<span data-ttu-id="0e394-204">仅当命令中使用了 *Once* 、 *At* 和 *RepetitionInterval* 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0e394-204">This parameter is valid only when the *Once* , *At* and *RepetitionInterval* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-205">-RepetitionInterval</span><span class="sxs-lookup"><span data-stu-id="0e394-205">-RepetitionInterval</span></span>
<span data-ttu-id="0e394-206">在指定的时间间隔重复运行作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-206">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="0e394-207">例如，如果此参数的值是 2 小时，则将每隔两小时触发该作业一次。</span><span class="sxs-lookup"><span data-stu-id="0e394-207">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="0e394-208">默认值为 0 时不重复该作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-208">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="0e394-209">输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。</span><span class="sxs-lookup"><span data-stu-id="0e394-209">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="0e394-210">仅当命令中使用了 *Once* 、 *At* 和 *RepetitionDuration* 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0e394-210">This parameter is valid only when the *Once* , *At* , and *RepetitionDuration* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-211">-User</span><span class="sxs-lookup"><span data-stu-id="0e394-211">-User</span></span>
<span data-ttu-id="0e394-212">指定可触发计划作业启动 *AtLogon* 的用户。</span><span class="sxs-lookup"><span data-stu-id="0e394-212">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="0e394-213">输入或格式的用户的名称 \<UserName\> ， \<Domain\Username\> 或输入一个星号 (\*) 以表示所有用户。</span><span class="sxs-lookup"><span data-stu-id="0e394-213">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="0e394-214">默认值为所有用户。</span><span class="sxs-lookup"><span data-stu-id="0e394-214">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-215">-Weekly</span><span class="sxs-lookup"><span data-stu-id="0e394-215">-Weekly</span></span>
<span data-ttu-id="0e394-216">指定一个循环的每周作业计划。</span><span class="sxs-lookup"><span data-stu-id="0e394-216">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="0e394-217">使用 Weekly 参数集中的其他参数来指定计划详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e394-217">Use the other parameters in the Weekly parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-218">-WeeksInterval</span><span class="sxs-lookup"><span data-stu-id="0e394-218">-WeeksInterval</span></span>
<span data-ttu-id="0e394-219">指定启动每周作业计划之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="0e394-219">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="0e394-220">例如，值为 3 时将在第 1 周、第 4 周、第 7 周（依此类推）启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="0e394-220">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="0e394-221">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="0e394-221">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e394-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e394-222">CommonParameters</span></span>
<span data-ttu-id="0e394-223">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0e394-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e394-224">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0e394-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e394-225">输入</span><span class="sxs-lookup"><span data-stu-id="0e394-225">INPUTS</span></span>

### <span data-ttu-id="0e394-226">无</span><span class="sxs-lookup"><span data-stu-id="0e394-226">None</span></span>
<span data-ttu-id="0e394-227">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e394-227">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0e394-228">输出</span><span class="sxs-lookup"><span data-stu-id="0e394-228">OUTPUTS</span></span>

### <span data-ttu-id="0e394-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="0e394-230">注释</span><span class="sxs-lookup"><span data-stu-id="0e394-230">NOTES</span></span>

* <span data-ttu-id="0e394-231">作业触发器不会保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="0e394-231">Job triggers are not saved to disk.</span></span> <span data-ttu-id="0e394-232">不过，计划作业保存在磁盘上，你可以使用 Get-JobTrigger 获取任何计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-232">However, scheduled jobs are saved to disk, and you can use the Get-JobTrigger to get the job trigger of any scheduled job.</span></span>
* <span data-ttu-id="0e394-233">**Get-jobtrigger** 不会阻止你创建不会运行计划作业的作业触发器，例如过去日期的一次性触发器。</span><span class="sxs-lookup"><span data-stu-id="0e394-233">**New-JobTrigger** does not prevent you from creating a job trigger that will not run a scheduled job, such as one-time trigger for a date in the past.</span></span>
* <span data-ttu-id="0e394-234">Register-ScheduledJob cmdlet 接受 ScheduledJobTrigger 对象，如 **get-jobtrigger** 或 Get-JobTrigger cmdlet 返回的对象，或者包含触发器值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="0e394-234">The Register-ScheduledJob cmdlet accepts a ScheduledJobTrigger object, such as one returned by the **New-JobTrigger** or Get-JobTrigger cmdlets, or a hash table with trigger values.</span></span>

  <span data-ttu-id="0e394-235">若要提交哈希表，请使用以下键。</span><span class="sxs-lookup"><span data-stu-id="0e394-235">To submit a hash table, use the following keys.</span></span>

  <span data-ttu-id="0e394-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (或任意有效的时间字符串) ; `DaysOfWeek="Monday", "Wednesday"` (或星期名称的任意组合) ; `Interval=2` (或任何有效频率间隔) ; `RandomDelay="30minutes"` (或任意有效的 timespan 字符串) ; `User="Domain1\User01` (或任意有效的用户;仅与 *AtLogon* frequency 值) } 一起使用</span><span class="sxs-lookup"><span data-stu-id="0e394-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01` (or any valid user; used only with the *AtLogon* frequency value) }</span></span>

## <span data-ttu-id="0e394-237">相关链接</span><span class="sxs-lookup"><span data-stu-id="0e394-237">RELATED LINKS</span></span>

[<span data-ttu-id="0e394-238">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-238">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="0e394-239">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-239">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="0e394-240">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0e394-240">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="0e394-241">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-241">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="0e394-242">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0e394-242">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="0e394-243">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-243">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="0e394-244">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0e394-244">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="0e394-245">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0e394-245">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="0e394-246">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-246">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="0e394-247">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0e394-247">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="0e394-248">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0e394-248">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="0e394-249">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-249">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="0e394-250">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0e394-250">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="0e394-251">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0e394-251">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="0e394-252">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0e394-252">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="0e394-253">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0e394-253">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
