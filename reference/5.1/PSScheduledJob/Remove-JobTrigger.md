---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197783"
---
# <span data-ttu-id="fc4e6-103">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-103">Remove-JobTrigger</span></span>

## <span data-ttu-id="fc4e6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fc4e6-104">SYNOPSIS</span></span>
<span data-ttu-id="fc4e6-105">从计划作业中删除作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-105">Delete job triggers from scheduled jobs.</span></span>

## <span data-ttu-id="fc4e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fc4e6-106">SYNTAX</span></span>

### <span data-ttu-id="fc4e6-107">JobDefinition（默认值）</span><span class="sxs-lookup"><span data-stu-id="fc4e6-107">JobDefinition (Default)</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### <span data-ttu-id="fc4e6-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="fc4e6-108">JobDefinitionId</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="fc4e6-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="fc4e6-109">JobDefinitionName</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="fc4e6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fc4e6-110">DESCRIPTION</span></span>
<span data-ttu-id="fc4e6-111">**Get-jobtrigger** cmdlet 从计划作业中删除作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-111">The **Remove-JobTrigger** cmdlet deletes job triggers from scheduled jobs.</span></span>

<span data-ttu-id="fc4e6-112">作业触发器定义用于启动计划作业的循环计划或条件。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-112">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="fc4e6-113">若要管理作业触发器，请使用 New-JobTrigger、Add-JobTrigger、Set-JobTrigger 和 Set-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-113">To manage job triggers, use the New-JobTrigger, Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJob cmdlets.</span></span>

<span data-ttu-id="fc4e6-114">使用 *Remove-JobTrigger* 的 *Name* 、 *ID* 或 **InputObject** 参数来标识从中删除触发器的计划作业。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-114">Use the *Name* , *ID* , or *InputObject* parameters of **Remove-JobTrigger** to identify the scheduled jobs from which the triggers are removed.</span></span>
<span data-ttu-id="fc4e6-115">使用 *TriggerID* 参数来标识要删除的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-115">Use the *TriggerID* parameter to identify the job triggers to delete.</span></span>
<span data-ttu-id="fc4e6-116">默认情况下， **Remove-JobTrigger** 将删除计划作业的所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-116">By default, **Remove-JobTrigger** deletes all job triggers of a scheduled job.</span></span>

<span data-ttu-id="fc4e6-117">**Remove-JobTrigger** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-117">**Remove-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="fc4e6-118">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="fc4e6-119">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="fc4e6-120">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="fc4e6-121">示例</span><span class="sxs-lookup"><span data-stu-id="fc4e6-121">EXAMPLES</span></span>

### <span data-ttu-id="fc4e6-122">示例 1：删除所有作业触发器</span><span class="sxs-lookup"><span data-stu-id="fc4e6-122">Example 1: Delete all job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

<span data-ttu-id="fc4e6-123">此命令从计划作业中删除名称以 "Test" 开头的所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-123">This command deletes all job triggers from scheduled job that have names that begin with Test.</span></span>

### <span data-ttu-id="fc4e6-124">示例 2：删除选定的作业触发器</span><span class="sxs-lookup"><span data-stu-id="fc4e6-124">Example 2: Delete selected job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

<span data-ttu-id="fc4e6-125">此命令仅从 BackupArchive 计划作业中删除第三个触发器 (ID = 3)。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-125">This command deletes only the third trigger (ID = 3) from the BackupArchive scheduled job.</span></span>

### <span data-ttu-id="fc4e6-126">示例 3：从所有计划作业中删除 AtStartup 作业触发器</span><span class="sxs-lookup"><span data-stu-id="fc4e6-126">Example 3: Delete AtStartup job triggers from all scheduled jobs</span></span>

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

<span data-ttu-id="fc4e6-127">此函数从本地计算机上的所有作业中删除所有 AtStartup 作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-127">This function deletes all AtStartup job triggers from all jobs on the local computer.</span></span>
<span data-ttu-id="fc4e6-128">若要使用函数，请在会话中运行函数，然后键入 `Delete-AtStartup` 。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-128">To use the function, run the function in your session and then type `Delete-AtStartup`.</span></span>

<span data-ttu-id="fc4e6-129">Delete-AtStartup 函数包含单个命令。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-129">The Delete-AtStartup function contains a single command.</span></span>
<span data-ttu-id="fc4e6-130">此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-130">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="fc4e6-131">管道运算符 (|) 将计划作业发送到 Get-JobTrigger cmdlet，此 cmdlet 从每个计划作业中获取所有作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-131">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all of the job triggers from each of the scheduled jobs.</span></span>
<span data-ttu-id="fc4e6-132">管道运算符将作业触发器发送到 Where-Object cmdlet，该 cmdlet 选择作业触发器的 Frequency 属性值等于 AtStartup 的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-132">A pipeline operator sends the job triggers to the Where-Object cmdlet, which selects job triggers where the value of the Frequency property of the job trigger equals AtStartup.</span></span>

<span data-ttu-id="fc4e6-133">**Get-jobtrigger** 对象具有 **JobDefinition** 属性，该属性包含其触发的计划作业。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-133">**JobTrigger** objects have a **JobDefinition** property that contains the scheduled job that they trigger.</span></span>
<span data-ttu-id="fc4e6-134">该命令的剩余部分将使用这一有价值的功能。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-134">The remainder of the command uses that valuable feature.</span></span>

<span data-ttu-id="fc4e6-135">管道运算符将 AtStartup 作业触发器发送到 ForEach-Object cmdlet，后者在每个 AtStartup 触发器上运行 **Remove-JobTrigger** 命令。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-135">A pipeline operator sends the AtStartup job triggers to the ForEach-Object cmdlet, which runs a **Remove-JobTrigger** command on each AtStartup trigger.</span></span>
<span data-ttu-id="fc4e6-136">在作业触发器的 JobDefinition 属性中， **Remove-JobTrigger** 的 *InputObject* 参数值是计划作业。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-136">The value of the *InputObject* parameter of **Remove-JobTrigger** is the scheduled job in the JobDefinition property of the job trigger.</span></span>
<span data-ttu-id="fc4e6-137">在作业触发器的 ID 属性中， *TriggerID* 参数的值是标识符。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-137">The value of the *TriggerID* parameter is the identifier in the ID property of the job trigger.</span></span>

### <span data-ttu-id="fc4e6-138">示例 4：从远程计划作业中删除作业触发器</span><span class="sxs-lookup"><span data-stu-id="fc4e6-138">Example 4: Delete a job trigger from a remote scheduled job</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

<span data-ttu-id="fc4e6-139">此命令从 Server01 计算机上的 Inventory 作业中删除第一个作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-139">This command deletes the first job trigger from the Inventory job on the Server01 computer.</span></span>

<span data-ttu-id="fc4e6-140">该命令使用 get-jobtrigger **cmdlet 在** Server01 计算机上运行 **Remove-JobTrigger** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-140">The command uses the **Invoke-Command** cmdlet to run the **Remove-JobTrigger** cmdlet on the Server01 computer.</span></span>
<span data-ttu-id="fc4e6-141">**Get-jobtrigger** Cmdlet 使用 *ID* 参数来标识清单计划作业，并使用 *TriggerID* 参数来指定第一个触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-141">The **Remove-JobTrigger** cmdlet uses the *ID* parameter to identify the Inventory scheduled job and the *TriggerID* parameter to specify the first trigger.</span></span>
<span data-ttu-id="fc4e6-142">当多个计划作业具有相同或类似的名称时， *ID* 参数特别有用。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-142">The *ID* parameter is especially useful when multiple scheduled jobs have the same or similar names.</span></span>

## <span data-ttu-id="fc4e6-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fc4e6-143">PARAMETERS</span></span>

### <span data-ttu-id="fc4e6-144">-Id</span><span class="sxs-lookup"><span data-stu-id="fc4e6-144">-Id</span></span>
<span data-ttu-id="fc4e6-145">指定计划作业的标识号。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-145">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="fc4e6-146">**Remove-JobTrigger** 可从指定的计划作业中删除作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-146">**Remove-JobTrigger** deletes job triggers from the specified scheduled jobs.</span></span>

<span data-ttu-id="fc4e6-147">若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-147">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="fc4e6-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fc4e6-148">-InputObject</span></span>
<span data-ttu-id="fc4e6-149">指定计划作业。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-149">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="fc4e6-150">请输入包含 **ScheduledJob** 对象的变量，或者键入获取 **ScheduledJob** 对象的命令或表达式，例如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-150">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="fc4e6-151">还可以通过管道将 **ScheduledJob** 对象传递给 **Remove-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-151">You can also pipe **ScheduledJob** objects to **Remove-JobTrigger** .</span></span>

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

### <span data-ttu-id="fc4e6-152">-Name</span><span class="sxs-lookup"><span data-stu-id="fc4e6-152">-Name</span></span>
<span data-ttu-id="fc4e6-153">指定计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-153">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="fc4e6-154">**Remove-JobTrigger** 可从指定的计划作业中删除作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-154">**Remove-JobTrigger** deletes the job triggers from the specified scheduled jobs.</span></span>
<span data-ttu-id="fc4e6-155">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-155">Wildcards are supported.</span></span>

<span data-ttu-id="fc4e6-156">若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-156">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="fc4e6-157">-TriggerId</span><span class="sxs-lookup"><span data-stu-id="fc4e6-157">-TriggerId</span></span>
<span data-ttu-id="fc4e6-158">只删除指定的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-158">Deletes only the specified job triggers.</span></span>
<span data-ttu-id="fc4e6-159">默认情况下， **Remove-JobTrigger** 可从计划作业中删除所有触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-159">By default, **Remove-JobTrigger** deletes all triggers from the scheduled jobs.</span></span>
<span data-ttu-id="fc4e6-160">在计划作业有多个作业触发器时使用此参数。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-160">Use this parameter when the scheduled jobs have multiple job triggers.</span></span>

<span data-ttu-id="fc4e6-161">输入计划作业中一个或多个作业触发器的触发器 ID。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="fc4e6-162">如果指定多个计划作业，则 **get-jobtrigger** 将从所有计划作业中删除具有指定 ID 的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-162">If you specify multiple scheduled jobs, **Remove-JobTrigger** deletes the job trigger with the specified ID from all scheduled jobs.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fc4e6-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fc4e6-163">CommonParameters</span></span>
<span data-ttu-id="fc4e6-164">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fc4e6-165">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fc4e6-166">输入</span><span class="sxs-lookup"><span data-stu-id="fc4e6-166">INPUTS</span></span>

### <span data-ttu-id="fc4e6-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="fc4e6-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fc4e6-168">你可以通过管道将计划作业传递给 **Remove-JobTrigger** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-168">You can pipe scheduled jobs to the **Remove-JobTrigger** cmdlet.</span></span>

## <span data-ttu-id="fc4e6-169">输出</span><span class="sxs-lookup"><span data-stu-id="fc4e6-169">OUTPUTS</span></span>

### <span data-ttu-id="fc4e6-170">无</span><span class="sxs-lookup"><span data-stu-id="fc4e6-170">None</span></span>
<span data-ttu-id="fc4e6-171">该 cmdlet 不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="fc4e6-171">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fc4e6-172">注释</span><span class="sxs-lookup"><span data-stu-id="fc4e6-172">NOTES</span></span>

## <span data-ttu-id="fc4e6-173">相关链接</span><span class="sxs-lookup"><span data-stu-id="fc4e6-173">RELATED LINKS</span></span>

[<span data-ttu-id="fc4e6-174">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-174">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="fc4e6-175">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-175">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="fc4e6-176">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fc4e6-176">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="fc4e6-177">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-177">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="fc4e6-178">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fc4e6-178">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="fc4e6-179">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-179">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="fc4e6-180">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fc4e6-180">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="fc4e6-181">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fc4e6-181">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="fc4e6-182">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-182">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="fc4e6-183">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fc4e6-183">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="fc4e6-184">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fc4e6-184">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="fc4e6-185">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-185">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="fc4e6-186">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fc4e6-186">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="fc4e6-187">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fc4e6-187">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="fc4e6-188">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fc4e6-188">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="fc4e6-189">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fc4e6-189">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
