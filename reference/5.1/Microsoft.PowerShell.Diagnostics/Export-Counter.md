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
# <span data-ttu-id="c11d1-103">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="c11d1-103">Export-Counter</span></span>

## <span data-ttu-id="c11d1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c11d1-104">SYNOPSIS</span></span>
<span data-ttu-id="c11d1-105">将性能计数器数据导出到日志文件。</span><span class="sxs-lookup"><span data-stu-id="c11d1-105">Exports performance counter data to log files.</span></span>

## <span data-ttu-id="c11d1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c11d1-106">SYNTAX</span></span>

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## <span data-ttu-id="c11d1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c11d1-107">DESCRIPTION</span></span>

<span data-ttu-id="c11d1-108">`Export-Counter`Cmdlet 将 (PerformanceCounterSampleSet 对象) 的性能计数器数据导出到二进制性能日志中的日志文件 ( .blg) 、逗号分隔值 ( .csv) 或制表符分隔值 ( tsv) 格式。</span><span class="sxs-lookup"><span data-stu-id="c11d1-108">The `Export-Counter` cmdlet exports performance counter data (PerformanceCounterSampleSet objects) to log files in binary performance log (.blg), comma-separated value (.csv), or tab-separated value (.tsv) format.</span></span> <span data-ttu-id="c11d1-109">使用此 cmdlet 可以记录性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-109">You use this cmdlet to log performance counter data.</span></span>

<span data-ttu-id="c11d1-110">`Export-Counter`Cmdlet 用于导出和 cmdlet 返回的数据 `Get-Counter` `Import-Counter` 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-110">The `Export-Counter` cmdlet is designed to export data that is returned by the `Get-Counter` and `Import-Counter` cmdlets.</span></span>

<span data-ttu-id="c11d1-111">此 cmdlet 只能在 Windows 7、Windows Server 2008 R2 以及更高版本的 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="c11d1-111">This cmdlet runs only on Windows 7, Windows Server 2008 R2, and later versions of Windows.</span></span>

## <span data-ttu-id="c11d1-112">示例</span><span class="sxs-lookup"><span data-stu-id="c11d1-112">EXAMPLES</span></span>

### <span data-ttu-id="c11d1-113">示例1：将计数器数据导出到文件</span><span class="sxs-lookup"><span data-stu-id="c11d1-113">EXAMPLE 1: Export counter data to a file</span></span>

<span data-ttu-id="c11d1-114">此示例将计数器数据导出到 .BLG 文件。</span><span class="sxs-lookup"><span data-stu-id="c11d1-114">This example exports counter data to a BLG file.</span></span>

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

<span data-ttu-id="c11d1-115">该命令使用 `Get-Counter` cmdlet 来收集处理器时间数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-115">The command uses the `Get-Counter` cmdlet to collect processor time data.</span></span> <span data-ttu-id="c11d1-116">它使用管道运算符 (|) 将数据发送到 `Export-Counter` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c11d1-116">It uses a pipeline operator (|) to send the data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="c11d1-117">该 `Export-Counter` 命令使用 **Path** 变量来指定输出文件。</span><span class="sxs-lookup"><span data-stu-id="c11d1-117">The `Export-Counter` command uses the **Path** variable to specify the output file.</span></span>

<span data-ttu-id="c11d1-118">由于此数据集可能很大，因此，此示例通过管道将数据发送到 `Export-Counter` 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-118">Because the data set might be very large, this example sends the data to `Export-Counter` through the pipeline.</span></span> <span data-ttu-id="c11d1-119">如果数据保存在变量中，则可能会使用不相称的内存量。</span><span class="sxs-lookup"><span data-stu-id="c11d1-119">If the data were saved in a variable, you might use a disproportionate amount of memory.</span></span>

### <span data-ttu-id="c11d1-120">示例 2：将文件导出为计数器文件格式</span><span class="sxs-lookup"><span data-stu-id="c11d1-120">Example 2: Export a file to a counter file format</span></span>

<span data-ttu-id="c11d1-121">此示例将 CSV 文件转换为计数器数据 .BLG 格式。</span><span class="sxs-lookup"><span data-stu-id="c11d1-121">This example converts a CSV file to a counter data BLG format.</span></span>

<span data-ttu-id="c11d1-122">`Import-Counter`Cmdlet 将从文件中导入性能计数器数据 `Threads.csv` 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-122">The `Import-Counter` cmdlet imports performance counter data from the `Threads.csv` file.</span></span> <span data-ttu-id="c11d1-123">该示例假定以前使用 cmdlet 导出了此文件 `Export-Counter` 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-123">The example presumes that this file was previously exported by using the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="c11d1-124">管道运算符 (`|`) 将导入的数据发送到 `Export-Counter` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c11d1-124">A pipeline operator (`|`) sends the imported data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="c11d1-125">此命令使用 **Path** 参数指定输出文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c11d1-125">The command uses the **Path** parameter to specify the location of the output file.</span></span> <span data-ttu-id="c11d1-126">它使用 " **循环** " 和 " **MaxSize** " 参数定向 `Export-Counter` cmdlet，以创建以 1 GB 为包装的循环日志。</span><span class="sxs-lookup"><span data-stu-id="c11d1-126">It uses the **Circular** and **MaxSize** parameters to direct the `Export-Counter` cmdlet to create a circular log that wraps at 1 GB.</span></span> <span data-ttu-id="c11d1-127">**MaxSize** 参数以 mb 表示。</span><span class="sxs-lookup"><span data-stu-id="c11d1-127">The **MaxSize** parameter is expressed in megabytes.</span></span>

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### <span data-ttu-id="c11d1-128">示例 3：从远程计算机获取计数器数据并将数据保存到文件</span><span class="sxs-lookup"><span data-stu-id="c11d1-128">Example 3: Get counter data from a remote computer and save the data to a file</span></span>

<span data-ttu-id="c11d1-129">此示例演示如何从远程计算机获取性能计数器数据，并将数据保存在远程计算机上的文件中。</span><span class="sxs-lookup"><span data-stu-id="c11d1-129">This example shows how to get performance counter data from a remote computer and save the data in a file on the remote computer.</span></span>

<span data-ttu-id="c11d1-130">第一个命令使用 `Get-Counter` cmdlet 从 Server01 （一台远程计算机）中收集工作集计数器数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-130">The first command uses the `Get-Counter` cmdlet to collect working set counter data from Server01, a remote computer.</span></span> <span data-ttu-id="c11d1-131">该命令将数据保存在 `$C` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c11d1-131">The command saves the data in the `$C` variable.</span></span>

<span data-ttu-id="c11d1-132">第二个命令使用管道运算符 (`|`) 将数据发送 `$C` 到 `Export-Counter` cmdlet，这会将数据保存在 `Workingset.blg` Server01 计算机的 Perf 共享文件中。</span><span class="sxs-lookup"><span data-stu-id="c11d1-132">The second command uses a pipeline operator (`|`) to send the data in `$C` to the `Export-Counter` cmdlet, which saves it in the `Workingset.blg` file in the Perf share of the Server01 computer.</span></span>

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### <span data-ttu-id="c11d1-133">示例 4：重新记录现有数据</span><span class="sxs-lookup"><span data-stu-id="c11d1-133">Example 4: Re-log existing data</span></span>

<span data-ttu-id="c11d1-134">此示例演示如何使用 `Import-Counter` 和 `Export-Counter` cmdlet 来重新记录现有数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-134">This example shows how to use the `Import-Counter` and `Export-Counter` cmdlets to re-log existing data.</span></span>

<span data-ttu-id="c11d1-135">第一个命令使用 `Import-Counter` cmdlet 从磁盘空间 .blg 日志导入性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-135">The first command uses the `Import-Counter` cmdlet to import performance counter data from the DiskSpace.blg log.</span></span> <span data-ttu-id="c11d1-136">它将数据保存在 `$All` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c11d1-136">It saves the data in the `$All` variable.</span></span> <span data-ttu-id="c11d1-137">此文件包含 \% 企业中超过200台远程计算机上的 "逻辑磁盘可用空间" 计数器的示例。</span><span class="sxs-lookup"><span data-stu-id="c11d1-137">This file contains samples of the "LogicalDisk\% Free Space" counter on more than 200 remote computers in the enterprise.</span></span>

<span data-ttu-id="c11d1-138">第二个命令使用 `Where-Object` cmdlet 来选择 **CookedValue** 小于 15 (%) 的对象。</span><span class="sxs-lookup"><span data-stu-id="c11d1-138">The second command uses the `Where-Object` cmdlet to select objects with **CookedValue** of less than 15 (percent).</span></span> <span data-ttu-id="c11d1-139">该命令将结果保存在 `$LowSpace` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c11d1-139">The command saves the results in the `$LowSpace` variable.</span></span>

<span data-ttu-id="c11d1-140">第三个命令使用管道运算符 (`|`) 将变量中的数据发送 `$LowSpace` 到 `Export-Counter` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c11d1-140">The third command uses a pipeline operator (`|`) to send the data in the `$LowSpace` variable to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="c11d1-141">此命令使用 **Path** 参数指示应该在 LowDiskSpace.blg 文件中记录选定的数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-141">The command uses the **Path** parameter to indicate that the selected data should be logged in the LowDiskSpace.blg file.</span></span>

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## <span data-ttu-id="c11d1-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c11d1-142">PARAMETERS</span></span>

### <span data-ttu-id="c11d1-143">-Circular</span><span class="sxs-lookup"><span data-stu-id="c11d1-143">-Circular</span></span>

<span data-ttu-id="c11d1-144">指示输出文件是采用先进先出 (FIFO) 格式的循环日志。</span><span class="sxs-lookup"><span data-stu-id="c11d1-144">Indicates that the output file is a circular log with first in, first out (FIFO) format.</span></span>
<span data-ttu-id="c11d1-145">当包含此参数时， **MaxSize** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="c11d1-145">When you include this parameter, the **MaxSize** parameter is required.</span></span>

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

### <span data-ttu-id="c11d1-146">-FileFormat</span><span class="sxs-lookup"><span data-stu-id="c11d1-146">-FileFormat</span></span>

<span data-ttu-id="c11d1-147">指定输出日志文件的输出格式。</span><span class="sxs-lookup"><span data-stu-id="c11d1-147">Specifies the output format of the output log file.</span></span>

<span data-ttu-id="c11d1-148">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="c11d1-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c11d1-149">CSV</span><span class="sxs-lookup"><span data-stu-id="c11d1-149">CSV</span></span>
- <span data-ttu-id="c11d1-150">TSV</span><span class="sxs-lookup"><span data-stu-id="c11d1-150">TSV</span></span>
- <span data-ttu-id="c11d1-151">BLG</span><span class="sxs-lookup"><span data-stu-id="c11d1-151">BLG</span></span>

<span data-ttu-id="c11d1-152">默认值为 BLG。</span><span class="sxs-lookup"><span data-stu-id="c11d1-152">The default value is BLG.</span></span>

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

### <span data-ttu-id="c11d1-153">-Force</span><span class="sxs-lookup"><span data-stu-id="c11d1-153">-Force</span></span>

<span data-ttu-id="c11d1-154">如果在 **Path** 参数指定的位置中存在某个文件，则覆盖并替换该现有文件。</span><span class="sxs-lookup"><span data-stu-id="c11d1-154">Overwrites and replaces an existing file if one exists in the location specified by the **Path** parameter.</span></span>

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

### <span data-ttu-id="c11d1-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c11d1-155">-InputObject</span></span>

<span data-ttu-id="c11d1-156">以数组形式指定要导出的计数器数据。</span><span class="sxs-lookup"><span data-stu-id="c11d1-156">Specifies, as an array, the counter data to export.</span></span> <span data-ttu-id="c11d1-157">输入一个变量，其中包含用于获取数据的数据或命令，如 `Get-Counter` 或 `Import-Counter` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c11d1-157">Enter a variable that contains the data or a command that gets the data, such as the `Get-Counter` or `Import-Counter` cmdlet.</span></span>

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

### <span data-ttu-id="c11d1-158">-MaxSize</span><span class="sxs-lookup"><span data-stu-id="c11d1-158">-MaxSize</span></span>

<span data-ttu-id="c11d1-159">指定输出文件的最大大小（mb） (MB) 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-159">Specifies the maximum size of the output file in megabytes (MB).</span></span>

<span data-ttu-id="c11d1-160">如果指定了 **循环** 参数，则当日志文件达到指定的最大大小时，将删除最旧的条目，因为添加了较新的条目。</span><span class="sxs-lookup"><span data-stu-id="c11d1-160">If the **Circular** parameter is specified, then when the log file reaches the specified maximum size, the oldest entries are deleted as newer ones are added.</span></span> <span data-ttu-id="c11d1-161">如果未指定 **循环** 参数，则当日志文件达到指定的最大大小时，将不会添加新数据，并且 cmdlet 将生成一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="c11d1-161">If the **Circular** parameter is not specified, then when the log file reaches the specified maximum size, no new data is added and the cmdlet generates a non-terminating error.</span></span>

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

### <span data-ttu-id="c11d1-162">-Path</span><span class="sxs-lookup"><span data-stu-id="c11d1-162">-Path</span></span>

<span data-ttu-id="c11d1-163">指定输出文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="c11d1-163">Specifies the path and file name of the output file.</span></span> <span data-ttu-id="c11d1-164">在本地计算机上输入相对或绝对路径，或者在远程计算机 (UNC) 路径中输入统一的命名约定，例如 `\\Computer\Share\file.blg` 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-164">Enter a relative or absolute path on the local computer, or a Uniform Naming Convention (UNC) path to a remote computer, such as `\\Computer\Share\file.blg`.</span></span> <span data-ttu-id="c11d1-165">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="c11d1-165">This parameter is required.</span></span>

<span data-ttu-id="c11d1-166">文件格式由 FileFormat  参数的值确定，而不是由路径中的文件扩展名确定。</span><span class="sxs-lookup"><span data-stu-id="c11d1-166">The file format is determined by the value of the **FileFormat** parameter, not by the file name extension in the path.</span></span>

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

### <span data-ttu-id="c11d1-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c11d1-167">CommonParameters</span></span>

<span data-ttu-id="c11d1-168">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c11d1-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c11d1-169">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c11d1-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c11d1-170">输入</span><span class="sxs-lookup"><span data-stu-id="c11d1-170">INPUTS</span></span>

### <span data-ttu-id="c11d1-171">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet</span><span class="sxs-lookup"><span data-stu-id="c11d1-171">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet</span></span>

<span data-ttu-id="c11d1-172">可以通过管道将性能计数器数据从 `Get-Counter` 或传递 `Import-Counter` 给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c11d1-172">You can pipe performance counter data from `Get-Counter` or `Import-Counter` to this cmdlet.</span></span>

## <span data-ttu-id="c11d1-173">输出</span><span class="sxs-lookup"><span data-stu-id="c11d1-173">OUTPUTS</span></span>

### <span data-ttu-id="c11d1-174">无</span><span class="sxs-lookup"><span data-stu-id="c11d1-174">None</span></span>

## <span data-ttu-id="c11d1-175">注释</span><span class="sxs-lookup"><span data-stu-id="c11d1-175">NOTES</span></span>

<span data-ttu-id="c11d1-176">日志文件生成器要求所有输入对象都具有相同的计数器路径，并且以时间升序顺序排列这些对象。</span><span class="sxs-lookup"><span data-stu-id="c11d1-176">The log file generator expects that all input objects have the same counter path and that the objects are arranged in ascending time order.</span></span>

<span data-ttu-id="c11d1-177">计数器类型和第一个输入对象的路径确定日志文件中记录的属性。</span><span class="sxs-lookup"><span data-stu-id="c11d1-177">The counter type and path of the first input object determines the properties recorded in the log file.</span></span> <span data-ttu-id="c11d1-178">如果其他输入对象没有已记录属性的值，则属性字段为空。</span><span class="sxs-lookup"><span data-stu-id="c11d1-178">If other input objects do not have a value for a recorded property, the property field is empty.</span></span> <span data-ttu-id="c11d1-179">如果对象具有未记录的属性值，则忽略额外的属性值。</span><span class="sxs-lookup"><span data-stu-id="c11d1-179">If the objects have property values that were not recorded, the extra property values are ignored.</span></span>

<span data-ttu-id="c11d1-180">性能监视器可能无法读取生成的所有日志 `Export-Counter` 。</span><span class="sxs-lookup"><span data-stu-id="c11d1-180">Performance Monitor might not be able to read all logs that `Export-Counter` generates.</span></span> <span data-ttu-id="c11d1-181">例如，性能监视器要求所有对象都具有相同的路径，并以相同的时间间隔分隔所有对象。</span><span class="sxs-lookup"><span data-stu-id="c11d1-181">For instance, Performance Monitor requires that all objects have the same path and that all objects are separated by the same time interval.</span></span>

<span data-ttu-id="c11d1-182">`Import-Counter`Cmdlet 没有 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="c11d1-182">The `Import-Counter` cmdlet does not have a **ComputerName** parameter.</span></span> <span data-ttu-id="c11d1-183">但是，如果为远程 Windows PowerShell Windows PowerShell 配置了计算机，则可以使用 `Invoke-Command` cmdlet `Import-Counter` 在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="c11d1-183">However, if the computer is configured for remote Windows PowerShell Windows PowerShell, you can use the `Invoke-Command` cmdlet to run an `Import-Counter` command on a remote computer.</span></span>

## <span data-ttu-id="c11d1-184">相关链接</span><span class="sxs-lookup"><span data-stu-id="c11d1-184">RELATED LINKS</span></span>

[<span data-ttu-id="c11d1-185">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="c11d1-185">Get-Counter</span></span>](Get-Counter.md)

[<span data-ttu-id="c11d1-186">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="c11d1-186">Import-Counter</span></span>](Import-Counter.md)
