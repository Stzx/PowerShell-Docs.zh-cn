---
title: 关于 switch 语句的各项须知内容
description: PowerShell 中的 switch 语句提供了其他语言没有的功能。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ebf6191d56374273465ae6bee49ef82a02cc1580
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149420"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a><span data-ttu-id="cc10f-103">关于 switch 语句的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="cc10f-103">Everything you ever wanted to know about the switch statement</span></span>

<span data-ttu-id="cc10f-104">与许多其他语言一样，PowerShell 具有用于控制脚本内执行流的命令。</span><span class="sxs-lookup"><span data-stu-id="cc10f-104">Like many other languages, PowerShell has commands for controlling the flow of execution within your scripts.</span></span> <span data-ttu-id="cc10f-105">其中一个语句是 [switch][] 语句，在 PowerShell 中，它提供了其他语言没有的功能。</span><span class="sxs-lookup"><span data-stu-id="cc10f-105">One of those statements is the [switch][] statement and in PowerShell, it offers features that aren't found in other languages.</span></span> <span data-ttu-id="cc10f-106">今天，我们将深入探讨如何使用 PowerShell `switch`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-106">Today, we take a deep dive into working with the PowerShell `switch`.</span></span>

> [!NOTE]
> <span data-ttu-id="cc10f-107">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="cc10f-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="cc10f-108">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="cc10f-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="cc10f-109">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="cc10f-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="if-statement"></a><span data-ttu-id="cc10f-110">If 语句</span><span class="sxs-lookup"><span data-stu-id="cc10f-110">If statement</span></span>

<span data-ttu-id="cc10f-111">首先要学习的语句之一是 `if` 语句。</span><span class="sxs-lookup"><span data-stu-id="cc10f-111">One of the first statements that you learn is the `if` statement.</span></span> <span data-ttu-id="cc10f-112">如果语句为 `$true`，则允许执行脚本块。</span><span class="sxs-lookup"><span data-stu-id="cc10f-112">It lets you execute a script block if a statement is `$true`.</span></span>

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

<span data-ttu-id="cc10f-113">可以通过使用 `elseif` 和 `else` 语句来获得更复杂的逻辑。</span><span class="sxs-lookup"><span data-stu-id="cc10f-113">You can have much more complicated logic by using `elseif` and `else` statements.</span></span> <span data-ttu-id="cc10f-114">下面是一个示例：一周中的某一天用数值表示，并且我想要获取字符串形式的名称。</span><span class="sxs-lookup"><span data-stu-id="cc10f-114">Here is an example where I have a numeric value for day of the week and I want to get the name as a string.</span></span>

``` powershell
$day = 3

if ( $day -eq 0 ) { $result = 'Sunday'        }
elseif ( $day -eq 1 ) { $result = 'Monday'    }
elseif ( $day -eq 2 ) { $result = 'Tuesday'   }
elseif ( $day -eq 3 ) { $result = 'Wednesday' }
elseif ( $day -eq 4 ) { $result = 'Thursday'  }
elseif ( $day -eq 5 ) { $result = 'Friday'    }
elseif ( $day -eq 6 ) { $result = 'Saturday'  }

$result
```

```Output
Wednesday
```

<span data-ttu-id="cc10f-115">事实证明，这是一种常见模式，可以通过多种方法来实现。</span><span class="sxs-lookup"><span data-stu-id="cc10f-115">It turns out that this is a common pattern and there are many ways to deal with this.</span></span> <span data-ttu-id="cc10f-116">其中一种方法是使用 `switch`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-116">One of them is with a `switch`.</span></span>

## <a name="switch-statement"></a><span data-ttu-id="cc10f-117">Switch 语句</span><span class="sxs-lookup"><span data-stu-id="cc10f-117">Switch statement</span></span>

<span data-ttu-id="cc10f-118">使用 `switch` 语句可以提供变量和可能值的列表。</span><span class="sxs-lookup"><span data-stu-id="cc10f-118">The `switch` statement allows you to provide a variable and a list of possible values.</span></span> <span data-ttu-id="cc10f-119">如果该值与变量匹配，则将执行其脚本块。</span><span class="sxs-lookup"><span data-stu-id="cc10f-119">If the value matches the variable, then its scriptblock is executed.</span></span>

``` powershell
$day = 3

switch ( $day )
{
    0 { $result = 'Sunday'    }
    1 { $result = 'Monday'    }
    2 { $result = 'Tuesday'   }
    3 { $result = 'Wednesday' }
    4 { $result = 'Thursday'  }
    5 { $result = 'Friday'    }
    6 { $result = 'Saturday'  }
}

$result
```

```Output
'Wednesday'
```

<span data-ttu-id="cc10f-120">在本示例中，`$day` 的值与其中一个数值匹配，然后正确的名称即会分配给 `$result`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-120">For this example, the value of `$day` matches one of the numeric values, then the correct name is assigned to `$result`.</span></span> <span data-ttu-id="cc10f-121">我们在本示例中只执行变量赋值，但可以在这些脚本块中执行任何 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cc10f-121">We are only doing a variable assignment in this example, but any PowerShell can be executed in those script blocks.</span></span>

### <a name="assign-to-a-variable"></a><span data-ttu-id="cc10f-122">给变量赋值</span><span class="sxs-lookup"><span data-stu-id="cc10f-122">Assign to a variable</span></span>

<span data-ttu-id="cc10f-123">我们可以通过另一种方法编写上一个示例。</span><span class="sxs-lookup"><span data-stu-id="cc10f-123">We can write that last example in another way.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday'    }
    1 { 'Monday'    }
    2 { 'Tuesday'   }
    3 { 'Wednesday' }
    4 { 'Thursday'  }
    5 { 'Friday'    }
    6 { 'Saturday'  }
}
```

<span data-ttu-id="cc10f-124">我们将该值置于 PowerShell 管道上，并将其赋予 `$result`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-124">We are placing the value on the PowerShell pipeline and assigning it to the `$result`.</span></span> <span data-ttu-id="cc10f-125">可以使用 `if` 和 `foreach` 语句执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="cc10f-125">You can do this same thing with the `if` and `foreach` statements.</span></span>

### <a name="default"></a><span data-ttu-id="cc10f-126">默认</span><span class="sxs-lookup"><span data-stu-id="cc10f-126">Default</span></span>

<span data-ttu-id="cc10f-127">如果没有匹配项，我们可以使用 `default` 关键字来确定应当出现的情况。</span><span class="sxs-lookup"><span data-stu-id="cc10f-127">We can use the `default` keyword to identify the what should happen if there is no match.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

<span data-ttu-id="cc10f-128">默认情况下，我们返回值 `Unknown`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-128">Here we return the value `Unknown` in the default case.</span></span>

### <a name="strings"></a><span data-ttu-id="cc10f-129">字符串</span><span class="sxs-lookup"><span data-stu-id="cc10f-129">Strings</span></span>

<span data-ttu-id="cc10f-130">我在上述几个示例中匹配的是数字，但你也可以匹配字符串。</span><span class="sxs-lookup"><span data-stu-id="cc10f-130">I was matching numbers in those last examples, but you can also match strings.</span></span>

``` powershell
$item = 'Role'

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="cc10f-131">我决定在此处不将 `Component`、`Role` 和 `Location` 匹配项括在引号中，以突出显示它们是可选的。</span><span class="sxs-lookup"><span data-stu-id="cc10f-131">I decided not to wrap the `Component`,`Role` and `Location` matches in quotes here to highlight that they're optional.</span></span> <span data-ttu-id="cc10f-132">在大多数情况下，`switch` 会将它们视为字符串。</span><span class="sxs-lookup"><span data-stu-id="cc10f-132">The `switch` treats those as a string in most cases.</span></span>

## <a name="arrays"></a><span data-ttu-id="cc10f-133">数组</span><span class="sxs-lookup"><span data-stu-id="cc10f-133">Arrays</span></span>

<span data-ttu-id="cc10f-134">PowerShell `switch` 的一项优异功能体现在处理数组的方式上。</span><span class="sxs-lookup"><span data-stu-id="cc10f-134">One of the cool features of the PowerShell `switch` is the way it handles arrays.</span></span> <span data-ttu-id="cc10f-135">如果向数组提供 `switch`，则会处理该集合中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="cc10f-135">If you give a `switch` an array, it processes each element in that collection.</span></span>

``` powershell
$roles = @('WEB','Database')

switch ( $roles ) {
    'Database'   { 'Configure SQL' }
    'WEB'        { 'Configure IIS' }
    'FileServer' { 'Configure Share' }
}
```

```Output
Configure IIS
Configure SQL
```

<span data-ttu-id="cc10f-136">如果数组中有重复项，则相应的部分会多次匹配它们。</span><span class="sxs-lookup"><span data-stu-id="cc10f-136">If you have repeated items in your array, then they're matched multiple times by the appropriate section.</span></span>

### <a name="psitem"></a><span data-ttu-id="cc10f-137">PSItem</span><span class="sxs-lookup"><span data-stu-id="cc10f-137">PSItem</span></span>

<span data-ttu-id="cc10f-138">可以使用 `$PSItem` 或 `$_` 来引用已处理的当前项。</span><span class="sxs-lookup"><span data-stu-id="cc10f-138">You can use the `$PSItem` or `$_` to reference the current item that was processed.</span></span> <span data-ttu-id="cc10f-139">当我们执行简单匹配时，`$PSItem` 是我们要匹配的值。</span><span class="sxs-lookup"><span data-stu-id="cc10f-139">When we do a simple match, `$PSItem` is the value that we are matching.</span></span> <span data-ttu-id="cc10f-140">在下一部分中，将使用此变量来执行一些高级匹配。</span><span class="sxs-lookup"><span data-stu-id="cc10f-140">I'll be performing some advanced matches in the next section where this variable is used.</span></span>

## <a name="parameters"></a><span data-ttu-id="cc10f-141">参数</span><span class="sxs-lookup"><span data-stu-id="cc10f-141">Parameters</span></span>

<span data-ttu-id="cc10f-142">PowerShell `switch` 的一项独特功能是它有许多可更改执行方式的[开关参数][]。</span><span class="sxs-lookup"><span data-stu-id="cc10f-142">A unique feature of the PowerShell `switch` is that it has a number of [switch parameters][] that change how it performs.</span></span>

### <a name="-casesensitive"></a><span data-ttu-id="cc10f-143">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="cc10f-143">-CaseSensitive</span></span>

<span data-ttu-id="cc10f-144">默认情况下，匹配项不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cc10f-144">The matches aren't case-sensitive by default.</span></span> <span data-ttu-id="cc10f-145">如果需要区分大小写，可以使用 `-CaseSensitive`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-145">If you need to be case-sensitive, you can use `-CaseSensitive`.</span></span> <span data-ttu-id="cc10f-146">这可以与其他开关参数结合使用。</span><span class="sxs-lookup"><span data-stu-id="cc10f-146">This can be used in combination with the other switch parameters.</span></span>

### <a name="-wildcard"></a><span data-ttu-id="cc10f-147">-Wildcard</span><span class="sxs-lookup"><span data-stu-id="cc10f-147">-Wildcard</span></span>

<span data-ttu-id="cc10f-148">可以使用 `-wildcard` 开关启用通配符支持。</span><span class="sxs-lookup"><span data-stu-id="cc10f-148">We can enable wildcard support with the `-wildcard` switch.</span></span> <span data-ttu-id="cc10f-149">这会使用与 `-like` 运算符相同的通配符逻辑来执行每次匹配。</span><span class="sxs-lookup"><span data-stu-id="cc10f-149">This uses the same wildcard logic as the `-like` operator to do each match.</span></span>

``` powershell
$Message = 'Warning, out of disk space'

switch -Wildcard ( $message )
{
    'Error*'
    {
        Write-Error -Message $Message
    }
    'Warning*'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

```Output
WARNING: Warning, out of disk space
```

<span data-ttu-id="cc10f-150">此时我们将处理一条消息，然后根据内容将其输出到不同的流中。</span><span class="sxs-lookup"><span data-stu-id="cc10f-150">Here we are processing a message and then outputting it on different streams based on the contents.</span></span>

### <a name="-regex"></a><span data-ttu-id="cc10f-151">-Regex</span><span class="sxs-lookup"><span data-stu-id="cc10f-151">-Regex</span></span>

<span data-ttu-id="cc10f-152">switch 语句支持正则表达式匹配，就像支持通配符一样。</span><span class="sxs-lookup"><span data-stu-id="cc10f-152">The switch statement supports regex matches just like it does wildcards.</span></span>

``` powershell
switch -Regex ( $message )
{
    '^Error'
    {
        Write-Error -Message $Message
    }
    '^Warning'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

<span data-ttu-id="cc10f-153">在我撰写的另一篇文章中有更多使用正则表达式的示例：[使用正则表达式的多种方式][]。</span><span class="sxs-lookup"><span data-stu-id="cc10f-153">I have more examples of using regex in another article I wrote: [The many ways to use regex][].</span></span>

### <a name="-file"></a><span data-ttu-id="cc10f-154">-File</span><span class="sxs-lookup"><span data-stu-id="cc10f-154">-File</span></span>

<span data-ttu-id="cc10f-155">switch 语句的一个鲜为人知的功能是，它可以使用 `-File` 参数处理文件。</span><span class="sxs-lookup"><span data-stu-id="cc10f-155">A little known feature of the switch statement is that it can process a file with the `-File` parameter.</span></span> <span data-ttu-id="cc10f-156">将 `-file` 与文件路径结合使用，而不是向其提供变量表达式。</span><span class="sxs-lookup"><span data-stu-id="cc10f-156">You use `-file` with a path to a file instead of giving it a variable expression.</span></span>

``` powershell
switch -Wildcard -File $path
{
    'Error*'
    {
        Write-Error -Message $PSItem
    }
    'Warning*'
    {
        Write-Warning -Message $PSItem
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="cc10f-157">它的工作方式就像处理数组一样。</span><span class="sxs-lookup"><span data-stu-id="cc10f-157">It works just like processing an array.</span></span> <span data-ttu-id="cc10f-158">在本示例中，我将它与通配符匹配结合使用，并使用 `$PSItem`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-158">In this example, I combine it with wildcard matching and make use of the `$PSItem`.</span></span> <span data-ttu-id="cc10f-159">这会处理日志文件，并根据正则表达式匹配将其转换为警告消息和错误消息。</span><span class="sxs-lookup"><span data-stu-id="cc10f-159">This would process a log file and convert it to warning and error messages depending on the regex matches.</span></span>

## <a name="advanced-details"></a><span data-ttu-id="cc10f-160">高级详细信息</span><span class="sxs-lookup"><span data-stu-id="cc10f-160">Advanced details</span></span>

<span data-ttu-id="cc10f-161">现在，你已经了解了所有这些文档中记录的功能，我们可以在更高级处理的上下文中使用它们。</span><span class="sxs-lookup"><span data-stu-id="cc10f-161">Now that you're aware of all these documented features, we can use them in the context of more advanced processing.</span></span>

### <a name="expressions"></a><span data-ttu-id="cc10f-162">表达式</span><span class="sxs-lookup"><span data-stu-id="cc10f-162">Expressions</span></span>

<span data-ttu-id="cc10f-163">`switch` 可以在表达式中，而不是在变量中。</span><span class="sxs-lookup"><span data-stu-id="cc10f-163">The `switch` can be on an expression instead of a variable.</span></span>

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

<span data-ttu-id="cc10f-164">表达式的计算结果均为用于匹配的值。</span><span class="sxs-lookup"><span data-stu-id="cc10f-164">Whatever the expression evaluates to is the value used for the match.</span></span>

### <a name="multiple-matches"></a><span data-ttu-id="cc10f-165">多个匹配</span><span class="sxs-lookup"><span data-stu-id="cc10f-165">Multiple matches</span></span>

<span data-ttu-id="cc10f-166">你可能已选择了此项，但 `switch` 可以匹配多个条件。</span><span class="sxs-lookup"><span data-stu-id="cc10f-166">You may have already picked up on this, but a `switch` can match to multiple conditions.</span></span> <span data-ttu-id="cc10f-167">当使用 `-wildcard` 或 `-regex` 匹配时，尤其如此。</span><span class="sxs-lookup"><span data-stu-id="cc10f-167">This is especially true when using `-wildcard` or `-regex` matches.</span></span> <span data-ttu-id="cc10f-168">可以多次添加同一条件，并同时触发所有条件。</span><span class="sxs-lookup"><span data-stu-id="cc10f-168">You can add the same condition multiple times and all of them are triggered.</span></span>

``` powershell
switch ( 'Word' )
{
    'word' { 'lower case word match' }
    'Word' { 'mixed case word match' }
    'WORD' { 'upper case word match' }
}
```

```Output
lower case word match
mixed case word match
upper case word match
```

<span data-ttu-id="cc10f-169">这三个语句都会触发。</span><span class="sxs-lookup"><span data-stu-id="cc10f-169">All three of these statements are fired.</span></span> <span data-ttu-id="cc10f-170">这表明每个条件都处于选中状态（按顺序）。</span><span class="sxs-lookup"><span data-stu-id="cc10f-170">This shows that every condition is checked (in order).</span></span> <span data-ttu-id="cc10f-171">这适用于处理每个项检查每个条件的数组。</span><span class="sxs-lookup"><span data-stu-id="cc10f-171">This holds true for processing arrays where each item checks each condition.</span></span>

### <a name="continue"></a><span data-ttu-id="cc10f-172">继续</span><span class="sxs-lookup"><span data-stu-id="cc10f-172">Continue</span></span>

<span data-ttu-id="cc10f-173">通常，我会在此介绍 `break` 语句，但最好先了解如何使用 `continue`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-173">Normally, this is where I would introduce the `break` statement, but it's better that we learn how to use `continue` first.</span></span> <span data-ttu-id="cc10f-174">正如 `foreach` 循环一样，`continue` 会继续进行到集合中的下一项，如果没有更多项，则会退出 `switch`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-174">Just like with a `foreach` loop, `continue` continues onto the next item in the collection or exits the `switch` if there are no more items.</span></span> <span data-ttu-id="cc10f-175">我们可以使用 continue 语句重写上一个示例，以便仅执行一个语句。</span><span class="sxs-lookup"><span data-stu-id="cc10f-175">We can rewrite that last example with continue statements so that only one statement executes.</span></span>

``` powershell
switch ( 'Word' )
{
    'word'
    {
        'lower case word match'
        continue
    }
    'Word'
    {
        'mixed case word match'
        continue
    }
    'WORD'
    {
        'upper case word match'
        continue
    }
}
```

```Output
lower case word match
```

<span data-ttu-id="cc10f-176">匹配第一个项，并且开关继续切换到下一个值，而不是匹配所有三个项。</span><span class="sxs-lookup"><span data-stu-id="cc10f-176">Instead of matching all three items, the first one is matched and the switch continues to the next value.</span></span> <span data-ttu-id="cc10f-177">由于没有要处理的值了，因此开关将退出。</span><span class="sxs-lookup"><span data-stu-id="cc10f-177">Because there are no values left to process, the switch exits.</span></span> <span data-ttu-id="cc10f-178">下一个示例演示通配符如何与多个项匹配。</span><span class="sxs-lookup"><span data-stu-id="cc10f-178">This next example is showing how a wildcard could match multiple items.</span></span>

``` powershell
switch -Wildcard -File $path
{
    '*Error*'
    {
        Write-Error -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="cc10f-179">由于输入文件中的一行可能同时包含单词 `Error` 和 `Warning`，因此我们只希望执行第一个，然后继续处理该文件。</span><span class="sxs-lookup"><span data-stu-id="cc10f-179">Because a line in the input file could contain both the word `Error` and `Warning`, we only want the first one to execute and then continue processing the file.</span></span>

### <a name="break"></a><span data-ttu-id="cc10f-180">中断</span><span class="sxs-lookup"><span data-stu-id="cc10f-180">Break</span></span>

<span data-ttu-id="cc10f-181">`break` 语句退出开关。</span><span class="sxs-lookup"><span data-stu-id="cc10f-181">A `break` statement exits the switch.</span></span> <span data-ttu-id="cc10f-182">这与 `continue` 为单个值提供的行为相同。</span><span class="sxs-lookup"><span data-stu-id="cc10f-182">This is the same behavior that `continue` presents for single values.</span></span> <span data-ttu-id="cc10f-183">差异会在处理数组时显示出来。</span><span class="sxs-lookup"><span data-stu-id="cc10f-183">The difference is shown when processing an array.</span></span> <span data-ttu-id="cc10f-184">`break` 会停止开关中的所有处理，而 `continue` 会继续进行到下一项。</span><span class="sxs-lookup"><span data-stu-id="cc10f-184">`break` stops all processing in the switch and `continue` moves onto the next item.</span></span>

``` powershell
$Messages = @(
    'Downloading update'
    'Ran into errors downloading file'
    'Error: out of disk space'
    'Sending email'
    '...'
)

switch -Wildcard ($Messages)
{
    'Error*'
    {
        Write-Error -Message $PSItem
        break
    }
    '*Error*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

```Output
Downloading update
WARNING: Ran into errors downloading file
write-error -message $PSItem : Error: out of disk space
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

<span data-ttu-id="cc10f-185">在这种情况下，如果点击以 `Error` 开头的任何行，则会出现错误，并且开关将停止。</span><span class="sxs-lookup"><span data-stu-id="cc10f-185">In this case, if we hit any lines that start with `Error` then we get an error and the switch stops.</span></span>
<span data-ttu-id="cc10f-186">这就是 `break` 语句的作用。</span><span class="sxs-lookup"><span data-stu-id="cc10f-186">This is what that `break` statement is doing for us.</span></span> <span data-ttu-id="cc10f-187">如果在字符串内（而不只是在开头）查找 `Error`，则将其编写为警告。</span><span class="sxs-lookup"><span data-stu-id="cc10f-187">If we find `Error` inside the string and not just at the beginning, we write it as a warning.</span></span> <span data-ttu-id="cc10f-188">我们将为 `Warning` 执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="cc10f-188">We do the same thing for `Warning`.</span></span> <span data-ttu-id="cc10f-189">一行中可能同时包含单词 `Error` 和 `Warning`，但我们只需处理一个。</span><span class="sxs-lookup"><span data-stu-id="cc10f-189">It's possible that a line could have both the word `Error` and `Warning`, but we only need one to process.</span></span> <span data-ttu-id="cc10f-190">这就是 `continue` 语句的作用。</span><span class="sxs-lookup"><span data-stu-id="cc10f-190">This is what the `continue` statement is doing for us.</span></span>

### <a name="break-labels"></a><span data-ttu-id="cc10f-191">中断标签</span><span class="sxs-lookup"><span data-stu-id="cc10f-191">Break labels</span></span>

<span data-ttu-id="cc10f-192">`switch` 语句支持 `break/continue` 标签，就像 `foreach` 一样。</span><span class="sxs-lookup"><span data-stu-id="cc10f-192">The `switch` statement supports `break/continue` labels just like `foreach`.</span></span>

``` powershell
:filelist foreach($path in $logs)
{
    :logFile switch -Wildcard -File $path
    {
        'Error*'
        {
            Write-Error -Message $PSItem
            break filelist
        }
        'Warning*'
        {
            Write-Error -Message $PSItem
            break logFile
        }
        default
        {
            Write-Output $PSItem
        }
    }
}
```

<span data-ttu-id="cc10f-193">我个人不喜欢使用中断标签，但我想要提一下它们，因为如果你之前从未见过它们，可能会感到困惑。</span><span class="sxs-lookup"><span data-stu-id="cc10f-193">I personally don't like the use of break labels but I wanted to point them out because they're confusing if you've never seen them before.</span></span> <span data-ttu-id="cc10f-194">如果有多个嵌套的 `switch` 或 `foreach` 语句，则可能需要中断的不只是最内部的项。</span><span class="sxs-lookup"><span data-stu-id="cc10f-194">When you have multiple `switch` or `foreach` statements that are nested, you may want to break out of more than the inner most item.</span></span> <span data-ttu-id="cc10f-195">可以在可作为 `break` 目标的 `switch` 上放置一个标签。</span><span class="sxs-lookup"><span data-stu-id="cc10f-195">You can place a label on a `switch` that can be the target of your `break`.</span></span>

### <a name="enum"></a><span data-ttu-id="cc10f-196">枚举</span><span class="sxs-lookup"><span data-stu-id="cc10f-196">Enum</span></span>

<span data-ttu-id="cc10f-197">PowerShell 5.0 为我们提供了枚举，我们可以在开关中使用它们。</span><span class="sxs-lookup"><span data-stu-id="cc10f-197">PowerShell 5.0 gave us enums and we can use them in a switch.</span></span>

``` powershell
enum Context {
    Component
    Role
    Location
}

$item = [Context]::Role

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="cc10f-198">如果要将所有内容保持为强类型枚举，则可以将其置于括号中。</span><span class="sxs-lookup"><span data-stu-id="cc10f-198">If you want to keep everything as strongly typed enums, then you can place them in parentheses.</span></span>

``` powershell
switch ($item )
{
    ([Context]::Component)
    {
        'is a component'
    }
    ([Context]::Role)
    {
        'is a role'
    }
    ([Context]::Location)
    {
        'is a location'
    }
}
```

<span data-ttu-id="cc10f-199">此处需要括号，以便开关不将值 `[Context]::Location` 视为文本字符串。</span><span class="sxs-lookup"><span data-stu-id="cc10f-199">The parentheses are needed here so that the switch doesn't treat the value `[Context]::Location` as a literal string.</span></span>

### <a name="scriptblock"></a><span data-ttu-id="cc10f-200">脚本块</span><span class="sxs-lookup"><span data-stu-id="cc10f-200">ScriptBlock</span></span>

<span data-ttu-id="cc10f-201">如果需要，我们可以使用脚本块来执行匹配的计算。</span><span class="sxs-lookup"><span data-stu-id="cc10f-201">We can use a scriptblock to perform the evaluation for a match if needed.</span></span>

``` powershell
$age = 37

switch ( $age )
{
    {$PSItem -le 18}
    {
        'child'
    }
    {$PSItem -gt 18}
    {
        'adult'
    }
}
```

```Output
'adult'
```

<span data-ttu-id="cc10f-202">这会增加复杂性，并且会使 `switch` 难以读取。</span><span class="sxs-lookup"><span data-stu-id="cc10f-202">This adds complexity and can make your `switch` hard to read.</span></span> <span data-ttu-id="cc10f-203">在大多数情况下，最好使用 `if` 和 `elseif` 语句。</span><span class="sxs-lookup"><span data-stu-id="cc10f-203">In most cases where you would use something like this it would be better to use `if` and `elseif` statements.</span></span> <span data-ttu-id="cc10f-204">如果已经有一个较大的开关，并且需要两个项来点击相同的计算块，我会考虑使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="cc10f-204">I would consider using this if I already had a large switch in place and I needed two items to hit the same evaluation block.</span></span>

<span data-ttu-id="cc10f-205">我认为有助于增强可读性的一点是将脚本块置于括号中。</span><span class="sxs-lookup"><span data-stu-id="cc10f-205">One thing that I think helps with legibility is to place the scriptblock in parentheses.</span></span>

``` powershell
switch ( $age )
{
    ({$PSItem -le 18})
    {
        'child'
    }
    ({$PSItem -gt 18})
    {
        'adult'
    }
}
```

<span data-ttu-id="cc10f-206">它仍以相同的方式执行，并在快速查看时提供更好的视觉中断。</span><span class="sxs-lookup"><span data-stu-id="cc10f-206">It still executes the same way and gives a better visual break when quickly looking at it.</span></span>

### <a name="regex-matches"></a><span data-ttu-id="cc10f-207">正则表达式 $matches</span><span class="sxs-lookup"><span data-stu-id="cc10f-207">Regex $matches</span></span>

<span data-ttu-id="cc10f-208">我们需要重新讨论正则表达式，以触及一些不太明显的内容。</span><span class="sxs-lookup"><span data-stu-id="cc10f-208">We need to revisit regex to touch on something that isn't immediately obvious.</span></span> <span data-ttu-id="cc10f-209">使用正则表达式可填充 `$matches` 变量。</span><span class="sxs-lookup"><span data-stu-id="cc10f-209">The use of regex populates the `$matches` variable.</span></span> <span data-ttu-id="cc10f-210">当我谈到[使用正则表达式的多种方式][]时，我确实更多地谈到了 `$matches` 的使用。</span><span class="sxs-lookup"><span data-stu-id="cc10f-210">I do go into the use of `$matches` more when I talk about [The many ways to use regex][].</span></span> <span data-ttu-id="cc10f-211">下面是一个快速示例，演示了使用命名匹配项时的情况。</span><span class="sxs-lookup"><span data-stu-id="cc10f-211">Here is a quick sample to show it in action with named matches.</span></span>

``` powershell
$message = 'my ssn is 123-23-3456 and credit card: 1234-5678-1234-5678'

switch -regex ($message)
{
    '(?<SSN>\d\d\d-\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a SSN: $($matches.SSN)"
    }
    '(?<CC>\d\d\d\d-\d\d\d\d-\d\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a credit card number: $($matches.CC)"
    }
    '(?<Phone>\d\d\d-\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a phone number: $($matches.Phone)"
    }
}
```

```Output
WARNING: message may contain a SSN: 123-23-3456
WARNING: message may contain a credit card number: 1234-5678-1234-5678
```

### <a name="null"></a><span data-ttu-id="cc10f-212">$null</span><span class="sxs-lookup"><span data-stu-id="cc10f-212">$null</span></span>

<span data-ttu-id="cc10f-213">可以匹配不一定为默认值的 `$null` 值。</span><span class="sxs-lookup"><span data-stu-id="cc10f-213">You can match a `$null` value that doesn't have to be the default.</span></span>

``` powershell
$value = $null

switch ( $value )
{
    $null
    {
        'Value is null'
    }
    default
    {
        'value is not null'
    }
}

```Output
Value is null
```

<span data-ttu-id="cc10f-214">对于空字符串也是如此。</span><span class="sxs-lookup"><span data-stu-id="cc10f-214">Same goes for an empty string.</span></span>

``` powershell
switch ( '' )
{
    ''
    {
        'Value is empty'
    }
    default
    {
        'value is a empty string'
    }
}

```Output
Value is empty
```

### <a name="constant-expression"></a><span data-ttu-id="cc10f-215">常量表达式</span><span class="sxs-lookup"><span data-stu-id="cc10f-215">Constant expression</span></span>

<span data-ttu-id="cc10f-216">Lee Dailey 指出，我们可以使用常量 `$true` 表达式来计算 `[bool]` 项。</span><span class="sxs-lookup"><span data-stu-id="cc10f-216">Lee Dailey pointed out that we can use a constant `$true` expression to evaluate `[bool]` items.</span></span>
<span data-ttu-id="cc10f-217">假设我们需要进行几个布尔检查。</span><span class="sxs-lookup"><span data-stu-id="cc10f-217">Imagine if we have several boolean checks that need to happen.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isSecure = $true

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isSecure
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Enabled-AdminMenu
```

<span data-ttu-id="cc10f-218">这是对若干个布尔字段的状态进行计算和执行操作的简便方法。</span><span class="sxs-lookup"><span data-stu-id="cc10f-218">This is a clean way to evaluate and take action on the status of several boolean fields.</span></span> <span data-ttu-id="cc10f-219">这样做的好处是，可以让一个匹配项来切换尚未计算的值的状态。</span><span class="sxs-lookup"><span data-stu-id="cc10f-219">The cool thing about this is that you can have one match flip the status of a value that hasn't been evaluated yet.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isAdmin = $false

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
        $isVisible = $true
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isAdmin
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Show-Animation
```

<span data-ttu-id="cc10f-220">在本示例中，将 `$isEnabled` 设置为 `$true` 可确保 `$isVisible` 也设置为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-220">Setting `$isEnabled` to `$true` in this example makes sure that `$isVisible` is also set to `$true`.</span></span> <span data-ttu-id="cc10f-221">然后，在计算 `$isVisible` 时，将调用其脚本块。</span><span class="sxs-lookup"><span data-stu-id="cc10f-221">Then when `$isVisible` gets evaluated, its scriptblock is invoked.</span></span> <span data-ttu-id="cc10f-222">这有点违反直觉，但却是对机制的巧妙使用。</span><span class="sxs-lookup"><span data-stu-id="cc10f-222">This is a bit counter-intuitive but is a clever use of the mechanics.</span></span>

### <a name="switch-automatic-variable"></a><span data-ttu-id="cc10f-223">$switch 自动变量</span><span class="sxs-lookup"><span data-stu-id="cc10f-223">$switch automatic variable</span></span>

<span data-ttu-id="cc10f-224">当 `switch` 处理其值时，将创建枚举器并称其为 `$switch`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-224">When the `switch` is processing its values, it creates an enumerator and calls it `$switch`.</span></span> <span data-ttu-id="cc10f-225">这是由 PowerShell 创建的自动变量，你可以直接对其进行操作。</span><span class="sxs-lookup"><span data-stu-id="cc10f-225">This is an automatic variable created by PowerShell and you can manipulate it directly.</span></span>

<span data-ttu-id="cc10f-226">这是 [/u/frmadsen](https://www.reddit.com/user/frmadsen) 向我指出的</span><span class="sxs-lookup"><span data-stu-id="cc10f-226">This was pointed out to me by [/u/frmadsen](https://www.reddit.com/user/frmadsen)</span></span>

<div class="reddit-embed" data-embed-media="www.redditmedia.com" data-embed-parent="false" data-embed-live="false" data-embed-uuid="8f6edbf1-abc6-4513-971e-ccd1d202889d" data-embed-created="2018-12-25T22:05:33.986Z"><span data-ttu-id="cc10f-227"><a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/">我（IT 学生）应该学习什么来掌握 PowerShell？</a> 讨论中的<a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/ecj2kji/">评论</a>。</span><span class="sxs-lookup"><span data-stu-id="cc10f-227"><a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/ecj2kji/">Comment</a> from discussion <a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/">What should I (IT student) learn to master PowerShell?</a>.</span></span></div><script async src="https://www.redditstatic.com/comment-embed.js"></script>

<span data-ttu-id="cc10f-228">这会为你提供以下结果：</span><span class="sxs-lookup"><span data-stu-id="cc10f-228">This gives you the results of:</span></span>

```Output
2
4
```

<span data-ttu-id="cc10f-229">通过向前移动枚举器，`switch` 不会处理下一项，但你可以直接访问该值。</span><span class="sxs-lookup"><span data-stu-id="cc10f-229">By moving the enumerator forward, the next item doesn't get processed by the `switch` but you can access that value directly.</span></span> <span data-ttu-id="cc10f-230">我称之为发疯。</span><span class="sxs-lookup"><span data-stu-id="cc10f-230">I would call it madness.</span></span>

## <a name="other-patterns"></a><span data-ttu-id="cc10f-231">其他模式</span><span class="sxs-lookup"><span data-stu-id="cc10f-231">Other patterns</span></span>

### <a name="hashtables"></a><span data-ttu-id="cc10f-232">哈希表</span><span class="sxs-lookup"><span data-stu-id="cc10f-232">Hashtables</span></span>

<span data-ttu-id="cc10f-233">我最受欢迎的一篇文章是关于[哈希表][]的。</span><span class="sxs-lookup"><span data-stu-id="cc10f-233">One of my most popular posts is the one I did on [hashtables][].</span></span> <span data-ttu-id="cc10f-234">`hashtable` 的用例之一是查找表。</span><span class="sxs-lookup"><span data-stu-id="cc10f-234">One of the use cases for a `hashtable` is to be a lookup table.</span></span> <span data-ttu-id="cc10f-235">这是一种常见模式的替代方法，`switch` 语句通常对该模式进行寻址。</span><span class="sxs-lookup"><span data-stu-id="cc10f-235">That is an alternate approach to a common pattern that a `switch` statement is often addressing.</span></span>

``` powershell
$day = 3

$lookup = @{
    0 = 'Sunday'
    1 = 'Monday'
    2 = 'Tuesday'
    3 = 'Wednesday'
    4 = 'Thursday'
    5 = 'Friday'
    6 = 'Saturday'
}

$lookup[$day]
```

```Output
Wednesday
```

<span data-ttu-id="cc10f-236">如果只是将 `switch` 用作查找，那么我通常会改用 `hashtable`。</span><span class="sxs-lookup"><span data-stu-id="cc10f-236">If I'm only using a `switch` as a lookup, I often use a `hashtable` instead.</span></span>

### <a name="enum"></a><span data-ttu-id="cc10f-237">枚举</span><span class="sxs-lookup"><span data-stu-id="cc10f-237">Enum</span></span>

<span data-ttu-id="cc10f-238">PowerShell 5.0 引入了 `Enum`，在这种情况下，它也是一个选项。</span><span class="sxs-lookup"><span data-stu-id="cc10f-238">PowerShell 5.0 introduced the `Enum` and it's also an option in this case.</span></span>

``` powershell
$day = 3

enum DayOfTheWeek {
    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
}

[DayOfTheWeek]$day
```

```Output
Wednesday
```

<span data-ttu-id="cc10f-239">我们会一直寻找不同的方法来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="cc10f-239">We could go all day looking at different ways to solve this problem.</span></span> <span data-ttu-id="cc10f-240">我只是想要确保你知道你拥有选择。</span><span class="sxs-lookup"><span data-stu-id="cc10f-240">I just wanted to make sure you knew you had options.</span></span>

## <a name="final-words"></a><span data-ttu-id="cc10f-241">结束语</span><span class="sxs-lookup"><span data-stu-id="cc10f-241">Final words</span></span>

<span data-ttu-id="cc10f-242">switch 语句表面上看起来很简单，但它提供了大多数人都不知道的一些高级功能。</span><span class="sxs-lookup"><span data-stu-id="cc10f-242">The switch statement is simple on the surface but it offers some advanced features that most people don't realize are available.</span></span> <span data-ttu-id="cc10f-243">这些功能结合在一起使其非常强大。</span><span class="sxs-lookup"><span data-stu-id="cc10f-243">Stringing those features together makes this a powerful feature.</span></span> <span data-ttu-id="cc10f-244">我希望你学到了一些之前不知道的内容。</span><span class="sxs-lookup"><span data-stu-id="cc10f-244">I hope you learned something that you had not realized before.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[original version]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[开关参数]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[switch parameters]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[使用正则表达式的多种方式]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[哈希表]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
