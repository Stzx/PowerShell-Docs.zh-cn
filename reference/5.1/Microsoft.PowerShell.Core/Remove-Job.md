---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 589c43c814d5d68e57fd20226c675bf0f9587b69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197628"
---
# <span data-ttu-id="cba3b-103">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-103">Remove-Job</span></span>

## <span data-ttu-id="cba3b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cba3b-104">SYNOPSIS</span></span>
<span data-ttu-id="cba3b-105">删除 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-105">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="cba3b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cba3b-106">SYNTAX</span></span>

### <span data-ttu-id="cba3b-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="cba3b-107">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba3b-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="cba3b-108">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba3b-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="cba3b-109">NameParameterSet</span></span>

```
Remove-Job [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba3b-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="cba3b-110">InstanceIdParameterSet</span></span>

```
Remove-Job [-InstanceId] <Guid[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba3b-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="cba3b-111">FilterParameterSet</span></span>

```
Remove-Job [-Filter] <Hashtable> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba3b-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="cba3b-112">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba3b-113">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="cba3b-113">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cba3b-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cba3b-114">DESCRIPTION</span></span>

<span data-ttu-id="cba3b-115">`Remove-Job`Cmdlet 会删除由 `Start-Job` cmdlet 或 cmdlet （如 `Invoke-Command` 支持 **AsJob** 参数）启动的 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-115">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="cba3b-116">您可以使用 `Remove-Job` 删除所有作业或删除所选作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-116">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="cba3b-117">作业由其 **名称** 、 **ID** 、 **实例 ID** 、 **命令** 或 **状态** 标识。</span><span class="sxs-lookup"><span data-stu-id="cba3b-117">The jobs are identified by their **Name** , **ID** , **Instance ID** , **Command** , or **State** .</span></span> <span data-ttu-id="cba3b-118">或者，作业对象可以向下发送到 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-118">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="cba3b-119">如果没有参数或参数值，则无效 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-119">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="cba3b-120">由于 PowerShell 3.0， `Remove-Job` 可以删除自定义作业类型，例如计划作业和工作流作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-120">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="cba3b-121">例如， `Remove-Job` 删除计划作业、磁盘上计划作业的所有实例，以及所有触发的作业实例的结果。</span><span class="sxs-lookup"><span data-stu-id="cba3b-121">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="cba3b-122">如果尝试删除正在运行的作业，将 `Remove-Job` 失败。</span><span class="sxs-lookup"><span data-stu-id="cba3b-122">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="cba3b-123">使用 `Stop-Job` cmdlet 可停止正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-123">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="cba3b-124">或者，使用 `Remove-Job` **Force** 参数删除正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-124">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="cba3b-125">作业将保留在全局作业缓存中，直到删除后台作业或关闭 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="cba3b-125">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="cba3b-126">示例</span><span class="sxs-lookup"><span data-stu-id="cba3b-126">EXAMPLES</span></span>

### <span data-ttu-id="cba3b-127">示例1：使用作业名称删除作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-127">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="cba3b-128">此示例使用变量和管道按名称删除作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-128">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="cba3b-129">`Get-Job` 使用 **Name** 参数来指定作业 **BatchJob** 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-129">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob** .</span></span> <span data-ttu-id="cba3b-130">作业对象存储在 `$batch` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cba3b-130">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="cba3b-131">中的对象 `$batch` 将向下发送到 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-131">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="cba3b-132">一种替代方法是使用 **作业** 参数，如 `Remove-Job -Job $batch` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-132">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="cba3b-133">示例2：删除会话中的所有作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-133">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="cba3b-134">在此示例中，将删除当前 PowerShell 会话中的所有作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-134">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="cba3b-135">`Get-Job` 获取当前 PowerShell 会话中的所有作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-135">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="cba3b-136">作业对象将向下发送到 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-136">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="cba3b-137">示例3：删除 NotStarted 作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-137">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="cba3b-138">此示例将从当前 PowerShell 会话中删除尚未启动的所有作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-138">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="cba3b-139">`Remove-Job` 使用 **State** 参数指定作业状态。</span><span class="sxs-lookup"><span data-stu-id="cba3b-139">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="cba3b-140">示例4：使用友好名称删除作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-140">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="cba3b-141">此示例将从当前会话中删除具有以 \* batch \* \* 结尾的友好名称的所有作业，包括正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-141">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="cba3b-142">`Remove-Job` 使用 **Name** 参数来指定作业名称模式。</span><span class="sxs-lookup"><span data-stu-id="cba3b-142">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="cba3b-143">此模式包含星号 (`*`) 通配符，以查找以 **批处理** 结尾的所有作业名称。</span><span class="sxs-lookup"><span data-stu-id="cba3b-143">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch** .</span></span> <span data-ttu-id="cba3b-144">**Force** 参数删除运行的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-144">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="cba3b-145">示例5：删除 Invoke-Command 创建的作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-145">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="cba3b-146">此示例将使用 `Invoke-Command` 带有 **AsJob** 参数的远程计算机上删除已启动的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-146">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="cba3b-147">由于该示例使用了 **AsJob** 参数，因此在本地计算机上创建了作业对象。</span><span class="sxs-lookup"><span data-stu-id="cba3b-147">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="cba3b-148">但该作业在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="cba3b-148">But, the job runs on a remote computer.</span></span> <span data-ttu-id="cba3b-149">因此，你可以使用本地命令来管理作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-149">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="cba3b-150">`Invoke-Command` 在 **Server01** 计算机上运行作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-150">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="cba3b-151">**AsJob** 参数将 **ScriptBlock** 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="cba3b-151">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="cba3b-152">作业对象存储在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cba3b-152">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="cba3b-153">`$job`变量对象将向下发送到 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-153">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="cba3b-154">示例6：删除由 Invoke-Command 和 Start-Job 创建的作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-154">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="cba3b-155">此示例演示如何删除使用运行的启动的远程计算机上的作业 `Invoke-Command` `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-155">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="cba3b-156">在远程计算机上创建作业对象，并使用远程命令来管理该作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-156">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="cba3b-157">运行远程命令时需要持续连接 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-157">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="cba3b-158">`New-PSSession`创建与 **Server01** 计算机的 **PSSession** （持久连接）。</span><span class="sxs-lookup"><span data-stu-id="cba3b-158">`New-PSSession` creates a **PSSession** , a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="cba3b-159">该连接保存在变量中 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-159">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="cba3b-160">`Invoke-Command` 连接到保存在中的会话 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-160">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="cba3b-161">**ScriptBlock** 使用 `Start-Job` 来启动远程作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-161">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="cba3b-162">作业运行 `Get-Process` 命令，并使用 **Name** 参数指定友好的作业名称 **MyJob** 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-162">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob** .</span></span>

<span data-ttu-id="cba3b-163">`Invoke-Command` 使用 `$S` 会话并运行 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-163">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="cba3b-164">**Name** 参数指定已删除名为 **MyJob** 的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-164">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="cba3b-165">示例7：通过使用其实例 Id 删除作业</span><span class="sxs-lookup"><span data-stu-id="cba3b-165">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="cba3b-166">此示例根据作业的 **InstanceId** 删除作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-166">This example removes a job based on its **InstanceId** .</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="cba3b-167">`Start-Job` 启动一个后台作业，该作业对象保存在变量中 `$job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-167">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="cba3b-168">中的对象 `$job` 将向下发送到 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-168">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="cba3b-169">**Property** 参数使用星号 (`*`) 来指定对象的所有属性都显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="cba3b-169">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="cba3b-170">`Remove-Job` 使用 **InstanceId** 参数指定要删除的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-170">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="cba3b-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cba3b-171">PARAMETERS</span></span>

### <span data-ttu-id="cba3b-172">-Command</span><span class="sxs-lookup"><span data-stu-id="cba3b-172">-Command</span></span>

<span data-ttu-id="cba3b-173">删除命令中包含指定的词的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-173">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="cba3b-174">可以输入以逗号分隔的数组。</span><span class="sxs-lookup"><span data-stu-id="cba3b-174">You can enter a comma-separated array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cba3b-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cba3b-175">-Confirm</span></span>

<span data-ttu-id="cba3b-176">在运行之前提示你进行确认 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-176">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="cba3b-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="cba3b-177">-Filter</span></span>

<span data-ttu-id="cba3b-178">删除满足在关联的哈希表中建立的所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-178">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="cba3b-179">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="cba3b-179">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="cba3b-180">此参数仅适用于自定义作业类型，例如工作流作业和计划作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-180">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="cba3b-181">它不适用于标准后台作业，例如通过使用创建的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-181">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="cba3b-182">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cba3b-182">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cba3b-183">-Force</span><span class="sxs-lookup"><span data-stu-id="cba3b-183">-Force</span></span>

<span data-ttu-id="cba3b-184">即使作业的状态为 **正在运行** ，也会删除该作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-184">Deletes a job even if the job's state is **Running** .</span></span> <span data-ttu-id="cba3b-185">如果未指定 **Force** 参数，则 `Remove-Job` 不会删除正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-185">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cba3b-186">-Id</span><span class="sxs-lookup"><span data-stu-id="cba3b-186">-Id</span></span>

<span data-ttu-id="cba3b-187">删除具有指定 **Id** 的后台作业。可以输入以逗号分隔的数组。</span><span class="sxs-lookup"><span data-stu-id="cba3b-187">Deletes background jobs with the specified **Id** . You can enter a comma-separated array.</span></span> <span data-ttu-id="cba3b-188">作业的 **Id** 是用于标识当前会话中的作业的唯一整数。</span><span class="sxs-lookup"><span data-stu-id="cba3b-188">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="cba3b-189">若要查找作业的 **Id** ，请使用 `Get-Job` 不带参数的。</span><span class="sxs-lookup"><span data-stu-id="cba3b-189">To find a job's **Id** , use `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="cba3b-190">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="cba3b-190">-InstanceId</span></span>

<span data-ttu-id="cba3b-191">删除具有指定 **InstanceId** 的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-191">Deletes jobs with the specified **InstanceId** .</span></span> <span data-ttu-id="cba3b-192">可以输入以逗号分隔的数组。</span><span class="sxs-lookup"><span data-stu-id="cba3b-192">You can enter a comma-separated array.</span></span> <span data-ttu-id="cba3b-193">**InstanceId** 是用于标识作业的唯一 GUID。</span><span class="sxs-lookup"><span data-stu-id="cba3b-193">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="cba3b-194">若要查找作业的 **InstanceId** ，请使用 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-194">To find a job's **InstanceId** , use `Get-Job`.</span></span>

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

### <span data-ttu-id="cba3b-195">-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-195">-Job</span></span>

<span data-ttu-id="cba3b-196">指定要删除的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-196">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="cba3b-197">请输入一个包含作业的变量，或一个可获取作业的命令。</span><span class="sxs-lookup"><span data-stu-id="cba3b-197">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="cba3b-198">可以输入以逗号分隔的数组。</span><span class="sxs-lookup"><span data-stu-id="cba3b-198">You can enter a comma-separated array.</span></span>

<span data-ttu-id="cba3b-199">可以将作业对象向下发送到 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-199">You can send job objects down the pipeline to `Remove-Job`.</span></span>

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

### <span data-ttu-id="cba3b-200">-Name</span><span class="sxs-lookup"><span data-stu-id="cba3b-200">-Name</span></span>

<span data-ttu-id="cba3b-201">仅删除具有指定友好名称的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-201">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="cba3b-202">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="cba3b-202">Wildcards are permitted.</span></span> <span data-ttu-id="cba3b-203">可以输入以逗号分隔的数组。</span><span class="sxs-lookup"><span data-stu-id="cba3b-203">You can enter a comma-separated array.</span></span>

<span data-ttu-id="cba3b-204">作业的友好名称并不保证在 PowerShell 会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cba3b-204">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="cba3b-205">按名称删除文件时，请使用 **WhatIf** 和 **Confirm** 参数。</span><span class="sxs-lookup"><span data-stu-id="cba3b-205">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="cba3b-206">-State</span><span class="sxs-lookup"><span data-stu-id="cba3b-206">-State</span></span>

<span data-ttu-id="cba3b-207">仅删除具有指定状态的作业。</span><span class="sxs-lookup"><span data-stu-id="cba3b-207">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="cba3b-208">若要删除状态为 " **正在运行** " 的作业，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="cba3b-208">To delete jobs with a state of **Running** , use the **Force** parameter.</span></span>

<span data-ttu-id="cba3b-209">接受的值：</span><span class="sxs-lookup"><span data-stu-id="cba3b-209">Accepted values:</span></span>

- <span data-ttu-id="cba3b-210">AtBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cba3b-210">AtBreakpoint</span></span>
- <span data-ttu-id="cba3b-211">已阻止</span><span class="sxs-lookup"><span data-stu-id="cba3b-211">Blocked</span></span>
- <span data-ttu-id="cba3b-212">已完成</span><span class="sxs-lookup"><span data-stu-id="cba3b-212">Completed</span></span>
- <span data-ttu-id="cba3b-213">已断开连接</span><span class="sxs-lookup"><span data-stu-id="cba3b-213">Disconnected</span></span>
- <span data-ttu-id="cba3b-214">失败</span><span class="sxs-lookup"><span data-stu-id="cba3b-214">Failed</span></span>
- <span data-ttu-id="cba3b-215">NotStarted</span><span class="sxs-lookup"><span data-stu-id="cba3b-215">NotStarted</span></span>
- <span data-ttu-id="cba3b-216">正在运行</span><span class="sxs-lookup"><span data-stu-id="cba3b-216">Running</span></span>
- <span data-ttu-id="cba3b-217">已停止</span><span class="sxs-lookup"><span data-stu-id="cba3b-217">Stopped</span></span>
- <span data-ttu-id="cba3b-218">正在停止</span><span class="sxs-lookup"><span data-stu-id="cba3b-218">Stopping</span></span>
- <span data-ttu-id="cba3b-219">已挂起</span><span class="sxs-lookup"><span data-stu-id="cba3b-219">Suspended</span></span>
- <span data-ttu-id="cba3b-220">正在暂停</span><span class="sxs-lookup"><span data-stu-id="cba3b-220">Suspending</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cba3b-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cba3b-221">-WhatIf</span></span>

<span data-ttu-id="cba3b-222">显示运行时将发生 `Remove-Job` 的情况。</span><span class="sxs-lookup"><span data-stu-id="cba3b-222">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="cba3b-223">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="cba3b-223">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cba3b-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cba3b-224">CommonParameters</span></span>

<span data-ttu-id="cba3b-225">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cba3b-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cba3b-226">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="cba3b-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cba3b-227">输入</span><span class="sxs-lookup"><span data-stu-id="cba3b-227">INPUTS</span></span>

### <span data-ttu-id="cba3b-228">System.Management.Automation.Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-228">System.Management.Automation.Job</span></span>

<span data-ttu-id="cba3b-229">可以将作业对象向下发送到 `Remove-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cba3b-229">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="cba3b-230">输出</span><span class="sxs-lookup"><span data-stu-id="cba3b-230">OUTPUTS</span></span>

### <span data-ttu-id="cba3b-231">无</span><span class="sxs-lookup"><span data-stu-id="cba3b-231">None</span></span>

<span data-ttu-id="cba3b-232">`Remove-Job` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="cba3b-232">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="cba3b-233">注释</span><span class="sxs-lookup"><span data-stu-id="cba3b-233">NOTES</span></span>

<span data-ttu-id="cba3b-234">PowerShell 作业创建一个新进程。</span><span class="sxs-lookup"><span data-stu-id="cba3b-234">A PowerShell job creates a new process.</span></span> <span data-ttu-id="cba3b-235">作业完成后，进程将退出。</span><span class="sxs-lookup"><span data-stu-id="cba3b-235">When the job completes, the process exits.</span></span> <span data-ttu-id="cba3b-236">当 `Remove-Job` 运行时，作业的状态将被删除。</span><span class="sxs-lookup"><span data-stu-id="cba3b-236">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="cba3b-237">如果作业在完成之前停止并且其进程尚未退出，则会强行终止进程。</span><span class="sxs-lookup"><span data-stu-id="cba3b-237">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="cba3b-238">相关链接</span><span class="sxs-lookup"><span data-stu-id="cba3b-238">RELATED LINKS</span></span>

[<span data-ttu-id="cba3b-239">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="cba3b-239">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="cba3b-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="cba3b-240">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="cba3b-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="cba3b-241">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="cba3b-242">Get-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-242">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="cba3b-243">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cba3b-243">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="cba3b-244">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-244">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="cba3b-245">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-245">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="cba3b-246">Start-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-246">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="cba3b-247">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-247">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="cba3b-248">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-248">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="cba3b-249">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="cba3b-249">Wait-Job</span></span>](Wait-Job.md)
