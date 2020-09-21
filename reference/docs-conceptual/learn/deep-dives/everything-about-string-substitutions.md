---
title: 关于字符串中变量替换的各项须知内容
description: 使用字符串中的变量创建格式化文本的方法有很多。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 786526fb98dbf1b3ec7c5c6c985ac95b85a96259
ms.sourcegitcommit: 4bb44f183dcbfa8dced57f075812e02d3b45fd70
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "86301312"
---
# <a name="everything-you-wanted-to-know-about-variable-substitution-in-strings"></a>关于字符串中变量替换的各项须知内容

可以通过很多方法使用字符串中的变量。 我称之为变量替换，但我指的是任何时候你想格式化一个字符串来包含变量的值的情形。 这是我经常向脚本编写新手解释的内容。

> [!NOTE]
> 本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。 PowerShell 团队感谢 Kevin 与我们分享这篇文章。 请前往 [PowerShellExplained.com][] 访问他的博客。

## <a name="concatenation"></a>串联

第一类方法可称为串联。 它基本上采用多个字符串并将它们联接在一起。 使用串联生成格式化字符串的做法由来已久。

```powershell
$name = 'Kevin Marquette'
$message = 'Hello, ' + $name
```

当只要添加几个值时，串联效果不错。 但这可能很快就会变得复杂。

```powershell
$first = 'Kevin'
$last = 'Marquette'
```

```powershell
$message = 'Hello, ' + $first + ' ' + $last + '.'
```

这个简单的示例已经变得越来越难读了。

## <a name="variable-substitution"></a>变量替换

PowerShell 提供了另一个更简单的选项。 你可以直接在字符串中指定变量。

```powershell
$message = "Hello, $first $last."
```

在字符串两边使用的引号类型会产生差别。 带双引号的字符串允许替换，带单引号的字符串则不允许替换。 有时候需要其中一种效果，所以你有选择的空间。

## <a name="command-substitution"></a>命令替换

开始尝试将属性的值获取到字符串中时，有一些麻烦。 很多新手都会在这里出错。 首先，我会向你展示他们觉得应该行得通的想法（从表面上看，值几乎与预期效果一样）。

```powershell
$directory = Get-Item 'c:\windows'
$message = "Time: $directory.CreationTime"
```

你希望从 `$directory` 获得 `CreationTime`，但结果得到的值是 `Time: c:\windows.CreationTime`。 原因在于，这种类型的替换仅看基变量。 它将句点视为字符串的一部分，因而停止更深入地解析值。

巧的是，在将此对象置于字符串中时，此对象会提供一个字符串作为默认值。
某些对象会为你提供类型名称，例如 `System.Collections.Hashtable`。 这里只是列举一些需要注意的事项。

PowerShell 允许使用特殊语法在字符串内执行命令。 这样，我们就可以获取这些对象的属性，并运行任何其他命令来获取值。

```powershell
$message = "Time: $($directory.CreationTime)"
```

这在某些情况下非常有用，但如果你只有几个变量，它可能会像串联一样变得相当古怪。

### <a name="command-execution"></a>命令执行

可以在字符串中运行命令。 虽然我有这个选项，但我并不喜欢。 因为它很快就会变得混乱，难以调试。 我会运行该命令并将其保存到变量或使用格式字符串。

```powershell
$message = "Date: $(Get-Date)"
```

## <a name="format-string"></a>格式字符串

.NET 提供了一种格式化字符串的方法，我发现这种方法非常易于使用。 首先，我会向你展示它的静态方法，然后再介绍达到同样目的的 PowerShell 快捷方式。

```powershell
# .NET string format string
[string]::Format('Hello, {0} {1}.',$first,$last)

# PowerShell format string
'Hello, {0} {1}.' -f $first, $last
```

此处发生的情况是，字符串针对 `{0}` 和 `{1}` 标记得到分析，然后使用该数字从提供的值中进行选择。 如果希望在字符串中的某个位置重复一个值，可以重用该值数字。

字符串越复杂，这种方法的价值越高。

### <a name="format-values-as-arrays"></a>将值格式化为数组

如果格式行的长度太长，可以先将值放入数组中。

```powershell
$values = @(
    "Kevin"
    "Marquette"
)
'Hello, {0} {1}.' -f $values
```

这不会展开，因为我要传递整个数组，但思路类似。

## <a name="advanced-formatting"></a>高级格式设置

我特意将这些方法称为来自 .NET，因为有许多格式化选项已经有关于它的详细[记录][]。 可以通过内置方式设置各种数据类型的格式。

```powershell
"{0:yyyyMMdd}" -f (Get-Date)
"Population {0:N0}" -f  8175133
```

我不打算进行深入讲解，但希望你知道，如果你需要的话，这是一个非常强大的格式化引擎。

## <a name="joining-strings"></a>联接字符串

有时，确实要将一些值串联在一起。 `-join` 运算符可为你执行此操作。 它甚至可以让你指定要在字符串之间联接的字符。

```powershell
$servers = @(
    'server1'
    'server2'
    'server3'
)

$servers  -join ','
```

如果需要对一些不带分隔符的字符串执行 `-join` 命令，则需要指定一个空字符串 `''`。
但如果这就是你全部需要的，还有一个更快的选择。

```powershell
[string]::Concat('server1','server2','server3')
[string]::Concat($servers)
```

还需指出的是，也可以对字符串执行 `-split` 命令。

## <a name="join-path"></a>Join-Path

它通常会被忽略，但却是用于生成文件路径的绝佳 cmdlet。

```powershell
$folder = 'Temp'
Join-Path -Path 'c:\windows' -ChildPath $folder
```

它的好处是，在将值放在一起时，它会正确地处理反斜杠。 如果从用户或配置文件获取值，则这一点尤其重要。

这也适用于 `Split-Path` 和 `Test-Path`。 我还在关于[读取和保存到文件][]的文章中介绍了这些内容。

## <a name="strings-are-arrays"></a>字符串是数组

在继续之前，我需要提一下添加字符串。 请记住，字符串只是一个字符数组。 如果一起添加多个字符串，则每次都会创建一个新数组。

请看下面的示例：

```powershell
$message = "Numbers: "
foreach($number in 1..10000)
{
    $message += " $number"
}
```

它看起来非常简单，但你没有看到的是，每次将一个字符串添加到 `$message` 时，都会创建一个全新的字符串。 将会分配内存，复制数据并丢弃旧数据。
如果只是执行几次，不是什么大问题，但类似这样的循环就会暴露出问题。

### <a name="stringbuilder"></a>StringBuilder

对于使用许多较小的字符串生成大型字符串，StringBuilder 也非常受欢迎。 原因是，它只收集你向它添加的所有字符串，并且只在你检索值时在末尾串联所有字符串。

```powershell
$stringBuilder = New-Object -TypeName "System.Text.StringBuilder"

[void]$stringBuilder.Append("Numbers: ")
foreach($number in 1..10000)
{
    [void]$stringBuilder.Append(" $number")
}
$message = $stringBuilder.ToString()
```

同样，这也是我向 .NET 寻求的东西。 我并不经常用到它，但知道这一点也有好处。

## <a name="delineation-with-braces"></a>带大括号的描述

这用于字符串内的后缀串联。 有时，你的变量没有干净的字边界。

```powershell
$test = "Bet"
$tester = "Better"
Write-Host "$test $tester ${test}ter"
```

谢谢 [/u/real_parbold][] 提供此方法。

下面是此方法的替代方法：

```powershell
Write-Host "$test $tester $($test)ter"
Write-Host "{0} {1} {0}ter" -f $test, $tester
```

我个人将格式字符串用于这种情况，但了解此替代方法也有好处，以防你在别处看到。

## <a name="find-and-replace-tokens"></a>查找和替换标记

虽然这些功能中大多数限制了你使用自己的解决方案的需求，但有时你可能需要替换大型模板文件中的字符串。

假设你从一个包含大量文本的文件中拉取了模板。

```powershell
$letter = Get-Content -Path TemplateLetter.txt -RAW
$letter = $letter -replace '#FULL_NAME#', 'Kevin Marquette'
```

可能有大量要替换的标记。 这里的诀窍是使用易于查找和替换的独特标记。 我倾向于在两端使用一个特殊字符来帮助区分。

我最近发现了一种新方法来解决这一问题。 我决定把这部分留在这里，因为这是一种常用的模式。

### <a name="replace-multiple-tokens"></a>替换多个标记

如果我有一系列需要替换的标记，我会采用更通用的方法。 我会将其放在哈希表中，然后循环访问它们来进行替换。

```powershell
$tokenList = @{
    Full_Name = 'Kevin Marquette'
    Location = 'Orange County'
    State = 'CA'
}

$letter = Get-Content -Path TemplateLetter.txt -RAW
foreach( $token in $tokenList.GetEnumerator() )
{
    $pattern = '#{0}#' -f $token.key
    $letter = $letter -replace $pattern, $token.Value
}
```

如果需要，可以从 JSON 或 CSV 加载这些标记。

### <a name="executioncontext-expandstring"></a>ExecutionContext ExpandString

有一种巧妙的方法可以使用单引号定义替换字符串，之后再展开变量。 请看下面的示例：

```powershell
$message = 'Hello, $Name!'
$name = 'Kevin Marquette'
$string = $ExecutionContext.InvokeCommand.ExpandString($message)
```

对当前执行上下文的 `.InvokeCommand.ExpandString` 调用使用了当前作用域内的变量进行替换。 此处的关键在于，可以在变量存在之前尽早定义 `$message`。

如果我们再展开一点点，就可以使用不同的值反复执行此替换。

```powershell
$message = 'Hello, $Name!'
$nameList = 'Mark Kraus','Kevin Marquette','Lee Dailey'
foreach($name in $nameList){
    $ExecutionContext.InvokeCommand.ExpandString($message)
}
```

若要继续实践这一想法，你可以从文本文件导入大型电子邮件模板来实现。 我要感谢 [Mark Kraus][] 提供此[建议][]

## <a name="whatever-works-the-best-for-you"></a>只要适合你就好

我是格式字符串方法的爱好者。 对于更复杂的字符串，或者如果有多个变量，我肯定会这样做。 对于非常短的内容，我可以使用上述方法中的任何一个。

## <a name="anything-else"></a>任何其他内容？

就这个主题我已经介绍了很多内容。 希望你能学习到一些新知识。

<!-- link references -->
[原始版本]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Mark Kraus]: https://get-powershellblog.blogspot.com/
[建议]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[/u/real_parbold]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfm6p/
[读取和保存到文件]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[记录]: /dotnet/api/system.string.format#overloads
