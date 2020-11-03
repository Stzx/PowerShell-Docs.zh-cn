---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 5b023efa2c1545da574f447b8542bfbfe9b5d861
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198719"
---
# <span data-ttu-id="27e1f-103">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-103">Stop-Job</span></span>

## <span data-ttu-id="27e1f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="27e1f-104">SYNOPSIS</span></span>
<span data-ttu-id="27e1f-105">停止 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-105">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="27e1f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27e1f-106">SYNTAX</span></span>

### <span data-ttu-id="27e1f-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="27e1f-107">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27e1f-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="27e1f-108">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27e1f-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="27e1f-109">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27e1f-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="27e1f-110">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27e1f-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="27e1f-111">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27e1f-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="27e1f-112">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="27e1f-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27e1f-113">DESCRIPTION</span></span>

<span data-ttu-id="27e1f-114">**停止作业** cmdlet 将停止正在进行的 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-114">The **Stop-Job** cmdlet stops PowerShell background jobs that are in progress.</span></span>
<span data-ttu-id="27e1f-115">可以使用此 cmdlet 停止所有作业，或者基于作业的名称、ID、实例 ID 或状态停止所选作业，或者通过将作业对象传递到 **停止作业** 来停止这些作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-115">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to **Stop-Job** .</span></span>

<span data-ttu-id="27e1f-116">可以使用 **Stop-Job** 停止后台作业，例如通过使用 Start-Job cmdlet 或任何 cmdlet 的 *AsJob* 参数。</span><span class="sxs-lookup"><span data-stu-id="27e1f-116">You can use **Stop-Job** to stop background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of any cmdlet.</span></span>
<span data-ttu-id="27e1f-117">停止后台作业时，PowerShell 将完成该作业队列中挂起的所有任务，然后结束该作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-117">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span>
<span data-ttu-id="27e1f-118">提交此命令后，将不会有新任务添加到队列。</span><span class="sxs-lookup"><span data-stu-id="27e1f-118">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="27e1f-119">此 cmdlet 不删除后台作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-119">This cmdlet does not delete background jobs.</span></span>
<span data-ttu-id="27e1f-120">若要删除作业，请使用 Remove-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27e1f-120">To delete a job, use the Remove-Job cmdlet.</span></span>

<span data-ttu-id="27e1f-121">从 Windows PowerShell 3.0 开始， **停止作业** 还将停止自定义作业类型，例如工作流作业和计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="27e1f-121">Starting in Windows PowerShell 3.0, **Stop-Job** also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="27e1f-122">若要使 **停止作业** 停止具有自定义作业类型的作业，请在运行 **停止作业** 命令之前将支持自定义作业类型的模块导入到会话中，方法是使用 Import-Module cmdlet 或使用或在模块中获取 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27e1f-122">To enable **Stop-Job** to stop a job with custom job type, import the module that supports the custom job type into the session before you run a **Stop-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="27e1f-123">有关特定的自定义作业类型的信息，请参阅自定义作业类型功能的文档。</span><span class="sxs-lookup"><span data-stu-id="27e1f-123">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="27e1f-124">示例</span><span class="sxs-lookup"><span data-stu-id="27e1f-124">EXAMPLES</span></span>

### <span data-ttu-id="27e1f-125">示例1：使用 Invoke-Command 停止远程计算机上的作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-125">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="27e1f-126">此示例显示了如何使用 **Stop-Job** cmdlet 停止在远程计算机上运行的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-126">This example shows how to use the **Stop-Job** cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="27e1f-127">由于作业是通过使用 Invoke-Command cmdlet 以远程方式 **运行的，** 作业对象存储在远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="27e1f-127">Because the job was started by using the Invoke-Command cmdlet to run a **Start-Job** command remotely, the job object is stored on the remote computer.</span></span>
<span data-ttu-id="27e1f-128">必须使用另一个 **调用命令** 命令远程运行 **停止作业** 命令。</span><span class="sxs-lookup"><span data-stu-id="27e1f-128">You must use another **Invoke-Command** command to run a **Stop-Job** command remotely.</span></span>
<span data-ttu-id="27e1f-129">有关远程后台作业的详细信息，请参阅 about_Remote_Jobs。</span><span class="sxs-lookup"><span data-stu-id="27e1f-129">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="27e1f-130">第一个命令在 Server01 计算机上创建 ( **PSSession** ) 的 PowerShell 会话，然后将该会话对象存储在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="27e1f-130">The first command creates a PowerShell session ( **PSSession** ) on the Server01 computer, and then stores the session object in the $s variable.</span></span>
<span data-ttu-id="27e1f-131">该命令使用某个域管理员的凭据。</span><span class="sxs-lookup"><span data-stu-id="27e1f-131">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="27e1f-132">第二个命令使用 **Invoke-Command** cmdlet 在该会话中运行 **Start-Job** 命令。</span><span class="sxs-lookup"><span data-stu-id="27e1f-132">The second command uses the **Invoke-Command** cmdlet to run a **Start-Job** command in the session.</span></span>
<span data-ttu-id="27e1f-133">作业中的此命令将获取系统事件日志中的所有事件。</span><span class="sxs-lookup"><span data-stu-id="27e1f-133">The command in the job gets all of the events in the System event log.</span></span>
<span data-ttu-id="27e1f-134">生成的作业对象存储在 $j 变量中。</span><span class="sxs-lookup"><span data-stu-id="27e1f-134">The resulting job object is stored in the $j variable.</span></span>

<span data-ttu-id="27e1f-135">第三个命令停止作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-135">The third command stops the job.</span></span>
<span data-ttu-id="27e1f-136">它使用 Server01 **cmdlet 在上的** **PSSession** 中运行 **停止作业** 命令。</span><span class="sxs-lookup"><span data-stu-id="27e1f-136">It uses the **Invoke-Command** cmdlet to run a **Stop-Job** command in the **PSSession** on Server01.</span></span>
<span data-ttu-id="27e1f-137">由于作业对象存储在本地计算机上的变量 $j 中，因此该命令将使用 Using 作用域修饰符来将 $j 标识为局部变量。</span><span class="sxs-lookup"><span data-stu-id="27e1f-137">Because the job objects are stored in $j, which is a variable on the local computer, the command uses the Using scope modifier to identify $j as a local variable.</span></span>
<span data-ttu-id="27e1f-138">有关 Using 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](about/about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="27e1f-138">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="27e1f-139">命令完成后，作业将停止，$s 中的 **PSSession** 可供使用。</span><span class="sxs-lookup"><span data-stu-id="27e1f-139">When the command finishes, the job is stopped and the **PSSession** in $s is available for use.</span></span>

### <span data-ttu-id="27e1f-140">示例2：停止后台作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-140">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="27e1f-141">此命令停止 Job1 后台作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-141">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="27e1f-142">示例3：停止多个后台作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-142">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="27e1f-143">此命令停止三个作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-143">This command stops three jobs.</span></span>
<span data-ttu-id="27e1f-144">它将通过 ID 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-144">It identifies them by their IDs.</span></span>

### <span data-ttu-id="27e1f-145">示例4：停止所有后台作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-145">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="27e1f-146">此命令停止当前会话中的所有后台作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-146">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="27e1f-147">示例5：停止所有阻止的后台作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-147">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="27e1f-148">此命令停止阻止的所有作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-148">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="27e1f-149">示例6：使用实例 ID 停止作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-149">Example 6: Stop a job by using an instance ID</span></span>

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

<span data-ttu-id="27e1f-150">这些命令显示了如何根据作业的实例 ID 来停止作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-150">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="27e1f-151">第一个命令使用 Get-Job cmdlet 获取当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-151">The first command uses the Get-Job cmdlet to get the jobs in the current session.</span></span>
<span data-ttu-id="27e1f-152">该命令使用管道运算符 (|) 将作业发送到 Format-Table 命令，此命令显示每个作业的指定属性的表。</span><span class="sxs-lookup"><span data-stu-id="27e1f-152">The command uses a pipeline operator (|) to send the jobs to a Format-Table command, which displays a table of the specified properties of each job.</span></span>
<span data-ttu-id="27e1f-153">该表包括每个作业的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="27e1f-153">The table includes the Instance ID of each job.</span></span>
<span data-ttu-id="27e1f-154">它使用计算属性来显示作业状态。</span><span class="sxs-lookup"><span data-stu-id="27e1f-154">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="27e1f-155">第二个命令使用带有 *InstanceID* 参数的 **停止作业** 命令来停止所选作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-155">The second command uses a **Stop-Job** command that has the *InstanceID* parameter to stop a selected job.</span></span>

### <span data-ttu-id="27e1f-156">示例7：停止远程计算机上的作业</span><span class="sxs-lookup"><span data-stu-id="27e1f-156">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="27e1f-157">此示例显示了如何使用 **Stop-Job** cmdlet 停止在远程计算机上运行的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-157">This example shows how to use the **Stop-Job** cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="27e1f-158">由于作业是使用 **Command** Cmdlet 的 *AsJob* 参数启动的，因此作业对象位于本地计算机上，即使作业运行在远程计算机上也是如此。</span><span class="sxs-lookup"><span data-stu-id="27e1f-158">Because the job was started by using the *AsJob* parameter of the **Invoke-Command** cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span>
<span data-ttu-id="27e1f-159">因此，你可以使用本地 **停止作业** 命令来停止作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-159">Therefore, you can use a local **Stop-Job** command to stop the job.</span></span>

<span data-ttu-id="27e1f-160">第一个命令使用 **Invoke-Command** cmdlet 在 Server01 计算机上启动后台作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-160">The first command uses the **Invoke-Command** cmdlet to start a background job on the Server01 computer.</span></span>
<span data-ttu-id="27e1f-161">该命令使用 *AsJob* 参数将远程命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="27e1f-161">The command uses the *AsJob* parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="27e1f-162">此命令返回一个作业对象，该对象是 **启动作业** cmdlet 返回的相同作业对象。</span><span class="sxs-lookup"><span data-stu-id="27e1f-162">This command returns a job object, which is the same job object that the **Start-Job** cmdlet returns.</span></span>
<span data-ttu-id="27e1f-163">该命令将作业对象保存在 $j 变量中。</span><span class="sxs-lookup"><span data-stu-id="27e1f-163">The command saves the job object in the $j variable.</span></span>

<span data-ttu-id="27e1f-164">第二个命令使用管道运算符将 $j 变量中的作业发送到 Stop-Job。</span><span class="sxs-lookup"><span data-stu-id="27e1f-164">The second command uses a pipeline operator to send the job in the $j variable to Stop-Job.</span></span>
<span data-ttu-id="27e1f-165">该命令使用 *PassThru* 参数来指示 **Stop-Job** 返回作业对象。</span><span class="sxs-lookup"><span data-stu-id="27e1f-165">The command uses the *PassThru* parameter to direct **Stop-Job** to return a job object.</span></span>
<span data-ttu-id="27e1f-166">作业对象显示确认作业的状态为 "已停止"。</span><span class="sxs-lookup"><span data-stu-id="27e1f-166">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="27e1f-167">有关远程后台作业的详细信息，请参阅 about_Remote_Jobs。</span><span class="sxs-lookup"><span data-stu-id="27e1f-167">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="27e1f-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27e1f-168">PARAMETERS</span></span>

### <span data-ttu-id="27e1f-169">-Filter</span><span class="sxs-lookup"><span data-stu-id="27e1f-169">-Filter</span></span>

<span data-ttu-id="27e1f-170">指定条件的哈希表。</span><span class="sxs-lookup"><span data-stu-id="27e1f-170">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="27e1f-171">此 cmdlet 将停止满足所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-171">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="27e1f-172">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="27e1f-172">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="27e1f-173">此参数仅适用于自定义作业类型，例如工作流作业和计划作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-173">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="27e1f-174">它不适用于标准后台作业，如使用 **Start-Job** cmdlet 创建的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-174">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="27e1f-175">有关支持此参数的信息，请参阅作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="27e1f-175">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="27e1f-176">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="27e1f-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="27e1f-177">-Id</span><span class="sxs-lookup"><span data-stu-id="27e1f-177">-Id</span></span>

<span data-ttu-id="27e1f-178">指定此 cmdlet 停止的作业的 Id。</span><span class="sxs-lookup"><span data-stu-id="27e1f-178">Specifies the IDs of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="27e1f-179">默认值为当前会话中的所有作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-179">The default is all jobs in the current session.</span></span>

<span data-ttu-id="27e1f-180">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-180">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="27e1f-181">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="27e1f-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="27e1f-182">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="27e1f-182">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="27e1f-183">若要查找作业的 ID，请键入 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="27e1f-183">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27e1f-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="27e1f-184">-InstanceId</span></span>

<span data-ttu-id="27e1f-185">指定此 cmdlet 停止的作业的实例 Id。</span><span class="sxs-lookup"><span data-stu-id="27e1f-185">Specifies the instance IDs of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="27e1f-186">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-186">The default is all jobs.</span></span>

<span data-ttu-id="27e1f-187">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="27e1f-188">若要查找某个作业的实例 ID，请使用 Get-Job。</span><span class="sxs-lookup"><span data-stu-id="27e1f-188">To find the instance ID of a job, use Get-Job.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27e1f-189">-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-189">-Job</span></span>

<span data-ttu-id="27e1f-190">指定此 cmdlet 停止的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-190">Specifies the jobs that this cmdlet stops.</span></span>
<span data-ttu-id="27e1f-191">请输入一个包含作业的变量，或一个可获取作业的命令。</span><span class="sxs-lookup"><span data-stu-id="27e1f-191">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="27e1f-192">你还可以使用管道运算符将作业提交到 **停止作业** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27e1f-192">You can also use a pipeline operator to submit jobs to the **Stop-Job** cmdlet.</span></span>
<span data-ttu-id="27e1f-193">默认情况下， **停止作业** 将删除当前会话中启动的所有作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-193">By default, **Stop-Job** deletes all jobs that were started in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="27e1f-194">-Name</span><span class="sxs-lookup"><span data-stu-id="27e1f-194">-Name</span></span>

<span data-ttu-id="27e1f-195">指定此 cmdlet 停止的作业的友好名称。</span><span class="sxs-lookup"><span data-stu-id="27e1f-195">Specifies friendly names of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="27e1f-196">以逗号分隔的列表形式输入作业名称，或使用通配符 (\*) 来输入作业名称模式。</span><span class="sxs-lookup"><span data-stu-id="27e1f-196">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span>
<span data-ttu-id="27e1f-197">默认情况下， **停止作业** 将停止在当前会话中创建的所有作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-197">By default, **Stop-Job** stops all jobs created in the current session.</span></span>

<span data-ttu-id="27e1f-198">由于不能保证友好名称是唯一的，因此在按名称停止作业时，请使用 *WhatIf* 和 *Confirm* 参数。</span><span class="sxs-lookup"><span data-stu-id="27e1f-198">Because the friendly name is not guaranteed to be unique, use the *WhatIf* and *Confirm* parameters when stopping jobs by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="27e1f-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="27e1f-199">-PassThru</span></span>

<span data-ttu-id="27e1f-200">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="27e1f-200">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="27e1f-201">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="27e1f-201">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27e1f-202">-State</span><span class="sxs-lookup"><span data-stu-id="27e1f-202">-State</span></span>

<span data-ttu-id="27e1f-203">指定作业状态。</span><span class="sxs-lookup"><span data-stu-id="27e1f-203">Specifies a job state.</span></span>
<span data-ttu-id="27e1f-204">此 cmdlet 仅停止处于指定状态的作业。</span><span class="sxs-lookup"><span data-stu-id="27e1f-204">This cmdlet stops only jobs in the specified state.</span></span>
<span data-ttu-id="27e1f-205">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="27e1f-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="27e1f-206">NotStarted</span><span class="sxs-lookup"><span data-stu-id="27e1f-206">NotStarted</span></span>
- <span data-ttu-id="27e1f-207">正在运行</span><span class="sxs-lookup"><span data-stu-id="27e1f-207">Running</span></span>
- <span data-ttu-id="27e1f-208">已完成</span><span class="sxs-lookup"><span data-stu-id="27e1f-208">Completed</span></span>
- <span data-ttu-id="27e1f-209">已失败</span><span class="sxs-lookup"><span data-stu-id="27e1f-209">Failed</span></span>
- <span data-ttu-id="27e1f-210">已停止</span><span class="sxs-lookup"><span data-stu-id="27e1f-210">Stopped</span></span>
- <span data-ttu-id="27e1f-211">已阻止</span><span class="sxs-lookup"><span data-stu-id="27e1f-211">Blocked</span></span>
- <span data-ttu-id="27e1f-212">Suspended</span><span class="sxs-lookup"><span data-stu-id="27e1f-212">Suspended</span></span>
- <span data-ttu-id="27e1f-213">已断开连接</span><span class="sxs-lookup"><span data-stu-id="27e1f-213">Disconnected</span></span>
- <span data-ttu-id="27e1f-214">正在暂停</span><span class="sxs-lookup"><span data-stu-id="27e1f-214">Suspending</span></span>
- <span data-ttu-id="27e1f-215">正在停止</span><span class="sxs-lookup"><span data-stu-id="27e1f-215">Stopping</span></span>

<span data-ttu-id="27e1f-216">有关作业状态的详细信息，请参阅 MSDN 库中的 [JobState 枚举](https://msdn.microsoft.com/library/system.management.automation.jobstate) 。</span><span class="sxs-lookup"><span data-stu-id="27e1f-216">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27e1f-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="27e1f-217">-Confirm</span></span>

<span data-ttu-id="27e1f-218">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="27e1f-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="27e1f-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="27e1f-219">-WhatIf</span></span>

<span data-ttu-id="27e1f-220">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="27e1f-220">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="27e1f-221">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="27e1f-221">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="27e1f-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27e1f-222">CommonParameters</span></span>

<span data-ttu-id="27e1f-223">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="27e1f-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27e1f-224">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="27e1f-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27e1f-225">输入</span><span class="sxs-lookup"><span data-stu-id="27e1f-225">INPUTS</span></span>

### <span data-ttu-id="27e1f-226">System.Management.Automation.RemotingJob</span><span class="sxs-lookup"><span data-stu-id="27e1f-226">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="27e1f-227">可以通过管道将作业对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27e1f-227">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="27e1f-228">输出</span><span class="sxs-lookup"><span data-stu-id="27e1f-228">OUTPUTS</span></span>

### <span data-ttu-id="27e1f-229">PSRemotingJob （无）</span><span class="sxs-lookup"><span data-stu-id="27e1f-229">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="27e1f-230">如果指定 *PassThru* 参数，则此 cmdlet 将返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="27e1f-230">This cmdlet returns a job object, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="27e1f-231">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="27e1f-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="27e1f-232">注释</span><span class="sxs-lookup"><span data-stu-id="27e1f-232">NOTES</span></span>

## <span data-ttu-id="27e1f-233">相关链接</span><span class="sxs-lookup"><span data-stu-id="27e1f-233">RELATED LINKS</span></span>

[<span data-ttu-id="27e1f-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="27e1f-235">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="27e1f-235">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="27e1f-236">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-236">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="27e1f-237">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-237">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="27e1f-238">Start-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-238">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="27e1f-239">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="27e1f-239">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="27e1f-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="27e1f-240">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="27e1f-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="27e1f-241">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="27e1f-242">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="27e1f-242">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="27e1f-243">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="27e1f-243">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="27e1f-244">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="27e1f-244">about_Scopes</span></span>](About/about_scopes.md)
