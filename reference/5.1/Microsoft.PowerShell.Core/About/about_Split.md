---
description: 说明如何使用 Split 运算符将一个或多个字符串拆分为子字符串。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/20/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: e93f68265bf560b03ac503ca914a11dde1f6b061
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200055"
---
# <a name="about-split"></a><span data-ttu-id="ee2c7-104">关于 Split</span><span class="sxs-lookup"><span data-stu-id="ee2c7-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="ee2c7-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ee2c7-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ee2c7-106">说明如何使用 Split 运算符将一个或多个字符串拆分为子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="ee2c7-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="ee2c7-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ee2c7-108">Split 运算符将一个或多个字符串拆分为子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="ee2c7-109">您可以更改 Split 操作的以下元素：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="ee2c7-110">后面.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-110">Delimiter.</span></span> <span data-ttu-id="ee2c7-111">默认值为空格，但您可以指定字符、字符串、模式或指定分隔符的脚本块。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="ee2c7-112">Windows PowerShell 中的 Split 运算符使用分隔符中的正则表达式，而不是简单字符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-112">The Split operator in Windows PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="ee2c7-113">子字符串的最大数目。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-113">Maximum number of substrings.</span></span> <span data-ttu-id="ee2c7-114">默认值为返回所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-114">The default is to return all substrings.</span></span> <span data-ttu-id="ee2c7-115">如果指定的数字小于子字符串的数目，则剩余的子字符串将连接到最后一个子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="ee2c7-116">用于指定匹配分隔符的条件的选项，如 SimpleMatch 和多行。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee2c7-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ee2c7-117">SYNTAX</span></span>

<span data-ttu-id="ee2c7-118">下图显示了-split 运算符的语法。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="ee2c7-119">参数名称不会出现在命令中。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="ee2c7-120">仅包括参数值。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-120">Include only the parameter values.</span></span> <span data-ttu-id="ee2c7-121">值必须以语法关系图中指定的顺序出现。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="ee2c7-122">可以 `-iSplit` `-cSplit` `-split` 在任何二进制 split 语句中替换或， (包含分隔符或脚本块的 Split 语句) 。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="ee2c7-123">`-iSplit`和 `-split` 运算符不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="ee2c7-124">`-cSplit`运算符区分大小写，这意味着在应用分隔符规则时将考虑大小写。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="ee2c7-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ee2c7-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="ee2c7-126">\<String\> 或 \<String[]\></span><span class="sxs-lookup"><span data-stu-id="ee2c7-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="ee2c7-127">指定一个或多个要拆分的字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="ee2c7-128">如果提交多个字符串，则所有字符串都将使用相同的分隔符规则进行拆分。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="ee2c7-129">示例：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="ee2c7-130">标识子字符串末尾的字符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="ee2c7-131">默认分隔符为空白，包括空格和不可打印的字符，如换行符 (\` n) 和制表符 (\` t) 。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="ee2c7-132">拆分字符串后，将从所有子字符串中省略分隔符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="ee2c7-133">示例：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="ee2c7-134">默认情况下，结果中省略了分隔符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="ee2c7-135">若要保留全部或部分分隔符，请将要保留的部分括在括号中。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="ee2c7-136">如果 \<Max-substrings\> 添加了参数，则当命令拆分集合时，此参数将优先。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="ee2c7-137">如果选择将分隔符作为输出的一部分包含，则该命令会将分隔符作为输出的一部分返回;但是，如果将字符串拆分为作为输出的一部分返回，则不计为拆分。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="ee2c7-138">示例:</span><span class="sxs-lookup"><span data-stu-id="ee2c7-138">Examples:</span></span>

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

<span data-ttu-id="ee2c7-139">在下面的示例中， \<Max-substrings\> 设置为3。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="ee2c7-140">这会生成三个字符串值的拆分，但生成的输出中总共有5个字符串;分隔符包含在拆分后，直到达到三个子字符串的最大值。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="ee2c7-141">最后一个子字符串中的其他分隔符将成为子字符串的一部分。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-141">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

<span data-ttu-id="ee2c7-142">指定一个字符串被拆分的最大次数。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="ee2c7-143">默认值为所有子字符串除以分隔符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="ee2c7-144">如果有多个子字符串，则它们将连接到最后一个子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="ee2c7-145">如果子字符串较少，则返回所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="ee2c7-146">值0和负值返回所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-146">A value of 0 and negative values return all the substrings.</span></span>

<span data-ttu-id="ee2c7-147">Max-子字符串未指定返回的最大对象数;其值等于拆分字符串的最大次数。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-147">Max-substrings does not specify the maximum number of objects that are returned; its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="ee2c7-148">如果将多个字符串 (一个字符串数组提交) Split 运算符，则最大子字符串限制将分别应用于每个字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-148">If you submit more than one string (an array of strings) to the Split operator , the Max-substrings limit is applied to each string separately.</span></span>

<span data-ttu-id="ee2c7-149">示例：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-149">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="ee2c7-150">一个表达式，指定用于应用分隔符的规则。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-150">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="ee2c7-151">表达式的计算结果必须为 $true 或 $false。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-151">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="ee2c7-152">将脚本块括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-152">Enclose the script block in braces.</span></span>

<span data-ttu-id="ee2c7-153">示例：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-153">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="ee2c7-154">将选项名称用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-154">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="ee2c7-155">仅当在 \<Max-substrings\> 语句中使用参数时，这些选项才有效。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-155">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="ee2c7-156">Options 参数的语法为：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-156">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="ee2c7-157">SimpleMatch 选项包括：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-157">The SimpleMatch options are:</span></span>

- <span data-ttu-id="ee2c7-158">**SimpleMatch** ：计算分隔符时使用简单的字符串比较。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-158">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="ee2c7-159">不能与 RegexMatch 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-159">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="ee2c7-160">**Regexoptions.ignorecase** ：强制不区分大小写的匹配，即使指定了-cSplit 运算符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-160">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="ee2c7-161">RegexMatch 选项包括：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-161">The RegexMatch options are:</span></span>

- <span data-ttu-id="ee2c7-162">**RegexMatch** ：使用正则表达式匹配计算分隔符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-162">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="ee2c7-163">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-163">This is the default behavior.</span></span> <span data-ttu-id="ee2c7-164">不能与 SimpleMatch 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-164">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="ee2c7-165">**Regexoptions.ignorecase** ：强制不区分大小写的匹配，即使指定了-cSplit 运算符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-165">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="ee2c7-166">**Regexoptions.cultureinvariant** ：用来评估分隔符时忽略语言中的区域性差异。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-166">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="ee2c7-167">仅对 RegexMatch 有效。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-167">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="ee2c7-168">**IgnorePatternWhitespace** ：忽略用数字符号标记的非转义空格和注释 ( # ) 。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-168">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="ee2c7-169">仅对 RegexMatch 有效。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="ee2c7-170">**多** 行模式强制 `^` 并 `$` 匹配每行的开头，而不是输入字符串的开头和结尾。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-170">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="ee2c7-171">**Regexoptions.singleline** ： regexoptions.singleline 模式将输入字符串视为 *regexoptions.singleline* 。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-171">**Singleline** : Singleline mode treats the input string as a *SingleLine* .</span></span>
  <span data-ttu-id="ee2c7-172">它强制 `.` 字符匹配每个字符 (包括换行符) ，而不是与除换行符之外的每个字符匹配 `\n` 。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-172">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="ee2c7-173">**Regexoptions.explicitcapture** ：忽略不命名的匹配组，以便仅在结果列表中返回显式捕获组。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-173">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="ee2c7-174">仅对 RegexMatch 有效。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-174">Valid only with RegexMatch.</span></span>

> [!NOTE]
> <span data-ttu-id="ee2c7-175">Regexoptions.singleline 是默认行为。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-175">SingleLine is the default behavior.</span></span> <span data-ttu-id="ee2c7-176">不能将 regexoptions.singleline 和多行与 options 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-176">Singleline and Multiline cannot be used together with the options parameter.</span></span> <span data-ttu-id="ee2c7-177">此操作已在 PowerShell 6.0 中解决。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-177">This was resolved in PowerShell 6.0.</span></span>
> <span data-ttu-id="ee2c7-178">解决方法是在正则表达式中使用 *模式修饰符* 。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-178">The work around is by using *Mode-Modifiers* in your regular expression.</span></span>
> <span data-ttu-id="ee2c7-179">可以在[正则表达式选项](/dotnet/standard/base-types/regular-expression-options)中阅读有关模式修饰符的详细信息</span><span class="sxs-lookup"><span data-stu-id="ee2c7-179">You can read more about mode modifiers in [Regular Expression Options](/dotnet/standard/base-types/regular-expression-options)</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="ee2c7-180">一元和二元拆分运算符</span><span class="sxs-lookup"><span data-stu-id="ee2c7-180">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="ee2c7-181">一元 split 运算符 (`-split <string>`) 的优先级高于逗号。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-181">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="ee2c7-182">因此，如果您将逗号分隔的字符串列表提交给一元 split 运算符，则在第一个逗号) 之前仅 (第一个字符串被拆分。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-182">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="ee2c7-183">使用下列模式之一拆分多个字符串：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-183">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="ee2c7-184">使用二进制拆分运算符 (\<string[]\> 拆分 \<delimiter\>) </span><span class="sxs-lookup"><span data-stu-id="ee2c7-184">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="ee2c7-185">将所有字符串括在括号中</span><span class="sxs-lookup"><span data-stu-id="ee2c7-185">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="ee2c7-186">将字符串存储在变量中，然后将变量提交给 split 运算符</span><span class="sxs-lookup"><span data-stu-id="ee2c7-186">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="ee2c7-187">请考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="ee2c7-187">Consider the following example:</span></span>

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

## <a name="examples"></a><span data-ttu-id="ee2c7-188">示例</span><span class="sxs-lookup"><span data-stu-id="ee2c7-188">EXAMPLES</span></span>

<span data-ttu-id="ee2c7-189">下面的语句在空格处拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-189">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="ee2c7-190">以下语句以任意逗号拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-190">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="ee2c7-191">下面的语句以 "er" 模式拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-191">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="ee2c7-192">以下语句执行区分大小写的字母 "N"。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-192">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="ee2c7-193">下面的语句在 "e" 和 "t" 处拆分字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-193">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```output
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

<span data-ttu-id="ee2c7-194">下面的语句在 "e" 和 "r" 处拆分字符串，但将生成的子字符串限制为六个子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-194">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="ee2c7-195">下面的语句将字符串拆分为三个子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-195">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="ee2c7-196">下面的语句将两个字符串拆分为三个子字符串。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-196">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="ee2c7-197"> (此限制分别应用于每个字符串。 ) </span><span class="sxs-lookup"><span data-stu-id="ee2c7-197">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="ee2c7-198">下面的语句在第一个数字处拆分了此处字符串中的每一行。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-198">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="ee2c7-199">它使用多行选项来识别每个行和字符串的开头。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-199">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="ee2c7-200">0表示 Max 子字符串参数的 "返回所有" 值。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-200">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="ee2c7-201">仅当指定了 Max 子字符串值时，才可以使用诸如多行的选项。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-201">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="ee2c7-202">以下语句使用反斜杠字符来转义 ( ) 分隔符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-202">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="ee2c7-203">默认值为 RegexMatch，用引号引起来的点 ( "。) 被解释为匹配除换行符外的任何字符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-203">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="ee2c7-204">因此，Split 语句为除换行符之外的每个字符返回一个空行。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-204">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```output
This
is
a
test
```

<span data-ttu-id="ee2c7-205">下面的语句使用 SimpleMatch 选项来指示-split 运算符解释点 (。 ) 分隔符。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-205">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="ee2c7-206">0表示 Max 子字符串参数的 "返回所有" 值。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-206">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="ee2c7-207">仅当指定了 Max 子字符串值时，才能使用 SimpleMatch 等选项。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-207">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```output
This
is
a
test
```

<span data-ttu-id="ee2c7-208">下面的语句根据变量的值，将字符串拆分为两个分隔符之一。</span><span class="sxs-lookup"><span data-stu-id="ee2c7-208">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="ee2c7-209">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee2c7-209">SEE ALSO</span></span>

[<span data-ttu-id="ee2c7-210">Split-Path</span><span class="sxs-lookup"><span data-stu-id="ee2c7-210">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="ee2c7-211">about_Operators</span><span class="sxs-lookup"><span data-stu-id="ee2c7-211">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="ee2c7-212">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="ee2c7-212">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="ee2c7-213">about_Join</span><span class="sxs-lookup"><span data-stu-id="ee2c7-213">about_Join</span></span>](about_Join.md)
