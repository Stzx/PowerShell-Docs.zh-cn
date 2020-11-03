---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197799"
---
# <span data-ttu-id="2d62c-103">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-103">Disable-ScheduledJob</span></span>

## <span data-ttu-id="2d62c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2d62c-104">SYNOPSIS</span></span>
<span data-ttu-id="2d62c-105">禁用计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-105">Disables a scheduled job.</span></span>

## <span data-ttu-id="2d62c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d62c-106">SYNTAX</span></span>

### <span data-ttu-id="2d62c-107">Definition（默认值）</span><span class="sxs-lookup"><span data-stu-id="2d62c-107">Definition (Default)</span></span>

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2d62c-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="2d62c-108">DefinitionId</span></span>

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2d62c-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="2d62c-109">DefinitionName</span></span>

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2d62c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d62c-110">DESCRIPTION</span></span>
<span data-ttu-id="2d62c-111">**Disable-ScheduledJob** cmdlet 可临时禁用计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-111">The **Disable-ScheduledJob** cmdlet temporarily disables scheduled jobs.</span></span>
<span data-ttu-id="2d62c-112">该禁用操作会保留所有作业属性且不禁用作业触发器，但它会在触发计划作业后阻止这些作业自动启动。</span><span class="sxs-lookup"><span data-stu-id="2d62c-112">Disabling preserves all job properties and does not disable the job triggers, but it prevents the scheduled jobs from starting automatically when triggered.</span></span>
<span data-ttu-id="2d62c-113">可使用 Start-Job cmdlet 启动禁用计划作业，或可将禁用计划作业用作模板。</span><span class="sxs-lookup"><span data-stu-id="2d62c-113">You can start a disabled scheduled job by using the Start-Job cmdlet or use a disabled scheduled job as a template.</span></span>

<span data-ttu-id="2d62c-114">若要禁用某个计划作业， **Disable-ScheduledJob** cmdlet 会将该计划作业的 **Enabled** 属性设置为 False ($false)。</span><span class="sxs-lookup"><span data-stu-id="2d62c-114">To disable a scheduled job, the **Disable-ScheduledJob** cmdlet sets the **Enabled** property of the scheduled job to False ($false).</span></span>
<span data-ttu-id="2d62c-115">若要重新启用计划作业，请使用 Enable-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2d62c-115">To re-enable the scheduled job, use the Enable-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="2d62c-116">**Disable-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="2d62c-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="2d62c-117">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="2d62c-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="2d62c-118">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="2d62c-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="2d62c-119">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2d62c-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="2d62c-120">示例</span><span class="sxs-lookup"><span data-stu-id="2d62c-120">EXAMPLES</span></span>

### <span data-ttu-id="2d62c-121">示例 1：禁用计划作业</span><span class="sxs-lookup"><span data-stu-id="2d62c-121">Example 1: Disable a scheduled job</span></span>

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

<span data-ttu-id="2d62c-122">此命令禁用本地计算机上的具有 ID 2 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-122">This command disables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="2d62c-123">此输出显示了该命令的作用。</span><span class="sxs-lookup"><span data-stu-id="2d62c-123">The output shows the effect of the command.</span></span>

### <span data-ttu-id="2d62c-124">示例 2：禁用所有计划作业</span><span class="sxs-lookup"><span data-stu-id="2d62c-124">Example 2: Disable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

<span data-ttu-id="2d62c-125">此命令禁用本地计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-125">This command disables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="2d62c-126">将使用 Get-ScheduledJob cmdlet 获取所有计划作业，并使用 **Disable-ScheduledJob** cmdlet 将其禁用。</span><span class="sxs-lookup"><span data-stu-id="2d62c-126">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Disable-ScheduledJob** cmdlet to disable them.</span></span>

<span data-ttu-id="2d62c-127">可使用 Enable-ScheduledJob cmdlet 重新启用计划作业，并使用 Start-Job cmdlet 运行禁用计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-127">You can re-enable scheduled job by using the Enable-ScheduledJob cmdlet and run a disabled scheduled job by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="2d62c-128">**Disable-ScheduledJob** 不会在禁用已禁用的计划作业时生成警告或错误，因此可以无条件地禁用所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-128">**Disable-ScheduledJob** does not generate warnings or errors if you disable a scheduled job that is already disabled, so you can disable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="2d62c-129">示例 3：禁用选定的计划作业</span><span class="sxs-lookup"><span data-stu-id="2d62c-129">Example 3: Disable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

<span data-ttu-id="2d62c-130">此命令禁用不包含凭据的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-130">This command disables scheduled job do not include a credential.</span></span>
<span data-ttu-id="2d62c-131">对于不具有凭据的作业，可使用创建它们的用户的权限进行运行。</span><span class="sxs-lookup"><span data-stu-id="2d62c-131">Jobs without credentials run with the permission of the user who created them.</span></span>

<span data-ttu-id="2d62c-132">此命令使用 Get-ScheduledJob cmdlet 获取计算机上的所有计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-132">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="2d62c-133">管道运算符将计划作业发送到 Where-Object cmdlet，此 cmdlet 可选择没有凭据的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-133">A pipeline operator sends the scheduled jobs to the Where-Object cmdlet, which selects scheduled jobs that do not have credentials.</span></span>
<span data-ttu-id="2d62c-134">此命令使用 not (!) 运算符并引用计划作业的 Credential 属性。</span><span class="sxs-lookup"><span data-stu-id="2d62c-134">The command uses the not (!) operator and references the Credential property of the scheduled job.</span></span>
<span data-ttu-id="2d62c-135">另一个管道运算符将选定的计划作业发送到 **Disable-ScheduledJob** cmdlet，此 cmdlet 可禁用这些作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-135">Another pipeline operator sends the selected scheduled jobs to the **Disable-ScheduledJob** cmdlet, which disables them.</span></span>

### <span data-ttu-id="2d62c-136">示例 4：禁用远程计算机上的计划作业</span><span class="sxs-lookup"><span data-stu-id="2d62c-136">Example 4: Disable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

<span data-ttu-id="2d62c-137">此命令禁用 Srv01 和 Srv10 这两台远程计算机上的 TestJob 计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-137">This command disables the TestJob scheduled job on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="2d62c-138">此命令使用 Invoke-Command cmdlet 在 Srv01 和 Srv10 计算机上运行 **Disable-ScheduledJob** 命令。</span><span class="sxs-lookup"><span data-stu-id="2d62c-138">The command uses the Invoke-Command cmdlet to run a **Disable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="2d62c-139">此命令使用 *Disable-ScheduledJob* 的 **Name** 参数，以在每台计算机上选择 TestJob 计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-139">The command uses the *Name* parameter of **Disable-ScheduledJob** to select the TestJob scheduled job on each computer.</span></span>

### <span data-ttu-id="2d62c-140">示例 5：通过计划作业的全局 ID 对其进行禁用</span><span class="sxs-lookup"><span data-stu-id="2d62c-140">Example 5: Disable a scheduled job by its global ID</span></span>

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

<span data-ttu-id="2d62c-141">此示例显示了如何通过使用计划作业的全局标识符对其进行禁用。</span><span class="sxs-lookup"><span data-stu-id="2d62c-141">This examples shows how to disable a scheduled job by using its global identifier.</span></span>
<span data-ttu-id="2d62c-142">计划作业的 GlobalID 属性值是唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="2d62c-142">The value of the GlobalID property of a scheduled job is a unique identifier (GUID).</span></span>
<span data-ttu-id="2d62c-143">当需要使用精度时（例如，禁用多台计算机上的计划作业时），可使用 GlobalID 值。</span><span class="sxs-lookup"><span data-stu-id="2d62c-143">Use the GlobalID value when precision is required, such as when you are disabling scheduled jobs on multiple computers.</span></span>

## <span data-ttu-id="2d62c-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d62c-144">PARAMETERS</span></span>

### <span data-ttu-id="2d62c-145">-Id</span><span class="sxs-lookup"><span data-stu-id="2d62c-145">-Id</span></span>
<span data-ttu-id="2d62c-146">禁用具有指定标识号 (ID) 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-146">Disables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="2d62c-147">输入计划作业的 ID。</span><span class="sxs-lookup"><span data-stu-id="2d62c-147">Enter the ID of a scheduled job.</span></span>

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

### <span data-ttu-id="2d62c-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2d62c-148">-InputObject</span></span>
<span data-ttu-id="2d62c-149">指定要禁用的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-149">Specifies the scheduled job to be disabled.</span></span>
<span data-ttu-id="2d62c-150">请输入包含 **ScheduledJobDefinition** 对象的变量，或者键入获取 **ScheduledJobDefinition** 对象的命令或表达式，例如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="2d62c-150">Enter a variable that contains  **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="2d62c-151">还可以通过管道将 **ScheduledJobDefinition** 对象传递给 **Disable-ScheduledJob** 。</span><span class="sxs-lookup"><span data-stu-id="2d62c-151">You can also pipe a **ScheduledJobDefinition** object to **Disable-ScheduledJob** .</span></span>

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

### <span data-ttu-id="2d62c-152">-Name</span><span class="sxs-lookup"><span data-stu-id="2d62c-152">-Name</span></span>
<span data-ttu-id="2d62c-153">禁用具有指定名称的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-153">Disables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="2d62c-154">输入计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="2d62c-154">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="2d62c-155">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="2d62c-155">Wildcards are supported.</span></span>

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

### <span data-ttu-id="2d62c-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2d62c-156">-PassThru</span></span>
<span data-ttu-id="2d62c-157">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="2d62c-157">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="2d62c-158">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="2d62c-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2d62c-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2d62c-159">-Confirm</span></span>
<span data-ttu-id="2d62c-160">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="2d62c-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2d62c-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2d62c-161">-WhatIf</span></span>
<span data-ttu-id="2d62c-162">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="2d62c-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2d62c-163">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2d62c-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2d62c-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2d62c-164">CommonParameters</span></span>
<span data-ttu-id="2d62c-165">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2d62c-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d62c-166">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2d62c-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d62c-167">输入</span><span class="sxs-lookup"><span data-stu-id="2d62c-167">INPUTS</span></span>

### <span data-ttu-id="2d62c-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="2d62c-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="2d62c-169">你可以通过管道将计划作业传递给 **Disable-ScheduledJob** 。</span><span class="sxs-lookup"><span data-stu-id="2d62c-169">You can pipe a scheduled job to **Disable-ScheduledJob** .</span></span>

## <span data-ttu-id="2d62c-170">输出</span><span class="sxs-lookup"><span data-stu-id="2d62c-170">OUTPUTS</span></span>

### <span data-ttu-id="2d62c-171">无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="2d62c-171">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="2d62c-172">如果你使用 **Passthru** 参数，则 **Disable-ScheduledJob** 将返回已禁用的计划作业。</span><span class="sxs-lookup"><span data-stu-id="2d62c-172">If you use the **Passthru** parameter, **Disable-ScheduledJob** returns the scheduled job that was disabled.</span></span>
<span data-ttu-id="2d62c-173">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="2d62c-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2d62c-174">注释</span><span class="sxs-lookup"><span data-stu-id="2d62c-174">NOTES</span></span>

* <span data-ttu-id="2d62c-175">**Disable-ScheduledJob** 不会在禁用已禁用的计划作业时生成警告或错误。</span><span class="sxs-lookup"><span data-stu-id="2d62c-175">**Disable-ScheduledJob** does not generate warnings or errors if you use it to disable a scheduled job that is already disabled.</span></span>

## <span data-ttu-id="2d62c-176">相关链接</span><span class="sxs-lookup"><span data-stu-id="2d62c-176">RELATED LINKS</span></span>

[<span data-ttu-id="2d62c-177">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-177">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="2d62c-178">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-178">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="2d62c-179">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-179">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="2d62c-180">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-180">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="2d62c-181">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-181">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="2d62c-182">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-182">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="2d62c-183">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-183">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="2d62c-184">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="2d62c-184">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="2d62c-185">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-185">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="2d62c-186">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="2d62c-186">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="2d62c-187">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-187">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="2d62c-188">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-188">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="2d62c-189">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2d62c-189">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="2d62c-190">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-190">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="2d62c-191">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="2d62c-191">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="2d62c-192">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2d62c-192">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
