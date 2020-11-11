---
description: 描述 PowerShell 支持的运算符。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: a9c589aacfc64495ece2d461687d97f95d885353
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483190"
---
# <a name="about-operators"></a><span data-ttu-id="2cde7-104">关于运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="2cde7-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="2cde7-105">Short description</span></span>
<span data-ttu-id="2cde7-106">描述 PowerShell 支持的运算符。</span><span class="sxs-lookup"><span data-stu-id="2cde7-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2cde7-107">长说明</span><span class="sxs-lookup"><span data-stu-id="2cde7-107">Long description</span></span>

<span data-ttu-id="2cde7-108">运算符是可在命令或表达式中使用的语言元素。</span><span class="sxs-lookup"><span data-stu-id="2cde7-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="2cde7-109">PowerShell 支持多种类型的运算符来帮助您操作值。</span><span class="sxs-lookup"><span data-stu-id="2cde7-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="2cde7-110">算术运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-110">Arithmetic Operators</span></span>

<span data-ttu-id="2cde7-111">使用算术运算符 (`+` 、 `-` 、 `*` 、 `/` `%`) 计算命令或表达式中的值。</span><span class="sxs-lookup"><span data-stu-id="2cde7-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="2cde7-112">使用这些运算符，可以添加、减、乘或相除值，计算除法运算的余数 (模数) 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="2cde7-113">加法运算符用于连接元素。</span><span class="sxs-lookup"><span data-stu-id="2cde7-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="2cde7-114">乘法运算符返回每个元素的指定数量的副本。</span><span class="sxs-lookup"><span data-stu-id="2cde7-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="2cde7-115">可以对任何实现它们的 .net 类型使用算术运算符，例如： `Int` 、 `String` 、 `DateTime` 、 `Hashtable` 和数组。</span><span class="sxs-lookup"><span data-stu-id="2cde7-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="2cde7-116">按位运算符 (`-band` 、、、、 `-bor` `-bxor` `-bnot` `-shl` `-shr`) 处理值中的位模式。</span><span class="sxs-lookup"><span data-stu-id="2cde7-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="2cde7-117">有关详细信息，请参阅 [about_Arithmetic_Operators](about_Arithmetic_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="2cde7-118">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-118">Assignment Operators</span></span>

<span data-ttu-id="2cde7-119">使用赋值运算符 (`=` 、 `+=` 、 `-=` 、 `*=` 、 `/=` 、 `%=`) 将值分配给变量或将值追加到变量。</span><span class="sxs-lookup"><span data-stu-id="2cde7-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="2cde7-120">可以将算术运算符与赋值结合使用，将算术运算的结果分配给变量。</span><span class="sxs-lookup"><span data-stu-id="2cde7-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="2cde7-121">有关详细信息，请参阅 [about_Assignment_Operators](about_Assignment_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="2cde7-122">比较运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-122">Comparison Operators</span></span>

<span data-ttu-id="2cde7-123">使用比较运算符 (`-eq` 、、、、、 `-ne` `-gt` `-lt` `-le` `-ge`) 比较值和测试条件。</span><span class="sxs-lookup"><span data-stu-id="2cde7-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="2cde7-124">例如，可以比较两个字符串值，以确定它们是否相等。</span><span class="sxs-lookup"><span data-stu-id="2cde7-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="2cde7-125">比较运算符还包括用于在文本中查找或替换模式的运算符。</span><span class="sxs-lookup"><span data-stu-id="2cde7-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="2cde7-126"> (`-match` 、 `-notmatch` `-replace`) 运算符使用正则表达式和 (`-like` ， `-notlike`) 使用通配符 `*` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="2cde7-127">包含比较运算符确定测试值是出现在引用集中， (，，， `-in` `-notin` `-contains` `-notcontains`) 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="2cde7-128">类型比较运算符 (`-is` ， `-isnot`) 确定对象是否为给定类型。</span><span class="sxs-lookup"><span data-stu-id="2cde7-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="2cde7-129">有关详细信息，请参阅 [about_Comparison_Operators](about_Comparison_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="2cde7-130">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-130">Logical Operators</span></span>

<span data-ttu-id="2cde7-131">使用逻辑运算符 (`-and` 、 `-or` 、 `-xor` 、 `-not` `!`) 将条件语句连接到单个复杂条件。</span><span class="sxs-lookup"><span data-stu-id="2cde7-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="2cde7-132">例如，可以使用逻辑 `-and` 运算符创建具有两个不同条件的对象筛选器。</span><span class="sxs-lookup"><span data-stu-id="2cde7-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="2cde7-133">有关详细信息，请参阅 [about_Logical_Operators](about_logical_operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="2cde7-134">重定向运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-134">Redirection Operators</span></span>

<span data-ttu-id="2cde7-135">使用重定向运算符 (`>` 、 `>>` 、 `2>` 、 `2>>` 和 `2>&1`) 将命令或表达式的输出发送到文本文件。</span><span class="sxs-lookup"><span data-stu-id="2cde7-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="2cde7-136">重定向运算符的工作方式类似于 `Out-File` 不带参数的 cmdlet () 但是，它们还允许你将错误输出重定向到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="2cde7-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="2cde7-137">你还可以使用 `Tee-Object` cmdlet 来重定向输出。</span><span class="sxs-lookup"><span data-stu-id="2cde7-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="2cde7-138">有关详细信息，请参阅 [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="2cde7-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="2cde7-139">拆分和联接运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-139">Split and Join Operators</span></span>

<span data-ttu-id="2cde7-140">`-split`和 `-join` 运算符划分并组合子字符串。</span><span class="sxs-lookup"><span data-stu-id="2cde7-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="2cde7-141">`-split`运算符将字符串拆分为子字符串。</span><span class="sxs-lookup"><span data-stu-id="2cde7-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="2cde7-142">`-join`运算符将多个字符串串联为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="2cde7-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="2cde7-143">有关详细信息，请参阅 [about_Split](about_Split.md) 和 [about_Join](about_Join.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="2cde7-144">类型运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-144">Type Operators</span></span>

<span data-ttu-id="2cde7-145">使用 (，) 的类型运算符 `-is` `-isnot` `-as` 查找或更改对象的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="2cde7-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="2cde7-146">有关详细信息，请参阅 [about_Type_Operators](about_Type_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="2cde7-147">一元运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-147">Unary Operators</span></span>

<span data-ttu-id="2cde7-148">使用一元运算符来递增或递减变量或对象属性，并将整数设置为正数或负数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="2cde7-149">例如，若要将变量 `$a` 从增加 `9` 到 `10` ，请键入 `$a++` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="2cde7-150">特殊运算符</span><span class="sxs-lookup"><span data-stu-id="2cde7-150">Special Operators</span></span>

<span data-ttu-id="2cde7-151">特殊运算符具有不适合任何其他操作员组的特定用例。</span><span class="sxs-lookup"><span data-stu-id="2cde7-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="2cde7-152">例如，使用特殊运算符可运行命令、更改值的数据类型或从数组中检索元素。</span><span class="sxs-lookup"><span data-stu-id="2cde7-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="2cde7-153">分组运算符 `( )`</span><span class="sxs-lookup"><span data-stu-id="2cde7-153">Grouping operator `( )`</span></span>

<span data-ttu-id="2cde7-154">与其他语言一样， `(...)` 用于重写表达式中的运算符优先级。</span><span class="sxs-lookup"><span data-stu-id="2cde7-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="2cde7-155">例如： `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="2cde7-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="2cde7-156">但是，在 PowerShell 中还有其他行为。</span><span class="sxs-lookup"><span data-stu-id="2cde7-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="2cde7-157">`(...)` 允许您允许 _命令_ 的输出参与表达式。</span><span class="sxs-lookup"><span data-stu-id="2cde7-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="2cde7-158">例如：</span><span class="sxs-lookup"><span data-stu-id="2cde7-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="2cde7-159">当用作管道的第一段时，用括号将命令或表达式括起来会导致表达式结果的 _枚举_ 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="2cde7-160">如果括号环绕 _命令_ ，则在通过管道发送结果之前，将使用 _内存中收集_ 的所有输出运行完成。</span><span class="sxs-lookup"><span data-stu-id="2cde7-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="2cde7-161">子表达式运算符 `$( )`</span><span class="sxs-lookup"><span data-stu-id="2cde7-161">Subexpression operator `$( )`</span></span>

<span data-ttu-id="2cde7-162">返回一个或多个语句的结果。</span><span class="sxs-lookup"><span data-stu-id="2cde7-162">Returns the result of one or more statements.</span></span> <span data-ttu-id="2cde7-163">对于单个结果，返回一个标量。</span><span class="sxs-lookup"><span data-stu-id="2cde7-163">For a single result, returns a scalar.</span></span> <span data-ttu-id="2cde7-164">对于多个结果，将返回一个数组。</span><span class="sxs-lookup"><span data-stu-id="2cde7-164">For multiple results, returns an array.</span></span> <span data-ttu-id="2cde7-165">如果要在另一个表达式内使用表达式，请使用此表达式。</span><span class="sxs-lookup"><span data-stu-id="2cde7-165">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="2cde7-166">例如，要在字符串表达式中嵌入命令的结果。</span><span class="sxs-lookup"><span data-stu-id="2cde7-166">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="2cde7-167">Array 子表达式运算符 `@( )`</span><span class="sxs-lookup"><span data-stu-id="2cde7-167">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="2cde7-168">以数组形式返回一个或多个语句的结果。</span><span class="sxs-lookup"><span data-stu-id="2cde7-168">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="2cde7-169">如果只有一个项，则数组只包含一个成员。</span><span class="sxs-lookup"><span data-stu-id="2cde7-169">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a><span data-ttu-id="2cde7-170">哈希表文本语法 `@{}`</span><span class="sxs-lookup"><span data-stu-id="2cde7-170">Hash table literal syntax `@{}`</span></span>

<span data-ttu-id="2cde7-171">与 array 子表达式类似，此语法用于声明哈希表。</span><span class="sxs-lookup"><span data-stu-id="2cde7-171">Similar to the array subexpression, this syntax is used to declare a hash table.</span></span>
<span data-ttu-id="2cde7-172">有关详细信息，请参阅 [about_Hash_Tables](about_Hash_Tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-172">For more information, see [about_Hash_Tables](about_Hash_Tables.md).</span></span>

#### <a name="call-operator-"></a><span data-ttu-id="2cde7-173">Call 运算符 `&`</span><span class="sxs-lookup"><span data-stu-id="2cde7-173">Call operator `&`</span></span>

<span data-ttu-id="2cde7-174">运行命令、脚本或脚本块。</span><span class="sxs-lookup"><span data-stu-id="2cde7-174">Runs a command, script, or script block.</span></span> <span data-ttu-id="2cde7-175">Call 运算符（也称为 "调用运算符"）允许您运行存储在变量中并由字符串或脚本块表示的命令。</span><span class="sxs-lookup"><span data-stu-id="2cde7-175">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="2cde7-176">调用运算符在子范围内执行。</span><span class="sxs-lookup"><span data-stu-id="2cde7-176">The call operator executes in a child scope.</span></span> <span data-ttu-id="2cde7-177">有关范围的详细信息，请参阅 [about_Scopes](about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-177">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="2cde7-178">此示例将命令存储在字符串中，并使用 call 运算符执行该命令。</span><span class="sxs-lookup"><span data-stu-id="2cde7-178">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="2cde7-179">调用运算符不分析字符串。</span><span class="sxs-lookup"><span data-stu-id="2cde7-179">The call operator does not parse strings.</span></span> <span data-ttu-id="2cde7-180">这意味着，在使用 call 运算符时，不能使用字符串中的命令参数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-180">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
```

<span data-ttu-id="2cde7-181">[调用表达式](xref:Microsoft.PowerShell.Utility.Invoke-Expression)cmdlet 可执行在使用 call 运算符时导致分析错误的代码。</span><span class="sxs-lookup"><span data-stu-id="2cde7-181">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

<span data-ttu-id="2cde7-182">可以使用 call 运算符来执行使用其文件名的脚本。</span><span class="sxs-lookup"><span data-stu-id="2cde7-182">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="2cde7-183">下面的示例显示了包含空格的脚本文件名。</span><span class="sxs-lookup"><span data-stu-id="2cde7-183">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="2cde7-184">当你尝试执行脚本时，PowerShell 将显示包含文件名的带引号的字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="2cde7-184">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="2cde7-185">Call 运算符用于执行包含文件名的字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="2cde7-185">The call operator allows you to execute the contents of the string containing the filename.</span></span>

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

<span data-ttu-id="2cde7-186">有关脚本块的详细信息，请参阅 [about_Script_Blocks](about_Script_Blocks.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-186">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="background-operator-"></a><span data-ttu-id="2cde7-187">后台运算符 `&`</span><span class="sxs-lookup"><span data-stu-id="2cde7-187">Background operator `&`</span></span>

<span data-ttu-id="2cde7-188">在 PowerShell 作业中，在后台运行管道。</span><span class="sxs-lookup"><span data-stu-id="2cde7-188">Runs the pipeline before it in the background, in a PowerShell job.</span></span> <span data-ttu-id="2cde7-189">此运算符的行为类似于 UNIX control 运算符 and (`&`) ，它在 subshell 中以异步方式运行命令作为作业。</span><span class="sxs-lookup"><span data-stu-id="2cde7-189">This operator acts similarly to the UNIX control operator ampersand (`&`), which runs the command before it asynchronously in subshell as a job.</span></span>

<span data-ttu-id="2cde7-190">此运算符在功能上等效于 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-190">This operator is functionally equivalent to `Start-Job`.</span></span> <span data-ttu-id="2cde7-191">默认情况下，后台运算符启动启动并行任务的调用方的当前工作目录中的作业。</span><span class="sxs-lookup"><span data-stu-id="2cde7-191">By default, the background operator starts the jobs in the current working directory of the caller that started the parallel tasks.</span></span> <span data-ttu-id="2cde7-192">下面的示例演示后台作业运算符的基本用法。</span><span class="sxs-lookup"><span data-stu-id="2cde7-192">The following example demonstrates basic usage of the background job operator.</span></span>

```powershell
Get-Process -Name pwsh &
```

<span data-ttu-id="2cde7-193">此命令在功能上等同于以下用法 `Start-Job` ：</span><span class="sxs-lookup"><span data-stu-id="2cde7-193">That command is functionally equivalent to the following usage of `Start-Job`:</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process -Name pwsh}
```

<span data-ttu-id="2cde7-194">就像一样 `Start-Job` ， `&` 后台运算符返回 `Job` 对象。</span><span class="sxs-lookup"><span data-stu-id="2cde7-194">Just like `Start-Job`, the `&` background operator returns a `Job` object.</span></span> <span data-ttu-id="2cde7-195">此对象可与和一起 `Receive-Job` 使用 `Remove-Job` ，就像你已使用 `Start-Job` 来启动该作业一样。</span><span class="sxs-lookup"><span data-stu-id="2cde7-195">This object can be used with `Receive-Job` and `Remove-Job`, just as if you had used `Start-Job` to start the job.</span></span>

```powershell
$job = Get-Process -Name pwsh &
Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

```powershell
Remove-Job $job
```

<span data-ttu-id="2cde7-196">`&`后台运算符也是语句终止符，就像)  (的 UNIX 控件运算符 "and" `&` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-196">The `&` background operator is also a statement terminator, just like the UNIX control operator ampersand (`&`).</span></span> <span data-ttu-id="2cde7-197">这允许您在后台运算符之后调用其他命令 `&` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-197">This allows you to invoke additional commands after the `&` background operator.</span></span> <span data-ttu-id="2cde7-198">下面的示例演示如何在后台运算符之后调用其他命令 `&` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-198">The following example demonstrates the invocation of additional commands after the `&` background operator.</span></span>

```powershell
$job = Get-Process -Name pwsh & Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

<span data-ttu-id="2cde7-199">这等效于以下脚本：</span><span class="sxs-lookup"><span data-stu-id="2cde7-199">This is equivalent to the following script:</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process -Name pwsh}
Receive-Job $job -Wait
```

<span data-ttu-id="2cde7-200">如果要运行多个命令，每个命令都在其自己的后台进程中，但全部在一行上，只需在 `&` 每个命令前后放置。</span><span class="sxs-lookup"><span data-stu-id="2cde7-200">If you want to run multiple commands, each in their own background process but all on one line, simply place `&` between and after each of the commands.</span></span>

```powershell
Get-Process -Name pwsh & Get-Service -Name BITS & Get-CimInstance -ClassName Win32_ComputerSystem &
```

<span data-ttu-id="2cde7-201">有关 PowerShell 作业的详细信息，请参阅 [about_Jobs](about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-201">For more information on PowerShell jobs, see [about_Jobs](about_Jobs.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="2cde7-202">Cast 运算符 `[ ]`</span><span class="sxs-lookup"><span data-stu-id="2cde7-202">Cast operator `[ ]`</span></span>

<span data-ttu-id="2cde7-203">将对象转换或限制为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="2cde7-203">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="2cde7-204">如果无法转换对象，PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="2cde7-204">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="2cde7-205">使用 [强制转换表示法](about_Variables.md)赋值时，还可以执行强制转换。</span><span class="sxs-lookup"><span data-stu-id="2cde7-205">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="2cde7-206">逗号运算符 `,`</span><span class="sxs-lookup"><span data-stu-id="2cde7-206">Comma operator `,`</span></span>

<span data-ttu-id="2cde7-207">作为二元运算符，逗号创建数组或追加到所创建的数组。</span><span class="sxs-lookup"><span data-stu-id="2cde7-207">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="2cde7-208">在表达式模式下，作为一元运算符，逗号创建只包含一个成员的数组。</span><span class="sxs-lookup"><span data-stu-id="2cde7-208">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="2cde7-209">将逗号置于成员前面。</span><span class="sxs-lookup"><span data-stu-id="2cde7-209">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="2cde7-210">由于 `Write-Object` 需要参数，因此必须将表达式放在括号中。</span><span class="sxs-lookup"><span data-stu-id="2cde7-210">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="2cde7-211">网点采购运算符 `.`</span><span class="sxs-lookup"><span data-stu-id="2cde7-211">Dot sourcing operator `.`</span></span>

<span data-ttu-id="2cde7-212">在当前作用域中运行脚本，以便将脚本创建的所有函数、别名和变量添加到当前作用域中，并覆盖现有作用域。</span><span class="sxs-lookup"><span data-stu-id="2cde7-212">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="2cde7-213">脚本声明的参数成为变量。</span><span class="sxs-lookup"><span data-stu-id="2cde7-213">Parameters declared by the script become variables.</span></span> <span data-ttu-id="2cde7-214">未为其提供值的参数将成为没有值的变量。</span><span class="sxs-lookup"><span data-stu-id="2cde7-214">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="2cde7-215">但是， `$args` 会保留自动变量。</span><span class="sxs-lookup"><span data-stu-id="2cde7-215">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="2cde7-216">点采购运算符后跟一个空格。</span><span class="sxs-lookup"><span data-stu-id="2cde7-216">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="2cde7-217">使用空格将点与表示当前目录的点 (`.`) 符号区分开来。</span><span class="sxs-lookup"><span data-stu-id="2cde7-217">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="2cde7-218">在下面的示例中，当前目录中的 Sample.ps1 脚本在当前作用域中运行。</span><span class="sxs-lookup"><span data-stu-id="2cde7-218">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="2cde7-219">Format 运算符 `-f`</span><span class="sxs-lookup"><span data-stu-id="2cde7-219">Format operator `-f`</span></span>

<span data-ttu-id="2cde7-220">使用字符串对象的 format 方法格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="2cde7-220">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="2cde7-221">在运算符的左侧输入格式字符串，并在运算符右侧输入要设置格式的对象。</span><span class="sxs-lookup"><span data-stu-id="2cde7-221">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="2cde7-222">如果需要 `{}` 在带格式的字符串中保留大括号 () ，可以通过将大括号加倍来对它们进行转义。</span><span class="sxs-lookup"><span data-stu-id="2cde7-222">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="2cde7-223">有关详细信息，请参阅 [字符串格式](/dotnet/api/system.string.format) 方法和 [复合格式设置](/dotnet/standard/base-types/composite-formatting)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-223">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="2cde7-224">Index 运算符 `[ ]`</span><span class="sxs-lookup"><span data-stu-id="2cde7-224">Index operator `[ ]`</span></span>

<span data-ttu-id="2cde7-225">从索引集合中选择对象，如数组和哈希表。</span><span class="sxs-lookup"><span data-stu-id="2cde7-225">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="2cde7-226">数组索引是从零开始的，因此第一个对象的索引为 `[0]` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-226">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="2cde7-227">对于仅)  (数组，还可以使用负索引来获取最后一个值。</span><span class="sxs-lookup"><span data-stu-id="2cde7-227">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="2cde7-228">哈希表按键值编制索引。</span><span class="sxs-lookup"><span data-stu-id="2cde7-228">Hash tables are indexed by key value.</span></span>

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a><span data-ttu-id="2cde7-229">管道运算符 `|`</span><span class="sxs-lookup"><span data-stu-id="2cde7-229">Pipeline operator `|`</span></span>

<span data-ttu-id="2cde7-230">将 ( "管道" ) 命令的输出发送到其后的命令。</span><span class="sxs-lookup"><span data-stu-id="2cde7-230">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="2cde7-231">如果输出中包含一个 "集合" )  (多个对象，则管道运算符每次发送一个对象。</span><span class="sxs-lookup"><span data-stu-id="2cde7-231">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="pipeline-chain-operators--and-"></a><span data-ttu-id="2cde7-232">管道链运算符 `&&` 和 `||`</span><span class="sxs-lookup"><span data-stu-id="2cde7-232">Pipeline chain operators `&&` and `||`</span></span>

<span data-ttu-id="2cde7-233">根据左侧管道的成功，有条件地执行右侧管道。</span><span class="sxs-lookup"><span data-stu-id="2cde7-233">Conditionally execute the right-hand side pipeline based on the success of the left-hand side pipeline.</span></span>

```powershell
# If Get-Process successfully finds a process called notepad,
# Stop-Process -Name notepad is called
Get-Process notepad && Stop-Process -Name notepad
```

```powershell
# If npm install fails, the node_modules directory is removed
npm install || Remove-Item -Recurse ./node_modules
```

<span data-ttu-id="2cde7-234">有关详细信息，请参阅 [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-234">For more information, see [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).</span></span>

#### <a name="range-operator-"></a><span data-ttu-id="2cde7-235">范围运算符 `..`</span><span class="sxs-lookup"><span data-stu-id="2cde7-235">Range operator `..`</span></span>

<span data-ttu-id="2cde7-236">表示整数数组中的顺序整数（给定上下限）。</span><span class="sxs-lookup"><span data-stu-id="2cde7-236">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="2cde7-237">您还可以按相反的顺序创建范围。</span><span class="sxs-lookup"><span data-stu-id="2cde7-237">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

<span data-ttu-id="2cde7-238">从 PowerShell 6 开始，range 运算符使用 **字符** 和 **整数** 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-238">Beginning in PowerShell 6, the range operator works with **Characters** as well as **Integers**.</span></span>

<span data-ttu-id="2cde7-239">若要创建字符范围，请将边界字符括在引号中。</span><span class="sxs-lookup"><span data-stu-id="2cde7-239">To create a range of characters, enclose the boundary characters in quotes.</span></span>

```powershell
PS> 'a'..'f'
a
b
c
d
e
f
```

```powershell
PS> 'F'..'A'
F
E
D
C
B
A
```

#### <a name="member-access-operator-"></a><span data-ttu-id="2cde7-240">成员访问运算符 `.`</span><span class="sxs-lookup"><span data-stu-id="2cde7-240">Member access operator `.`</span></span>

<span data-ttu-id="2cde7-241">访问对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="2cde7-241">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="2cde7-242">成员名称可以是表达式。</span><span class="sxs-lookup"><span data-stu-id="2cde7-242">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="2cde7-243">静态成员运算符 `::`</span><span class="sxs-lookup"><span data-stu-id="2cde7-243">Static member operator `::`</span></span>

<span data-ttu-id="2cde7-244">调用 .NET Framework 类的静态属性和方法。</span><span class="sxs-lookup"><span data-stu-id="2cde7-244">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="2cde7-245">若要查找对象的静态属性和方法，请使用 cmdlet 的静态参数 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-245">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="2cde7-246">成员名称可以是表达式。</span><span class="sxs-lookup"><span data-stu-id="2cde7-246">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

#### <a name="ternary-operator--if-true--if-false"></a><span data-ttu-id="2cde7-247">三元运算符 `? <if-true> : <if-false>`</span><span class="sxs-lookup"><span data-stu-id="2cde7-247">Ternary operator `? <if-true> : <if-false>`</span></span>

<span data-ttu-id="2cde7-248">在简单的条件情况下，可以使用三元运算符替换 `if-else` 语句。</span><span class="sxs-lookup"><span data-stu-id="2cde7-248">You can use the ternary operator as a replacement for the `if-else` statement in simple conditional cases.</span></span>

<span data-ttu-id="2cde7-249">有关详细信息，请参阅 [about_If](about_If.md)。</span><span class="sxs-lookup"><span data-stu-id="2cde7-249">For more information, see [about_If](about_If.md).</span></span>

#### <a name="null-coalescing-operator-"></a><span data-ttu-id="2cde7-250">Null 合并运算符 `??`</span><span class="sxs-lookup"><span data-stu-id="2cde7-250">Null-coalescing operator `??`</span></span>

<span data-ttu-id="2cde7-251">如果 null 合并运算符 `??` 不为 null，则它返回其左操作数的值。</span><span class="sxs-lookup"><span data-stu-id="2cde7-251">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span> <span data-ttu-id="2cde7-252">否则，它将计算右操作数并返回其结果。</span><span class="sxs-lookup"><span data-stu-id="2cde7-252">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="2cde7-253">如果左操作数的计算结果为非 null，则 `??` 运算符不会计算其右操作数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-253">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
```

```Output
100
```

<span data-ttu-id="2cde7-254">在下面的示例中，不会计算右侧的操作数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-254">In the following example, the right-hand operand won't be evaluated.</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-coalescing-assignment-operator-"></a><span data-ttu-id="2cde7-255">Null 合并赋值运算符 `??=`</span><span class="sxs-lookup"><span data-stu-id="2cde7-255">Null-coalescing assignment operator `??=`</span></span>

<span data-ttu-id="2cde7-256">`??=`如果左操作数的计算结果为 null，则 null 合并赋值运算符仅将其右操作数的值分配给其左操作数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-256">The null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="2cde7-257">如果左操作数的计算结果为非 null，则 `??=` 运算符不会计算其右操作数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-257">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
```

```Output
100
```

<span data-ttu-id="2cde7-258">在下面的示例中，不会计算右侧的操作数。</span><span class="sxs-lookup"><span data-stu-id="2cde7-258">In the following example, the right-hand operand won't be evaluated.</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-conditional-operators--and-"></a><span data-ttu-id="2cde7-259">Null 条件运算符 `?.` 和 `?[]`</span><span class="sxs-lookup"><span data-stu-id="2cde7-259">Null-conditional operators `?.` and `?[]`</span></span>

> [!NOTE]
> <span data-ttu-id="2cde7-260">此功能已从实验迁移到 PowerShell 7.1 中的主流。</span><span class="sxs-lookup"><span data-stu-id="2cde7-260">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

<span data-ttu-id="2cde7-261">`?.`只有当操作数的计算结果为非 null 时，null 条件运算符才会将成员访问、或元素访问权限应用于 `?[]` 其操作数; 否则，它将返回 null。</span><span class="sxs-lookup"><span data-stu-id="2cde7-261">A null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

<span data-ttu-id="2cde7-262">由于 PowerShell 允许 `?` 作为变量名称的一部分，因此使用这些运算符需要变量名称的形式规范。</span><span class="sxs-lookup"><span data-stu-id="2cde7-262">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="2cde7-263">因此，使用 `{}` 将变量名称括起来（如 `${a}`）或 `?` 是变量名称 `${a?}` 的一部分时需要形式规范。</span><span class="sxs-lookup"><span data-stu-id="2cde7-263">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="2cde7-264">在下面的示例中，将返回 **PropName** 的值。</span><span class="sxs-lookup"><span data-stu-id="2cde7-264">In the following example, the value of **PropName** is returned.</span></span>

```powershell
$a = @{ PropName = 100 }
${a}?.PropName
```

```Output
100
```

<span data-ttu-id="2cde7-265">下面的示例将返回 null，而不会尝试访问成员名称 **PropName** 。</span><span class="sxs-lookup"><span data-stu-id="2cde7-265">The following example will return null, without trying to access the member name **PropName**.</span></span>

```powershell
$a = $null
${a}?.PropName
```

<span data-ttu-id="2cde7-266">同样，将返回元素的值。</span><span class="sxs-lookup"><span data-stu-id="2cde7-266">Similarly, the value of the element will be returned.</span></span>

```powershell
$a = 1..10
${a}?[0]
```

```Output
1
```

<span data-ttu-id="2cde7-267">如果操作数为 null，则不会访问该元素，并返回 null。</span><span class="sxs-lookup"><span data-stu-id="2cde7-267">And when the operand is null, the element isn't accessed and null is returned.</span></span>

```PowerShell
$a = $null
${a}?[0]
```

> [!NOTE]
> <span data-ttu-id="2cde7-268">由于 PowerShell 允许 `?` 作为变量名称的一部分，因此使用这些运算符需要变量名称的形式规范。</span><span class="sxs-lookup"><span data-stu-id="2cde7-268">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="2cde7-269">因此，使用 `{}` 将变量名称括起来（如 `${a}`）或 `?` 是变量名称 `${a?}` 的一部分时需要形式规范。</span><span class="sxs-lookup"><span data-stu-id="2cde7-269">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>
>
> <span data-ttu-id="2cde7-270">的变量名语法 `${<name>}` 不应与 `$()` 子表达式运算符混淆。</span><span class="sxs-lookup"><span data-stu-id="2cde7-270">The variable name syntax of `${<name>}` should not be confused with the `$()` subexpression operator.</span></span> <span data-ttu-id="2cde7-271">有关详细信息，请参阅 [about_Variables](about_Variables.md#Variable-names-that-include-special-characters)的变量名称部分。</span><span class="sxs-lookup"><span data-stu-id="2cde7-271">For more information, see Variable name section of [about_Variables](about_Variables.md#Variable-names-that-include-special-characters).</span></span>

## <a name="see-also"></a><span data-ttu-id="2cde7-272">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cde7-272">See also</span></span>

[<span data-ttu-id="2cde7-273">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="2cde7-273">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="2cde7-274">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="2cde7-274">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="2cde7-275">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="2cde7-275">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="2cde7-276">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="2cde7-276">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="2cde7-277">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="2cde7-277">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="2cde7-278">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="2cde7-278">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="2cde7-279">about_Pipeline_Chain_Operators</span><span class="sxs-lookup"><span data-stu-id="2cde7-279">about_Pipeline_Chain_Operators</span></span>](about_Pipeline_Chain_Operators.md)

[<span data-ttu-id="2cde7-280">about_Split</span><span class="sxs-lookup"><span data-stu-id="2cde7-280">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="2cde7-281">about_Join</span><span class="sxs-lookup"><span data-stu-id="2cde7-281">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="2cde7-282">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="2cde7-282">about_Redirection</span></span>](about_Redirection.md)
