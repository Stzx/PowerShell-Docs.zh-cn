---
description: 描述处理终止错误的关键字。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 9627c632769cb87e790cc421c09d1103b90acf1d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200048"
---
# <a name="about-trap"></a><span data-ttu-id="23900-104">关于陷阱</span><span class="sxs-lookup"><span data-stu-id="23900-104">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="23900-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="23900-105">Short description</span></span>

<span data-ttu-id="23900-106">描述处理终止错误的关键字。</span><span class="sxs-lookup"><span data-stu-id="23900-106">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="23900-107">长说明</span><span class="sxs-lookup"><span data-stu-id="23900-107">Long description</span></span>

<span data-ttu-id="23900-108">终止错误阻止语句运行。</span><span class="sxs-lookup"><span data-stu-id="23900-108">A terminating error stops a statement from running.</span></span> <span data-ttu-id="23900-109">如果 PowerShell 未以某种方式处理终止错误，则 PowerShell 还会停止在当前管道中运行该函数或脚本。</span><span class="sxs-lookup"><span data-stu-id="23900-109">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="23900-110">在其他语言（如 c #）中，终止错误称为 "异常"。</span><span class="sxs-lookup"><span data-stu-id="23900-110">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="23900-111">`trap`关键字指定发生终止错误时要运行的语句的列表。</span><span class="sxs-lookup"><span data-stu-id="23900-111">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="23900-112">`trap` 语句按以下方式处理终止错误：</span><span class="sxs-lookup"><span data-stu-id="23900-112">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="23900-113">在处理语句块后显示错误 `trap` ，并继续执行包含的脚本或函数 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-113">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="23900-114">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="23900-114">This is the default behavior.</span></span>

- <span data-ttu-id="23900-115">显示错误并中止语句中包含 using 的脚本或函数的 `trap` 执行 `break` `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-115">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="23900-116">为此错误静音，但 `trap` 使用语句中的来继续执行包含的脚本或函数 `continue` `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-116">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="23900-117">的语句列表 `trap` 可以包含多个条件或函数调用。</span><span class="sxs-lookup"><span data-stu-id="23900-117">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="23900-118">`trap`可以编写日志、测试条件，甚至可以运行其他程序。</span><span class="sxs-lookup"><span data-stu-id="23900-118">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="23900-119">语法</span><span class="sxs-lookup"><span data-stu-id="23900-119">Syntax</span></span>

<span data-ttu-id="23900-120">`trap`语句具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="23900-120">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="23900-121">`trap`语句包括在发生终止错误时要运行的语句的列表。</span><span class="sxs-lookup"><span data-stu-id="23900-121">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="23900-122">`trap`语句包含 `trap` 关键字，后面可以跟类型表达式，包含在捕获错误时要运行的语句的列表。</span><span class="sxs-lookup"><span data-stu-id="23900-122">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="23900-123">类型表达式精炼了捕获的错误类型 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-123">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="23900-124">脚本或命令可以包含多个 `trap` 语句。</span><span class="sxs-lookup"><span data-stu-id="23900-124">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="23900-125">`trap` 语句可以出现在脚本或命令中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="23900-125">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="23900-126">捕获所有终止错误</span><span class="sxs-lookup"><span data-stu-id="23900-126">Trapping all terminating errors</span></span>

<span data-ttu-id="23900-127">当发生终止错误时，如果在脚本或命令中未以其他方式进行处理，则 PowerShell 会检查是否有 `trap` 处理错误的语句。</span><span class="sxs-lookup"><span data-stu-id="23900-127">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="23900-128">如果 `trap` 有语句，则 PowerShell 将继续运行语句中的脚本或命令 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-128">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="23900-129">下面的示例是一个非常简单的 `trap` 语句：</span><span class="sxs-lookup"><span data-stu-id="23900-129">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="23900-130">此 `trap` 语句捕获任何终止错误。</span><span class="sxs-lookup"><span data-stu-id="23900-130">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="23900-131">在下面的示例中，函数包含导致运行时错误的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="23900-131">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="23900-132">运行此函数将返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="23900-132">Running this function returns the following:</span></span>

```Output
Error found.
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     nonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="23900-133">下面的示例包含 `trap` 使用自动变量显示错误的语句 `$_` ：</span><span class="sxs-lookup"><span data-stu-id="23900-133">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="23900-134">运行此版本的函数将返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="23900-134">Running this version of the function returns the following:</span></span>

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     nonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

> [!IMPORTANT]
> <span data-ttu-id="23900-135">`trap` 语句可以在给定范围内的任何位置定义，但始终应用于该范围内的所有语句。</span><span class="sxs-lookup"><span data-stu-id="23900-135">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="23900-136">在运行时，将在 `trap` 执行任何其他语句之前定义块中的语句。</span><span class="sxs-lookup"><span data-stu-id="23900-136">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="23900-137">在 JavaScript 中，这称为 [提升](https://wikipedia.org/wiki/JavaScript_syntax#hoisting)。</span><span class="sxs-lookup"><span data-stu-id="23900-137">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="23900-138">这意味着， `trap` 即使执行操作未提前过定义的点，语句也适用于该块中的所有语句。</span><span class="sxs-lookup"><span data-stu-id="23900-138">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="23900-139">例如， `trap` 在脚本末尾定义，并在第一个语句中引发错误仍将触发 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-139">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="23900-140">捕获特定错误</span><span class="sxs-lookup"><span data-stu-id="23900-140">Trapping specific errors</span></span>

<span data-ttu-id="23900-141">脚本或命令可以包含多个 `trap` 语句。</span><span class="sxs-lookup"><span data-stu-id="23900-141">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="23900-142">`trap`可以定义来处理特定的错误。</span><span class="sxs-lookup"><span data-stu-id="23900-142">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="23900-143">以下示例是 `trap` 捕获特定错误 **system.management.automation.commandnotfoundexception** 的语句：</span><span class="sxs-lookup"><span data-stu-id="23900-143">The following example is a `trap` statement that traps the specific error **CommandNotFoundException** :</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="23900-144">当函数或脚本遇到与已知命令不匹配的字符串时，此 `trap` 语句将显示 "命令错误捕获" 字符串。</span><span class="sxs-lookup"><span data-stu-id="23900-144">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="23900-145">运行 `trap` 语句列表后，PowerShell 将错误对象写入错误流，然后继续运行脚本。</span><span class="sxs-lookup"><span data-stu-id="23900-145">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="23900-146">PowerShell 使用 .NET 异常类型。</span><span class="sxs-lookup"><span data-stu-id="23900-146">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="23900-147">下面 **的示例指定了 system.exception** 错误类型：</span><span class="sxs-lookup"><span data-stu-id="23900-147">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="23900-148">**System.management.automation.commandnotfoundexception** 错误类型继承自 **system.object** 类型。</span><span class="sxs-lookup"><span data-stu-id="23900-148">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="23900-149">此语句捕获未知命令创建的错误。</span><span class="sxs-lookup"><span data-stu-id="23900-149">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="23900-150">它还捕获其他错误类型。</span><span class="sxs-lookup"><span data-stu-id="23900-150">It also traps other error types.</span></span>

<span data-ttu-id="23900-151">一个脚本中可以有多个 `trap` 语句。</span><span class="sxs-lookup"><span data-stu-id="23900-151">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="23900-152">每个错误类型只能用一条语句来捕获 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-152">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="23900-153">当发生终止错误时，PowerShell 会 `trap` 在当前的执行范围内搜索具有最特定匹配的。</span><span class="sxs-lookup"><span data-stu-id="23900-153">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="23900-154">下面的脚本示例包含错误。</span><span class="sxs-lookup"><span data-stu-id="23900-154">The following script example contains an error.</span></span> <span data-ttu-id="23900-155">该脚本包含一个 `trap` 用于捕获任何终止错误和 `trap` 指定 **system.management.automation.commandnotfoundexception** 类型的特定语句的常规语句。</span><span class="sxs-lookup"><span data-stu-id="23900-155">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="23900-156">运行此脚本会生成以下结果：</span><span class="sxs-lookup"><span data-stu-id="23900-156">Running this script produces the following result:</span></span>

```Output
Command error trapped
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At C:\Temp\traptest.ps1:5 char:1
+ nonsenseString
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="23900-157">由于 PowerShell 无法将 "nonsenseString" 识别为 cmdlet 或其他项，因此它将返回 **system.management.automation.commandnotfoundexception** 错误。</span><span class="sxs-lookup"><span data-stu-id="23900-157">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="23900-158">此终止错误由特定的语句捕获 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-158">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="23900-159">下面的脚本示例包含 `trap` 具有不同错误的相同语句：</span><span class="sxs-lookup"><span data-stu-id="23900-159">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="23900-160">运行此脚本会生成以下结果：</span><span class="sxs-lookup"><span data-stu-id="23900-160">Running this script produces the following result:</span></span>

```Output
Attempted to divide by zero.
At C:\temp\traptest.ps1:4 char:1
+ 1/$null
+ ~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], RuntimeException
    + FullyQualifiedErrorId : RuntimeException
```

<span data-ttu-id="23900-161">尝试除以零不会造成 **system.management.automation.commandnotfoundexception** 错误。</span><span class="sxs-lookup"><span data-stu-id="23900-161">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="23900-162">相反，此错误由另一语句捕获 `trap` ，后者捕获任何终止错误。</span><span class="sxs-lookup"><span data-stu-id="23900-162">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="23900-163">捕获错误和范围</span><span class="sxs-lookup"><span data-stu-id="23900-163">Trapping errors and scope</span></span>

<span data-ttu-id="23900-164">如果终止错误发生在语句所在的作用域内 `trap` ，则 PowerShell 将运行由定义的语句列表 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-164">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="23900-165">错误之后的语句将继续执行。</span><span class="sxs-lookup"><span data-stu-id="23900-165">Execution continues at the statement after the error.</span></span> <span data-ttu-id="23900-166">如果 `trap` 语句不同于错误的作用域，则执行将在语句所在的下一个语句中继续执行 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-166">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="23900-167">例如，如果某个函数中出现错误，并且该 `trap` 语句在函数中，则该脚本将继续执行下一条语句。</span><span class="sxs-lookup"><span data-stu-id="23900-167">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="23900-168">下面的脚本包含错误和 `trap` 语句：</span><span class="sxs-lookup"><span data-stu-id="23900-168">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="23900-169">运行此脚本会生成以下结果：</span><span class="sxs-lookup"><span data-stu-id="23900-169">Running this script produces the following result:</span></span>

```Output
An error:
NonsenseString : The term 'NonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     NonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (NonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

function1 was completed
```

<span data-ttu-id="23900-170">`trap`函数中的语句捕获错误。</span><span class="sxs-lookup"><span data-stu-id="23900-170">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="23900-171">显示消息后，PowerShell 将继续运行函数。</span><span class="sxs-lookup"><span data-stu-id="23900-171">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="23900-172">请注意， `Function1` 已完成。</span><span class="sxs-lookup"><span data-stu-id="23900-172">Note that `Function1` was completed.</span></span>

<span data-ttu-id="23900-173">将此与以下包含相同错误和语句的示例进行比较 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-173">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="23900-174">在此示例中， `trap` 语句发生在函数的外部：</span><span class="sxs-lookup"><span data-stu-id="23900-174">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="23900-175">运行 `Function2` 函数会生成以下结果：</span><span class="sxs-lookup"><span data-stu-id="23900-175">Running the `Function2` function produces the following result:</span></span>

```Output
An error:
NonsenseString : The term 'NonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At C:\temp\traptest.ps1:2 char:5
+     NonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (NonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="23900-176">在此示例中，"function2 已完成" 命令未运行。</span><span class="sxs-lookup"><span data-stu-id="23900-176">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="23900-177">在这两个示例中，终止错误发生在函数内。</span><span class="sxs-lookup"><span data-stu-id="23900-177">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="23900-178">但在此示例中， `trap` 语句位于函数之外。</span><span class="sxs-lookup"><span data-stu-id="23900-178">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="23900-179">运行语句后，PowerShell 不会返回函数 `trap` 。</span><span class="sxs-lookup"><span data-stu-id="23900-179">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="23900-180">为同一个错误条件定义多个陷阱时，将 `trap` 使用范围) 中的第一个已定义的词法 (最高。</span><span class="sxs-lookup"><span data-stu-id="23900-180">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="23900-181">在下面的示例中，仅 `trap` 运行带 "了 1" 的。</span><span class="sxs-lookup"><span data-stu-id="23900-181">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="23900-182">Trap 语句的作用域限定为它的编译位置。</span><span class="sxs-lookup"><span data-stu-id="23900-182">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="23900-183">如果在 `trap` 函数或带句点的脚本中有语句，则当函数或点即点脚本退出时， `trap` 将删除中的所有语句。</span><span class="sxs-lookup"><span data-stu-id="23900-183">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="23900-184">使用 break 和 continue 关键字</span><span class="sxs-lookup"><span data-stu-id="23900-184">Using the break and continue keywords</span></span>

<span data-ttu-id="23900-185">可以 `break` `continue` 在语句中使用和关键字， `trap` 以确定在终止错误之后脚本或命令是否继续运行。</span><span class="sxs-lookup"><span data-stu-id="23900-185">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="23900-186">如果在 `break` 语句列表中包含语句 `trap` ，则 PowerShell 将停止该函数或脚本。</span><span class="sxs-lookup"><span data-stu-id="23900-186">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="23900-187">下面的示例函数 `break` 在语句中使用关键字 `trap` ：</span><span class="sxs-lookup"><span data-stu-id="23900-187">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
Attempted to divide by zero.
At line:6 char:5
+     1/$null
+     ~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RuntimeException
```

<span data-ttu-id="23900-188">由于 `trap` 语句包含 `break` 关键字，因此该函数不会继续运行，并且不会运行 "函数已完成" 行。</span><span class="sxs-lookup"><span data-stu-id="23900-188">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="23900-189">如果在 `continue` 语句中包含关键字 `trap` ，则 PowerShell 会在导致错误的语句之后恢复，就像没有 `break` 或一样 `continue` 。</span><span class="sxs-lookup"><span data-stu-id="23900-189">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="23900-190">但使用 `continue` 关键字时，PowerShell 不会将错误写入错误流。</span><span class="sxs-lookup"><span data-stu-id="23900-190">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="23900-191">下面的示例函数 `continue` 在语句中使用关键字 `trap` ：</span><span class="sxs-lookup"><span data-stu-id="23900-191">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

<span data-ttu-id="23900-192">函数在捕获错误后恢复，并且 "函数已完成" 语句将运行。</span><span class="sxs-lookup"><span data-stu-id="23900-192">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="23900-193">不会将错误写入错误流。</span><span class="sxs-lookup"><span data-stu-id="23900-193">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="23900-194">注释</span><span class="sxs-lookup"><span data-stu-id="23900-194">Notes</span></span>

<span data-ttu-id="23900-195">`trap` 语句提供一种简单的方法来广泛地确保处理范围内的所有终止错误。</span><span class="sxs-lookup"><span data-stu-id="23900-195">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="23900-196">若要进行更细化的错误处理，请使用 `try` / `catch` 使用语句定义陷阱的块 `catch` 。</span><span class="sxs-lookup"><span data-stu-id="23900-196">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="23900-197">`catch`语句仅适用于关联语句中的代码 `try` 。</span><span class="sxs-lookup"><span data-stu-id="23900-197">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="23900-198">有关详细信息，请参阅 [about_Try_Catch_Finally](about_Try_Catch_Finally.md)。</span><span class="sxs-lookup"><span data-stu-id="23900-198">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="23900-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23900-199">See also</span></span>

[<span data-ttu-id="23900-200">about_Break</span><span class="sxs-lookup"><span data-stu-id="23900-200">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="23900-201">about_Continue</span><span class="sxs-lookup"><span data-stu-id="23900-201">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="23900-202">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="23900-202">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="23900-203">about_Throw</span><span class="sxs-lookup"><span data-stu-id="23900-203">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="23900-204">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="23900-204">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
