---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388529"
---
# <span data-ttu-id="e8140-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-103">Resume-Job</span></span>

## <span data-ttu-id="e8140-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e8140-104">SYNOPSIS</span></span>
<span data-ttu-id="e8140-105">重新启动挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="e8140-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8140-106">SYNTAX</span></span>

### <span data-ttu-id="e8140-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="e8140-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e8140-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="e8140-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e8140-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="e8140-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e8140-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="e8140-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e8140-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="e8140-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e8140-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="e8140-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e8140-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e8140-113">DESCRIPTION</span></span>

<span data-ttu-id="e8140-114">`Resume-Job`Cmdlet 可恢复已挂起的工作流作业，例如通过使用 `Suspend-Job` cmdlet 或[about_Suspend-workflow](../PSWorkflow/about/about_Suspend-Workflow.md)活动。</span><span class="sxs-lookup"><span data-stu-id="e8140-114">The `Resume-Job` cmdlet resumes a workflow job that was suspended, such as by using the `Suspend-Job` cmdlet or the [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) activity.</span></span> <span data-ttu-id="e8140-115">工作流作业恢复后，作业引擎将从已保存的资源（如检查点）重新构建状态、元数据和输出。</span><span class="sxs-lookup"><span data-stu-id="e8140-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span> <span data-ttu-id="e8140-116">在不丢失任何状态或数据的情况下重新启动作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="e8140-117">作业状态将从 **Suspended** 更改为 **Running** 。</span><span class="sxs-lookup"><span data-stu-id="e8140-117">The job state is changed from **Suspended** to **Running**.</span></span>

<span data-ttu-id="e8140-118">使用的参数 `Resume-Job` 可按名称、id、实例 ID 或管道将作业对象（如 cmdlet 返回的作业对象）选择 `Get-Job` 为 `Resume-Job` 。</span><span class="sxs-lookup"><span data-stu-id="e8140-118">Use the parameters of `Resume-Job` to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the `Get-Job` cmdlet, to `Resume-Job`.</span></span> <span data-ttu-id="e8140-119">还可以使用属性筛选器来选择要恢复的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="e8140-120">默认情况下， `Resume-Job` 即使可能尚未恢复所有作业，也会立即返回。</span><span class="sxs-lookup"><span data-stu-id="e8140-120">By default, `Resume-Job` returns immediately, even though all jobs might not yet be resumed.</span></span> <span data-ttu-id="e8140-121">若要在恢复所有指定的作业之前禁止显示命令提示符，请使用 **Wait** 参数。</span><span class="sxs-lookup"><span data-stu-id="e8140-121">To suppress the command prompt until all specified jobs are resumed, use the **Wait** parameter.</span></span>

<span data-ttu-id="e8140-122">此 `Resume-Job` cmdlet 仅适用于自定义作业类型，例如工作流作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-122">The `Resume-Job` cmdlet works only on custom job types, such as workflow jobs.</span></span> <span data-ttu-id="e8140-123">它不适用于标准后台作业，如使用 cmdlet 启动的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="e8140-123">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="e8140-124">如果提交的作业的类型不受支持，则会 `Resume-Job` 生成一个终止错误并停止运行。</span><span class="sxs-lookup"><span data-stu-id="e8140-124">If you submit a job of an unsupported type, `Resume-Job` generates a terminating error and stops running.</span></span>

<span data-ttu-id="e8140-125">若要标识工作流作业，请查找该作业的 **PSWorkflowJob** 属性中的 **PSJobTypeName** 值。</span><span class="sxs-lookup"><span data-stu-id="e8140-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="e8140-126">若要确定某个特定的自定义作业类型是否支持该 `Resume-Job` cmdlet，请参阅自定义作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e8140-126">To determine whether a particular custom job type supports the `Resume-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="e8140-127">在自定义作业类型上使用 Job cmdlet 之前，请使用 `Import-Module` cmdlet 或获取或使用模块中的 cmdlet 导入支持该自定义作业类型的模块。</span><span class="sxs-lookup"><span data-stu-id="e8140-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the `Import-Module` cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="e8140-128">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e8140-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="e8140-129">示例</span><span class="sxs-lookup"><span data-stu-id="e8140-129">EXAMPLES</span></span>

### <span data-ttu-id="e8140-130">示例 1：按 ID 恢复作业</span><span class="sxs-lookup"><span data-stu-id="e8140-130">Example 1: Resume a job by ID</span></span>

<span data-ttu-id="e8140-131">此示例中的命令将验证该作业是否为挂起的工作流作业，然后恢复该作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span> <span data-ttu-id="e8140-132">第一个命令使用 `Get-Job` cmdlet 来获取作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-132">The first command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="e8140-133">该输出显示该作业是挂起的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-133">The output shows that the job is a suspended workflow job.</span></span> <span data-ttu-id="e8140-134">第二个命令使用 cmdlet 的 **id** 参数 `Resume-Job` 恢复 **id** 值为4的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-134">The second command uses the **Id** parameter of the `Resume-Job` cmdlet to resume the job with an **Id** value of 4.</span></span>

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### <span data-ttu-id="e8140-135">示例 2：按名称恢复作业</span><span class="sxs-lookup"><span data-stu-id="e8140-135">Example 2: Resume a job by name</span></span>

<span data-ttu-id="e8140-136">此命令使用 **Name** 参数来恢复本地计算机上的多个工作流作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-136">This command uses the **Name** parameter to resume several workflow jobs on the local computer.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### <span data-ttu-id="e8140-137">示例 3：使用自定义属性值</span><span class="sxs-lookup"><span data-stu-id="e8140-137">Example 3: Use custom property values</span></span>

<span data-ttu-id="e8140-138">此命令使用自定义属性的值来标识要恢复的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-138">This command uses the value of a custom property to identify the workflow job to resume.</span></span> <span data-ttu-id="e8140-139">它使用 **Filter** 参数来按其 **CustomID** 属性标识工作流作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-139">It uses the **Filter** parameter to identify the workflow job by its **CustomID** property.</span></span> <span data-ttu-id="e8140-140">它还使用 **State** 参数来验证在尝试恢复工作流作业之前，工作流作业是否已挂起。</span><span class="sxs-lookup"><span data-stu-id="e8140-140">It also uses the **State** parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### <span data-ttu-id="e8140-141">示例 4：恢复远程计算机上所有挂起的作业</span><span class="sxs-lookup"><span data-stu-id="e8140-141">Example 4: Resume all suspended jobs on a remote computer</span></span>

<span data-ttu-id="e8140-142">此命令将恢复 Srv01 远程计算机上所有挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-142">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="e8140-143">该命令使用 `Invoke-Command` cmdlet 在 Srv01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="e8140-143">The command uses the `Invoke-Command` cmdlet to run a command on the Srv01 computer.</span></span> <span data-ttu-id="e8140-144">远程命令使用 cmdlet 的 **State** 参数 `Get-Job` 获取计算机上所有挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-144">The remote command uses the **State** parameter of the `Get-Job` cmdlet to get all suspended jobs on the computer.</span></span> <span data-ttu-id="e8140-145">管道运算符 (`|`) 将挂起的作业发送到 `Resume-Job` cmdlet，这会恢复它们。</span><span class="sxs-lookup"><span data-stu-id="e8140-145">A pipeline operator (`|`) sends the suspended jobs to the `Resume-Job` cmdlet, which resumes them.</span></span>

### <span data-ttu-id="e8140-146">示例5：等待作业恢复</span><span class="sxs-lookup"><span data-stu-id="e8140-146">Example 5: Wait for jobs to resume</span></span>

<span data-ttu-id="e8140-147">此命令使用 **Wait** 参数定向 `Resume-Job` 到仅在恢复所有指定作业后返回。</span><span class="sxs-lookup"><span data-stu-id="e8140-147">This command uses the **Wait** parameter to direct `Resume-Job` to return only after all specified jobs are resumed.</span></span> <span data-ttu-id="e8140-148">**Wait** 参数在假定已在脚本继续运行之前恢复作业的脚本中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="e8140-148">The **Wait** parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### <span data-ttu-id="e8140-149">示例6：恢复挂起自身的工作流</span><span class="sxs-lookup"><span data-stu-id="e8140-149">Example 6: Resume a workflow that suspends itself</span></span>

<span data-ttu-id="e8140-150">此代码示例显示 `Suspend-Workflow` 工作流中的活动。</span><span class="sxs-lookup"><span data-stu-id="e8140-150">This code sample shows the `Suspend-Workflow` activity in a workflow.</span></span>

<span data-ttu-id="e8140-151">`Test-Suspend`Server01 计算机上的工作流。</span><span class="sxs-lookup"><span data-stu-id="e8140-151">The `Test-Suspend` workflow on the Server01 computer.</span></span> <span data-ttu-id="e8140-152">运行工作流时，工作流将运行 `Get-Date` 活动，并将结果存储在 `$a` 变量中。</span><span class="sxs-lookup"><span data-stu-id="e8140-152">When you run the workflow, the workflow runs the `Get-Date` activity and stores the result in the `$a` variable.</span></span> <span data-ttu-id="e8140-153">然后运行 `Suspend-Workflow` 活动。</span><span class="sxs-lookup"><span data-stu-id="e8140-153">Then it runs the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="e8140-154">该工作流会采用一个检查点、挂起该工作流，并返回一个工作流作业对象来作为回复。</span><span class="sxs-lookup"><span data-stu-id="e8140-154">In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.</span></span> <span data-ttu-id="e8140-155">`Suspend-Workflow` 返回工作流作业对象，即使工作流不是作为作业显式运行。</span><span class="sxs-lookup"><span data-stu-id="e8140-155">`Suspend-Workflow` returns a workflow job object even if the workflow is not explicitly run as a job.</span></span>

<span data-ttu-id="e8140-156">`Resume-Job` 恢复 `Test-Suspend` Job8 中的工作流。</span><span class="sxs-lookup"><span data-stu-id="e8140-156">`Resume-Job` resumes the `Test-Suspend` workflow in Job8.</span></span> <span data-ttu-id="e8140-157">它使用 **Wait** 参数来保留命令提示符，直至作业恢复。</span><span class="sxs-lookup"><span data-stu-id="e8140-157">It uses the **Wait** parameter to hold the command prompt until the job is resumed.</span></span>

<span data-ttu-id="e8140-158">`Receive-Job`Cmdlet 将获取工作流的结果 `Test-Suspend` 。</span><span class="sxs-lookup"><span data-stu-id="e8140-158">The `Receive-Job` cmdlet gets the results of the `Test-Suspend` workflow.</span></span> <span data-ttu-id="e8140-159">工作流中的最后一个命令将返回一个 **TimeSpan** 对象，该对象表示当前日期和时间与在 `$a` 挂起工作流之前保存在变量中的日期和时间之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="e8140-159">The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the `$a` variable before the workflow was suspended.</span></span>

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

<span data-ttu-id="e8140-160">`Resume-Job`Cmdlet 可让你恢复使用活动挂起的工作流作业 `Suspend-Workflow` 。</span><span class="sxs-lookup"><span data-stu-id="e8140-160">The `Resume-Job` cmdlet lets you resume a workflow job that was suspend by using the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="e8140-161">此活动将从工作流内部挂起工作流。</span><span class="sxs-lookup"><span data-stu-id="e8140-161">This activity suspends a workflow from within a workflow.</span></span> <span data-ttu-id="e8140-162">它仅在工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="e8140-162">It is valid only in workflows.</span></span>

<span data-ttu-id="e8140-163">有关的信息 `Suspend-Workflow` ，请参阅 about_Suspend-Workflow] (。/PSWorkflow/about/about_Suspend) 。</span><span class="sxs-lookup"><span data-stu-id="e8140-163">For information about the `Suspend-Workflow`, see about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md).</span></span>

## <span data-ttu-id="e8140-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8140-164">PARAMETERS</span></span>

### <span data-ttu-id="e8140-165">-Filter</span><span class="sxs-lookup"><span data-stu-id="e8140-165">-Filter</span></span>

<span data-ttu-id="e8140-166">指定条件的哈希表。</span><span class="sxs-lookup"><span data-stu-id="e8140-166">Specifies a hash table of conditions.</span></span> <span data-ttu-id="e8140-167">此 cmdlet 将恢复满足哈希表中所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-167">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="e8140-168">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="e8140-168">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="e8140-169">-Id</span><span class="sxs-lookup"><span data-stu-id="e8140-169">-Id</span></span>

<span data-ttu-id="e8140-170">指定此 cmdlet 恢复的作业的 Id 数组。</span><span class="sxs-lookup"><span data-stu-id="e8140-170">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="e8140-171">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-171">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="e8140-172">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e8140-172">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="e8140-173">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="e8140-173">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="e8140-174">若要查找作业的 ID，请运行 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="e8140-174">To find the ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="e8140-175">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="e8140-175">-InstanceId</span></span>

<span data-ttu-id="e8140-176">指定此 cmdlet 恢复的作业的实例 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="e8140-176">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="e8140-177">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-177">The default is all jobs.</span></span>

<span data-ttu-id="e8140-178">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-178">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="e8140-179">若要查找作业的实例 ID，请运行 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="e8140-179">To find the instance ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="e8140-180">-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-180">-Job</span></span>

<span data-ttu-id="e8140-181">指定要恢复的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-181">Specifies the jobs to be resumed.</span></span> <span data-ttu-id="e8140-182">请输入一个包含作业的变量，或一个可获取作业的命令。</span><span class="sxs-lookup"><span data-stu-id="e8140-182">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="e8140-183">还可以通过管道将作业传递给 `Resume-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e8140-183">You can also pipe jobs to the `Resume-Job` cmdlet.</span></span>

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

### <span data-ttu-id="e8140-184">-Name</span><span class="sxs-lookup"><span data-stu-id="e8140-184">-Name</span></span>

<span data-ttu-id="e8140-185">指定此 cmdlet 恢复的作业的友好名称数组。</span><span class="sxs-lookup"><span data-stu-id="e8140-185">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="e8140-186">输入一个或多个作业名称。</span><span class="sxs-lookup"><span data-stu-id="e8140-186">Enter one or more job names.</span></span>
<span data-ttu-id="e8140-187">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e8140-187">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e8140-188">-State</span><span class="sxs-lookup"><span data-stu-id="e8140-188">-State</span></span>

<span data-ttu-id="e8140-189">指定要恢复的作业的状态。</span><span class="sxs-lookup"><span data-stu-id="e8140-189">Specifies the state of jobs to resume.</span></span> <span data-ttu-id="e8140-190">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="e8140-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e8140-191">NotStarted</span><span class="sxs-lookup"><span data-stu-id="e8140-191">NotStarted</span></span>
- <span data-ttu-id="e8140-192">正在运行</span><span class="sxs-lookup"><span data-stu-id="e8140-192">Running</span></span>
- <span data-ttu-id="e8140-193">已完成</span><span class="sxs-lookup"><span data-stu-id="e8140-193">Completed</span></span>
- <span data-ttu-id="e8140-194">已失败</span><span class="sxs-lookup"><span data-stu-id="e8140-194">Failed</span></span>
- <span data-ttu-id="e8140-195">已停止</span><span class="sxs-lookup"><span data-stu-id="e8140-195">Stopped</span></span>
- <span data-ttu-id="e8140-196">已阻止</span><span class="sxs-lookup"><span data-stu-id="e8140-196">Blocked</span></span>
- <span data-ttu-id="e8140-197">Suspended</span><span class="sxs-lookup"><span data-stu-id="e8140-197">Suspended</span></span>
- <span data-ttu-id="e8140-198">已断开连接</span><span class="sxs-lookup"><span data-stu-id="e8140-198">Disconnected</span></span>
- <span data-ttu-id="e8140-199">正在暂停</span><span class="sxs-lookup"><span data-stu-id="e8140-199">Suspending</span></span>
- <span data-ttu-id="e8140-200">正在停止</span><span class="sxs-lookup"><span data-stu-id="e8140-200">Stopping</span></span>

<span data-ttu-id="e8140-201">此 cmdlet 仅恢复处于 **挂起** 状态的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-201">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="e8140-202">有关作业状态的详细信息，请参阅 [JobState 枚举](/dotnet/api/system.management.automation.jobstate)。</span><span class="sxs-lookup"><span data-stu-id="e8140-202">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="e8140-203">-Wait</span><span class="sxs-lookup"><span data-stu-id="e8140-203">-Wait</span></span>

<span data-ttu-id="e8140-204">指示此 cmdlet 禁止显示命令提示符，直到重新启动所有作业结果。</span><span class="sxs-lookup"><span data-stu-id="e8140-204">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span> <span data-ttu-id="e8140-205">默认情况下，此 cmdlet 会立即返回可用的结果。</span><span class="sxs-lookup"><span data-stu-id="e8140-205">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="e8140-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e8140-206">-Confirm</span></span>

<span data-ttu-id="e8140-207">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e8140-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e8140-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e8140-208">-WhatIf</span></span>

<span data-ttu-id="e8140-209">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e8140-209">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e8140-210">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e8140-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e8140-211">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e8140-211">CommonParameters</span></span>

<span data-ttu-id="e8140-212">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e8140-212">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e8140-213">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e8140-213">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e8140-214">输入</span><span class="sxs-lookup"><span data-stu-id="e8140-214">INPUTS</span></span>

### <span data-ttu-id="e8140-215">System.Management.Automation.Job</span><span class="sxs-lookup"><span data-stu-id="e8140-215">System.Management.Automation.Job</span></span>

<span data-ttu-id="e8140-216">可以通过管道将所有类型的作业传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e8140-216">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="e8140-217">如果 `Resume-Job` 获取不受支持的类型的作业，它将返回终止错误。</span><span class="sxs-lookup"><span data-stu-id="e8140-217">If `Resume-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="e8140-218">输出</span><span class="sxs-lookup"><span data-stu-id="e8140-218">OUTPUTS</span></span>

### <span data-ttu-id="e8140-219">无、管理系统</span><span class="sxs-lookup"><span data-stu-id="e8140-219">None, System.Management.Automation.Job</span></span>

<span data-ttu-id="e8140-220">如果使用 **PassThru** 参数，则此 cmdlet 将返回尝试恢复的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-220">This cmdlet returns the jobs that it tries to resume, if you use the **PassThru** parameter.</span></span>
<span data-ttu-id="e8140-221">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="e8140-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e8140-222">注释</span><span class="sxs-lookup"><span data-stu-id="e8140-222">NOTES</span></span>

- <span data-ttu-id="e8140-223">`Resume-Job` 只能恢复挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-223">`Resume-Job` can only resume jobs that are suspended.</span></span> <span data-ttu-id="e8140-224">如果提交处于不同状态的作业，则 `Resume-Job` 对作业运行恢复操作，但是会生成一个警告，通知你无法恢复作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-224">If you submit a job in a different state, `Resume-Job` runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="e8140-225">若要禁止显示警告，请使用值为 SilentlyContinue 的 **WarningAction** 通用参数。</span><span class="sxs-lookup"><span data-stu-id="e8140-225">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>
- <span data-ttu-id="e8140-226">如果作业不是支持恢复的类型（如工作流作业 ( **PSWorkflowJob** ) ），则 `Resume-Job` 返回终止错误。</span><span class="sxs-lookup"><span data-stu-id="e8140-226">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), `Resume-Job` returns a terminating error.</span></span>
- <span data-ttu-id="e8140-227">根据作业类型，保存挂起作业的机制和位置可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="e8140-227">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="e8140-228">例如，挂起的工作流作业默认保存在平面文件存储中，但是也可能保存在 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="e8140-228">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
- <span data-ttu-id="e8140-229">恢复作业后，作业状态将从 **Suspended** 更改为 **Running** 。</span><span class="sxs-lookup"><span data-stu-id="e8140-229">When you resume a job, the job state changes from **Suspended** to **Running**.</span></span> <span data-ttu-id="e8140-230">若要查找正在运行的作业，包括已由此 cmdlet 恢复的作业，请使用 cmdlet 的 **State** 参数 `Get-Job` 获取处于 **运行** 状态的作业。</span><span class="sxs-lookup"><span data-stu-id="e8140-230">To find the jobs that are running, including those that were resumed by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get jobs in the **Running** state.</span></span>
- <span data-ttu-id="e8140-231">某些作业类型具有可阻止 Windows PowerShell 挂起作业的选项或属性。</span><span class="sxs-lookup"><span data-stu-id="e8140-231">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="e8140-232">如果挂起作业的尝试失败，请验证作业选项和属性是否允许挂起。</span><span class="sxs-lookup"><span data-stu-id="e8140-232">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="e8140-233">相关链接</span><span class="sxs-lookup"><span data-stu-id="e8140-233">RELATED LINKS</span></span>

[<span data-ttu-id="e8140-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="e8140-235">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="e8140-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="e8140-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="e8140-238">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-238">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="e8140-239">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-239">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="e8140-240">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="e8140-240">Wait-Job</span></span>](Wait-Job.md)
