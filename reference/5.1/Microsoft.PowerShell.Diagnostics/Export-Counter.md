---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199624"
---
# Export-Counter

## 摘要
将性能计数器数据导出到日志文件。

## SYNTAX

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## DESCRIPTION

`Export-Counter`Cmdlet 将 (PerformanceCounterSampleSet 对象) 的性能计数器数据导出到二进制性能日志中的日志文件 ( .blg) 、逗号分隔值 ( .csv) 或制表符分隔值 ( tsv) 格式。 使用此 cmdlet 可以记录性能计数器数据。

`Export-Counter`Cmdlet 用于导出和 cmdlet 返回的数据 `Get-Counter` `Import-Counter` 。

此 cmdlet 只能在 Windows 7、Windows Server 2008 R2 以及更高版本的 Windows 上运行。

## 示例

### 示例1：将计数器数据导出到文件

此示例将计数器数据导出到 .BLG 文件。

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

该命令使用 `Get-Counter` cmdlet 来收集处理器时间数据。 它使用管道运算符 (|) 将数据发送到 `Export-Counter` cmdlet。 该 `Export-Counter` 命令使用 **Path** 变量来指定输出文件。

由于此数据集可能很大，因此，此示例通过管道将数据发送到 `Export-Counter` 。 如果数据保存在变量中，则可能会使用不相称的内存量。

### 示例 2：将文件导出为计数器文件格式

此示例将 CSV 文件转换为计数器数据 .BLG 格式。

`Import-Counter`Cmdlet 将从文件中导入性能计数器数据 `Threads.csv` 。 该示例假定以前使用 cmdlet 导出了此文件 `Export-Counter` 。 管道运算符 (`|`) 将导入的数据发送到 `Export-Counter` cmdlet。 此命令使用 **Path** 参数指定输出文件的位置。 它使用 " **循环** " 和 " **MaxSize** " 参数定向 `Export-Counter` cmdlet，以创建以 1 GB 为包装的循环日志。 **MaxSize** 参数以 mb 表示。

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### 示例 3：从远程计算机获取计数器数据并将数据保存到文件

此示例演示如何从远程计算机获取性能计数器数据，并将数据保存在远程计算机上的文件中。

第一个命令使用 `Get-Counter` cmdlet 从 Server01 （一台远程计算机）中收集工作集计数器数据。 该命令将数据保存在 `$C` 变量中。

第二个命令使用管道运算符 (`|`) 将数据发送 `$C` 到 `Export-Counter` cmdlet，这会将数据保存在 `Workingset.blg` Server01 计算机的 Perf 共享文件中。

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### 示例 4：重新记录现有数据

此示例演示如何使用 `Import-Counter` 和 `Export-Counter` cmdlet 来重新记录现有数据。

第一个命令使用 `Import-Counter` cmdlet 从磁盘空间 .blg 日志导入性能计数器数据。 它将数据保存在 `$All` 变量中。 此文件包含 \% 企业中超过200台远程计算机上的 "逻辑磁盘可用空间" 计数器的示例。

第二个命令使用 `Where-Object` cmdlet 来选择 **CookedValue** 小于 15 (%) 的对象。 该命令将结果保存在 `$LowSpace` 变量中。

第三个命令使用管道运算符 (`|`) 将变量中的数据发送 `$LowSpace` 到 `Export-Counter` cmdlet。 此命令使用 **Path** 参数指示应该在 LowDiskSpace.blg 文件中记录选定的数据。

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## PARAMETERS

### -Circular

指示输出文件是采用先进先出 (FIFO) 格式的循环日志。
当包含此参数时， **MaxSize** 参数是必需的。

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

### -FileFormat

指定输出日志文件的输出格式。

此参数的可接受值为：

- CSV
- TSV
- BLG

默认值为 BLG。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

如果在 **Path** 参数指定的位置中存在某个文件，则覆盖并替换该现有文件。

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

### -InputObject

以数组形式指定要导出的计数器数据。 输入一个变量，其中包含用于获取数据的数据或命令，如 `Get-Counter` 或 `Import-Counter` cmdlet。

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaxSize

指定输出文件的最大大小（mb） (MB) 。

如果指定了 **循环** 参数，则当日志文件达到指定的最大大小时，将删除最旧的条目，因为添加了较新的条目。 如果未指定 **循环** 参数，则当日志文件达到指定的最大大小时，将不会添加新数据，并且 cmdlet 将生成一个非终止错误。

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定输出文件的路径和文件名。 在本地计算机上输入相对或绝对路径，或者在远程计算机 (UNC) 路径中输入统一的命名约定，例如 `\\Computer\Share\file.blg` 。 此参数是必需的。

文件格式由 FileFormat  参数的值确定，而不是由路径中的文件扩展名确定。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet

可以通过管道将性能计数器数据从 `Get-Counter` 或传递 `Import-Counter` 给此 cmdlet。

## 输出

### 无

## 注释

日志文件生成器要求所有输入对象都具有相同的计数器路径，并且以时间升序顺序排列这些对象。

计数器类型和第一个输入对象的路径确定日志文件中记录的属性。 如果其他输入对象没有已记录属性的值，则属性字段为空。 如果对象具有未记录的属性值，则忽略额外的属性值。

性能监视器可能无法读取生成的所有日志 `Export-Counter` 。 例如，性能监视器要求所有对象都具有相同的路径，并以相同的时间间隔分隔所有对象。

`Import-Counter`Cmdlet 没有 **ComputerName** 参数。 但是，如果为远程 Windows PowerShell Windows PowerShell 配置了计算机，则可以使用 `Invoke-Command` cmdlet `Import-Counter` 在远程计算机上运行命令。

## 相关链接

[Get-Counter](Get-Counter.md)

[Import-Counter](Import-Counter.md)
