---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197773"
---
# <span data-ttu-id="03dcd-103">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-103">Unregister-ScheduledJob</span></span>

## <span data-ttu-id="03dcd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="03dcd-104">SYNOPSIS</span></span>
<span data-ttu-id="03dcd-105">删除本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-105">Deletes scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="03dcd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03dcd-106">SYNTAX</span></span>

### <span data-ttu-id="03dcd-107">Definition（默认值）</span><span class="sxs-lookup"><span data-stu-id="03dcd-107">Definition (Default)</span></span>

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="03dcd-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="03dcd-108">DefinitionId</span></span>

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="03dcd-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="03dcd-109">DefinitionName</span></span>

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="03dcd-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03dcd-110">DESCRIPTION</span></span>
<span data-ttu-id="03dcd-111">**Unregister-ScheduledJob** cmdlet 可删除本地计算机中的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-111">The **Unregister-ScheduledJob** cmdlet deletes scheduled jobs from the local computer.</span></span>

<span data-ttu-id="03dcd-112">当删除或注销计划作业时， **get-scheduledjob** 会在 $home \appdata\local\microsoft\windows\powershell\scheduledjobs 目录) 中删除计划作业 (的目录，该目录包含用于定义计划作业、作业执行历史记录和所有作业结果的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="03dcd-112">When it deletes or unregisters a scheduled job, **Unregister-ScheduledJob** deletes the directory for the scheduled job (in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory), which contains the XML file that defines the scheduled job, the job execution history, and all job results.</span></span>
<span data-ttu-id="03dcd-113">此操作还将删除任务计划程序中的作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-113">This action also deletes the job from Task Scheduler.</span></span>

<span data-ttu-id="03dcd-114">**Unregister-ScheduledJob** 仅删除使用 Register-ScheduledJob cmdlet 创建的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-114">**Unregister-ScheduledJob** deletes only the scheduled jobs that are created by using the Register-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="03dcd-115">它不会删除在任务计划程序中创建的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-115">It does not delete scheduled jobs that are created in Task Scheduler.</span></span>

<span data-ttu-id="03dcd-116">你可以使用 **get-scheduledjob** 的参数，按 ID 或名称或从 Get-ScheduledJob 中的管道计划作业来删除 **get-scheduledjob** 。</span><span class="sxs-lookup"><span data-stu-id="03dcd-116">You can use the parameters of **Unregister-ScheduledJob** to delete scheduled jobs by ID or name, or pipe scheduled jobs from Get-ScheduledJob to **Unregister-ScheduledJob** .</span></span>

<span data-ttu-id="03dcd-117">**Unregister-ScheduledJob** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="03dcd-117">**Unregister-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="03dcd-118">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="03dcd-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="03dcd-119">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="03dcd-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="03dcd-120">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="03dcd-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="03dcd-121">示例</span><span class="sxs-lookup"><span data-stu-id="03dcd-121">EXAMPLES</span></span>

### <span data-ttu-id="03dcd-122">示例 1：删除计划作业</span><span class="sxs-lookup"><span data-stu-id="03dcd-122">Example 1: Delete a scheduled job</span></span>

```
PS C:\> Unregister-ScheduledJob TestJob
```

<span data-ttu-id="03dcd-123">此命令删除本地计算机上的 TestJob 计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-123">This command deletes the TestJob scheduled job on the local computer.</span></span>

### <span data-ttu-id="03dcd-124">示例 2：删除所有计划作业</span><span class="sxs-lookup"><span data-stu-id="03dcd-124">Example 2: Delete all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

<span data-ttu-id="03dcd-125">此示例显示删除本地计算机上所有计划作业的两个不同命令。</span><span class="sxs-lookup"><span data-stu-id="03dcd-125">This example shows two different commands that delete all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="03dcd-126">第一个命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-126">The first command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="03dcd-127">管道运算符 (|) 将计划作业发送到 **Unregister-ScheduleJob** ，它将删除这些作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-127">A pipeline operator (|) sends the scheduled jobs to **Unregister-ScheduleJob** , which deletes them.</span></span>

<span data-ttu-id="03dcd-128">第二个命令使用具有所有 (\*) 的值的 *Unregister-ScheduledJob* 的 **Name** 参数来删除所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-128">The second command uses the *Name* parameter of **Unregister-ScheduledJob** with a value of all (\*) to delete all scheduled jobs.</span></span>

<span data-ttu-id="03dcd-129">这两个命令都使用 *Force* 参数，该参数可删除计划作业，即使该作业的实例正在运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="03dcd-129">Both commands use the *Force* parameter, which deletes a scheduled job even if an instance of the job is running.</span></span>

### <span data-ttu-id="03dcd-130">示例 3：删除远程计算机上的计划作业</span><span class="sxs-lookup"><span data-stu-id="03dcd-130">Example 3: Delete a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

<span data-ttu-id="03dcd-131">此命令将删除 Server01 远程计算机上以 Test 开头的名称的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-131">This command deletes scheduled jobs with names that begin with Test on the Server01 remote computer.</span></span>
<span data-ttu-id="03dcd-132">此命令使用 Invoke-Command cmdlet 在 Server02 计算机上运行 **Unregister-ScheduledJob** 命令。</span><span class="sxs-lookup"><span data-stu-id="03dcd-132">The command uses the Invoke-Command cmdlet to run the **Unregister-ScheduledJob** command on the Server02 computer.</span></span>

## <span data-ttu-id="03dcd-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03dcd-133">PARAMETERS</span></span>

### <span data-ttu-id="03dcd-134">-Force</span><span class="sxs-lookup"><span data-stu-id="03dcd-134">-Force</span></span>
<span data-ttu-id="03dcd-135">删除计划作业，即使该作业的实例正在运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="03dcd-135">Deletes the scheduled job even if an instance of the job is running.</span></span>
<span data-ttu-id="03dcd-136">默认情况下， **Unregister-ScheduledJob** 不会中断正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-136">By default, **Unregister-ScheduledJob** does not interrupt running jobs.</span></span>

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

### <span data-ttu-id="03dcd-137">-Id</span><span class="sxs-lookup"><span data-stu-id="03dcd-137">-Id</span></span>
<span data-ttu-id="03dcd-138">删除具有指定标识号 (ID) 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-138">Deletes the scheduled jobs with the specified identification numbers (ID).</span></span>
<span data-ttu-id="03dcd-139">在计算机上输入计划作业的 ID。</span><span class="sxs-lookup"><span data-stu-id="03dcd-139">Enter the IDs of scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03dcd-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="03dcd-140">-InputObject</span></span>
<span data-ttu-id="03dcd-141">指定计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-141">Specifies a scheduled job.</span></span>
<span data-ttu-id="03dcd-142">请输入包含 **ScheduledJob** 对象的变量，或者键入获取 **ScheduledJob** 对象的命令或表达式，例如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="03dcd-142">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="03dcd-143">还可以通过管道将 **ScheduledJob** 对象传递给 **Unregister-JobTrigger** 。</span><span class="sxs-lookup"><span data-stu-id="03dcd-143">You can also pipe **ScheduledJob** objects to **Unregister-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="03dcd-144">-Name</span><span class="sxs-lookup"><span data-stu-id="03dcd-144">-Name</span></span>
<span data-ttu-id="03dcd-145">删除具有指定名称的计划作业。</span><span class="sxs-lookup"><span data-stu-id="03dcd-145">Deletes the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="03dcd-146">在计算机上输入一个或多个计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="03dcd-146">Enter the names of one or more scheduled jobs on the computer.</span></span>
<span data-ttu-id="03dcd-147">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="03dcd-147">Wildcards are supported.</span></span>

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

### <span data-ttu-id="03dcd-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="03dcd-148">-Confirm</span></span>
<span data-ttu-id="03dcd-149">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="03dcd-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="03dcd-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="03dcd-150">-WhatIf</span></span>
<span data-ttu-id="03dcd-151">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="03dcd-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="03dcd-152">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="03dcd-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="03dcd-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03dcd-153">CommonParameters</span></span>
<span data-ttu-id="03dcd-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="03dcd-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03dcd-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="03dcd-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03dcd-156">输入</span><span class="sxs-lookup"><span data-stu-id="03dcd-156">INPUTS</span></span>

### <span data-ttu-id="03dcd-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="03dcd-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="03dcd-158">你可以通过管道将计划作业传递给 Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-158">You can pipe scheduled jobs to Unregister-ScheduledJob</span></span>

## <span data-ttu-id="03dcd-159">输出</span><span class="sxs-lookup"><span data-stu-id="03dcd-159">OUTPUTS</span></span>

### <span data-ttu-id="03dcd-160">无</span><span class="sxs-lookup"><span data-stu-id="03dcd-160">None</span></span>
<span data-ttu-id="03dcd-161">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="03dcd-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="03dcd-162">注释</span><span class="sxs-lookup"><span data-stu-id="03dcd-162">NOTES</span></span>

## <span data-ttu-id="03dcd-163">相关链接</span><span class="sxs-lookup"><span data-stu-id="03dcd-163">RELATED LINKS</span></span>

[<span data-ttu-id="03dcd-164">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-164">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="03dcd-165">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-165">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="03dcd-166">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-166">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="03dcd-167">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-167">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="03dcd-168">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-168">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="03dcd-169">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-169">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="03dcd-170">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-170">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="03dcd-171">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="03dcd-171">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="03dcd-172">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-172">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="03dcd-173">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="03dcd-173">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="03dcd-174">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-174">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="03dcd-175">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-175">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="03dcd-176">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="03dcd-176">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="03dcd-177">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-177">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="03dcd-178">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="03dcd-178">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="03dcd-179">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="03dcd-179">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
