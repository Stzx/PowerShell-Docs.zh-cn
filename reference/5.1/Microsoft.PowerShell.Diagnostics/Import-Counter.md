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
# <span data-ttu-id="8a748-103">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="8a748-103">Import-Counter</span></span>

## <span data-ttu-id="8a748-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8a748-104">SYNOPSIS</span></span>
<span data-ttu-id="8a748-105">导入性能计数器日志文件，并创建代表日志中每个计数器样本的对象。</span><span class="sxs-lookup"><span data-stu-id="8a748-105">Imports performance counter log files and creates the objects that represent each counter sample in the log.</span></span>

## <span data-ttu-id="8a748-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a748-106">SYNTAX</span></span>

### <span data-ttu-id="8a748-107">GetCounterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="8a748-107">GetCounterSet (Default)</span></span>

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="8a748-108">ListSetSet</span><span class="sxs-lookup"><span data-stu-id="8a748-108">ListSetSet</span></span>

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8a748-109">SummarySet</span><span class="sxs-lookup"><span data-stu-id="8a748-109">SummarySet</span></span>

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## <span data-ttu-id="8a748-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8a748-110">DESCRIPTION</span></span>

<span data-ttu-id="8a748-111">**Import-module** cmdlet 从性能计数器日志文件中导入性能计数器数据，并为文件中的每个计数器样本创建对象。</span><span class="sxs-lookup"><span data-stu-id="8a748-111">The **Import-Counter** cmdlet imports performance counter data from performance counter log files and creates objects for each counter sample in the file.</span></span>
<span data-ttu-id="8a748-112">它创建的 **PerformanceCounterSampleSet** 对象与 **获取** 性能计数器数据时返回的对象是相同的。</span><span class="sxs-lookup"><span data-stu-id="8a748-112">The **PerformanceCounterSampleSet** objects that it creates are identical to the objects that **Get-Counter** returns when it collects performance counter data.</span></span>

<span data-ttu-id="8a748-113">可以从逗号分隔值 (.csv)、制表符分隔值 (.tsv) 和二进制性能日志 (.blg) 性能日志文件中导入数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-113">You can import data from comma-separated value (.csv), tab-separated value ( .tsv), and binary performance log (.blg) performance log files.</span></span>
<span data-ttu-id="8a748-114">如果使用的是 .blg 文件，则最多可以在每个命令中导入32个文件。</span><span class="sxs-lookup"><span data-stu-id="8a748-114">If you are using .blg files, you can import up to 32 files in each command.</span></span>
<span data-ttu-id="8a748-115">可以使用 **导入计数器** 的参数来筛选导入的数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-115">You can use the parameters of **Import-Counter** to filter the data that you import.</span></span>

<span data-ttu-id="8a748-116">与 Get-Counter 和 Export-Counter cmdlet 一起，此功能可让你收集、导出、导入、合并、筛选、操作和重新导出 Windows PowerShell 中的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-116">Along with the Get-Counter and Export-Counter cmdlets, this feature lets you collect, export, import, combine, filter, manipulate, and re-export performance counter data within Windows PowerShell.</span></span>

## <span data-ttu-id="8a748-117">示例</span><span class="sxs-lookup"><span data-stu-id="8a748-117">EXAMPLES</span></span>

### <span data-ttu-id="8a748-118">示例1：导入文件中的所有计数器数据</span><span class="sxs-lookup"><span data-stu-id="8a748-118">Example 1: Import all counter data from a file</span></span>

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

<span data-ttu-id="8a748-119">此命令将 ProcessorData.csv 文件中的所有计数器数据导入到 $Data 变量。</span><span class="sxs-lookup"><span data-stu-id="8a748-119">This command imports all counter data from the ProcessorData.csv file into the $Data variable.</span></span>

### <span data-ttu-id="8a748-120">示例2：从文件导入特定计数器数据</span><span class="sxs-lookup"><span data-stu-id="8a748-120">Example 2: Import specific counter data from a file</span></span>

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

<span data-ttu-id="8a748-121">此命令仅将 Processordata.blg 文件中的 **"Processor (_total) \ 中断/秒"** 计数器数据导入到 $I 变量中。</span><span class="sxs-lookup"><span data-stu-id="8a748-121">This command imports only the **"Processor(_total)\Interrupts/sec"** counter data from the ProcessorData.blg file into the $I variable.</span></span>

### <span data-ttu-id="8a748-122">示例3：选择性能计数器中的数据，然后将其导出到文件</span><span class="sxs-lookup"><span data-stu-id="8a748-122">Example 3: Select data from a performance counter then export it to a file</span></span>

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

<span data-ttu-id="8a748-123">此示例显示了如何从性能计数器日志文件 (.blg) 中选择数据，然后将选定的数据导出到 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="8a748-123">This example shows how to select data from a performance counter log file (.blg) and then export the selected data to a .csv file.</span></span>
<span data-ttu-id="8a748-124">前四个命令从文件中获取计数器路径并将它们保存在名为 $Data 的变量中。</span><span class="sxs-lookup"><span data-stu-id="8a748-124">The first four commands get the counter paths from the file and save them in the variable named $Data.</span></span>
<span data-ttu-id="8a748-125">后两个命令导入选定的数据，然后只导出这些选定的数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-125">The last two commands import selected data and then export only the selected data.</span></span>

### <span data-ttu-id="8a748-126">示例4：显示一组导入的计数器集中的所有计数器路径</span><span class="sxs-lookup"><span data-stu-id="8a748-126">Example 4: Display all counter paths in a group of imported counter sets</span></span>

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

<span data-ttu-id="8a748-127">此示例显示了如何显示一组导入的计数器集中的所有计数器路径。</span><span class="sxs-lookup"><span data-stu-id="8a748-127">This example shows how to display all the counter paths in a group of imported counter sets.</span></span>

### <span data-ttu-id="8a748-128">示例5：导入时间戳范围内的计数器数据</span><span class="sxs-lookup"><span data-stu-id="8a748-128">Example 5: Import counter data from a range of time stamps</span></span>

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

<span data-ttu-id="8a748-129">此示例只导入时间戳介于命令中指定的开始和结束范围中的计数器数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-129">This example imports only the counter data that has a time stamp between the starting an ending ranges specified in the command.</span></span>

### <span data-ttu-id="8a748-130">示例6：从性能计数器日志文件中导入指定数目的最旧样本</span><span class="sxs-lookup"><span data-stu-id="8a748-130">Example 6: Import a specified number of the oldest samples from a performance counter log file</span></span>

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

<span data-ttu-id="8a748-131">此示例显示了如何从性能计数器日志文件中导入五个最旧的样本和五个最新的样本。</span><span class="sxs-lookup"><span data-stu-id="8a748-131">This example shows how to import the five oldest and five newest samples from a performance counter log file.</span></span>

### <span data-ttu-id="8a748-132">示例7：从文件中获取计数器数据的摘要</span><span class="sxs-lookup"><span data-stu-id="8a748-132">Example 7: Get a summary of counter data from a file</span></span>

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

<span data-ttu-id="8a748-133">此命令使用 *Import-Counter* cmdlet 的 **Summary** 参数来获取 Memory.blg 文件中的计数器数据摘要。</span><span class="sxs-lookup"><span data-stu-id="8a748-133">This command uses the *Summary* parameter of the **Import-Counter** cmdlet to get a summary of the counter data in the Memory.blg file.</span></span>

### <span data-ttu-id="8a748-134">示例8：更新性能计数器日志文件</span><span class="sxs-lookup"><span data-stu-id="8a748-134">Example 8: Update a performance counter log file</span></span>

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

<span data-ttu-id="8a748-135">此示例更新性能计数器日志文件。</span><span class="sxs-lookup"><span data-stu-id="8a748-135">This example updates a performance counter log file.</span></span>

### <span data-ttu-id="8a748-136">示例9：从多个文件导入性能日志数据，然后将其保存</span><span class="sxs-lookup"><span data-stu-id="8a748-136">Example 9: Import performance log data from multiple files and then save it</span></span>

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

<span data-ttu-id="8a748-137">此命令从两个日志中导入性能日志数据并将数据保存在 $Counters 变量中。</span><span class="sxs-lookup"><span data-stu-id="8a748-137">This command imports performance log data from two logs and saves the data in the $Counters variable.</span></span>
<span data-ttu-id="8a748-138">此命令使用管道运算符将性能日志路径发送到 Import-Counter，它将从指定的路径中导入数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-138">The command uses a pipeline operator to send the performance log paths to Import-Counter, which imports the data from the specified paths.</span></span>

<span data-ttu-id="8a748-139">请注意，每个路径用引号引起，并且各个路径之间用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="8a748-139">Notice that each path is enclosed in quotation marks and that the paths are separated from each other by a comma.</span></span>

## <span data-ttu-id="8a748-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a748-140">PARAMETERS</span></span>

### <span data-ttu-id="8a748-141">-Counter</span><span class="sxs-lookup"><span data-stu-id="8a748-141">-Counter</span></span>

<span data-ttu-id="8a748-142">以字符串数组的形式指定性能计数器。</span><span class="sxs-lookup"><span data-stu-id="8a748-142">Specifies, as a string array, the performance counters.</span></span>
<span data-ttu-id="8a748-143">默认情况下， **导入计数器** 将导入输入文件中所有计数器的所有数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-143">By default, **Import-Counter** imports all data from all counters in the input files.</span></span>
<span data-ttu-id="8a748-144">输入一个或多个计数器路径。</span><span class="sxs-lookup"><span data-stu-id="8a748-144">Enter one or more counter paths.</span></span>
<span data-ttu-id="8a748-145">允许在路径的 Instance 部分中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8a748-145">Wildcards are permitted in the Instance part of the path.</span></span>

<span data-ttu-id="8a748-146">每个计数器路径都具有以下格式。</span><span class="sxs-lookup"><span data-stu-id="8a748-146">Each counter path has the following format.</span></span>
<span data-ttu-id="8a748-147">ComputerName 值在路径中是必需的。</span><span class="sxs-lookup"><span data-stu-id="8a748-147">The ComputerName value is required in the path.</span></span>
<span data-ttu-id="8a748-148">例如：</span><span class="sxs-lookup"><span data-stu-id="8a748-148">For instance:</span></span>

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

<span data-ttu-id="8a748-149">例如：</span><span class="sxs-lookup"><span data-stu-id="8a748-149">For example:</span></span>

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

### <span data-ttu-id="8a748-150">-EndTime</span><span class="sxs-lookup"><span data-stu-id="8a748-150">-EndTime</span></span>

<span data-ttu-id="8a748-151">指定此 cmdlet 在 *StartTime* 和此参数时间戳之间导入计数器数据的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8a748-151">Specifies an end date and time that this cmdlet imports counter data between the *StartTime* and this parameter timestamps.</span></span>
<span data-ttu-id="8a748-152">输入 **DateTime** 对象，例如 Get-Date cmdlet 创建的一个。</span><span class="sxs-lookup"><span data-stu-id="8a748-152">Enter a **DateTime** object, such as one created by the Get-Date cmdlet.</span></span>
<span data-ttu-id="8a748-153">默认情况下， **导入计数器** 将导入 *Path* 参数所指定的文件中的所有计数器数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-153">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="8a748-154">-ListSet</span><span class="sxs-lookup"><span data-stu-id="8a748-154">-ListSet</span></span>

<span data-ttu-id="8a748-155">指定导出的文件中表示的性能计数器集。</span><span class="sxs-lookup"><span data-stu-id="8a748-155">Specifies the performance counter sets that are represented in the exported files.</span></span>
<span data-ttu-id="8a748-156">使用此参数的命令不会导入任何数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-156">Commands with this parameter do not import any data.</span></span>

<span data-ttu-id="8a748-157">输入一个或多个计数器集名称。</span><span class="sxs-lookup"><span data-stu-id="8a748-157">Enter one or more counter set names.</span></span>
<span data-ttu-id="8a748-158">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8a748-158">Wildcards are permitted.</span></span>
<span data-ttu-id="8a748-159">若要获取文件中的所有计数器集，请键入 `Import-Counter -ListSet *` 。</span><span class="sxs-lookup"><span data-stu-id="8a748-159">To get all counter sets in the file, type `Import-Counter -ListSet *`.</span></span>

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

### <span data-ttu-id="8a748-160">-MaxSamples</span><span class="sxs-lookup"><span data-stu-id="8a748-160">-MaxSamples</span></span>

<span data-ttu-id="8a748-161">指定要导入的每个计数器的样本的最大数目。</span><span class="sxs-lookup"><span data-stu-id="8a748-161">Specifies the maximum number of samples of each counter to import.</span></span>
<span data-ttu-id="8a748-162">默认情况下， **Get 计数器** 将导入 *Path* 参数所指定的文件中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-162">By default, **Get-Counter** imports all of the data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="8a748-163">-Path</span><span class="sxs-lookup"><span data-stu-id="8a748-163">-Path</span></span>

<span data-ttu-id="8a748-164">指定要导入的文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="8a748-164">Specifies the file paths of the files to be imported.</span></span>
<span data-ttu-id="8a748-165">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="8a748-165">This parameter is required.</span></span>

<span data-ttu-id="8a748-166">输入使用 **Export-Counter** cmdlet 导出的、.csv,,. tsv 或 .blg 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="8a748-166">Enter the path and file name of a, .csv,, .tsv, or .blg file that you exported by using the **Export-Counter** cmdlet.</span></span>
<span data-ttu-id="8a748-167">在每个命令中只能指定一个 .csv 或 .tsv 文件，但可以指定多个 .blg 文件（最多 32 个）。</span><span class="sxs-lookup"><span data-stu-id="8a748-167">You can specify only one .csv or .tsv file, but you can specify multiple .blg files (up to 32) in each command.</span></span>
<span data-ttu-id="8a748-168">你还可以通过管道将文件路径字符串 (在引号) 到 **导入计数器** 中。</span><span class="sxs-lookup"><span data-stu-id="8a748-168">You can also pipe file path strings (in quotation marks) to **Import-Counter** .</span></span>

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

### <span data-ttu-id="8a748-169">-StartTime</span><span class="sxs-lookup"><span data-stu-id="8a748-169">-StartTime</span></span>

<span data-ttu-id="8a748-170">指定此 cmdlet 获取计数器数据的开始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8a748-170">Specifies the start date and time in which this cmdlet gets counter data.</span></span>
<span data-ttu-id="8a748-171">输入 **DateTime** 对象，例如由 **获取日期** cmdlet 创建的一个。</span><span class="sxs-lookup"><span data-stu-id="8a748-171">Enter a **DateTime** object, such as one created by the **Get-Date** cmdlet.</span></span>
<span data-ttu-id="8a748-172">默认情况下， **导入计数器** 将导入 *Path* 参数所指定的文件中的所有计数器数据。</span><span class="sxs-lookup"><span data-stu-id="8a748-172">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="8a748-173">-Summary</span><span class="sxs-lookup"><span data-stu-id="8a748-173">-Summary</span></span>

<span data-ttu-id="8a748-174">指示此 cmdlet 获取导入数据的摘要，而不是获取各个计数器数据样本。</span><span class="sxs-lookup"><span data-stu-id="8a748-174">Indicates that this cmdlet gets a summary of the imported data, instead of getting individual counter data samples.</span></span>

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

### <span data-ttu-id="8a748-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8a748-175">CommonParameters</span></span>

<span data-ttu-id="8a748-176">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8a748-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a748-177">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8a748-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a748-178">输入</span><span class="sxs-lookup"><span data-stu-id="8a748-178">INPUTS</span></span>

### <span data-ttu-id="8a748-179">System.String</span><span class="sxs-lookup"><span data-stu-id="8a748-179">System.String</span></span>

<span data-ttu-id="8a748-180">可以通过管道将性能计数器日志路径传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a748-180">You can pipe performance counter log paths to this cmdlet.</span></span>

## <span data-ttu-id="8a748-181">输出</span><span class="sxs-lookup"><span data-stu-id="8a748-181">OUTPUTS</span></span>

### <span data-ttu-id="8a748-182">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet、Microsoft.PowerShell.Commands.GetCounter.CounterSet、Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo</span><span class="sxs-lookup"><span data-stu-id="8a748-182">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo</span></span>

<span data-ttu-id="8a748-183">此 cmdlet 将返回 **microsoft.powershell.commands.getcounter.counterset。 PerformanceCounterSampleSet** 。</span><span class="sxs-lookup"><span data-stu-id="8a748-183">This cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet** .</span></span>
<span data-ttu-id="8a748-184">如果使用 *ListSet* 参数，则此 cmdlet 将返回 **microsoft.powershell.commands.getcounter.counterset** 对象。</span><span class="sxs-lookup"><span data-stu-id="8a748-184">If you use the *ListSet* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterSet** object.</span></span>
<span data-ttu-id="8a748-185">如果使用 *Summary* 参数，则此 cmdlet 将返回 **microsoft.powershell.commands.getcounter.counterset. microsoft.powershell.commands.getcounter.counterfileinfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="8a748-185">If you use the *Summary* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo** object.</span></span>

## <span data-ttu-id="8a748-186">注释</span><span class="sxs-lookup"><span data-stu-id="8a748-186">NOTES</span></span>

* <span data-ttu-id="8a748-187">此 cmdlet 没有 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="8a748-187">This cmdlet does not have a *ComputerName* parameter.</span></span> <span data-ttu-id="8a748-188">但是，如果计算机配置为使用 Windows PowerShell 远程处理，则可以使用 Invoke-Command cmdlet 在远程计算机上运行 **导入计数器** 命令。</span><span class="sxs-lookup"><span data-stu-id="8a748-188">However, if the computer is configured for Windows PowerShell remoting, you can use the Invoke-Command cmdlet to run an **Import-Counter** command on a remote computer.</span></span>

## <span data-ttu-id="8a748-189">相关链接</span><span class="sxs-lookup"><span data-stu-id="8a748-189">RELATED LINKS</span></span>

[<span data-ttu-id="8a748-190">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="8a748-190">Export-Counter</span></span>](Export-Counter.md)

[<span data-ttu-id="8a748-191">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="8a748-191">Get-Counter</span></span>](Get-Counter.md)
