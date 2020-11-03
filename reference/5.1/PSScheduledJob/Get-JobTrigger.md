---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197790"
---
# <span data-ttu-id="515b7-103">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-103">Get-JobTrigger</span></span>

## <span data-ttu-id="515b7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="515b7-104">SYNOPSIS</span></span>
<span data-ttu-id="515b7-105">获取计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-105">Gets the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="515b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="515b7-106">SYNTAX</span></span>

### <span data-ttu-id="515b7-107">JobDefinition（默认值）</span><span class="sxs-lookup"><span data-stu-id="515b7-107">JobDefinition (Default)</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="515b7-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="515b7-108">JobDefinitionId</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="515b7-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="515b7-109">JobDefinitionName</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="515b7-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="515b7-110">DESCRIPTION</span></span>
<span data-ttu-id="515b7-111">**Get-JobTrigger** cmdlet 可获取计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-111">The **Get-JobTrigger** cmdlet gets the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="515b7-112">你可以使用此命令检查作业触发器或通过管道将其传递给其他 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="515b7-112">You can use this command to examine the job triggers or to pipe the job triggers to other cmdlets.</span></span>

<span data-ttu-id="515b7-113">作业触发器定义用于启动计划作业的循环计划或条件。</span><span class="sxs-lookup"><span data-stu-id="515b7-113">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="515b7-114">不会单独将作业触发器保存到磁盘，因为它们是计划作业的一部分。</span><span class="sxs-lookup"><span data-stu-id="515b7-114">Job triggers are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="515b7-115">若要获取作业触发器，请指定该触发器启动的计划作业。</span><span class="sxs-lookup"><span data-stu-id="515b7-115">To get a job trigger, specify the scheduled job that the trigger starts.</span></span>

<span data-ttu-id="515b7-116">使用 **Get-JobTrigger** cmdlet 的参数来标识计划作业。</span><span class="sxs-lookup"><span data-stu-id="515b7-116">Use the parameters of the **Get-JobTrigger** cmdlet to identify the scheduled jobs.</span></span>
<span data-ttu-id="515b7-117">你可以通过其名称或标识号来标识计划作业，或者通过将 **get-scheduledjob** 对象（如 Get-ScheduledJob cmdlet 返回的对象）输入或管道传递给 **get-jobtrigger** 。</span><span class="sxs-lookup"><span data-stu-id="515b7-117">You can identify the scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-JobTrigger** .</span></span>

<span data-ttu-id="515b7-118">**Get-JobTrigger** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="515b7-118">**Get-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="515b7-119">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="515b7-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="515b7-120">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="515b7-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="515b7-121">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="515b7-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="515b7-122">示例</span><span class="sxs-lookup"><span data-stu-id="515b7-122">EXAMPLES</span></span>

### <span data-ttu-id="515b7-123">示例 1：按计划作业名称获取作业触发器</span><span class="sxs-lookup"><span data-stu-id="515b7-123">Example 1: Get a job trigger by scheduled job name</span></span>

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

<span data-ttu-id="515b7-124">该命令使用 **get-jobtrigger** 的 *Name* 参数获取 BackupJob 计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-124">The command uses the *Name* parameter of **Get-JobTrigger** to get the job triggers of the BackupJob scheduled job.</span></span>

### <span data-ttu-id="515b7-125">示例 2：按 ID 获取作业触发器</span><span class="sxs-lookup"><span data-stu-id="515b7-125">Example 2: Get a job trigger by ID</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

<span data-ttu-id="515b7-126">该示例使用 **get-jobtrigger** 的 *ID* 参数来获取计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-126">The example uses the *ID* parameter of **Get-JobTrigger** to get the job triggers of a scheduled job.</span></span>

### <span data-ttu-id="515b7-127">示例 3：通过管道传递作业以获取作业触发器</span><span class="sxs-lookup"><span data-stu-id="515b7-127">Example 3: Get job triggers by piping a job</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

<span data-ttu-id="515b7-128">此命令获取其名称中包含备份或存档的所有作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-128">This command gets the job triggers of all jobs that have Backup or Archive in their names.</span></span>

### <span data-ttu-id="515b7-129">示例 4：获取远程计算机上某个作业的作业触发器</span><span class="sxs-lookup"><span data-stu-id="515b7-129">Example 4: Get the job trigger of a job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

<span data-ttu-id="515b7-130">此命令获取远程计算机上某个计划作业的两个作业触发器之一。</span><span class="sxs-lookup"><span data-stu-id="515b7-130">This command gets one of the two job triggers of a scheduled job on a remote computer.</span></span>

<span data-ttu-id="515b7-131">该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="515b7-131">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>
<span data-ttu-id="515b7-132">它使用 Get-ScheduledJob cmdlet 获取 Backup 计划作业，该作业将通过管道传递给 **Get-JobTrigger** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="515b7-132">It uses the Get-ScheduledJob cmdlet to get the Backup scheduled job, which it pipes to the **Get-JobTrigger** cmdlet.</span></span>
<span data-ttu-id="515b7-133">它使用 *TriggerID* 参数仅获取第二个触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-133">It uses the *TriggerID* parameter to get only the second trigger.</span></span>

### <span data-ttu-id="515b7-134">示例 5：获取所有作业触发器</span><span class="sxs-lookup"><span data-stu-id="515b7-134">Example 5: Get all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

<span data-ttu-id="515b7-135">此命令获取本地计算机上的所有计划作业的所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-135">This command gets all job triggers of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="515b7-136">此命令使用 Get-ScheduledJob 获取本地计算机上的计划作业，并通过管道将这些作业传递给 **Get-JobTrigger** ，它将获取每个计划作业的作业触发器（如果有）。</span><span class="sxs-lookup"><span data-stu-id="515b7-136">The command uses the Get-ScheduledJob to get the scheduled jobs on the local computer and pipes them to **Get-JobTrigger** , which gets the job trigger of each scheduled job (if any).</span></span>

<span data-ttu-id="515b7-137">若要将计划作业的名称添加到作业触发器显示中，该命令将使用 Format-Table cmdlet 的计算属性功能。</span><span class="sxs-lookup"><span data-stu-id="515b7-137">To add the name of the scheduled job to the job trigger display, the command uses the calculated property feature of the Format-Table cmdlet.</span></span>
<span data-ttu-id="515b7-138">除了默认情况下显示的作业触发器属性，该命令还会创建一个新的 Get-scheduledjob 属性，用于显示计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="515b7-138">In addition to the job trigger properties that are displayed by default, the command creates a new ScheduledJob property that displays the name of the scheduled job.</span></span>

### <span data-ttu-id="515b7-139">示例 6：获取计划作业的作业触发器属性</span><span class="sxs-lookup"><span data-stu-id="515b7-139">Example 6: Get the job trigger property of a scheduled job</span></span>

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

<span data-ttu-id="515b7-140">计划作业的作业触发器存储在该作业的 JobTriggers 属性中。</span><span class="sxs-lookup"><span data-stu-id="515b7-140">The job triggers of a scheduled job are stored in the JobTriggers property of the job.</span></span>
<span data-ttu-id="515b7-141">此示例显示了使用 **get-jobtrigger** cmdlet 获取作业触发器的替代方法。</span><span class="sxs-lookup"><span data-stu-id="515b7-141">This example shows alternatives to using the **Get-JobTrigger** cmdlet to get job triggers.</span></span>
<span data-ttu-id="515b7-142">结果与使用 **Get-JobTrigger** cmdlet 相同，因此这两项技术可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="515b7-142">The results are identical to using the **Get-JobTrigger** cmdlet and the techniques can be used interchangeably.</span></span>

### <span data-ttu-id="515b7-143">示例 7：比较作业触发器</span><span class="sxs-lookup"><span data-stu-id="515b7-143">Example 7: Compare job triggers</span></span>

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

<span data-ttu-id="515b7-144">此示例显示了如何比较两个计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-144">This example shows how to compare the job triggers of two scheduled jobs.</span></span>

## <span data-ttu-id="515b7-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="515b7-145">PARAMETERS</span></span>

### <span data-ttu-id="515b7-146">-Id</span><span class="sxs-lookup"><span data-stu-id="515b7-146">-Id</span></span>
<span data-ttu-id="515b7-147">指定计划作业的标识号。</span><span class="sxs-lookup"><span data-stu-id="515b7-147">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="515b7-148">**Get-JobTrigger** 可获取指定的计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-148">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>

<span data-ttu-id="515b7-149">若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="515b7-149">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="515b7-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="515b7-150">-InputObject</span></span>
<span data-ttu-id="515b7-151">指定计划作业。</span><span class="sxs-lookup"><span data-stu-id="515b7-151">Specifies a scheduled job.</span></span>
<span data-ttu-id="515b7-152">输入包含  **get-scheduledjob** 对象的变量，或者键入获取 **get-scheduledjob** 对象的命令或表达式，如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="515b7-152">Enter a variable that contains  **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="515b7-153">还可以通过管道将 **ScheduledJob** 对象传递给 **Get-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="515b7-153">You can also pipe **ScheduledJob** objects to **Get-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="515b7-154">-Name</span><span class="sxs-lookup"><span data-stu-id="515b7-154">-Name</span></span>
<span data-ttu-id="515b7-155">指定计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="515b7-155">Specifies the name of a scheduled job.</span></span>
<span data-ttu-id="515b7-156">**Get-JobTrigger** 可获取指定的计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-156">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>
<span data-ttu-id="515b7-157">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="515b7-157">Wildcards are supported.</span></span>

<span data-ttu-id="515b7-158">若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="515b7-158">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="515b7-159">-TriggerId</span><span class="sxs-lookup"><span data-stu-id="515b7-159">-TriggerId</span></span>
<span data-ttu-id="515b7-160">获取指定的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="515b7-160">Gets the specified job triggers.</span></span>
<span data-ttu-id="515b7-161">输入计划作业中一个或多个作业触发器的触发器 ID。</span><span class="sxs-lookup"><span data-stu-id="515b7-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="515b7-162">在 *Name* 、 *ID* 或 *InputObject* 参数指定的计划作业有多个作业触发器时使用此参数。</span><span class="sxs-lookup"><span data-stu-id="515b7-162">Use this parameter when the scheduled job that is specified by the *Name* , *ID* , or *InputObject* parameters has multiple job triggers.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="515b7-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="515b7-163">CommonParameters</span></span>
<span data-ttu-id="515b7-164">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="515b7-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="515b7-165">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="515b7-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="515b7-166">输入</span><span class="sxs-lookup"><span data-stu-id="515b7-166">INPUTS</span></span>

### <span data-ttu-id="515b7-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="515b7-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="515b7-168">可以通过管道将计划作业从 Get-ScheduledJob 传递到 **Get-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="515b7-168">You can pipe a scheduled job from Get-ScheduledJob to **Get-JobTrigger** .</span></span>

## <span data-ttu-id="515b7-169">输出</span><span class="sxs-lookup"><span data-stu-id="515b7-169">OUTPUTS</span></span>

### <span data-ttu-id="515b7-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="515b7-171">注释</span><span class="sxs-lookup"><span data-stu-id="515b7-171">NOTES</span></span>

## <span data-ttu-id="515b7-172">相关链接</span><span class="sxs-lookup"><span data-stu-id="515b7-172">RELATED LINKS</span></span>

[<span data-ttu-id="515b7-173">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-173">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="515b7-174">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-174">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="515b7-175">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="515b7-175">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="515b7-176">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-176">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="515b7-177">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="515b7-177">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="515b7-178">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-178">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="515b7-179">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="515b7-179">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="515b7-180">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="515b7-180">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="515b7-181">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-181">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="515b7-182">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="515b7-182">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="515b7-183">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="515b7-183">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="515b7-184">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-184">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="515b7-185">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="515b7-185">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="515b7-186">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="515b7-186">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="515b7-187">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="515b7-187">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="515b7-188">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="515b7-188">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
