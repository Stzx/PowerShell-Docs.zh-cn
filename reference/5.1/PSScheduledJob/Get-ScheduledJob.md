---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197789"
---
# <span data-ttu-id="bd3c8-103">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-103">Get-ScheduledJob</span></span>

## <span data-ttu-id="bd3c8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="bd3c8-104">SYNOPSIS</span></span>
<span data-ttu-id="bd3c8-105">获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-105">Gets scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="bd3c8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd3c8-106">SYNTAX</span></span>

### <span data-ttu-id="bd3c8-107">DefinitionId（默认值）</span><span class="sxs-lookup"><span data-stu-id="bd3c8-107">DefinitionId (Default)</span></span>

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="bd3c8-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="bd3c8-108">DefinitionName</span></span>

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="bd3c8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd3c8-109">DESCRIPTION</span></span>
<span data-ttu-id="bd3c8-110">**Get-ScheduledJob** cmdlet 可获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-110">The **Get-ScheduledJob** cmdlet gets scheduled jobs on the local computer.</span></span>
<span data-ttu-id="bd3c8-111">**Get-ScheduledJob** 仅获取当前用户使用 Register-ScheduledJob cmdlet 创建的计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-111">**Get-ScheduledJob** gets only scheduled jobs that are created by the current user using the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="bd3c8-112">尽管使用 **Register-ScheduledJob** cmdlet 所创建的作业会显示在任务计划程序中，但 **Get-ScheduledJob** 仅获取计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-112">Although jobs that are created by using the **Register-ScheduledJob** cmdlet appear in Task Scheduler, **Get-ScheduledJob** gets only scheduled jobs.</span></span>
<span data-ttu-id="bd3c8-113">它不会获取在任务计划程序中创建的计划任务。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-113">It does not get scheduled tasks created in Task Scheduler.</span></span>

<span data-ttu-id="bd3c8-114">在没有参数的情况下， **Get-ScheduledJob** 将获取计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-114">Without parameters, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="bd3c8-115">你可以使用 **Get-ScheduledJob** 的参数，按 ID 或名称获取计划作业并对其进行检查，或者通过管道将它们传递给其他 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-115">You can use the parameters of **Get-ScheduledJob** to get scheduled jobs by ID or name and examine them or pipe them to other cmdlets.</span></span>

<span data-ttu-id="bd3c8-116">**Get-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-116">**Get-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="bd3c8-117">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="bd3c8-118">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="bd3c8-119">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="bd3c8-120">示例</span><span class="sxs-lookup"><span data-stu-id="bd3c8-120">EXAMPLES</span></span>

### <span data-ttu-id="bd3c8-121">示例 1：获取所有计划作业</span><span class="sxs-lookup"><span data-stu-id="bd3c8-121">Example 1: Get all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob
```

<span data-ttu-id="bd3c8-122">此命令获取本地计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-122">This command gets all scheduled jobs on the local computer.</span></span>

### <span data-ttu-id="bd3c8-123">示例 2：按名称获取计划作业</span><span class="sxs-lookup"><span data-stu-id="bd3c8-123">Example 2: Get scheduled jobs by name</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

<span data-ttu-id="bd3c8-124">此命令获取计算机上的其名称包含“Backup”或“Archive”的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-124">This command gets all scheduled jobs on the computer that have names that include Backup or Archive.</span></span>
<span data-ttu-id="bd3c8-125">你可通过此命令格式搜索特定作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-125">This command format lets you search for particular jobs.</span></span>

### <span data-ttu-id="bd3c8-126">示例 3：获取远程计算机上的计划作业</span><span class="sxs-lookup"><span data-stu-id="bd3c8-126">Example 3: Get scheduled jobs on remote computers</span></span>

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

<span data-ttu-id="bd3c8-127">在 Servers.txt 文件中，此命令获取计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-127">This command gets all scheduled jobs on the computers that are listed in the Servers.txt file.</span></span>
<span data-ttu-id="bd3c8-128">该命令使用 Invoke-Command cmdlet 在每台计算机上运行 **Get-ScheduleJob** 命令。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-128">The command uses the Invoke-Command cmdlet to run a **Get-ScheduleJob** command on each computer.</span></span>

### <span data-ttu-id="bd3c8-129">示例 4：通过管道将计划作业传递给其他 cmdlet</span><span class="sxs-lookup"><span data-stu-id="bd3c8-129">Example 4: Pipe scheduled jobs to other cmdlets</span></span>

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

<span data-ttu-id="bd3c8-130">此命令获取 DailyBackup 和 WeeklyBackup 计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-130">This command gets the job triggers of the DailyBackup and WeeklyBackup scheduled jobs.</span></span>
<span data-ttu-id="bd3c8-131">它使用 **Get-ScheduledJob** cmdlet 获取计划作业，并使用 Get-JobTrigger cmdlet 获取计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-131">It uses the **Get-ScheduledJob** cmdlet to get the scheduled jobs and the Get-JobTrigger cmdlet to get the job triggers of the scheduled jobs.</span></span>

## <span data-ttu-id="bd3c8-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd3c8-132">PARAMETERS</span></span>

### <span data-ttu-id="bd3c8-133">-Id</span><span class="sxs-lookup"><span data-stu-id="bd3c8-133">-Id</span></span>
<span data-ttu-id="bd3c8-134">仅获取具有指定标识号 (ID) 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-134">Gets only the scheduled jobs with the specified identification number (ID).</span></span>
<span data-ttu-id="bd3c8-135">在计算机上输入一个或多个计划作业的 ID。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-135">Enter one or more IDs of scheduled jobs on the computer.</span></span>
<span data-ttu-id="bd3c8-136">默认情况下， **Get-ScheduledJob** 将获取计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-136">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3c8-137">-Name</span><span class="sxs-lookup"><span data-stu-id="bd3c8-137">-Name</span></span>
<span data-ttu-id="bd3c8-138">仅获取具有指定名称的计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-138">Gets only the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="bd3c8-139">在计算机上输入一个或多个计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-139">Enter one or more names of scheduled jobs on the computer.</span></span>
<span data-ttu-id="bd3c8-140">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-140">Wildcards are supported.</span></span>
<span data-ttu-id="bd3c8-141">默认情况下， **Get-ScheduledJob** 将获取计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-141">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3c8-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd3c8-142">CommonParameters</span></span>
<span data-ttu-id="bd3c8-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd3c8-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd3c8-145">输入</span><span class="sxs-lookup"><span data-stu-id="bd3c8-145">INPUTS</span></span>

### <span data-ttu-id="bd3c8-146">无</span><span class="sxs-lookup"><span data-stu-id="bd3c8-146">None</span></span>
<span data-ttu-id="bd3c8-147">不能通过管道将输入传递给 **Get-ScheduledJob** 。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-147">You cannot pipe input to **Get-ScheduledJob** .</span></span>

## <span data-ttu-id="bd3c8-148">输出</span><span class="sxs-lookup"><span data-stu-id="bd3c8-148">OUTPUTS</span></span>

### <span data-ttu-id="bd3c8-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="bd3c8-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="bd3c8-150">注释</span><span class="sxs-lookup"><span data-stu-id="bd3c8-150">NOTES</span></span>

* <span data-ttu-id="bd3c8-151">每个计划作业都保存在本地计算机上的 $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs 目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-151">Each scheduled job is saved in a subdirectory of the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the local computer.</span></span> <span data-ttu-id="bd3c8-152">该子目录是按计划作业命名的，并且包含计划作业的 XML 文件以及该计划作业的执行历史记录。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-152">The subdirectory is named for the scheduled job and contains the XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="bd3c8-153">有关磁盘上计划作业的详细信息，请参阅 about_Scheduled_Jobs_Advanced。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-153">For more information about scheduled jobs on disk, see about_Scheduled_Jobs_Advanced.</span></span>
* <span data-ttu-id="bd3c8-154">在 Windows PowerShell 中创建的计划作业会显示在 Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs 文件夹中的任务计划程序中。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-154">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs folder.</span></span> <span data-ttu-id="bd3c8-155">你可以使用任务计划程序查看和编辑计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-155">You can use Task Scheduler to view and edit the scheduled job.</span></span>
* <span data-ttu-id="bd3c8-156">你可以使用任务计划程序、SchTasks.exe 命令行工具和 Task Scheduler cmdlet 来管理使用 Scheduled Job cmdlet 创建的计划作业。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-156">You can use Task Scheduler, the SchTasks.exe command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="bd3c8-157">但是，你无法使用 Scheduled Job cmdlet 来管理在任务计划程序中创建的任务。</span><span class="sxs-lookup"><span data-stu-id="bd3c8-157">However, you cannot use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

## <span data-ttu-id="bd3c8-158">相关链接</span><span class="sxs-lookup"><span data-stu-id="bd3c8-158">RELATED LINKS</span></span>

[<span data-ttu-id="bd3c8-159">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-159">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="bd3c8-160">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-160">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="bd3c8-161">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-161">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="bd3c8-162">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-162">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="bd3c8-163">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-163">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="bd3c8-164">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-164">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="bd3c8-165">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-165">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="bd3c8-166">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="bd3c8-166">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="bd3c8-167">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-167">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="bd3c8-168">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="bd3c8-168">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="bd3c8-169">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-169">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="bd3c8-170">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-170">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="bd3c8-171">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="bd3c8-171">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="bd3c8-172">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-172">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="bd3c8-173">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="bd3c8-173">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="bd3c8-174">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="bd3c8-174">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
