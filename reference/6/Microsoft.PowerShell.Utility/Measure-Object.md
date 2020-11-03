---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: a4d80876136ca2c5837be9288c22776dc5a6a6f2
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "93199267"
---
# <span data-ttu-id="bc0b7-103">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-103">Measure-Object</span></span>

## <span data-ttu-id="bc0b7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="bc0b7-104">SYNOPSIS</span></span>
<span data-ttu-id="bc0b7-105">计算对象的数值属性，以及字符串对象（如文本文件）中的字符、单词和行。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-105">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="bc0b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc0b7-106">SYNTAX</span></span>

### <span data-ttu-id="bc0b7-107">GenericMeasure（默认值）</span><span class="sxs-lookup"><span data-stu-id="bc0b7-107">GenericMeasure (Default)</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### <span data-ttu-id="bc0b7-108">TextMeasure</span><span class="sxs-lookup"><span data-stu-id="bc0b7-108">TextMeasure</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="bc0b7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc0b7-109">DESCRIPTION</span></span>

<span data-ttu-id="bc0b7-110">`Measure-Object`Cmdlet 计算特定类型的对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-110">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="bc0b7-111">`Measure-Object` 执行三种类型的度量，具体取决于命令中的参数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-111">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="bc0b7-112">`Measure-Object`Cmdlet 对对象的属性值执行计算。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-112">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="bc0b7-113">您可以使用 `Measure-Object` 来对对象进行计数，或使用指定 **属性** 对对象计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-113">You can use `Measure-Object` to count objects or count objects with a specified **Property** .</span></span> <span data-ttu-id="bc0b7-114">还可以使用 `Measure-Object` 来计算数值的 **最小** 值、 **最大** 值、 **总和** 、 **StandardDeviation** 值和 **平均值** 。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-114">You can also use `Measure-Object` to calculate the **Minimum** , **Maximum** , **Sum** , **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="bc0b7-115">对于 **字符串** 对象，还可以使用 `Measure-Object` 来计算行数、字数和字符数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-115">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="bc0b7-116">示例</span><span class="sxs-lookup"><span data-stu-id="bc0b7-116">EXAMPLES</span></span>

### <span data-ttu-id="bc0b7-117">示例 1：计数目录中的文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="bc0b7-117">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="bc0b7-118">此命令对当前目录中的文件和文件夹进行计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-118">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="bc0b7-119">示例 2：度量目录中的文件</span><span class="sxs-lookup"><span data-stu-id="bc0b7-119">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="bc0b7-120">此命令显示当前目录中所有文件的大小的 **最小值** 、 **最大** 值和 **总和** ，以及目录中的文件的平均大小。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-120">This command displays the **Minimum** , **Maximum** , and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="bc0b7-121">示例 3：度量文本文件中的文本</span><span class="sxs-lookup"><span data-stu-id="bc0b7-121">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="bc0b7-122">此命令显示 Text.txt 文件中的字符数、字数和行数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-122">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="bc0b7-123">如果没有 **Raw** 参数，则会 `Get-Content` 将文件作为行的数组输出。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-123">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="bc0b7-124">第一个命令使用 `Set-Content` 将一些默认文本添加到文件。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-124">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="bc0b7-125">示例4：度量值对象包含指定属性</span><span class="sxs-lookup"><span data-stu-id="bc0b7-125">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="bc0b7-126">此示例对具有 **DisplayName** 属性的对象的数目进行计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-126">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="bc0b7-127">前两个命令检索本地计算机上的所有服务和进程。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-127">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="bc0b7-128">第三个命令对服务和进程的组合数量进行计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-128">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="bc0b7-129">最后一个命令将结果与结果组合在一起 `Measure-Object` 。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-129">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="bc0b7-130">" **System.object** " 对象没有 **DisplayName** 属性，并且不在最终的计数中。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-130">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### <span data-ttu-id="bc0b7-131">示例 5：度量 CSV 文件的内容</span><span class="sxs-lookup"><span data-stu-id="bc0b7-131">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="bc0b7-132">此命令计算一家公司雇员的平均服务年限。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-132">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="bc0b7-133">该 `ServiceYrs.csv` 文件是一个 CSV 文件，其中包含每个员工的员工人数和年服务。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-133">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="bc0b7-134">表中的第一行是 **EmpNo** ， **年** 的标题行。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-134">The first row in the table is a header row of **EmpNo** , **Years** .</span></span>

<span data-ttu-id="bc0b7-135">当你使用 `Import-Csv` 导入文件时，结果将是 **PSCustomObject** ，其便笺属性为 **EmpNo** 和 **年** 。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-135">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years** .</span></span>
<span data-ttu-id="bc0b7-136">您可以使用 `Measure-Object` 来计算这些属性的值，就像对象的任何其他属性一样。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-136">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="bc0b7-137">示例 6：度量布尔值</span><span class="sxs-lookup"><span data-stu-id="bc0b7-137">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="bc0b7-138">此示例演示如何 `Measure-Object` 测量布尔值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-138">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="bc0b7-139">在这种情况下，它使用 **PSIsContainer** **布尔** 值属性来测量当前目录中 () 文件夹的发生情况。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-139">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### <span data-ttu-id="bc0b7-140">示例7：度量值字符串</span><span class="sxs-lookup"><span data-stu-id="bc0b7-140">Example 7: Measure strings</span></span>

<span data-ttu-id="bc0b7-141">下面的示例测量行数，首先是单个字符串，然后是多个字符串。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-141">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="bc0b7-142">换行符将 <code>\`n</code> 字符串分隔为多个行。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-142">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

### <span data-ttu-id="bc0b7-143">示例8：度量所有值</span><span class="sxs-lookup"><span data-stu-id="bc0b7-143">Example 8: Measure all the values</span></span>

<span data-ttu-id="bc0b7-144">从 PowerShell 6 开始，的 **AllStats** 参数 `Measure-Object` 允许你将所有统计信息一起测量。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-144">Beginning in PowerShell 6, the **AllStats** parameter of `Measure-Object` allows you to measure all the statistics together.</span></span>

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### <span data-ttu-id="bc0b7-145">示例9：使用 scriptblock 属性测量</span><span class="sxs-lookup"><span data-stu-id="bc0b7-145">Example 9: Measure using scriptblock properties</span></span>

<span data-ttu-id="bc0b7-146">从 PowerShell 6 开始， `Measure-Object` 支持 **ScriptBlock** 属性。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-146">Beginning in PowerShell 6, `Measure-Object` supports **ScriptBlock** properties.</span></span> <span data-ttu-id="bc0b7-147">下面的示例演示如何使用 **ScriptBlock** 属性来确定目录中所有文件的大小（以 Mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-147">The following example demonstrates how to use a **ScriptBlock** property to determine the size, in MegaBytes, of all the files in a directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### <span data-ttu-id="bc0b7-148">示例10：度量值哈希表</span><span class="sxs-lookup"><span data-stu-id="bc0b7-148">Example 10: Measure hashtables</span></span>

<span data-ttu-id="bc0b7-149">从 PowerShell 6 开始， `Measure-Object` 支持度量 **哈希表** 输入。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-149">Beginning in PowerShell 6, `Measure-Object` supports measurement of **hashtable** input.</span></span> <span data-ttu-id="bc0b7-150">下面的示例确定 `num` 3 个 **哈希表** 对象的键的最大值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-150">The following example determines the largest value for the `num` key of 3 **hashtable** objects.</span></span>

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### <span data-ttu-id="bc0b7-151">示例11：度量标准偏差</span><span class="sxs-lookup"><span data-stu-id="bc0b7-151">Example 11: Measure the Standard Deviation</span></span>

<span data-ttu-id="bc0b7-152">从 PowerShell 6 开始， `Measure-Object` 支持 `-StandardDeviation` 参数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-152">Beginning in PowerShell 6, `Measure-Object` supports the `-StandardDeviation` parameter.</span></span> <span data-ttu-id="bc0b7-153">下面的示例确定所有进程使用的 CPU 的 *标准偏差* 。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-153">The following example determines the *standard deviation* for the CPU used by all processes.</span></span> <span data-ttu-id="bc0b7-154">较大的偏差将指示占用最多 CPU 的少量进程。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-154">A large deviation would indicate a small number of processes consuming the most CPU.</span></span>

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### <span data-ttu-id="bc0b7-155">示例12：使用通配符度量值</span><span class="sxs-lookup"><span data-stu-id="bc0b7-155">Example 12: Measure using wildcards</span></span>

<span data-ttu-id="bc0b7-156">从 PowerShell 6 开始， `Measure-Object` 支持在属性名称中使用通配符对对象进行度量。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-156">Beginning in PowerShell 6, `Measure-Object` supports measurement of objects by using wildcards in property names.</span></span> <span data-ttu-id="bc0b7-157">下面的示例确定一组进程中任何类型的分页内存使用量的最大值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-157">The following example determines the maximum of any type of paged memory usage among a set of processes.</span></span>

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## <span data-ttu-id="bc0b7-158">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc0b7-158">PARAMETERS</span></span>

### <span data-ttu-id="bc0b7-159">-Average</span><span class="sxs-lookup"><span data-stu-id="bc0b7-159">-Average</span></span>

<span data-ttu-id="bc0b7-160">指示该 cmdlet 显示指定属性的平均值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-160">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-161">-Character</span><span class="sxs-lookup"><span data-stu-id="bc0b7-161">-Character</span></span>

<span data-ttu-id="bc0b7-162">指示该 cmdlet 对输入对象中的字符数进行计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-162">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="bc0b7-163">每 *个输入对象内以及输入* 对象 *中* 的 **单词** 、 **字符** 和 **行** 开关均计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-163">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="bc0b7-164">请参阅示例7。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-164">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-165">-IgnoreWhiteSpace</span><span class="sxs-lookup"><span data-stu-id="bc0b7-165">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="bc0b7-166">指示 cmdlet 忽略字符计数中的空格。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-166">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="bc0b7-167">默认情况下，不忽略空格。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-167">By default, white space is not ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bc0b7-168">-InputObject</span></span>

<span data-ttu-id="bc0b7-169">指定要测量的对象。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-169">Specifies the objects to be measured.</span></span>
<span data-ttu-id="bc0b7-170">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-170">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="bc0b7-171">当你将 **inputobject** 参数与一起使用时 `Measure-Object` ， `Measure-Object` **inputobject** 值将被视为单个对象，而不是管道将命令结果传递给。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-171">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="bc0b7-172">`Measure-Object`如果要根据对象是否在定义的属性中具有特定值，则建议在管道中使用。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-172">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-173">-Line</span><span class="sxs-lookup"><span data-stu-id="bc0b7-173">-Line</span></span>

<span data-ttu-id="bc0b7-174">指示该 cmdlet 对输入对象中的行数进行计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-174">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="bc0b7-175">每 *个输入对象内以及输入* 对象 *中* 的 **单词** 、 **字符** 和 **行** 开关均计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-175">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="bc0b7-176">请参阅示例7。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-176">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-177">-Maximum</span><span class="sxs-lookup"><span data-stu-id="bc0b7-177">-Maximum</span></span>

<span data-ttu-id="bc0b7-178">指示该 cmdlet 显示指定属性的最大值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-178">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-179">-Minimum</span><span class="sxs-lookup"><span data-stu-id="bc0b7-179">-Minimum</span></span>

<span data-ttu-id="bc0b7-180">指示该 cmdlet 显示指定属性的最小值。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-180">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-181">-Property</span><span class="sxs-lookup"><span data-stu-id="bc0b7-181">-Property</span></span>

<span data-ttu-id="bc0b7-182">指定要度量的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-182">Specifies one or more properties to measure.</span></span> <span data-ttu-id="bc0b7-183">如果未指定任何其他度量值，则 `Measure-Object` 会计算具有指定属性的对象。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-183">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

<span data-ttu-id="bc0b7-184">**Property** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-184">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="bc0b7-185">计算属性必须是脚本块。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-185">The calculated property must be a script block.</span></span> <span data-ttu-id="bc0b7-186">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-186">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="bc0b7-187">-StandardDeviation</span><span class="sxs-lookup"><span data-stu-id="bc0b7-187">-StandardDeviation</span></span>

<span data-ttu-id="bc0b7-188">指示该 cmdlet 显示指定属性的值的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-188">Indicates that the cmdlet displays the standard deviation of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-189">-Sum</span><span class="sxs-lookup"><span data-stu-id="bc0b7-189">-Sum</span></span>

<span data-ttu-id="bc0b7-190">指示该 cmdlet 显示指定属性的值的总和。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-190">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-191">-AllStats</span><span class="sxs-lookup"><span data-stu-id="bc0b7-191">-AllStats</span></span>

<span data-ttu-id="bc0b7-192">指示该 cmdlet 显示指定属性的所有统计信息。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-192">Indicates that the cmdlet displays all the statistics of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-193">-Word</span><span class="sxs-lookup"><span data-stu-id="bc0b7-193">-Word</span></span>

<span data-ttu-id="bc0b7-194">指示该 cmdlet 对输入对象中的单词进行计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-194">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="bc0b7-195">每 *个输入对象内以及输入* 对象 *中* 的 **单词** 、 **字符** 和 **行** 开关均计数。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-195">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="bc0b7-196">请参阅示例7。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-196">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc0b7-197">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bc0b7-197">CommonParameters</span></span>

<span data-ttu-id="bc0b7-198">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-198">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc0b7-199">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-199">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc0b7-200">输入</span><span class="sxs-lookup"><span data-stu-id="bc0b7-200">INPUTS</span></span>

### <span data-ttu-id="bc0b7-201">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="bc0b7-201">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="bc0b7-202">可以通过管道将对象传递给 `Measure-Object` 。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-202">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="bc0b7-203">输出</span><span class="sxs-lookup"><span data-stu-id="bc0b7-203">OUTPUTS</span></span>

### <span data-ttu-id="bc0b7-204">GenericMeasureInfo。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-204">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="bc0b7-205">TextMeasureInfo。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-205">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="bc0b7-206">如果使用 **Word** 参数，则 `Measure-Object` 返回 **TextMeasureInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-206">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="bc0b7-207">否则，它返回 **GenericMeasureInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="bc0b7-207">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="bc0b7-208">注释</span><span class="sxs-lookup"><span data-stu-id="bc0b7-208">NOTES</span></span>

## <span data-ttu-id="bc0b7-209">相关链接</span><span class="sxs-lookup"><span data-stu-id="bc0b7-209">RELATED LINKS</span></span>

[<span data-ttu-id="bc0b7-210">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="bc0b7-210">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="bc0b7-211">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-211">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="bc0b7-212">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-212">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="bc0b7-213">Group-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-213">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="bc0b7-214">New-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-214">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="bc0b7-215">Select-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-215">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="bc0b7-216">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-216">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="bc0b7-217">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-217">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="bc0b7-218">Where-Object</span><span class="sxs-lookup"><span data-stu-id="bc0b7-218">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
