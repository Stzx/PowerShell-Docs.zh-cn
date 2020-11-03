---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/import-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Counter
ms.openlocfilehash: 837f6b4b3b2869c6f74b3b02904dd43b73f6bcd5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197598"
---
# Import-Counter

## 摘要
导入性能计数器日志文件，并创建代表日志中每个计数器样本的对象。

## SYNTAX

### GetCounterSet（默认值）

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### ListSetSet

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### SummarySet

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## DESCRIPTION

**Import-module** cmdlet 从性能计数器日志文件中导入性能计数器数据，并为文件中的每个计数器样本创建对象。
它创建的 **PerformanceCounterSampleSet** 对象与 **获取** 性能计数器数据时返回的对象是相同的。

可以从逗号分隔值 (.csv)、制表符分隔值 (.tsv) 和二进制性能日志 (.blg) 性能日志文件中导入数据。
如果使用的是 .blg 文件，则最多可以在每个命令中导入32个文件。
可以使用 **导入计数器** 的参数来筛选导入的数据。

与 Get-Counter 和 Export-Counter cmdlet 一起，此功能可让你收集、导出、导入、合并、筛选、操作和重新导出 Windows PowerShell 中的性能计数器数据。

## 示例

### 示例1：导入文件中的所有计数器数据

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

此命令将 ProcessorData.csv 文件中的所有计数器数据导入到 $Data 变量。

### 示例2：从文件导入特定计数器数据

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

此命令仅将 Processordata.blg 文件中的 **"Processor (_total) \ 中断/秒"** 计数器数据导入到 $I 变量中。

### 示例3：选择性能计数器中的数据，然后将其导出到文件

```
The first command uses **Import-Counter** to import all of the performance counter data from the ProcessorData.blg files. The command saves the data in the $Data variable.
PS C:\> $Data = Import-Counter .\ProcessorData.blg

The second command displays the counter paths in the $Data variable. To get the display shown in the command output, the example uses the Format-Table cmdlet to format as a table the counter paths of the first counter in the $Data variable.
PS C:\> $Data[0].CounterSamples | Format-Table -Property Path

Path
----
\\SERVER01\Processor(_Total)\DPC Rate
\\SERVER01\Processor(1)\DPC Rate
\\SERVER01\Processor(0)\DPC Rate
\\SERVER01\Processor(_Total)\% Idle Time
\\SERVER01\Processor(1)\% Idle Time
\\SERVER01\Processor(0)\% Idle Time
\\SERVER01\Processor(_Total)\% C3 Time
\\SERVER01\Processor(1)\% C3 Time

The third command gets the counter paths that end in "Interrupts/sec" and saves the paths in the $IntCtrs variable. It uses the Where-Object cmdlet to filter the counter paths and the ForEach-Object cmdlet to get only the value of the **Path** property of each selected path object.
PS C:\> $IntCtrs = $Data[0].Countersamples | Where-Object {$_.Path -like "*Interrupts/sec"} | ForEach-Object {$_.Path}

The fourth command displays the selected counter paths in the $IntCtrs variable.
PS C:\> $IntCtrs

\\SERVER01\Processor(_Total)\Interrupts/sec
\\SERVER01\Processor(1)\Interrupts/sec
\\SERVER01\Processor(0)\Interrupts/sec

The fifth command uses the **Import-Counter** cmdlet to import the data. It uses the $IntCtrs variable as the value of the *Counter* parameter to import only data for the counter paths in $IntCtrs.
PS C:\> $I = Import-Counter -Path .\ProcessorData.blg -Counter $intCtrs

The sixth command uses the Export-Counter cmdlet to export the data to the Interrupts.csv file.
PS C:\> $I | Export-Counter -Path .\Interrupts.csv -Format CSV
```

此示例显示了如何从性能计数器日志文件 (.blg) 中选择数据，然后将选定的数据导出到 .csv 文件中。
前四个命令从文件中获取计数器路径并将它们保存在名为 $Data 的变量中。
后两个命令导入选定的数据，然后只导出这些选定的数据。

### 示例4：显示一组导入的计数器集中的所有计数器路径

```
The first command uses the *ListSet* parameter of the **Import-Counter** cmdlet to get all of the counter sets that are represented in a counter data file.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet *

CounterSetName     : Processor
MachineName        : \\SERVER01
CounterSetType     : MultiInstance
Description        :
Paths              : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}
PathsWithInstances : {\\SERVER01\Processor(_Total)\DPC Rate, \\SERVER01\Processor(1)\DPC Rate, \\SERVER01
\Processor(0)\DPC Rate, \\SERVER01\Processor(_Total)\% Idle Time...}
Counter            : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}

The second command gets all of the counter paths from the list set.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet * | ForEach-Object {$_.Paths}

\\SERVER01\Processor(*)\DPC Rate
\\SERVER01\Processor(*)\% Idle Time
\\SERVER01\Processor(*)\% C3 Time
\\SERVER01\Processor(*)\% Interrupt Time
\\SERVER01\Processor(*)\% C2 Time
\\SERVER01\Processor(*)\% User Time
\\SERVER01\Processor(*)\% C1 Time
\\SERVER01\Processor(*)\% Processor Time
\\SERVER01\Processor(*)\C1 Transitions/sec
\\SERVER01\Processor(*)\% DPC Time
\\SERVER01\Processor(*)\C2 Transitions/sec
\\SERVER01\Processor(*)\% Privileged Time
\\SERVER01\Processor(*)\C3 Transitions/sec
\\SERVER01\Processor(*)\DPCs Queued/sec
\\SERVER01\Processor(*)\Interrupts/sec
```

此示例显示了如何显示一组导入的计数器集中的所有计数器路径。

### 示例5：导入时间戳范围内的计数器数据

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

此示例只导入时间戳介于命令中指定的开始和结束范围中的计数器数据。

### 示例6：从性能计数器日志文件中导入指定数目的最旧样本

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

此示例显示了如何从性能计数器日志文件中导入五个最旧的样本和五个最新的样本。

### 示例7：从文件中获取计数器数据的摘要

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

此命令使用 *Import-Counter* cmdlet 的 **Summary** 参数来获取 Memory.blg 文件中的计数器数据摘要。

### 示例8：更新性能计数器日志文件

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

此示例更新性能计数器日志文件。

### 示例9：从多个文件导入性能日志数据，然后将其保存

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

此命令从两个日志中导入性能日志数据并将数据保存在 $Counters 变量中。
此命令使用管道运算符将性能日志路径发送到 Import-Counter，它将从指定的路径中导入数据。

请注意，每个路径用引号引起，并且各个路径之间用逗号分隔开。

## PARAMETERS

### -Counter

以字符串数组的形式指定性能计数器。
默认情况下， **导入计数器** 将导入输入文件中所有计数器的所有数据。
输入一个或多个计数器路径。
允许在路径的 Instance 部分中使用通配符。

每个计数器路径都具有以下格式。
ComputerName 值在路径中是必需的。
例如：

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

例如：

- `\\Server01\Processor(2)\% User Time`
- `\\Server01\Processor(*)\% Processor Time`

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: All counter
Accept pipeline input: False
Accept wildcard characters: True
```

### -EndTime

指定此 cmdlet 在 *StartTime* 和此参数时间戳之间导入计数器数据的结束日期和时间。
输入 **DateTime** 对象，例如 Get-Date cmdlet 创建的一个。
默认情况下， **导入计数器** 将导入 *Path* 参数所指定的文件中的所有计数器数据。

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No end time
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListSet

指定导出的文件中表示的性能计数器集。
使用此参数的命令不会导入任何数据。

输入一个或多个计数器集名称。
允许使用通配符。
若要获取文件中的所有计数器集，请键入 `Import-Counter -ListSet *` 。

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -MaxSamples

指定要导入的每个计数器的样本的最大数目。
默认情况下， **Get 计数器** 将导入 *Path* 参数所指定的文件中的所有数据。

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No maximum
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定要导入的文件的文件路径。
此参数是必需的。

输入使用 **Export-Counter** cmdlet 导出的、.csv,,. tsv 或 .blg 文件的路径和文件名。
在每个命令中只能指定一个 .csv 或 .tsv 文件，但可以指定多个 .blg 文件（最多 32 个）。
你还可以通过管道将文件路径字符串 (在引号) 到 **导入计数器** 中。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StartTime

指定此 cmdlet 获取计数器数据的开始日期和时间。
输入 **DateTime** 对象，例如由 **获取日期** cmdlet 创建的一个。
默认情况下， **导入计数器** 将导入 *Path* 参数所指定的文件中的所有计数器数据。

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No start time
Accept pipeline input: False
Accept wildcard characters: False
```

### -Summary

指示此 cmdlet 获取导入数据的摘要，而不是获取各个计数器数据样本。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SummarySet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String

可以通过管道将性能计数器日志路径传递给此 cmdlet。

## 输出

### Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet、Microsoft.PowerShell.Commands.GetCounter.CounterSet、Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo

此 cmdlet 将返回 **microsoft.powershell.commands.getcounter.counterset。 PerformanceCounterSampleSet** 。
如果使用 *ListSet* 参数，则此 cmdlet 将返回 **microsoft.powershell.commands.getcounter.counterset** 对象。
如果使用 *Summary* 参数，则此 cmdlet 将返回 **microsoft.powershell.commands.getcounter.counterset. microsoft.powershell.commands.getcounter.counterfileinfo** 对象。

## 注释

* 此 cmdlet 没有 *ComputerName* 参数。 但是，如果计算机配置为使用 Windows PowerShell 远程处理，则可以使用 Invoke-Command cmdlet 在远程计算机上运行 **导入计数器** 命令。

## 相关链接

[Export-Counter](Export-Counter.md)

[Get-Counter](Get-Counter.md)
