---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197791"
---
# <span data-ttu-id="c9dc1-103">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-103">Enable-JobTrigger</span></span>

## <span data-ttu-id="c9dc1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c9dc1-104">SYNOPSIS</span></span>
<span data-ttu-id="c9dc1-105">启用计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-105">Enables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="c9dc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9dc1-106">SYNTAX</span></span>

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c9dc1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c9dc1-107">DESCRIPTION</span></span>
<span data-ttu-id="c9dc1-108">**Enable-JobTrigger** cmdlet 重新启用作业计划的作业触发器，例如通过 Disable-JobTrigger cmdlet 禁用的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-108">The **Enable-JobTrigger** cmdlet re-enables job triggers of scheduled jobs, such as those that were disabled by using the Disable-JobTrigger cmdlet.</span></span>
<span data-ttu-id="c9dc1-109">启用和重新启用的作业触发器均可立即启动计划作业；无需重新启动 Windows 或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-109">Enabled and re-enabled job triggers can start scheduled jobs immediately; there is no need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="c9dc1-110">若要使用此 cmdlet，请使用 Get-JobTrigger cmdlet 获取作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-110">To use this cmdlet, use the  Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="c9dc1-111">然后，通过管道将这些作业触发器传递给 **Enable-JobTrigger** ，或使用其 *InputObject* 参数。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-111">Then pipe the job triggers to **Enable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="c9dc1-112">若要启用作业触发器， **Enable-JobTrigger** cmdlet 应将该作业触发器的 Enabled 属性设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-112">To enable a job trigger, the **Enable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $True.</span></span>

<span data-ttu-id="c9dc1-113">**Enable-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-113">**Enable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="c9dc1-114">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-114">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="c9dc1-115">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-115">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="c9dc1-116">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c9dc1-117">示例</span><span class="sxs-lookup"><span data-stu-id="c9dc1-117">EXAMPLES</span></span>

### <span data-ttu-id="c9dc1-118">示例 1：启用作业触发器</span><span class="sxs-lookup"><span data-stu-id="c9dc1-118">Example 1: Enable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

<span data-ttu-id="c9dc1-119">启用本地计算机上 Backup-Archives 计划作业的第一个触发器（ID 为 1）。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-119">This command enables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="c9dc1-120">此命令使用 Get-JobTrigger cmdlet 获取作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-120">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="c9dc1-121">管道运算符将该作业触发器发送到 **Enable-JobTrigger** cmdlet，此 cmdlet 将对其进行启用。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-121">A pipeline operator sends the job trigger to the **Enable-JobTrigger** cmdlet, which enables it.</span></span>

### <span data-ttu-id="c9dc1-122">示例 2：启用所有作业触发器</span><span class="sxs-lookup"><span data-stu-id="c9dc1-122">Example 2: Enable all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

<span data-ttu-id="c9dc1-123">此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-123">The command uses the Get-ScheduledJob cmdlet to get  the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="c9dc1-124">管道运算符 (|) 将计划作业发送到 Get-JobTrigger cmdlet，此 cmdlet 从计划作业中获取所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-124">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="c9dc1-125">另一个管道运算符将这些作业触发器发送到 **Enable-JobTrigger** cmdlet，此 cmdlet 将对其进行启用。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-125">Another pipeline operator sends the job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="c9dc1-126">示例 3：启用远程计算机上计划作业的作业触发器</span><span class="sxs-lookup"><span data-stu-id="c9dc1-126">Example 3: Enable the job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

<span data-ttu-id="c9dc1-127">此命令在 Server01 远程计算机上重新启用 DeployPackage 计划作业中的 AtLogon 作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-127">This command re-enables the AtLogon job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="c9dc1-128">该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-128">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="c9dc1-129">远程命令使用 Get-JobTrigger cmdlet 获取 DeployPackage 计划作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-129">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="c9dc1-130">管道运算符将作业触发器发送到 Where-Object cmdlet，此 cmdlet 仅返回 AtLogon 作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-130">A pipeline operator sends the job triggers to the Where-Object cmdlet which returns only AtLogon job triggers.</span></span>
<span data-ttu-id="c9dc1-131">另一个管道运算符将 AtLogon 作业触发器发送到 **Enable-JobTrigger** cmdlet，此 cmdlet 将对其进行启用。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-131">A pipeline operator sends the AtLogon job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="c9dc1-132">示例 4：显示禁用的作业触发器</span><span class="sxs-lookup"><span data-stu-id="c9dc1-132">Example 4: Display disabled job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="c9dc1-133">此命令将所有计划作业的所有禁用的作业触发器都显示在某个表中。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-133">This command displays all disabled job triggers of all scheduled jobs in a table.</span></span>
<span data-ttu-id="c9dc1-134">你可以使用类似此命令的命令来发现可能需要启用的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-134">You can use a command like this one to discover job triggers that might need to be enabled.</span></span>

<span data-ttu-id="c9dc1-135">此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-135">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="c9dc1-136">管道运算符 (|) 将计划作业发送到 Get-JobTrigger cmdlet，此 cmdlet 从计划作业中获取所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-136">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="c9dc1-137">另一个管道运算符将作业触发器发送到 Where-Object cmdlet，此 cmdlet 仅返回已禁用的作业触发器，即其中作业触发器的 Enabled 属性值不为 (!) true。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-137">Another pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only job triggers that are disabled, that is, where the value of the Enabled property of the job trigger is not (!) true.</span></span>

<span data-ttu-id="c9dc1-138">另一个管道运算符将禁用的作业触发器发送到 Format-Table cmdlet，后者在表中显示作业触发器的选定属性。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-138">Another pipeline operator sends the disabled job triggers to the Format-Table cmdlet, which displays the selected properties of the job triggers in a table.</span></span>
<span data-ttu-id="c9dc1-139">这些属性包含新的 JobName 属性，该属性可在作业触发器的 JobDefinition 属性中显示计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-139">The properties include a new JobName property that displays the name of the scheduled job in the JobDefinition property of the job trigger.</span></span>

## <span data-ttu-id="c9dc1-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9dc1-140">PARAMETERS</span></span>

### <span data-ttu-id="c9dc1-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c9dc1-141">-InputObject</span></span>
<span data-ttu-id="c9dc1-142">指定要启用的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-142">Specifies the job trigger to enable.</span></span>
<span data-ttu-id="c9dc1-143">输入包含 **ScheduledJobTrigger** 对象的变量，或者键入获取 **ScheduledJobTrigger** 对象的命令或表达式，如 Get-JobTrigger 命令。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-143">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="c9dc1-144">还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Enable-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-144">You can also pipe a **ScheduledJobTrigger** object to **Enable-JobTrigger** .</span></span>

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

### <span data-ttu-id="c9dc1-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c9dc1-145">-PassThru</span></span>
<span data-ttu-id="c9dc1-146">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-146">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="c9dc1-147">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c9dc1-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c9dc1-148">-Confirm</span></span>
<span data-ttu-id="c9dc1-149">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c9dc1-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c9dc1-150">-WhatIf</span></span>
<span data-ttu-id="c9dc1-151">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c9dc1-152">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c9dc1-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c9dc1-153">CommonParameters</span></span>
<span data-ttu-id="c9dc1-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9dc1-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9dc1-156">输入</span><span class="sxs-lookup"><span data-stu-id="c9dc1-156">INPUTS</span></span>

### <span data-ttu-id="c9dc1-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="c9dc1-158">可以通过管道将作业触发器传递给 **Enable-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-158">You can pipe job triggers to **Enable-JobTrigger** .</span></span>

## <span data-ttu-id="c9dc1-159">输出</span><span class="sxs-lookup"><span data-stu-id="c9dc1-159">OUTPUTS</span></span>

### <span data-ttu-id="c9dc1-160">无</span><span class="sxs-lookup"><span data-stu-id="c9dc1-160">None</span></span>
<span data-ttu-id="c9dc1-161">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c9dc1-162">注释</span><span class="sxs-lookup"><span data-stu-id="c9dc1-162">NOTES</span></span>

* <span data-ttu-id="c9dc1-163">如果启用某个已启用的作业触发器， **Enable-JobTrigger** 不会生成错误或警告。</span><span class="sxs-lookup"><span data-stu-id="c9dc1-163">**Enable-JobTrigger** does not generate errors or warnings if you enable a job trigger that is already enabled.</span></span>

## <span data-ttu-id="c9dc1-164">相关链接</span><span class="sxs-lookup"><span data-stu-id="c9dc1-164">RELATED LINKS</span></span>

[<span data-ttu-id="c9dc1-165">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-165">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="c9dc1-166">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-166">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="c9dc1-167">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c9dc1-167">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="c9dc1-168">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-168">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="c9dc1-169">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c9dc1-169">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="c9dc1-170">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-170">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="c9dc1-171">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c9dc1-171">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="c9dc1-172">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c9dc1-172">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="c9dc1-173">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-173">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="c9dc1-174">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c9dc1-174">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="c9dc1-175">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c9dc1-175">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="c9dc1-176">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-176">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="c9dc1-177">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c9dc1-177">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="c9dc1-178">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c9dc1-178">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="c9dc1-179">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c9dc1-179">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="c9dc1-180">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c9dc1-180">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
