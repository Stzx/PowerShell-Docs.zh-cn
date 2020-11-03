---
description: 说明如何使用 Split 运算符将一个或多个字符串拆分为子字符串。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: ed57cec30577fbd02f7aa317460bf1a73b006685
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199565"
---
# <a name="about-split"></a><span data-ttu-id="051ae-104">关于 Split</span><span class="sxs-lookup"><span data-stu-id="051ae-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="051ae-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="051ae-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="051ae-106">说明如何使用 Split 运算符将一个或多个字符串拆分为子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="051ae-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="051ae-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="051ae-108">Split 运算符将一个或多个字符串拆分为子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="051ae-109">您可以更改 Split 操作的以下元素：</span><span class="sxs-lookup"><span data-stu-id="051ae-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="051ae-110">后面.</span><span class="sxs-lookup"><span data-stu-id="051ae-110">Delimiter.</span></span> <span data-ttu-id="051ae-111">默认值为空格，但您可以指定字符、字符串、模式或指定分隔符的脚本块。</span><span class="sxs-lookup"><span data-stu-id="051ae-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="051ae-112">PowerShell 中的 Split 运算符使用分隔符中的正则表达式，而不是简单字符。</span><span class="sxs-lookup"><span data-stu-id="051ae-112">The Split operator in PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="051ae-113">子字符串的最大数目。</span><span class="sxs-lookup"><span data-stu-id="051ae-113">Maximum number of substrings.</span></span> <span data-ttu-id="051ae-114">默认值为返回所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-114">The default is to return all substrings.</span></span> <span data-ttu-id="051ae-115">如果指定的数字小于子字符串的数目，则剩余的子字符串将连接到最后一个子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="051ae-116">用于指定匹配分隔符的条件的选项，如 SimpleMatch 和多行。</span><span class="sxs-lookup"><span data-stu-id="051ae-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="051ae-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="051ae-117">SYNTAX</span></span>

<span data-ttu-id="051ae-118">下图显示了-split 运算符的语法。</span><span class="sxs-lookup"><span data-stu-id="051ae-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="051ae-119">参数名称不会出现在命令中。</span><span class="sxs-lookup"><span data-stu-id="051ae-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="051ae-120">仅包括参数值。</span><span class="sxs-lookup"><span data-stu-id="051ae-120">Include only the parameter values.</span></span> <span data-ttu-id="051ae-121">值必须以语法关系图中指定的顺序出现。</span><span class="sxs-lookup"><span data-stu-id="051ae-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="051ae-122">可以 `-iSplit` `-cSplit` `-split` 在任何二进制 split 语句中替换或， (包含分隔符或脚本块的 Split 语句) 。</span><span class="sxs-lookup"><span data-stu-id="051ae-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="051ae-123">`-iSplit`和 `-split` 运算符不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="051ae-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="051ae-124">`-cSplit`运算符区分大小写，这意味着在应用分隔符规则时将考虑大小写。</span><span class="sxs-lookup"><span data-stu-id="051ae-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="051ae-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="051ae-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="051ae-126">\<String\> 或 \<String[]\></span><span class="sxs-lookup"><span data-stu-id="051ae-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="051ae-127">指定一个或多个要拆分的字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="051ae-128">如果提交多个字符串，则所有字符串都将使用相同的分隔符规则进行拆分。</span><span class="sxs-lookup"><span data-stu-id="051ae-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="051ae-129">示例：</span><span class="sxs-lookup"><span data-stu-id="051ae-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="051ae-130">标识子字符串末尾的字符。</span><span class="sxs-lookup"><span data-stu-id="051ae-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="051ae-131">默认分隔符为空白，包括空格和不可打印的字符，如换行符 (\` n) 和制表符 (\` t) 。</span><span class="sxs-lookup"><span data-stu-id="051ae-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="051ae-132">拆分字符串后，将从所有子字符串中省略分隔符。</span><span class="sxs-lookup"><span data-stu-id="051ae-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="051ae-133">示例：</span><span class="sxs-lookup"><span data-stu-id="051ae-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="051ae-134">默认情况下，结果中省略了分隔符。</span><span class="sxs-lookup"><span data-stu-id="051ae-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="051ae-135">若要保留全部或部分分隔符，请将要保留的部分括在括号中。</span><span class="sxs-lookup"><span data-stu-id="051ae-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="051ae-136">如果 \<Max-substrings\> 添加了参数，则当命令拆分集合时，此参数将优先。</span><span class="sxs-lookup"><span data-stu-id="051ae-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="051ae-137">如果选择将分隔符作为输出的一部分包含，则该命令会将分隔符作为输出的一部分返回;但是，如果将字符串拆分为作为输出的一部分返回，则不计为拆分。</span><span class="sxs-lookup"><span data-stu-id="051ae-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="051ae-138">示例:</span><span class="sxs-lookup"><span data-stu-id="051ae-138">Examples:</span></span>

```
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

<span data-ttu-id="051ae-139">在下面的示例中， \<Max-substrings\> 设置为3。</span><span class="sxs-lookup"><span data-stu-id="051ae-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="051ae-140">这会生成三个字符串值的拆分，但生成的输出中总共有5个字符串;分隔符包含在拆分后，直到达到三个子字符串的最大值。</span><span class="sxs-lookup"><span data-stu-id="051ae-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="051ae-141">最后一个子字符串中的其他分隔符将成为子字符串的一部分。</span><span class="sxs-lookup"><span data-stu-id="051ae-141">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```Output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

<span data-ttu-id="051ae-142">指定一个字符串被拆分的最大次数。</span><span class="sxs-lookup"><span data-stu-id="051ae-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="051ae-143">默认值为所有子字符串除以分隔符。</span><span class="sxs-lookup"><span data-stu-id="051ae-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="051ae-144">如果有多个子字符串，则它们将连接到最后一个子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="051ae-145">如果子字符串较少，则返回所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="051ae-146">值0返回所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-146">A value of 0 returns all the substrings.</span></span> <span data-ttu-id="051ae-147">负值返回从输入字符串末尾开始请求的子字符串量。</span><span class="sxs-lookup"><span data-stu-id="051ae-147">Negative values return the amount of substrings requested starting from the end of the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="051ae-148">PowerShell 7 中添加了对负值的支持。</span><span class="sxs-lookup"><span data-stu-id="051ae-148">Support for negative values was added in PowerShell 7.</span></span>

<span data-ttu-id="051ae-149">**Max-子字符串** 未指定返回的最大对象数。</span><span class="sxs-lookup"><span data-stu-id="051ae-149">**Max-substrings** does not specify the maximum number of objects that are returned.</span></span> <span data-ttu-id="051ae-150">其值等于拆分字符串的最大次数。</span><span class="sxs-lookup"><span data-stu-id="051ae-150">Its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="051ae-151">如果将多个字符串 (一个字符串数组提交) 到 `-split` 运算符，则 **最大子** 字符串限制将分别应用于每个字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-151">If you submit more than one string (an array of strings) to the `-split` operator, the **Max-substrings** limit is applied to each string separately.</span></span>

<span data-ttu-id="051ae-152">示例：</span><span class="sxs-lookup"><span data-stu-id="051ae-152">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```Output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", -5
```

```Output
Mercury,Venus,Earth,Mars
Jupiter
Saturn
Uranus
Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="051ae-153">一个表达式，指定用于应用分隔符的规则。</span><span class="sxs-lookup"><span data-stu-id="051ae-153">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="051ae-154">表达式的计算结果必须为 $true 或 $false。</span><span class="sxs-lookup"><span data-stu-id="051ae-154">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="051ae-155">将脚本块括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="051ae-155">Enclose the script block in braces.</span></span>

<span data-ttu-id="051ae-156">示例：</span><span class="sxs-lookup"><span data-stu-id="051ae-156">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```Output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="051ae-157">将选项名称用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="051ae-157">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="051ae-158">仅当在 \<Max-substrings\> 语句中使用参数时，这些选项才有效。</span><span class="sxs-lookup"><span data-stu-id="051ae-158">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="051ae-159">Options 参数的语法为：</span><span class="sxs-lookup"><span data-stu-id="051ae-159">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="051ae-160">SimpleMatch 选项包括：</span><span class="sxs-lookup"><span data-stu-id="051ae-160">The SimpleMatch options are:</span></span>

- <span data-ttu-id="051ae-161">**SimpleMatch** ：计算分隔符时使用简单的字符串比较。</span><span class="sxs-lookup"><span data-stu-id="051ae-161">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="051ae-162">不能与 RegexMatch 一起使用。</span><span class="sxs-lookup"><span data-stu-id="051ae-162">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="051ae-163">**Regexoptions.ignorecase** ：强制不区分大小写的匹配，即使指定了-cSplit 运算符。</span><span class="sxs-lookup"><span data-stu-id="051ae-163">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="051ae-164">RegexMatch 选项包括：</span><span class="sxs-lookup"><span data-stu-id="051ae-164">The RegexMatch options are:</span></span>

- <span data-ttu-id="051ae-165">**RegexMatch** ：使用正则表达式匹配计算分隔符。</span><span class="sxs-lookup"><span data-stu-id="051ae-165">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="051ae-166">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="051ae-166">This is the default behavior.</span></span> <span data-ttu-id="051ae-167">不能与 SimpleMatch 一起使用。</span><span class="sxs-lookup"><span data-stu-id="051ae-167">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="051ae-168">**Regexoptions.ignorecase** ：强制不区分大小写的匹配，即使指定了-cSplit 运算符。</span><span class="sxs-lookup"><span data-stu-id="051ae-168">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="051ae-169">**Regexoptions.cultureinvariant** ：用来评估分隔符时忽略语言中的区域性差异。</span><span class="sxs-lookup"><span data-stu-id="051ae-169">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="051ae-170">仅对 RegexMatch 有效。</span><span class="sxs-lookup"><span data-stu-id="051ae-170">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="051ae-171">**IgnorePatternWhitespace** ：忽略用数字符号标记的非转义空格和注释 ( # ) 。</span><span class="sxs-lookup"><span data-stu-id="051ae-171">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="051ae-172">仅对 RegexMatch 有效。</span><span class="sxs-lookup"><span data-stu-id="051ae-172">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="051ae-173">**多** 行模式强制 `^` 并 `$` 匹配每行的开头，而不是输入字符串的开头和结尾。</span><span class="sxs-lookup"><span data-stu-id="051ae-173">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="051ae-174">**Regexoptions.singleline** ： regexoptions.singleline 模式将输入字符串视为 *regexoptions.singleline* 。</span><span class="sxs-lookup"><span data-stu-id="051ae-174">**Singleline** : Singleline mode treats the input string as a *SingleLine* .</span></span>
  <span data-ttu-id="051ae-175">它强制 `.` 字符匹配每个字符 (包括换行符) ，而不是与除换行符之外的每个字符匹配 `\n` 。</span><span class="sxs-lookup"><span data-stu-id="051ae-175">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="051ae-176">**Regexoptions.explicitcapture** ：忽略不命名的匹配组，以便仅在结果列表中返回显式捕获组。</span><span class="sxs-lookup"><span data-stu-id="051ae-176">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="051ae-177">仅对 RegexMatch 有效。</span><span class="sxs-lookup"><span data-stu-id="051ae-177">Valid only with RegexMatch.</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="051ae-178">一元和二元拆分运算符</span><span class="sxs-lookup"><span data-stu-id="051ae-178">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="051ae-179">一元 split 运算符 (`-split <string>`) 的优先级高于逗号。</span><span class="sxs-lookup"><span data-stu-id="051ae-179">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="051ae-180">因此，如果您将逗号分隔的字符串列表提交给一元 split 运算符，则在第一个逗号) 之前仅 (第一个字符串被拆分。</span><span class="sxs-lookup"><span data-stu-id="051ae-180">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="051ae-181">使用下列模式之一拆分多个字符串：</span><span class="sxs-lookup"><span data-stu-id="051ae-181">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="051ae-182">使用二进制拆分运算符 (\<string[]\> 拆分 \<delimiter\>) </span><span class="sxs-lookup"><span data-stu-id="051ae-182">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="051ae-183">将所有字符串括在括号中</span><span class="sxs-lookup"><span data-stu-id="051ae-183">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="051ae-184">将字符串存储在变量中，然后将变量提交给 split 运算符</span><span class="sxs-lookup"><span data-stu-id="051ae-184">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="051ae-185">请考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="051ae-185">Consider the following example:</span></span>

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a><span data-ttu-id="051ae-186">示例</span><span class="sxs-lookup"><span data-stu-id="051ae-186">EXAMPLES</span></span>

<span data-ttu-id="051ae-187">下面的语句在空格处拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-187">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```Output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="051ae-188">以下语句以任意逗号拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-188">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```Output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="051ae-189">下面的语句以 "er" 模式拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-189">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="051ae-190">以下语句执行区分大小写的字母 "N"。</span><span class="sxs-lookup"><span data-stu-id="051ae-190">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="051ae-191">下面的语句在 "e" 和 "t" 处拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-191">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```Output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

<span data-ttu-id="051ae-192">下面的语句在 "e" 和 "r" 处拆分字符串，但将生成的子字符串限制为六个子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-192">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```Output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="051ae-193">下面的语句将字符串拆分为三个子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-193">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="051ae-194">下面的语句将字符串拆分为从字符串末尾开始的三个子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-194">The following statement splits a string into three substrings starting from the end of the string.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

<span data-ttu-id="051ae-195">下面的语句将两个字符串拆分为三个子字符串。</span><span class="sxs-lookup"><span data-stu-id="051ae-195">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="051ae-196"> (此限制分别应用于每个字符串。 ) </span><span class="sxs-lookup"><span data-stu-id="051ae-196">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```Output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="051ae-197">下面的语句在第一个数字处拆分了此处字符串中的每一行。</span><span class="sxs-lookup"><span data-stu-id="051ae-197">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="051ae-198">它使用多行选项来识别每个行和字符串的开头。</span><span class="sxs-lookup"><span data-stu-id="051ae-198">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="051ae-199">0表示 Max 子字符串参数的 "返回所有" 值。</span><span class="sxs-lookup"><span data-stu-id="051ae-199">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="051ae-200">仅当指定了 Max 子字符串值时，才可以使用诸如多行的选项。</span><span class="sxs-lookup"><span data-stu-id="051ae-200">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```Output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="051ae-201">以下语句使用反斜杠字符来转义 ( ) 分隔符。</span><span class="sxs-lookup"><span data-stu-id="051ae-201">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="051ae-202">默认值为 RegexMatch，用引号引起来的点 ( "。) 被解释为匹配除换行符外的任何字符。</span><span class="sxs-lookup"><span data-stu-id="051ae-202">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="051ae-203">因此，Split 语句为除换行符之外的每个字符返回一个空行。</span><span class="sxs-lookup"><span data-stu-id="051ae-203">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

<span data-ttu-id="051ae-204">下面的语句使用 SimpleMatch 选项来指示-split 运算符解释点 (。 ) 分隔符。</span><span class="sxs-lookup"><span data-stu-id="051ae-204">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="051ae-205">0表示 Max 子字符串参数的 "返回所有" 值。</span><span class="sxs-lookup"><span data-stu-id="051ae-205">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="051ae-206">仅当指定了 Max 子字符串值时，才能使用 SimpleMatch 等选项。</span><span class="sxs-lookup"><span data-stu-id="051ae-206">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

<span data-ttu-id="051ae-207">下面的语句根据变量的值，将字符串拆分为两个分隔符之一。</span><span class="sxs-lookup"><span data-stu-id="051ae-207">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="051ae-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="051ae-208">SEE ALSO</span></span>

[<span data-ttu-id="051ae-209">Split-Path</span><span class="sxs-lookup"><span data-stu-id="051ae-209">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="051ae-210">about_Operators</span><span class="sxs-lookup"><span data-stu-id="051ae-210">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="051ae-211">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="051ae-211">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="051ae-212">about_Join</span><span class="sxs-lookup"><span data-stu-id="051ae-212">about_Join</span></span>](about_Join.md)
