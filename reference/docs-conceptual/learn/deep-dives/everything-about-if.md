---
title: 关于 IF 语句的各项须知内容
description: 与许多其他语言一样，PowerShell 提供了用于在脚本中有条件地执行代码的语句。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 6ffb70af694e80430d31991045b9fadc1a2cc3f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149520"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a><span data-ttu-id="aa403-103">关于 IF 语句的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="aa403-103">Everything you wanted to know about the IF statement</span></span>

<span data-ttu-id="aa403-104">与许多其他语言一样，PowerShell 提供了用于在脚本中有条件地执行代码的语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-104">Like many other languages, PowerShell has statements for conditionally executing code in your scripts.</span></span> <span data-ttu-id="aa403-105">其中一个语句是 [if][] 语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-105">One of those statements is the [if][] statement.</span></span> <span data-ttu-id="aa403-106">今天，我们将深入探讨 PowerShell 中最基本的命令之一。</span><span class="sxs-lookup"><span data-stu-id="aa403-106">Today we will take a deep dive into one of the most fundamental commands in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="aa403-107">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="aa403-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="aa403-108">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="aa403-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="aa403-109">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="aa403-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="conditional-execution"></a><span data-ttu-id="aa403-110">有条件执行</span><span class="sxs-lookup"><span data-stu-id="aa403-110">Conditional execution</span></span>

<span data-ttu-id="aa403-111">你的脚本通常需要做出决策，并根据这些决策执行不同的逻辑。</span><span class="sxs-lookup"><span data-stu-id="aa403-111">Your scripts often need to make decisions and perform different logic based on those decisions.</span></span>
<span data-ttu-id="aa403-112">这就是有条件执行的意思。</span><span class="sxs-lookup"><span data-stu-id="aa403-112">This is what I mean by conditional execution.</span></span> <span data-ttu-id="aa403-113">需要计算一个语句或值，然后根据该计算结果执行不同的代码段。</span><span class="sxs-lookup"><span data-stu-id="aa403-113">You have one statement or value to evaluate, then execute a different section of code based on that evaluation.</span></span> <span data-ttu-id="aa403-114">这正是 `if` 语句能够发挥作用的地方。</span><span class="sxs-lookup"><span data-stu-id="aa403-114">This is exactly what the `if` statement does.</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="aa403-115">if 语句</span><span class="sxs-lookup"><span data-stu-id="aa403-115">The if statement</span></span>

<span data-ttu-id="aa403-116">下面是 `if` 语句的基本示例：</span><span class="sxs-lookup"><span data-stu-id="aa403-116">Here is a basic example of the `if` statement:</span></span>

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

<span data-ttu-id="aa403-117">`if` 语句执行的第一步是计算括号中的表达式。</span><span class="sxs-lookup"><span data-stu-id="aa403-117">The first thing the `if` statement does is evaluate the expression in parentheses.</span></span> <span data-ttu-id="aa403-118">如果计算结果为 `$true`，则执行大括号中的 `scriptblock`。</span><span class="sxs-lookup"><span data-stu-id="aa403-118">If it evaluates to `$true`, then it executes the `scriptblock` in the braces.</span></span> <span data-ttu-id="aa403-119">如果值为 `$false`，则会跳过该脚本块。</span><span class="sxs-lookup"><span data-stu-id="aa403-119">If the value was `$false`, then it would skip over that scriptblock.</span></span>

<span data-ttu-id="aa403-120">在上面的示例中，`if` 语句仅计算 `$condition` 变量。</span><span class="sxs-lookup"><span data-stu-id="aa403-120">In the previous example, the `if` statement was just evaluating the `$condition` variable.</span></span> <span data-ttu-id="aa403-121">其计算结果为 `$true`，将在脚本块内执行 `Write-Output` 命令。</span><span class="sxs-lookup"><span data-stu-id="aa403-121">It was `$true` and would have executed the `Write-Output` command inside the scriptblock.</span></span>

<span data-ttu-id="aa403-122">在某些语言中，可以在 `if` 语句后放置一行代码，并执行该语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-122">In some languages, you can place a single line of code after the `if` statement and it gets executed.</span></span> <span data-ttu-id="aa403-123">在 PowerShell 中情况并非如此。</span><span class="sxs-lookup"><span data-stu-id="aa403-123">That isn't the case in PowerShell.</span></span> <span data-ttu-id="aa403-124">必须提供带大括号的完整 `scriptblock` 才能使其正常工作。</span><span class="sxs-lookup"><span data-stu-id="aa403-124">You must provide a full `scriptblock` with braces for it to work correctly.</span></span>

## <a name="comparison-operators"></a><span data-ttu-id="aa403-125">比较运算符</span><span class="sxs-lookup"><span data-stu-id="aa403-125">Comparison operators</span></span>

<span data-ttu-id="aa403-126">`if` 语句最常见的用法是比较两个项。</span><span class="sxs-lookup"><span data-stu-id="aa403-126">The most common use of the `if` statement for is comparing two items with each other.</span></span> <span data-ttu-id="aa403-127">PowerShell 具有特殊运算符，可用于不同比较方案。</span><span class="sxs-lookup"><span data-stu-id="aa403-127">PowerShell has special operators for different comparison scenarios.</span></span> <span data-ttu-id="aa403-128">当使用比较运算符时，会将左右两侧的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="aa403-128">When you use a comparison operator, the value on the left-hand side is compared to the value on the right-hand side.</span></span>

### <a name="-eq-for-equality"></a><span data-ttu-id="aa403-129">-eq（相等）</span><span class="sxs-lookup"><span data-stu-id="aa403-129">-eq for equality</span></span>

<span data-ttu-id="aa403-130">`-eq` 在两个值之间执行相等检查，以确保它们彼此相等。</span><span class="sxs-lookup"><span data-stu-id="aa403-130">The `-eq` does an equality check between two values to make sure they're equal to each other.</span></span>

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

<span data-ttu-id="aa403-131">在此示例中，我采用已知值 `5`，并将其与 `$value` 进行比较，以确定它们是否匹配。</span><span class="sxs-lookup"><span data-stu-id="aa403-131">In this example, I'm taking a known value of `5` and comparing it to my `$value` to see if they match.</span></span>

<span data-ttu-id="aa403-132">一个可能的用例是在对值执行操作之前检查值的状态。</span><span class="sxs-lookup"><span data-stu-id="aa403-132">One possible use case is to check the status of a value before you take an action on it.</span></span> <span data-ttu-id="aa403-133">你可以获得一种服务，并检查状态是否正在运行，然后再对其调用 `Restart-Service`。</span><span class="sxs-lookup"><span data-stu-id="aa403-133">You could get a service and check that the status was running before you called `Restart-Service` on it.</span></span>

<span data-ttu-id="aa403-134">在其他语言（如 C#）中，通常使用 `==` 检查是否相等（例如：`5 == $value`），但此方法不适用于 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="aa403-134">It's common in other languages like C# to use `==` for equality (ex: `5 == $value`) but that doesn't work with PowerShell.</span></span> <span data-ttu-id="aa403-135">人们常犯的另一种错误是保留等号（例如：`5 = $value`）来为变量赋值。</span><span class="sxs-lookup"><span data-stu-id="aa403-135">Another common mistake that people make is to use the equals sign (ex: `5 = $value`) that is reserved for assigning values to variables.</span></span> <span data-ttu-id="aa403-136">将已知值放在左侧会让这个错误变得更尴尬。</span><span class="sxs-lookup"><span data-stu-id="aa403-136">By placing your known value on the left, it makes that mistaken more awkward to make.</span></span>

<span data-ttu-id="aa403-137">此运算符（以及其他运算符）具有几个变体。</span><span class="sxs-lookup"><span data-stu-id="aa403-137">This operator (and others) has a few variations.</span></span>

- <span data-ttu-id="aa403-138">`-eq` 不区分大小写相等</span><span class="sxs-lookup"><span data-stu-id="aa403-138">`-eq` case-insensitive equality</span></span>
- <span data-ttu-id="aa403-139">`-ieq` 不区分大小写相等</span><span class="sxs-lookup"><span data-stu-id="aa403-139">`-ieq` case-insensitive equality</span></span>
- <span data-ttu-id="aa403-140">`-ceq` 区分大小写相等</span><span class="sxs-lookup"><span data-stu-id="aa403-140">`-ceq` case-sensitive equality</span></span>

### <a name="-ne-not-equal"></a><span data-ttu-id="aa403-141">-ne（不等于）</span><span class="sxs-lookup"><span data-stu-id="aa403-141">-ne not equal</span></span>

<span data-ttu-id="aa403-142">许多运算符都有一个相关的运算符，用于检查相反的结果。</span><span class="sxs-lookup"><span data-stu-id="aa403-142">Many operators have a related operator that is checking for the opposite result.</span></span> <span data-ttu-id="aa403-143">`-ne` 用于验证这些值是否相互不相等。</span><span class="sxs-lookup"><span data-stu-id="aa403-143">`-ne` verifies that the values don't equal each other.</span></span>

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

<span data-ttu-id="aa403-144">使用此方法可确保仅在值不等于 `5` 时才执行操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-144">Use this to make sure that the action only executes if the value isn't `5`.</span></span> <span data-ttu-id="aa403-145">一个很好的用例是，在尝试启动服务之前检查服务是否处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="aa403-145">A good use-cases where would be to check if a service was in the running state before you try to start it.</span></span>

<span data-ttu-id="aa403-146">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-146">**Variations:**</span></span>

- <span data-ttu-id="aa403-147">`-ne` 不区分大小写不等于</span><span class="sxs-lookup"><span data-stu-id="aa403-147">`-ne` case-insensitive not equal</span></span>
- <span data-ttu-id="aa403-148">`-ine` 不区分大小写不等于</span><span class="sxs-lookup"><span data-stu-id="aa403-148">`-ine` case-insensitive not equal</span></span>
- <span data-ttu-id="aa403-149">`-cne` 区分大小写不等于</span><span class="sxs-lookup"><span data-stu-id="aa403-149">`-cne` case-sensitive not equal</span></span>

<span data-ttu-id="aa403-150">这些是 `-eq` 的反向变体。</span><span class="sxs-lookup"><span data-stu-id="aa403-150">These are inverse variations of `-eq`.</span></span> <span data-ttu-id="aa403-151">当列出其他运算符的变体时，我将把这些类型组合在一起。</span><span class="sxs-lookup"><span data-stu-id="aa403-151">I'll group these types together when I list variations for other operators.</span></span>

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a><span data-ttu-id="aa403-152">-gt -ge -lt -le（大于或小于）</span><span class="sxs-lookup"><span data-stu-id="aa403-152">-gt -ge -lt -le for greater than or less than</span></span>

<span data-ttu-id="aa403-153">检查某个值是否大于或小于另一个值时，将使用这些运算符。</span><span class="sxs-lookup"><span data-stu-id="aa403-153">These operators are used when checking to see if a value is larger or smaller than another value.</span></span>
<span data-ttu-id="aa403-154">`-gt -ge -lt -le` 代表 GreaterThan、GreaterThanOrEqual、LessThan 和 LessThanOrEqual。</span><span class="sxs-lookup"><span data-stu-id="aa403-154">The `-gt -ge -lt -le` stand for GreaterThan, GreaterThanOrEqual, LessThan, and LessThanOrEqual.</span></span>

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

<span data-ttu-id="aa403-155">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-155">**Variations:**</span></span>

- <span data-ttu-id="aa403-156">`-gt` 大于</span><span class="sxs-lookup"><span data-stu-id="aa403-156">`-gt` greater than</span></span>
- <span data-ttu-id="aa403-157">`-igt` 大于（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-157">`-igt` greater than, case-insensitive</span></span>
- <span data-ttu-id="aa403-158">`-cgt` 大于（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-158">`-cgt` greater than, case-sensitive</span></span>
- <span data-ttu-id="aa403-159">`-ge` 大于或等于</span><span class="sxs-lookup"><span data-stu-id="aa403-159">`-ge` greater than or equal</span></span>
- <span data-ttu-id="aa403-160">`-ige` 大于或等于（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-160">`-ige` greater than or equal, case-insensitive</span></span>
- <span data-ttu-id="aa403-161">`-cge` 大于或等于（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-161">`-cge` greater than or equal, case-sensitive</span></span>
- <span data-ttu-id="aa403-162">`-lt` 小于</span><span class="sxs-lookup"><span data-stu-id="aa403-162">`-lt` less than</span></span>
- <span data-ttu-id="aa403-163">`-ilt` 小于（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-163">`-ilt` less than, case-insensitive</span></span>
- <span data-ttu-id="aa403-164">`-clt` 小于（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-164">`-clt` less than, case-sensitive</span></span>
- <span data-ttu-id="aa403-165">`-le` 小于或等于</span><span class="sxs-lookup"><span data-stu-id="aa403-165">`-le` less than or equal</span></span>
- <span data-ttu-id="aa403-166">`-ile` 小于或等于（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-166">`-ile` less than or equal, case-insensitive</span></span>
- <span data-ttu-id="aa403-167">`-cle` 小于或等于（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aa403-167">`-cle` less than or equal, case-sensitive</span></span>

<span data-ttu-id="aa403-168">我不知道为什么这些运算符要使用区分大小写和不区分大小写的选项。</span><span class="sxs-lookup"><span data-stu-id="aa403-168">I don't know why you would use case-sensitive and insensitive options for these operators.</span></span>

### <a name="-like-wildcard-matches"></a><span data-ttu-id="aa403-169">-like（通配符匹配）</span><span class="sxs-lookup"><span data-stu-id="aa403-169">-like wildcard matches</span></span>

<span data-ttu-id="aa403-170">PowerShell 具有其自己的通配符模式匹配语法，你可以将其与 `-like` 运算符一起使用。</span><span class="sxs-lookup"><span data-stu-id="aa403-170">PowerShell has its own wildcard-based pattern matching syntax and you can use it with the `-like` operator.</span></span> <span data-ttu-id="aa403-171">这些通配符模式都非常基本。</span><span class="sxs-lookup"><span data-stu-id="aa403-171">These wildcard patterns are fairly basic.</span></span>

- <span data-ttu-id="aa403-172">`?` 匹配任何单个字符</span><span class="sxs-lookup"><span data-stu-id="aa403-172">`?` matches any single character</span></span>
- <span data-ttu-id="aa403-173">`*` 匹配任意数量的字符</span><span class="sxs-lookup"><span data-stu-id="aa403-173">`*` matches any number of characters</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

<span data-ttu-id="aa403-174">必须指出该模式与整个字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="aa403-174">It's important to point out that the pattern matches the whole string.</span></span> <span data-ttu-id="aa403-175">如果需要匹配字符串中间的某些内容，则需要在字符串的两端放置 `*`。</span><span class="sxs-lookup"><span data-stu-id="aa403-175">If you need to match something in the middle of the string, you need to place the `*` on both ends of the string.</span></span>

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

<span data-ttu-id="aa403-176">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-176">**Variations:**</span></span>

- <span data-ttu-id="aa403-177">`-like` 不区分大小写通配符</span><span class="sxs-lookup"><span data-stu-id="aa403-177">`-like` case-insensitive wildcard</span></span>
- <span data-ttu-id="aa403-178">`-ilike` 不区分大小写通配符</span><span class="sxs-lookup"><span data-stu-id="aa403-178">`-ilike` case-insensitive wildcard</span></span>
- <span data-ttu-id="aa403-179">`-clike` 区分大小写通配符</span><span class="sxs-lookup"><span data-stu-id="aa403-179">`-clike` case-sensitive wildcard</span></span>
- <span data-ttu-id="aa403-180">`-notlike` 不区分大小写通配符不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-180">`-notlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="aa403-181">`-inotlike` 不区分大小写通配符不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-181">`-inotlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="aa403-182">`-cnotlike` 区分大小写通配符不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-182">`-cnotlike` case-sensitive wildcard not matched</span></span>

### <a name="-match-regular-expression"></a><span data-ttu-id="aa403-183">-match（正则表达式）</span><span class="sxs-lookup"><span data-stu-id="aa403-183">-match regular expression</span></span>

<span data-ttu-id="aa403-184">使用 `-match` 运算符可以检查字符串中是否有基于正则表达式的匹配项。</span><span class="sxs-lookup"><span data-stu-id="aa403-184">The `-match` operator allows you to check a string for a regular-expression-based match.</span></span> <span data-ttu-id="aa403-185">当你觉得通配符模式不够灵活时，请使用此模式。</span><span class="sxs-lookup"><span data-stu-id="aa403-185">Use this when the wildcard patterns aren't flexible enough for you.</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

<span data-ttu-id="aa403-186">默认情况下，正则表达式模式匹配字符串的任意位置。</span><span class="sxs-lookup"><span data-stu-id="aa403-186">A regex pattern matches anywhere in the string by default.</span></span> <span data-ttu-id="aa403-187">因此，你可以指定希望匹配的子字符串，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa403-187">So you can specify a substring that you want matched like this:</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

<span data-ttu-id="aa403-188">正则表达式是一种复杂的语言，值得研究。</span><span class="sxs-lookup"><span data-stu-id="aa403-188">Regex is a complex language of its own and worth looking into.</span></span> <span data-ttu-id="aa403-189">我在另一篇文章中详细介绍了 `-match` 和[使用正则表达式的多种方式][]。</span><span class="sxs-lookup"><span data-stu-id="aa403-189">I talk more about `-match` and [the many ways to use regex][] in another article.</span></span>

<span data-ttu-id="aa403-190">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-190">**Variations:**</span></span>

- <span data-ttu-id="aa403-191">`-match` 不区分大小写正则表达式</span><span class="sxs-lookup"><span data-stu-id="aa403-191">`-match` case-insensitive regex</span></span>
- <span data-ttu-id="aa403-192">`-imatch` 不区分大小写正则表达式</span><span class="sxs-lookup"><span data-stu-id="aa403-192">`-imatch` case-insensitive regex</span></span>
- <span data-ttu-id="aa403-193">`-cmatch` 区分大小写正则表达式</span><span class="sxs-lookup"><span data-stu-id="aa403-193">`-cmatch` case-sensitive regex</span></span>
- <span data-ttu-id="aa403-194">`-notmatch` 不区分大小写正则表达式不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-194">`-notmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="aa403-195">`-inotmatch` 不区分大小写正则表达式不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-195">`-inotmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="aa403-196">`-cnotmatch` 区分大小写正则表达式不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-196">`-cnotmatch` case-sensitive regex not matched</span></span>

### <a name="-is-of-type"></a><span data-ttu-id="aa403-197">-is（属于类型）</span><span class="sxs-lookup"><span data-stu-id="aa403-197">-is of type</span></span>

<span data-ttu-id="aa403-198">你可以使用 `-is` 运算符检查值的类型。</span><span class="sxs-lookup"><span data-stu-id="aa403-198">You can check a value's type with the `-is` operator.</span></span>

```powershell
if ( $value -is [string] )
{
    # do something
}
```

<span data-ttu-id="aa403-199">如果使用的是类或通过管道接受各种对象，则可以使用此项。</span><span class="sxs-lookup"><span data-stu-id="aa403-199">You may use this if you're working with classes or accepting various objects over the pipeline.</span></span> <span data-ttu-id="aa403-200">可以将服务或服务名称作为输入。</span><span class="sxs-lookup"><span data-stu-id="aa403-200">You could have either a service or a service name as your input.</span></span> <span data-ttu-id="aa403-201">然后，查看是否有服务并提取服务（如果只有名称）。</span><span class="sxs-lookup"><span data-stu-id="aa403-201">Then check to see if you have a service and fetch the service if you only have the name.</span></span>

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

<span data-ttu-id="aa403-202">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-202">**Variations:**</span></span>

- <span data-ttu-id="aa403-203">`-is` 属于类型</span><span class="sxs-lookup"><span data-stu-id="aa403-203">`-is` of type</span></span>
- <span data-ttu-id="aa403-204">`-isnot` 不属于类型</span><span class="sxs-lookup"><span data-stu-id="aa403-204">`-isnot` not of type</span></span>

## <a name="collection-operators"></a><span data-ttu-id="aa403-205">集合运算符</span><span class="sxs-lookup"><span data-stu-id="aa403-205">Collection operators</span></span>

<span data-ttu-id="aa403-206">对单个值使用前面的运算符时，结果为 `$true` 或 `$false`。</span><span class="sxs-lookup"><span data-stu-id="aa403-206">When you use the previous operators with a single value, the result is `$true` or `$false`.</span></span> <span data-ttu-id="aa403-207">处理集合时，处理方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="aa403-207">This is handled slightly differently when working with a collection.</span></span> <span data-ttu-id="aa403-208">集合中的每一项都将进行计算，运算符将返回计算结果为 `$true` 的每个值。</span><span class="sxs-lookup"><span data-stu-id="aa403-208">Each item in the collection gets evaluated and the operator returns every value that evaluates to `$true`.</span></span>

```powershell
PS> 1,2,3,4 -eq 3
3
```

<span data-ttu-id="aa403-209">这在 `if` 语句中仍能正常运行。</span><span class="sxs-lookup"><span data-stu-id="aa403-209">This still works correctly in a `if` statement.</span></span> <span data-ttu-id="aa403-210">因此运算符返回一个值，则整个语句为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-210">So a value is returned by your operator, then the whole statement is `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

<span data-ttu-id="aa403-211">我需要指出的是，此处的详细信息隐藏了一个小陷阱。以这种方式使用 `-ne` 运算符时，很容易错误地向后查看逻辑。</span><span class="sxs-lookup"><span data-stu-id="aa403-211">There's one small trap hiding in the details here that I need to point out. When using the `-ne` operator this way, it's easy to mistakenly look at the logic backwards.</span></span> <span data-ttu-id="aa403-212">如果集合中的任何项与你的值都不匹配，则对集合使用 `-ne` 将返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-212">Using `-ne` with a collection returns `$true` if any item in the collection doesn't match your value.</span></span>

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

<span data-ttu-id="aa403-213">这个花招看起来巧妙，但我们有运算符 `-contains` 和 `-in` 可以更高效地处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="aa403-213">This may look like a clever trick, but we have operators `-contains` and `-in` that handle this more efficiently.</span></span> <span data-ttu-id="aa403-214">并且 `-notcontains` 会执行你期望的操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-214">And `-notcontains` does what you expect.</span></span>

### <a name="-contains"></a><span data-ttu-id="aa403-215">-contains</span><span class="sxs-lookup"><span data-stu-id="aa403-215">-contains</span></span>

<span data-ttu-id="aa403-216">`-contains` 运算符会针对你的值检查集合。</span><span class="sxs-lookup"><span data-stu-id="aa403-216">The `-contains` operator checks the collection for your value.</span></span> <span data-ttu-id="aa403-217">找到匹配项后，将返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-217">As soon as it finds a match, it returns `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

<span data-ttu-id="aa403-218">这是查看集合是否包含你的值的首选方法。</span><span class="sxs-lookup"><span data-stu-id="aa403-218">This is the preferred way to see if a collection contains your value.</span></span> <span data-ttu-id="aa403-219">使用 `Where-Object`（或 `-eq`）时，每次都会遍历整个列表，且速度显著降低。</span><span class="sxs-lookup"><span data-stu-id="aa403-219">Using `Where-Object` (or `-eq`) walks the entire list every time and is significantly slower.</span></span>

<span data-ttu-id="aa403-220">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-220">**Variations:**</span></span>

- <span data-ttu-id="aa403-221">`-contains` 不区分大小写匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-221">`-contains` case-insensitive match</span></span>
- <span data-ttu-id="aa403-222">`-icontains` 不区分大小写匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-222">`-icontains` case-insensitive match</span></span>
- <span data-ttu-id="aa403-223">`-ccontains` 区分大小写匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-223">`-ccontains` case-sensitive match</span></span>
- <span data-ttu-id="aa403-224">`-notcontains` 不区分大小写不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-224">`-notcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="aa403-225">`-inotcontains` 不区分大小写不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-225">`-inotcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="aa403-226">`-cnotcontains` 区分大小写不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-226">`-cnotcontains` case-sensitive not matched</span></span>

### <a name="-in"></a><span data-ttu-id="aa403-227">-in</span><span class="sxs-lookup"><span data-stu-id="aa403-227">-in</span></span>

<span data-ttu-id="aa403-228">`-in` 运算符与 `-contains` 运算符类似，只是集合位于右侧。</span><span class="sxs-lookup"><span data-stu-id="aa403-228">The `-in` operator is just like the `-contains` operator except the collection is on the right-hand side.</span></span>

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

<span data-ttu-id="aa403-229">变体：</span><span class="sxs-lookup"><span data-stu-id="aa403-229">**Variations:**</span></span>

- <span data-ttu-id="aa403-230">`-in` 不区分大小写匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-230">`-in` case-insensitive match</span></span>
- <span data-ttu-id="aa403-231">`-iin` 不区分大小写匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-231">`-iin` case-insensitive match</span></span>
- <span data-ttu-id="aa403-232">`-cin` 区分大小写匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-232">`-cin` case-sensitive match</span></span>
- <span data-ttu-id="aa403-233">`-notin` 不区分大小写不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-233">`-notin` case-insensitive not matched</span></span>
- <span data-ttu-id="aa403-234">`-inotin` 不区分大小写不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-234">`-inotin` case-insensitive not matched</span></span>
- <span data-ttu-id="aa403-235">`-cnotin` 区分大小写不匹配</span><span class="sxs-lookup"><span data-stu-id="aa403-235">`-cnotin` case-sensitive not matched</span></span>

## <a name="logical-operators"></a><span data-ttu-id="aa403-236">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="aa403-236">Logical operators</span></span>

<span data-ttu-id="aa403-237">逻辑运算符用于反转或合并其他表达式。</span><span class="sxs-lookup"><span data-stu-id="aa403-237">Logical operators are used to invert or combine other expressions.</span></span>

### <a name="-not"></a><span data-ttu-id="aa403-238">-not</span><span class="sxs-lookup"><span data-stu-id="aa403-238">-not</span></span>

<span data-ttu-id="aa403-239">`-not` 运算符将表达式从 `$false` 翻转到 `$true` 或从 `$true` 翻转到 `$false`。</span><span class="sxs-lookup"><span data-stu-id="aa403-239">The `-not` operator flips an expression from `$false` to `$true` or from `$true` to `$false`.</span></span> <span data-ttu-id="aa403-240">下面是一个示例，我们希望在 `Test-Path` 为 `$false` 时执行操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-240">Here is an example where we want to perform an action when `Test-Path` is `$false`.</span></span>

```powershell
if ( -not ( Test-Path -Path $path ) )
```

<span data-ttu-id="aa403-241">我们讨论的大多数运算符都有一种变体，你在其中无需使用 `-not` 运算符。</span><span class="sxs-lookup"><span data-stu-id="aa403-241">Most of the operators we talked about do have a variation where you do not need to use the `-not` operator.</span></span> <span data-ttu-id="aa403-242">但它还是有用武之地。</span><span class="sxs-lookup"><span data-stu-id="aa403-242">But there are still times it is useful.</span></span>

### <a name="-operator"></a><span data-ttu-id="aa403-243">!</span><span class="sxs-lookup"><span data-stu-id="aa403-243">!</span></span> <span data-ttu-id="aa403-244">运算符后的表达式</span><span class="sxs-lookup"><span data-stu-id="aa403-244">operator</span></span>

<span data-ttu-id="aa403-245">你可以使用 `!` 作为 `-not` 的别名。</span><span class="sxs-lookup"><span data-stu-id="aa403-245">You can use `!` as an alias for `-not`.</span></span>

```powershell
if ( -not $value ){}
if ( !$value ){}
```

<span data-ttu-id="aa403-246">你可能会发现其他语言（如 C#）的用户更多地使用 `!`。</span><span class="sxs-lookup"><span data-stu-id="aa403-246">You may see `!` used more by people that come from another languages like C#.</span></span> <span data-ttu-id="aa403-247">我更喜欢把它打出来，因为我发现在快速查看脚本时很难看清。</span><span class="sxs-lookup"><span data-stu-id="aa403-247">I prefer to type it out because I find it hard to see when quickly looking at my scripts.</span></span>

### <a name="-and"></a><span data-ttu-id="aa403-248">-and</span><span class="sxs-lookup"><span data-stu-id="aa403-248">-and</span></span>

<span data-ttu-id="aa403-249">可以将表达式与 `-and` 运算符组合在一起。</span><span class="sxs-lookup"><span data-stu-id="aa403-249">You can combine expressions with the `-and` operator.</span></span> <span data-ttu-id="aa403-250">当你这样做时，两侧都应为 `$true`，这样整个表达式才能为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-250">When you do that, both sides need to be `$true` for the whole expression to be `$true`.</span></span>

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

<span data-ttu-id="aa403-251">在此示例中，左侧的 `$age` 必须为 13 或更大，右侧必须小于 55。</span><span class="sxs-lookup"><span data-stu-id="aa403-251">In that example, `$age` must be 13 or older for the left side and less than 55 for the right side.</span></span> <span data-ttu-id="aa403-252">我添加了额外的括号以使其更清晰，但只要表达式简单，它们就是可选的。</span><span class="sxs-lookup"><span data-stu-id="aa403-252">I added extra parentheses to make it clearer in that example but they're optional as long as the expression is simple.</span></span> <span data-ttu-id="aa403-253">下面是同一个示例不使用括号的情况。</span><span class="sxs-lookup"><span data-stu-id="aa403-253">Here is the same example without them.</span></span>

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

<span data-ttu-id="aa403-254">计算从左到右进行。</span><span class="sxs-lookup"><span data-stu-id="aa403-254">Evaluation happens from left to right.</span></span> <span data-ttu-id="aa403-255">如果第一项的计算结果为 `$false`，它将提前退出，并且不会执行正确的比较。</span><span class="sxs-lookup"><span data-stu-id="aa403-255">If the first item evaluates to `$false`, it exits early and doesn't perform the right comparison.</span></span> <span data-ttu-id="aa403-256">如果你在使用值之前需要确保该值存在，这非常方便。</span><span class="sxs-lookup"><span data-stu-id="aa403-256">This is handy when you need to make sure a value exists before you use it.</span></span> <span data-ttu-id="aa403-257">例如，如果为 `Test-Path` 提供 `$null` 路径，则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="aa403-257">For example, `Test-Path` throws an error if you give it a `$null` path.</span></span>

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a><span data-ttu-id="aa403-258">-or</span><span class="sxs-lookup"><span data-stu-id="aa403-258">-or</span></span>

<span data-ttu-id="aa403-259">`-or` 允许指定两个表达式，并在其中一个表达式为 `$true` 时返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-259">The `-or` allows for you to specify two expressions and returns `$true` if either one of them is `$true`.</span></span>

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

<span data-ttu-id="aa403-260">与 `-and` 运算符一样，计算从左到右进行。</span><span class="sxs-lookup"><span data-stu-id="aa403-260">Just like with the `-and` operator, the evaluation happens from left to right.</span></span> <span data-ttu-id="aa403-261">例外情况是如果第一部分为 `$true`，则整个语句为 `$true`，且其不会处理表达式的其余部分。</span><span class="sxs-lookup"><span data-stu-id="aa403-261">Except that if the first part is `$true`, then the whole statement is `$true` and it doesn't process the rest of the expression.</span></span>

<span data-ttu-id="aa403-262">另外，请注意语法如何应用于这些运算符。</span><span class="sxs-lookup"><span data-stu-id="aa403-262">Also make note of how the syntax works for these operators.</span></span> <span data-ttu-id="aa403-263">需要两个单独的表达式。</span><span class="sxs-lookup"><span data-stu-id="aa403-263">You need two separate expressions.</span></span> <span data-ttu-id="aa403-264">我发现用户尝试执行类似于此 `$value -eq 5 -or 6` 的操作，但没有意识到他们的错误。</span><span class="sxs-lookup"><span data-stu-id="aa403-264">I have seen users try to do something like this `$value -eq 5 -or 6` without realizing their mistake.</span></span>

### <a name="-xor-exclusive-or"></a><span data-ttu-id="aa403-265">-xor 异或</span><span class="sxs-lookup"><span data-stu-id="aa403-265">-xor exclusive or</span></span>

<span data-ttu-id="aa403-266">这个运算符有点不寻常。</span><span class="sxs-lookup"><span data-stu-id="aa403-266">This one is a little unusual.</span></span> <span data-ttu-id="aa403-267">`-xor` 仅允许一个表达式的计算结果为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-267">`-xor` allows only one expression to evaluate to `$true`.</span></span> <span data-ttu-id="aa403-268">因此，如果两个项均为 `$false` 或者均为 `$true`，则整个表达式为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="aa403-268">So if both items are `$false` or both items are `$true`, then the whole expression is `$false`.</span></span> <span data-ttu-id="aa403-269">另一种了解此运算符的方法是，仅当表达式的结果不同时，表达式才为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="aa403-269">Another way to look at this is the expression is only `$true` when the results of the expression are different.</span></span>

<span data-ttu-id="aa403-270">很少有人会使用此逻辑运算符，我也举不出一个好的使用示例。</span><span class="sxs-lookup"><span data-stu-id="aa403-270">It's rare that anyone would ever use this logical operator and I can't think up a good example as to why I would ever use it.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="aa403-271">位运算符</span><span class="sxs-lookup"><span data-stu-id="aa403-271">Bitwise operators</span></span>

<span data-ttu-id="aa403-272">位运算符会对值中的位执行计算，并生成一个新值作为结果。</span><span class="sxs-lookup"><span data-stu-id="aa403-272">Bitwise operators perform calculations on the bits within the values and produce a new value as the result.</span></span> <span data-ttu-id="aa403-273">讲授[位运算符][]超出了本文的范围，下面仅列出这些运算符。</span><span class="sxs-lookup"><span data-stu-id="aa403-273">Teaching [bitwise operators][] is beyond the scope of this article, but here is the list the them.</span></span>

- <span data-ttu-id="aa403-274">`-band` 二进制和</span><span class="sxs-lookup"><span data-stu-id="aa403-274">`-band` binary AND</span></span>
- <span data-ttu-id="aa403-275">`-bor` 二进制或</span><span class="sxs-lookup"><span data-stu-id="aa403-275">`-bor` binary OR</span></span>
- <span data-ttu-id="aa403-276">`-bxor` 二进制异或</span><span class="sxs-lookup"><span data-stu-id="aa403-276">`-bxor` binary exclusive OR</span></span>
- <span data-ttu-id="aa403-277">`-bnot` 二进制非</span><span class="sxs-lookup"><span data-stu-id="aa403-277">`-bnot` binary NOT</span></span>
- <span data-ttu-id="aa403-278">`-shl` 左移</span><span class="sxs-lookup"><span data-stu-id="aa403-278">`-shl` shift left</span></span>
- <span data-ttu-id="aa403-279">`-shr` 右移</span><span class="sxs-lookup"><span data-stu-id="aa403-279">`-shr` shift right</span></span>

## <a name="powershell-expressions"></a><span data-ttu-id="aa403-280">PowerShell 表达式</span><span class="sxs-lookup"><span data-stu-id="aa403-280">PowerShell expressions</span></span>

<span data-ttu-id="aa403-281">可以在条件语句中使用常规 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="aa403-281">We can use normal PowerShell inside the condition statement.</span></span>

```powershell
if ( Test-Path -Path $Path )
```

<span data-ttu-id="aa403-282">执行 `Test-Path` 时返回 `$true` 或 `$false`。</span><span class="sxs-lookup"><span data-stu-id="aa403-282">`Test-Path` returns `$true` or `$false` when it executes.</span></span> <span data-ttu-id="aa403-283">这也适用于返回其他值的命令。</span><span class="sxs-lookup"><span data-stu-id="aa403-283">This also applies to commands that return other values.</span></span>

```powershell
if ( Get-Process Notepad* )
```

<span data-ttu-id="aa403-284">其计算结果为 `$true`（如果有返回的进程）和 `$false`（如果不返回任何结果）。</span><span class="sxs-lookup"><span data-stu-id="aa403-284">It evaluates to `$true` if there's a returned process and `$false` if there'sn'thing.</span></span> <span data-ttu-id="aa403-285">使用管道表达式或其他 PowerShell 语句非常有效，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa403-285">It's perfectly valid to use pipeline expressions or other PowerShell statements like this:</span></span>

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

<span data-ttu-id="aa403-286">这些表达式可以与 `-and` 和 `-or` 运算符相互组合在一起，但你可能必须使用括号将它们拆分为子表达式。</span><span class="sxs-lookup"><span data-stu-id="aa403-286">These expressions can be combined with each other with the `-and` and `-or` operators, but you may have to use parenthesis to break them into subexpressions.</span></span>

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a><span data-ttu-id="aa403-287">检查 $null</span><span class="sxs-lookup"><span data-stu-id="aa403-287">Checking for $null</span></span>

<span data-ttu-id="aa403-288">在 `if` 语句中，如果没有结果或 `$null` 值的计算结果为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="aa403-288">Having a no result or a `$null` value evaluates to `$false` in the `if` statement.</span></span> <span data-ttu-id="aa403-289">专门检查 `$null` 时，最佳做法是将 `$null` 放在左侧。</span><span class="sxs-lookup"><span data-stu-id="aa403-289">When checking specifically for `$null`, it's a best practice to place the `$null` on the left-hand side.</span></span>

```powershell
if ( $null -eq $value )
```

<span data-ttu-id="aa403-290">在 PowerShell 中处理 `$null` 值时，有很多细微差别。</span><span class="sxs-lookup"><span data-stu-id="aa403-290">There are quite a few nuances when dealing with `$null` values in PowerShell.</span></span> <span data-ttu-id="aa403-291">如果你有兴趣深入研究，请参阅我写的一篇相关文章：[关于 $null 的各项须知内容][]。</span><span class="sxs-lookup"><span data-stu-id="aa403-291">If you're interested in diving deeper, I have an article about [everything you wanted to know about $null][].</span></span>

### <a name="variable-assignment"></a><span data-ttu-id="aa403-292">变量赋值</span><span class="sxs-lookup"><span data-stu-id="aa403-292">Variable assignment</span></span>

<span data-ttu-id="aa403-293">幸亏 [Prasoon Karunan V][] 提醒我，我差点忘了添加这一内容。</span><span class="sxs-lookup"><span data-stu-id="aa403-293">I almost forgot to add this one until [Prasoon Karunan V][] reminded me of it.</span></span>

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

<span data-ttu-id="aa403-294">通常，在为变量赋值时，该值不会传递到管道或控制台。</span><span class="sxs-lookup"><span data-stu-id="aa403-294">Normally when you assign a value to a variable, the value isn't passed onto the pipeline or console.</span></span> <span data-ttu-id="aa403-295">在子表达式中执行变量赋值时，它会传递到管道。</span><span class="sxs-lookup"><span data-stu-id="aa403-295">When you do a variable assignment in a sub expression, it does get passed on to the pipeline.</span></span>

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

<span data-ttu-id="aa403-296">了解 `$first` 赋值是否没有输出，`$second` 赋值是否有输出？</span><span class="sxs-lookup"><span data-stu-id="aa403-296">See how the `$first` assignment has no output and the `$second` assignment does?</span></span> <span data-ttu-id="aa403-297">当在 `if` 语句中完成赋值时，它的执行方式就像上述 `$second` 赋值一样。</span><span class="sxs-lookup"><span data-stu-id="aa403-297">When an assignment is done in an `if` statement, it executes just like the `$second` assignment above.</span></span> <span data-ttu-id="aa403-298">下面一个关于其使用方式的简单示例：</span><span class="sxs-lookup"><span data-stu-id="aa403-298">Here is a clean example on how you could use it:</span></span>

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

<span data-ttu-id="aa403-299">如果为 `$process` 赋值，则语句为 `$true` 且 `$process` 将停止。</span><span class="sxs-lookup"><span data-stu-id="aa403-299">If `$process` gets assigned a value, then the statement is `$true` and `$process` gets stopped.</span></span>

<span data-ttu-id="aa403-300">请确保不要将这种情况与 `-eq` 混淆，因为这不是相等检查。</span><span class="sxs-lookup"><span data-stu-id="aa403-300">Make sure you don't confuse this with `-eq` because this isn't an equality check.</span></span> <span data-ttu-id="aa403-301">这是一项更为隐蔽的功能，大多数人不会以这种方式实现此功能。</span><span class="sxs-lookup"><span data-stu-id="aa403-301">This is a more obscure feature that most people don't realize works this way.</span></span>

## <a name="alternate-execution-path"></a><span data-ttu-id="aa403-302">替代执行路径</span><span class="sxs-lookup"><span data-stu-id="aa403-302">Alternate execution path</span></span>

<span data-ttu-id="aa403-303">使用 `if` 语句，可以在语句为 `$true` 和 `$false` 时指定操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-303">The `if` statement allows you to specify an action for not only when the statement is `$true`, but also for when it's `$false`.</span></span> <span data-ttu-id="aa403-304">这就是 `else` 语句的用武之地。</span><span class="sxs-lookup"><span data-stu-id="aa403-304">This is where the `else` statement comes into play.</span></span>

### <a name="else"></a><span data-ttu-id="aa403-305">else</span><span class="sxs-lookup"><span data-stu-id="aa403-305">else</span></span>

<span data-ttu-id="aa403-306">使用时，`else` 语句始终是 `if` 语句的最后一部分。</span><span class="sxs-lookup"><span data-stu-id="aa403-306">The `else` statement is always the last part of the `if` statement when used.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

<span data-ttu-id="aa403-307">在此示例中，我们将检查 `$path`，确保它是一个文件。</span><span class="sxs-lookup"><span data-stu-id="aa403-307">In this example, we check the `$path` to make sure it's a file.</span></span> <span data-ttu-id="aa403-308">如果找到该文件，则将其移动。</span><span class="sxs-lookup"><span data-stu-id="aa403-308">If we find the file, we move it.</span></span> <span data-ttu-id="aa403-309">如果未找到，我们会编写一个警告。</span><span class="sxs-lookup"><span data-stu-id="aa403-309">If not, we write a warning.</span></span> <span data-ttu-id="aa403-310">这种类型的分支逻辑非常常见。</span><span class="sxs-lookup"><span data-stu-id="aa403-310">This type of branching logic is very common.</span></span>

### <a name="nested-if"></a><span data-ttu-id="aa403-311">嵌套 if</span><span class="sxs-lookup"><span data-stu-id="aa403-311">Nested if</span></span>

<span data-ttu-id="aa403-312">`if` 和 `else` 语句采用脚本块，因此可以将任何 PowerShell 命令放入其中，包括另一个 `if` 语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-312">The `if` and `else` statements take a script block, so we can place any PowerShell command inside them, including another `if` statement.</span></span> <span data-ttu-id="aa403-313">这使你可以使用更复杂的逻辑。</span><span class="sxs-lookup"><span data-stu-id="aa403-313">This allows you to make use of much more complicated logic.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

<span data-ttu-id="aa403-314">在此示例中，我们首先测试愉快路径，然后对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-314">In this example, we test the happy path first and then take action on it.</span></span> <span data-ttu-id="aa403-315">如果失败，我们会进行另一个检查，并为用户提供更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="aa403-315">If that fails, we do another check and to provide more detailed information to the user.</span></span>

### <a name="elseif"></a><span data-ttu-id="aa403-316">elseif</span><span class="sxs-lookup"><span data-stu-id="aa403-316">elseif</span></span>

<span data-ttu-id="aa403-317">我们不仅限于单个条件检查。</span><span class="sxs-lookup"><span data-stu-id="aa403-317">We aren't limited to just a single conditional check.</span></span> <span data-ttu-id="aa403-318">我们可以将 `if` 和 `else` 语句链接在一起，而不是使用 `elseif` 语句来嵌套它们。</span><span class="sxs-lookup"><span data-stu-id="aa403-318">We can chain `if` and `else` statements together instead of nesting them by using the `elseif` statement.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

<span data-ttu-id="aa403-319">执行按自上而下的顺序进行。</span><span class="sxs-lookup"><span data-stu-id="aa403-319">The execution happens from the top to the bottom.</span></span> <span data-ttu-id="aa403-320">首先计算顶级 `if` 语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-320">The top `if` statement is evaluated first.</span></span> <span data-ttu-id="aa403-321">如果为 `$false`，则会向下移动到列表中的下一个 `elseif` 或 `else`。</span><span class="sxs-lookup"><span data-stu-id="aa403-321">If that is `$false`, then it moves down to the next `elseif` or `else` in the list.</span></span> <span data-ttu-id="aa403-322">最后一个 `else` 是在其他任何语句未返回 `$true` 时要执行的默认操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-322">That last `else` is the default action to take if none of the others return `$true`.</span></span>

### <a name="switch"></a><span data-ttu-id="aa403-323">开关</span><span class="sxs-lookup"><span data-stu-id="aa403-323">switch</span></span>

<span data-ttu-id="aa403-324">现在，我要提到 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-324">At this point, I need to mention the `switch` statement.</span></span> <span data-ttu-id="aa403-325">它提供了一个替代语法，用于对值执行多个比较。</span><span class="sxs-lookup"><span data-stu-id="aa403-325">It provides an alternate syntax for doing multiple comparisons with a value.</span></span> <span data-ttu-id="aa403-326">使用 `switch`，你可以指定表达式，并将结果与多个不同值进行比较。</span><span class="sxs-lookup"><span data-stu-id="aa403-326">With the `switch`, you specify an expression and that result gets compared with several different values.</span></span> <span data-ttu-id="aa403-327">如果其中一个值匹配，则执行匹配的代码块。</span><span class="sxs-lookup"><span data-stu-id="aa403-327">If one of those values match, the matching code block is executed.</span></span> <span data-ttu-id="aa403-328">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="aa403-328">Take a look at this example:</span></span>

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

<span data-ttu-id="aa403-329">有三个可能的值可与 `$itemType` 匹配。</span><span class="sxs-lookup"><span data-stu-id="aa403-329">There three possible values that can match the `$itemType`.</span></span> <span data-ttu-id="aa403-330">在这种情况下，它与 `Role` 匹配。</span><span class="sxs-lookup"><span data-stu-id="aa403-330">In this case, it matches with `Role`.</span></span> <span data-ttu-id="aa403-331">我使用了一个简单的示例来向你介绍 `switch` 运算符。</span><span class="sxs-lookup"><span data-stu-id="aa403-331">I used a simple example just to give you some exposure to the `switch` operator.</span></span> <span data-ttu-id="aa403-332">我在另一篇文章[关于 switch 语句的各项须知内容][]中介绍了更多内容。</span><span class="sxs-lookup"><span data-stu-id="aa403-332">I talk more about [everything you ever wanted to know about the switch statement][] in another article.</span></span>

## <a name="pipeline"></a><span data-ttu-id="aa403-333">管道</span><span class="sxs-lookup"><span data-stu-id="aa403-333">Pipeline</span></span>

<span data-ttu-id="aa403-334">管道是 PowerShell 一项独特的重要功能。</span><span class="sxs-lookup"><span data-stu-id="aa403-334">The pipeline is a unique and important feature of PowerShell.</span></span> <span data-ttu-id="aa403-335">未禁止或赋给变量的任何值都将放在管道中。</span><span class="sxs-lookup"><span data-stu-id="aa403-335">Any value that isn't suppressed or assigned to a variable gets placed in the pipeline.</span></span> <span data-ttu-id="aa403-336">`if` 以一种不总是显而易见的方式为我们提供了一种利用管道的方法。</span><span class="sxs-lookup"><span data-stu-id="aa403-336">The `if` provides us a way to take advantage of the pipeline in a way that isn't always obvious.</span></span>

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

<span data-ttu-id="aa403-337">每个脚本块将结果、命令或值放入管道。</span><span class="sxs-lookup"><span data-stu-id="aa403-337">Each script block is placing the results the commands or the value into the pipeline.</span></span> <span data-ttu-id="aa403-338">然后，将 if 语句的结果赋给 `$discount` 变量。</span><span class="sxs-lookup"><span data-stu-id="aa403-338">Then we assign the result of the if statement to the `$discount` variable.</span></span> <span data-ttu-id="aa403-339">该示例可以在每个脚本块中直接将这些值赋给 `$discount` 变量。</span><span class="sxs-lookup"><span data-stu-id="aa403-339">That example could have just as easily assigned those values to the `$discount` variable directly in each scriptblock.</span></span> <span data-ttu-id="aa403-340">我不能说我经常将此方法与 `if` 语句一起使用，但我确实有一个最近使用的例子。</span><span class="sxs-lookup"><span data-stu-id="aa403-340">I can't say that I use this with the `if` statement often, but I do have an example where I used this recently.</span></span>

### <a name="array-inline"></a><span data-ttu-id="aa403-341">数组内联</span><span class="sxs-lookup"><span data-stu-id="aa403-341">Array inline</span></span>

<span data-ttu-id="aa403-342">我有一个名为 [Invoke-SnowSql][] 的函数，该函数使用几个命令行参数启动可执行文件。</span><span class="sxs-lookup"><span data-stu-id="aa403-342">I have a function called [Invoke-SnowSql][] that launches an executable with several command-line arguments.</span></span> <span data-ttu-id="aa403-343">下面是此函数中的一个片段，可在其中生成参数数组。</span><span class="sxs-lookup"><span data-stu-id="aa403-343">Here is a clip from that function where I build the array of arguments.</span></span>

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

<span data-ttu-id="aa403-344">`$Debug` 和 `$Path` 变量是由最终用户提供的函数的参数。</span><span class="sxs-lookup"><span data-stu-id="aa403-344">The `$Debug` and `$Path` variables are parameters on the function that are provided by the end user.</span></span>
<span data-ttu-id="aa403-345">我在初始化数组时以内联方式计算其结果。</span><span class="sxs-lookup"><span data-stu-id="aa403-345">I evaluate them inline inside the initialization of my array.</span></span> <span data-ttu-id="aa403-346">如果 `$Debug` 为 true，则这些值将位于 `$snowSqlParam` 中的正确位置。</span><span class="sxs-lookup"><span data-stu-id="aa403-346">If `$Debug` is true, then those values fall into the `$snowSqlParam` in the correct place.</span></span> <span data-ttu-id="aa403-347">`$Path` 变量情况相同。</span><span class="sxs-lookup"><span data-stu-id="aa403-347">Same holds true for the `$Path` variable.</span></span>

## <a name="simplify-complex-operations"></a><span data-ttu-id="aa403-348">简化复杂操作</span><span class="sxs-lookup"><span data-stu-id="aa403-348">Simplify complex operations</span></span>

<span data-ttu-id="aa403-349">你不可避免会遇到这样的情况：有太多的比较需要检查，if 语句从屏幕右侧滚出。</span><span class="sxs-lookup"><span data-stu-id="aa403-349">It's inevitable that you run into a situation that has way too many comparisons to check and your if statement scrolls way off the right side of the screen.</span></span>

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

<span data-ttu-id="aa403-350">它们不便阅读，这使你更容易出错。</span><span class="sxs-lookup"><span data-stu-id="aa403-350">They can be hard to read and that make you more prone to make mistakes.</span></span> <span data-ttu-id="aa403-351">我们可以对此进行一些操作。</span><span class="sxs-lookup"><span data-stu-id="aa403-351">There are a few things we can do about that.</span></span>

### <a name="line-continuation"></a><span data-ttu-id="aa403-352">续行符</span><span class="sxs-lookup"><span data-stu-id="aa403-352">Line continuation</span></span>

<span data-ttu-id="aa403-353">PowerShell 中提供了一些运算符，可让你将命令换到下一行。</span><span class="sxs-lookup"><span data-stu-id="aa403-353">There some operators in PowerShell that let you wrap you command to the next line.</span></span> <span data-ttu-id="aa403-354">如果要将表达式分为多行，则逻辑运算符 `-and` 和 `-or` 是理想的运算符。</span><span class="sxs-lookup"><span data-stu-id="aa403-354">The logical operators `-and` and `-or` are good operators to use if you want to break your expression into multiple lines.</span></span>

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

<span data-ttu-id="aa403-355">还有很多内容，但将每个部分放在其自己的行上会有很大不同。</span><span class="sxs-lookup"><span data-stu-id="aa403-355">There's still a lot going on there, but placing each piece on its own line makes a big difference.</span></span>
<span data-ttu-id="aa403-356">当我进行两次以上的比较，或者如果我必须向右滚动来阅读任何逻辑时，我通常会使用此方法。</span><span class="sxs-lookup"><span data-stu-id="aa403-356">I generally use this when I get more than two comparisons or if I have to scroll to the right to read any of the logic.</span></span>

### <a name="pre-calculating-results"></a><span data-ttu-id="aa403-357">预先计算结果</span><span class="sxs-lookup"><span data-stu-id="aa403-357">Pre-calculating results</span></span>

<span data-ttu-id="aa403-358">我们可以将该语句从 if 语句中取出并仅检查结果。</span><span class="sxs-lookup"><span data-stu-id="aa403-358">We can take that statement out of the if statement and only check the result.</span></span>

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

<span data-ttu-id="aa403-359">这样感觉比上一个示例简洁得多。</span><span class="sxs-lookup"><span data-stu-id="aa403-359">This just feels much cleaner than the previous example.</span></span> <span data-ttu-id="aa403-360">你还可以使用变量名称来解释你真正检查的内容。</span><span class="sxs-lookup"><span data-stu-id="aa403-360">You also are given an opportunity to use a variable name that explains what it's that you're really checking.</span></span> <span data-ttu-id="aa403-361">这也是节省不必要注释的自文档化代码的示例。</span><span class="sxs-lookup"><span data-stu-id="aa403-361">This is also and example of self-documenting code that saves unnecessary comments.</span></span>

### <a name="multiple-if-statements"></a><span data-ttu-id="aa403-362">多个 if 语句</span><span class="sxs-lookup"><span data-stu-id="aa403-362">Multiple if statements</span></span>

<span data-ttu-id="aa403-363">我们可以将此语句分为多个语句，并一次查看一个语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-363">We can break this up into multiple statements and check them one at a time.</span></span> <span data-ttu-id="aa403-364">在这种情况下，我们使用标志或跟踪变量来合并结果。</span><span class="sxs-lookup"><span data-stu-id="aa403-364">In this case, we use a flag or a tracking variable to combine the results.</span></span>

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

<span data-ttu-id="aa403-365">我不得不对逻辑进行反转操作，使标志逻辑正常工作。</span><span class="sxs-lookup"><span data-stu-id="aa403-365">I did have to invert the logic to make the flag logic work correctly.</span></span> <span data-ttu-id="aa403-366">每个计算都是单个 `if` 语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-366">Each evaluation is an individual `if` statement.</span></span> <span data-ttu-id="aa403-367">这样做的优点是，当你进行调试时，你可以确切地判断逻辑的作用。</span><span class="sxs-lookup"><span data-stu-id="aa403-367">The advantage of this is that when you're debugging, you can tell exactly what the logic is doing.</span></span> <span data-ttu-id="aa403-368">我能够同时添加更好的详细程度。</span><span class="sxs-lookup"><span data-stu-id="aa403-368">I was able to add much better verbosity at the same time.</span></span>

<span data-ttu-id="aa403-369">明显的缺点是，要编写的代码太多。</span><span class="sxs-lookup"><span data-stu-id="aa403-369">The obvious downside is that it's so much more code to write.</span></span> <span data-ttu-id="aa403-370">代码读起来更复杂，因为它采用单行逻辑，并分解成 25 行或更多行。</span><span class="sxs-lookup"><span data-stu-id="aa403-370">The code is more complex to look at as it takes a single line of logic and explodes it into 25 or more lines.</span></span>

### <a name="using-functions"></a><span data-ttu-id="aa403-371">使用函数</span><span class="sxs-lookup"><span data-stu-id="aa403-371">Using functions</span></span>

<span data-ttu-id="aa403-372">我们还可以将所有验证逻辑移到一个函数中。</span><span class="sxs-lookup"><span data-stu-id="aa403-372">We can also move all that validation logic into a function.</span></span> <span data-ttu-id="aa403-373">看看这样看起来多清爽。</span><span class="sxs-lookup"><span data-stu-id="aa403-373">Look at how clean this looks at a glance.</span></span>

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

<span data-ttu-id="aa403-374">你仍必须创建函数来执行验证，但它使得此代码更容易使用。</span><span class="sxs-lookup"><span data-stu-id="aa403-374">You still have to create the function to do the validation, but it makes this code much easier to work with.</span></span> <span data-ttu-id="aa403-375">这使代码更易于测试。</span><span class="sxs-lookup"><span data-stu-id="aa403-375">It makes this code easier to test.</span></span> <span data-ttu-id="aa403-376">在测试中，可以模拟对 `Test-ADDriveConfiguration` 的调用，而只需对此函数进行两次测试。</span><span class="sxs-lookup"><span data-stu-id="aa403-376">In your tests, you can mock the call to `Test-ADDriveConfiguration` and you only need two tests for this function.</span></span> <span data-ttu-id="aa403-377">其中一个返回 `$true`，另一个返回 `$false`。</span><span class="sxs-lookup"><span data-stu-id="aa403-377">One where it returns `$true` and one where it returns `$false`.</span></span> <span data-ttu-id="aa403-378">测试其他函数的方法更简单，因为它很小。</span><span class="sxs-lookup"><span data-stu-id="aa403-378">Testing the other function is simpler because it's so small.</span></span>

<span data-ttu-id="aa403-379">该函数的主体仍然可以是我们开始时使用的单行命令或我们在上一部分中使用的分离逻辑。</span><span class="sxs-lookup"><span data-stu-id="aa403-379">The body of that function could still be that one-liner we started with or the exploded logic that we used in the last section.</span></span> <span data-ttu-id="aa403-380">这适用于这两种方案，并使你能够在以后轻松地更改该实现。</span><span class="sxs-lookup"><span data-stu-id="aa403-380">This works well for both scenarios and allows you to easily change that implementation later.</span></span>

## <a name="error-handling"></a><span data-ttu-id="aa403-381">错误处理。</span><span class="sxs-lookup"><span data-stu-id="aa403-381">Error handling</span></span>

<span data-ttu-id="aa403-382">`if` 语句的一项重要用途是在出现错误之前检查错误条件。</span><span class="sxs-lookup"><span data-stu-id="aa403-382">One important use of the `if` statement is to check for error conditions before you run into errors.</span></span> <span data-ttu-id="aa403-383">一个不错的示例是，在尝试创建文件夹之前检查文件夹是否已存在。</span><span class="sxs-lookup"><span data-stu-id="aa403-383">A good example is to check if a folder already exists before you try to create it.</span></span>

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

<span data-ttu-id="aa403-384">我想说的是，如果你预计会发生异常，那么它就不是真正的异常。</span><span class="sxs-lookup"><span data-stu-id="aa403-384">I like to say that if you expect an exception to happen, then it's not really an exception.</span></span> <span data-ttu-id="aa403-385">因此，请检查你的值并在可能的地方验证你的条件。</span><span class="sxs-lookup"><span data-stu-id="aa403-385">So check your values and validate your conditions where you can.</span></span>

<span data-ttu-id="aa403-386">如果你想要更深入地了解实际异常处理，请参阅我写的另一篇文章[关于异常的各项须知内容][]。</span><span class="sxs-lookup"><span data-stu-id="aa403-386">If you want to dive a little more into actual exception handling, I have an article on [everything you ever wanted to know about exceptions][].</span></span>

## <a name="final-words"></a><span data-ttu-id="aa403-387">结束语</span><span class="sxs-lookup"><span data-stu-id="aa403-387">Final words</span></span>

<span data-ttu-id="aa403-388">`if` 语句非常简单，但却是 PowerShell 的一个基本部分。</span><span class="sxs-lookup"><span data-stu-id="aa403-388">The `if` statement is such a simple statement but is a fundamental piece of PowerShell.</span></span> <span data-ttu-id="aa403-389">你会发现自己在编写的几乎每个脚本中都会多次使用此语句。</span><span class="sxs-lookup"><span data-stu-id="aa403-389">You will find yourself using this multiple times in almost every script you write.</span></span> <span data-ttu-id="aa403-390">希望你比以往更好地理解这些内容。</span><span class="sxs-lookup"><span data-stu-id="aa403-390">I hope you have a better understanding than you had before.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2019-08-11-PowerShell-if-then-else-equals-operator/
[original version]: https://powershellexplained.com/2019-08-11-PowerShell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if
[位运算符]: https://powershellexplained.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[bitwise operators]: https://powershellexplained.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[使用正则表达式的多种方式]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[the many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[关于异常的各项须知内容]: everything-about-exceptions.md
[everything you ever wanted to know about exceptions]: everything-about-exceptions.md
[关于 $null 的各项须知内容]: everything-about-null.md
[everything you wanted to know about $null]: everything-about-null.md
[Prasoon Karunan V]: https://twitter.com/prasoonkarunan
[关于 switch 语句的各项须知内容]: everything-about-switch.md
[everything you ever wanted to know about the switch statement]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
