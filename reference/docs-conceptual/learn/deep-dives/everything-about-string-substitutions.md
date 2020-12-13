---
title: 关于字符串中变量替换的各项须知内容
description: 使用字符串中的变量创建格式化文本的方法有很多。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 786526fb98dbf1b3ec7c5c6c985ac95b85a96259
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "86301312"
---
# <a name="everything-you-wanted-to-know-about-variable-substitution-in-strings"></a><span data-ttu-id="6d858-103">关于字符串中变量替换的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="6d858-103">Everything you wanted to know about variable substitution in strings</span></span>

<span data-ttu-id="6d858-104">可以通过很多方法使用字符串中的变量。</span><span class="sxs-lookup"><span data-stu-id="6d858-104">There are many ways to use variables in strings.</span></span> <span data-ttu-id="6d858-105">我称之为变量替换，但我指的是任何时候你想格式化一个字符串来包含变量的值的情形。</span><span class="sxs-lookup"><span data-stu-id="6d858-105">I'm calling this variable substitution but I'm referring to any time you want to format a string to include values from variables.</span></span> <span data-ttu-id="6d858-106">这是我经常向脚本编写新手解释的内容。</span><span class="sxs-lookup"><span data-stu-id="6d858-106">This is something that I often find myself explaining to new scripters.</span></span>

> [!NOTE]
> <span data-ttu-id="6d858-107">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="6d858-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="6d858-108">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="6d858-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="6d858-109">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="6d858-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="concatenation"></a><span data-ttu-id="6d858-110">串联</span><span class="sxs-lookup"><span data-stu-id="6d858-110">Concatenation</span></span>

<span data-ttu-id="6d858-111">第一类方法可称为串联。</span><span class="sxs-lookup"><span data-stu-id="6d858-111">The first class of methods can be referred to as concatenation.</span></span> <span data-ttu-id="6d858-112">它基本上采用多个字符串并将它们联接在一起。</span><span class="sxs-lookup"><span data-stu-id="6d858-112">It's basically taking several strings and joining them together.</span></span> <span data-ttu-id="6d858-113">使用串联生成格式化字符串的做法由来已久。</span><span class="sxs-lookup"><span data-stu-id="6d858-113">There's a long history of using concatenation to build formatted strings.</span></span>

```powershell
$name = 'Kevin Marquette'
$message = 'Hello, ' + $name
```

<span data-ttu-id="6d858-114">当只要添加几个值时，串联效果不错。</span><span class="sxs-lookup"><span data-stu-id="6d858-114">Concatenation works out OK when there are only a few values to add.</span></span> <span data-ttu-id="6d858-115">但这可能很快就会变得复杂。</span><span class="sxs-lookup"><span data-stu-id="6d858-115">But this can get complicated quickly.</span></span>

```powershell
$first = 'Kevin'
$last = 'Marquette'
```

```powershell
$message = 'Hello, ' + $first + ' ' + $last + '.'
```

<span data-ttu-id="6d858-116">这个简单的示例已经变得越来越难读了。</span><span class="sxs-lookup"><span data-stu-id="6d858-116">This simple example is already getting harder to read.</span></span>

## <a name="variable-substitution"></a><span data-ttu-id="6d858-117">变量替换</span><span class="sxs-lookup"><span data-stu-id="6d858-117">Variable substitution</span></span>

<span data-ttu-id="6d858-118">PowerShell 提供了另一个更简单的选项。</span><span class="sxs-lookup"><span data-stu-id="6d858-118">PowerShell has another option that is easier.</span></span> <span data-ttu-id="6d858-119">你可以直接在字符串中指定变量。</span><span class="sxs-lookup"><span data-stu-id="6d858-119">You can specify your variables directly in the strings.</span></span>

```powershell
$message = "Hello, $first $last."
```

<span data-ttu-id="6d858-120">在字符串两边使用的引号类型会产生差别。</span><span class="sxs-lookup"><span data-stu-id="6d858-120">The type of quotes you use around the string makes a difference.</span></span> <span data-ttu-id="6d858-121">带双引号的字符串允许替换，带单引号的字符串则不允许替换。</span><span class="sxs-lookup"><span data-stu-id="6d858-121">A double quoted string allows the substitution but a single quoted string doesn't.</span></span> <span data-ttu-id="6d858-122">有时候需要其中一种效果，所以你有选择的空间。</span><span class="sxs-lookup"><span data-stu-id="6d858-122">There are times you want one or the other so you have an option.</span></span>

## <a name="command-substitution"></a><span data-ttu-id="6d858-123">命令替换</span><span class="sxs-lookup"><span data-stu-id="6d858-123">Command substitution</span></span>

<span data-ttu-id="6d858-124">开始尝试将属性的值获取到字符串中时，有一些麻烦。</span><span class="sxs-lookup"><span data-stu-id="6d858-124">Things get a little tricky when you start trying to get the values of properties into a string.</span></span> <span data-ttu-id="6d858-125">很多新手都会在这里出错。</span><span class="sxs-lookup"><span data-stu-id="6d858-125">This is where many new people get tripped up.</span></span> <span data-ttu-id="6d858-126">首先，我会向你展示他们觉得应该行得通的想法（从表面上看，值几乎与预期效果一样）。</span><span class="sxs-lookup"><span data-stu-id="6d858-126">First let me show you what they think should work (and at face value almost looks like it should).</span></span>

```powershell
$directory = Get-Item 'c:\windows'
$message = "Time: $directory.CreationTime"
```

<span data-ttu-id="6d858-127">你希望从 `$directory` 获得 `CreationTime`，但结果得到的值是 `Time: c:\windows.CreationTime`。</span><span class="sxs-lookup"><span data-stu-id="6d858-127">You would be expecting to get the `CreationTime` off of the `$directory`, but instead you get this `Time: c:\windows.CreationTime` as your value.</span></span> <span data-ttu-id="6d858-128">原因在于，这种类型的替换仅看基变量。</span><span class="sxs-lookup"><span data-stu-id="6d858-128">The reason is that this type of substitution only sees the base variable.</span></span> <span data-ttu-id="6d858-129">它将句点视为字符串的一部分，因而停止更深入地解析值。</span><span class="sxs-lookup"><span data-stu-id="6d858-129">It considers the period as part of the string so it stops resolving the value any deeper.</span></span>

<span data-ttu-id="6d858-130">巧的是，在将此对象置于字符串中时，此对象会提供一个字符串作为默认值。</span><span class="sxs-lookup"><span data-stu-id="6d858-130">It just so happens that this object gives a string as a default value when placed into a string.</span></span>
<span data-ttu-id="6d858-131">某些对象会为你提供类型名称，例如 `System.Collections.Hashtable`。</span><span class="sxs-lookup"><span data-stu-id="6d858-131">Some objects give you the type name instead like `System.Collections.Hashtable`.</span></span> <span data-ttu-id="6d858-132">这里只是列举一些需要注意的事项。</span><span class="sxs-lookup"><span data-stu-id="6d858-132">Just something to watch for.</span></span>

<span data-ttu-id="6d858-133">PowerShell 允许使用特殊语法在字符串内执行命令。</span><span class="sxs-lookup"><span data-stu-id="6d858-133">PowerShell allows you to do command execution inside the string with a special syntax.</span></span> <span data-ttu-id="6d858-134">这样，我们就可以获取这些对象的属性，并运行任何其他命令来获取值。</span><span class="sxs-lookup"><span data-stu-id="6d858-134">This allows us to get the properties of these objects and run any other command to get a value.</span></span>

```powershell
$message = "Time: $($directory.CreationTime)"
```

<span data-ttu-id="6d858-135">这在某些情况下非常有用，但如果你只有几个变量，它可能会像串联一样变得相当古怪。</span><span class="sxs-lookup"><span data-stu-id="6d858-135">This works great for some situations but it can get just as crazy as concatenation if you have just a few variables.</span></span>

### <a name="command-execution"></a><span data-ttu-id="6d858-136">命令执行</span><span class="sxs-lookup"><span data-stu-id="6d858-136">Command execution</span></span>

<span data-ttu-id="6d858-137">可以在字符串中运行命令。</span><span class="sxs-lookup"><span data-stu-id="6d858-137">You can run commands inside a string.</span></span> <span data-ttu-id="6d858-138">虽然我有这个选项，但我并不喜欢。</span><span class="sxs-lookup"><span data-stu-id="6d858-138">Even though I have this option, I don't like it.</span></span> <span data-ttu-id="6d858-139">因为它很快就会变得混乱，难以调试。</span><span class="sxs-lookup"><span data-stu-id="6d858-139">It gets cluttered quickly and hard to debug.</span></span> <span data-ttu-id="6d858-140">我会运行该命令并将其保存到变量或使用格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6d858-140">I either run the command and save to a variable or use a format string.</span></span>

```powershell
$message = "Date: $(Get-Date)"
```

## <a name="format-string"></a><span data-ttu-id="6d858-141">格式字符串</span><span class="sxs-lookup"><span data-stu-id="6d858-141">Format string</span></span>

<span data-ttu-id="6d858-142">.NET 提供了一种格式化字符串的方法，我发现这种方法非常易于使用。</span><span class="sxs-lookup"><span data-stu-id="6d858-142">.NET has a way to format strings that I find fairly easy to work with.</span></span> <span data-ttu-id="6d858-143">首先，我会向你展示它的静态方法，然后再介绍达到同样目的的 PowerShell 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="6d858-143">First let me show you the static method for it before I show you the PowerShell shortcut to do the same thing.</span></span>

```powershell
# .NET string format string
[string]::Format('Hello, {0} {1}.',$first,$last)

# PowerShell format string
'Hello, {0} {1}.' -f $first, $last
```

<span data-ttu-id="6d858-144">此处发生的情况是，字符串针对 `{0}` 和 `{1}` 标记得到分析，然后使用该数字从提供的值中进行选择。</span><span class="sxs-lookup"><span data-stu-id="6d858-144">What is happening here is that the string is parsed for the tokens `{0}` and `{1}`, then it uses that number to pick from the values provided.</span></span> <span data-ttu-id="6d858-145">如果希望在字符串中的某个位置重复一个值，可以重用该值数字。</span><span class="sxs-lookup"><span data-stu-id="6d858-145">If you want to repeat one value some place in the string, you can reuse that values number.</span></span>

<span data-ttu-id="6d858-146">字符串越复杂，这种方法的价值越高。</span><span class="sxs-lookup"><span data-stu-id="6d858-146">The more complicated the string gets, the more value you get out of this approach.</span></span>

### <a name="format-values-as-arrays"></a><span data-ttu-id="6d858-147">将值格式化为数组</span><span class="sxs-lookup"><span data-stu-id="6d858-147">Format values as arrays</span></span>

<span data-ttu-id="6d858-148">如果格式行的长度太长，可以先将值放入数组中。</span><span class="sxs-lookup"><span data-stu-id="6d858-148">If your format line gets too long, you can place your values into an array first.</span></span>

```powershell
$values = @(
    "Kevin"
    "Marquette"
)
'Hello, {0} {1}.' -f $values
```

<span data-ttu-id="6d858-149">这不会展开，因为我要传递整个数组，但思路类似。</span><span class="sxs-lookup"><span data-stu-id="6d858-149">This is not splatting because I'm passing the whole array in, but the idea is similar.</span></span>

## <a name="advanced-formatting"></a><span data-ttu-id="6d858-150">高级格式设置</span><span class="sxs-lookup"><span data-stu-id="6d858-150">Advanced formatting</span></span>

<span data-ttu-id="6d858-151">我特意将这些方法称为来自 .NET，因为有许多格式化选项已经有关于它的详细[记录][]。</span><span class="sxs-lookup"><span data-stu-id="6d858-151">I intentionally called these out as coming from .NET because there are lots of formatting options already well [documented][] on it.</span></span> <span data-ttu-id="6d858-152">可以通过内置方式设置各种数据类型的格式。</span><span class="sxs-lookup"><span data-stu-id="6d858-152">There are built in ways to format various data types.</span></span>

```powershell
"{0:yyyyMMdd}" -f (Get-Date)
"Population {0:N0}" -f  8175133
```

<span data-ttu-id="6d858-153">我不打算进行深入讲解，但希望你知道，如果你需要的话，这是一个非常强大的格式化引擎。</span><span class="sxs-lookup"><span data-stu-id="6d858-153">I'm not going to go into them but I just wanted to let you know that this is a very powerful formatting engine if you need it.</span></span>

## <a name="joining-strings"></a><span data-ttu-id="6d858-154">联接字符串</span><span class="sxs-lookup"><span data-stu-id="6d858-154">Joining strings</span></span>

<span data-ttu-id="6d858-155">有时，确实要将一些值串联在一起。</span><span class="sxs-lookup"><span data-stu-id="6d858-155">Sometimes you actually do want to concatenate a list of values together.</span></span> <span data-ttu-id="6d858-156">`-join` 运算符可为你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6d858-156">There's a `-join` operator that can do that for you.</span></span> <span data-ttu-id="6d858-157">它甚至可以让你指定要在字符串之间联接的字符。</span><span class="sxs-lookup"><span data-stu-id="6d858-157">It even lets you specify a character to join between the strings.</span></span>

```powershell
$servers = @(
    'server1'
    'server2'
    'server3'
)

$servers  -join ','
```

<span data-ttu-id="6d858-158">如果需要对一些不带分隔符的字符串执行 `-join` 命令，则需要指定一个空字符串 `''`。</span><span class="sxs-lookup"><span data-stu-id="6d858-158">If you want to `-join` some strings without a separator, you need to specify an empty string `''`.</span></span>
<span data-ttu-id="6d858-159">但如果这就是你全部需要的，还有一个更快的选择。</span><span class="sxs-lookup"><span data-stu-id="6d858-159">But if that is all you need, there's a faster option.</span></span>

```powershell
[string]::Concat('server1','server2','server3')
[string]::Concat($servers)
```

<span data-ttu-id="6d858-160">还需指出的是，也可以对字符串执行 `-split` 命令。</span><span class="sxs-lookup"><span data-stu-id="6d858-160">It's also worth pointing out that you can also `-split` strings too.</span></span>

## <a name="join-path"></a><span data-ttu-id="6d858-161">Join-Path</span><span class="sxs-lookup"><span data-stu-id="6d858-161">Join-Path</span></span>

<span data-ttu-id="6d858-162">它通常会被忽略，但却是用于生成文件路径的绝佳 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d858-162">This is often overlooked but a great cmdlet for building a file path.</span></span>

```powershell
$folder = 'Temp'
Join-Path -Path 'c:\windows' -ChildPath $folder
```

<span data-ttu-id="6d858-163">它的好处是，在将值放在一起时，它会正确地处理反斜杠。</span><span class="sxs-lookup"><span data-stu-id="6d858-163">The great thing about this is it works out the backslashes correctly when it puts the values together.</span></span> <span data-ttu-id="6d858-164">如果从用户或配置文件获取值，则这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="6d858-164">This is especially important if you are taking values from users or config files.</span></span>

<span data-ttu-id="6d858-165">这也适用于 `Split-Path` 和 `Test-Path`。</span><span class="sxs-lookup"><span data-stu-id="6d858-165">This also goes well with `Split-Path` and `Test-Path`.</span></span> <span data-ttu-id="6d858-166">我还在关于[读取和保存到文件][]的文章中介绍了这些内容。</span><span class="sxs-lookup"><span data-stu-id="6d858-166">I also cover these in my post about [reading and saving to files][].</span></span>

## <a name="strings-are-arrays"></a><span data-ttu-id="6d858-167">字符串是数组</span><span class="sxs-lookup"><span data-stu-id="6d858-167">Strings are arrays</span></span>

<span data-ttu-id="6d858-168">在继续之前，我需要提一下添加字符串。</span><span class="sxs-lookup"><span data-stu-id="6d858-168">I do need to mention adding strings here before I go on.</span></span> <span data-ttu-id="6d858-169">请记住，字符串只是一个字符数组。</span><span class="sxs-lookup"><span data-stu-id="6d858-169">Remember that a string is just an array of characters.</span></span> <span data-ttu-id="6d858-170">如果一起添加多个字符串，则每次都会创建一个新数组。</span><span class="sxs-lookup"><span data-stu-id="6d858-170">When you add multiple strings together, a new array is created each time.</span></span>

<span data-ttu-id="6d858-171">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="6d858-171">Look at this example:</span></span>

```powershell
$message = "Numbers: "
foreach($number in 1..10000)
{
    $message += " $number"
}
```

<span data-ttu-id="6d858-172">它看起来非常简单，但你没有看到的是，每次将一个字符串添加到 `$message` 时，都会创建一个全新的字符串。</span><span class="sxs-lookup"><span data-stu-id="6d858-172">It looks very basic but what you don't see is that each time a string is added to `$message` that a whole new string is created.</span></span> <span data-ttu-id="6d858-173">将会分配内存，复制数据并丢弃旧数据。</span><span class="sxs-lookup"><span data-stu-id="6d858-173">Memory gets allocated, data gets copied and the old one is discarded.</span></span>
<span data-ttu-id="6d858-174">如果只是执行几次，不是什么大问题，但类似这样的循环就会暴露出问题。</span><span class="sxs-lookup"><span data-stu-id="6d858-174">Not a big deal when it's only done a few times, but a loop like this would really expose the issue.</span></span>

### <a name="stringbuilder"></a><span data-ttu-id="6d858-175">StringBuilder</span><span class="sxs-lookup"><span data-stu-id="6d858-175">StringBuilder</span></span>

<span data-ttu-id="6d858-176">对于使用许多较小的字符串生成大型字符串，StringBuilder 也非常受欢迎。</span><span class="sxs-lookup"><span data-stu-id="6d858-176">StringBuilder is also very popular for building large strings from lots of smaller strings.</span></span> <span data-ttu-id="6d858-177">原因是，它只收集你向它添加的所有字符串，并且只在你检索值时在末尾串联所有字符串。</span><span class="sxs-lookup"><span data-stu-id="6d858-177">The reason why is because it just collects all the strings you add to it and only concatenates all of them at the end when you retrieve the value.</span></span>

```powershell
$stringBuilder = New-Object -TypeName "System.Text.StringBuilder"

[void]$stringBuilder.Append("Numbers: ")
foreach($number in 1..10000)
{
    [void]$stringBuilder.Append(" $number")
}
$message = $stringBuilder.ToString()
```

<span data-ttu-id="6d858-178">同样，这也是我向 .NET 寻求的东西。</span><span class="sxs-lookup"><span data-stu-id="6d858-178">Again, this is something that I'm reaching out to .NET for.</span></span> <span data-ttu-id="6d858-179">我并不经常用到它，但知道这一点也有好处。</span><span class="sxs-lookup"><span data-stu-id="6d858-179">I don't use it often anymore but it's good to know it's there.</span></span>

## <a name="delineation-with-braces"></a><span data-ttu-id="6d858-180">带大括号的描述</span><span class="sxs-lookup"><span data-stu-id="6d858-180">Delineation with braces</span></span>

<span data-ttu-id="6d858-181">这用于字符串内的后缀串联。</span><span class="sxs-lookup"><span data-stu-id="6d858-181">This is used for suffix concatenation within the string.</span></span> <span data-ttu-id="6d858-182">有时，你的变量没有干净的字边界。</span><span class="sxs-lookup"><span data-stu-id="6d858-182">Sometimes your variable doesn't have a clean word boundary.</span></span>

```powershell
$test = "Bet"
$tester = "Better"
Write-Host "$test $tester ${test}ter"
```

<span data-ttu-id="6d858-183">谢谢 [/u/real_parbold][] 提供此方法。</span><span class="sxs-lookup"><span data-stu-id="6d858-183">Thank you [/u/real_parbold][] for that one.</span></span>

<span data-ttu-id="6d858-184">下面是此方法的替代方法：</span><span class="sxs-lookup"><span data-stu-id="6d858-184">Here is an alternate to this approach:</span></span>

```powershell
Write-Host "$test $tester $($test)ter"
Write-Host "{0} {1} {0}ter" -f $test, $tester
```

<span data-ttu-id="6d858-185">我个人将格式字符串用于这种情况，但了解此替代方法也有好处，以防你在别处看到。</span><span class="sxs-lookup"><span data-stu-id="6d858-185">I personally use format string for this, but this is good to know incase you see it in the wild.</span></span>

## <a name="find-and-replace-tokens"></a><span data-ttu-id="6d858-186">查找和替换标记</span><span class="sxs-lookup"><span data-stu-id="6d858-186">Find and replace tokens</span></span>

<span data-ttu-id="6d858-187">虽然这些功能中大多数限制了你使用自己的解决方案的需求，但有时你可能需要替换大型模板文件中的字符串。</span><span class="sxs-lookup"><span data-stu-id="6d858-187">While most of these features limit your need to roll your own solution, there are times where you may have large template files where you want to replace strings inside.</span></span>

<span data-ttu-id="6d858-188">假设你从一个包含大量文本的文件中拉取了模板。</span><span class="sxs-lookup"><span data-stu-id="6d858-188">Let us assume you pulled in a template from a file that has a lot of text.</span></span>

```powershell
$letter = Get-Content -Path TemplateLetter.txt -RAW
$letter = $letter -replace '#FULL_NAME#', 'Kevin Marquette'
```

<span data-ttu-id="6d858-189">可能有大量要替换的标记。</span><span class="sxs-lookup"><span data-stu-id="6d858-189">You may have lots of tokens to replace.</span></span> <span data-ttu-id="6d858-190">这里的诀窍是使用易于查找和替换的独特标记。</span><span class="sxs-lookup"><span data-stu-id="6d858-190">The trick is to use a very distinct token that is easy to find and replace.</span></span> <span data-ttu-id="6d858-191">我倾向于在两端使用一个特殊字符来帮助区分。</span><span class="sxs-lookup"><span data-stu-id="6d858-191">I tend to use a special character at both ends to help distinguish it.</span></span>

<span data-ttu-id="6d858-192">我最近发现了一种新方法来解决这一问题。</span><span class="sxs-lookup"><span data-stu-id="6d858-192">I recently found a new way to approach this.</span></span> <span data-ttu-id="6d858-193">我决定把这部分留在这里，因为这是一种常用的模式。</span><span class="sxs-lookup"><span data-stu-id="6d858-193">I decided to leave this section in here because this is a pattern that is commonly used.</span></span>

### <a name="replace-multiple-tokens"></a><span data-ttu-id="6d858-194">替换多个标记</span><span class="sxs-lookup"><span data-stu-id="6d858-194">Replace multiple tokens</span></span>

<span data-ttu-id="6d858-195">如果我有一系列需要替换的标记，我会采用更通用的方法。</span><span class="sxs-lookup"><span data-stu-id="6d858-195">When I have a list of tokens that I need to replace, I take a more generic approach.</span></span> <span data-ttu-id="6d858-196">我会将其放在哈希表中，然后循环访问它们来进行替换。</span><span class="sxs-lookup"><span data-stu-id="6d858-196">I would place them in a hashtable and iterate over them to do the replace.</span></span>

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

<span data-ttu-id="6d858-197">如果需要，可以从 JSON 或 CSV 加载这些标记。</span><span class="sxs-lookup"><span data-stu-id="6d858-197">Those tokens could be loaded from JSON or CSV if needed.</span></span>

### <a name="executioncontext-expandstring"></a><span data-ttu-id="6d858-198">ExecutionContext ExpandString</span><span class="sxs-lookup"><span data-stu-id="6d858-198">ExecutionContext ExpandString</span></span>

<span data-ttu-id="6d858-199">有一种巧妙的方法可以使用单引号定义替换字符串，之后再展开变量。</span><span class="sxs-lookup"><span data-stu-id="6d858-199">There's a clever way to define a substitution string with single quotes and expand the variables later.</span></span> <span data-ttu-id="6d858-200">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="6d858-200">Look at this example:</span></span>

```powershell
$message = 'Hello, $Name!'
$name = 'Kevin Marquette'
$string = $ExecutionContext.InvokeCommand.ExpandString($message)
```

<span data-ttu-id="6d858-201">对当前执行上下文的 `.InvokeCommand.ExpandString` 调用使用了当前作用域内的变量进行替换。</span><span class="sxs-lookup"><span data-stu-id="6d858-201">The call to `.InvokeCommand.ExpandString` on the current execution context uses the variables in the current scope for substitution.</span></span> <span data-ttu-id="6d858-202">此处的关键在于，可以在变量存在之前尽早定义 `$message`。</span><span class="sxs-lookup"><span data-stu-id="6d858-202">The key thing here is that the `$message` can be defined very early before the variables even exist.</span></span>

<span data-ttu-id="6d858-203">如果我们再展开一点点，就可以使用不同的值反复执行此替换。</span><span class="sxs-lookup"><span data-stu-id="6d858-203">If we expand on that just a little bit, we can perform this substitution over and over wih different values.</span></span>

```powershell
$message = 'Hello, $Name!'
$nameList = 'Mark Kraus','Kevin Marquette','Lee Dailey'
foreach($name in $nameList){
    $ExecutionContext.InvokeCommand.ExpandString($message)
}
```

<span data-ttu-id="6d858-204">若要继续实践这一想法，你可以从文本文件导入大型电子邮件模板来实现。</span><span class="sxs-lookup"><span data-stu-id="6d858-204">To keep going on this idea; you could be importing a large email template from a text file to do this.</span></span> <span data-ttu-id="6d858-205">我要感谢 [Mark Kraus][] 提供此[建议][]</span><span class="sxs-lookup"><span data-stu-id="6d858-205">I have to thank [Mark Kraus][] for this [suggestion][].</span></span>

## <a name="whatever-works-the-best-for-you"></a><span data-ttu-id="6d858-206">只要适合你就好</span><span class="sxs-lookup"><span data-stu-id="6d858-206">Whatever works the best for you</span></span>

<span data-ttu-id="6d858-207">我是格式字符串方法的爱好者。</span><span class="sxs-lookup"><span data-stu-id="6d858-207">I'm a fan of the format string approach.</span></span> <span data-ttu-id="6d858-208">对于更复杂的字符串，或者如果有多个变量，我肯定会这样做。</span><span class="sxs-lookup"><span data-stu-id="6d858-208">I definitely do this with the more complicated strings or if there are multiple variables.</span></span> <span data-ttu-id="6d858-209">对于非常短的内容，我可以使用上述方法中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="6d858-209">On anything that is very short, I may use any one of these.</span></span>

## <a name="anything-else"></a><span data-ttu-id="6d858-210">任何其他内容？</span><span class="sxs-lookup"><span data-stu-id="6d858-210">Anything else?</span></span>

<span data-ttu-id="6d858-211">就这个主题我已经介绍了很多内容。</span><span class="sxs-lookup"><span data-stu-id="6d858-211">I covered a lot of ground on this one.</span></span> <span data-ttu-id="6d858-212">希望你能学习到一些新知识。</span><span class="sxs-lookup"><span data-stu-id="6d858-212">My hope is that you walk away learning something new.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[original version]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Mark Kraus]: https://get-powershellblog.blogspot.com/
[建议]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[suggestion]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[/u/real_parbold]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfm6p/
[读取和保存到文件]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[reading and saving to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[记录]: /dotnet/api/system.string.format#overloads
[documented]: /dotnet/api/system.string.format#overloads
