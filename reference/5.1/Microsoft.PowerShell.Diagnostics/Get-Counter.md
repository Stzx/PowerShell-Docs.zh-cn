---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 7c1ab665fc7ffddc54ec936f80b76b4329291a3b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197601"
---
# <span data-ttu-id="cbf42-103">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="cbf42-103">Get-Counter</span></span>

## <span data-ttu-id="cbf42-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cbf42-104">SYNOPSIS</span></span>
<span data-ttu-id="cbf42-105">从本地和远程计算机获取性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-105">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="cbf42-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cbf42-106">SYNTAX</span></span>

### <span data-ttu-id="cbf42-107">GetCounterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="cbf42-107">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="cbf42-108">ListSetSet</span><span class="sxs-lookup"><span data-stu-id="cbf42-108">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="cbf42-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cbf42-109">DESCRIPTION</span></span>

<span data-ttu-id="cbf42-110">`Get-Counter`Cmdlet 直接从 Windows 操作系统系列中的 "性能监视" 检测获取性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-110">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="cbf42-111">`Get-Counter` 从本地计算机或远程计算机获取性能数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-111">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="cbf42-112">您可以使用 `Get-Counter` 参数指定一台或多台计算机，列出性能计数器集及其包含的实例，设置采样间隔，并指定最大样本数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-112">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="cbf42-113">如果没有参数， `Get-Counter` 则获取一组系统计数器的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-113">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="cbf42-114">许多计数器集受 (ACL) 的访问控制列表保护。</span><span class="sxs-lookup"><span data-stu-id="cbf42-114">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="cbf42-115">若要查看所有计数器集，请以 "以 **管理员身份运行** " 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cbf42-115">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="cbf42-116">示例</span><span class="sxs-lookup"><span data-stu-id="cbf42-116">EXAMPLES</span></span>

### <span data-ttu-id="cbf42-117">示例1：获取计数器集列表</span><span class="sxs-lookup"><span data-stu-id="cbf42-117">Example 1: Get the counter set list</span></span>

<span data-ttu-id="cbf42-118">此示例将获取本地计算机的计数器集列表。</span><span class="sxs-lookup"><span data-stu-id="cbf42-118">This example gets the local computer's list of counter sets.</span></span>

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

<span data-ttu-id="cbf42-119">`Get-Counter` 使用带有星号 () 的 **ListSet** 参数 `*` 来获取计数器集列表。</span><span class="sxs-lookup"><span data-stu-id="cbf42-119">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="cbf42-120">`.` **MachineName** 列中)  (点表示本地计算机。</span><span class="sxs-lookup"><span data-stu-id="cbf42-120">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="cbf42-121">示例2：指定 SampleInterval 和 MaxSamples</span><span class="sxs-lookup"><span data-stu-id="cbf42-121">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="cbf42-122">此示例将获取本地计算机上的所有处理器的计数器数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-122">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="cbf42-123">数据将以两秒为间隔收集，直到有三个示例。</span><span class="sxs-lookup"><span data-stu-id="cbf42-123">Data is collected at two-second intervals until there are three samples.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

<span data-ttu-id="cbf42-124">`Get-Counter` 使用 **counter** 参数来指定计数器路径 `\Processor(_Total)\% Processor Time` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-124">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="cbf42-125">**SampleInterval** 参数设置一个2秒的间隔以检查计数器。</span><span class="sxs-lookup"><span data-stu-id="cbf42-125">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="cbf42-126">**MaxSamples** 确定三是检查计数器的最大次数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-126">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="cbf42-127">示例3：获取计数器的连续示例</span><span class="sxs-lookup"><span data-stu-id="cbf42-127">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="cbf42-128">此示例每秒获取计数器的连续样本数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-128">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="cbf42-129">若要停止该命令，请按<kbd>CTRL</kbd> + <kbd>C</kbd>。</span><span class="sxs-lookup"><span data-stu-id="cbf42-129">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="cbf42-130">若要指定样本之间的更长时间间隔，请使用 **SampleInterval** 参数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-130">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

<span data-ttu-id="cbf42-131">`Get-Counter` 使用 **counter** 参数来指定 `\Processor\% Processor Time` 计数器。</span><span class="sxs-lookup"><span data-stu-id="cbf42-131">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="cbf42-132">**连续** 参数指定每秒获取样本，直到命令通过 <kbd>CTRL</kbd> + <kbd>C</kbd>停止。</span><span class="sxs-lookup"><span data-stu-id="cbf42-132">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="cbf42-133">示例4：计数器集的按字母顺序排列的列表</span><span class="sxs-lookup"><span data-stu-id="cbf42-133">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="cbf42-134">此示例使用管道获取计数器列表集，然后按字母顺序对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="cbf42-134">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

```powershell
Get-Counter -ListSet * | Sort-Object -Property CounterSetName | Format-Table -AutoSize
```

```Output
CounterSetName                        MachineName CounterSetType  Description
--------------                        ----------- --------------  -----------
.NET CLR Data                         .           SingleInstance  .Net CLR Data
.NET Data Provider for SqlServer      .           SingleInstance  Counters for System.Data.SqlClient
AppV Client Streamed Data Percentage  .           SingleInstance  Size of data streamed to disk ...
Authorization Manager Applications    .           SingleInstance  The set of Counters for ...
BitLocker                             .           MultiInstance   BitLocker Drive Encryption ...
Bluetooth Device                      .           SingleInstance  Counters related to a remote ...
Cache                                 .           SingleInstance  The Cache performance object ...
Client Side Caching                   .           SingleInstance  Performance counters for SMB ...
```

<span data-ttu-id="cbf42-135">`Get-Counter` 使用带有星号 () 的 **ListSet** 参数 `*` 获取完整的计数器集列表。</span><span class="sxs-lookup"><span data-stu-id="cbf42-135">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="cbf42-136">**CounterSet** 对象沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="cbf42-136">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="cbf42-137">`Sort-Object` 使用 **Property** 参数来指定按 **CounterSetName** 对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="cbf42-137">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName** .</span></span> <span data-ttu-id="cbf42-138">对象将向下发送到 `Format-Table` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-138">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="cbf42-139">**AutoSize** 参数调整列宽以尽可能减少截断。</span><span class="sxs-lookup"><span data-stu-id="cbf42-139">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="cbf42-140">`.` **MachineName** 列中)  (点表示本地计算机。</span><span class="sxs-lookup"><span data-stu-id="cbf42-140">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="cbf42-141">示例5：运行后台作业以获取计数器数据</span><span class="sxs-lookup"><span data-stu-id="cbf42-141">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="cbf42-142">在此示例中，在 `Start-Job` `Get-Counter` 本地计算机上将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="cbf42-142">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="cbf42-143">若要查看作业的性能计数器输出，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cbf42-143">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="cbf42-144">`Start-Job` 使用 **ScriptBlock** 参数运行 `Get-Counter` 命令。</span><span class="sxs-lookup"><span data-stu-id="cbf42-144">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="cbf42-145">`Get-Counter` 使用 **counter** 参数来指定计数器路径 `\LogicalDisk(_Total)\% Free Space` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-145">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="cbf42-146">**MaxSamples** 参数指定获取计数器的1000示例。</span><span class="sxs-lookup"><span data-stu-id="cbf42-146">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="cbf42-147">示例6：从多台计算机获取计数器数据</span><span class="sxs-lookup"><span data-stu-id="cbf42-147">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="cbf42-148">此示例使用变量从两台计算机获取性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-148">This example uses a variable to get performance counter data from two computers.</span></span>

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

<span data-ttu-id="cbf42-149">`$DiskReads`变量存储 `\LogicalDisk(C:)\Disk Reads/sec` 计数器路径。</span><span class="sxs-lookup"><span data-stu-id="cbf42-149">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="cbf42-150">将 `$DiskReads` 变量向下发送到 `Get-Counter` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-150">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="cbf42-151">**计数器** 是第一个位置参数，接受存储在中的路径 `$DiskReads` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-151">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="cbf42-152">**ComputerName** 指定两台计算机， **MaxSamples** 指定从每台计算机获取10个样本。</span><span class="sxs-lookup"><span data-stu-id="cbf42-152">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="cbf42-153">示例7：从多个随机计算机获取计数器的实例值</span><span class="sxs-lookup"><span data-stu-id="cbf42-153">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="cbf42-154">此示例获取企业中的50随机远程计算机上的性能计数器的值。</span><span class="sxs-lookup"><span data-stu-id="cbf42-154">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="cbf42-155">**ComputerName** 参数使用存储在变量中的随机计算机名称。</span><span class="sxs-lookup"><span data-stu-id="cbf42-155">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="cbf42-156">若要更新变量中的计算机名，请重新创建变量。</span><span class="sxs-lookup"><span data-stu-id="cbf42-156">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="cbf42-157">**ComputerName** 参数中服务器名称的替代方法是使用文本文件。</span><span class="sxs-lookup"><span data-stu-id="cbf42-157">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="cbf42-158">例如：</span><span class="sxs-lookup"><span data-stu-id="cbf42-158">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="cbf42-159">计数器路径包含 `*` 实例名称中的星号 () ，以获取每台远程计算机的处理器的数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-159">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

<span data-ttu-id="cbf42-160">`Get-Random`Cmdlet 使用 `Get-Content` 从文件中选择50随机计算机名称 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-160">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="cbf42-161">远程计算机的名称存储在变量中 `$Servers` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-161">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="cbf42-162">`\Processor(*)\% Processor Time`计数器的路径存储在 `$Counter` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-162">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="cbf42-163">`Get-Counter` 使用 **Counter** 参数来指定变量中的计数器 `$Counter` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-163">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="cbf42-164">**ComputerName** 参数指定变量中的计算机名称 `$Servers` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-164">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="cbf42-165">示例8：使用 Path 属性获取格式化的路径名称</span><span class="sxs-lookup"><span data-stu-id="cbf42-165">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="cbf42-166">此示例使用计数器集的 **path** 属性来查找性能计数器的格式化路径名称。</span><span class="sxs-lookup"><span data-stu-id="cbf42-166">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="cbf42-167">管道与 cmdlet 一起用于 `Where-Object` 查找路径名称的子集。</span><span class="sxs-lookup"><span data-stu-id="cbf42-167">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="cbf42-168">若要查找计数器，请设置计数器路径的完整列表， (`|`) 和命令中删除管道 `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-168">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="cbf42-169">`$_`是管道中的当前对象的自动变量。</span><span class="sxs-lookup"><span data-stu-id="cbf42-169">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="cbf42-170">有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="cbf42-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

<span data-ttu-id="cbf42-171">`Get-Counter` 使用 **ListSet** 参数来指定 **内存** 计数器集。</span><span class="sxs-lookup"><span data-stu-id="cbf42-171">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="cbf42-172">命令括在括号中，以便 **Paths** 属性以字符串的形式返回每个路径。</span><span class="sxs-lookup"><span data-stu-id="cbf42-172">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="cbf42-173">对象将向下发送到 `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-173">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="cbf42-174">`Where-Object` 使用变量 `$_` 来处理每个对象，并使用 `-like` 运算符查找该字符串的匹配项 `*Cache*` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-174">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="cbf42-175">星号 (`*`) 是任何字符的通配符。</span><span class="sxs-lookup"><span data-stu-id="cbf42-175">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="cbf42-176">示例9：使用 PathsWithInstances 属性获取格式化的路径名称</span><span class="sxs-lookup"><span data-stu-id="cbf42-176">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="cbf42-177">此示例获取包含 **PhysicalDisk** 性能计数器的实例的格式化路径名称。</span><span class="sxs-lookup"><span data-stu-id="cbf42-177">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

<span data-ttu-id="cbf42-178">`Get-Counter` 使用 **ListSet** 参数来指定 **PhysicalDisk** 计数器集。</span><span class="sxs-lookup"><span data-stu-id="cbf42-178">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="cbf42-179">命令括在括号中，以便 **PathsWithInstances** 属性将每个路径实例作为字符串返回。</span><span class="sxs-lookup"><span data-stu-id="cbf42-179">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="cbf42-180">示例10：获取计数器集中每个计数器的单个值</span><span class="sxs-lookup"><span data-stu-id="cbf42-180">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="cbf42-181">在此示例中，将为本地计算机的 **内存** 计数器集中的每个性能计数器返回单个值。</span><span class="sxs-lookup"><span data-stu-id="cbf42-181">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

<span data-ttu-id="cbf42-182">`Get-Counter` 使用 **ListSet** 参数来指定 **内存** 计数器集。</span><span class="sxs-lookup"><span data-stu-id="cbf42-182">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="cbf42-183">命令括在括号中，以便 **Paths** 属性以字符串的形式返回每个路径。</span><span class="sxs-lookup"><span data-stu-id="cbf42-183">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="cbf42-184">路径存储在 `$MemCounters` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-184">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="cbf42-185">`Get-Counter` 使用 **counter** 参数来指定变量中的计数器路径 `$MemCounters` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-185">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="cbf42-186">示例11：显示对象的属性值</span><span class="sxs-lookup"><span data-stu-id="cbf42-186">Example 11: Display an object's property values</span></span>

<span data-ttu-id="cbf42-187">**PerformanceCounterSample** 对象中的属性值表示每个数据样本。</span><span class="sxs-lookup"><span data-stu-id="cbf42-187">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="cbf42-188">在此示例中，我们使用 **CounterSamples** 对象的属性来检查、选择、排序和分组数据。</span><span class="sxs-lookup"><span data-stu-id="cbf42-188">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

<span data-ttu-id="cbf42-189">计数器路径存储在 `$Counter` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-189">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="cbf42-190">`Get-Counter` 获取计数器值的一个样本，并将结果存储在 `$Data` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-190">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="cbf42-191">`$Data`变量使用 **CounterSamples** 属性获取该对象的属性。</span><span class="sxs-lookup"><span data-stu-id="cbf42-191">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="cbf42-192">将对象向下发送到 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-192">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="cbf42-193">**Property** 参数使用) 通配符 (星号 `*` 来选择所有属性。</span><span class="sxs-lookup"><span data-stu-id="cbf42-193">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="cbf42-194">示例12：性能计数器数组值</span><span class="sxs-lookup"><span data-stu-id="cbf42-194">Example 12: Performance counter array values</span></span>

<span data-ttu-id="cbf42-195">在此示例中，变量存储每个性能计数器。</span><span class="sxs-lookup"><span data-stu-id="cbf42-195">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="cbf42-196">**CounterSamples** 属性是可显示特定计数器值的数组。</span><span class="sxs-lookup"><span data-stu-id="cbf42-196">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="cbf42-197">若要显示每个计数器示例，请使用 `$Counter.CounterSamples` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-197">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="cbf42-198">`Get-Counter` 使用 **counter** 参数来指定计数器 `\Processor(*)\% Processor Time` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-198">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="cbf42-199">值存储在 `$Counter` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-199">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="cbf42-200">`$Counter.CounterSamples[0]` 显示第一个计数器值的数组值。</span><span class="sxs-lookup"><span data-stu-id="cbf42-200">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="cbf42-201">示例13：比较性能计数器值</span><span class="sxs-lookup"><span data-stu-id="cbf42-201">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="cbf42-202">此示例查找本地计算机上每个处理器使用的处理器时间量。</span><span class="sxs-lookup"><span data-stu-id="cbf42-202">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="cbf42-203">**CounterSamples** 属性用于将计数器数据与指定值进行比较。</span><span class="sxs-lookup"><span data-stu-id="cbf42-203">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="cbf42-204">若要显示每个计数器示例，请使用 `$Counter.CounterSamples` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-204">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

<span data-ttu-id="cbf42-205">`Get-Counter` 使用 **counter** 参数来指定计数器 `\Processor(*)\% Processor Time` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-205">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="cbf42-206">值存储在 `$Counter` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-206">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="cbf42-207">存储在中的对象 `$Counter.CounterSamples` 会沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="cbf42-207">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="cbf42-208">`Where-Object` 使用脚本块将每个对象的值与指定的值20进行比较。</span><span class="sxs-lookup"><span data-stu-id="cbf42-208">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="cbf42-209">`$_.CookedValue`是管道中的当前对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cbf42-209">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="cbf42-210">显示 **CookedValue** 小于20的计数器。</span><span class="sxs-lookup"><span data-stu-id="cbf42-210">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="cbf42-211">示例14：对性能计数器数据进行排序</span><span class="sxs-lookup"><span data-stu-id="cbf42-211">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="cbf42-212">此示例演示如何对性能计数器数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="cbf42-212">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="cbf42-213">该示例在示例中查找正在使用处理器时间最多的计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="cbf42-213">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

<span data-ttu-id="cbf42-214">`Get-Counter` 使用 **counter** 参数为 `\Process(*)\% Processor Time` 本地计算机上的所有进程指定计数器。</span><span class="sxs-lookup"><span data-stu-id="cbf42-214">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="cbf42-215">结果存储在 `$Procs` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cbf42-215">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="cbf42-216">`$Procs`带有 **CounterSamples** 属性的变量将 **PerformanceCounterSample** 对象向下发送管道。</span><span class="sxs-lookup"><span data-stu-id="cbf42-216">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="cbf42-217">`Sort-Object` 使用 **Property** 参数按 **CookedValue** 按 **降序** 对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="cbf42-217">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="cbf42-218">`Format-Table` 使用 **Property** 参数来选择输出的列。</span><span class="sxs-lookup"><span data-stu-id="cbf42-218">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="cbf42-219">**AutoSize** 参数调整列宽以尽可能减少截断。</span><span class="sxs-lookup"><span data-stu-id="cbf42-219">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="cbf42-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cbf42-220">PARAMETERS</span></span>

### <span data-ttu-id="cbf42-221">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="cbf42-221">-ComputerName</span></span>

<span data-ttu-id="cbf42-222">指定一个计算机名称或以逗号分隔的 **远程** 计算机名称的数组。</span><span class="sxs-lookup"><span data-stu-id="cbf42-222">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="cbf42-223">使用 NetBIOS 名称、IP 地址或计算机的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="cbf42-223">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="cbf42-224">若要从 **本地** 计算机获取性能计数器数据，请排除 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-224">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="cbf42-225">对于包含 **MachineName** 列的输出（如 **ListSet** ），) 点 (`.` 表示本地计算机。</span><span class="sxs-lookup"><span data-stu-id="cbf42-225">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="cbf42-226">`Get-Counter` 不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="cbf42-226">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="cbf42-227">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-227">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cbf42-228">-Continuous</span><span class="sxs-lookup"><span data-stu-id="cbf42-228">-Continuous</span></span>

<span data-ttu-id="cbf42-229">指定 **连续** 后，将 `Get-Counter` 获取示例，直到按下 <kbd>CTRL</kbd> + <kbd>C</kbd>。</span><span class="sxs-lookup"><span data-stu-id="cbf42-229">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="cbf42-230">每秒为每个指定的性能计数器获取样本。</span><span class="sxs-lookup"><span data-stu-id="cbf42-230">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="cbf42-231">使用 **SampleInterval** 参数可增加连续样本之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="cbf42-231">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cbf42-232">-Counter</span><span class="sxs-lookup"><span data-stu-id="cbf42-232">-Counter</span></span>

<span data-ttu-id="cbf42-233">指定一个或多个计数器路径的路径。</span><span class="sxs-lookup"><span data-stu-id="cbf42-233">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="cbf42-234">路径作为以逗号分隔的数组、变量或文本文件中的值输入。</span><span class="sxs-lookup"><span data-stu-id="cbf42-234">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="cbf42-235">可以将计数器路径字符串沿管道向下发送到 `Get-Counter` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-235">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="cbf42-236">计数器路径使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="cbf42-236">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="cbf42-237">例如：</span><span class="sxs-lookup"><span data-stu-id="cbf42-237">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="cbf42-238">在 `\\ComputerName` 性能计数器路径中是可选的。</span><span class="sxs-lookup"><span data-stu-id="cbf42-238">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="cbf42-239">如果该计数器路径不包含计算机名称，则 `Get-Counter` 使用本地计算机。</span><span class="sxs-lookup"><span data-stu-id="cbf42-239">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="cbf42-240">`*`实例中) 星号 (为获取计数器所有实例的通配符。</span><span class="sxs-lookup"><span data-stu-id="cbf42-240">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="cbf42-241">-ListSet</span><span class="sxs-lookup"><span data-stu-id="cbf42-241">-ListSet</span></span>

<span data-ttu-id="cbf42-242">列出计算机上的性能计数器集。</span><span class="sxs-lookup"><span data-stu-id="cbf42-242">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="cbf42-243">使用星号 (`*`) 指定所有计数器集。</span><span class="sxs-lookup"><span data-stu-id="cbf42-243">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="cbf42-244">输入一个名称或以逗号分隔的计数器集名称字符串。</span><span class="sxs-lookup"><span data-stu-id="cbf42-244">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="cbf42-245">可以向下发送计数器集名称。</span><span class="sxs-lookup"><span data-stu-id="cbf42-245">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="cbf42-246">若要获取计数器集的格式计数器路径，请使用 **ListSet** 参数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-246">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="cbf42-247">每个计数器集的 **Paths** 和 **PathsWithInstances** 属性都包含格式化为字符串的单个计数器路径。</span><span class="sxs-lookup"><span data-stu-id="cbf42-247">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="cbf42-248">可以将计数器路径字符串保存在变量中，或使用管道将该字符串发送到其他 `Get-Counter` 命令。</span><span class="sxs-lookup"><span data-stu-id="cbf42-248">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="cbf42-249">例如，将每个 **处理器** 计数器路径发送到 `Get-Counter` ：</span><span class="sxs-lookup"><span data-stu-id="cbf42-249">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="cbf42-250">-MaxSamples</span><span class="sxs-lookup"><span data-stu-id="cbf42-250">-MaxSamples</span></span>

<span data-ttu-id="cbf42-251">指定从每个指定的性能计数器获取的样本数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-251">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="cbf42-252">若要获取样本的常量流，请使用 **连续** 参数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-252">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="cbf42-253">如果未指定 **MaxSamples** 参数，则 `Get-Counter` 只为每个指定的计数器获取一个样本。</span><span class="sxs-lookup"><span data-stu-id="cbf42-253">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="cbf42-254">若要收集大型数据集，请将 `Get-Counter` 作为 PowerShell 后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="cbf42-254">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="cbf42-255">有关详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="cbf42-255">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cbf42-256">-SampleInterval</span><span class="sxs-lookup"><span data-stu-id="cbf42-256">-SampleInterval</span></span>

<span data-ttu-id="cbf42-257">指定每个指定性能计数器的样本之间的秒数。</span><span class="sxs-lookup"><span data-stu-id="cbf42-257">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="cbf42-258">如果未指定 **SampleInterval** 参数，则 `Get-Counter` 使用一秒的间隔。</span><span class="sxs-lookup"><span data-stu-id="cbf42-258">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cbf42-259">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cbf42-259">CommonParameters</span></span>

<span data-ttu-id="cbf42-260">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cbf42-260">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cbf42-261">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="cbf42-261">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cbf42-262">输入</span><span class="sxs-lookup"><span data-stu-id="cbf42-262">INPUTS</span></span>

### <span data-ttu-id="cbf42-263">System.String[]</span><span class="sxs-lookup"><span data-stu-id="cbf42-263">System.String[]</span></span>

<span data-ttu-id="cbf42-264">`Get-Counter` 接受计数器路径和计数器集名称的管道输入。</span><span class="sxs-lookup"><span data-stu-id="cbf42-264">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="cbf42-265">输出</span><span class="sxs-lookup"><span data-stu-id="cbf42-265">OUTPUTS</span></span>

### <span data-ttu-id="cbf42-266">Microsoft.PowerShell.Commands.GetCounter.CounterSet、Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet、Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span><span class="sxs-lookup"><span data-stu-id="cbf42-266">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="cbf42-267">若要查看对象的属性，请向下将输出发送到 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="cbf42-267">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="cbf42-268">输出的对象类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="cbf42-268">The object types that are output are as follows:</span></span>

<span data-ttu-id="cbf42-269">**ListSet** 参数： **microsoft.powershell.commands.getcounter.counterset** 的参数</span><span class="sxs-lookup"><span data-stu-id="cbf42-269">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="cbf42-270">**计数器** 参数： **microsoft.powershell.commands.getcounter.counterset. PerformanceCounterSampleSet**</span><span class="sxs-lookup"><span data-stu-id="cbf42-270">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="cbf42-271">**CounterSamples** 属性： **microsoft.powershell.commands.getcounter.counterset. PerformanceCounterSample**</span><span class="sxs-lookup"><span data-stu-id="cbf42-271">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="cbf42-272">注释</span><span class="sxs-lookup"><span data-stu-id="cbf42-272">NOTES</span></span>

<span data-ttu-id="cbf42-273">如果未指定任何参数，则 `Get-Counter` 为每个指定的性能计数器获取一个样本。</span><span class="sxs-lookup"><span data-stu-id="cbf42-273">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="cbf42-274">使用 **MaxSamples** 和 **连续** 参数获取更多示例。</span><span class="sxs-lookup"><span data-stu-id="cbf42-274">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="cbf42-275">`Get-Counter` 在样本之间使用一秒的间隔。</span><span class="sxs-lookup"><span data-stu-id="cbf42-275">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="cbf42-276">使用 **SampleInterval** 参数增加间隔。</span><span class="sxs-lookup"><span data-stu-id="cbf42-276">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="cbf42-277">**MaxSamples** 和 **SampleInterval** 值适用于命令中每台计算机上的所有计数器。</span><span class="sxs-lookup"><span data-stu-id="cbf42-277">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="cbf42-278">若要为不同的计数器设置不同的值，请输入单独的 `Get-Counter` 命令。</span><span class="sxs-lookup"><span data-stu-id="cbf42-278">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

## <span data-ttu-id="cbf42-279">相关链接</span><span class="sxs-lookup"><span data-stu-id="cbf42-279">RELATED LINKS</span></span>

[<span data-ttu-id="cbf42-280">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cbf42-280">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="cbf42-281">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="cbf42-281">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="cbf42-282">Format-List</span><span class="sxs-lookup"><span data-stu-id="cbf42-282">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="cbf42-283">Format-Table</span><span class="sxs-lookup"><span data-stu-id="cbf42-283">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="cbf42-284">Get-Member</span><span class="sxs-lookup"><span data-stu-id="cbf42-284">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="cbf42-285">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="cbf42-285">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="cbf42-286">Start-Job</span><span class="sxs-lookup"><span data-stu-id="cbf42-286">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="cbf42-287">Where-Object</span><span class="sxs-lookup"><span data-stu-id="cbf42-287">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)
