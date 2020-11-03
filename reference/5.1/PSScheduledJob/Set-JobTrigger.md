---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197780"
---
# <span data-ttu-id="03869-103">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-103">Set-JobTrigger</span></span>

## <span data-ttu-id="03869-104">摘要</span><span class="sxs-lookup"><span data-stu-id="03869-104">SYNOPSIS</span></span>
<span data-ttu-id="03869-105">更改计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-105">Changes the job trigger of a scheduled job.</span></span>

## <span data-ttu-id="03869-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03869-106">SYNTAX</span></span>

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="03869-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03869-107">DESCRIPTION</span></span>
<span data-ttu-id="03869-108">**Set-JobTrigger** cmdlet 可更改计划作业的作业触发器的属性。</span><span class="sxs-lookup"><span data-stu-id="03869-108">The **Set-JobTrigger** cmdlet changes the properties of the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="03869-109">它可用于更改作业启动的时间或频率，还可用于将计划从基于时间的计划更改为登录或启动时触发的计划。</span><span class="sxs-lookup"><span data-stu-id="03869-109">You can use it to change the time or frequency at which the jobs start or to change from a time-based schedules to schedules that are triggered by a logon or startup.</span></span>

<span data-ttu-id="03869-110">作业触发器定义用于启动计划作业的循环计划或条件。</span><span class="sxs-lookup"><span data-stu-id="03869-110">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="03869-111">虽然作业触发器不保存到磁盘，但你可以更改计划作业的作业触发器，这些触发器可保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="03869-111">Although job triggers are not saved to disk, you can change the job triggers of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="03869-112">若要更改计划作业的作业触发器，应首先使用 Get-JobTrigger cmdlet 来获取计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-112">To change a job trigger of a scheduled job, begin by using the Get-JobTrigger cmdlet to get the job trigger of a scheduled job.</span></span>
<span data-ttu-id="03869-113">然后，通过管道将触发器传递给 **Set-JobTrigger** 或将其保存在某个变量中，并且使用 *Set-JobTrigger* cmdlet 的 **InputObject** 参数来标识触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-113">Then, pipe the trigger to **Set-JobTrigger** or save the trigger in a variable and use the *InputObject* parameter of **Set-JobTrigger** cmdlet to identify the trigger.</span></span>
<span data-ttu-id="03869-114">使用 **Set-JobTrigger** 的剩余参数来更改作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-114">Use the remaining parameters of **Set-JobTrigger** to change the job trigger.</span></span>

<span data-ttu-id="03869-115">更改作业触发器的类型（例如将作业触发器从每日或每周触发器更改为 *AtLogon* 触发器）时，将删除原始触发器属性。</span><span class="sxs-lookup"><span data-stu-id="03869-115">When you change the type of a job trigger, such as changing a job trigger from a daily or weekly trigger to an *AtLogon* trigger, the original trigger properties are deleted.</span></span>
<span data-ttu-id="03869-116">但是，如果更改触发器的值而非其类型（例如在每周触发器中更改日期），则仅更改指定的属性。</span><span class="sxs-lookup"><span data-stu-id="03869-116">However, if you change the values of the trigger, but not its type, such as changing the days in a weekly trigger, only the properties that you specify are changed.</span></span>
<span data-ttu-id="03869-117">保留原始作业触发器的所有其他属性。</span><span class="sxs-lookup"><span data-stu-id="03869-117">All other properties of the original job trigger are retained.</span></span>

<span data-ttu-id="03869-118">**et-JobTrigger** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="03869-118">**Set-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="03869-119">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="03869-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="03869-120">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="03869-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*`  or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="03869-121">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="03869-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="03869-122">示例</span><span class="sxs-lookup"><span data-stu-id="03869-122">EXAMPLES</span></span>

### <span data-ttu-id="03869-123">示例 1：更改作业触发器中的星期几名称</span><span class="sxs-lookup"><span data-stu-id="03869-123">Example 1: Change the days in a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

<span data-ttu-id="03869-124">此示例显示了如何更改每周作业触发器中的星期几名称。</span><span class="sxs-lookup"><span data-stu-id="03869-124">This example shows how to change the days in a weekly job trigger.</span></span>

<span data-ttu-id="03869-125">第一个命令使用 Get-JobTrigger cmdlet 来获取 DeployPackage 计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-125">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="03869-126">该输出显示触发器在星期三和星期六的午夜启动作业。</span><span class="sxs-lookup"><span data-stu-id="03869-126">The output shows that the trigger starts the job at midnight on Wednesdays and Saturdays.</span></span>

<span data-ttu-id="03869-127">此命令不是必需的；包含它只是为了显示触发器更改的效果。</span><span class="sxs-lookup"><span data-stu-id="03869-127">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="03869-128">示例 2：更改作业触发器类型</span><span class="sxs-lookup"><span data-stu-id="03869-128">Example 2: Change the job trigger type</span></span>

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

<span data-ttu-id="03869-129">此示例显示了如何更改用于启动作业的作业触发器的类型。</span><span class="sxs-lookup"><span data-stu-id="03869-129">This example shows how to change the type of job trigger that starts a job.</span></span>
<span data-ttu-id="03869-130">此示例中的命令将 AtStartup 作业触发器替换为每周触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-130">The commands in this example replace an AtStartup job trigger with a weekly trigger.</span></span>

<span data-ttu-id="03869-131">第一个命令使用 Get-JobTrigger cmdlet 获取清单计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-131">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the Inventory scheduled job.</span></span>
<span data-ttu-id="03869-132">此输出显示，作业有两个触发器，即每日触发器和 *AtStartup* 触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-132">The output shows that the job has two triggers a daily trigger and an *AtStartup* trigger.</span></span>

<span data-ttu-id="03869-133">此命令不是必需的；包含它只是为了显示触发器更改的效果。</span><span class="sxs-lookup"><span data-stu-id="03869-133">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="03869-134">示例 3：更改远程作业触发器上的用户</span><span class="sxs-lookup"><span data-stu-id="03869-134">Example 3: Change the user on a remote job trigger</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

<span data-ttu-id="03869-135">此命令更改 Server01 计算机上计划作业的所有 *AtLogon* 作业触发器中的用户。</span><span class="sxs-lookup"><span data-stu-id="03869-135">This command changes the user in all *AtLogon* job triggers of scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="03869-136">该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="03869-136">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="03869-137">远程命令以获取计算机上所有计划作业的 Get-ScheduledJob 命令开头。</span><span class="sxs-lookup"><span data-stu-id="03869-137">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="03869-138">计划作业通过管道传递给 Get-JobTrigger cmdlet，此 cmdlet 将获取这些计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-138">The scheduled jobs are piped to the Get-JobTrigger cmdlet, which gets the job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="03869-139">每个作业触发器都包含 JobDefinition 属性，该属性包括计划作业，因此触发器与计划作业保持关联，即使该作业出现更改也是如此。</span><span class="sxs-lookup"><span data-stu-id="03869-139">Each job trigger contains a JobDefinition property that contains the scheduled job, so the trigger remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="03869-140">作业触发器通过管道传输到 Where-Object cmdlet，该 cmdlet 将获取具有 User 属性的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-140">The job triggers are piped to the Where-Object cmdlet, which gets job triggers that have the User property.</span></span>
<span data-ttu-id="03869-141">通过管道将选定的作业触发器传递给 **Set-JobTrigger** cmdlet，此 cmdlet 可将用户更改为 Domain01\Admin02。</span><span class="sxs-lookup"><span data-stu-id="03869-141">The selected job triggers are piped to the **Set-JobTrigger** cmdlet, which changes the user to Domain01\Admin02.</span></span>

### <span data-ttu-id="03869-142">示例 4：更改许多作业触发器中的一个</span><span class="sxs-lookup"><span data-stu-id="03869-142">Example 4: Change one of many job triggers</span></span>

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="03869-143">此示例中的命令将 SecurityCheck 计划作业的 *Once* 作业触发器的重复间隔时间从每 60 分钟更改为每 90 分钟。</span><span class="sxs-lookup"><span data-stu-id="03869-143">The commands in this example changes the repetition interval of the *Once* job trigger of SecurityCheck scheduled job from every 60 minutes to every 90 minutes.</span></span>
<span data-ttu-id="03869-144">SecurityCheck 计划作业具有三个作业触发器，因此该命令使用 Get-JobTrigger cmdlet 的 *TriggerId* 参数标识所更改的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-144">The SecurityCheck scheduled job has three job triggers, so the commands use the *TriggerId* parameter of the Get-JobTrigger cmdlet to identify the job trigger that is being changed.</span></span>

<span data-ttu-id="03869-145">第一个命令使用 **Get-JobTrigger** cmdlet 来获取 SecurityCheck 计划作业的所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-145">The first command uses the **Get-JobTrigger** cmdlet to get all job triggers of the SecurityCheck scheduled job.</span></span>
<span data-ttu-id="03869-146">用于显示作业触发器的 ID 的输出可显示 ID 为 3 的 *Once* 作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-146">The output, which displays the IDs of the job triggers, reveals that the *Once* job trigger has an ID of 3.</span></span>

## <span data-ttu-id="03869-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03869-147">PARAMETERS</span></span>

### <span data-ttu-id="03869-148">-At</span><span class="sxs-lookup"><span data-stu-id="03869-148">-At</span></span>
<span data-ttu-id="03869-149">在指定的日期和时间启动作业。</span><span class="sxs-lookup"><span data-stu-id="03869-149">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="03869-150">输入一个 **DateTime** 对象（例如 Get-Date cmdlet 返回的对象），或输入一个可转换为时间的字符串（例如“April 19, 2012 15:00”、“12/31/2013 9:00 PM”或“3am”）。</span><span class="sxs-lookup"><span data-stu-id="03869-150">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a time, such as "April 19, 2012 15:00", "12/31/2013 9:00 PM", or "3am".</span></span>

<span data-ttu-id="03869-151">如果未指定 **DateTime** 对象的元素（例如秒），则不会更改作业触发器的元素。</span><span class="sxs-lookup"><span data-stu-id="03869-151">If you don't specify an element of the **DateTime** object, such as seconds, that element of the job trigger is not changed.</span></span>
<span data-ttu-id="03869-152">如果原始作业触发器没有包含 **DateTime** 对象，而您省略了某个元素，则将使用当前日期和时间中的相应元素来创建作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-152">If the original job trigger didn't include a **DateTime** object and you omit an element, the job trigger is created with the corresponding element from the current date and time.</span></span>

<span data-ttu-id="03869-153">使用 *Once* 参数时，将 *At* 参数值设置为特定的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="03869-153">When using the *Once* parameter, set the value of the *At* parameter to a particular date and time.</span></span>
<span data-ttu-id="03869-154">由于 **DateTime** 对象中的默认日期为当前日期，因此在没有显式日期的情况下设置当前时间之前的某个时间时，将针对过去的某个时间生成作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-154">Because the default date in a **DateTime** object is the current date, setting a time before the current time without an explicit date results in a job trigger for a time in the past.</span></span>

<span data-ttu-id="03869-155">**DateTime** 对象以及可转换为 **DateTime** 对象的字符串将自动调整为与在“控制面板”的“区域和语言”中为本地计算机选择的日期和时间格式兼容。</span><span class="sxs-lookup"><span data-stu-id="03869-155">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03869-156">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="03869-156">-AtLogOn</span></span>
<span data-ttu-id="03869-157">在指定的用户登录到计算机时，启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-157">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="03869-158">若要指定某个用户，请使用 *User* 参数。</span><span class="sxs-lookup"><span data-stu-id="03869-158">To specify a user, use the *User* parameter.</span></span>

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

### <span data-ttu-id="03869-159">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="03869-159">-AtStartup</span></span>
<span data-ttu-id="03869-160">在 Windows 启动时，启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-160">Starts the scheduled job when Windows starts.</span></span>

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

### <span data-ttu-id="03869-161">-Daily</span><span class="sxs-lookup"><span data-stu-id="03869-161">-Daily</span></span>
<span data-ttu-id="03869-162">指定一个循环的每日作业计划。</span><span class="sxs-lookup"><span data-stu-id="03869-162">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="03869-163">使用 *每日* 参数集中的其他参数来指定计划详细信息。</span><span class="sxs-lookup"><span data-stu-id="03869-163">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="03869-164">-DaysInterval</span><span class="sxs-lookup"><span data-stu-id="03869-164">-DaysInterval</span></span>
<span data-ttu-id="03869-165">指定启动每日计划之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="03869-165">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="03869-166">例如，值为 3 时将在第 1 天、第 4 天、第 7 天（依此类推）启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-166">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="03869-167">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="03869-167">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03869-168">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="03869-168">-DaysOfWeek</span></span>
<span data-ttu-id="03869-169">指定在星期几运行每周计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-169">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="03869-170">输入 "日期名称"，如 "星期一"、"星期四"、"整数 0-6"，其中0表示 "星期日" 或 "星号" (\*) 以表示每天。</span><span class="sxs-lookup"><span data-stu-id="03869-170">Enter day names, such as Monday, Thursday, integers 0-6, where 0 represents Sunday, or an asterisk (\*) to represent every day.</span></span>
<span data-ttu-id="03869-171">在 Weekly 参数集中需要此参数。</span><span class="sxs-lookup"><span data-stu-id="03869-171">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="03869-172">在作业触发器中，应将星期几名称转换为其对应的整数值。</span><span class="sxs-lookup"><span data-stu-id="03869-172">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="03869-173">在某个命令中将星期几名称括在引号中时，应单独将每个星期几名称括在引号中，例如“Monday”、“Tuesday”。</span><span class="sxs-lookup"><span data-stu-id="03869-173">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="03869-174">如果将多个星期几名称括在一对引号中，则应合计相应的整数值。</span><span class="sxs-lookup"><span data-stu-id="03869-174">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="03869-175">例如，“Monday, Tuesday”(1, 2) 将生成一个“Wednesday”(3) 值。</span><span class="sxs-lookup"><span data-stu-id="03869-175">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03869-176">-InputObject</span><span class="sxs-lookup"><span data-stu-id="03869-176">-InputObject</span></span>
<span data-ttu-id="03869-177">指定作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-177">Specifies the job triggers.</span></span>
<span data-ttu-id="03869-178">输入包含 **ScheduledJobTrigger** 对象的变量，或者键入获取 **ScheduledJobTrigger** 对象的命令或表达式，如 Get-JobTrigger 命令。</span><span class="sxs-lookup"><span data-stu-id="03869-178">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="03869-179">还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Set-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="03869-179">You can also pipe a **ScheduledJobTrigger** object to **Set-JobTrigger** .</span></span>

<span data-ttu-id="03869-180">如果指定多个作业触发器，则 **Set-JobTrigger** 将对所有作业触发器做出相同的更改。</span><span class="sxs-lookup"><span data-stu-id="03869-180">If you specify multiple job triggers, **Set-JobTrigger** makes the same changes to all job triggers.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="03869-181">-Once</span><span class="sxs-lookup"><span data-stu-id="03869-181">-Once</span></span>
<span data-ttu-id="03869-182">指定非循环（一次性）计划。</span><span class="sxs-lookup"><span data-stu-id="03869-182">Specifies a non-recurring (one time) schedule.</span></span>

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

### <span data-ttu-id="03869-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="03869-183">-PassThru</span></span>
<span data-ttu-id="03869-184">返回更改的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-184">Returns the job triggers that changed.</span></span>
<span data-ttu-id="03869-185">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="03869-185">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="03869-186">-RandomDelay</span><span class="sxs-lookup"><span data-stu-id="03869-186">-RandomDelay</span></span>
<span data-ttu-id="03869-187">启用从计划开始时间开始的随机延迟，并设置最大延迟值。</span><span class="sxs-lookup"><span data-stu-id="03869-187">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="03869-188">针对每次启动以伪随机地方式设置延迟的长度，该长度可从无延迟变化到由此参数值指定的时间。</span><span class="sxs-lookup"><span data-stu-id="03869-188">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="03869-189">默认值为零 (00:00:00) 时将禁用随机延迟。</span><span class="sxs-lookup"><span data-stu-id="03869-189">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="03869-190">输入 timespan 对象（如 New-TimeSpan cmdlet 返回的对象），或输入 \<hours\> ：： format 形式的值 \<minutes\> ，该对象会 \<seconds\> 自动转换为 timespan 对象。</span><span class="sxs-lookup"><span data-stu-id="03869-190">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a timespan object.</span></span>

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

### <span data-ttu-id="03869-191">-RepeatIndefinitely</span><span class="sxs-lookup"><span data-stu-id="03869-191">-RepeatIndefinitely</span></span>
<span data-ttu-id="03869-192">使用此参数（可在 Windows PowerShell 4.0 中启动），可在不指定 **RepetitionDuration** 参数的 *TimeSpan.MaxValue* 值的情况下无限期重复运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-192">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

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

### <span data-ttu-id="03869-193">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="03869-193">-RepetitionDuration</span></span>
<span data-ttu-id="03869-194">重复运行该作业，直到指定时间到期为止。</span><span class="sxs-lookup"><span data-stu-id="03869-194">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="03869-195">重复频率由 *RepetitionInterval* 参数值确定。</span><span class="sxs-lookup"><span data-stu-id="03869-195">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="03869-196">例如，如果 **RepetitionInterval** 的值为 5 分钟且 *RepetitionDuration* 的值为 2 小时，将在两小时内每 5 分钟触发一次该作业。</span><span class="sxs-lookup"><span data-stu-id="03869-196">For example, if the value of **RepetitionInterval** is 5 minutes and the value of *RepetitionDuration* is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="03869-197">输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。</span><span class="sxs-lookup"><span data-stu-id="03869-197">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="03869-198">若要无限期地运行作业，请改为添加 *RepeatIndefinitely* 参数。</span><span class="sxs-lookup"><span data-stu-id="03869-198">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="03869-199">若要在作业触发器重复持续时间到期之前停止作业，请将 **RepetitionDuration** 值设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="03869-199">To stop a job before the job trigger repetition duration expires, set the **RepetitionDuration** value to zero (0).</span></span>

<span data-ttu-id="03869-200">若要更改 *Once* 作业触发器的重复持续时间或重复间隔时间，该命令必须包含 **RepetitionInterval** 和 **RepetitionDuration** 参数。</span><span class="sxs-lookup"><span data-stu-id="03869-200">To change the repetition duration or repetition interval of a *Once* job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="03869-201">若要更改其他类型的作业触发器的重复持续时间或重复间隔时间，该命令必须包含 *Once* 、 *At* 、 *RepetitionInterval* 和 *RepetitionDuration* 参数。</span><span class="sxs-lookup"><span data-stu-id="03869-201">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the *Once* , *At* , *RepetitionInterval* and *RepetitionDuration* parameters.</span></span>

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

### <span data-ttu-id="03869-202">-RepetitionInterval</span><span class="sxs-lookup"><span data-stu-id="03869-202">-RepetitionInterval</span></span>
<span data-ttu-id="03869-203">在指定的时间间隔重复运行作业。</span><span class="sxs-lookup"><span data-stu-id="03869-203">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="03869-204">例如，如果此参数的值是 2 小时，则将每隔两小时触发该作业一次。</span><span class="sxs-lookup"><span data-stu-id="03869-204">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="03869-205">默认值为 0 时不重复该作业。</span><span class="sxs-lookup"><span data-stu-id="03869-205">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="03869-206">输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。</span><span class="sxs-lookup"><span data-stu-id="03869-206">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="03869-207">若要更改 **Once** 作业触发器的重复持续时间或重复间隔时间，该命令必须包含 **RepetitionInterval** 和 **RepetitionDuration** 参数。</span><span class="sxs-lookup"><span data-stu-id="03869-207">To change the repetition duration or repetition interval of a **Once** job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="03869-208">若要更改其他类型的作业触发器的重复持续时间或重复间隔时间，该命令必须包含 **Once** 、 **At** 、 **RepetitionInterval** 和 **RepetitionDuration** 参数。</span><span class="sxs-lookup"><span data-stu-id="03869-208">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the **Once** , **At** , **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>

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

### <span data-ttu-id="03869-209">-User</span><span class="sxs-lookup"><span data-stu-id="03869-209">-User</span></span>
<span data-ttu-id="03869-210">指定可触发计划作业启动 *AtLogon* 的用户。</span><span class="sxs-lookup"><span data-stu-id="03869-210">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="03869-211">输入或格式的用户的名称 \<UserName\> ， \<Domain\Username\> 或输入一个星号 (\*) 以表示所有用户。</span><span class="sxs-lookup"><span data-stu-id="03869-211">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="03869-212">默认值为所有用户。</span><span class="sxs-lookup"><span data-stu-id="03869-212">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03869-213">-Weekly</span><span class="sxs-lookup"><span data-stu-id="03869-213">-Weekly</span></span>
<span data-ttu-id="03869-214">指定一个循环的每周作业计划。</span><span class="sxs-lookup"><span data-stu-id="03869-214">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="03869-215">使用 " *每周* " 参数集中的其他参数来指定计划详细信息。</span><span class="sxs-lookup"><span data-stu-id="03869-215">Use the other parameters in the *Weekly* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="03869-216">-WeeksInterval</span><span class="sxs-lookup"><span data-stu-id="03869-216">-WeeksInterval</span></span>
<span data-ttu-id="03869-217">指定启动每周作业计划之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="03869-217">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="03869-218">例如，值为 3 时将在第 1 周、第 4 周、第 7 周（依此类推）启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-218">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="03869-219">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="03869-219">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03869-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03869-220">CommonParameters</span></span>
<span data-ttu-id="03869-221">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="03869-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03869-222">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="03869-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03869-223">输入</span><span class="sxs-lookup"><span data-stu-id="03869-223">INPUTS</span></span>

### <span data-ttu-id="03869-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="03869-225">可以通过管道将多个作业触发器传递给 **get-jobtrigger** 。</span><span class="sxs-lookup"><span data-stu-id="03869-225">You can pipe multiple job triggers to **Set-JobTrigger** .</span></span>

## <span data-ttu-id="03869-226">输出</span><span class="sxs-lookup"><span data-stu-id="03869-226">OUTPUTS</span></span>

### <span data-ttu-id="03869-227">无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-227">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="03869-228">当使用 *Passthru* 参数时， **Set-JobTrigger** 将返回已更改的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="03869-228">When you use the *Passthru* parameter, **Set-JobTrigger** returns the job triggers that were changed.</span></span>
<span data-ttu-id="03869-229">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="03869-229">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="03869-230">注释</span><span class="sxs-lookup"><span data-stu-id="03869-230">NOTES</span></span>

* <span data-ttu-id="03869-231">作业触发器具有一个将其与计划作业相关联的 JobDefintion 属性。</span><span class="sxs-lookup"><span data-stu-id="03869-231">Job triggers have a JobDefintion property that associates them with the scheduled job.</span></span> <span data-ttu-id="03869-232">当更改计划作业的作业触发器时，该作业将发生更改。</span><span class="sxs-lookup"><span data-stu-id="03869-232">When you change the job trigger of a scheduled job, the job is changed.</span></span> <span data-ttu-id="03869-233">无需使用 Set-ScheduledJob 命令即可将更改的触发器应用于计划作业。</span><span class="sxs-lookup"><span data-stu-id="03869-233">You do not need to use a Set-ScheduledJob command to apply the changed trigger to the scheduled job.</span></span>

## <span data-ttu-id="03869-234">相关链接</span><span class="sxs-lookup"><span data-stu-id="03869-234">RELATED LINKS</span></span>

[<span data-ttu-id="03869-235">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-235">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="03869-236">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-236">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="03869-237">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03869-237">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="03869-238">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-238">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="03869-239">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03869-239">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="03869-240">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-240">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="03869-241">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03869-241">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="03869-242">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="03869-242">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="03869-243">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-243">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="03869-244">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="03869-244">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="03869-245">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03869-245">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="03869-246">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-246">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="03869-247">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03869-247">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="03869-248">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03869-248">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="03869-249">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="03869-249">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="03869-250">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03869-250">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
