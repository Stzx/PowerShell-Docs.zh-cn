---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 9b18782fae77fa0776aa2cfaa39b74a2292099d9
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388458"
---
# <span data-ttu-id="448bb-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-103">Suspend-Job</span></span>

## <span data-ttu-id="448bb-104">摘要</span><span class="sxs-lookup"><span data-stu-id="448bb-104">SYNOPSIS</span></span>
<span data-ttu-id="448bb-105">暂时停止工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="448bb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="448bb-106">SYNTAX</span></span>

### <span data-ttu-id="448bb-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="448bb-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="448bb-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="448bb-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="448bb-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="448bb-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="448bb-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="448bb-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="448bb-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="448bb-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="448bb-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="448bb-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="448bb-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="448bb-113">DESCRIPTION</span></span>

<span data-ttu-id="448bb-114">`Suspend-Job`Cmdlet 将挂起工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-114">The `Suspend-Job` cmdlet suspends workflow jobs.</span></span> <span data-ttu-id="448bb-115">"挂起" 表示暂时中断或暂停工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span> <span data-ttu-id="448bb-116">此 cmdlet 允许运行工作流的用户挂起该工作流。</span><span class="sxs-lookup"><span data-stu-id="448bb-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span> <span data-ttu-id="448bb-117">它补充挂起工作流 https://go.microsoft.com/fwlink/?LinkId=267141 活动，这是工作流中挂起工作流的命令。</span><span class="sxs-lookup"><span data-stu-id="448bb-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="448bb-118">此 `Suspend-Job` cmdlet 仅适用于工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-118">The `Suspend-Job` cmdlet works only on workflow jobs.</span></span> <span data-ttu-id="448bb-119">它不适用于标准后台作业，如使用 cmdlet 启动的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="448bb-119">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="448bb-120">若要标识工作流作业，请查找该作业的 **PSJobTypeName** 属性中的 PSWorkflowJob 值。</span><span class="sxs-lookup"><span data-stu-id="448bb-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="448bb-121">若要确定某个特定的自定义作业类型是否支持该 `Suspend-Job` cmdlet，请参阅自定义作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="448bb-121">To determine whether a particular custom job type supports the `Suspend-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="448bb-122">挂起工作流作业时，工作流作业将运行到下一个检查点、挂起，然后立即返回一个工作流作业对象。</span><span class="sxs-lookup"><span data-stu-id="448bb-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span> <span data-ttu-id="448bb-123">若要在获取作业之前等待挂起完成，请使用或 cmdlet 的 **wait** 参数 `Suspend-Job` `Wait-Job` 。</span><span class="sxs-lookup"><span data-stu-id="448bb-123">To wait for the suspension to complete before getting the job, use the **Wait** parameter of `Suspend-Job` or the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="448bb-124">挂起工作流作业时，将挂起该作业的 **State** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="448bb-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="448bb-125">能否正确挂起取决于检查点。</span><span class="sxs-lookup"><span data-stu-id="448bb-125">Suspending correctly relies on checkpoints.</span></span> <span data-ttu-id="448bb-126">当前作业状态、元数据和输出都保存在检查点中，因此可以在不丢失状态或数据的情况下恢复工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span> <span data-ttu-id="448bb-127">如果工作流作业不具有检查点，则无法将其正确挂起。</span><span class="sxs-lookup"><span data-stu-id="448bb-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span> <span data-ttu-id="448bb-128">若要向运行中的工作流添加检查点，请使用 **PSPersist** 工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="448bb-128">To add checkpoints to a workflow that you are running, use the **PSPersist** workflow common parameter.</span></span> <span data-ttu-id="448bb-129">您可以使用 **Force** 参数立即挂起任何工作流作业并挂起不具有检查点的工作流作业，但该操作可能会导致状态和数据丢失。</span><span class="sxs-lookup"><span data-stu-id="448bb-129">You can use the **Force** parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="448bb-130">在对自定义作业类型（例如工作流作业 ( **PSWorkflowJob** ）使用作业 cmdlet 之前) 导入支持该自定义作业类型的模块，方法是使用 `Import-Module` cmdlet 或使用模块中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448bb-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the `Import-Module` cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="448bb-131">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="448bb-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="448bb-132">示例</span><span class="sxs-lookup"><span data-stu-id="448bb-132">EXAMPLES</span></span>

### <span data-ttu-id="448bb-133">示例 1：按名称挂起工作流作业</span><span class="sxs-lookup"><span data-stu-id="448bb-133">Example 1: Suspend a workflow job by name</span></span>

<span data-ttu-id="448bb-134">此示例显示了如何挂起工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-134">This example shows how to suspend a workflow job.</span></span>

<span data-ttu-id="448bb-135">第一个命令创建 `Get-SystemLog` 工作流。</span><span class="sxs-lookup"><span data-stu-id="448bb-135">The first command creates the `Get-SystemLog` workflow.</span></span> <span data-ttu-id="448bb-136">工作流使用 `CheckPoint-Workflow` 活动在工作流中定义检查点。</span><span class="sxs-lookup"><span data-stu-id="448bb-136">The workflow uses the `CheckPoint-Workflow` activity to define a checkpoint in the workflow.</span></span>

<span data-ttu-id="448bb-137">第二个命令使用所有工作流通用的 **AsJob** 参数将 `Get-SystemLog` 工作流作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="448bb-137">The second command uses the **AsJob** parameter that is common to all workflows to run the `Get-SystemLog` workflow as a background job.</span></span> <span data-ttu-id="448bb-138">该命令使用 **JobName** 工作流通用参数来指定工作流作业的友好名称。</span><span class="sxs-lookup"><span data-stu-id="448bb-138">The command uses the **JobName** workflow common parameter to specify a friendly name for the workflow job.</span></span>

<span data-ttu-id="448bb-139">第三个命令使用 `Get-Job` cmdlet 来获取 `Get-SystemLogJob` 工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-139">The third command uses the `Get-Job` cmdlet to get the `Get-SystemLogJob` workflow job.</span></span> <span data-ttu-id="448bb-140">输出显示 **PSJobTypeName** 属性的值为 PSWorkflowJob。</span><span class="sxs-lookup"><span data-stu-id="448bb-140">The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.</span></span>

<span data-ttu-id="448bb-141">第四个命令使用 `Suspend-Job` cmdlet 来挂起 `Get-SystemLogJob` 作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-141">The fourth command uses the `Suspend-Job` cmdlet to suspend the `Get-SystemLogJob` job.</span></span> <span data-ttu-id="448bb-142">该作业将运行到检查点，然后挂起。</span><span class="sxs-lookup"><span data-stu-id="448bb-142">The job runs to the checkpoint and then suspends.</span></span>

```
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```


### <span data-ttu-id="448bb-143">示例 2：挂起和恢复工作流作业</span><span class="sxs-lookup"><span data-stu-id="448bb-143">Example 2: Suspend and resume a workflow job</span></span>

<span data-ttu-id="448bb-144">此示例显示了如何挂起和恢复工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-144">This example shows how to suspend and resume a workflow job.</span></span>

<span data-ttu-id="448bb-145">第一个命令挂起 LogWorkflowJob 作业。命令立即返回。</span><span class="sxs-lookup"><span data-stu-id="448bb-145">The first command suspends the LogWorkflowJob job.The command returns immediately.</span></span> <span data-ttu-id="448bb-146">输出显示工作流作业仍在运行，即使正在挂起。</span><span class="sxs-lookup"><span data-stu-id="448bb-146">The output shows that the workflow job is still running, even though it is being suspended.</span></span>

<span data-ttu-id="448bb-147">第二个命令使用 `Get-Job` cmdlet 来获取 LogWorkflowJob 作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-147">The second command uses the `Get-Job` cmdlet to get the LogWorkflowJob job.</span></span> <span data-ttu-id="448bb-148">该输出显示已成功挂起工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-148">The output shows that the workflow job suspended successfully.</span></span>

<span data-ttu-id="448bb-149">第三个命令使用 `Get-Job` cmdlet 来获取 LogWorkflowJob 作业，并使用 `Resume-Job` cmdlet 来恢复该作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-149">The third command uses the `Get-Job` cmdlet to get the LogWorkflowJob job and the `Resume-Job` cmdlet to resume it.</span></span> <span data-ttu-id="448bb-150">该输出显示已成功恢复工作流作业且它现在正在运行中。</span><span class="sxs-lookup"><span data-stu-id="448bb-150">The output shows that the workflow job resumed successfully and is now running.</span></span>

```
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```


### <span data-ttu-id="448bb-151">示例 3：挂起远程计算机上的工作流作业</span><span class="sxs-lookup"><span data-stu-id="448bb-151">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="448bb-152">此命令使用 `Invoke-Command` cmdlet 挂起 Srv01 远程计算机上的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-152">This command uses the `Invoke-Command` cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span> <span data-ttu-id="448bb-153">**Filter** 参数的值是指定 CustomID 值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="448bb-153">The value of the **Filter** parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="448bb-154">此 **CustomID** 是作业元数据 ( **PSPrivateMetadata** )。</span><span class="sxs-lookup"><span data-stu-id="448bb-154">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="448bb-155">示例 4：待工作流作业挂起</span><span class="sxs-lookup"><span data-stu-id="448bb-155">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="448bb-156">此命令将挂起 VersionCheck 工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-156">This command suspends the VersionCheck workflow job.</span></span> <span data-ttu-id="448bb-157">该命令使用 **Wait** 参数等待工作流作业挂起。</span><span class="sxs-lookup"><span data-stu-id="448bb-157">The command uses the **Wait** parameter to wait until the workflow job is suspended.</span></span> <span data-ttu-id="448bb-158">当工作流作业运行到下一个检查点并被挂起时，该命令完成并返回作业对象。</span><span class="sxs-lookup"><span data-stu-id="448bb-158">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="448bb-159">示例 5：强制工作流作业挂起</span><span class="sxs-lookup"><span data-stu-id="448bb-159">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="448bb-160">此命令将强制挂起 Maintenance 工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-160">This command suspends the Maintenance workflow job forcibly.</span></span> <span data-ttu-id="448bb-161">维护作业没有检查点。</span><span class="sxs-lookup"><span data-stu-id="448bb-161">The Maintenance job does not have checkpoints.</span></span> <span data-ttu-id="448bb-162">它无法正确挂起，并且可能无法正确恢复。</span><span class="sxs-lookup"><span data-stu-id="448bb-162">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="448bb-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="448bb-163">PARAMETERS</span></span>

### <span data-ttu-id="448bb-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="448bb-164">-Filter</span></span>

<span data-ttu-id="448bb-165">指定条件的哈希表。</span><span class="sxs-lookup"><span data-stu-id="448bb-165">Specifies a hash table of conditions.</span></span> <span data-ttu-id="448bb-166">此 cmdlet 将挂起满足所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-166">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="448bb-167">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="448bb-167">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-168">-Force</span><span class="sxs-lookup"><span data-stu-id="448bb-168">-Force</span></span>

<span data-ttu-id="448bb-169">立即挂起工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-169">Suspends the workflow job immediately.</span></span> <span data-ttu-id="448bb-170">此操作可能会导致状态和数据丢失。</span><span class="sxs-lookup"><span data-stu-id="448bb-170">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="448bb-171">默认情况下， `Suspend-Job` 允许工作流作业运行到下一个检查点，然后将其挂起。</span><span class="sxs-lookup"><span data-stu-id="448bb-171">By default, `Suspend-Job` lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="448bb-172">还可以使用此参数挂起不具有检查点的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-172">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-173">-Id</span><span class="sxs-lookup"><span data-stu-id="448bb-173">-Id</span></span>

<span data-ttu-id="448bb-174">指定此 cmdlet 挂起的作业的 Id。</span><span class="sxs-lookup"><span data-stu-id="448bb-174">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="448bb-175">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-175">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="448bb-176">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="448bb-176">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="448bb-177">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="448bb-177">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="448bb-178">若要查找作业的 ID，请使用 `Get-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448bb-178">To find the ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-179">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="448bb-179">-InstanceId</span></span>

<span data-ttu-id="448bb-180">指定此 cmdlet 挂起的作业的实例 Id。</span><span class="sxs-lookup"><span data-stu-id="448bb-180">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="448bb-181">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-181">The default is all jobs.</span></span>

<span data-ttu-id="448bb-182">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-182">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="448bb-183">若要查找作业的实例 ID，请使用 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="448bb-183">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-184">-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-184">-Job</span></span>

<span data-ttu-id="448bb-185">指定此 cmdlet 停止的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-185">Specifies the workflow jobs that this cmdlet stops.</span></span> <span data-ttu-id="448bb-186">请输入包含工作流作业的变量或可获取工作流作业的命令。</span><span class="sxs-lookup"><span data-stu-id="448bb-186">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span> <span data-ttu-id="448bb-187">还可以通过管道将工作流作业传递给 `Suspend-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448bb-187">You can also pipe workflow jobs to the `Suspend-Job` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-188">-Name</span><span class="sxs-lookup"><span data-stu-id="448bb-188">-Name</span></span>

<span data-ttu-id="448bb-189">指定此 cmdlet 挂起的作业的友好名称。</span><span class="sxs-lookup"><span data-stu-id="448bb-189">Specifies friendly names of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="448bb-190">输入一个或多个工作流作业名称。</span><span class="sxs-lookup"><span data-stu-id="448bb-190">Enter one or more workflow job names.</span></span>
<span data-ttu-id="448bb-191">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="448bb-191">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-192">-State</span><span class="sxs-lookup"><span data-stu-id="448bb-192">-State</span></span>

<span data-ttu-id="448bb-193">指定作业状态。</span><span class="sxs-lookup"><span data-stu-id="448bb-193">Specifies a job state.</span></span> <span data-ttu-id="448bb-194">此 cmdlet 仅停止处于指定状态的作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-194">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="448bb-195">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="448bb-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="448bb-196">NotStarted</span><span class="sxs-lookup"><span data-stu-id="448bb-196">NotStarted</span></span>
- <span data-ttu-id="448bb-197">正在运行</span><span class="sxs-lookup"><span data-stu-id="448bb-197">Running</span></span>
- <span data-ttu-id="448bb-198">已完成</span><span class="sxs-lookup"><span data-stu-id="448bb-198">Completed</span></span>
- <span data-ttu-id="448bb-199">已失败</span><span class="sxs-lookup"><span data-stu-id="448bb-199">Failed</span></span>
- <span data-ttu-id="448bb-200">已停止</span><span class="sxs-lookup"><span data-stu-id="448bb-200">Stopped</span></span>
- <span data-ttu-id="448bb-201">已阻止</span><span class="sxs-lookup"><span data-stu-id="448bb-201">Blocked</span></span>
- <span data-ttu-id="448bb-202">Suspended</span><span class="sxs-lookup"><span data-stu-id="448bb-202">Suspended</span></span>
- <span data-ttu-id="448bb-203">已断开连接</span><span class="sxs-lookup"><span data-stu-id="448bb-203">Disconnected</span></span>
- <span data-ttu-id="448bb-204">正在暂停</span><span class="sxs-lookup"><span data-stu-id="448bb-204">Suspending</span></span>
- <span data-ttu-id="448bb-205">正在停止</span><span class="sxs-lookup"><span data-stu-id="448bb-205">Stopping</span></span>

<span data-ttu-id="448bb-206">`Suspend-Job` 仅挂起处于 **运行** 状态的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-206">`Suspend-Job` suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="448bb-207">有关作业状态的详细信息，请参阅 [JobState 枚举](/dotnet/api/system.management.automation.jobstate)。</span><span class="sxs-lookup"><span data-stu-id="448bb-207">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448bb-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="448bb-208">-Wait</span></span>

<span data-ttu-id="448bb-209">指示此 cmdlet 禁止显示命令提示符，直到工作流作业处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="448bb-209">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span> <span data-ttu-id="448bb-210">默认情况下， `Suspend-Job` 即使工作流作业尚未处于挂起状态，也会立即返回。</span><span class="sxs-lookup"><span data-stu-id="448bb-210">By default, `Suspend-Job` returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="448bb-211">**Wait** 参数等效于通过管道将 `Suspend-Job` 命令传递给 `Wait-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448bb-211">The **Wait** parameter is equivalent to piping a `Suspend-Job` command to the `Wait-Job` cmdlet.</span></span>

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

### <span data-ttu-id="448bb-212">-Confirm</span><span class="sxs-lookup"><span data-stu-id="448bb-212">-Confirm</span></span>

<span data-ttu-id="448bb-213">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="448bb-213">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="448bb-214">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="448bb-214">-WhatIf</span></span>

<span data-ttu-id="448bb-215">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="448bb-215">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="448bb-216">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="448bb-216">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="448bb-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="448bb-217">CommonParameters</span></span>

<span data-ttu-id="448bb-218">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="448bb-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="448bb-219">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="448bb-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="448bb-220">输入</span><span class="sxs-lookup"><span data-stu-id="448bb-220">INPUTS</span></span>

### <span data-ttu-id="448bb-221">System.Management.Automation.Job</span><span class="sxs-lookup"><span data-stu-id="448bb-221">System.Management.Automation.Job</span></span>

<span data-ttu-id="448bb-222">可以通过管道将所有类型的作业传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448bb-222">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="448bb-223">但是，如果 `Suspend-Job` 获取不受支持的类型的作业，它将返回终止错误。</span><span class="sxs-lookup"><span data-stu-id="448bb-223">However, if `Suspend-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="448bb-224">输出</span><span class="sxs-lookup"><span data-stu-id="448bb-224">OUTPUTS</span></span>

### <span data-ttu-id="448bb-225">System.Management.Automation.Job</span><span class="sxs-lookup"><span data-stu-id="448bb-225">System.Management.Automation.Job</span></span>
<span data-ttu-id="448bb-226">此 cmdlet 将返回它挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="448bb-226">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="448bb-227">注释</span><span class="sxs-lookup"><span data-stu-id="448bb-227">NOTES</span></span>

- <span data-ttu-id="448bb-228">根据作业类型，保存挂起作业的机制和位置可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="448bb-228">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="448bb-229">例如，挂起的工作流作业默认保存在平面文件存储中，但是也可能保存在数据库中。</span><span class="sxs-lookup"><span data-stu-id="448bb-229">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
- <span data-ttu-id="448bb-230">如果提交未处于 "正在运行" 状态的工作流作业，则 `Suspend-Job` 将显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="448bb-230">If you submit a workflow job that is not in the Running state, `Suspend-Job` displays a warning message.</span></span> <span data-ttu-id="448bb-231">若要禁止显示警告，请使用值为 SilentlyContinue 的 **WarningAction** 通用参数。</span><span class="sxs-lookup"><span data-stu-id="448bb-231">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="448bb-232">如果作业不属于支持挂起的类型，则 `Suspend-Job` 返回终止错误。</span><span class="sxs-lookup"><span data-stu-id="448bb-232">If a job is not of a type that supports suspending, `Suspend-Job` returns a terminating error.</span></span>

- <span data-ttu-id="448bb-233">若要查找挂起的工作流作业（包括此 cmdlet 挂起的工作流作业），请使用该 cmdlet 的 **State** 参数 `Get-Job` 以使工作流作业处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="448bb-233">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get workflow jobs in the Suspended state.</span></span>
- <span data-ttu-id="448bb-234">某些作业类型具有可阻止 Windows PowerShell 挂起作业的选项或属性。</span><span class="sxs-lookup"><span data-stu-id="448bb-234">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="448bb-235">如果挂起作业的尝试失败，请验证作业选项和属性是否允许挂起。</span><span class="sxs-lookup"><span data-stu-id="448bb-235">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="448bb-236">相关链接</span><span class="sxs-lookup"><span data-stu-id="448bb-236">RELATED LINKS</span></span>

[<span data-ttu-id="448bb-237">Get-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-237">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="448bb-238">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-238">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="448bb-239">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-239">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="448bb-240">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-240">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="448bb-241">Start-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-241">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="448bb-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-242">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="448bb-243">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-243">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="448bb-244">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="448bb-244">Wait-Job</span></span>](Wait-Job.md)
