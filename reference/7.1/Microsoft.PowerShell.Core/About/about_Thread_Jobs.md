---
description: 提供有关基于 PowerShell 线程的作业的信息。 线程作业是一种后台作业，它在当前会话进程中的单独线程中运行命令或表达式。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: d3f7c2754a2e54bc1b6f9fb95d1cf6ce2fed5b9b
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "93200578"
---
# <a name="about-thread-jobs"></a>关于线程作业

## <a name="short-description"></a>简短说明

提供有关基于 PowerShell 线程的作业的信息。 线程作业是一种后台作业，它在当前会话进程中的单独线程中运行命令或表达式。

## <a name="long-description"></a>长说明

本文介绍如何在本地计算机上的 PowerShell 中运行线程作业。
有关在本地计算机上运行后台作业的信息，请参阅 [about_Jobs](about_Jobs.md)。

可以通过以下两种方式之一来启动线程作业。

第一种方法是 `Start-ThreadJob` cmdlet。 此 cmdlet 在 PowerShell 随附的 **ThreadJob** 模块中提供。 `Start-ThreadJob` 返回一个作业对象，该对象封装正在运行的命令或脚本，可与所有 PowerShell 作业操作 cmdlet 一起使用。

第二种方法是与 cmdlet 一起，同时提供参数 `ForEach-Object` `-Parallel` script 块参数和 `-AsJob` 参数开关。 此 cmdlet 将返回单个 (父) 作业对象，该对象包含用于传递到 cmdlet 的每个输入的子作业。 每个子作业都在一个单独的线程中运行脚本， `-ThrottleLimit`) 限制为在给定时间运行的子作业的 (。

## <a name="the-job-cmdlets"></a>作业 CMDLET

|Cmdlet           |说明                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|在本地计算机上启动线程作业。               |
|`ForEach-Object` |为每个管道输入对象启动线程作业，时间为   |
|                 |与并行和-AsJob 参数一起使用。             |
|`Get-Job`        |获取在当前会话中启动的作业。|
|`Receive-Job`    |获取作业的结果。                              |
|`Stop-Job`       |停止正在运行的作业。                                   |
|`Wait-Job`       |禁止显示命令提示符，直到其中一个或所有作业都为|
|                 |完成.                                              |
|`Remove-Job`     |删除作业。                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a>如何在本地计算机上启动线程作业

若要在本地计算机上启动线程作业，请使用 `Start-ThreadJob` cmdlet。

若要编写 `Start-ThreadJob` 命令，请将该命令或脚本括在大括号中， (`{ }`) 。

下面的命令启动在 `Get-Process` 本地计算机上运行命令的线程作业。

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

该 `Start-ThreadJob` 命令将返回一个 `ThreadJob` 对象，该对象表示正在运行的作业。 作业对象包含有关作业的有用信息，包括作业的当前运行状态。 它在生成结果时收集作业的结果。

若要将 `ForEach-Object -Parallel` 命令、管道数据写入命令，并将该命令或脚本括在大括号中， (`{}`) 。 使用 `-AsJob` 参数开关，以便返回一个作业对象。

下面的命令启动一个作业，该作业包含向命令传递的每个输入值的子作业。 每个子作业都将 `Write-Output` 使用一个管道输入值作为参数来运行该命令。

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

该 `ForEach-Object -Parallel` 命令将返回一个 `PSTaskJob` 对象，该对象包含每个管道输入值的子作业。 作业对象包含有关子作业运行状态的有用信息。 它在生成结果时收集子作业的结果。

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a>如何等待作业完成并检索作业结果

你可以使用 PowerShell 作业 cmdlet （如 `Wait-Job` 和） `Receive-Job` 等待作业完成，然后返回作业生成的所有结果。

下面的命令启动一个运行命令的线程作业 `Get-Process` ，然后等待该命令完成，最后返回该命令生成的所有数据结果。

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

下面的命令启动一个作业，该作业 `Write-Output` 对每个管道输入运行一个命令，然后等待所有子作业完成，最后返回子作业生成的所有数据结果。

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

`Receive-Job`Cmdlet 返回子作业的结果。

```powershell
1
3
2
4
5
```

由于每个子作业都是并行运行的，因此不保证生成的结果的顺序。

## <a name="powershell-concurrency-and-jobs"></a>PowerShell 并发和作业

PowerShell 并发运行命令，并通过作业编写脚本。 PowerShell 提供了三个基于作业的解决方案来支持并发。

|作业            |说明                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |命令和脚本在远程计算机上运行。                 |
|`BackgroundJob`|命令和脚本在本地的单独进程中运行    |
|               |虚拟 CPU。                                                     |
|`ThreadJob`    |命令和脚本在同一内的单独线程中运行  |
|               |在本地计算机上进行处理。                                |

每种类型的作业都有其优点和缺点。 在单独的计算机上或在单独的进程中远程运行脚本具有很好的隔离。 任何错误不会影响其他正在运行的作业或启动该作业的客户端。 但远程处理层增加了开销，包括对象序列化。 所有传递到远程会话的对象都必须进行序列化，然后在客户端与目标会话之间传递时进行反序列化。 对于大型复杂数据对象，序列化操作可以使用很多计算资源和内存资源。

## <a name="powershell-thread-based-jobs"></a>基于 PowerShell 线程的作业

基于线程的作业不像远程和后台作业那样可靠，因为它们在不同线程上的同一进程中运行。 如果一个作业发生了导致进程崩溃的严重错误，则该进程中的所有其他作业也会失败。

但是，基于线程的作业的开销更少。 它们不需要使用远程层或序列化。 结果是基于线程的作业的运行速度要快得多，且使用的资源比其他作业类型要少得多。

## <a name="thread-job-performance"></a>线程作业性能

与其他类型的作业相比，线程作业的权重更快且更轻。 但与作业正在进行的工作相比，它们的开销可能会很大。

PowerShell 在会话中运行命令和脚本。 会话中一次只能运行一个命令或脚本。 因此，在运行多个作业时，每个作业都在单独的会话中运行。 每个会话都可提供开销。

当执行的工作大于用于运行作业的会话的开销时，线程作业可提供最佳性能。 满足此条件的情况有两种情况。

- 工作是计算密集型-在多个线程作业上运行脚本可充分利用多个处理器核心并更快完成。

- 工作包括大量等待时间的脚本，该脚本花费时间等待 i/o 或远程调用结果。 并行运行通常比按顺序运行快。

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

上面的第一个示例显示了一个 foreach 循环，该循环创建1000线程作业来编写简单的字符串。 由于作业开销，需要超过33秒钟才能完成。

第二个示例运行 `ForEach` cmdlet 来执行相同的1000操作，并按顺序执行每个字符串写入，无需任何作业开销。 它只会在25毫秒内完成。

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

在上面的示例中，最多可以为10个单独的系统日志收集5000个条目。 由于脚本涉及到读取多个日志，因此有必要并行执行操作。 并且作业的完成时间比脚本按顺序运行的时间快两倍。

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a>线程作业和变量

变量以各种方式传递到线程作业中。

`Start-ThreadJob` 可以接受通过管道传递给脚本块的、通过关键字传递到脚本块的变量， `$using` 也可以通过 **ArgumentList** 参数传入。

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

由于线程作业在同一进程中运行，因此必须仔细对待传入作业的任何变量引用类型。 如果它不是线程安全对象，则绝不应将其分配给，并且永远不应在其上调用方法和属性。

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

上面的示例将一个线程安全的 dotNet `ConcurrentDictionary` 对象传递给所有子作业，以收集唯一命名的进程对象。 由于它是线程安全对象，因此可以安全地使用该对象，同时在进程中同时运行作业。

## <a name="see-also"></a>另请参阅

- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](about_Thread_Jobs.md)
- [about_Job_Details](about_Job_Details.md)
- [about_Remote](about_Remote.md)
- [about_PSSessions](about_PSSessions.md)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
