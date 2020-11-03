---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197967"
---
# <span data-ttu-id="d2868-103">Convert-String</span><span class="sxs-lookup"><span data-stu-id="d2868-103">Convert-String</span></span>

## <span data-ttu-id="d2868-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d2868-104">SYNOPSIS</span></span>
<span data-ttu-id="d2868-105">格式化字符串以匹配示例。</span><span class="sxs-lookup"><span data-stu-id="d2868-105">Formats a string to match examples.</span></span>

## <span data-ttu-id="d2868-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2868-106">SYNTAX</span></span>

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## <span data-ttu-id="d2868-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d2868-107">DESCRIPTION</span></span>

<span data-ttu-id="d2868-108">**转换字符串** cmdlet 将字符串的格式设置为与示例格式匹配。</span><span class="sxs-lookup"><span data-stu-id="d2868-108">The **Convert-String** cmdlet formats a string to match the format of examples.</span></span>

## <span data-ttu-id="d2868-109">示例</span><span class="sxs-lookup"><span data-stu-id="d2868-109">EXAMPLES</span></span>

### <span data-ttu-id="d2868-110">示例1：转换字符串格式</span><span class="sxs-lookup"><span data-stu-id="d2868-110">Example 1: Convert format of a string</span></span>

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

<span data-ttu-id="d2868-111">第一个命令创建一个包含名字和姓氏的数组。</span><span class="sxs-lookup"><span data-stu-id="d2868-111">The first command creates an array that contains first and last names.</span></span>

<span data-ttu-id="d2868-112">第二个命令根据示例设置名称的格式。</span><span class="sxs-lookup"><span data-stu-id="d2868-112">The second command formats the names according to the example.</span></span>
<span data-ttu-id="d2868-113">它将姓放在输出中，后跟一个初始。</span><span class="sxs-lookup"><span data-stu-id="d2868-113">It puts the surname first in the output, followed by an initial.</span></span>

### <span data-ttu-id="d2868-114">示例2：简化字符串的格式</span><span class="sxs-lookup"><span data-stu-id="d2868-114">Example 2: Simplify format of a string</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

<span data-ttu-id="d2868-115">第一个命令创建一个包含名字、中间名和姓氏的数组。</span><span class="sxs-lookup"><span data-stu-id="d2868-115">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="d2868-116">请注意，最后一个条目没有中间名。</span><span class="sxs-lookup"><span data-stu-id="d2868-116">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="d2868-117">第二个命令根据示例设置名称的格式。</span><span class="sxs-lookup"><span data-stu-id="d2868-117">The second command formats the names according to the example.</span></span>
<span data-ttu-id="d2868-118">它将姓氏置于输出的开头，后接名字。</span><span class="sxs-lookup"><span data-stu-id="d2868-118">It puts the last name first in the output, followed by the first name.</span></span>
<span data-ttu-id="d2868-119">删除所有中间名;没有中间名的条目得到正确处理。</span><span class="sxs-lookup"><span data-stu-id="d2868-119">All middle names removed; entry without middle name is handled correctly.</span></span>

### <span data-ttu-id="d2868-120">示例3：当字符串不匹配示例时的输出管理</span><span class="sxs-lookup"><span data-stu-id="d2868-120">Example 3: Output management when strings don't match example</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

<span data-ttu-id="d2868-121">第一个命令创建一个包含名字、中间名和姓氏的数组。</span><span class="sxs-lookup"><span data-stu-id="d2868-121">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="d2868-122">请注意，最后一个条目没有中间名。</span><span class="sxs-lookup"><span data-stu-id="d2868-122">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="d2868-123">第二个命令根据示例设置名称的格式。</span><span class="sxs-lookup"><span data-stu-id="d2868-123">The second command formats the names according to the example.</span></span>
<span data-ttu-id="d2868-124">它将 **中间名** 放在输出的开头，后跟名字。</span><span class="sxs-lookup"><span data-stu-id="d2868-124">It puts the **middle name** first in the output, followed by the first name.</span></span>
<span data-ttu-id="d2868-125">将跳过 **$Composers** 中的最后一项，因为它不匹配示例模式：它没有中间名。</span><span class="sxs-lookup"><span data-stu-id="d2868-125">The last entry in **$Composers** is skipped, because it doesn't match the sample pattern: it has no middle name.</span></span>

### <span data-ttu-id="d2868-126">示例4：对美空格注意事项</span><span class="sxs-lookup"><span data-stu-id="d2868-126">Example 4: Caution with beauty spaces</span></span>

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

<span data-ttu-id="d2868-127">第一个命令创建名字和姓氏的数组。</span><span class="sxs-lookup"><span data-stu-id="d2868-127">The first command creates an array of first and last names.</span></span>
<span data-ttu-id="d2868-128">请注意，第二个和第四项在姓氏之后有多余的尾随空格。</span><span class="sxs-lookup"><span data-stu-id="d2868-128">Note that second and fourth items have an extra trailing space, after the last name.</span></span>

<span data-ttu-id="d2868-129">第二个命令将转换与示例模式匹配的所有字符串： _单词、空格、单词和最后尾随空格，并_ 在等号之前进行。</span><span class="sxs-lookup"><span data-stu-id="d2868-129">The second command converts all strings that match the sample pattern: _word, space, word, and final trailing space_ , all of this before the equal sign.</span></span>
<span data-ttu-id="d2868-130">另外，请注意输出中的前导空格。</span><span class="sxs-lookup"><span data-stu-id="d2868-130">Also, note the leading space in the output.</span></span>

### <span data-ttu-id="d2868-131">示例5：设置具有多个模式的进程信息的格式</span><span class="sxs-lookup"><span data-stu-id="d2868-131">Example 5: Format process information with multiple patterns</span></span>

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

<span data-ttu-id="d2868-132">**$ExamplePatterns** 通过示例定义数据中的不同预期模式。</span><span class="sxs-lookup"><span data-stu-id="d2868-132">**$ExamplePatterns** defines different expected patterns in the data, through examples.</span></span>

<span data-ttu-id="d2868-133">第一种模式是 `@{before='"Hello","World"'; after='World: Hello'}` 按如下所示读取：应为这样 _的字符串：字词括在双引号中，然后是逗号，_ 
 _最后是括在引号中的第二个和最后一个单词。_ 
_字符串中没有空格。输出：在不使用引号的情况下，首先放置第二个单词，_ 
 _不使用引号，然后输入单个空格和第一个单词。_</span><span class="sxs-lookup"><span data-stu-id="d2868-133">The first pattern, `@{before='"Hello","World"'; after='World: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then the second, and last, word enclosed in quotes;_
_with no spaces in the string. On the output: place second word first,_
_without quotes, then a single space, and then the first word, without quotes._</span></span>

<span data-ttu-id="d2868-134">第二种模式是 `@{before='"Hello","1"'; after='1: Hello'}` 按如下所示读取：应为这样 _的字符串：字词括在双引号中，然后是逗号，_ 然后 
 _是用引号引起来的数字;_ 
_字符串中没有空格。在输出上：将数字置于第一，_ 
 _不使用引号，然后是单个空格，然后是不带引号的单词。_</span><span class="sxs-lookup"><span data-stu-id="d2868-134">The second pattern, `@{before='"Hello","1"'; after='1: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then a number enclosed in quotes;_
_with no spaces in the string. On the output: place the number first,_
_without quotes, then a single space, and then the word, without quotes._</span></span>

<span data-ttu-id="d2868-135">第三种模式是按如下所示 `@{before='"Hello-World","22"'; after='22: Hello-World'}` 读取： _需要字符串，其中两个单词之间有连字符，中间用双引号括起来_ 
 _，然后是逗号，然后是用引号引起来的数字。_ 
_逗号和第三个双引号之间没有空格。_ 
_在输出上：首先放置数字，不使用引号，然后输入单个空格，_ 
再 _加上带引号的单词。_</span><span class="sxs-lookup"><span data-stu-id="d2868-135">The third pattern, `@{before='"Hello-World","22"'; after='22: Hello-World'}`, reads as follows: _expect strings where two words with a hyphen in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the hyphenated words, without quotes._</span></span>

<span data-ttu-id="d2868-136">第四个和最后一种模式，如下所示 `@{before='"hello world","333"'; after='333: hello world'}` ： _需要字符串，其中两个单词之间有一个空格，中间用双引号括起来_ 
 _，然后是逗号，然后是用引号引起来的数字。_ 
_逗号和第三个双引号之间没有空格。_ 
_在输出上：首先放置数字，不使用引号，然后输入单个空格，_ 
然后 _是带有空格的单词，无引号。_</span><span class="sxs-lookup"><span data-stu-id="d2868-136">The fourth, and final, pattern, `@{before='"hello world","333"'; after='333: hello world'}`, reads as follows: _expect strings where two words with a space in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the words with the space in between, without quotes._</span></span>

<span data-ttu-id="d2868-137">第一个命令使用 Get-Process cmdlet 获取所有进程。</span><span class="sxs-lookup"><span data-stu-id="d2868-137">The first command gets all processes by using the Get-Process cmdlet.</span></span>
<span data-ttu-id="d2868-138">命令将它们传递给 Select-Object cmdlet，后者将选择进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="d2868-138">The command passes them to the Select-Object cmdlet, which selects the process name and process ID.</span></span> <span data-ttu-id="d2868-139">在管道的末尾，命令使用 ConvertTo-Csv cmdlet 将输出转换为逗号分隔值，而不包含类型信息。</span><span class="sxs-lookup"><span data-stu-id="d2868-139">At the end of the pipeline, the command converts the output to comma separated values, without type information, by using the ConvertTo-Csv cmdlet.</span></span>
<span data-ttu-id="d2868-140">该命令将结果存储在 **$Processes** 变量中。</span><span class="sxs-lookup"><span data-stu-id="d2868-140">The command stores the results in the **$Processes** variable.</span></span>
<span data-ttu-id="d2868-141">**$Processes** 现在包含进程名称和 PID。</span><span class="sxs-lookup"><span data-stu-id="d2868-141">**$Processes** now contains process names and PID.</span></span>

<span data-ttu-id="d2868-142">第二个命令指定更改输入项顺序的示例变量。</span><span class="sxs-lookup"><span data-stu-id="d2868-142">The second command specifies an example variable that changes the order of the input items.</span></span>
<span data-ttu-id="d2868-143">该命令将 **$Processes** 中的每个字符串。</span><span class="sxs-lookup"><span data-stu-id="d2868-143">The command coverts each string in **$Processes** .</span></span>

><span data-ttu-id="d2868-144">**注意** 第四种模式隐式指出了两个或多个由空格分隔的单词。</span><span class="sxs-lookup"><span data-stu-id="d2868-144">**Note** The fourth pattern implicitly says that two or more words separated by spaces are matched.</span></span>
>
><span data-ttu-id="d2868-145">如果没有第四种模式，则仅匹配括在双引号中的字符串的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="d2868-145">Without the fourth pattern, only the first word of the string enclosed in double quotes is matched.</span></span>

## <span data-ttu-id="d2868-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2868-146">PARAMETERS</span></span>

### <span data-ttu-id="d2868-147">-示例</span><span class="sxs-lookup"><span data-stu-id="d2868-147">-Example</span></span>

<span data-ttu-id="d2868-148">指定目标格式的示例列表。</span><span class="sxs-lookup"><span data-stu-id="d2868-148">Specifies a list of examples of the target format.</span></span>
<span data-ttu-id="d2868-149">指定由相等 (=) 符号分隔的对，左侧有源模式，右侧有目标模式，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d2868-149">Specify pairs separated by the equal (=) sign, with the source pattern on the left and the target pattern on the right, as in the following examples:</span></span>

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

><span data-ttu-id="d2868-150">**注意** 第二个示例使用模式列表</span><span class="sxs-lookup"><span data-stu-id="d2868-150">**Note** The second example uses a list of patterns</span></span>

<span data-ttu-id="d2868-151">另外 **，还可** 指定包含 **前后** 属性的哈希表的列表。</span><span class="sxs-lookup"><span data-stu-id="d2868-151">Alternatively, specify a list of hash tables that contain **Before** and **After** properties.</span></span>

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

><span data-ttu-id="d2868-152">**警告** 避免在等号前后使用空格，因为它们被视为模式的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2868-152">**Caution** Avoid using spaces around the equal sign, as they are treated as part of the pattern.</span></span>

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2868-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d2868-153">-InputObject</span></span>

<span data-ttu-id="d2868-154">指定要设置格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2868-154">Specifies a string to format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d2868-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d2868-155">CommonParameters</span></span>

<span data-ttu-id="d2868-156">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d2868-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d2868-157">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d2868-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d2868-158">输入</span><span class="sxs-lookup"><span data-stu-id="d2868-158">INPUTS</span></span>

### <span data-ttu-id="d2868-159">字符串</span><span class="sxs-lookup"><span data-stu-id="d2868-159">String</span></span>

<span data-ttu-id="d2868-160">可以通过管道将字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2868-160">You can pipe strings to this cmdlet.</span></span>

## <span data-ttu-id="d2868-161">输出</span><span class="sxs-lookup"><span data-stu-id="d2868-161">OUTPUTS</span></span>

### <span data-ttu-id="d2868-162">字符串</span><span class="sxs-lookup"><span data-stu-id="d2868-162">String</span></span>

<span data-ttu-id="d2868-163">此 cmdlet 将返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="d2868-163">This cmdlet returns a string.</span></span>

## <span data-ttu-id="d2868-164">注释</span><span class="sxs-lookup"><span data-stu-id="d2868-164">NOTES</span></span>

## <span data-ttu-id="d2868-165">相关链接</span><span class="sxs-lookup"><span data-stu-id="d2868-165">RELATED LINKS</span></span>

[<span data-ttu-id="d2868-166">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="d2868-166">ConvertFrom-String</span></span>](ConvertFrom-String.md)

[<span data-ttu-id="d2868-167">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="d2868-167">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="d2868-168">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d2868-168">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="d2868-169">Out-String</span><span class="sxs-lookup"><span data-stu-id="d2868-169">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="d2868-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="d2868-170">Select-Object</span></span>](Select-Object.md)
