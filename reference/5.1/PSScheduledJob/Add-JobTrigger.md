---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197804"
---
# <span data-ttu-id="6997b-103">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-103">Add-JobTrigger</span></span>

## <span data-ttu-id="6997b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6997b-104">SYNOPSIS</span></span>
<span data-ttu-id="6997b-105">将作业触发器添加到计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-105">Adds job triggers to scheduled jobs.</span></span>

## <span data-ttu-id="6997b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6997b-106">SYNTAX</span></span>

### <span data-ttu-id="6997b-107">JobDefinition（默认值）</span><span class="sxs-lookup"><span data-stu-id="6997b-107">JobDefinition (Default)</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### <span data-ttu-id="6997b-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="6997b-108">JobDefinitionId</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="6997b-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="6997b-109">JobDefinitionName</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="6997b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6997b-110">DESCRIPTION</span></span>
<span data-ttu-id="6997b-111">**Add-JobTrigger** cmdlet 可将作业触发器添加到计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-111">The **Add-JobTrigger** cmdlet adds job triggers to scheduled jobs.</span></span>
<span data-ttu-id="6997b-112">它可用于将多个触发器添加到多个计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-112">You can use it to add multiple triggers to multiple scheduled jobs.</span></span>

<span data-ttu-id="6997b-113">作业触发器按一次性或定期计划或事件发生时启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-113">A job trigger starts a scheduled job on a one-time or recurring schedule or when an event occurs.</span></span>

<span data-ttu-id="6997b-114">使用 **Add-JobTrigger** 的 *Trigger* 参数来标识要添加的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="6997b-114">Use the *Trigger* parameter of **Add-JobTrigger** to identify the job triggers to add.</span></span>
<span data-ttu-id="6997b-115">使用 **Add-JobTrigger** 的 *Name* 、 *ID* 或 *InputObject* 参数来标识将触发器添加到的计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-115">Use the *Name* , *ID* , or *InputObject* parameters of **Add-JobTrigger** to identify the scheduled job to which the triggers are added.</span></span>

<span data-ttu-id="6997b-116">若要创建 *Trigger* 参数的值的作业触发器，请使用 New-JobTrigger cmdlet 或使用哈希表指定作业触发器。</span><span class="sxs-lookup"><span data-stu-id="6997b-116">To create job triggers for the value of the *Trigger* parameter, use the New-JobTrigger cmdlet or use a hash table to specify the job trigger.</span></span>

<span data-ttu-id="6997b-117">**Add-JobTrigger** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="6997b-117">**Add-JobTrigger** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="6997b-118">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="6997b-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="6997b-119">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="6997b-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="6997b-120">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="6997b-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="6997b-121">示例</span><span class="sxs-lookup"><span data-stu-id="6997b-121">EXAMPLES</span></span>

### <span data-ttu-id="6997b-122">示例 1：将作业触发器添加到计划作业</span><span class="sxs-lookup"><span data-stu-id="6997b-122">Example 1: Add a job trigger to a scheduled job</span></span>

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

<span data-ttu-id="6997b-123">以下命令将每日作业触发器添加到 TestJob 计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-123">These commands add the Daily job trigger to the TestJob scheduled job.</span></span>

<span data-ttu-id="6997b-124">第一个命令使用 New-JobTrigger cmdlet 创建每天凌晨 3:00 启动计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="6997b-124">The first command uses the New-JobTrigger cmdlet to create a job trigger that starts a scheduled job every day at 3:00 a.m.</span></span>
<span data-ttu-id="6997b-125">此命令将作业触发器保存在 $Daily 变量中。</span><span class="sxs-lookup"><span data-stu-id="6997b-125">The command saves the job trigger in the $Daily variable.</span></span>

<span data-ttu-id="6997b-126">第二个命令使用 **Add-JobTrigger** cmdlet 将 $Startup 变量中的作业触发器添加到 TestJob 计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-126">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in the $Startup variable to the TestJob scheduled job.</span></span>

### <span data-ttu-id="6997b-127">示例2：将作业触发器添加到多个计划作业</span><span class="sxs-lookup"><span data-stu-id="6997b-127">Example 2: Add a job trigger to several scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

<span data-ttu-id="6997b-128">此命令将一个 AtStartup 作业触发器添加到本地计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-128">This command adds an AtStartup job trigger to all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="6997b-129">它使用 Get-ScheduledJob 获取该计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-129">It uses the Get-ScheduledJob to get all of the scheduled jobs on the computer.</span></span>
<span data-ttu-id="6997b-130">它使用管道运算符 (|) 将作业发送到 **Add-JobTrigger** cmdlet，此 cmdlet 将作业触发器添加到每个计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-130">It uses a pipeline operator (|) to send the jobs to the **Add-JobTrigger** cmdlet, which adds the job trigger to each of the scheduled jobs.</span></span>
<span data-ttu-id="6997b-131">*Trigger* 参数的值是创建 AtStartup 作业触发器的 New-JobTrigger 命令。</span><span class="sxs-lookup"><span data-stu-id="6997b-131">The value of the *Trigger* parameter is a New-JobTrigger command that creates the AtStartup job trigger.</span></span>

### <span data-ttu-id="6997b-132">示例 3：复制作业触发器</span><span class="sxs-lookup"><span data-stu-id="6997b-132">Example 3: Copy a job trigger</span></span>

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

<span data-ttu-id="6997b-133">以下命令从 BackupArchives 计划作业复制作业触发器，然后将它添加到 TestBackup 和 BackupLogs 计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-133">These commands copy the job trigger from the BackupArchives scheduled job and add it to the TestBackup and BackupLogs scheduled jobs.</span></span>

<span data-ttu-id="6997b-134">第一个命令使用 Get-JobTrigger cmdlet 获取 BackupArchives 计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="6997b-134">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the BackupArchives scheduled job.</span></span>
<span data-ttu-id="6997b-135">此命令将该触发器保存在 $t 变量中。</span><span class="sxs-lookup"><span data-stu-id="6997b-135">The command saves the trigger in the $t variable.</span></span>

<span data-ttu-id="6997b-136">第二个命令使用 **Add-JobTrigger** cmdlet 将 $t 中的作业触发器添加到 TestBackup 和 BackupLogs 计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-136">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in $t to the TestBackup and BackupLogs scheduled jobs.</span></span>

## <span data-ttu-id="6997b-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6997b-137">PARAMETERS</span></span>

### <span data-ttu-id="6997b-138">-Id</span><span class="sxs-lookup"><span data-stu-id="6997b-138">-Id</span></span>
<span data-ttu-id="6997b-139">指定计划作业的标识号。</span><span class="sxs-lookup"><span data-stu-id="6997b-139">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="6997b-140">**Add-JobTrigger** 将作业触发器添加到指定的计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-140">**Add-JobTrigger** adds the job trigger to the specified scheduled jobs.</span></span>

<span data-ttu-id="6997b-141">若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6997b-141">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6997b-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6997b-142">-InputObject</span></span>
<span data-ttu-id="6997b-143">指定计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-143">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="6997b-144">请输入包含 **ScheduledJob** 对象的变量，或者键入获取 **ScheduledJob** 对象的命令或表达式，例如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="6997b-144">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="6997b-145">还可以通过管道将 **ScheduledJob** 对象传递给 **Add-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="6997b-145">You can also pipe **ScheduledJob** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6997b-146">-Name</span><span class="sxs-lookup"><span data-stu-id="6997b-146">-Name</span></span>
<span data-ttu-id="6997b-147">指定计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="6997b-147">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="6997b-148">**Add-JobTrigger** 将作业触发器添加到指定的计划作业。</span><span class="sxs-lookup"><span data-stu-id="6997b-148">**Add-JobTrigger** adds the job triggers to the specified scheduled jobs.</span></span>
<span data-ttu-id="6997b-149">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="6997b-149">Wildcards are supported.</span></span>

<span data-ttu-id="6997b-150">若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6997b-150">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6997b-151">-Trigger</span><span class="sxs-lookup"><span data-stu-id="6997b-151">-Trigger</span></span>
<span data-ttu-id="6997b-152">指定要添加的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="6997b-152">Specifies the job triggers to add.</span></span>
<span data-ttu-id="6997b-153">输入一个可指定作业触发器的哈希表或包含 **ScheduledJobTrigger** 对象的变量，或者键入可获取 **ScheduledJobTrigger** 对象的命令或表达式，例如 Get-JobTrigger 命令。</span><span class="sxs-lookup"><span data-stu-id="6997b-153">Enter a hash table that specifies job triggers or a variable that contains **ScheduledJobTrigger** objects, or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="6997b-154">还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Add-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="6997b-154">You can also pipe **ScheduledJobTrigger** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6997b-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6997b-155">CommonParameters</span></span>
<span data-ttu-id="6997b-156">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6997b-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6997b-157">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6997b-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6997b-158">输入</span><span class="sxs-lookup"><span data-stu-id="6997b-158">INPUTS</span></span>

### <span data-ttu-id="6997b-159">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger、Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="6997b-159">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger, Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="6997b-160">你可以通过管道将作业触发器或计划作业传递给 **Add-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="6997b-160">You can pipe job triggers or scheduled jobs to **Add-JobTrigger** .</span></span>

## <span data-ttu-id="6997b-161">输出</span><span class="sxs-lookup"><span data-stu-id="6997b-161">OUTPUTS</span></span>

### <span data-ttu-id="6997b-162">无</span><span class="sxs-lookup"><span data-stu-id="6997b-162">None</span></span>
<span data-ttu-id="6997b-163">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="6997b-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6997b-164">注释</span><span class="sxs-lookup"><span data-stu-id="6997b-164">NOTES</span></span>

## <span data-ttu-id="6997b-165">相关链接</span><span class="sxs-lookup"><span data-stu-id="6997b-165">RELATED LINKS</span></span>

[<span data-ttu-id="6997b-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="6997b-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="6997b-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6997b-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="6997b-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="6997b-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6997b-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="6997b-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="6997b-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6997b-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="6997b-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6997b-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="6997b-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="6997b-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6997b-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="6997b-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6997b-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="6997b-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="6997b-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6997b-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="6997b-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6997b-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="6997b-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6997b-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="6997b-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6997b-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
