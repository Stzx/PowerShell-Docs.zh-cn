---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197803"
---
# <span data-ttu-id="44281-103">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-103">Disable-JobTrigger</span></span>

## <span data-ttu-id="44281-104">摘要</span><span class="sxs-lookup"><span data-stu-id="44281-104">SYNOPSIS</span></span>
<span data-ttu-id="44281-105">禁用计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-105">Disables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="44281-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44281-106">SYNTAX</span></span>

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="44281-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44281-107">DESCRIPTION</span></span>
<span data-ttu-id="44281-108">**Disable-JobTrigger** cmdlet 可临时禁用计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-108">The **Disable-JobTrigger** cmdlet temporarily disables the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="44281-109">该禁用操作会保留所有作业触发器属性，但它会阻止作业触发器启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="44281-109">Disabling preserves all job trigger properties, but it prevents the job trigger from starting the scheduled job.</span></span>

<span data-ttu-id="44281-110">若要使用此 cmdlet，请使用 Get-JobTrigger cmdlet 来获取作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-110">To use this cmdlet, use the Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="44281-111">然后，通过管道将这些作业触发器传递给 **Disable-JobTrigger** ，或使用其 *InputObject* 参数。</span><span class="sxs-lookup"><span data-stu-id="44281-111">Then pipe the job triggers to **Disable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="44281-112">若要禁用作业触发器， **get-jobtrigger** cmdlet 会将该作业触发器的 Enabled 属性设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="44281-112">To disable a job trigger, the **Disable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $False.</span></span>
<span data-ttu-id="44281-113">若要重新启用作业触发器，请使用 Enable-JobTrigger cmdlet，该 cmdlet 可将作业触发器的 **Enabled** 属性设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="44281-113">To re-enable the job trigger, use the Enable-JobTrigger cmdlet, which sets the **Enabled** property of the job trigger to $True.</span></span>
<span data-ttu-id="44281-114">禁用某个作业触发器不会禁用计划作业（例如可通过 Disable-ScheduledJob 来实现），但如果禁用所有作业触发器，结果与禁用计划作业相同。</span><span class="sxs-lookup"><span data-stu-id="44281-114">Disabling a job trigger does not disable the scheduled job, such as is done by the Disable-ScheduledJob cmdlet, but if you disable all job triggers, the effect is the same as disabling the scheduled job.</span></span>

<span data-ttu-id="44281-115">如果禁用了计划作业或者禁用了计划作业的所有作业触发器，你仍然可以使用 Start-Job cmdlet 来启动该作业，或将禁用的计划作业用作模板。</span><span class="sxs-lookup"><span data-stu-id="44281-115">If you disable a scheduled job or disable all job triggers of a scheduled job, you can still start the job by using the Start-Job cmdlet or use the disabled scheduled job as a template.</span></span>

<span data-ttu-id="44281-116">**Disable-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="44281-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="44281-117">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="44281-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="44281-118">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="44281-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="44281-119">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="44281-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="44281-120">示例</span><span class="sxs-lookup"><span data-stu-id="44281-120">EXAMPLES</span></span>

### <span data-ttu-id="44281-121">示例 1：禁用作业触发器</span><span class="sxs-lookup"><span data-stu-id="44281-121">Example 1: Disable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

<span data-ttu-id="44281-122">此命令禁用本地计算机上 Backup-Archives 计划作业的第一个触发器（ID 为 1）。</span><span class="sxs-lookup"><span data-stu-id="44281-122">This command disables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="44281-123">此命令使用 Get-JobTrigger cmdlet 获取作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-123">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="44281-124">管道运算符将该作业触发器发送到 **Disable-JobTrigger** cmdlet，此 cmdlet 将对其进行禁用。</span><span class="sxs-lookup"><span data-stu-id="44281-124">A pipeline operator sends the job trigger to the **Disable-JobTrigger** cmdlet, which disables it.</span></span>

### <span data-ttu-id="44281-125">示例 2：禁用所有作业触发器</span><span class="sxs-lookup"><span data-stu-id="44281-125">Example 2: Disable all job triggers</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="44281-126">以下命令禁用两个计划作业上的所有作业触发器并显示结果。</span><span class="sxs-lookup"><span data-stu-id="44281-126">These commands disable all job triggers on two scheduled jobs and display the results.</span></span>

### <span data-ttu-id="44281-127">示例3：禁用远程计算机上计划作业的作业触发器</span><span class="sxs-lookup"><span data-stu-id="44281-127">Example 3: Disable job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

<span data-ttu-id="44281-128">此命令在 Server01 远程计算机上禁用 DeployPackage 计划作业中每日作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-128">This command disables the daily job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="44281-129">该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="44281-129">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="44281-130">远程命令使用 Get-JobTrigger cmdlet 获取 DeployPackage 计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-130">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="44281-131">管道运算符将作业触发器发送到 Where-Object cmdlet，该 cmdlet 仅返回每日作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-131">A pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only daily job triggers.</span></span>
<span data-ttu-id="44281-132">管道运算符将每日作业触发器发送到 **get-jobtrigger** cmdlet，这会将其禁用。</span><span class="sxs-lookup"><span data-stu-id="44281-132">A pipeline operator sends the daily job triggers to the **Disable-JobTrigger** cmdlet, which disables them.</span></span>

## <span data-ttu-id="44281-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44281-133">PARAMETERS</span></span>

### <span data-ttu-id="44281-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="44281-134">-InputObject</span></span>
<span data-ttu-id="44281-135">指定要禁用的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="44281-135">Specifies the job trigger to be disabled.</span></span>
<span data-ttu-id="44281-136">输入包含 **ScheduledJobTrigger** 对象的变量，或者键入可获取 **ScheduledJobTrigger** 对象的命令或表达式，例如 Get-JobTrigger 命令。</span><span class="sxs-lookup"><span data-stu-id="44281-136">Enter a variable that contains  **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="44281-137">还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Disable-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="44281-137">You can also pipe a **ScheduledJobTrigger** object to **Disable-JobTrigger** .</span></span>

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

### <span data-ttu-id="44281-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="44281-138">-PassThru</span></span>
<span data-ttu-id="44281-139">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="44281-139">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="44281-140">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="44281-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="44281-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="44281-141">-Confirm</span></span>
<span data-ttu-id="44281-142">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="44281-142">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44281-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="44281-143">-WhatIf</span></span>
<span data-ttu-id="44281-144">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="44281-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="44281-145">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="44281-145">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44281-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="44281-146">CommonParameters</span></span>
<span data-ttu-id="44281-147">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="44281-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44281-148">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="44281-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44281-149">输入</span><span class="sxs-lookup"><span data-stu-id="44281-149">INPUTS</span></span>

### <span data-ttu-id="44281-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="44281-151">你可以通过管道将作业触发器传递给 **Disable-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="44281-151">You can pipe job triggers to **Disable-JobTrigger** .</span></span>

## <span data-ttu-id="44281-152">输出</span><span class="sxs-lookup"><span data-stu-id="44281-152">OUTPUTS</span></span>

### <span data-ttu-id="44281-153">无</span><span class="sxs-lookup"><span data-stu-id="44281-153">None</span></span>
<span data-ttu-id="44281-154">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="44281-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="44281-155">注释</span><span class="sxs-lookup"><span data-stu-id="44281-155">NOTES</span></span>

* <span data-ttu-id="44281-156">**Disable-JobTrigger** 不会在你禁用某个已禁用的作业触发器时生成错误或警告。</span><span class="sxs-lookup"><span data-stu-id="44281-156">**Disable-JobTrigger** does not generate errors or warnings if you disable a job trigger that is already disabled.</span></span>

## <span data-ttu-id="44281-157">相关链接</span><span class="sxs-lookup"><span data-stu-id="44281-157">RELATED LINKS</span></span>

[<span data-ttu-id="44281-158">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-158">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="44281-159">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-159">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="44281-160">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="44281-160">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="44281-161">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-161">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="44281-162">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="44281-162">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="44281-163">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-163">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="44281-164">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="44281-164">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="44281-165">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="44281-165">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="44281-166">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-166">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="44281-167">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="44281-167">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="44281-168">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="44281-168">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="44281-169">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-169">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="44281-170">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="44281-170">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="44281-171">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="44281-171">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="44281-172">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="44281-172">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="44281-173">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="44281-173">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
