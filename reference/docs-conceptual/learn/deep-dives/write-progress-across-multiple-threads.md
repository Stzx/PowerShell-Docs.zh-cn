---
title: 在多线程处理时显示进度
description: 如何跨多个具有 Foreach-Object -Parallel 的线程使用 Write-Progress
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "89410836"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a><span data-ttu-id="f4f6e-103">跨多个具有 Foreach Parallel 的线程写入进度</span><span class="sxs-lookup"><span data-stu-id="f4f6e-103">Writing Progress across multiple threads with Foreach Parallel</span></span>

<span data-ttu-id="f4f6e-104">从 PowerShell 7.0 开始，可以使用 [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet 中的 Parallel 参数同时处理多个线程。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-104">Starting in PowerShell 7.0, the ability to work in multiple threads simultaneously is possible using the **Parallel** parameter in the [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet.</span></span> <span data-ttu-id="f4f6e-105">但监视这些线程的进度可能有难度。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-105">Monitoring the progress of these threads can be a challenge though.</span></span> <span data-ttu-id="f4f6e-106">通常，可以使用 [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress) 监视进程的进度。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-106">Normally, you can monitor the progress of a process using [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span></span>
<span data-ttu-id="f4f6e-107">但是，由于 PowerShell 在使用 Parallel 时会对每个线程使用单独的运行空间，因此将进度报告给主机不像正常使用 `Write-Progress` 那样简单。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-107">However, since PowerShell uses a separate runspace for each thread when using **Parallel**, reporting the progress back to the host isn't as straight forward as normal use of `Write-Progress`.</span></span>

## <a name="using-a-synced-hashtable-to-track-progress"></a><span data-ttu-id="f4f6e-108">使用同步的哈希表跟踪进度</span><span class="sxs-lookup"><span data-stu-id="f4f6e-108">Using a synced hashtable to track progress</span></span>

<span data-ttu-id="f4f6e-109">从多个线程写入进度时，跟踪会变得比较困难，因为在 PowerShell 中运行并行进程时，每个进程都有其自己的运行空间。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-109">When writing the progress from multiple threads, tracking becomes difficult because when running parallel processes in PowerShell, each process has it's own runspace.</span></span> <span data-ttu-id="f4f6e-110">若要解决此问题，可以使用[同步的哈希表](/dotnet/api/system.collections.hashtable.synchronized)。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-110">To get around this, you can use a [synchronized hashtable](/dotnet/api/system.collections.hashtable.synchronized).</span></span> <span data-ttu-id="f4f6e-111">同步的哈希表是一个线程安全数据结构，可以由多个线程同时进行修改，而不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-111">A synced hashtable is a thread safe data structure that can be modified by multiple threads simultaneously without throwing an error.</span></span>

### <a name="set-up"></a><span data-ttu-id="f4f6e-112">设置</span><span class="sxs-lookup"><span data-stu-id="f4f6e-112">Set up</span></span>

<span data-ttu-id="f4f6e-113">此方法的一个缺点是，它需要进行比较复杂的设置，以确保一切内容正常运行且不会出错。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-113">One of the downsides to this approach is it takes a, somewhat, complex set up to ensure everything runs without error.</span></span>

```powershell
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)
```

<span data-ttu-id="f4f6e-114">本部分创建三个不同的数据结构，用于三种不同的目的。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-114">This section creates three different data structures, for three different purposes.</span></span>

<span data-ttu-id="f4f6e-115">`$dataSet` 变量存储哈希表数组，用于协调后续步骤，从而避免被修改风险。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-115">The `$dataSet` variable stores an array of hashtables that is used to coordinate the next steps without the risk of being modified.</span></span> <span data-ttu-id="f4f6e-116">如果在循环访问对象集合时修改了某个集合，则 PowerShell 将引发错误。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-116">If an object collection is modified while iterating through the collection, PowerShell throws an error.</span></span> <span data-ttu-id="f4f6e-117">必须将循环中的对象集合与要修改的对象分开保存。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-117">You must keep the object collection in the loop separate from the objects being modified.</span></span> <span data-ttu-id="f4f6e-118">每个哈希表中的 `Id` 键都是 mock 进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-118">The `Id` key in each hashtable is the identifier for a mock process.</span></span> <span data-ttu-id="f4f6e-119">`Wait` 键模拟要跟踪的每个 mock 进程的工作负载。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-119">The `Wait` key simulates the workload of each mock process being tracked.</span></span>

<span data-ttu-id="f4f6e-120">`$origin` 变量存储嵌套的哈希表，其中每个键都是 mock 进程的 ID 之一。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-120">The `$origin` variable stores a nested hashtable with each key being one of the mock process id's.</span></span>
<span data-ttu-id="f4f6e-121">该变量用于提取 `$sync` 变量中存储的同步哈希表。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-121">Then, it is used to hydrate the synchronized hashtable stored in the `$sync` variable.</span></span> <span data-ttu-id="f4f6e-122">`$sync` 变量负责向显示进度的父运行空间报告进度。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-122">The `$sync` variable is responsible for reporting the progress back to the parent runspace, which displays the progress.</span></span>

### <a name="running-the-processes"></a><span data-ttu-id="f4f6e-123">运行进程</span><span class="sxs-lookup"><span data-stu-id="f4f6e-123">Running the processes</span></span>

<span data-ttu-id="f4f6e-124">本部分运行多线程进程，并创建一些用于显示进度的输出。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-124">This section runs the multi-threaded processes and creates some of the output used to display progress.</span></span>

```powershell
$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}
```

<span data-ttu-id="f4f6e-125">Mock 进程将被发送到 `Foreach-Object` 并作为作业启动。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-125">The mock processes are sent to `Foreach-Object` and started as jobs.</span></span> <span data-ttu-id="f4f6e-126">ThrottleLimit 设置为 3，以突出显示队列中运行的多个进程 。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-126">The **ThrottleLimit** is set to **3** to highlight running multiple processes in a queue.</span></span> <span data-ttu-id="f4f6e-127">作业存储在 `$job` 变量中，这样我们可以知道稍后所有进程的完成时间。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-127">The jobs are stored in the `$job` variable and allows us to know when all the processes have finished later on.</span></span>

<span data-ttu-id="f4f6e-128">使用 `using:` 语句在 PowerShell 中引用父作用域变量时，不能使用表达式使其动态化。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-128">When using the `using:` statement to reference a parent scope variable in PowerShell, you can't use expressions to make it dynamic.</span></span> <span data-ttu-id="f4f6e-129">例如，如果你尝试创建 `$process` 变量（如 `$process = $using:sync.$($PSItem.id)`），你会收到一条错误消息，指出无法在此处使用表达式。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-129">For example, if you tried to create the `$process` variable like this, `$process = $using:sync.$($PSItem.id)`, you would get an error stating you can't use expressions there.</span></span> <span data-ttu-id="f4f6e-130">因此，我们创建了 `$syncCopy` 变量，以便能够引用和修改 `$sync` 变量，而不会引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-130">So, we create the `$syncCopy` variable to be able to reference and modify the `$sync` variable without the risk of it failing.</span></span>

<span data-ttu-id="f4f6e-131">接下来，我们通过引用同步的哈希表键，使用 `$process` 变量来生成哈希表，以表示当前循环中进程的进度。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-131">Next, we build out a hashtable to represent the progress of the process currently in the loop using the `$process` variable by referencing the synchronized hashtable keys.</span></span> <span data-ttu-id="f4f6e-132">Activity 和 Status 键用作 `Write-Progress` 的参数值，以在下一部分中显示给定 mock 进程的状态 。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-132">The **Activity** and the **Status** keys are used as parameter values for `Write-Progress` to display the status of a given mock process in the next section.</span></span>

<span data-ttu-id="f4f6e-133">`foreach` 循环只是一种模拟进程工作的方式，并且基于 `$dataSet` Wait 属性随机使用毫秒设置 `Start-Sleep`。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-133">The `foreach` loop is just a way to simulate the process working and is randomized based on the `$dataSet` **Wait** attribute to set `Start-Sleep` using milliseconds.</span></span> <span data-ttu-id="f4f6e-134">计算进程进度的方式可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-134">How you calculate the progress of your process may vary.</span></span>

### <a name="displaying-the-progress-of-multiple-processes"></a><span data-ttu-id="f4f6e-135">显示多个进程的进度</span><span class="sxs-lookup"><span data-stu-id="f4f6e-135">Displaying the progress of multiple processes</span></span>

<span data-ttu-id="f4f6e-136">Mock 进程作为作业运行后，我们就可以开始将进程进度写入 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-136">Now that the mock processes are running as jobs, we can start to write the processes progress to the PowerShell window.</span></span>

```powershell
while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

<span data-ttu-id="f4f6e-137">`$job` 变量包含父作业，并为每个 mock 进程提供一个子作业 。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-137">The `$job` variable contains the parent **job** and has a child **job** for each of the mock processes.</span></span> <span data-ttu-id="f4f6e-138">当任何子作业仍在运行时，父作业状态仍将保持为“正在运行”。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-138">While any of the child jobs are still running, the parent job **State** will remain "Running".</span></span> <span data-ttu-id="f4f6e-139">这使我们可以使用 `while` 循环持续更新每个进程的进度，直到完成所有进程。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-139">This allows us to use the `while` loop to continually update the progress of every process until all processes are finished.</span></span>

<span data-ttu-id="f4f6e-140">在 while 循环内，我们循环遍历 `$sync` 变量中的每个键。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-140">Within the while loop, we loop through each of the keys in the `$sync` variable.</span></span> <span data-ttu-id="f4f6e-141">由于这是一个同步的哈希表，因此它会不断更新，但仍可进行访问，且不引发任何错误。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-141">Since this is a synchronized hashtable, it is constantly updated but can still be accessed without throwing any errors.</span></span>

<span data-ttu-id="f4f6e-142">有一项检查可确保正在报告的进程实际上正在使用 `IsNullOrEmpty()` 方法运行。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-142">There is a check to ensure that the process being reported is actually running using the `IsNullOrEmpty()` method.</span></span> <span data-ttu-id="f4f6e-143">如果尚未启动进程，则循环将不会报告该进程并继续转到下一个进程，直到它到达已启动的进程。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-143">If the process hasn't been started, the loop won't report on it and move on to the next until it gets to a process that has been started.</span></span> <span data-ttu-id="f4f6e-144">如果已启动进程，则当前键中的哈希表将用于将参数展开到 `Write-Progress`。</span><span class="sxs-lookup"><span data-stu-id="f4f6e-144">If the process is started, the hashtable from the current key is used to splat the parameters to `Write-Progress`.</span></span>

### <a name="full-example"></a><span data-ttu-id="f4f6e-145">完整示例</span><span class="sxs-lookup"><span data-stu-id="f4f6e-145">Full example</span></span>

```powershell
# Example workload
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)

$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}

while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

## <a name="related-links"></a><span data-ttu-id="f4f6e-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="f4f6e-146">Related Links</span></span>

- [<span data-ttu-id="f4f6e-147">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="f4f6e-147">about_Jobs</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [<span data-ttu-id="f4f6e-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="f4f6e-148">about_Scopes</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [<span data-ttu-id="f4f6e-149">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="f4f6e-149">about_Splatting</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
