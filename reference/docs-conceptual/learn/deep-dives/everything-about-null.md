---
title: 关于 $null 的各项须知内容
description: PowerShell $null 通常看起来很简单，但却有很多细微的差别。 我们来详细了解一下 $null，这样你就知道当意外遇到 null 值时将发生的情况。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e0553a5e17450d8044f548792649369e99903850
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149470"
---
# <a name="everything-you-wanted-to-know-about-null"></a><span data-ttu-id="c45b4-104">关于 $null 的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="c45b4-104">Everything you wanted to know about $null</span></span>

<span data-ttu-id="c45b4-105">PowerShell `$null` 通常看起来很简单，但却有很多细微的差别。</span><span class="sxs-lookup"><span data-stu-id="c45b4-105">The PowerShell `$null` often appears to be simple but it has a lot of nuances.</span></span> <span data-ttu-id="c45b4-106">我们来详细了解一下 `$null`，这样你就知道当意外遇到 `$null` 值时将发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c45b4-106">Let's take a close look at `$null` so you know what happens when you unexpectedly run into a `$null` value.</span></span>

> [!NOTE]
> <span data-ttu-id="c45b4-107">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="c45b4-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="c45b4-108">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="c45b4-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="c45b4-109">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="c45b4-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-null"></a><span data-ttu-id="c45b4-110">什么是 NULL？</span><span class="sxs-lookup"><span data-stu-id="c45b4-110">What is NULL?</span></span>

<span data-ttu-id="c45b4-111">可以将 NULL 视为未知值或空值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-111">You can think of NULL as an unknown or empty value.</span></span> <span data-ttu-id="c45b4-112">在为变量赋值或分配对象之前，该变量为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c45b4-112">A variable is NULL until you assign a value or an object to it.</span></span> <span data-ttu-id="c45b4-113">这一点非常重要，因为某些命令需要值，并在值为 NULL 时生成错误。</span><span class="sxs-lookup"><span data-stu-id="c45b4-113">This can be important because there are some commands that require a value and generate errors if the value is NULL.</span></span>

### <a name="powershell-null"></a><span data-ttu-id="c45b4-114">PowerShell $null</span><span class="sxs-lookup"><span data-stu-id="c45b4-114">PowerShell $null</span></span>

<span data-ttu-id="c45b4-115">`$null` 是 PowerShell 中用于表示 NULL 的自动变量。</span><span class="sxs-lookup"><span data-stu-id="c45b4-115">`$null` is an automatic variable in PowerShell used to represent NULL.</span></span> <span data-ttu-id="c45b4-116">可以将其分配给变量，将其用于比较，以及将其用作集合中 NULL 值的占位符。</span><span class="sxs-lookup"><span data-stu-id="c45b4-116">You can assign it to variables, use it in comparisons and use it as a place holder for NULL in a collection.</span></span>

<span data-ttu-id="c45b4-117">PowerShell 将 `$null` 视为具有 NULL 值的对象。</span><span class="sxs-lookup"><span data-stu-id="c45b4-117">PowerShell treats `$null` as an object with a value of NULL.</span></span> <span data-ttu-id="c45b4-118">如果你使用其他语言，则这会与你的预期不同。</span><span class="sxs-lookup"><span data-stu-id="c45b4-118">This is different than what you may expect if you come from another language.</span></span>

## <a name="examples-of-null"></a><span data-ttu-id="c45b4-119">$null 示例</span><span class="sxs-lookup"><span data-stu-id="c45b4-119">Examples of $null</span></span>

<span data-ttu-id="c45b4-120">任何时候尝试使用尚未初始化的变量时，值都为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-120">Anytime you try to use a variable that you have not initialized, the value is `$null`.</span></span> <span data-ttu-id="c45b4-121">这是 `$null` 值进入代码的最常见方式之一。</span><span class="sxs-lookup"><span data-stu-id="c45b4-121">This is one of the most common ways that `$null` values sneak into your code.</span></span>

```powershell
PS> $null -eq $undefinedVariable
True
```

<span data-ttu-id="c45b4-122">如果变量名称键入错误，PowerShell 会将其视为不同的变量，且值为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-122">If you happen to mistype a variable name then PowerShell sees it as a different variable and the value is `$null`.</span></span>

<span data-ttu-id="c45b4-123">查找 `$null` 值的另一种方法是，当它们来自不提供任何结果的其他命令时。</span><span class="sxs-lookup"><span data-stu-id="c45b4-123">The other way you find `$null` values is when they come from other commands that don't give you any results.</span></span>

```powershell
PS> function Get-Nothing {}
PS> $value = Get-Nothing
PS> $null -eq $value
True
```

## <a name="impact-of-null"></a><span data-ttu-id="c45b4-124">$null 的影响</span><span class="sxs-lookup"><span data-stu-id="c45b4-124">Impact of $null</span></span>

<span data-ttu-id="c45b4-125">`$null` 值会以不同方式影响代码，具体取决于它们显示的位置。</span><span class="sxs-lookup"><span data-stu-id="c45b4-125">`$null` values impact your code differently depending on where they show up.</span></span>

### <a name="in-strings"></a><span data-ttu-id="c45b4-126">在字符串中</span><span class="sxs-lookup"><span data-stu-id="c45b4-126">In strings</span></span>

<span data-ttu-id="c45b4-127">如果在字符串中使用 `$null`，则其为空值（或空字符串）。</span><span class="sxs-lookup"><span data-stu-id="c45b4-127">If you use `$null` in a string, then it's a blank value (or empty string).</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is $value"
The value is
```

<span data-ttu-id="c45b4-128">这是我在日志消息中使用变量时喜欢将变量用括号括起来的原因之一。</span><span class="sxs-lookup"><span data-stu-id="c45b4-128">This is one of the reasons that I like to place brackets around variables when using them in log messages.</span></span> <span data-ttu-id="c45b4-129">当值位于字符串的末尾时，识别变量值的边缘更为重要。</span><span class="sxs-lookup"><span data-stu-id="c45b4-129">It's even more important to identify the edges of your variable values when the value is at the end of the string.</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is [$value]"
The value is []
```

<span data-ttu-id="c45b4-130">这会使空字符串和 `$null` 值易于发现。</span><span class="sxs-lookup"><span data-stu-id="c45b4-130">This makes empty strings and `$null` values easy to spot.</span></span>

### <a name="in-numeric-equation"></a><span data-ttu-id="c45b4-131">在数值公式中</span><span class="sxs-lookup"><span data-stu-id="c45b4-131">In numeric equation</span></span>

<span data-ttu-id="c45b4-132">当数值公式中使用 `$null` 值时，如果未生成错误，则结果无效。</span><span class="sxs-lookup"><span data-stu-id="c45b4-132">When a `$null` value is used in a numeric equation then your results are invalid if they don't give an error.</span></span> <span data-ttu-id="c45b4-133">有时 `$null` 的计算结果为 `0`，而其他时间生成完整结果 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-133">Sometimes the `$null` evaluates to `0` and other times it makes the whole result `$null`.</span></span>
<span data-ttu-id="c45b4-134">下面是一个包含乘法的示例，其生成 0 或 `$null`，具体取决于值的顺序。</span><span class="sxs-lookup"><span data-stu-id="c45b4-134">Here is an example with multiplication that gives 0 or `$null` depending on the order of the values.</span></span>

```powershell
PS> $null * 5
PS> $null -eq ( $null * 5 )
True

PS> 5 * $null
0
PS> $null -eq ( 5 * $null )
False
```

### <a name="in-place-of-a-collection"></a><span data-ttu-id="c45b4-135">取代集合</span><span class="sxs-lookup"><span data-stu-id="c45b4-135">In place of a collection</span></span>

<span data-ttu-id="c45b4-136">集合允许你使用索引来访问值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-136">A collection allow you use an index to access values.</span></span> <span data-ttu-id="c45b4-137">如果尝试对实际为 `null` 的集合建立索引，将生成此错误：`Cannot index into a null array`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-137">If you try to index into a collection that is actually `null`, you get this error: `Cannot index into a null array`.</span></span>

```powershell
PS> $value = $null
PS> $value[10]
Cannot index into a null array.
At line:1 char:1
+ $value[10]
+ ~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : NullArray
```

<span data-ttu-id="c45b4-138">如果你有一个集合，但尝试访问不在此集合中的元素，将生成 `$null` 结果。</span><span class="sxs-lookup"><span data-stu-id="c45b4-138">If you have a collection but try to access an element that is not in the collection, you get a `$null` result.</span></span>

```powershell
$array = @( 'one','two','three' )
$null -eq $array[100]
True
```

### <a name="in-place-of-an-object"></a><span data-ttu-id="c45b4-139">取代对象</span><span class="sxs-lookup"><span data-stu-id="c45b4-139">In place of an object</span></span>

<span data-ttu-id="c45b4-140">如果尝试访问不含指定属性的对象的某个属性或子属性，将得到 `$null` 值，就像使用未定义的变量一样。</span><span class="sxs-lookup"><span data-stu-id="c45b4-140">If you try to access a property or sub property of an object that doesn't have the specified property, you get a `$null` value like you would for an undefined variable.</span></span> <span data-ttu-id="c45b4-141">在此情况中，变量为 `$null` 或实际对象无关紧要。</span><span class="sxs-lookup"><span data-stu-id="c45b4-141">It doesn't matter if the variable is `$null` or an actual object in this case.</span></span>

```powershell
PS> $null -eq $undefined.some.fake.property
True

PS> $date = Get-Date
PS> $null -eq $date.some.fake.property
True
```

### <a name="method-on-a-null-valued-expression"></a><span data-ttu-id="c45b4-142">null 值表达式上的方法</span><span class="sxs-lookup"><span data-stu-id="c45b4-142">Method on a null-valued expression</span></span>

<span data-ttu-id="c45b4-143">在 `$null` 对象上调用方法将引发 `RuntimeException`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-143">Calling a method on a `$null` object throws a `RuntimeException`.</span></span>

```powershell
PS> $value = $null
PS> $value.toString()
You cannot call a method on a null-valued expression.
At line:1 char:1
+ $value.tostring()
+ ~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
```

<span data-ttu-id="c45b4-144">每当我看到这句 `You cannot call a method on a null-valued expression` 时，我首先会查找在变量上调用方法的位置，而不是检查是否有 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-144">Whenever I see the phrase `You cannot call a method on a null-valued expression` then the first thing I look for are places where I am calling a method on a variable without first checking it for `$null`.</span></span>

## <a name="checking-for-null"></a><span data-ttu-id="c45b4-145">检查 $null</span><span class="sxs-lookup"><span data-stu-id="c45b4-145">Checking for $null</span></span>

<span data-ttu-id="c45b4-146">你可能已注意到，在我的示例中，检查 `$null` 时，始终会将 `$null` 放在左侧。</span><span class="sxs-lookup"><span data-stu-id="c45b4-146">You may have noticed that I always place the `$null` on the left when checking for `$null` in my examples.</span></span> <span data-ttu-id="c45b4-147">这是有意为之，并被视为 PowerShell 最佳实践。</span><span class="sxs-lookup"><span data-stu-id="c45b4-147">This is intentional and accepted as a PowerShell best practice.</span></span> <span data-ttu-id="c45b4-148">在某些情况下，将其放在右侧不会生成预期结果。</span><span class="sxs-lookup"><span data-stu-id="c45b4-148">There are some scenarios where placing it on the right doesn't give you the expected result.</span></span>

<span data-ttu-id="c45b4-149">查看下一个示例，并尝试预测结果：</span><span class="sxs-lookup"><span data-stu-id="c45b4-149">Look at this next example and try to predict the results:</span></span>

```powershell
if ( $value -eq $null )
{
    'The array is $null'
}
if ( $value -ne $null )
{
    'The array is not $null'
}
```

<span data-ttu-id="c45b4-150">如果我未定义 `$value`，则第一个的计算结果为 `$true`，消息为 `The array is $null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-150">If I do not define `$value`, the first one evaluates to `$true` and our message is `The array is $null`.</span></span> <span data-ttu-id="c45b4-151">这里的陷阱是，可以创建一个 `$value`，使两者都为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-151">The trap here is that it's possible to create a `$value` that allows both of them to be `$false`</span></span>

```powershell
$value = @( $null )
```

<span data-ttu-id="c45b4-152">在这种情况下，`$value` 是一个包含 `$null` 的数组。</span><span class="sxs-lookup"><span data-stu-id="c45b4-152">In this case, the `$value` is an array that contains a `$null`.</span></span> <span data-ttu-id="c45b4-153">`-eq` 检查数组中的每个值，并返回匹配的 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-153">The `-eq` checks every value in the array and returns the `$null` that is matched.</span></span> <span data-ttu-id="c45b4-154">其计算结果为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-154">This evaluates to `$false`.</span></span> <span data-ttu-id="c45b4-155">`-ne` 返回与 `$null` 不匹配的所有内容，在这种情况下不会生成任何结果（计算结果也为 `$false`）。</span><span class="sxs-lookup"><span data-stu-id="c45b4-155">The `-ne` returns everything that doesn't match `$null` and in this case there are no results (This also evaluates to `$false`).</span></span> <span data-ttu-id="c45b4-156">没有一项的计算结果为 `$true`，尽管看起来其中一个应该是这个结果。</span><span class="sxs-lookup"><span data-stu-id="c45b4-156">Neither one is `$true` even though it looks like one of them should be.</span></span>

<span data-ttu-id="c45b4-157">我们不仅可以创建一个值来使这两项的计算结果为 `$false`，还可以创建一个值使这两项的计算结果为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-157">Not only can we create a value that makes both of them evaluate to `$false`, it's possible to create a value where they both evaluate to `$true`.</span></span> <span data-ttu-id="c45b4-158">Mathias Jessen (@IISResetMe) 发表了一篇[好文章][]，深入探究了这种方案。</span><span class="sxs-lookup"><span data-stu-id="c45b4-158">Mathias Jessen (@IISResetMe) has a [good post][] that dives into that scenario.</span></span>

### <a name="psscriptanalyzer-and-vscode"></a><span data-ttu-id="c45b4-159">PSScriptAnalyzer 和 VSCode</span><span class="sxs-lookup"><span data-stu-id="c45b4-159">PSScriptAnalyzer and VSCode</span></span>

<span data-ttu-id="c45b4-160">[PSScriptAnalyzer][] 模块具有一个检查此问题的规则，称为 `PSPossibleIncorrectComparisonWithNull`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-160">The [PSScriptAnalyzer][] module has a rule that checks for this issue called `PSPossibleIncorrectComparisonWithNull`.</span></span>

```powershell
PS> Invoke-ScriptAnalyzer ./myscript.ps1

RuleName                              Message
--------                              -------
PSPossibleIncorrectComparisonWithNull $null should be on the left side of equality comparisons.
```

<span data-ttu-id="c45b4-161">由于 VS Code 也使用 PSScriptAnalyser 规则，因此它也会在脚本中突出显示或将其标识为问题。</span><span class="sxs-lookup"><span data-stu-id="c45b4-161">Because VS Code uses the PSScriptAnalyser rules too, it also highlights or identifies this as a problem in your script.</span></span>

### <a name="simple-if-check"></a><span data-ttu-id="c45b4-162">简单 if 检查</span><span class="sxs-lookup"><span data-stu-id="c45b4-162">Simple if check</span></span>

<span data-ttu-id="c45b4-163">检查非 $null 值的常见方法是使用简单的 `if()` 语句，而不进行比较。</span><span class="sxs-lookup"><span data-stu-id="c45b4-163">A common way that people check for a non-$null value is to use a simple `if()` statement without the comparison.</span></span>

```powershell
if ( $value )
{
    Do-Something
}
```

<span data-ttu-id="c45b4-164">如果值为 `$null`，则计算结果为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-164">If the value is `$null`, this evaluates to `$false`.</span></span> <span data-ttu-id="c45b4-165">此值易于读取，但请注意，它会准确地查找你希望它查找的内容。</span><span class="sxs-lookup"><span data-stu-id="c45b4-165">This is easy to read, but be careful that it's looking for exactly what you're expecting it to look for.</span></span> <span data-ttu-id="c45b4-166">我将该行代码解读为：</span><span class="sxs-lookup"><span data-stu-id="c45b4-166">I read that line of code as:</span></span>

> <span data-ttu-id="c45b4-167">如果 `$value` 具有值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-167">If `$value` has a value.</span></span>

<span data-ttu-id="c45b4-168">但这并不是完整内容。</span><span class="sxs-lookup"><span data-stu-id="c45b4-168">But that's not the whole story.</span></span> <span data-ttu-id="c45b4-169">该行的实际内容为：</span><span class="sxs-lookup"><span data-stu-id="c45b4-169">That line is actually saying:</span></span>

> <span data-ttu-id="c45b4-170">如果 `$value` 不是 `$null` 或 `0` 或 `$false` 或 `empty string`</span><span class="sxs-lookup"><span data-stu-id="c45b4-170">If `$value` is not `$null` or `0` or `$false` or an `empty string`</span></span>

<span data-ttu-id="c45b4-171">下面是该语句的一个更完整的示例。</span><span class="sxs-lookup"><span data-stu-id="c45b4-171">Here is a more complete sample of that statement.</span></span>

```powershell
if ( $null -ne $value -and
        $value -ne 0 -and
        $value -ne '' -and
        $value -ne $false )
{
    Do-Something
}
```

<span data-ttu-id="c45b4-172">只要你记住其他值被视为 `$false` 而不只是变量具有值，就完全可以使用基本 `if` 检查。</span><span class="sxs-lookup"><span data-stu-id="c45b4-172">It's perfectly OK to use a basic `if` check as long as you remember those other values count as `$false` and not just that a variable has a value.</span></span>

<span data-ttu-id="c45b4-173">几天前重构某些代码时，我遇到了此问题。</span><span class="sxs-lookup"><span data-stu-id="c45b4-173">I ran into this issue when refactoring some code a few days ago.</span></span> <span data-ttu-id="c45b4-174">它的基本属性检查如下所示。</span><span class="sxs-lookup"><span data-stu-id="c45b4-174">It had a basic property check like this.</span></span>

```powershell
if ( $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="c45b4-175">仅当对象属性存在时，我才希望为其分配值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-175">I wanted to assign a value to the object property only if it existed.</span></span> <span data-ttu-id="c45b4-176">在大多数情况下，原始对象的值在 `if` 语句中的计算结果为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-176">In most cases, the original object had a value that would evaluate to `$true` in the `if` statement.</span></span> <span data-ttu-id="c45b4-177">但我遇到了一个问题，即偶尔未设置此值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-177">But I ran into an issue where the value was occasionally not getting set.</span></span> <span data-ttu-id="c45b4-178">我调试了代码，发现该对象具有属性，但它是一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-178">I debugged the code and found that the object had the property but it was a blank string value.</span></span> <span data-ttu-id="c45b4-179">这会阻止其使用以前的逻辑进行更新。</span><span class="sxs-lookup"><span data-stu-id="c45b4-179">This prevented it from ever getting updated with the previous logic.</span></span> <span data-ttu-id="c45b4-180">因此，我添加了一个适当的 `$null` 检查，一切正常。</span><span class="sxs-lookup"><span data-stu-id="c45b4-180">So I added a proper `$null` check and everything worked.</span></span>

```powershell
if ( $null -ne $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="c45b4-181">这类小 bug 很难发现，也促使我主动检查 `$null` 值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-181">It's little bugs like these that are hard to spot and make me aggressively check values for `$null`.</span></span>

## <a name="nullcount"></a><span data-ttu-id="c45b4-182">$null.Count</span><span class="sxs-lookup"><span data-stu-id="c45b4-182">$null.Count</span></span>

<span data-ttu-id="c45b4-183">如果尝试访问 `$null` 值的属性，则该属性也为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-183">If you try to access a property on a `$null` value, that the property is also `$null`.</span></span> <span data-ttu-id="c45b4-184">`count` 属性是此规则的例外情况。</span><span class="sxs-lookup"><span data-stu-id="c45b4-184">The `count` property is the exception to this rule.</span></span>

```powershell
PS> $value = $null
PS> $value.count
0
```

<span data-ttu-id="c45b4-185">如果有 `$null` 值，则 `count` 为 `0`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-185">When you have a `$null` value, then the `count` is `0`.</span></span> <span data-ttu-id="c45b4-186">PowerShell 会添加此特殊属性。</span><span class="sxs-lookup"><span data-stu-id="c45b4-186">This special property is added by PowerShell.</span></span>

### <a name="pscustomobject-count"></a><span data-ttu-id="c45b4-187">[PSCustomObject] 计数</span><span class="sxs-lookup"><span data-stu-id="c45b4-187">[PSCustomObject] Count</span></span>

<span data-ttu-id="c45b4-188">PowerShell 中的几乎所有对象均具有该计数属性。</span><span class="sxs-lookup"><span data-stu-id="c45b4-188">Almost all objects in PowerShell have that count property.</span></span> <span data-ttu-id="c45b4-189">一个重要的例外是 Windows PowerShell 5.1 中的 `[PSCustomObject]`（此问题在 PowerShell 6.0 中得以修复）。</span><span class="sxs-lookup"><span data-stu-id="c45b4-189">One important exception is the `[PSCustomObject]` in Windows PowerShell 5.1 (This is fixed in PowerShell 6.0).</span></span> <span data-ttu-id="c45b4-190">它没有计数属性，因此如果你尝试使用它，将得到 `$null` 值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-190">It doesn't have a count property so you get a `$null` value if you try to use it.</span></span> <span data-ttu-id="c45b4-191">我在这里提到这一点，这样你就不会尝试使用 `.Count` 代替 `$null` 检查。</span><span class="sxs-lookup"><span data-stu-id="c45b4-191">I call this out here so that you don't try to use `.Count` instead of a `$null` check.</span></span>

<span data-ttu-id="c45b4-192">在 Windows PowerShell 5.1 和 PowerShell 6.0 上运行此示例可生成不同的结果。</span><span class="sxs-lookup"><span data-stu-id="c45b4-192">Running this example on Windows PowerShell 5.1 and PowerShell 6.0 gives you different results.</span></span>

```powershell
$value = [PSCustomObject]@{Name='MyObject'}
if ( $value.count -eq 1 )
{
    "We have a value"
}
```

## <a name="empty-null"></a><span data-ttu-id="c45b4-193">空 null 值</span><span class="sxs-lookup"><span data-stu-id="c45b4-193">Empty null</span></span>

<span data-ttu-id="c45b4-194">有一种特殊类型的 `$null`，其行为与其他类型不同。</span><span class="sxs-lookup"><span data-stu-id="c45b4-194">There is one special type of `$null` that acts differently than the others.</span></span> <span data-ttu-id="c45b4-195">我要称它为空 `$null`，但它实际上是 [System.Management.Automation.Internal.AutomationNull][]。</span><span class="sxs-lookup"><span data-stu-id="c45b4-195">I am going to call it the empty `$null` but it's really a [System.Management.Automation.Internal.AutomationNull][].</span></span> <span data-ttu-id="c45b4-196">此空 `$null` 是从不返回任何值的函数或脚本块得到的结（空结果）。</span><span class="sxs-lookup"><span data-stu-id="c45b4-196">This empty `$null` is the one you get as the result of a function or script block that returns nothing (a void result).</span></span>

```powershell
PS> function Get-Nothing {}
PS> $nothing = Get-Nothing
PS> $null -eq $nothing
True
```

<span data-ttu-id="c45b4-197">如果将其与 `$null` 比较，将得到值 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-197">If you compare it with `$null`, you get a `$null` value.</span></span> <span data-ttu-id="c45b4-198">在需要值的计算中使用时，此值始终为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-198">When used in an evaluation where a value is required, the value is always `$null`.</span></span> <span data-ttu-id="c45b4-199">但如果将其放在数组中，则会将其视为与空数组相同。</span><span class="sxs-lookup"><span data-stu-id="c45b4-199">But if you place it inside an array, it's treated the same as an empty array.</span></span>

```powershell
PS> $containempty = @( @() )
PS> $containnothing = @($nothing)
PS> $containnull = @($null)

PS> $containempty.count
0
PS> $containnothing.count
0
PS> $containnull.count
1
```

<span data-ttu-id="c45b4-200">你可以有一个数组，其包含一个 `$null` 值，且其 `count` 为 `1`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-200">You can have an array that contains one `$null` value and its `count` is `1`.</span></span> <span data-ttu-id="c45b4-201">但如果将空结果置于数组中，则不会将其计为一个项。</span><span class="sxs-lookup"><span data-stu-id="c45b4-201">But if you place an empty result inside an array then it's not counted as an item.</span></span> <span data-ttu-id="c45b4-202">计数为 `0`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-202">The count is `0`.</span></span>

<span data-ttu-id="c45b4-203">如果将空 `$null` 视为集合，则它为空。</span><span class="sxs-lookup"><span data-stu-id="c45b4-203">If you treat the empty `$null` like a collection, then it's empty.</span></span>

### <a name="pipeline"></a><span data-ttu-id="c45b4-204">管道</span><span class="sxs-lookup"><span data-stu-id="c45b4-204">Pipeline</span></span>

<span data-ttu-id="c45b4-205">出现差异的主要地方是使用管道时。</span><span class="sxs-lookup"><span data-stu-id="c45b4-205">The primary place you see the difference is when using the pipeline.</span></span> <span data-ttu-id="c45b4-206">可以通过管道传递 `$null` 值，但不能传递空 `$null` 值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-206">You can pipe a `$null` value but not an empty `$null` value.</span></span>

```powershell
PS> $null | ForEach-Object{ Write-Output 'NULL Value' }
'NULL Value'
PS> $nothing | ForEach-Object{ Write-Output 'No Value' }
```

<span data-ttu-id="c45b4-207">根据你的代码，你应在逻辑中考虑 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-207">Depending on your code, you should account for the `$null` in your logic.</span></span>

<span data-ttu-id="c45b4-208">先检查 `$null`</span><span class="sxs-lookup"><span data-stu-id="c45b4-208">Either check for `$null` first</span></span>

- <span data-ttu-id="c45b4-209">筛选出管道上的 null (`... | Where {$null -ne $_} | ...`)</span><span class="sxs-lookup"><span data-stu-id="c45b4-209">Filter out null on the pipeline (`... | Where {$null -ne $_} | ...`)</span></span>
- <span data-ttu-id="c45b4-210">在管道函数中进行处理</span><span class="sxs-lookup"><span data-stu-id="c45b4-210">Handle it in the pipeline function</span></span>

## <a name="foreach"></a><span data-ttu-id="c45b4-211">foreach</span><span class="sxs-lookup"><span data-stu-id="c45b4-211">foreach</span></span>

<span data-ttu-id="c45b4-212">我最喜欢的 `foreach` 功能之一是它不会枚举 `$null` 集合。</span><span class="sxs-lookup"><span data-stu-id="c45b4-212">One of my favorite features of `foreach` is that it doesn't enumerate over a `$null` collection.</span></span>

```powershell
foreach ( $node in $null )
{
    #skipped
}
```

<span data-ttu-id="c45b4-213">这样，我就不必在枚举前对集合执行 `$null` 检查。</span><span class="sxs-lookup"><span data-stu-id="c45b4-213">This saves me from having to `$null` check the collection before I enumerate it.</span></span> <span data-ttu-id="c45b4-214">如果你有一个 `$null` 值的集合，`$node` 仍可以为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-214">If you have a collection of `$null` values, the `$node` can still be `$null`.</span></span>

<span data-ttu-id="c45b4-215">从 PowerShell 3.0 起，Foreach 开始以此方式运行。</span><span class="sxs-lookup"><span data-stu-id="c45b4-215">The foreach started working this way with PowerShell 3.0.</span></span> <span data-ttu-id="c45b4-216">如果你使用的是较低版本，则不会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="c45b4-216">If you happen to be on an older version, then this is not the case.</span></span> <span data-ttu-id="c45b4-217">在向后移植代码以实现 2.0 兼容性时，这是要注意的重要更改之一。</span><span class="sxs-lookup"><span data-stu-id="c45b4-217">This is one of the important changes to be aware of when back-porting code for 2.0 compatibility.</span></span>

## <a name="value-types"></a><span data-ttu-id="c45b4-218">值类型</span><span class="sxs-lookup"><span data-stu-id="c45b4-218">Value types</span></span>

<span data-ttu-id="c45b4-219">在技术上，只有引用类型可以为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-219">Technically, only reference types can be `$null`.</span></span> <span data-ttu-id="c45b4-220">但 PowerShell 非常宽松，允许变量为任意类型。</span><span class="sxs-lookup"><span data-stu-id="c45b4-220">But PowerShell is very generous and allows for variables to be any type.</span></span> <span data-ttu-id="c45b4-221">如果决定强键入值类型，其不能为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-221">If you decide to strongly type a value type, it cannot be `$null`.</span></span>
<span data-ttu-id="c45b4-222">PowerShell 会将 `$null` 转换为许多类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-222">PowerShell converts `$null` to a default value for many types.</span></span>

```powershell
PS> [int]$number = $null
PS> $number
0

PS> [bool]$boolean = $null
PS> $boolean
False

PS> [string]$string = $null
PS> $string -eq ''
True
```

<span data-ttu-id="c45b4-223">某些类型从 `$null` 转换无效。</span><span class="sxs-lookup"><span data-stu-id="c45b4-223">There are some types that do not have a valid conversion from `$null`.</span></span> <span data-ttu-id="c45b4-224">这些类型会生成 `Cannot convert null to type` 错误。</span><span class="sxs-lookup"><span data-stu-id="c45b4-224">These types generate a `Cannot convert null to type` error.</span></span>

```powershell
PS> [datetime]$date = $null
Cannot convert null to type "System.DateTime".
At line:1 char:1
+ [datetime]$date = $null
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : MetadataError: (:) [], ArgumentTransformationMetadataException
    + FullyQualifiedErrorId : RuntimeException
```

### <a name="function-parameters"></a><span data-ttu-id="c45b4-225">函数参数</span><span class="sxs-lookup"><span data-stu-id="c45b4-225">Function parameters</span></span>

<span data-ttu-id="c45b4-226">在函数参数中使用强类型值非常常见。</span><span class="sxs-lookup"><span data-stu-id="c45b4-226">Using a strongly typed values in function parameters is very common.</span></span> <span data-ttu-id="c45b4-227">我们通常学习了如何定义参数的类型，即使我们倾向于不在脚本中定义其他变量的类型也是如此。</span><span class="sxs-lookup"><span data-stu-id="c45b4-227">We generally learn to define the types of our parameters even if we tend not to define the types of other variables in our scripts.</span></span> <span data-ttu-id="c45b4-228">函数中可能已有一些强类型变量，你甚至可能没有意识到。</span><span class="sxs-lookup"><span data-stu-id="c45b4-228">You may already have some strongly typed variables in your functions and not even realize it.</span></span>

```powershell
function Do-Something
{
    param(
        [String] $Value
    )
}
```

<span data-ttu-id="c45b4-229">将参数类型设置为 `string` 后，值永远不得为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-229">As soon as you set the type of the parameter as a `string`, the value can never be `$null`.</span></span> <span data-ttu-id="c45b4-230">通常会检查值是否为 `$null`，以了解用户是否提供了值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-230">It's common to check if a value is `$null` to see if the user provided a value or not.</span></span>

```powershell
if ( $null -ne $Value ){...}
```

<span data-ttu-id="c45b4-231">如果未提供任何值，则 `$Value` 为空字符串 `''`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-231">`$Value` is an empty string `''` when no value is provided.</span></span> <span data-ttu-id="c45b4-232">改为使用自动变量 `$PSBoundParameters.Value`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-232">Use the automatic variable `$PSBoundParameters.Value` instead.</span></span>

```powershell
if ( $null -ne $PSBoundParameters.Value ){...}
```

<span data-ttu-id="c45b4-233">`$PSBoundParameters` 仅包含调用函数时指定的参数。</span><span class="sxs-lookup"><span data-stu-id="c45b4-233">`$PSBoundParameters` only contains the parameters that were specified when the function was called.</span></span>
<span data-ttu-id="c45b4-234">你还可以使用 `ContainsKey` 方法来检查属性。</span><span class="sxs-lookup"><span data-stu-id="c45b4-234">You can also use the `ContainsKey` method to check for the property.</span></span>

```powershell
if ( $PSBoundParameters.ContainsKey('Value') ){...}
```

### <a name="isnotnullorempty"></a><span data-ttu-id="c45b4-235">IsNotNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="c45b4-235">IsNotNullOrEmpty</span></span>

<span data-ttu-id="c45b4-236">如果值为字符串，则可以同时使用静态字符串函数检查值为 `$null` 还是空字符串。</span><span class="sxs-lookup"><span data-stu-id="c45b4-236">If the value is a string, you can use a static string function to check if the value is `$null` or an empty string at the same time.</span></span>

```powershell
if ( -not [string]::IsNullOrEmpty( $value ) ){...}
```

<span data-ttu-id="c45b4-237">在我知道值类型应为字符串时，我发现自己经常使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="c45b4-237">I find myself using this often when I know the value type should be a string.</span></span>

## <a name="when-i-null-check"></a><span data-ttu-id="c45b4-238">当我检查 $null 时</span><span class="sxs-lookup"><span data-stu-id="c45b4-238">When I $null check</span></span>

<span data-ttu-id="c45b4-239">我是一个防守型脚本编写者。</span><span class="sxs-lookup"><span data-stu-id="c45b4-239">I am a defensive scripter.</span></span> <span data-ttu-id="c45b4-240">每次调用函数并将其分配给变量时，我都会在其中检查 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-240">Anytime I call a function and assign it to a variable, I check it for `$null`.</span></span>

```powershell
$userList = Get-ADUser kevmar
if ($null -ne $userList){...}
```

<span data-ttu-id="c45b4-241">与 `try/catch` 相比，我更喜欢使用 `if` 或 `foreach`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-241">I much prefer using `if` or `foreach` over using `try/catch`.</span></span> <span data-ttu-id="c45b4-242">别误会，我仍然会大量使用 `try/catch`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-242">Don't get me wrong, I still use `try/catch` a lot.</span></span> <span data-ttu-id="c45b4-243">但如果我可以测试错误条件或空结果集，则可以使我的异常处理用于真正的异常。</span><span class="sxs-lookup"><span data-stu-id="c45b4-243">But if I can test for an error condition or an empty set of results, I can allow my exception handling be for true exceptions.</span></span>

<span data-ttu-id="c45b4-244">在对值编制索引或为对象调用方法之前，我还倾向于检查 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-244">I also tend to check for `$null` before I index into a value or call methods on an object.</span></span> <span data-ttu-id="c45b4-245">对 `$null` 对象执行这两个操作失败，因此，我发现最好先对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="c45b4-245">These two actions fail for a `$null` object so I find it important to validate them first.</span></span> <span data-ttu-id="c45b4-246">我已经在本文前面介绍了这些方案。</span><span class="sxs-lookup"><span data-stu-id="c45b4-246">I already covered those scenarios earlier in this post.</span></span>

### <a name="no-results-scenario"></a><span data-ttu-id="c45b4-247">无结果方案</span><span class="sxs-lookup"><span data-stu-id="c45b4-247">No results scenario</span></span>

<span data-ttu-id="c45b4-248">了解这一点很重要：不同的函数和命令以不同方式处理无结果方案。</span><span class="sxs-lookup"><span data-stu-id="c45b4-248">It's important to know that different functions and commands handle the no results scenario differently.</span></span> <span data-ttu-id="c45b4-249">许多 PowerShell 命令返回空 `$null` 和错误流中的一个错误。</span><span class="sxs-lookup"><span data-stu-id="c45b4-249">Many PowerShell commands return the empty `$null` and an error in the error stream.</span></span> <span data-ttu-id="c45b4-250">但其他命令会引发异常或向你提供状态对象。</span><span class="sxs-lookup"><span data-stu-id="c45b4-250">But others throw exceptions or give you a status object.</span></span> <span data-ttu-id="c45b4-251">但你仍可以决定是否要了解你所使用的命令如何处理无结果和错误方案。</span><span class="sxs-lookup"><span data-stu-id="c45b4-251">It's still up to you to know how the commands you use deal with the no results and error scenarios.</span></span>

## <a name="initializing-to-null"></a><span data-ttu-id="c45b4-252">初始化至 $null</span><span class="sxs-lookup"><span data-stu-id="c45b4-252">Initializing to $null</span></span>

<span data-ttu-id="c45b4-253">我养成的一个习惯是，在使用之前初始化所有变量。</span><span class="sxs-lookup"><span data-stu-id="c45b4-253">One habit that I have picked up is initializing all my variables before I use them.</span></span> <span data-ttu-id="c45b4-254">在其他语言中必须执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c45b4-254">You are required to do this in other languages.</span></span> <span data-ttu-id="c45b4-255">在函数顶部或在输入 foreach 循环时，我会定义正在使用的所有值。</span><span class="sxs-lookup"><span data-stu-id="c45b4-255">At the top of my function or as I enter a foreach loop, I define all the values that I'm using.</span></span>

<span data-ttu-id="c45b4-256">下面是一个方案，希望你能详细了解。</span><span class="sxs-lookup"><span data-stu-id="c45b4-256">Here is a scenario that I want you to take a close look at.</span></span> <span data-ttu-id="c45b4-257">以下是我之前追踪的一个 bug 示例。</span><span class="sxs-lookup"><span data-stu-id="c45b4-257">It's an example of a bug I had to chase down before.</span></span>

```powershell
function Do-Something
{
    foreach ( $node in 1..6 )
    {
        try
        {
            $result = Get-Something -ID $node
        }
        catch
        {
            Write-Verbose "[$result] not valid"
        }

        if ( $null -ne $result )
        {
            Update-Something $result
        }
    }
}
```

<span data-ttu-id="c45b4-258">这里的预期目标是 `Get-Something` 返回一个结果或空 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-258">The expectation here is that `Get-Something` returns either a result or an empty `$null`.</span></span> <span data-ttu-id="c45b4-259">如果出现错误，我们会记录。</span><span class="sxs-lookup"><span data-stu-id="c45b4-259">If there is an error, we log it.</span></span> <span data-ttu-id="c45b4-260">然后我们进行检查，以确保在处理之前得到了有效的结果。</span><span class="sxs-lookup"><span data-stu-id="c45b4-260">Then we check to make sure we got a valid result before processing it.</span></span>

<span data-ttu-id="c45b4-261">隐藏在此代码中的 bug 是当 `Get-Something` 引发异常且未给 `$result` 赋值时。</span><span class="sxs-lookup"><span data-stu-id="c45b4-261">The bug hiding in this code is when `Get-Something` throws an exception and doesn't assign a value to `$result`.</span></span> <span data-ttu-id="c45b4-262">它在赋值之前就失败了，因此我们不会将 `$null` 赋予 `$result` 变量。</span><span class="sxs-lookup"><span data-stu-id="c45b4-262">It fails before the assignment so we don't even assign `$null` to the `$result` variable.</span></span> <span data-ttu-id="c45b4-263">`$result` 仍包含之前来自其他迭代的有效 `$result`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-263">`$result` still contains the previous valid `$result` from other iterations.</span></span>
<span data-ttu-id="c45b4-264">`Update-Something` 在此示例中对同一对象执行多次。</span><span class="sxs-lookup"><span data-stu-id="c45b4-264">`Update-Something` to execute multiple times on the same object in this example.</span></span>

<span data-ttu-id="c45b4-265">我在 foreach 循环内部将 `$result` 设置为 `$null`，然后使用它来缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="c45b4-265">I set `$result` to `$null` right inside the foreach loop before I use it to mitigate this issue.</span></span>

```powershell
foreach ( $node in 1..6 )
{
    $result = $null
    try
    {
        ...
```

### <a name="scope-issues"></a><span data-ttu-id="c45b4-266">作用域问题</span><span class="sxs-lookup"><span data-stu-id="c45b4-266">Scope issues</span></span>

<span data-ttu-id="c45b4-267">这也有助于缓解作用域问题。</span><span class="sxs-lookup"><span data-stu-id="c45b4-267">This also helps mitigate scoping issues.</span></span> <span data-ttu-id="c45b4-268">在该示例中，我们在循环中反复将值赋予 `$result`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-268">In that example, we assign values to `$result` over and over in a loop.</span></span> <span data-ttu-id="c45b4-269">但由于 PowerShell 允许来自函数外部的变量值渗透到当前函数的作用域中，因此在函数内初始化它们可减少可能通过这种方式引入的 bug。</span><span class="sxs-lookup"><span data-stu-id="c45b4-269">But because PowerShell allows variable values from outside the function to bleed into the scope of the current function, initializing them inside your function mitigates bugs that can be introduced that way.</span></span>

<span data-ttu-id="c45b4-270">如果函数中未初始化的变量在父作用域中设置为一个值，其不会为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-270">An uninitialized variable in your function is not `$null` if it's set to a value in a parent scope.</span></span>
<span data-ttu-id="c45b4-271">父作用域可能是调用你的函数并使用相同变量名称的另一个函数。</span><span class="sxs-lookup"><span data-stu-id="c45b4-271">The parent scope could be another function that calls your function and uses the same variable names.</span></span>

<span data-ttu-id="c45b4-272">如果我使用同一个 `Do-something` 示例并删除循环，最终就会看到类似于以下示例的内容：</span><span class="sxs-lookup"><span data-stu-id="c45b4-272">If I take that same `Do-something` example and remove the loop, I would end up with something that looks like this example:</span></span>

```powershell
function Invoke-Something
{
    $result = 'ParentScope'
    Do-Something
}

function Do-Something
{
    try
    {
        $result = Get-Something -ID $node
    }
    catch
    {
        Write-Verbose "[$result] not valid"
    }

    if ( $null -ne $result )
    {
        Update-Something $result
    }
}
```

<span data-ttu-id="c45b4-273">如果对 `Get-Something` 的调用引发了异常，则我的 `$null` 检查将从 `Invoke-Something` 查找 `$result`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-273">If the call to `Get-Something` throws an exception, then my `$null` check finds the `$result` from `Invoke-Something`.</span></span> <span data-ttu-id="c45b4-274">初始化函数内的值会缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="c45b4-274">Initializing the value inside your function mitigates this issue.</span></span>

<span data-ttu-id="c45b4-275">命名变量很难，因此，作者通常会在多个函数中使用相同的变量名称。</span><span class="sxs-lookup"><span data-stu-id="c45b4-275">Naming variables is hard and it's common for an author to use the same variable names in multiple functions.</span></span> <span data-ttu-id="c45b4-276">我一直在使用 `$node`、`$result` 和 `$data`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-276">I know I use `$node`,`$result`,`$data` all the time.</span></span> <span data-ttu-id="c45b4-277">因此，来自不同作用域的值很容易出现在它们不该出现的地方。</span><span class="sxs-lookup"><span data-stu-id="c45b4-277">So it would be very easy for values from different scopes to show up in places where they should not be.</span></span>

## <a name="redirect-output-to-null"></a><span data-ttu-id="c45b4-278">将输出重定向到 $null</span><span class="sxs-lookup"><span data-stu-id="c45b4-278">Redirect output to $null</span></span>

<span data-ttu-id="c45b4-279">我们通篇都在讨论 `$null` 值，但如果不提将输出重定向到 `$null`，那么这个主题就不算完整。</span><span class="sxs-lookup"><span data-stu-id="c45b4-279">I have been talking about `$null` values for this entire article but the topic is not complete if I didn't mention redirecting output to `$null`.</span></span> <span data-ttu-id="c45b4-280">有时，一些命令会输出你要禁止显示的信息或对象。</span><span class="sxs-lookup"><span data-stu-id="c45b4-280">There are times when you have commands that output information or objects that you want to suppress.</span></span> <span data-ttu-id="c45b4-281">将输出重定向到 `$null` 会有此行为。</span><span class="sxs-lookup"><span data-stu-id="c45b4-281">Redirecting output to `$null` does that.</span></span>

### <a name="out-null"></a><span data-ttu-id="c45b4-282">Out-Null</span><span class="sxs-lookup"><span data-stu-id="c45b4-282">Out-Null</span></span>

<span data-ttu-id="c45b4-283">Out-Null 命令是将管道数据重定向到 `$null` 的内置方法。</span><span class="sxs-lookup"><span data-stu-id="c45b4-283">The Out-Null command is the built-in way to redirect pipeline data to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path | Out-Null
```

### <a name="assign-to-null"></a><span data-ttu-id="c45b4-284">分配给 $null</span><span class="sxs-lookup"><span data-stu-id="c45b4-284">Assign to $null</span></span>

<span data-ttu-id="c45b4-285">可以将命令的结果分配给 `$null`，以获得与使用 `Out-Null` 相同的结果。</span><span class="sxs-lookup"><span data-stu-id="c45b4-285">You can assign the results of a command to `$null` for the same effect as using `Out-Null`.</span></span>

```powershell
$null = New-Item -Type Directory -Path $path
```

<span data-ttu-id="c45b4-286">由于 `$null` 是常量值，因此永远不能覆盖它。</span><span class="sxs-lookup"><span data-stu-id="c45b4-286">Because `$null` is a constant value, you can never overwrite it.</span></span> <span data-ttu-id="c45b4-287">我不喜欢它在代码中的显示方式，但它的执行速度通常比 `Out-Null` 快。</span><span class="sxs-lookup"><span data-stu-id="c45b4-287">I don't like the way it looks in my code but it often performs faster than `Out-Null`.</span></span>

### <a name="redirect-to-null"></a><span data-ttu-id="c45b4-288">重定向到 $null</span><span class="sxs-lookup"><span data-stu-id="c45b4-288">Redirect to $null</span></span>

<span data-ttu-id="c45b4-289">你还可以使用重定向运算符将输出发送到 `$null`。</span><span class="sxs-lookup"><span data-stu-id="c45b4-289">You can also use the redirection operator to send output to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path > $null
```

<span data-ttu-id="c45b4-290">如果要处理在不同流上输出的命令行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="c45b4-290">If you're dealing with command-line executables that output on the different streams.</span></span> <span data-ttu-id="c45b4-291">可以将所有输出流重定向到 `$null`，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c45b4-291">You can redirect all output streams to `$null` like this:</span></span>

```powershell
git status *> $null
```

## <a name="summary"></a><span data-ttu-id="c45b4-292">总结</span><span class="sxs-lookup"><span data-stu-id="c45b4-292">Summary</span></span>

<span data-ttu-id="c45b4-293">我在本文中介绍了许多有关此值的基础知识，但我知道这比我的大部分深入研究零碎得多。</span><span class="sxs-lookup"><span data-stu-id="c45b4-293">I covered a lot of ground on this one and I know this article is more fragmented than most of my deep dives.</span></span> <span data-ttu-id="c45b4-294">这是因为 `$null` 值可以在 PowerShell 中的许多不同位置弹出，并且所有细微差别都特定于它的位置。</span><span class="sxs-lookup"><span data-stu-id="c45b4-294">That is because `$null` values can pop up in many different places in PowerShell and all the nuances are specific to where you find it.</span></span> <span data-ttu-id="c45b4-295">希望你在读完本文后能够更好地了解 `$null`，并意识到你可能会遇到更令人费解的情形。</span><span class="sxs-lookup"><span data-stu-id="c45b4-295">I hope you walk away from this with a better understanding of `$null` and an awareness of the more obscure scenarios you may run into.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[好文章]: https://blog.iisreset.me/schrodingers-argumentlist
[good post]: https://blog.iisreset.me/schrodingers-argumentlist
[PSScriptAnalyzer]: https://www.powershellgallery.com/packages/PSScriptAnalyzer
[System.Management.Automation.Internal.AutomationNull]: /dotnet/api/system.management.automation.internal.automationnull
