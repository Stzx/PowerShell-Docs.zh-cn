---
description: 描述可用于立即退出、、、、 `foreach` `for` `while` `do` `switch` 或 `trap` 语句的语句。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 4dbc1a09ca4ec317c4756c65058f661ec41a513a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199620"
---
# <a name="about-break"></a><span data-ttu-id="bae8b-104">关于中断</span><span class="sxs-lookup"><span data-stu-id="bae8b-104">About Break</span></span>

## <a name="short-description"></a><span data-ttu-id="bae8b-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="bae8b-105">Short description</span></span>

<span data-ttu-id="bae8b-106">描述可用于立即退出、、、、 `foreach` `for` `while` `do` `switch` 或 `trap` 语句的语句。</span><span class="sxs-lookup"><span data-stu-id="bae8b-106">Describes a statement you can use to immediately exit `foreach`, `for`, `while`, `do`, `switch`, or `trap` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="bae8b-107">长说明</span><span class="sxs-lookup"><span data-stu-id="bae8b-107">Long description</span></span>

<span data-ttu-id="bae8b-108">`break`语句提供退出当前控制块的方法。</span><span class="sxs-lookup"><span data-stu-id="bae8b-108">The `break` statement provides a way to exit the current control block.</span></span>
<span data-ttu-id="bae8b-109">继续执行控制块后的下一条语句。</span><span class="sxs-lookup"><span data-stu-id="bae8b-109">Execution continues at the next statement after the control block.</span></span> <span data-ttu-id="bae8b-110">语句支持标签。</span><span class="sxs-lookup"><span data-stu-id="bae8b-110">The statement supports labels.</span></span> <span data-ttu-id="bae8b-111">标签是为脚本中的语句分配的名称。</span><span class="sxs-lookup"><span data-stu-id="bae8b-111">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-break-in-loops"></a><span data-ttu-id="bae8b-112">在循环中使用 break</span><span class="sxs-lookup"><span data-stu-id="bae8b-112">Using break in loops</span></span>

<span data-ttu-id="bae8b-113">如果 `break` 语句出现在循环中，如 `foreach` 、 `for` 、 `do` 或循环，则 PowerShell 会 `while` 立即退出该循环。</span><span class="sxs-lookup"><span data-stu-id="bae8b-113">When a `break` statement appears in a loop, such as a `foreach`, `for`, `do`, or `while` loop, PowerShell immediately exits the loop.</span></span>

<span data-ttu-id="bae8b-114">`break`语句可以包含一个标签，使您可以退出嵌入循环。</span><span class="sxs-lookup"><span data-stu-id="bae8b-114">A `break` statement can include a label that lets you exit embedded loops.</span></span> <span data-ttu-id="bae8b-115">标签可以在脚本中指定任意循环关键字，如 `foreach` 、 `for` 或 `while` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-115">A label can specify any loop keyword, such as `foreach`, `for`, or `while`, in a script.</span></span>

<span data-ttu-id="bae8b-116">下面的示例演示如何使用 `break` 语句退出 `for` 语句：</span><span class="sxs-lookup"><span data-stu-id="bae8b-116">The following example shows how to use a `break` statement to exit a `for` statement:</span></span>

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

<span data-ttu-id="bae8b-117">在此示例中， `break` `for` 如果变量等于1，语句将退出循环 `$i` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-117">In this example, the `break` statement exits the `for` loop when the `$i` variable equals 1.</span></span> <span data-ttu-id="bae8b-118">尽管语句的 `for` 计算结果为 **True** ，但直到 `$i` 大于10，否则，PowerShell 将在第一次运行循环时到达 break 语句 `for` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-118">Even though the `for` statement evaluates to **True** until `$i` is greater than 10, PowerShell reaches the break statement the first time the `for` loop is run.</span></span>

<span data-ttu-id="bae8b-119">`break`在必须满足内部条件的循环中使用语句更为常见。</span><span class="sxs-lookup"><span data-stu-id="bae8b-119">It is more common to use the `break` statement in a loop where an inner condition must be met.</span></span> <span data-ttu-id="bae8b-120">请看下面的 `foreach` 语句示例：</span><span class="sxs-lookup"><span data-stu-id="bae8b-120">Consider the following `foreach` statement example:</span></span>

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

<span data-ttu-id="bae8b-121">在此示例中， `foreach` 语句将循环访问 `$varB` 数组。</span><span class="sxs-lookup"><span data-stu-id="bae8b-121">In this example, the `foreach` statement iterates the `$varB` array.</span></span> <span data-ttu-id="bae8b-122">`if`语句的计算结果为 False，即循环运行的前两次，变量 `$i` 递增1。</span><span class="sxs-lookup"><span data-stu-id="bae8b-122">The `if` statement evaluates to False the first two times the loop is run and the variable `$i` is incremented by 1.</span></span> <span data-ttu-id="bae8b-123">第三次运行循环时， `$i` 等于2， `$val` 变量等于30。</span><span class="sxs-lookup"><span data-stu-id="bae8b-123">The third time the loop is run, `$i` equals 2, and the `$val` variable equals 30.</span></span> <span data-ttu-id="bae8b-124">此时， `break` 语句将运行，并且 `foreach` 循环将退出。</span><span class="sxs-lookup"><span data-stu-id="bae8b-124">At this point, the `break` statement runs, and the `foreach` loop exits.</span></span>

### <a name="using-a-labeled-break-in-a-loop"></a><span data-ttu-id="bae8b-125">在循环中使用带标记的中断</span><span class="sxs-lookup"><span data-stu-id="bae8b-125">Using a labeled break in a loop</span></span>

<span data-ttu-id="bae8b-126">`break`语句可以包含标签。</span><span class="sxs-lookup"><span data-stu-id="bae8b-126">A `break` statement can include a label.</span></span> <span data-ttu-id="bae8b-127">如果对标签使用 `break` 关键字，则 PowerShell 会退出标记的循环，而不是退出当前循环。</span><span class="sxs-lookup"><span data-stu-id="bae8b-127">If you use the `break` keyword with a label, PowerShell exits the labeled loop instead of exiting the current loop.</span></span>
<span data-ttu-id="bae8b-128">标签是一个冒号，后跟您分配的名称。</span><span class="sxs-lookup"><span data-stu-id="bae8b-128">The label is a colon followed by a name that you assign.</span></span> <span data-ttu-id="bae8b-129">标签必须是语句中的第一个标记，并且必须后跟循环关键字，如 `while` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-129">The label must be the first token in a statement, and it must be followed by the looping keyword, such as `while`.</span></span>

<span data-ttu-id="bae8b-130">`break` 将执行移出标记循环。</span><span class="sxs-lookup"><span data-stu-id="bae8b-130">`break` moves execution out of the labeled loop.</span></span> <span data-ttu-id="bae8b-131">在嵌入循环中，此方法的结果与 `break` 关键字本身使用时的结果不同。</span><span class="sxs-lookup"><span data-stu-id="bae8b-131">In embedded loops, this has a different result than the `break` keyword has when it is used by itself.</span></span> <span data-ttu-id="bae8b-132">此示例包含 `while` 带有语句的语句 `for` ：</span><span class="sxs-lookup"><span data-stu-id="bae8b-132">This example has a `while` statement with a `for` statement:</span></span>

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

<span data-ttu-id="bae8b-133">如果条件2的计算结果为 **True** ，则脚本的执行将向下跳到标记的循环后的语句。</span><span class="sxs-lookup"><span data-stu-id="bae8b-133">If condition 2 evaluates to **True** , the execution of the script skips down to the statement after the labeled loop.</span></span> <span data-ttu-id="bae8b-134">在此示例中，执行再次与语句一起开始 `$a = $c` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-134">In the example, execution starts again with the statement `$a = $c`.</span></span>

<span data-ttu-id="bae8b-135">可以嵌套多个标记的循环，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="bae8b-135">You can nest many labeled loops, as shown in the following example.</span></span>

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

<span data-ttu-id="bae8b-136">如果 `$b` 变量的计算结果为 True，则脚本的执行将在标记为 "red" 的循环后恢复。</span><span class="sxs-lookup"><span data-stu-id="bae8b-136">If the `$b` variable evaluates to True, execution of the script resumes after the loop that is labeled "red".</span></span> <span data-ttu-id="bae8b-137">如果 `$c` 变量的计算结果为 True，则脚本控件的执行将在标记为 "黄色" 的循环后恢复。</span><span class="sxs-lookup"><span data-stu-id="bae8b-137">If the `$c` variable evaluates to True, execution of the script control resumes after the loop that is labeled "yellow".</span></span>

<span data-ttu-id="bae8b-138">如果 `$a` 变量的计算结果为 True，则执行将在最内层循环后恢复。</span><span class="sxs-lookup"><span data-stu-id="bae8b-138">If the `$a` variable evaluates to True, execution resumes after the innermost loop.</span></span> <span data-ttu-id="bae8b-139">不需要标签。</span><span class="sxs-lookup"><span data-stu-id="bae8b-139">No label is needed.</span></span>

<span data-ttu-id="bae8b-140">PowerShell 不会限制标签可继续执行的程度。</span><span class="sxs-lookup"><span data-stu-id="bae8b-140">PowerShell does not limit how far labels can resume execution.</span></span> <span data-ttu-id="bae8b-141">标签甚至可以在脚本和函数调用边界之间传递控制。</span><span class="sxs-lookup"><span data-stu-id="bae8b-141">The label can even pass control across script and function call boundaries.</span></span>

## <a name="using-break-in-a-switch-statement"></a><span data-ttu-id="bae8b-142">在 switch 语句中使用 break</span><span class="sxs-lookup"><span data-stu-id="bae8b-142">Using break in a switch statement</span></span>

<span data-ttu-id="bae8b-143">在 `switch` 构造中， `break` 导致 PowerShell 退出 `switch` 代码块。</span><span class="sxs-lookup"><span data-stu-id="bae8b-143">In a `switch`construct, `break` causes PowerShell to exit the `switch` code block.</span></span>

<span data-ttu-id="bae8b-144">`break`关键字用于离开 `switch` 构造。</span><span class="sxs-lookup"><span data-stu-id="bae8b-144">The `break` keyword is used to leave the `switch` construct.</span></span> <span data-ttu-id="bae8b-145">例如，下面的 `switch` 语句使用 `break` 语句来测试最具体的条件：</span><span class="sxs-lookup"><span data-stu-id="bae8b-145">For example, the following `switch` statement uses `break` statements to test for the most specific condition:</span></span>

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

<span data-ttu-id="bae8b-146">在此示例中，将 `$var` 创建变量并将其初始化为的字符串值 `word2` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-146">In this example, the `$var` variable is created and initialized to a string value of `word2`.</span></span> <span data-ttu-id="bae8b-147">`switch`语句使用 **Regex** 类将变量值首先与字词进行匹配 `word2` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-147">The `switch` statement uses the **Regex** class to match the variable value first with the term `word2`.</span></span> <span data-ttu-id="bae8b-148">由于变量值和语句中的第一个测试 `switch` 匹配，因此语句中的第一个代码块将 `switch` 运行。</span><span class="sxs-lookup"><span data-stu-id="bae8b-148">Because the variable value and the first test in the `switch` statement match, the first code block in the `switch` statement runs.</span></span>

<span data-ttu-id="bae8b-149">当 PowerShell 到达第一 `break` 条语句时， `switch` 语句将退出。</span><span class="sxs-lookup"><span data-stu-id="bae8b-149">When PowerShell reaches the first `break` statement, the `switch` statement exits.</span></span> <span data-ttu-id="bae8b-150">如果删除了该示例中的四个 `break` 语句，则满足所有四个条件。</span><span class="sxs-lookup"><span data-stu-id="bae8b-150">If the four `break` statements are removed from the example, all four conditions are met.</span></span> <span data-ttu-id="bae8b-151">此示例使用 `break` 语句在满足最特定的条件时显示结果。</span><span class="sxs-lookup"><span data-stu-id="bae8b-151">This example uses the `break` statement to display results when the most specific condition is met.</span></span>

## <a name="using-break-in-a-trap-statement"></a><span data-ttu-id="bae8b-152">在 trap 语句中使用 break</span><span class="sxs-lookup"><span data-stu-id="bae8b-152">Using break in a trap statement</span></span>

<span data-ttu-id="bae8b-153">如果在语句体中执行的最后一条语句 `trap` 是 `break` ，则会取消错误对象，并重新引发异常。</span><span class="sxs-lookup"><span data-stu-id="bae8b-153">If the final statement executed in the body of a `trap` statement is `break`, the error object is suppressed and the exception is re-thrown.</span></span>

<span data-ttu-id="bae8b-154">下面的示例创建一个使用语句捕获的 **system.dividebyzeroexception** 异常 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-154">The following example create a **DivideByZeroException** exception that is trapped using the `trap` statement.</span></span>

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

请注意，执行在出现异常时停止。 <span data-ttu-id="bae8b-156">永远不会 `After loop` 到达。</span><span class="sxs-lookup"><span data-stu-id="bae8b-156">The `After loop` is never reached.</span></span>
<span data-ttu-id="bae8b-157">执行后，将重新引发异常 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-157">The exception is re-thrown after the `trap` executes.</span></span>

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="bae8b-158">不要在循环、开关或陷阱的外部使用 break</span><span class="sxs-lookup"><span data-stu-id="bae8b-158">Do not use break outside of a loop, switch, or trap</span></span>

<span data-ttu-id="bae8b-159">如果在 `break` 直接支持 (循环、) 的构造之外使用，则 `switch` `trap` PowerShell 将查找封闭构造 _的调用堆栈_ 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-159">When `break` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="bae8b-160">如果找不到封闭构造，则当前的运行空间将不知不觉地终止。</span><span class="sxs-lookup"><span data-stu-id="bae8b-160">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="bae8b-161">这意味着，不小心在支持它的封闭构造之外使用的函数和脚本 `break` 可能会意外终止其 _调用方_ 。</span><span class="sxs-lookup"><span data-stu-id="bae8b-161">This means that functions and scripts that inadvertently use a `break` outside of an enclosing construct that supports it can inadvertently terminate their _callers_ .</span></span>

<span data-ttu-id="bae8b-162">在 `break` 管道内使用（ `break` 如 `ForEach-Object` 脚本块），不仅会退出管道，还可能终止整个运行空间。</span><span class="sxs-lookup"><span data-stu-id="bae8b-162">Using `break` inside a pipeline `break`, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="bae8b-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bae8b-163">See also</span></span>

[<span data-ttu-id="bae8b-164">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="bae8b-164">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="bae8b-165">about_Continue</span><span class="sxs-lookup"><span data-stu-id="bae8b-165">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="bae8b-166">about_For</span><span class="sxs-lookup"><span data-stu-id="bae8b-166">about_For</span></span>](about_For.md)

[<span data-ttu-id="bae8b-167">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="bae8b-167">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="bae8b-168">about_Switch</span><span class="sxs-lookup"><span data-stu-id="bae8b-168">about_Switch</span></span>](about_Switch.md)

[<span data-ttu-id="bae8b-169">about_Throw</span><span class="sxs-lookup"><span data-stu-id="bae8b-169">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="bae8b-170">about_Trap</span><span class="sxs-lookup"><span data-stu-id="bae8b-170">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="bae8b-171">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="bae8b-171">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

[<span data-ttu-id="bae8b-172">about_While</span><span class="sxs-lookup"><span data-stu-id="bae8b-172">about_While</span></span>](about_While.md)