---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197792"
---
# <span data-ttu-id="d907e-103">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-103">Enable-ScheduledJob</span></span>

## <span data-ttu-id="d907e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d907e-104">SYNOPSIS</span></span>
<span data-ttu-id="d907e-105">启用计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-105">Enables a scheduled job.</span></span>

## <span data-ttu-id="d907e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d907e-106">SYNTAX</span></span>

### <span data-ttu-id="d907e-107">Definition（默认值）</span><span class="sxs-lookup"><span data-stu-id="d907e-107">Definition (Default)</span></span>

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="d907e-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="d907e-108">DefinitionId</span></span>

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d907e-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="d907e-109">DefinitionName</span></span>

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d907e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d907e-110">DESCRIPTION</span></span>
<span data-ttu-id="d907e-111">**Get-scheduledjob** cmdlet 可重新启用已禁用的计划作业，例如通过使用 Disable-ScheduledJob cmdlet 禁用的作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-111">The **Enable-ScheduledJob** cmdlet re-enables scheduled jobs that are disabled, such as those that are disabled by using the Disable-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="d907e-112">触发作业后，它们将自动运行。</span><span class="sxs-lookup"><span data-stu-id="d907e-112">Enabled jobs run automatically when triggered.</span></span>

<span data-ttu-id="d907e-113">若要启用某个计划作业， **get-scheduledjob** cmdlet 会将该计划作业的 Enabled 属性设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="d907e-113">To enable a scheduled job, the **Enable-ScheduledJob** cmdlet sets the Enabled property of the scheduled job to $True.</span></span>

<span data-ttu-id="d907e-114">**Enabled-get-scheduledjob** 是 Windows PowerShell 中包含的 **PSScheduledJob** 模块中的作业计划 cmdlet 集合之一。</span><span class="sxs-lookup"><span data-stu-id="d907e-114">**Enabled-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="d907e-115">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="d907e-115">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="d907e-116">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="d907e-116">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="d907e-117">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d907e-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d907e-118">示例</span><span class="sxs-lookup"><span data-stu-id="d907e-118">EXAMPLES</span></span>

### <span data-ttu-id="d907e-119">示例1：启用计划作业</span><span class="sxs-lookup"><span data-stu-id="d907e-119">Example 1: Enable a scheduled job</span></span>

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

<span data-ttu-id="d907e-120">此命令启动本地计算机上的具有 ID 2 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-120">This command enables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="d907e-121">此输出显示了该命令的作用。</span><span class="sxs-lookup"><span data-stu-id="d907e-121">The output shows the effect of the command.</span></span>

### <span data-ttu-id="d907e-122">示例2：启用所有计划作业</span><span class="sxs-lookup"><span data-stu-id="d907e-122">Example 2: Enable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

<span data-ttu-id="d907e-123">此命令启用本地计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-123">This command enables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="d907e-124">它使用 Get-ScheduledJob cmdlet 获取所有计划作业，并使用 **get-scheduledjob** cmdlet 来启用它们。</span><span class="sxs-lookup"><span data-stu-id="d907e-124">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Enable-ScheduledJob** cmdlet to enable them.</span></span>

<span data-ttu-id="d907e-125">如果启用已启用的计划作业，则 **get-scheduledjob** 不会生成警告或错误，因此你可以在不使用条件的情况下启用所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-125">**Enable-ScheduledJob** does not generate warnings or errors if you enable a scheduled job that is already enabled, so you can enable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="d907e-126">示例3：启用选定的计划作业</span><span class="sxs-lookup"><span data-stu-id="d907e-126">Example 3: Enable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

<span data-ttu-id="d907e-127">此命令启用不需要网络连接的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-127">This command enables scheduled jobs that do not require a network connection.</span></span>

<span data-ttu-id="d907e-128">此命令使用 Get-ScheduledJob cmdlet 获取计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-128">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="d907e-129">管道运算符将计划作业发送到 Get-ScheduledJobOption cmdlet，该 cmdlet 可获取每个计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="d907e-129">A pipeline operator sends the scheduled jobs to the Get-ScheduledJobOption cmdlet, which gets the job options of each scheduled job.</span></span>
<span data-ttu-id="d907e-130">每个作业选项对象都具有一个 JobDefinition 属性，该属性包含关联的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-130">Each job options object has a JobDefinition property that contains the associated scheduled job.</span></span>
<span data-ttu-id="d907e-131">JobDefinition 属性用于完成此命令。</span><span class="sxs-lookup"><span data-stu-id="d907e-131">The JobDefinition property is used to complete the command.</span></span>

<span data-ttu-id="d907e-132">该命令使用管道运算符 (|) 将作业选项发送到 Where-Object cmdlet，后者将选择计划作业选项对象，其中 **RunWithoutNetwork** 属性的值为 True ($true) 。</span><span class="sxs-lookup"><span data-stu-id="d907e-132">The command uses a pipeline operator (|) to send the job options to the Where-Object cmdlet, which selects scheduled job option objects in which the **RunWithoutNetwork** property has a value of True ($true).</span></span>
<span data-ttu-id="d907e-133">另一个管道运算符将选定的计划作业选项对象发送到 ForEach-Object cmdlet，该 cmdlet 在计划作业的每个作业选项对象的 JobDefinition 属性值中运行 **get-scheduledjob** 命令。</span><span class="sxs-lookup"><span data-stu-id="d907e-133">Another pipeline operator sends the selected scheduled job options objects to the ForEach-Object cmdlet which runs an **Enable-ScheduledJob** command on the scheduled job in the value of the JobDefinition property of each job options object.</span></span>

### <span data-ttu-id="d907e-134">示例4：启用远程计算机上的计划作业</span><span class="sxs-lookup"><span data-stu-id="d907e-134">Example 4: Enable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

<span data-ttu-id="d907e-135">此命令启用两台远程计算机（Srv01 和 Srv10）上其名称中含有“test”的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-135">This command enables scheduled jobs that have "test" in their names on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="d907e-136">该命令使用 Invoke-Command cmdlet 在 Srv01 和 Srv10 计算机上运行 **get-scheduledjob** 命令。</span><span class="sxs-lookup"><span data-stu-id="d907e-136">The command uses the Invoke-Command cmdlet to run an **Enable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="d907e-137">此命令使用 *Enable-ScheduledJob* 的 **Name** 参数，以在每台计算机上启用 Inventory 计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-137">The command uses the *Name* parameter of **Enable-ScheduledJob** to enable the Inventory scheduled job on each computer.</span></span>

## <span data-ttu-id="d907e-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d907e-138">PARAMETERS</span></span>

### <span data-ttu-id="d907e-139">-Id</span><span class="sxs-lookup"><span data-stu-id="d907e-139">-Id</span></span>
<span data-ttu-id="d907e-140">启用具有指定标识号 (ID) 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-140">Enables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="d907e-141">输入计划作业的 ID。</span><span class="sxs-lookup"><span data-stu-id="d907e-141">Enter the ID of a scheduled job.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d907e-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d907e-142">-InputObject</span></span>
<span data-ttu-id="d907e-143">指定要启用的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-143">Specifies the scheduled job to enable.</span></span>
<span data-ttu-id="d907e-144">输入包含 **ScheduledJobDefinition** 对象的变量，或者键入获取 **ScheduledJobDefinition** 对象的命令或表达式，如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="d907e-144">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="d907e-145">还可以通过管道将 **ScheduledJobDefinition** 对象传递给 **get-scheduledjob** 。</span><span class="sxs-lookup"><span data-stu-id="d907e-145">You can also pipe a **ScheduledJobDefinition** object to **Enable-ScheduledJob** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d907e-146">-Name</span><span class="sxs-lookup"><span data-stu-id="d907e-146">-Name</span></span>
<span data-ttu-id="d907e-147">启用具有指定名称的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-147">Enables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="d907e-148">输入计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="d907e-148">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="d907e-149">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="d907e-149">Wildcards are supported.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d907e-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d907e-150">-PassThru</span></span>
<span data-ttu-id="d907e-151">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="d907e-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="d907e-152">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="d907e-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d907e-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d907e-153">-Confirm</span></span>
<span data-ttu-id="d907e-154">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="d907e-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d907e-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d907e-155">-WhatIf</span></span>
<span data-ttu-id="d907e-156">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d907e-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d907e-157">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="d907e-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d907e-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d907e-158">CommonParameters</span></span>
<span data-ttu-id="d907e-159">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d907e-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d907e-160">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d907e-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d907e-161">输入</span><span class="sxs-lookup"><span data-stu-id="d907e-161">INPUTS</span></span>

### <span data-ttu-id="d907e-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="d907e-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="d907e-163">可以通过管道将计划作业传递给 **get-scheduledjob** 。</span><span class="sxs-lookup"><span data-stu-id="d907e-163">You can pipe a scheduled job to **Enable-ScheduledJob** .</span></span>

## <span data-ttu-id="d907e-164">输出</span><span class="sxs-lookup"><span data-stu-id="d907e-164">OUTPUTS</span></span>

### <span data-ttu-id="d907e-165">无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="d907e-165">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="d907e-166">如果你使用 **Passthru** 参数，则 **Enable-ScheduledJob** 将返回已启用的计划作业。</span><span class="sxs-lookup"><span data-stu-id="d907e-166">If you use the **Passthru** parameter, **Enable-ScheduledJob** returns the scheduled job that was enabled.</span></span>
<span data-ttu-id="d907e-167">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="d907e-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d907e-168">注释</span><span class="sxs-lookup"><span data-stu-id="d907e-168">NOTES</span></span>

* <span data-ttu-id="d907e-169">如果你使用 **get-scheduledjob** 来启用已启用的计划作业，则它不会生成警告或错误。</span><span class="sxs-lookup"><span data-stu-id="d907e-169">**Enable-ScheduledJob** does not generate warnings or errors if you use it to enable a scheduled job that is already enabled.</span></span>

## <span data-ttu-id="d907e-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="d907e-170">RELATED LINKS</span></span>

[<span data-ttu-id="d907e-171">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-171">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="d907e-172">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-172">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="d907e-173">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-173">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="d907e-174">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-174">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="d907e-175">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-175">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="d907e-176">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-176">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="d907e-177">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-177">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="d907e-178">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d907e-178">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="d907e-179">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-179">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="d907e-180">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d907e-180">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="d907e-181">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-181">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="d907e-182">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-182">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="d907e-183">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d907e-183">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="d907e-184">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-184">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="d907e-185">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d907e-185">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="d907e-186">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d907e-186">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
