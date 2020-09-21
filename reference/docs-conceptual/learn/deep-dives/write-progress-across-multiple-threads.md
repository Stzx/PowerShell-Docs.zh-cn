---
title: 在多线程处理时显示进度
description: 如何跨多个具有 Foreach-Object -Parallel 的线程使用 Write-Progress
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: 640646992955116def23d16dd12c221857d37b68
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "89410836"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a>跨多个具有 Foreach Parallel 的线程写入进度

从 PowerShell 7.0 开始，可以使用 [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet 中的 Parallel 参数同时处理多个线程。 但监视这些线程的进度可能有难度。 通常，可以使用 [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress) 监视进程的进度。
但是，由于 PowerShell 在使用 Parallel 时会对每个线程使用单独的运行空间，因此将进度报告给主机不像正常使用 `Write-Progress` 那样简单。

## <a name="using-a-synced-hashtable-to-track-progress"></a>使用同步的哈希表跟踪进度

从多个线程写入进度时，跟踪会变得比较困难，因为在 PowerShell 中运行并行进程时，每个进程都有其自己的运行空间。 若要解决此问题，可以使用[同步的哈希表](/dotnet/api/system.collections.hashtable.synchronized)。 同步的哈希表是一个线程安全数据结构，可以由多个线程同时进行修改，而不会引发错误。

### <a name="set-up"></a>设置

此方法的一个缺点是，它需要进行比较复杂的设置，以确保一切内容正常运行且不会出错。

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

本部分创建三个不同的数据结构，用于三种不同的目的。

`$dataSet` 变量存储哈希表数组，用于协调后续步骤，从而避免被修改风险。 如果在循环访问对象集合时修改了某个集合，则 PowerShell 将引发错误。 必须将循环中的对象集合与要修改的对象分开保存。 每个哈希表中的 `Id` 键都是 mock 进程的标识符。 `Wait` 键模拟要跟踪的每个 mock 进程的工作负载。

`$origin` 变量存储嵌套的哈希表，其中每个键都是 mock 进程的 ID 之一。
该变量用于提取 `$sync` 变量中存储的同步哈希表。 `$sync` 变量负责向显示进度的父运行空间报告进度。

### <a name="running-the-processes"></a>运行进程

本部分运行多线程进程，并创建一些用于显示进度的输出。

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

Mock 进程将被发送到 `Foreach-Object` 并作为作业启动。 ThrottleLimit 设置为 3，以突出显示队列中运行的多个进程 。 作业存储在 `$job` 变量中，这样我们可以知道稍后所有进程的完成时间。

使用 `using:` 语句在 PowerShell 中引用父作用域变量时，不能使用表达式使其动态化。 例如，如果你尝试创建 `$process` 变量（如 `$process = $using:sync.$($PSItem.id)`），你会收到一条错误消息，指出无法在此处使用表达式。 因此，我们创建了 `$syncCopy` 变量，以便能够引用和修改 `$sync` 变量，而不会引发任何异常。

接下来，我们通过引用同步的哈希表键，使用 `$process` 变量来生成哈希表，以表示当前循环中进程的进度。 Activity 和 Status 键用作 `Write-Progress` 的参数值，以在下一部分中显示给定 mock 进程的状态 。

`foreach` 循环只是一种模拟进程工作的方式，并且基于 `$dataSet` Wait 属性随机使用毫秒设置 `Start-Sleep`。 计算进程进度的方式可能有所不同。

### <a name="displaying-the-progress-of-multiple-processes"></a>显示多个进程的进度

Mock 进程作为作业运行后，我们就可以开始将进程进度写入 PowerShell 窗口。

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

`$job` 变量包含父作业，并为每个 mock 进程提供一个子作业 。 当任何子作业仍在运行时，父作业状态仍将保持为“正在运行”。 这使我们可以使用 `while` 循环持续更新每个进程的进度，直到完成所有进程。

在 while 循环内，我们循环遍历 `$sync` 变量中的每个键。 由于这是一个同步的哈希表，因此它会不断更新，但仍可进行访问，且不引发任何错误。

有一项检查可确保正在报告的进程实际上正在使用 `IsNullOrEmpty()` 方法运行。 如果尚未启动进程，则循环将不会报告该进程并继续转到下一个进程，直到它到达已启动的进程。 如果已启动进程，则当前键中的哈希表将用于将参数展开到 `Write-Progress`。

### <a name="full-example"></a>完整示例

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

## <a name="related-links"></a>相关链接

- [about_Jobs](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [about_Scopes](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [about_Splatting](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
