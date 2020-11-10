---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: e0026749990c665d88b5c9d0c01d22905191dff1
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388784"
---
# <span data-ttu-id="92a21-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-103">Get-Job</span></span>

## <span data-ttu-id="92a21-104">摘要</span><span class="sxs-lookup"><span data-stu-id="92a21-104">SYNOPSIS</span></span>
<span data-ttu-id="92a21-105">获取当前会话中正在运行的 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="92a21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="92a21-106">SYNTAX</span></span>

### <span data-ttu-id="92a21-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="92a21-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="92a21-108">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="92a21-108">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="92a21-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="92a21-109">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="92a21-110">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="92a21-110">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="92a21-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="92a21-111">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="92a21-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="92a21-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="92a21-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="92a21-113">DESCRIPTION</span></span>

<span data-ttu-id="92a21-114">`Get-Job`Cmdlet 可获取表示在当前会话中启动的后台作业的对象。</span><span class="sxs-lookup"><span data-stu-id="92a21-114">The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="92a21-115">你可以使用 `Get-Job` 来获取通过使用 `Start-Job` cmdlet 或通过使用任何 Cmdlet 的 **AsJob** 参数启动的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-115">You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.</span></span>

<span data-ttu-id="92a21-116">如果没有参数，则 `Get-Job` 命令将获取当前会话中的所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-116">Without parameters, a `Get-Job` command gets all jobs in the current session.</span></span> <span data-ttu-id="92a21-117">您可以使用的参数 `Get-Job` 来获取特定作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-117">You can use the parameters of `Get-Job` to get particular jobs.</span></span>

<span data-ttu-id="92a21-118">返回的作业对象 `Get-Job` 包含有关该作业的有用信息，但不包含作业结果。</span><span class="sxs-lookup"><span data-stu-id="92a21-118">The job object that `Get-Job` returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="92a21-119">若要获取结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92a21-119">To get the results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="92a21-120">Windows PowerShell 后台作业是在后台运行的命令，不与当前会话交互。</span><span class="sxs-lookup"><span data-stu-id="92a21-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="92a21-121">通常，可以使用后台作业来运行需要很长时间才能完成的复杂命令。</span><span class="sxs-lookup"><span data-stu-id="92a21-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="92a21-122">有关 Windows PowerShell 中的后台作业的详细信息，请参阅 [about_Jobs](./about/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="92a21-122">For more information about background jobs in Windows PowerShell, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="92a21-123">从 Windows PowerShell 3.0 开始， `Get-Job` cmdlet 还获取自定义作业类型，例如工作流作业和计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="92a21-123">Beginning in Windows PowerShell 3.0, the `Get-Job` cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="92a21-124">若要查找作业的作业类型，请使用该作业的 **PSJobTypeName** 属性。</span><span class="sxs-lookup"><span data-stu-id="92a21-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="92a21-125">若要允许 `Get-Job` 获取自定义作业类型，请在运行命令之前将支持自定义作业类型的模块导入到会话中 `Get-Job` ，方法是使用 `Import-Module` cmdlet 或通过使用或在模块中获取 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92a21-125">To enable `Get-Job` to get a custom job type, import the module that supports the custom job type into the session before you run a `Get-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="92a21-126">有关特定的自定义作业类型的信息，请参阅自定义作业类型功能的文档。</span><span class="sxs-lookup"><span data-stu-id="92a21-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="92a21-127">示例</span><span class="sxs-lookup"><span data-stu-id="92a21-127">EXAMPLES</span></span>

### <span data-ttu-id="92a21-128">示例1：获取当前会话中启动的所有后台作业</span><span class="sxs-lookup"><span data-stu-id="92a21-128">Example 1: Get all background jobs started in the current session</span></span>

<span data-ttu-id="92a21-129">此命令将获取在当前会话中启动的所有后台作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-129">This command gets all background jobs started in the current session.</span></span> <span data-ttu-id="92a21-130">它不包括在其他会话中创建的作业，即使这些作业是在本地计算机上运行的也是如此。</span><span class="sxs-lookup"><span data-stu-id="92a21-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

```
PS C:\> Get-Job
```

### <span data-ttu-id="92a21-131">示例2：使用实例 ID 停止作业</span><span class="sxs-lookup"><span data-stu-id="92a21-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="92a21-132">这些命令演示如何获取作业的实例 ID，然后用它来停止作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span> <span data-ttu-id="92a21-133">与非唯一的作业名称不同，实例 ID 是唯一的。</span><span class="sxs-lookup"><span data-stu-id="92a21-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

<span data-ttu-id="92a21-134">第一个命令使用 `Get-Job` cmdlet 来获取作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-134">The first command uses the `Get-Job` cmdlet to get a job.</span></span> <span data-ttu-id="92a21-135">它使用 **Name** 参数来标识作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-135">It uses the **Name** parameter to identify the job.</span></span> <span data-ttu-id="92a21-136">此命令存储 `Get-Job` 在变量中返回的作业对象 `$j` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-136">The command stores the job object that `Get-Job` returns in the `$j` variable.</span></span> <span data-ttu-id="92a21-137">在此示例中，只有一个作业具有指定的名称。</span><span class="sxs-lookup"><span data-stu-id="92a21-137">In this example, there is only one job with the specified name.</span></span> <span data-ttu-id="92a21-138">第二个命令获取变量中的对象的 **InstanceId** 属性 `$j` ，并将其存储在 `$ID` 变量中。</span><span class="sxs-lookup"><span data-stu-id="92a21-138">The second command gets the **InstanceId** property of the object in the `$j` variable and stores it in the `$ID` variable.</span></span> <span data-ttu-id="92a21-139">第三个命令显示变量的值 `$ID` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-139">The third command displays the value of the `$ID` variable.</span></span> <span data-ttu-id="92a21-140">第四个命令使用 `Stop-Job` cmdlet 来停止作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-140">The fourth command uses `Stop-Job` cmdlet to stop the job.</span></span>
<span data-ttu-id="92a21-141">它使用 **InstanceId** 参数来标识作业，使用 `$ID` 变量来表示作业的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="92a21-141">It uses the **InstanceId** parameter to identify the job and `$ID` variable to represent the instance ID of the job.</span></span>

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### <span data-ttu-id="92a21-142">示例3：获取包含特定命令的作业</span><span class="sxs-lookup"><span data-stu-id="92a21-142">Example 3: Get jobs that include a specific command</span></span>

<span data-ttu-id="92a21-143">此命令获取系统中包含命令的作业 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-143">This command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="92a21-144">命令使用的 **命令** 参数 `Get-Job` 来限制检索的作业数。</span><span class="sxs-lookup"><span data-stu-id="92a21-144">The command uses the **Command** parameter of `Get-Job` to limit the jobs retrieved.</span></span> <span data-ttu-id="92a21-145">该命令使用通配符 (`*`) 来获取 `Get-Process` 在命令字符串中的任意位置包含一个命令的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-145">The command uses wildcard characters (`*`) to get jobs that include a `Get-Process` command anywhere in the command string.</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

### <span data-ttu-id="92a21-146">示例4：使用管道获取包含特定命令的作业</span><span class="sxs-lookup"><span data-stu-id="92a21-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

<span data-ttu-id="92a21-147">与上一示例中的命令一样，此命令获取系统中包含命令的作业 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-147">Like the command in the previous example, this command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="92a21-148">该命令使用管道运算符 (`|`) 将字符串（在引号中）发送到 `Get-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92a21-148">The command uses a pipeline operator (`|`) to send a string, in quotation marks, to the `Get-Job` cmdlet.</span></span> <span data-ttu-id="92a21-149">它等效于之前的命令。</span><span class="sxs-lookup"><span data-stu-id="92a21-149">It is the equivalent of the previous command.</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

### <span data-ttu-id="92a21-150">示例5：获取尚未启动的作业</span><span class="sxs-lookup"><span data-stu-id="92a21-150">Example 5: Get jobs that have not been started</span></span>

<span data-ttu-id="92a21-151">此命令只获取那些已创建的但尚未启动的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-151">This command gets only those jobs that have been created but have not yet been started.</span></span> <span data-ttu-id="92a21-152">这包括计划要在将来运行的作业和尚未计划的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

```
PS C:\> Get-Job -State NotStarted
```

### <span data-ttu-id="92a21-153">示例6：获取未分配名称的作业</span><span class="sxs-lookup"><span data-stu-id="92a21-153">Example 6: Get jobs that have not been assigned a name</span></span>

<span data-ttu-id="92a21-154">此命令获取作业名称以 job 开头的所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-154">This command gets all jobs that have job names that begin with job.</span></span> <span data-ttu-id="92a21-155">由于 `job<number>` 是作业的默认名称，因此此命令将获取没有显式分配的名称的所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-155">Because `job<number>` is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

```
PS C:\> Get-Job -Name Job*
```

### <span data-ttu-id="92a21-156">示例7：在命令中使用作业对象来表示作业</span><span class="sxs-lookup"><span data-stu-id="92a21-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="92a21-157">此示例演示如何使用 `Get-Job` 来获取作业对象，并演示如何在命令中使用作业对象来表示作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-157">This example shows how to use `Get-Job` to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

<span data-ttu-id="92a21-158">第一个命令使用 `Start-Job` cmdlet 来启动在 `Get-Process` 本地计算机上运行命令的后台作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-158">The first command uses the `Start-Job` cmdlet to start a background job that runs a `Get-Process` command on the local computer.</span></span> <span data-ttu-id="92a21-159">该命令使用的 **Name** 参数 `Start-Job` 为作业指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="92a21-159">The command uses the **Name** parameter of `Start-Job` to assign a friendly name to the job.</span></span> <span data-ttu-id="92a21-160">第二个命令使用 `Get-Job` 来获取作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-160">The second command uses `Get-Job` to get the job.</span></span> <span data-ttu-id="92a21-161">它使用的 **Name** 参数 `Get-Job` 来标识作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-161">It uses the **Name** parameter of `Get-Job` to identify the job.</span></span> <span data-ttu-id="92a21-162">该命令将生成的作业对象保存在 `$j` 变量中。</span><span class="sxs-lookup"><span data-stu-id="92a21-162">The command saves the resulting job object in the `$j` variable.</span></span> <span data-ttu-id="92a21-163">第三个命令显示变量中的作业对象的值 `$j` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-163">The third command displays the value of the job object in the `$j` variable.</span></span> <span data-ttu-id="92a21-164">" **状态** " 属性的值显示作业已完成。</span><span class="sxs-lookup"><span data-stu-id="92a21-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="92a21-165">**HasMoreData** 属性的值显示尚未检索的作业中存在可检索的结果。</span><span class="sxs-lookup"><span data-stu-id="92a21-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span> <span data-ttu-id="92a21-166">第四个命令使用 `Receive-Job` cmdlet 来获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="92a21-166">The fourth command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="92a21-167">它使用变量中的作业对象 `$j` 来表示作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-167">It uses the job object in the `$j` variable to represent the job.</span></span> <span data-ttu-id="92a21-168">你还可以使用管道运算符将作业对象发送到 `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-168">You can also use a pipeline operator to send a job object to `Receive-Job`.</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### <span data-ttu-id="92a21-169">示例8：获取所有作业，包括其他方法启动的作业</span><span class="sxs-lookup"><span data-stu-id="92a21-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="92a21-170">此示例演示该 `Get-Job` cmdlet 可获取在当前会话中启动的所有作业，即使这些作业是使用不同的方法启动的。</span><span class="sxs-lookup"><span data-stu-id="92a21-170">This example demonstrates that the `Get-Job` cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

<span data-ttu-id="92a21-171">第一个命令使用 `Start-Job` cmdlet 在本地计算机上启动作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-171">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="92a21-172">第二个命令使用 cmdlet 的 **AsJob** 参数 `Invoke-Command` 在 S1 计算机上启动作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-172">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="92a21-173">虽然作业中的命令在远程计算机上运行，但该作业对象是在本地计算机上创建的，所以应使用本地命令来管理该作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span> <span data-ttu-id="92a21-174">第三个命令使用 `Invoke-Command` cmdlet `Start-Job` 在 S2 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="92a21-174">The third command uses the `Invoke-Command` cmdlet to run a `Start-Job` command on the S2 computer.</span></span> <span data-ttu-id="92a21-175">通过使用此方法，将在远程计算机上创建作业对象，因此你可以使用远程命令来管理该作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span> <span data-ttu-id="92a21-176">第四个命令使用 `Get-Job` 来获取存储在本地计算机上的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-176">The fourth command uses `Get-Job` to get the jobs stored on the local computer.</span></span> <span data-ttu-id="92a21-177">Windows PowerShell 3.0 中引入的作业的 **PSJobTypeName** 属性显示，使用 cmdlet 启动的本地作业 `Start-Job` 是后台作业，使用 cmdlet 在远程会话中启动的作业 `Invoke-Command` 是远程作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the `Start-Job` cmdlet is a background job and the job started in a remote session by using the `Invoke-Command` cmdlet is a remote job.</span></span> <span data-ttu-id="92a21-178">第五个命令使用 `Invoke-Command` `Get-Job` 在 S2 计算机上运行命令。示例输出显示了该命令的结果 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-178">The fifth command uses `Invoke-Command` to run a `Get-Job` command on the S2 computer.The sample output shows the results of the `Get-Job` command.</span></span> <span data-ttu-id="92a21-179">在 S2 计算机上，该作业看起来像是本地作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="92a21-180">计算机名称为 localhost，作业类型为后台作业。有关如何在远程计算机上运行后台作业的详细信息，请参阅 [about_Remote_Jobs](./about/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="92a21-180">The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### <span data-ttu-id="92a21-181">示例9：调查失败的作业</span><span class="sxs-lookup"><span data-stu-id="92a21-181">Example 9: Investigate a failed job</span></span>

<span data-ttu-id="92a21-182">此命令演示如何使用返回的作业对象 `Get-Job` 来调查作业失败的原因。</span><span class="sxs-lookup"><span data-stu-id="92a21-182">This command shows how to use the job object that `Get-Job` returns to investigate why a job failed.</span></span>
<span data-ttu-id="92a21-183">此命令还显示了如何获取每个作业的子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-183">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="92a21-184">第一个命令使用 `Start-Job` cmdlet 在本地计算机上启动作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-184">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="92a21-185">返回的作业对象 `Start-Job` 显示作业失败。</span><span class="sxs-lookup"><span data-stu-id="92a21-185">The job object that `Start-Job` returns shows that the job failed.</span></span> <span data-ttu-id="92a21-186">**State** 属性的值失败。</span><span class="sxs-lookup"><span data-stu-id="92a21-186">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="92a21-187">第二个命令使用 `Get-Job` cmdlet 来获取作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-187">The second command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="92a21-188">该命令使用点法获取对象的 **JobStateInfo** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="92a21-188">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="92a21-189">它使用管道运算符将 **JobStateInfo** 属性中的对象发送给 `Format-List` cmdlet，该 cmdlet 将对象的所有属性的格式设置为 `*` 列表中的)  (。此命令的结果 `Format-List` 显示作业的 " **原因** " 属性值为空。</span><span class="sxs-lookup"><span data-stu-id="92a21-189">It uses a pipeline operator to send the object in the **JobStateInfo** property to the `Format-List` cmdlet, which formats all of the properties of the object (`*`) in a list.The result of the `Format-List` command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="92a21-190">第三个命令调查更多。</span><span class="sxs-lookup"><span data-stu-id="92a21-190">The third command investigates more.</span></span> <span data-ttu-id="92a21-191">它使用 `Get-Job` 命令获取作业，然后使用管道运算符将整个作业对象发送给 `Format-List` cmdlet，该 cmdlet 将在列表中显示作业的所有属性。作业对象中所有属性的显示显示作业包含一个名为 Job2 的子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-191">It uses a `Get-Job` command to get the job and then uses a pipeline operator to send the whole job object to the `Format-List` cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="92a21-192">第四个命令使用 `Get-Job` 获取表示 Job2 子作业的作业对象。</span><span class="sxs-lookup"><span data-stu-id="92a21-192">The fourth command uses `Get-Job` to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="92a21-193">命令实际在该作业中运行。</span><span class="sxs-lookup"><span data-stu-id="92a21-193">This is the job in which the command actually ran.</span></span> <span data-ttu-id="92a21-194">它使用点方法获取 **JobStateInfo** 属性的 **原因** 属性。结果显示作业由于拒绝访问错误而失败。</span><span class="sxs-lookup"><span data-stu-id="92a21-194">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="92a21-195">在这种情况下，用户会忘记使用 Windows PowerShell 的 "以管理员身份运行" 选项。因为后台作业使用 Windows PowerShell 的远程处理功能，所以必须将计算机配置为进行远程处理以运行作业，即使该作业在本地计算机上运行也是如此。有关 Windows PowerShell 中的远程处理要求的信息，请参阅 [about_Remote_Requirements](./about/about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92a21-195">In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span></span> <span data-ttu-id="92a21-196">有关疑难解答提示，请参阅 [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="92a21-196">For troubleshooting tips, see [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### <span data-ttu-id="92a21-197">示例10：获取筛选的结果</span><span class="sxs-lookup"><span data-stu-id="92a21-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="92a21-198">此示例显示如何使用 **Filter** 参数获取工作流作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-198">This example shows how to use the **Filter** parameter to get a workflow job.</span></span> <span data-ttu-id="92a21-199">在 Windows PowerShell 3.0 中引入的 **Filter** 参数仅在自定义作业类型（例如工作流作业和计划作业）上有效。</span><span class="sxs-lookup"><span data-stu-id="92a21-199">The **Filter** parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

<span data-ttu-id="92a21-200">第一个命令使用 **workflow** 关键字创建 WFProcess 工作流。</span><span class="sxs-lookup"><span data-stu-id="92a21-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span> <span data-ttu-id="92a21-201">第二个命令使用 WFProcess 工作流的 **AsJob** 参数将工作流作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="92a21-201">The second command uses the **AsJob** parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="92a21-202">该命令使用工作流的 **JobName** 参数为作业指定名称，并使用工作流的 **PSPrivateMetadata** 参数指定自定义 ID。</span><span class="sxs-lookup"><span data-stu-id="92a21-202">It uses the **JobName** parameter of the workflow to specify a name for the job, and the **PSPrivateMetadata** parameter of the workflow to specify a custom ID.</span></span> <span data-ttu-id="92a21-203">第三个命令使用的 **筛选器** 参数 `Get-Job` 通过在 **PSPrivateMetadata** 参数中指定的自定义 ID 获取作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-203">The third command uses the **Filter** parameter of `Get-Job` to get the job by custom ID that was specified in the **PSPrivateMetadata** parameter.</span></span>

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### <span data-ttu-id="92a21-204">示例11：获取有关子作业的信息</span><span class="sxs-lookup"><span data-stu-id="92a21-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="92a21-205">此示例演示使用 cmdlet 的 **IncludeChildJob** 和 **ChildJobState** 参数的效果 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-205">This example shows the effect of using the **IncludeChildJob** and **ChildJobState** parameters of the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="92a21-206">第一个命令获取当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="92a21-207">输出包括一个后台作业、一个远程作业和一个计划作业的几个实例。</span><span class="sxs-lookup"><span data-stu-id="92a21-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="92a21-208">远程作业 Job4 显示为已失败。</span><span class="sxs-lookup"><span data-stu-id="92a21-208">The remote job, Job4, appears to have failed.</span></span>
<span data-ttu-id="92a21-209">第二个命令使用的 **IncludeChildJob** 参数 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-209">The second command uses the **IncludeChildJob** parameter of `Get-Job`.</span></span> <span data-ttu-id="92a21-210">输出添加具有子作业的所有作业的子作业。在这种情况下，修改后的输出显示只有 Job4 的 Job5 子作业失败。</span><span class="sxs-lookup"><span data-stu-id="92a21-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span> <span data-ttu-id="92a21-211">第三个命令使用值为 "Failed" 的 **ChildJobState** 参数。输出中包括所有父作业和失败的子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-211">The third command uses the **ChildJobState** parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span> <span data-ttu-id="92a21-212">第五个命令使用作业的 **JobStateInfo** 属性及其 **Reason** 属性来发现 Job5 失败的原因。</span><span class="sxs-lookup"><span data-stu-id="92a21-212">The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

<span data-ttu-id="92a21-213">有关详细信息，请参阅 [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="92a21-213">For more information, see the [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Help topic.</span></span>

## <span data-ttu-id="92a21-214">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="92a21-214">PARAMETERS</span></span>

### <span data-ttu-id="92a21-215">-After</span><span class="sxs-lookup"><span data-stu-id="92a21-215">-After</span></span>

<span data-ttu-id="92a21-216">获取在指定日期和时间后结束完成的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-216">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="92a21-217">输入一个 **DateTime** 对象，如 cmdlet 返回的一个 `Get-Date` 或可转换为 **DateTime** 对象的字符串（例如或） `Dec 1, 2012 2:00 AM` `11/06` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-217">Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="92a21-218">此参数仅适用于具有 **EndTime** 属性的自定义作业类型（例如工作流作业和计划作业）。</span><span class="sxs-lookup"><span data-stu-id="92a21-218">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="92a21-219">它不适用于标准后台作业，如使用 cmdlet 创建的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-219">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="92a21-220">有关支持此参数的信息，请参阅作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="92a21-220">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="92a21-221">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-222">-Before</span><span class="sxs-lookup"><span data-stu-id="92a21-222">-Before</span></span>

<span data-ttu-id="92a21-223">获取在指定日期和时间前结束前完成的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-223">Gets completed jobs that ended before the specified date and time.</span></span> <span data-ttu-id="92a21-224">输入 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="92a21-224">Enter a **DateTime** object.</span></span>

<span data-ttu-id="92a21-225">此参数仅适用于具有 **EndTime** 属性的自定义作业类型（例如工作流作业和计划作业）。</span><span class="sxs-lookup"><span data-stu-id="92a21-225">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="92a21-226">它不适用于标准后台作业，如使用 cmdlet 创建的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-226">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="92a21-227">有关支持此参数的信息，请参阅作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="92a21-227">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="92a21-228">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-229">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="92a21-229">-ChildJobState</span></span>

<span data-ttu-id="92a21-230">只获取具有指定状态的子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-230">Gets only the child jobs that have the specified state.</span></span> <span data-ttu-id="92a21-231">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="92a21-231">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="92a21-232">NotStarted</span><span class="sxs-lookup"><span data-stu-id="92a21-232">NotStarted</span></span>
- <span data-ttu-id="92a21-233">正在运行</span><span class="sxs-lookup"><span data-stu-id="92a21-233">Running</span></span>
- <span data-ttu-id="92a21-234">已完成</span><span class="sxs-lookup"><span data-stu-id="92a21-234">Completed</span></span>
- <span data-ttu-id="92a21-235">已失败</span><span class="sxs-lookup"><span data-stu-id="92a21-235">Failed</span></span>
- <span data-ttu-id="92a21-236">已停止</span><span class="sxs-lookup"><span data-stu-id="92a21-236">Stopped</span></span>
- <span data-ttu-id="92a21-237">已阻止</span><span class="sxs-lookup"><span data-stu-id="92a21-237">Blocked</span></span>
- <span data-ttu-id="92a21-238">Suspended</span><span class="sxs-lookup"><span data-stu-id="92a21-238">Suspended</span></span>
- <span data-ttu-id="92a21-239">已断开连接</span><span class="sxs-lookup"><span data-stu-id="92a21-239">Disconnected</span></span>
- <span data-ttu-id="92a21-240">正在暂停</span><span class="sxs-lookup"><span data-stu-id="92a21-240">Suspending</span></span>
- <span data-ttu-id="92a21-241">正在停止</span><span class="sxs-lookup"><span data-stu-id="92a21-241">Stopping</span></span>

<span data-ttu-id="92a21-242">默认情况下，不 `Get-Job` 获取子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-242">By default, `Get-Job` does not get child jobs.</span></span> <span data-ttu-id="92a21-243">使用 **IncludeChildJob** 参数 `Get-Job` 获取所有子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-243">By using the **IncludeChildJob** parameter, `Get-Job` gets all child jobs.</span></span> <span data-ttu-id="92a21-244">如果使用 **ChildJobState** 参数，则 **IncludeChildJob** 参数将不起作用。</span><span class="sxs-lookup"><span data-stu-id="92a21-244">If you use the **ChildJobState** parameter, the **IncludeChildJob** parameter has no effect.</span></span>

<span data-ttu-id="92a21-245">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-245">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-246">-Command</span><span class="sxs-lookup"><span data-stu-id="92a21-246">-Command</span></span>

<span data-ttu-id="92a21-247">将命令数组指定为字符串。</span><span class="sxs-lookup"><span data-stu-id="92a21-247">Specifies an array of commands as strings.</span></span> <span data-ttu-id="92a21-248">此 cmdlet 将获取包含指定命令的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-248">This cmdlet gets the jobs that include the specified commands.</span></span> <span data-ttu-id="92a21-249">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-249">The default is all jobs.</span></span> <span data-ttu-id="92a21-250">您可以使用通配符来指定命令模式。</span><span class="sxs-lookup"><span data-stu-id="92a21-250">You can use wildcard characters to specify a command pattern.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="92a21-251">-Filter</span><span class="sxs-lookup"><span data-stu-id="92a21-251">-Filter</span></span>

<span data-ttu-id="92a21-252">指定条件的哈希表。</span><span class="sxs-lookup"><span data-stu-id="92a21-252">Specifies a hash table of conditions.</span></span> <span data-ttu-id="92a21-253">此 cmdlet 将获取满足所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-253">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="92a21-254">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="92a21-254">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="92a21-255">此参数仅适用于自定义作业类型，例如工作流作业和计划作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-255">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="92a21-256">它不适用于标准后台作业，如使用 cmdlet 创建的作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-256">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="92a21-257">有关支持此参数的信息，请参阅作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="92a21-257">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="92a21-258">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="92a21-259">-HasMoreData</span><span class="sxs-lookup"><span data-stu-id="92a21-259">-HasMoreData</span></span>

<span data-ttu-id="92a21-260">指示此 cmdlet 是否仅获取具有指定的 **HasMoreData** 属性值的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-260">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="92a21-261">**HasMoreData** 属性指示当前会话中是否已接收所有作业结果。</span><span class="sxs-lookup"><span data-stu-id="92a21-261">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span> <span data-ttu-id="92a21-262">若要获取具有更多结果的作业，请将值指定为 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-262">To get jobs that have more results, specify a value of `$True`.</span></span> <span data-ttu-id="92a21-263">若要获取没有更多结果的作业，请将值指定为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-263">To get jobs that do not have more results, specify a value of `$False`.</span></span>

<span data-ttu-id="92a21-264">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92a21-264">To get the results of a job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="92a21-265">当使用 cmdlet 时 `Receive-Job` ，它会将其返回的结果从其内存中的特定于会话的存储中删除。</span><span class="sxs-lookup"><span data-stu-id="92a21-265">When you use the `Receive-Job` cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="92a21-266">在当前会话中返回作业的所有结果后，它会将作业的 **HasMoreData** 属性的值设置为 `$False`) ，以指示它在当前会话中没有更多的作业结果。</span><span class="sxs-lookup"><span data-stu-id="92a21-266">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to `$False`) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="92a21-267">使用 **Keep** 参数 `Receive-Job` 禁止 `Receive-Job` 删除结果并更改 **HasMoreData** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="92a21-267">Use the **Keep** parameter of `Receive-Job` to prevent `Receive-Job` from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="92a21-268">要了解详情，请键入 `Get-Help Receive-Job`。</span><span class="sxs-lookup"><span data-stu-id="92a21-268">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="92a21-269">**HasMoreData** 属性特定于当前会话。</span><span class="sxs-lookup"><span data-stu-id="92a21-269">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="92a21-270">如果自定义作业类型的结果保存在会话之外（例如计划作业类型，这会将作业结果保存在磁盘上），则可以使用 `Receive-Job` 其他会话中的 cmdlet 再次获取作业结果，即使 **HasMoreData** 的值为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-270">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the `Receive-Job` cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is `$False`.</span></span> <span data-ttu-id="92a21-271">有关详细信息，请参阅自定义作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="92a21-271">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="92a21-272">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-273">-Id</span><span class="sxs-lookup"><span data-stu-id="92a21-273">-Id</span></span>

<span data-ttu-id="92a21-274">指定此 cmdlet 获取的作业 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="92a21-274">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="92a21-275">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-275">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="92a21-276">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="92a21-276">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="92a21-277">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="92a21-277">You can type one or more IDs separated by commas.</span></span> <span data-ttu-id="92a21-278">若要查找作业的 ID，请键入（ `Get-Job` 不带参数）。</span><span class="sxs-lookup"><span data-stu-id="92a21-278">To find the ID of a job, type `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-279">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="92a21-279">-IncludeChildJob</span></span>

<span data-ttu-id="92a21-280">指示除了父作业，此 cmdlet 还将返回子作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-280">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="92a21-281">此参数对于调查工作流作业（其 `Get-Job` 返回容器父作业和作业失败）特别有用，因为失败的原因保存在子作业的属性中。</span><span class="sxs-lookup"><span data-stu-id="92a21-281">This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="92a21-282">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-283">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="92a21-283">-InstanceId</span></span>

<span data-ttu-id="92a21-284">指定此 cmdlet 获取的作业的实例 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="92a21-284">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span> <span data-ttu-id="92a21-285">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-285">The default is all jobs.</span></span>

<span data-ttu-id="92a21-286">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-286">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="92a21-287">若要查找作业的实例 ID，请使用 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-287">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="92a21-288">-Name</span><span class="sxs-lookup"><span data-stu-id="92a21-288">-Name</span></span>

<span data-ttu-id="92a21-289">指定此 cmdlet 获取的实例的友好名称的数组。</span><span class="sxs-lookup"><span data-stu-id="92a21-289">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span> <span data-ttu-id="92a21-290">输入作业名称，或使用通配符输入作业名称模式。</span><span class="sxs-lookup"><span data-stu-id="92a21-290">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span> <span data-ttu-id="92a21-291">默认情况下， `Get-Job` 获取当前会话中的所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-291">By default, `Get-Job` gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="92a21-292">-Newest</span><span class="sxs-lookup"><span data-stu-id="92a21-292">-Newest</span></span>

<span data-ttu-id="92a21-293">指定要获取的作业数。</span><span class="sxs-lookup"><span data-stu-id="92a21-293">Specifies a number of jobs to get.</span></span> <span data-ttu-id="92a21-294">此 cmdlet 将获取最近结束的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-294">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="92a21-295">**Newest** 参数不会按结束时间的顺序对输出进行排序或返回最新的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-295">The **Newest** parameter does not sort or return the newest jobs in end-time order.</span></span> <span data-ttu-id="92a21-296">若要对输出进行排序，请使用 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92a21-296">To sort the output, use the `Sort-Object` cmdlet.</span></span>

<span data-ttu-id="92a21-297">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="92a21-297">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92a21-298">-State</span><span class="sxs-lookup"><span data-stu-id="92a21-298">-State</span></span>

<span data-ttu-id="92a21-299">指定作业状态。</span><span class="sxs-lookup"><span data-stu-id="92a21-299">Specifies a job state.</span></span> <span data-ttu-id="92a21-300">此 cmdlet 仅获取处于指定状态的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-300">This cmdlet gets only jobs in the specified state.</span></span> <span data-ttu-id="92a21-301">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="92a21-301">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="92a21-302">NotStarted</span><span class="sxs-lookup"><span data-stu-id="92a21-302">NotStarted</span></span>
- <span data-ttu-id="92a21-303">正在运行</span><span class="sxs-lookup"><span data-stu-id="92a21-303">Running</span></span>
- <span data-ttu-id="92a21-304">已完成</span><span class="sxs-lookup"><span data-stu-id="92a21-304">Completed</span></span>
- <span data-ttu-id="92a21-305">已失败</span><span class="sxs-lookup"><span data-stu-id="92a21-305">Failed</span></span>
- <span data-ttu-id="92a21-306">已停止</span><span class="sxs-lookup"><span data-stu-id="92a21-306">Stopped</span></span>
- <span data-ttu-id="92a21-307">已阻止</span><span class="sxs-lookup"><span data-stu-id="92a21-307">Blocked</span></span>
- <span data-ttu-id="92a21-308">Suspended</span><span class="sxs-lookup"><span data-stu-id="92a21-308">Suspended</span></span>
- <span data-ttu-id="92a21-309">已断开连接</span><span class="sxs-lookup"><span data-stu-id="92a21-309">Disconnected</span></span>
- <span data-ttu-id="92a21-310">正在暂停</span><span class="sxs-lookup"><span data-stu-id="92a21-310">Suspending</span></span>
- <span data-ttu-id="92a21-311">正在停止</span><span class="sxs-lookup"><span data-stu-id="92a21-311">Stopping</span></span>

<span data-ttu-id="92a21-312">默认情况下， `Get-Job` 获取当前会话中的所有作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-312">By default, `Get-Job` gets all the jobs in the current session.</span></span>

<span data-ttu-id="92a21-313">有关作业状态的详细信息，请参阅 [JobState 枚举](/dotnet/api/system.management.automation.jobstate)。</span><span class="sxs-lookup"><span data-stu-id="92a21-313">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="92a21-314">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="92a21-314">CommonParameters</span></span>

<span data-ttu-id="92a21-315">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="92a21-315">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="92a21-316">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="92a21-316">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="92a21-317">输入</span><span class="sxs-lookup"><span data-stu-id="92a21-317">INPUTS</span></span>

### <span data-ttu-id="92a21-318">无</span><span class="sxs-lookup"><span data-stu-id="92a21-318">None</span></span>

<span data-ttu-id="92a21-319">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92a21-319">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="92a21-320">输出</span><span class="sxs-lookup"><span data-stu-id="92a21-320">OUTPUTS</span></span>

### <span data-ttu-id="92a21-321">System.Management.Automation.RemotingJob</span><span class="sxs-lookup"><span data-stu-id="92a21-321">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="92a21-322">此 cmdlet 将返回表示会话中的作业的对象。</span><span class="sxs-lookup"><span data-stu-id="92a21-322">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="92a21-323">注释</span><span class="sxs-lookup"><span data-stu-id="92a21-323">NOTES</span></span>

<span data-ttu-id="92a21-324">作业的 **PSJobTypeName** 属性指示作业的作业类型。</span><span class="sxs-lookup"><span data-stu-id="92a21-324">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="92a21-325">该属性值由作业类型的作者确定。</span><span class="sxs-lookup"><span data-stu-id="92a21-325">The property value is determined by the job type author.</span></span> <span data-ttu-id="92a21-326">以下列表显示了常见作业类型。</span><span class="sxs-lookup"><span data-stu-id="92a21-326">The following list shows common job types.</span></span>

- <span data-ttu-id="92a21-327">**BackgroundJob** 。</span><span class="sxs-lookup"><span data-stu-id="92a21-327">**BackgroundJob**.</span></span> <span data-ttu-id="92a21-328">使用启动的本地作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-328">Local job started by using `Start-Job`.</span></span>
- <span data-ttu-id="92a21-329">**RemoteJob** 。</span><span class="sxs-lookup"><span data-stu-id="92a21-329">**RemoteJob**.</span></span> <span data-ttu-id="92a21-330">使用 cmdlet 的 **AsJob** 参数在 **PSSession** 中启动作业 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="92a21-330">Job started in a **PSSession** by using the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span>
- <span data-ttu-id="92a21-331">**PSWorkflowJob** 。</span><span class="sxs-lookup"><span data-stu-id="92a21-331">**PSWorkflowJob**.</span></span> <span data-ttu-id="92a21-332">通过使用工作流的 **AsJob** 通用参数启动的作业。</span><span class="sxs-lookup"><span data-stu-id="92a21-332">Job started by using the **AsJob** common parameter of workflows.</span></span>

## <span data-ttu-id="92a21-333">相关链接</span><span class="sxs-lookup"><span data-stu-id="92a21-333">RELATED LINKS</span></span>

[<span data-ttu-id="92a21-334">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="92a21-334">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="92a21-335">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-335">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="92a21-336">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-336">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="92a21-337">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-337">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="92a21-338">Start-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-338">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="92a21-339">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-339">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="92a21-340">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-340">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="92a21-341">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="92a21-341">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="92a21-342">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="92a21-342">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="92a21-343">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="92a21-343">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="92a21-344">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="92a21-344">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="92a21-345">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="92a21-345">about_Scheduled_Jobs</span></span>](../PSScheduledJob/About/about_Scheduled_Jobs.md)
