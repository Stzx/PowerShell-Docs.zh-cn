---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197787"
---
# <span data-ttu-id="285d7-103">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="285d7-103">Get-ScheduledJobOption</span></span>

## <span data-ttu-id="285d7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="285d7-104">SYNOPSIS</span></span>
<span data-ttu-id="285d7-105">获取计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-105">Gets the job options of scheduled jobs.</span></span>

## <span data-ttu-id="285d7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="285d7-106">SYNTAX</span></span>

### <span data-ttu-id="285d7-107">JobDefinition（默认值）</span><span class="sxs-lookup"><span data-stu-id="285d7-107">JobDefinition (Default)</span></span>

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="285d7-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="285d7-108">JobDefinitionId</span></span>

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="285d7-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="285d7-109">JobDefinitionName</span></span>

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="285d7-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="285d7-110">DESCRIPTION</span></span>
<span data-ttu-id="285d7-111">**Get-scheduledjoboption** cmdlet 获取计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-111">The **Get-ScheduledJobOption** cmdlet gets the job options of scheduled jobs.</span></span>
<span data-ttu-id="285d7-112">你可以使用此命令检查作业选项或通过管道将其传递给其他 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="285d7-112">You can use this command to examine the job options or to pipe the job options to other cmdlets.</span></span>

<span data-ttu-id="285d7-113">不会单独将作业选项保存到磁盘，因为它们是计划作业的一部分。</span><span class="sxs-lookup"><span data-stu-id="285d7-113">Job options are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="285d7-114">若要获取某个计划作业的作业选项，请指定该计划作业。</span><span class="sxs-lookup"><span data-stu-id="285d7-114">To get the job options of a scheduled job, specify the scheduled job.</span></span>

<span data-ttu-id="285d7-115">使用 **Get-ScheduledJobOption** cmdlet 的参数来标识计划作业。</span><span class="sxs-lookup"><span data-stu-id="285d7-115">Use the parameters of the **Get-ScheduledJobOption** cmdlet to identify the scheduled job.</span></span>
<span data-ttu-id="285d7-116">可以通过其名称或标识号来识别计划作业，或者通过将 **get-scheduledjob** 对象（如 Get-ScheduledJob cmdlet 返回的对象）输入或管道传递给 **get-scheduledjoboption** 。</span><span class="sxs-lookup"><span data-stu-id="285d7-116">You can identify scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-ScheduledJobOption** .</span></span>

<span data-ttu-id="285d7-117">**Get-ScheduledJobOption** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="285d7-117">**Get-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="285d7-118">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="285d7-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="285d7-119">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="285d7-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="285d7-120">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="285d7-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="285d7-121">示例</span><span class="sxs-lookup"><span data-stu-id="285d7-121">EXAMPLES</span></span>

### <span data-ttu-id="285d7-122">示例 1：获取作业选项</span><span class="sxs-lookup"><span data-stu-id="285d7-122">Example 1: Get job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="285d7-123">此命令获取其名称中有备份的计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-123">This command gets the job options of scheduled jobs that have BackUp in their names.</span></span>
<span data-ttu-id="285d7-124">结果将显示 **Get-ScheduledJobOption** 返回的作业选项对象。</span><span class="sxs-lookup"><span data-stu-id="285d7-124">The results show the job options object that **Get-ScheduledJobOption** returned.</span></span>

### <span data-ttu-id="285d7-125">示例 2：获取所有作业选项</span><span class="sxs-lookup"><span data-stu-id="285d7-125">Example 2: Get all job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

<span data-ttu-id="285d7-126">此命令获取本地计算机上的所有计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-126">This command gets the job options of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="285d7-127">此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。</span><span class="sxs-lookup"><span data-stu-id="285d7-127">It uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="285d7-128">管道运算符 (|) 将计划作业发送到 **get-scheduledjoboption** cmdlet，此 cmdlet 可获取每个计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-128">A pipeline operator (|) sends the scheduled jobs to the **Get-ScheduledJobOption** cmdlet, which gets the job options of each scheduled job.</span></span>

### <span data-ttu-id="285d7-129">示例 3：获取选定的作业选项</span><span class="sxs-lookup"><span data-stu-id="285d7-129">Example 3: Get selected job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

<span data-ttu-id="285d7-130">此示例显示了如何使用特定值查找作业选项对象。</span><span class="sxs-lookup"><span data-stu-id="285d7-130">This example shows how to find job options object with particular values.</span></span>

<span data-ttu-id="285d7-131">第一个命令获取 RunElevated 属性值为 $True，RunWithoutNetwork 属性值为 $False 的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-131">The first command gets job options in which the RunElevated property has a value of $True and the RunWithoutNetwork property has a value of $False.</span></span>
<span data-ttu-id="285d7-132">输出显示选定的 **JobOptions** 对象。</span><span class="sxs-lookup"><span data-stu-id="285d7-132">The output shows the **JobOptions** object that was selected.</span></span>

### <span data-ttu-id="285d7-133">示例 4：使用作业选项创建新作业</span><span class="sxs-lookup"><span data-stu-id="285d7-133">Example 4: Use job options to create a new job</span></span>

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

<span data-ttu-id="285d7-134">此示例演示如何使用 Get-ScheduledJobOption 在新的计划作业中获取的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-134">This example shows how to use the job options that Get-ScheduledJobOption gets in a new scheduled job.</span></span>

<span data-ttu-id="285d7-135">第一个命令使用 **get-scheduledjoboption** 获取 BackupTestLogs 计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-135">The first command uses **Get-ScheduledJobOption** to get the jobs options of the BackupTestLogs scheduled job.</span></span>
<span data-ttu-id="285d7-136">此命令将这些选项保存在 $Opts 变量中。</span><span class="sxs-lookup"><span data-stu-id="285d7-136">The command saves the options in the $Opts variable.</span></span>

<span data-ttu-id="285d7-137">第二个命令使用 Register-ScheduledJob cmdlet 创建新的计划作业。</span><span class="sxs-lookup"><span data-stu-id="285d7-137">The second command uses Register-ScheduledJob cmdlet to create a new scheduled job.</span></span>
<span data-ttu-id="285d7-138">*ScheduledJobOption* 参数的值是 $Opts 变量中的选项对象。</span><span class="sxs-lookup"><span data-stu-id="285d7-138">The value of the *ScheduledJobOption* parameter is the options object in the $Opts variable.</span></span>

### <span data-ttu-id="285d7-139">示例 5：从远程计算机获取作业选项</span><span class="sxs-lookup"><span data-stu-id="285d7-139">Example 5: Get job options from a remote computer</span></span>

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

<span data-ttu-id="285d7-140">此命令使用 Invoke-Command cmdlet 获取 Srv01 计算机上的 DataDemon 作业的计划作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-140">This command uses the Invoke-Command cmdlet to get the scheduled job options of the DataDemon job on the Srv01 computer.</span></span>
<span data-ttu-id="285d7-141">该命令将选项保存在 $O 变量中。</span><span class="sxs-lookup"><span data-stu-id="285d7-141">The command saves the options in the $O variable.</span></span>

## <span data-ttu-id="285d7-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="285d7-142">PARAMETERS</span></span>

### <span data-ttu-id="285d7-143">-Id</span><span class="sxs-lookup"><span data-stu-id="285d7-143">-Id</span></span>
<span data-ttu-id="285d7-144">指定计划作业的标识号。</span><span class="sxs-lookup"><span data-stu-id="285d7-144">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="285d7-145">**Get-ScheduledJobOption** 可获取指定的计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-145">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>

<span data-ttu-id="285d7-146">若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="285d7-146">To get the identification numbers of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="285d7-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="285d7-147">-InputObject</span></span>
<span data-ttu-id="285d7-148">指定计划作业。</span><span class="sxs-lookup"><span data-stu-id="285d7-148">Specifies a scheduled job.</span></span>
<span data-ttu-id="285d7-149">请输入包含 **ScheduledJob** 对象的变量，或者键入获取 **ScheduledJob** 对象的命令或表达式，例如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="285d7-149">Enter a variable that contains a **ScheduledJob** object or type a command or expression that gets a **ScheduledJob** object, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="285d7-150">还可以通过管道将 **ScheduledJob** 对象传递给 **Get-ScheduledJobOption** 。</span><span class="sxs-lookup"><span data-stu-id="285d7-150">You can also pipe a **ScheduledJob** object to **Get-ScheduledJobOption** .</span></span>

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

### <span data-ttu-id="285d7-151">-Name</span><span class="sxs-lookup"><span data-stu-id="285d7-151">-Name</span></span>
<span data-ttu-id="285d7-152">指定计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="285d7-152">Specifies the names of scheduled jobs.</span></span>
<span data-ttu-id="285d7-153">**Get-ScheduledJobOption** 可获取指定的计划作业的作业选项。</span><span class="sxs-lookup"><span data-stu-id="285d7-153">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>
<span data-ttu-id="285d7-154">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="285d7-154">Wildcards are supported.</span></span>

<span data-ttu-id="285d7-155">若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="285d7-155">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="285d7-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="285d7-156">CommonParameters</span></span>
<span data-ttu-id="285d7-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="285d7-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="285d7-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="285d7-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="285d7-159">输入</span><span class="sxs-lookup"><span data-stu-id="285d7-159">INPUTS</span></span>

### <span data-ttu-id="285d7-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="285d7-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="285d7-161">可以通过管道将计划作业从 Get-ScheduledJob 传递到 **Get-ScheduledJobOption** 。</span><span class="sxs-lookup"><span data-stu-id="285d7-161">You can pipe a scheduled job from Get-ScheduledJob to **Get-ScheduledJobOption** .</span></span>

## <span data-ttu-id="285d7-162">输出</span><span class="sxs-lookup"><span data-stu-id="285d7-162">OUTPUTS</span></span>

### <span data-ttu-id="285d7-163">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="285d7-163">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="285d7-164">注释</span><span class="sxs-lookup"><span data-stu-id="285d7-164">NOTES</span></span>

## <span data-ttu-id="285d7-165">相关链接</span><span class="sxs-lookup"><span data-stu-id="285d7-165">RELATED LINKS</span></span>

[<span data-ttu-id="285d7-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="285d7-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="285d7-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="285d7-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="285d7-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="285d7-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="285d7-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="285d7-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="285d7-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="285d7-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="285d7-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="285d7-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="285d7-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="285d7-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="285d7-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="285d7-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="285d7-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="285d7-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="285d7-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="285d7-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="285d7-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="285d7-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="285d7-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="285d7-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="285d7-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="285d7-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
