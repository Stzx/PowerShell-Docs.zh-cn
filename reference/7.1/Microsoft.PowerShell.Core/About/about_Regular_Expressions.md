---
description: 描述 PowerShell 中的正则表达式。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: fe3f668265101f8c0aa07967f235a1092d76e299
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200421"
---
# <a name="about-regular-expressions"></a><span data-ttu-id="e45c0-104">关于正则表达式</span><span class="sxs-lookup"><span data-stu-id="e45c0-104">About Regular Expressions</span></span>

## <a name="short-description"></a><span data-ttu-id="e45c0-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="e45c0-105">Short description</span></span>
<span data-ttu-id="e45c0-106">描述 PowerShell 中的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e45c0-106">Describes regular expressions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e45c0-107">长说明</span><span class="sxs-lookup"><span data-stu-id="e45c0-107">Long description</span></span>

> [!NOTE]
> <span data-ttu-id="e45c0-108">本文将介绍在 PowerShell 中使用正则表达式的语法和方法，并非所有语法都进行了讨论。</span><span class="sxs-lookup"><span data-stu-id="e45c0-108">This article will show you the syntax and methods for using regular expressions in PowerShell, not all syntax is discussed.</span></span> <span data-ttu-id="e45c0-109">有关更完整的参考信息，请参阅 [正则表达式语言-快速参考](/dotnet/standard/base-types/regular-expression-language-quick-reference)。</span><span class="sxs-lookup"><span data-stu-id="e45c0-109">For a more complete reference, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

<span data-ttu-id="e45c0-110">正则表达式是用于匹配文本的模式。</span><span class="sxs-lookup"><span data-stu-id="e45c0-110">A regular expression is a pattern used to match text.</span></span> <span data-ttu-id="e45c0-111">它可以由文本字符、运算符和其他构造组成。</span><span class="sxs-lookup"><span data-stu-id="e45c0-111">It can be made up of literal characters, operators, and other constructs.</span></span>

<span data-ttu-id="e45c0-112">本文演示了 PowerShell 中的正则表达式语法。</span><span class="sxs-lookup"><span data-stu-id="e45c0-112">This article demonstrates regular expression syntax in PowerShell.</span></span> <span data-ttu-id="e45c0-113">PowerShell 具有几个使用正则表达式的运算符和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e45c0-113">PowerShell has several operators and cmdlets that use regular expressions.</span></span> <span data-ttu-id="e45c0-114">可以在下面的链接中了解有关其语法和用法的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e45c0-114">You can read more about their syntax and usage at the links below.</span></span>

- [<span data-ttu-id="e45c0-115">Select-String</span><span class="sxs-lookup"><span data-stu-id="e45c0-115">Select-String</span></span>](xref:Microsoft.PowerShell.Utility.Select-String)
- [<span data-ttu-id="e45c0-116">-match 和-replace 运算符</span><span class="sxs-lookup"><span data-stu-id="e45c0-116">-match and -replace operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="e45c0-117">-split</span><span class="sxs-lookup"><span data-stu-id="e45c0-117">-split</span></span>](about_Split.md)
- [<span data-ttu-id="e45c0-118">switch 语句替换为-regex 选项</span><span class="sxs-lookup"><span data-stu-id="e45c0-118">switch statement with -regex option</span></span>](about_Switch.md)

<span data-ttu-id="e45c0-119">默认情况下，PowerShell 正则表达式不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e45c0-119">PowerShell regular expressions are case-insensitive by default.</span></span> <span data-ttu-id="e45c0-120">上面所示的每个方法都有不同的方法来强制区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e45c0-120">Each method shown above has a different way to force case sensitivity.</span></span>

|       <span data-ttu-id="e45c0-121">方法</span><span class="sxs-lookup"><span data-stu-id="e45c0-121">Method</span></span>       |                      <span data-ttu-id="e45c0-122">区分大小写</span><span class="sxs-lookup"><span data-stu-id="e45c0-122">Case Sensitivity</span></span>                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | <span data-ttu-id="e45c0-123">使用 `-CaseSensitive` 开关</span><span class="sxs-lookup"><span data-stu-id="e45c0-123">use `-CaseSensitive` switch</span></span>                                |
| <span data-ttu-id="e45c0-124">`switch` 语句</span><span class="sxs-lookup"><span data-stu-id="e45c0-124">`switch` statement</span></span> | <span data-ttu-id="e45c0-125">使用 `-casesensitive` 选项</span><span class="sxs-lookup"><span data-stu-id="e45c0-125">use the `-casesensitive` option</span></span>                            |
| <span data-ttu-id="e45c0-126">运算符</span><span class="sxs-lookup"><span data-stu-id="e45c0-126">operators</span></span>          | <span data-ttu-id="e45c0-127">前缀为 **"c"** (`-cmatch` 、 `-csplit` 或 `-creplace`) </span><span class="sxs-lookup"><span data-stu-id="e45c0-127">prefix with **'c'** (`-cmatch`, `-csplit`, or `-creplace`)</span></span> |

### <a name="character-literals"></a><span data-ttu-id="e45c0-128">字符文本</span><span class="sxs-lookup"><span data-stu-id="e45c0-128">Character literals</span></span>

<span data-ttu-id="e45c0-129">正则表达式可以是文本字符或字符串。</span><span class="sxs-lookup"><span data-stu-id="e45c0-129">A regular expression can be a literal character or a string.</span></span> <span data-ttu-id="e45c0-130">表达式使引擎与指定的文本完全匹配。</span><span class="sxs-lookup"><span data-stu-id="e45c0-130">The expression causes the engine to match the text specified exactly.</span></span>

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a><span data-ttu-id="e45c0-131">字符类</span><span class="sxs-lookup"><span data-stu-id="e45c0-131">Character classes</span></span>

<span data-ttu-id="e45c0-132">虽然在您知道确切的模式的情况下，字符文本有效，但字符类允许您不太具体。</span><span class="sxs-lookup"><span data-stu-id="e45c0-132">While character literals work if you know the exact pattern, character classes allow you to be less specific.</span></span>

#### <a name="character-groups"></a><span data-ttu-id="e45c0-133">字符组</span><span class="sxs-lookup"><span data-stu-id="e45c0-133">Character groups</span></span>

<span data-ttu-id="e45c0-134">`[character group]` 允许您一次匹配任意数量的字符，而 `[^character group]` 只匹配不在组中的字符。</span><span class="sxs-lookup"><span data-stu-id="e45c0-134">`[character group]` allows you to match any number of characters one time, while `[^character group]` only matches characters NOT in the group.</span></span>

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

<span data-ttu-id="e45c0-135">如果要匹配的字符列表包括连字符 (`-`) ，则它必须位于列表的开头或结尾，才能将其与字符范围表达式区分开来。</span><span class="sxs-lookup"><span data-stu-id="e45c0-135">If your list of characters to match includes the hyphen character (`-`), it must be at the beginning or end of the list to distinguish it from a character range expression.</span></span>

#### <a name="character-ranges"></a><span data-ttu-id="e45c0-136">字符范围</span><span class="sxs-lookup"><span data-stu-id="e45c0-136">Character ranges</span></span>

<span data-ttu-id="e45c0-137">模式也可以是一系列字符。</span><span class="sxs-lookup"><span data-stu-id="e45c0-137">A pattern can also be a range of characters.</span></span> <span data-ttu-id="e45c0-138">字符可以是字母 `[A-Z]` 、数字 `[0-9]` ，甚至是基于 ASCII 的 `[ -~]` (所有可打印字符) 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-138">The characters can be alphabetic `[A-Z]`, numeric `[0-9]`, or even ASCII-based `[ -~]` (all printable characters).</span></span>

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a><span data-ttu-id="e45c0-139">数字</span><span class="sxs-lookup"><span data-stu-id="e45c0-139">Numbers</span></span>

<span data-ttu-id="e45c0-140">`\d`字符类将匹配任何十进制数字。</span><span class="sxs-lookup"><span data-stu-id="e45c0-140">The `\d` character class will match any decimal digit.</span></span> <span data-ttu-id="e45c0-141">相反， `\D` 将与任何非十进制数字匹配。</span><span class="sxs-lookup"><span data-stu-id="e45c0-141">Conversely, `\D` will match any non-decimal digit.</span></span>

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a><span data-ttu-id="e45c0-142">单词字符</span><span class="sxs-lookup"><span data-stu-id="e45c0-142">Word characters</span></span>

<span data-ttu-id="e45c0-143">`\w`字符类将匹配任何单词字符 `[a-zA-Z_0-9]` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-143">The `\w` character class will match any word character `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="e45c0-144">若要匹配任何非单词字符，请使用 `\W` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-144">To match any non-word character, use `\W`.</span></span>

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a><span data-ttu-id="e45c0-145">通配符</span><span class="sxs-lookup"><span data-stu-id="e45c0-145">Wildcards</span></span>

<span data-ttu-id="e45c0-146">句点 (`.`) 是正则表达式中的通配符。</span><span class="sxs-lookup"><span data-stu-id="e45c0-146">The period (`.`) is a wildcard character in regular expressions.</span></span> <span data-ttu-id="e45c0-147">它将匹配除换行 () 之外的任何字符 `\n` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-147">It will match any character except a newline (`\n`).</span></span>

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a><span data-ttu-id="e45c0-148">空格</span><span class="sxs-lookup"><span data-stu-id="e45c0-148">Whitespace</span></span>

<span data-ttu-id="e45c0-149">使用字符类匹配空白 `\s` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-149">Whitespace is matched using the `\s` character class.</span></span> <span data-ttu-id="e45c0-150">使用匹配的任何非空白字符 `\S` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-150">Any non-whitespace character is matched using `\S`.</span></span> <span data-ttu-id="e45c0-151">`' '`还可以使用文本空格字符。</span><span class="sxs-lookup"><span data-stu-id="e45c0-151">Literal space characters `' '` can also be used.</span></span>

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a><span data-ttu-id="e45c0-152">数量词</span><span class="sxs-lookup"><span data-stu-id="e45c0-152">Quantifiers</span></span>

<span data-ttu-id="e45c0-153">限定符控制输入字符串中应存在的每个元素的实例数。</span><span class="sxs-lookup"><span data-stu-id="e45c0-153">Quantifiers control how many instances of each element should be present in the input string.</span></span>

<span data-ttu-id="e45c0-154">下面是 PowerShell 中提供的几个限定符：</span><span class="sxs-lookup"><span data-stu-id="e45c0-154">The following are a few of the quantifiers available in PowerShell:</span></span>

| <span data-ttu-id="e45c0-155">限定符</span><span class="sxs-lookup"><span data-stu-id="e45c0-155">Quantifier</span></span> |                <span data-ttu-id="e45c0-156">描述</span><span class="sxs-lookup"><span data-stu-id="e45c0-156">Description</span></span>                |
| ---------- | ----------------------------------------- |
| `*`        | <span data-ttu-id="e45c0-157">零次或多次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-157">Zero or more times.</span></span>                       |
| `+`        | <span data-ttu-id="e45c0-158">一次或多次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-158">One or more times.</span></span>                        |
| `?`        | <span data-ttu-id="e45c0-159">零次或一次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-159">Zero or one time.</span></span>                         |
| `{n,m}`    | <span data-ttu-id="e45c0-160">至少 `n` ，但不超过 `m` 次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-160">At least `n`, but no more than `m` times.</span></span> |

<span data-ttu-id="e45c0-161">星号 (`*`) 匹配上一个元素零次或多次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-161">The asterisk (`*`) matches the previous element zero or more times.</span></span> <span data-ttu-id="e45c0-162">结果是，即使输入字符串没有元素也是匹配项。</span><span class="sxs-lookup"><span data-stu-id="e45c0-162">The result is that even an input string without the element would be a match.</span></span>

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

<span data-ttu-id="e45c0-163">加号 (`+`) 匹配上一个元素一次或多次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-163">The plus sign (`+`) matches the previous element one or more times.</span></span>

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

<span data-ttu-id="e45c0-164">问号 `?` 匹配上一个元素零次或一次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-164">The question mark `?` matches the previous element zero or one time.</span></span> <span data-ttu-id="e45c0-165">与星号类似 `*` ，它甚至会匹配缺少元素的字符串。</span><span class="sxs-lookup"><span data-stu-id="e45c0-165">Like asterisk `*`, it will even match strings where the element is absent.</span></span>

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

<span data-ttu-id="e45c0-166">`{n, m}`限定符可以使用多种不同的方式来允许对限定符进行精细控制。</span><span class="sxs-lookup"><span data-stu-id="e45c0-166">The `{n, m}` quantifier can be used several different ways to allow granular control over the quantifier.</span></span> <span data-ttu-id="e45c0-167">第二个元素 `m` 和逗号 `,` 是可选的。</span><span class="sxs-lookup"><span data-stu-id="e45c0-167">The second element `m` and the comma `,` are optional.</span></span>

| <span data-ttu-id="e45c0-168">限定符</span><span class="sxs-lookup"><span data-stu-id="e45c0-168">Quantifier</span></span> |                <span data-ttu-id="e45c0-169">描述</span><span class="sxs-lookup"><span data-stu-id="e45c0-169">Description</span></span>                 |
| ---------- | ------------------------------------------ |
| `{n}`      | <span data-ttu-id="e45c0-170">精确匹配 `n` 次数。</span><span class="sxs-lookup"><span data-stu-id="e45c0-170">Match EXACTLY `n` number of times.</span></span>         |
| `{n,}`     | <span data-ttu-id="e45c0-171">匹配至少 `n` 次。</span><span class="sxs-lookup"><span data-stu-id="e45c0-171">Match at LEAST `n` number of times.</span></span>        |
| `{n,m}`    | <span data-ttu-id="e45c0-172">匹配 `n` 和 `m` 次数。</span><span class="sxs-lookup"><span data-stu-id="e45c0-172">Match between `n` and `m` number of times.</span></span> |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a><span data-ttu-id="e45c0-173">定位点</span><span class="sxs-lookup"><span data-stu-id="e45c0-173">Anchors</span></span>

<span data-ttu-id="e45c0-174">定位点允许根据输入字符串中的匹配位置，使匹配成功或失败。</span><span class="sxs-lookup"><span data-stu-id="e45c0-174">Anchors allow you to cause a match to succeed or fail based on the matches position within the input string.</span></span>

<span data-ttu-id="e45c0-175">两个常用的定位点为 `^` 和 `$` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-175">The two commonly used anchors are `^` and `$`.</span></span> <span data-ttu-id="e45c0-176">插入符号 `^` 与字符串的开头匹配，后者与 `$` 字符串的末尾匹配。</span><span class="sxs-lookup"><span data-stu-id="e45c0-176">The caret `^` matches the start of a string, and `$`, which matches the end of a string.</span></span> <span data-ttu-id="e45c0-177">定位点允许您在特定位置匹配文本，同时还会丢弃不需要的字符。</span><span class="sxs-lookup"><span data-stu-id="e45c0-177">The anchors allow you to match your text at a specific position while also discarding unwanted characters.</span></span>

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> <span data-ttu-id="e45c0-178">定义包含定位点的 regex 时 `$` ，请确保使用单引号将 regex 括起来 (`'`) 而不是双引号 (`"`) 或 PowerShell 将表达式扩展为变量。</span><span class="sxs-lookup"><span data-stu-id="e45c0-178">When defining a regex containing an `$` anchor, be sure to enclose the regex using single quotes (`'`) instead of double quotes (`"`) or PowerShell will expand the expression as a variable.</span></span>

<span data-ttu-id="e45c0-179">在 PowerShell 中使用定位点时，应了解 **regexoptions.singleline** 和 **多行** 正则表达式选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e45c0-179">When using anchors in PowerShell, you should understand the difference between **Singleline** and **Multiline** regular expression options.</span></span>

- <span data-ttu-id="e45c0-180">**多** 行模式强制 `^` 并 `$` 匹配每行的开头，而不是输入字符串的开头和结尾。</span><span class="sxs-lookup"><span data-stu-id="e45c0-180">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every LINE instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="e45c0-181">**Regexoptions.singleline** ： regexoptions.singleline 模式将输入字符串视为 **regexoptions.singleline** 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-181">**Singleline** : Singleline mode treats the input string as a **SingleLine** .</span></span>
  <span data-ttu-id="e45c0-182">它强制 `.` 字符匹配每个字符 (包括换行符) ，而不是与除换行符之外的每个字符匹配 `\n` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-182">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>

<span data-ttu-id="e45c0-183">若要了解有关这些选项以及如何使用这些选项的详细信息，请访问 [正则表达式语言-快速参考](/dotnet/standard/base-types/regular-expression-language-quick-reference)。</span><span class="sxs-lookup"><span data-stu-id="e45c0-183">To read more about these options and how to use them, visit the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

### <a name="escaping-characters"></a><span data-ttu-id="e45c0-184">转义字符</span><span class="sxs-lookup"><span data-stu-id="e45c0-184">Escaping characters</span></span>

<span data-ttu-id="e45c0-185">反斜杠 (`\`) 用于转义字符，因此正则表达式引擎不会对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="e45c0-185">The backslash (`\`) is used to escape characters so they aren't parsed by the regular expression engine.</span></span>

<span data-ttu-id="e45c0-186">保留以下字符： `[]().\^$|?*+{}` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-186">The following characters are reserved: `[]().\^$|?*+{}`.</span></span>

<span data-ttu-id="e45c0-187">需要对模式中的这些字符进行转义，使其与输入字符串中的字符匹配。</span><span class="sxs-lookup"><span data-stu-id="e45c0-187">You'll need to escape these characters in your patterns to match them in your input strings.</span></span>

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

<span data-ttu-id="e45c0-188">Regex 类的静态方法可为你转义文本。</span><span class="sxs-lookup"><span data-stu-id="e45c0-188">There\`s a static method of the regex class that can escape text for you.</span></span>

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> <span data-ttu-id="e45c0-189">这会转义所有保留的正则表达式字符，包括字符类中使用的现有反斜杠。</span><span class="sxs-lookup"><span data-stu-id="e45c0-189">This escapes all reserved regular expression characters, including existing backslashes used in character classes.</span></span> <span data-ttu-id="e45c0-190">请确保只在您需要转义的模式部分使用它。</span><span class="sxs-lookup"><span data-stu-id="e45c0-190">Be sure to only use it on the portion of your pattern that you need to escape.</span></span>

#### <a name="other-character-escapes"></a><span data-ttu-id="e45c0-191">其他字符转义</span><span class="sxs-lookup"><span data-stu-id="e45c0-191">Other character escapes</span></span>

<span data-ttu-id="e45c0-192">还可以使用保留字符转义来匹配特殊字符类型。</span><span class="sxs-lookup"><span data-stu-id="e45c0-192">There are also reserved character escapes that you can use to match special character types.</span></span>

<span data-ttu-id="e45c0-193">下面是几个常用的字符转义：</span><span class="sxs-lookup"><span data-stu-id="e45c0-193">The following are a few commonly used character escapes:</span></span>

|<span data-ttu-id="e45c0-194">字符转义</span><span class="sxs-lookup"><span data-stu-id="e45c0-194">Character Escape</span></span>  |<span data-ttu-id="e45c0-195">说明</span><span class="sxs-lookup"><span data-stu-id="e45c0-195">Description</span></span>  |
|---------|---------|
|`\t`|<span data-ttu-id="e45c0-196">匹配选项卡</span><span class="sxs-lookup"><span data-stu-id="e45c0-196">Matches a tab</span></span>|
|`\n`|<span data-ttu-id="e45c0-197">匹配换行符</span><span class="sxs-lookup"><span data-stu-id="e45c0-197">Matches a newline</span></span>|
|`\r`|<span data-ttu-id="e45c0-198">匹配回车符</span><span class="sxs-lookup"><span data-stu-id="e45c0-198">Matches a carriage return</span></span>|

### <a name="groups-captures-and-substitutions"></a><span data-ttu-id="e45c0-199">组、捕获和替换</span><span class="sxs-lookup"><span data-stu-id="e45c0-199">Groups, Captures, and Substitutions</span></span>

<span data-ttu-id="e45c0-200">分组构造将输入字符串分隔为可捕获或忽略的子字符串。</span><span class="sxs-lookup"><span data-stu-id="e45c0-200">Grouping constructs separate an input string into substrings that can be captured or ignored.</span></span> <span data-ttu-id="e45c0-201">分组的子字符串称为子字符串。</span><span class="sxs-lookup"><span data-stu-id="e45c0-201">Grouped substrings are called subexpressions.</span></span> <span data-ttu-id="e45c0-202">默认情况下，子表达式是在编号组中捕获的，但也可以为它们指定名称。</span><span class="sxs-lookup"><span data-stu-id="e45c0-202">By default subexpressions are captured in numbered groups, though you can assign names to them as well.</span></span>

<span data-ttu-id="e45c0-203">分组构造是括在括号中的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e45c0-203">A grouping construct is a regular expression surrounded by parentheses.</span></span> <span data-ttu-id="e45c0-204">捕获由正则表达式匹配的任何文本。</span><span class="sxs-lookup"><span data-stu-id="e45c0-204">Any text matched by the enclosed regular expression is captured.</span></span> <span data-ttu-id="e45c0-205">下面的示例将输入文本分成两个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e45c0-205">The following example will break the input text into two capturing groups.</span></span>

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

<span data-ttu-id="e45c0-206">使用 `$Matches` **哈希表** 自动变量检索捕获的文本。</span><span class="sxs-lookup"><span data-stu-id="e45c0-206">Use the `$Matches` **Hashtable** automatic variable to retrieve captured text.</span></span>
<span data-ttu-id="e45c0-207">表示整个匹配项的文本存储在键上 `0` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-207">The text representing the entire match is stored at key `0`.</span></span>

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

<span data-ttu-id="e45c0-208">捕获以从左到右递增的数值 **整数** 键存储。</span><span class="sxs-lookup"><span data-stu-id="e45c0-208">Captures are stored in numeric **Integer** keys that increase from left to right.</span></span> <span data-ttu-id="e45c0-209">捕获 `1` 包含所有文本，直到用户名、捕获 `2` 只包含用户名。</span><span class="sxs-lookup"><span data-stu-id="e45c0-209">Capture `1` contains all the text until the username, capture `2` contains just the username.</span></span>

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> <span data-ttu-id="e45c0-210">`0`该键是一个 **整数** 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-210">The `0` key is an **Integer** .</span></span> <span data-ttu-id="e45c0-211">您可以使用任何 **哈希表** 方法来访问存储的值。</span><span class="sxs-lookup"><span data-stu-id="e45c0-211">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```
> PS> 'Good Dog' -match 'Dog'
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

#### <a name="named-captures"></a><span data-ttu-id="e45c0-212">命名捕获</span><span class="sxs-lookup"><span data-stu-id="e45c0-212">Named Captures</span></span>

<span data-ttu-id="e45c0-213">默认情况下，捕获以升序从左到右的顺序存储。</span><span class="sxs-lookup"><span data-stu-id="e45c0-213">By default, captures are stored in ascending numeric order, from left to right.</span></span>
<span data-ttu-id="e45c0-214">你还可以为捕获组分配一个 **名称** 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-214">You can also assign a **name** to a capturing group.</span></span> <span data-ttu-id="e45c0-215">此 **名称** 将成为 `$Matches` **哈希表** 自动变量上的键。</span><span class="sxs-lookup"><span data-stu-id="e45c0-215">This **name** becomes a key on the `$Matches` **Hashtable** automatic variable.</span></span>

<span data-ttu-id="e45c0-216">在捕获组内，使用将 `?<keyname>` 捕获的数据存储在已命名的密钥下。</span><span class="sxs-lookup"><span data-stu-id="e45c0-216">Inside a capturing group, use `?<keyname>` to store captured data under a named key.</span></span>

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

<span data-ttu-id="e45c0-217">下面的示例在 Windows 安全日志中存储最新的日志条目。</span><span class="sxs-lookup"><span data-stu-id="e45c0-217">The following example stores the newest log entry in the Windows Security Log.</span></span>
<span data-ttu-id="e45c0-218">提供的正则表达式从消息中提取用户名和域，并将其存储在 " **N** 名称" 下，将其存储在 "域名" 和 " **D** "。</span><span class="sxs-lookup"><span data-stu-id="e45c0-218">The provided regular expression extracts the username and domain from the message and stores them under the keys: **N** for name and **D** for domain.</span></span>

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

<span data-ttu-id="e45c0-219">有关详细信息，请参阅 [正则表达式中的分组构造](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions)。</span><span class="sxs-lookup"><span data-stu-id="e45c0-219">For more information, see [Grouping Constructs in Regular Expressions](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="e45c0-220">正则表达式中的替代</span><span class="sxs-lookup"><span data-stu-id="e45c0-220">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="e45c0-221">将正则表达式与运算符一起使用， `-replace` 可以使用捕获的文本动态替换文本。</span><span class="sxs-lookup"><span data-stu-id="e45c0-221">Using the regular expressions with the `-replace` operator allows you to dynamically replace text using captured text.</span></span>

`<input> -replace <original>, <substitute>`

- <span data-ttu-id="e45c0-222">`<input>`：要搜索的字符串</span><span class="sxs-lookup"><span data-stu-id="e45c0-222">`<input>`: The string to be searched</span></span>
- <span data-ttu-id="e45c0-223">`<original>`：用于搜索输入字符串的正则表达式</span><span class="sxs-lookup"><span data-stu-id="e45c0-223">`<original>`: A regular expression used to search the input string</span></span>
- <span data-ttu-id="e45c0-224">`<substitute>`：用于替换输入字符串中找到的匹配项的正则表达式替换表达式。</span><span class="sxs-lookup"><span data-stu-id="e45c0-224">`<substitute>`: A regular expression substitution expression to replace matches found in the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="e45c0-225">`<original>`和 `<substitute>` 操作数服从正则表达式引擎（如字符转义）的规则。</span><span class="sxs-lookup"><span data-stu-id="e45c0-225">The `<original>` and `<substitute>` operands are subject to rules of the regular expression engine such as character escaping.</span></span>

<span data-ttu-id="e45c0-226">捕获组可以在字符串中引用 `<substitute>` 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-226">Capturing groups can be referenced in the `<substitute>` string.</span></span> <span data-ttu-id="e45c0-227">通过使用 `$` 组标识符前面的字符来完成替换。</span><span class="sxs-lookup"><span data-stu-id="e45c0-227">The substitution is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="e45c0-228">引用捕获组的两种方法是按 **编号** 和 **名称** 。</span><span class="sxs-lookup"><span data-stu-id="e45c0-228">Two ways to reference capturing groups are by **Number** and by **Name** .</span></span>

- <span data-ttu-id="e45c0-229">按 **编号** 捕获组按从左到右的顺序进行编号。</span><span class="sxs-lookup"><span data-stu-id="e45c0-229">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="e45c0-230">通过 **名称** ，也可以按名称引用捕获组。</span><span class="sxs-lookup"><span data-stu-id="e45c0-230">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

<span data-ttu-id="e45c0-231">`$&`表达式表示匹配的所有文本。</span><span class="sxs-lookup"><span data-stu-id="e45c0-231">The `$&` expression represents all the text matched.</span></span>

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> <span data-ttu-id="e45c0-232">由于 `$` 字符是在字符串扩展中使用的，因此您需要将字符串与替换一起使用，或者 `$` 在使用双引号时对字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="e45c0-232">Since the `$` character is used in string expansion, you'll need to use literal strings with substitution, or escape the `$` character when using double quotes.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> <span data-ttu-id="e45c0-233">此外，如果你希望将 `$` 作为文本字符，请使用 `$$` 而不是常规转义字符。</span><span class="sxs-lookup"><span data-stu-id="e45c0-233">Additionally, if you want to have the `$` as a literal character, use `$$` instead of the normal escape characters.</span></span> <span data-ttu-id="e45c0-234">使用双引号时，仍然会转义的所有实例， `$` 以避免不正确的替换。</span><span class="sxs-lookup"><span data-stu-id="e45c0-234">When using double quotes, still escape all instances of `$` to avoid incorrect substitution.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

<span data-ttu-id="e45c0-235">有关详细信息，请参阅 [正则表达式中的替换](/dotnet/standard/base-types/substitutions-in-regular-expressions)。</span><span class="sxs-lookup"><span data-stu-id="e45c0-235">For more information, see [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span></span>

## <a name="see-also"></a><span data-ttu-id="e45c0-236">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e45c0-236">See also</span></span>

[<span data-ttu-id="e45c0-237">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="e45c0-237">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="e45c0-238">about_Operators</span><span class="sxs-lookup"><span data-stu-id="e45c0-238">about_Operators</span></span>](about_Operators.md)

