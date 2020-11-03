---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197624"
---
# <span data-ttu-id="771ec-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-103">Resume-Job</span></span>

## <span data-ttu-id="771ec-104">摘要</span><span class="sxs-lookup"><span data-stu-id="771ec-104">SYNOPSIS</span></span>
<span data-ttu-id="771ec-105">重新启动挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="771ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="771ec-106">SYNTAX</span></span>

### <span data-ttu-id="771ec-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="771ec-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="771ec-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="771ec-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="771ec-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="771ec-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="771ec-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="771ec-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="771ec-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="771ec-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="771ec-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="771ec-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="771ec-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="771ec-113">DESCRIPTION</span></span>
<span data-ttu-id="771ec-114">**Resume-Job** cmdlet 允许恢复已挂起的工作流作业，例如通过使用 Suspend-Job cmdlet 或 about_Suspend-Workflow 挂起的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-114">The **Resume-Job** cmdlet resumes a workflow job that was suspended, such as by using the Suspend-Job cmdlet or the about_Suspend-Workflow activity.</span></span>
<span data-ttu-id="771ec-115">工作流作业恢复后，作业引擎将从已保存的资源（如检查点）重新构建状态、元数据和输出。</span><span class="sxs-lookup"><span data-stu-id="771ec-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span>
<span data-ttu-id="771ec-116">在不丢失任何状态或数据的情况下重新启动作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="771ec-117">作业状态将从 **Suspended** 更改为 **Running** 。</span><span class="sxs-lookup"><span data-stu-id="771ec-117">The job state is changed from **Suspended** to **Running** .</span></span>

<span data-ttu-id="771ec-118">使用 **Resume-Job** 的参数按名称 ID、实例 ID 选择作业，或者通过管道将作业对象（例如由 Get-Job cmdlet 返回的作业对象）返回到 **Resume-Job** 。</span><span class="sxs-lookup"><span data-stu-id="771ec-118">Use the parameters of **Resume-Job** to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the Get-Job cmdlet, to **Resume-Job** .</span></span>
<span data-ttu-id="771ec-119">还可以使用属性筛选器来选择要恢复的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="771ec-120">默认情况下，即使可能尚未恢复所有作业， **Resume-Job** 也将立即返回。</span><span class="sxs-lookup"><span data-stu-id="771ec-120">By default, **Resume-Job** returns immediately, even though all jobs might not yet be resumed.</span></span>
<span data-ttu-id="771ec-121">若要在恢复所有指定的作业之前禁止显示命令提示符，请使用 *Wait* 参数。</span><span class="sxs-lookup"><span data-stu-id="771ec-121">To suppress the command prompt until all specified jobs are resumed, use the *Wait* parameter.</span></span>

<span data-ttu-id="771ec-122">**Resume-Job** cmdlet 仅适用于自定义作业类型，例如工作流作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-122">The **Resume-Job** cmdlet works only on custom job types, such as workflow jobs.</span></span>
<span data-ttu-id="771ec-123">它不适用于标准后台作业，例如通过使用 Start-Job cmdlet 启动的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-123">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>
<span data-ttu-id="771ec-124">如果你提交了一个类型不受支持的作业，则 **Resume-Job** 将生成一个终止错误并停止运行。</span><span class="sxs-lookup"><span data-stu-id="771ec-124">If you submit a job of an unsupported type, **Resume-Job** generates a terminating error and stops running.</span></span>

<span data-ttu-id="771ec-125">若要标识工作流作业，请查找该作业的 **PSWorkflowJob** 属性中的 **PSJobTypeName** 值。</span><span class="sxs-lookup"><span data-stu-id="771ec-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="771ec-126">若要确定某个特定的自定义作业类型是否支持 **Resume-Job** cmdlet，请参阅自定义作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="771ec-126">To determine whether a particular custom job type supports the **Resume-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="771ec-127">在自定义作业类型上使用 Job cmdlet 之前，请使用 Import-Module cmdlet 或者获取或使用模块中的 cmdlet 导入支持该自定义作业类型的模块。</span><span class="sxs-lookup"><span data-stu-id="771ec-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the Import-Module cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="771ec-128">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="771ec-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="771ec-129">示例</span><span class="sxs-lookup"><span data-stu-id="771ec-129">EXAMPLES</span></span>

### <span data-ttu-id="771ec-130">示例 1：按 ID 恢复作业</span><span class="sxs-lookup"><span data-stu-id="771ec-130">Example 1: Resume a job by ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

<span data-ttu-id="771ec-131">此示例中的命令将验证该作业是否为挂起的工作流作业，然后恢复该作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span>

### <span data-ttu-id="771ec-132">示例 2：按名称恢复作业</span><span class="sxs-lookup"><span data-stu-id="771ec-132">Example 2: Resume a job by name</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

<span data-ttu-id="771ec-133">此命令使用 *Name* 参数来恢复本地计算机上的多个工作流作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-133">This command uses the *Name* parameter to resume several workflow jobs on the local computer.</span></span>

### <span data-ttu-id="771ec-134">示例 3：使用自定义属性值</span><span class="sxs-lookup"><span data-stu-id="771ec-134">Example 3: Use custom property values</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

<span data-ttu-id="771ec-135">此命令使用自定义属性的值来标识要恢复的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-135">This command uses the value of a custom property to identify the workflow job to resume.</span></span>
<span data-ttu-id="771ec-136">它使用 *Filter* 参数来按其 **CustomID** 属性标识工作流作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-136">It uses the *Filter* parameter to identify the workflow job by its **CustomID** property.</span></span>
<span data-ttu-id="771ec-137">它还使用 *State* 参数来验证在尝试恢复工作流作业之前，工作流作业是否已挂起。</span><span class="sxs-lookup"><span data-stu-id="771ec-137">It also uses the *State* parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

### <span data-ttu-id="771ec-138">示例 4：恢复远程计算机上所有挂起的作业</span><span class="sxs-lookup"><span data-stu-id="771ec-138">Example 4: Resume all suspended jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="771ec-139">此命令将恢复 Srv01 远程计算机上所有挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-139">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

<span data-ttu-id="771ec-140">该命令使用 Invoke-Command cmdlet 在 Srv01 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="771ec-140">The command uses the Invoke-Command cmdlet to run a command on the Srv01 computer.</span></span>
<span data-ttu-id="771ec-141">远程命令使用 **get-help** Cmdlet 的 *State* 参数获取计算机上所有挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-141">The remote command uses the *State* parameter of the **Get-Job** cmdlet to get all suspended jobs on the computer.</span></span>
<span data-ttu-id="771ec-142">管道运算符 (|) 将挂起的作业发送到 **Resume-Job** cmdlet，后者将恢复它们。</span><span class="sxs-lookup"><span data-stu-id="771ec-142">A pipeline operator (|) sends the suspended jobs to the **Resume-Job** cmdlet, which resumes them.</span></span>

### <span data-ttu-id="771ec-143">示例5：等待作业恢复</span><span class="sxs-lookup"><span data-stu-id="771ec-143">Example 5: Wait for jobs to resume</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

<span data-ttu-id="771ec-144">此命令使用 *Wait* 参数定向到仅在恢复所有指定作业后返回 **的 Resume 作业** 。</span><span class="sxs-lookup"><span data-stu-id="771ec-144">This command uses the *Wait* parameter to direct **Resume-Job** to return only after all specified jobs are resumed.</span></span>
<span data-ttu-id="771ec-145">*Wait* 参数在假定已在脚本继续运行之前恢复作业的脚本中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="771ec-145">The *Wait* parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

### <span data-ttu-id="771ec-146">示例6：恢复挂起自身的工作流</span><span class="sxs-lookup"><span data-stu-id="771ec-146">Example 6: Resume a workflow that suspends itself</span></span>

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
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

<span data-ttu-id="771ec-147">使用 **resume-Job** cmdlet 可以恢复使用 **挂起工作流** 活动挂起的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-147">The **Resume-Job** cmdlet lets you resume a workflow job that was suspend by using the **Suspend-Workflow** activity.</span></span>
<span data-ttu-id="771ec-148">此活动将从工作流内部挂起工作流。</span><span class="sxs-lookup"><span data-stu-id="771ec-148">This activity suspends a workflow from within a workflow.</span></span>
<span data-ttu-id="771ec-149">它仅在工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="771ec-149">It is valid only in workflows.</span></span>

<span data-ttu-id="771ec-150">若要了解 Suspend-Workflow，请参阅 about_Suspend-Workflow。</span><span class="sxs-lookup"><span data-stu-id="771ec-150">For information about the Suspend-Workflow, see about_Suspend-Workflow.</span></span>

## <span data-ttu-id="771ec-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="771ec-151">PARAMETERS</span></span>

### <span data-ttu-id="771ec-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="771ec-152">-Filter</span></span>
<span data-ttu-id="771ec-153">指定条件的哈希表。</span><span class="sxs-lookup"><span data-stu-id="771ec-153">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="771ec-154">此 cmdlet 将恢复满足哈希表中所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-154">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="771ec-155">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="771ec-155">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="771ec-156">-Id</span><span class="sxs-lookup"><span data-stu-id="771ec-156">-Id</span></span>
<span data-ttu-id="771ec-157">指定此 cmdlet 恢复的作业的 Id 数组。</span><span class="sxs-lookup"><span data-stu-id="771ec-157">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="771ec-158">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-158">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="771ec-159">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="771ec-159">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="771ec-160">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="771ec-160">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="771ec-161">若要查找作业的 ID，请运行 " **获取作业** "。</span><span class="sxs-lookup"><span data-stu-id="771ec-161">To find the ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="771ec-162">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="771ec-162">-InstanceId</span></span>
<span data-ttu-id="771ec-163">指定此 cmdlet 恢复的作业的实例 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="771ec-163">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="771ec-164">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-164">The default is all jobs.</span></span>

<span data-ttu-id="771ec-165">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-165">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="771ec-166">若要查找作业的实例 ID，请运行 " **获取作业** "。</span><span class="sxs-lookup"><span data-stu-id="771ec-166">To find the instance ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="771ec-167">-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-167">-Job</span></span>
<span data-ttu-id="771ec-168">指定要恢复的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-168">Specifies the jobs to be resumed.</span></span>
<span data-ttu-id="771ec-169">请输入一个包含作业的变量，或一个可获取作业的命令。</span><span class="sxs-lookup"><span data-stu-id="771ec-169">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="771ec-170">还可以通过管道将作业传递给 **Resume-Job** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="771ec-170">You can also pipe jobs to the **Resume-Job** cmdlet.</span></span>

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

### <span data-ttu-id="771ec-171">-Name</span><span class="sxs-lookup"><span data-stu-id="771ec-171">-Name</span></span>
<span data-ttu-id="771ec-172">指定此 cmdlet 恢复的作业的友好名称数组。</span><span class="sxs-lookup"><span data-stu-id="771ec-172">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="771ec-173">输入一个或多个作业名称。</span><span class="sxs-lookup"><span data-stu-id="771ec-173">Enter one or more job names.</span></span>
<span data-ttu-id="771ec-174">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="771ec-174">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="771ec-175">-State</span><span class="sxs-lookup"><span data-stu-id="771ec-175">-State</span></span>
<span data-ttu-id="771ec-176">指定要恢复的作业的状态。</span><span class="sxs-lookup"><span data-stu-id="771ec-176">Specifies the state of jobs to resume.</span></span>
<span data-ttu-id="771ec-177">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="771ec-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="771ec-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="771ec-178">NotStarted</span></span>
- <span data-ttu-id="771ec-179">正在运行</span><span class="sxs-lookup"><span data-stu-id="771ec-179">Running</span></span>
- <span data-ttu-id="771ec-180">已完成</span><span class="sxs-lookup"><span data-stu-id="771ec-180">Completed</span></span>
- <span data-ttu-id="771ec-181">已失败</span><span class="sxs-lookup"><span data-stu-id="771ec-181">Failed</span></span>
- <span data-ttu-id="771ec-182">已停止</span><span class="sxs-lookup"><span data-stu-id="771ec-182">Stopped</span></span>
- <span data-ttu-id="771ec-183">已阻止</span><span class="sxs-lookup"><span data-stu-id="771ec-183">Blocked</span></span>
- <span data-ttu-id="771ec-184">Suspended</span><span class="sxs-lookup"><span data-stu-id="771ec-184">Suspended</span></span>
- <span data-ttu-id="771ec-185">已断开连接</span><span class="sxs-lookup"><span data-stu-id="771ec-185">Disconnected</span></span>
- <span data-ttu-id="771ec-186">正在暂停</span><span class="sxs-lookup"><span data-stu-id="771ec-186">Suspending</span></span>
- <span data-ttu-id="771ec-187">正在停止</span><span class="sxs-lookup"><span data-stu-id="771ec-187">Stopping</span></span>

<span data-ttu-id="771ec-188">此 cmdlet 仅恢复处于 **挂起** 状态的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-188">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="771ec-189">有关作业状态的详细信息，请参阅 MSDN 库中的 [JobState 枚举](https://msdn.microsoft.com/library/system.management.automation.jobstate) 。</span><span class="sxs-lookup"><span data-stu-id="771ec-189">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="771ec-190">-Wait</span><span class="sxs-lookup"><span data-stu-id="771ec-190">-Wait</span></span>
<span data-ttu-id="771ec-191">指示此 cmdlet 禁止显示命令提示符，直到重新启动所有作业结果。</span><span class="sxs-lookup"><span data-stu-id="771ec-191">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span>
<span data-ttu-id="771ec-192">默认情况下，此 cmdlet 会立即返回可用的结果。</span><span class="sxs-lookup"><span data-stu-id="771ec-192">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="771ec-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="771ec-193">-Confirm</span></span>
<span data-ttu-id="771ec-194">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="771ec-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="771ec-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="771ec-195">-WhatIf</span></span>
<span data-ttu-id="771ec-196">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="771ec-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="771ec-197">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="771ec-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="771ec-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="771ec-198">CommonParameters</span></span>
<span data-ttu-id="771ec-199">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="771ec-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="771ec-200">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="771ec-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="771ec-201">输入</span><span class="sxs-lookup"><span data-stu-id="771ec-201">INPUTS</span></span>

### <span data-ttu-id="771ec-202">System.Management.Automation.Job</span><span class="sxs-lookup"><span data-stu-id="771ec-202">System.Management.Automation.Job</span></span>
<span data-ttu-id="771ec-203">可以通过管道将所有类型的作业传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="771ec-203">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="771ec-204">如果 **Resume 作业** 获取不受支持的类型的作业，它将返回终止错误。</span><span class="sxs-lookup"><span data-stu-id="771ec-204">If **Resume-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="771ec-205">输出</span><span class="sxs-lookup"><span data-stu-id="771ec-205">OUTPUTS</span></span>

### <span data-ttu-id="771ec-206">无、管理系统</span><span class="sxs-lookup"><span data-stu-id="771ec-206">None, System.Management.Automation.Job</span></span>
<span data-ttu-id="771ec-207">如果使用 *PassThru* 参数，则此 cmdlet 将返回尝试恢复的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-207">This cmdlet returns the jobs that it tries to resume, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="771ec-208">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="771ec-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="771ec-209">注释</span><span class="sxs-lookup"><span data-stu-id="771ec-209">NOTES</span></span>

* <span data-ttu-id="771ec-210">**Resume-Job** 仅可恢复已挂起的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-210">**Resume-Job** can only resume jobs that are suspended.</span></span> <span data-ttu-id="771ec-211">如果你提交了处于其他状态的作业，则 **Resume-Job** 将在该作业上运行恢复操作，但是会生成一个警告，提示你无法恢复该作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-211">If you submit a job in a different state, **Resume-Job** runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="771ec-212">若要禁止显示警告，请使用值为 SilentlyContinue 的 *WarningAction* 通用参数。</span><span class="sxs-lookup"><span data-stu-id="771ec-212">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>
* <span data-ttu-id="771ec-213">如果作业的类型不是支持恢复的类型（如工作流作业 ( **PSWorkflowJob** ) ），则 **恢复作业** 将返回终止错误。</span><span class="sxs-lookup"><span data-stu-id="771ec-213">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), **Resume-Job** returns a terminating error.</span></span>
* <span data-ttu-id="771ec-214">根据作业类型，保存挂起作业的机制和位置可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="771ec-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="771ec-215">例如，挂起的工作流作业默认保存在平面文件存储中，但是也可能保存在 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="771ec-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
* <span data-ttu-id="771ec-216">恢复作业后，作业状态将从 **Suspended** 更改为 **Running** 。</span><span class="sxs-lookup"><span data-stu-id="771ec-216">When you resume a job, the job state changes from **Suspended** to **Running** .</span></span> <span data-ttu-id="771ec-217">若要查找正在运行的作业，包括已由此 cmdlet 恢复的作业，请使用 **get-help** Cmdlet 的 *State* 参数获取处于 **运行** 状态的作业。</span><span class="sxs-lookup"><span data-stu-id="771ec-217">To find the jobs that are running, including those that were resumed by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get jobs in the **Running** state.</span></span>
* <span data-ttu-id="771ec-218">某些作业类型具有可阻止 Windows PowerShell 挂起作业的选项或属性。</span><span class="sxs-lookup"><span data-stu-id="771ec-218">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="771ec-219">如果挂起作业的尝试失败，请验证作业选项和属性是否允许挂起。</span><span class="sxs-lookup"><span data-stu-id="771ec-219">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="771ec-220">相关链接</span><span class="sxs-lookup"><span data-stu-id="771ec-220">RELATED LINKS</span></span>

[<span data-ttu-id="771ec-221">Get-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-221">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="771ec-222">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-222">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="771ec-223">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-223">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="771ec-224">Start-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-224">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="771ec-225">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-225">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="771ec-226">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-226">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="771ec-227">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="771ec-227">Wait-Job</span></span>](Wait-Job.md)
