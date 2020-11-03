---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: a2dced2eabd7a9d21d8637922e576ecd7dd3e6d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197089"
---
# <span data-ttu-id="0ae71-103">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-103">Receive-Job</span></span>

## <span data-ttu-id="0ae71-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0ae71-104">SYNOPSIS</span></span>
<span data-ttu-id="0ae71-105">获取当前会话中 PowerShell 后台作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-105">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="0ae71-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ae71-106">SYNTAX</span></span>

### <span data-ttu-id="0ae71-107">Location（默认值）</span><span class="sxs-lookup"><span data-stu-id="0ae71-107">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="0ae71-108">计算机名</span><span class="sxs-lookup"><span data-stu-id="0ae71-108">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="0ae71-109">会话</span><span class="sxs-lookup"><span data-stu-id="0ae71-109">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="0ae71-110">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ae71-110">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="0ae71-111">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ae71-111">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="0ae71-112">SessionIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ae71-112">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="0ae71-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ae71-113">DESCRIPTION</span></span>

<span data-ttu-id="0ae71-114">该 `Receive-Job` cmdlet 将获取 PowerShell 后台作业的结果，如使用 `Start-Job` cmdlet 或任何 Cmdlet 的 **AsJob** 参数启动的作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-114">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="0ae71-115">你可以获取所有作业的结果，或通过作业的名称、ID、实例 ID、计算机名称、位置或会话或者通过提交作业对象来标识作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-115">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="0ae71-116">启动 PowerShell 后台作业时，该作业将启动，但是结果不会立即显示。</span><span class="sxs-lookup"><span data-stu-id="0ae71-116">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="0ae71-117">而该命令将返回一个表示该后台作业的对象。</span><span class="sxs-lookup"><span data-stu-id="0ae71-117">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="0ae71-118">该作业对象包含有关该作业的有用信息，但是不包含结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-118">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="0ae71-119">此方法允许你在作业运行的同时继续在会话中工作。</span><span class="sxs-lookup"><span data-stu-id="0ae71-119">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="0ae71-120">有关 PowerShell 中的后台作业的详细信息，请参阅 [about_Jobs](./About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae71-120">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="0ae71-121">该 `Receive-Job` cmdlet 将获取 `Receive-Job` 提交命令后生成的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-121">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="0ae71-122">如果尚未完成结果，你可以运行其他 `Receive-Job` 命令来获取剩余结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-122">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="0ae71-123">默认情况下，作业结果将在你收到它们时从系统中删除，但是你可以使用 **Keep** 参数来保存这些结果，以便可以再次收到它们。</span><span class="sxs-lookup"><span data-stu-id="0ae71-123">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="0ae71-124">若要删除作业结果，请在 `Receive-Job` 不使用 **Keep** 参数的情况下再次运行该命令，关闭会话，或使用 `Remove-Job` cmdlet 从会话中删除该作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-124">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="0ae71-125">从 Windows PowerShell 3.0 开始， `Receive-Job` 还获取自定义作业类型的结果，如工作流作业和计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="0ae71-125">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="0ae71-126">若要使 `Receive-Job` 能够获取自定义作业类型的结果，请在运行命令之前将支持自定义作业类型的模块导入到会话中 `Receive-Job` ，方法是使用 `Import-Module` cmdlet 或通过使用或在模块中获取 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ae71-126">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="0ae71-127">有关特定的自定义作业类型的信息，请参阅自定义作业类型功能的文档。</span><span class="sxs-lookup"><span data-stu-id="0ae71-127">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="0ae71-128">示例</span><span class="sxs-lookup"><span data-stu-id="0ae71-128">EXAMPLES</span></span>

### <span data-ttu-id="0ae71-129">示例1：获取特定作业的结果</span><span class="sxs-lookup"><span data-stu-id="0ae71-129">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="0ae71-130">这些命令使用的 **作业** 参数 `Receive-Job` 来获取特定作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-130">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="0ae71-131">第一个命令使用启动一个作业 `Start-Job` ，并将该作业对象存储在 `$job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0ae71-131">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="0ae71-132">第二个命令使用 `Receive-Job` cmdlet 来获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-132">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="0ae71-133">它使用 **Job** 参数来指定作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-133">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="0ae71-134">示例2：使用 Keep 参数</span><span class="sxs-lookup"><span data-stu-id="0ae71-134">Example 2: Use the Keep parameter</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

<span data-ttu-id="0ae71-135">此示例在变量中存储作业 `$job` ，并通过管道将作业传递给 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ae71-135">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="0ae71-136">`-Keep`参数还用于允许在第一次查看之后再次检索聚合流数据。</span><span class="sxs-lookup"><span data-stu-id="0ae71-136">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="0ae71-137">示例3：获取多个后台作业的结果</span><span class="sxs-lookup"><span data-stu-id="0ae71-137">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="0ae71-138">使用的 **AsJob** 参数 `Invoke-Command` 启动作业时，将在本地计算机上创建作业对象，即使该作业在远程计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="0ae71-138">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="0ae71-139">因此，你可以使用本地命令来管理作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-139">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="0ae71-140">此外，当你使用 **AsJob** 时，PowerShell 将返回一个作业对象，其中包含已启动的每个作业的子作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-140">Also, when you use **AsJob** , PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="0ae71-141">在此示例中，该作业对象包含三个子作业，分别对应于每台远程计算机上的每个作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-141">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### <span data-ttu-id="0ae71-142">示例4：获取多台远程计算机上的后台作业的结果</span><span class="sxs-lookup"><span data-stu-id="0ae71-142">Example 4: Get results of background jobs on multiple remote computers</span></span>

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

<span data-ttu-id="0ae71-143">此示例显示了如何获取在三台远程计算机上运行的后台作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-143">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="0ae71-144">与前面的示例不同，使用 `Invoke-Command` 运行 `Start-Job` 命令实际上是在三台计算机上的每一台计算机上启动了三个独立的作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-144">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="0ae71-145">因此，该命令返回了三个作业对象，以表示在三台不同的计算机上本地运行的三个作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-145">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

> [!NOTE]
> <span data-ttu-id="0ae71-146">在最后一个命令中，由于 `$j` 是局部变量，因此脚本块使用 **Using** 作用域修饰符来标识 `$j` 变量。</span><span class="sxs-lookup"><span data-stu-id="0ae71-146">In the last command, because `$j` is a local variable, the script block uses the **Using** scope modifier to identify the `$j` variable.</span></span> <span data-ttu-id="0ae71-147">有关 **Using** 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](./About/about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae71-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md).</span></span>

### <span data-ttu-id="0ae71-148">示例5：访问子作业</span><span class="sxs-lookup"><span data-stu-id="0ae71-148">Example 5: Access child jobs</span></span>

<span data-ttu-id="0ae71-149">`-Keep`参数保留作业的聚合流的状态，以便可以再次查看。</span><span class="sxs-lookup"><span data-stu-id="0ae71-149">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="0ae71-150">如果没有此参数，则当接收到作业时，所有聚合流数据都将被清除。</span><span class="sxs-lookup"><span data-stu-id="0ae71-150">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="0ae71-151">有关详细信息，请参阅 [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="0ae71-151">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="0ae71-152">聚合流包括所有子作业的流。</span><span class="sxs-lookup"><span data-stu-id="0ae71-152">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="0ae71-153">你仍可以通过作业对象和子作业对象访问单个数据流。</span><span class="sxs-lookup"><span data-stu-id="0ae71-153">You can still reach the individual streams of data through the job object and child job objects.</span></span>

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```Output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```Output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```Output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## <span data-ttu-id="0ae71-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ae71-154">PARAMETERS</span></span>

### <span data-ttu-id="0ae71-155">-AutoRemoveJob</span><span class="sxs-lookup"><span data-stu-id="0ae71-155">-AutoRemoveJob</span></span>

<span data-ttu-id="0ae71-156">指示此 cmdlet 在返回作业结果后删除该作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-156">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="0ae71-157">如果作业有更多结果，则仍将删除该作业，但会 `Receive-Job` 显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="0ae71-157">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="0ae71-158">此参数仅适用于自定义作业类型。</span><span class="sxs-lookup"><span data-stu-id="0ae71-158">This parameter works only on custom job types.</span></span>
<span data-ttu-id="0ae71-159">它专门用于保存会话之外的作业或类型的作业类型的实例，例如计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="0ae71-159">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="0ae71-160">不能在缺少 **Wait** 参数的情况下使用此参数。</span><span class="sxs-lookup"><span data-stu-id="0ae71-160">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="0ae71-161">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0ae71-161">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ae71-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0ae71-162">-ComputerName</span></span>

<span data-ttu-id="0ae71-163">指定计算机的名称数组。</span><span class="sxs-lookup"><span data-stu-id="0ae71-163">Specifies an array of names of computers.</span></span>

<span data-ttu-id="0ae71-164">此参数从存储在本地计算机的作业结果中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0ae71-164">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="0ae71-165">它不会获取在远程计算机上运行的作业的数据。</span><span class="sxs-lookup"><span data-stu-id="0ae71-165">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="0ae71-166">若要获取存储在远程计算机上的作业结果，请使用 `Invoke-Command` cmdlet 远程运行 `Receive-Job` 命令。</span><span class="sxs-lookup"><span data-stu-id="0ae71-166">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0ae71-167">-Force</span><span class="sxs-lookup"><span data-stu-id="0ae71-167">-Force</span></span>

<span data-ttu-id="0ae71-168">指示当作业处于 **挂起** 或 **断开连接** 状态时，此 cmdlet 将继续等待。</span><span class="sxs-lookup"><span data-stu-id="0ae71-168">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="0ae71-169">默认情况下， **Wait** `Receive-Job` 当作业处于以下状态之一时，的 wait 参数将返回或终止等待：</span><span class="sxs-lookup"><span data-stu-id="0ae71-169">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="0ae71-170">已完成</span><span class="sxs-lookup"><span data-stu-id="0ae71-170">Completed</span></span>
- <span data-ttu-id="0ae71-171">已失败</span><span class="sxs-lookup"><span data-stu-id="0ae71-171">Failed</span></span>
- <span data-ttu-id="0ae71-172">已停止</span><span class="sxs-lookup"><span data-stu-id="0ae71-172">Stopped</span></span>
- <span data-ttu-id="0ae71-173">已挂起</span><span class="sxs-lookup"><span data-stu-id="0ae71-173">Suspended</span></span>
- <span data-ttu-id="0ae71-174">已断开连接。</span><span class="sxs-lookup"><span data-stu-id="0ae71-174">Disconnected.</span></span>

<span data-ttu-id="0ae71-175">仅当命令中也使用 **Wait** 参数时， **Force** 参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0ae71-175">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="0ae71-176">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0ae71-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ae71-177">-Id</span><span class="sxs-lookup"><span data-stu-id="0ae71-177">-Id</span></span>

<span data-ttu-id="0ae71-178">指定一个 ID 数组。</span><span class="sxs-lookup"><span data-stu-id="0ae71-178">Specifies an array of IDs.</span></span>
<span data-ttu-id="0ae71-179">此 cmdlet 将获取具有指定 Id 的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-179">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="0ae71-180">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-180">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="0ae71-181">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0ae71-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="0ae71-182">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="0ae71-182">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="0ae71-183">若要查找作业的 ID，请使用 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="0ae71-183">To find the ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="0ae71-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0ae71-184">-InstanceId</span></span>

<span data-ttu-id="0ae71-185">指定实例 ID 的数组。</span><span class="sxs-lookup"><span data-stu-id="0ae71-185">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="0ae71-186">此 cmdlet 将获取具有指定实例 Id 的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-186">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="0ae71-187">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="0ae71-188">若要查找作业的实例 ID，请使用 `Get-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ae71-188">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0ae71-189">-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-189">-Job</span></span>

<span data-ttu-id="0ae71-190">指定要检索其结果的作业。</span><span class="sxs-lookup"><span data-stu-id="0ae71-190">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="0ae71-191">请输入一个包含作业的变量，或一个可获取作业的命令。</span><span class="sxs-lookup"><span data-stu-id="0ae71-191">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="0ae71-192">还可以通过管道将作业对象传递给 `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="0ae71-192">You can also pipe a job object to `Receive-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ae71-193">-Keep</span><span class="sxs-lookup"><span data-stu-id="0ae71-193">-Keep</span></span>

<span data-ttu-id="0ae71-194">指示此 cmdlet 将聚合流数据保存在系统中，即使在收到这些数据后也是如此。</span><span class="sxs-lookup"><span data-stu-id="0ae71-194">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="0ae71-195">默认情况下，在使用查看后将清除聚合流数据 `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="0ae71-195">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="0ae71-196">关闭会话，或删除具有 cmdlet 的作业 `Remove-Job` 也会删除聚合的流数据。</span><span class="sxs-lookup"><span data-stu-id="0ae71-196">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

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

### <span data-ttu-id="0ae71-197">-Location</span><span class="sxs-lookup"><span data-stu-id="0ae71-197">-Location</span></span>

<span data-ttu-id="0ae71-198">指定位置的数组。</span><span class="sxs-lookup"><span data-stu-id="0ae71-198">Specifies an array of locations.</span></span>
<span data-ttu-id="0ae71-199">此 cmdlet 仅获取指定位置中的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-199">This cmdlet gets only the results of jobs in the specified locations.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ae71-200">-Name</span><span class="sxs-lookup"><span data-stu-id="0ae71-200">-Name</span></span>

<span data-ttu-id="0ae71-201">指定一个友好名称数组。</span><span class="sxs-lookup"><span data-stu-id="0ae71-201">Specifies an array of friendly names.</span></span>
<span data-ttu-id="0ae71-202">此 cmdlet 将获取具有指定名称的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-202">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="0ae71-203">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0ae71-203">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="0ae71-204">-NoRecurse</span><span class="sxs-lookup"><span data-stu-id="0ae71-204">-NoRecurse</span></span>

<span data-ttu-id="0ae71-205">指示此 cmdlet 仅获取指定作业中的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-205">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="0ae71-206">默认情况下， `Receive-Job` 还会获取指定作业的所有子作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-206">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

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

### <span data-ttu-id="0ae71-207">-Session</span><span class="sxs-lookup"><span data-stu-id="0ae71-207">-Session</span></span>

<span data-ttu-id="0ae71-208">指定会话的数组。</span><span class="sxs-lookup"><span data-stu-id="0ae71-208">Specifies an array of sessions.</span></span>
<span data-ttu-id="0ae71-209">此 cmdlet 将获取 ( **PSSession** ) 在指定的 PowerShell 会话中运行的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-209">This cmdlet gets the results of jobs that were run in the specified PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="0ae71-210">输入包含 **pssession** 的变量或获取 **pssession** 的命令（如 `Get-PSSession` 命令）。</span><span class="sxs-lookup"><span data-stu-id="0ae71-210">Enter a variable that contains the **PSSession** or a command that gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0ae71-211">-Wait</span><span class="sxs-lookup"><span data-stu-id="0ae71-211">-Wait</span></span>

<span data-ttu-id="0ae71-212">指示此 cmdlet 禁止显示命令提示符，直到收到所有作业结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-212">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="0ae71-213">默认情况下，会 `Receive-Job` 立即返回可用结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-213">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="0ae71-214">默认情况下， **Wait** 参数将等待作业处于以下状态之一：</span><span class="sxs-lookup"><span data-stu-id="0ae71-214">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="0ae71-215">已完成</span><span class="sxs-lookup"><span data-stu-id="0ae71-215">Completed</span></span>
- <span data-ttu-id="0ae71-216">已失败</span><span class="sxs-lookup"><span data-stu-id="0ae71-216">Failed</span></span>
- <span data-ttu-id="0ae71-217">已停止</span><span class="sxs-lookup"><span data-stu-id="0ae71-217">Stopped</span></span>
- <span data-ttu-id="0ae71-218">已挂起</span><span class="sxs-lookup"><span data-stu-id="0ae71-218">Suspended</span></span>
- <span data-ttu-id="0ae71-219">已断开连接。</span><span class="sxs-lookup"><span data-stu-id="0ae71-219">Disconnected.</span></span>

<span data-ttu-id="0ae71-220">若要指示 **wait** 参数继续等待作业状态为 "已挂起" 还是 "已断开连接"，请将 **Force** 参数与 **Wait** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="0ae71-220">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="0ae71-221">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0ae71-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ae71-222">-WriteEvents</span><span class="sxs-lookup"><span data-stu-id="0ae71-222">-WriteEvents</span></span>

<span data-ttu-id="0ae71-223">指示此 cmdlet 在等待作业完成时报告作业状态的更改。</span><span class="sxs-lookup"><span data-stu-id="0ae71-223">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="0ae71-224">仅当在命令中使用 **Wait** 参数并且省略 **Keep** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0ae71-224">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="0ae71-225">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0ae71-225">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ae71-226">-WriteJobInResults</span><span class="sxs-lookup"><span data-stu-id="0ae71-226">-WriteJobInResults</span></span>

<span data-ttu-id="0ae71-227">指示此 cmdlet 返回后跟结果的作业对象。</span><span class="sxs-lookup"><span data-stu-id="0ae71-227">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="0ae71-228">仅当在命令中使用 **Wait** 参数并且省略 **Keep** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0ae71-228">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="0ae71-229">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0ae71-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ae71-230">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0ae71-230">CommonParameters</span></span>

<span data-ttu-id="0ae71-231">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0ae71-231">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ae71-232">有关详细信息，请参阅 [about_CommonParameters](./About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae71-232">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0ae71-233">输入</span><span class="sxs-lookup"><span data-stu-id="0ae71-233">INPUTS</span></span>

### <span data-ttu-id="0ae71-234">System.Management.Automation.Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-234">System.Management.Automation.Job</span></span>

<span data-ttu-id="0ae71-235">可以通过管道将作业对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ae71-235">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="0ae71-236">输出</span><span class="sxs-lookup"><span data-stu-id="0ae71-236">OUTPUTS</span></span>

### <span data-ttu-id="0ae71-237">PSObject</span><span class="sxs-lookup"><span data-stu-id="0ae71-237">PSObject</span></span>

<span data-ttu-id="0ae71-238">此 cmdlet 将返回作业中命令的结果。</span><span class="sxs-lookup"><span data-stu-id="0ae71-238">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="0ae71-239">注释</span><span class="sxs-lookup"><span data-stu-id="0ae71-239">NOTES</span></span>

## <span data-ttu-id="0ae71-240">相关链接</span><span class="sxs-lookup"><span data-stu-id="0ae71-240">RELATED LINKS</span></span>

[<span data-ttu-id="0ae71-241">Get-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-241">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="0ae71-242">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0ae71-242">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0ae71-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-243">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="0ae71-244">Start-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-244">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="0ae71-245">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-245">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="0ae71-246">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="0ae71-246">Wait-Job</span></span>](Wait-Job.md)
