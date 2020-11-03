---
description: 介绍如何使用运算符为变量赋值。
keywords: powershell,cmdlet
ms.date: 04/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: b9cb0f6a972ef627b7ce2621db489896992b406e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200134"
---
# <a name="about-assignment-operators"></a><span data-ttu-id="cf211-104">关于赋值运算符</span><span class="sxs-lookup"><span data-stu-id="cf211-104">About Assignment Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="cf211-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="cf211-105">Short description</span></span>
<span data-ttu-id="cf211-106">介绍如何使用运算符为变量赋值。</span><span class="sxs-lookup"><span data-stu-id="cf211-106">Describes how to use operators to assign values to variables.</span></span>

## <a name="long-description"></a><span data-ttu-id="cf211-107">长说明</span><span class="sxs-lookup"><span data-stu-id="cf211-107">Long description</span></span>

<span data-ttu-id="cf211-108">赋值运算符将一个或多个值分配给变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-108">Assignment operators assign one or more values to a variable.</span></span> <span data-ttu-id="cf211-109">它们可以对赋值前的值执行数字运算。</span><span class="sxs-lookup"><span data-stu-id="cf211-109">They can perform numeric operations on the values before the assignment.</span></span>

<span data-ttu-id="cf211-110">PowerShell 支持以下赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="cf211-110">PowerShell supports the following assignment operators.</span></span>

|<span data-ttu-id="cf211-111">运算符</span><span class="sxs-lookup"><span data-stu-id="cf211-111">Operator</span></span>|<span data-ttu-id="cf211-112">说明</span><span class="sxs-lookup"><span data-stu-id="cf211-112">Description</span></span>                                                  |
|--------|-------------------------------------------------------------|
|=       |<span data-ttu-id="cf211-113">将变量的值设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="cf211-113">Sets the value of a variable to the specified value.</span></span>         |
|+=      |<span data-ttu-id="cf211-114">将变量的值增加指定的值，或</span><span class="sxs-lookup"><span data-stu-id="cf211-114">Increases the value of a variable by the specified value, or</span></span> |
|        |<span data-ttu-id="cf211-115">将指定值追加到现有值。</span><span class="sxs-lookup"><span data-stu-id="cf211-115">appends the specified value to the existing value.</span></span>           |
|-=      |<span data-ttu-id="cf211-116">将变量的值降低指定的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-116">Decreases the value of a variable by the specified value.</span></span>    |
|*=      |<span data-ttu-id="cf211-117">将变量的值乘以指定的值，或</span><span class="sxs-lookup"><span data-stu-id="cf211-117">Multiplies the value of a variable by the specified value, or</span></span>|
|        |<span data-ttu-id="cf211-118">将指定值追加到现有值。</span><span class="sxs-lookup"><span data-stu-id="cf211-118">appends the specified value to the existing value.</span></span>           |
|/=      |<span data-ttu-id="cf211-119">将变量的值除以指定值。</span><span class="sxs-lookup"><span data-stu-id="cf211-119">Divides the value of a variable by the specified value.</span></span>      |
|%=      |<span data-ttu-id="cf211-120">将变量的值除以指定的值并</span><span class="sxs-lookup"><span data-stu-id="cf211-120">Divides the value of a variable by the specified value and</span></span>   |
|        |<span data-ttu-id="cf211-121">然后，将余数 (取模) 赋给该变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-121">then assigns the remainder (modulus) to the variable.</span></span>        |
|++      |<span data-ttu-id="cf211-122">增加变量、可赋值属性的值，或</span><span class="sxs-lookup"><span data-stu-id="cf211-122">Increases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="cf211-123">数组元素1。</span><span class="sxs-lookup"><span data-stu-id="cf211-123">array element by 1.</span></span>                                          |
|--      |<span data-ttu-id="cf211-124">减小变量、可赋值属性的值，或</span><span class="sxs-lookup"><span data-stu-id="cf211-124">Decreases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="cf211-125">数组元素1。</span><span class="sxs-lookup"><span data-stu-id="cf211-125">array element by 1.</span></span>                                          |

## <a name="syntax"></a><span data-ttu-id="cf211-126">语法</span><span class="sxs-lookup"><span data-stu-id="cf211-126">Syntax</span></span>

<span data-ttu-id="cf211-127">赋值运算符的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-127">The syntax of the assignment operators is as follows:</span></span>

<span data-ttu-id="cf211-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span><span class="sxs-lookup"><span data-stu-id="cf211-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span></span>

<span data-ttu-id="cf211-129">可赋值表达式包含变量和属性。</span><span class="sxs-lookup"><span data-stu-id="cf211-129">Assignable expressions include variables and properties.</span></span> <span data-ttu-id="cf211-130">该值可以是单个值、值的数组，也可以是命令、表达式或语句。</span><span class="sxs-lookup"><span data-stu-id="cf211-130">The value can be a single value, an array of values, or a command, expression, or statement.</span></span>

<span data-ttu-id="cf211-131">递增和递减运算符是一元运算符。</span><span class="sxs-lookup"><span data-stu-id="cf211-131">The increment and decrement operators are unary operators.</span></span> <span data-ttu-id="cf211-132">每个都具有前缀和后缀版本。</span><span class="sxs-lookup"><span data-stu-id="cf211-132">Each has prefix and postfix versions.</span></span>

`<assignable-expression><operator>`
`<operator><assignable-expression>`

<span data-ttu-id="cf211-133">可分配的表达式必须是数字，或者必须可以转换为数字。</span><span class="sxs-lookup"><span data-stu-id="cf211-133">The assignable expression must be a number or it must be convertible to a number.</span></span>

## <a name="assigning-values"></a><span data-ttu-id="cf211-134">赋值</span><span class="sxs-lookup"><span data-stu-id="cf211-134">Assigning values</span></span>

<span data-ttu-id="cf211-135">变量称为存储值的内存空间。</span><span class="sxs-lookup"><span data-stu-id="cf211-135">Variables are named memory spaces that store values.</span></span> <span data-ttu-id="cf211-136">使用赋值运算符将值存储在变量中 `=` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-136">You store the values in variables by using the assignment operator `=`.</span></span> <span data-ttu-id="cf211-137">新值可以替换变量的现有值，也可以将新值追加到现有值。</span><span class="sxs-lookup"><span data-stu-id="cf211-137">The new value can replace the existing value of the variable, or you can append a new value to the existing value.</span></span>

<span data-ttu-id="cf211-138">基本赋值运算符是等号 `=` `(ASCII 61)` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-138">The basic assignment operator is the equal sign `=` `(ASCII 61)`.</span></span> <span data-ttu-id="cf211-139">例如，下面的语句将值 PowerShell 赋给 `$MyShell` 变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-139">For example, the following statement assigns the value PowerShell to the `$MyShell` variable:</span></span>

```powershell
$MyShell = "PowerShell"
```

<span data-ttu-id="cf211-140">在 PowerShell 中为变量分配值时，如果该变量尚不存在，则将创建它。</span><span class="sxs-lookup"><span data-stu-id="cf211-140">When you assign a value to a variable in PowerShell, the variable is created if it did not already exist.</span></span> <span data-ttu-id="cf211-141">例如，以下两个赋值语句中的第一个语句将创建 `$a` 变量，并将值6赋给 `$a` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-141">For example, the first of the following two assignment statements creates the `$a` variable and assigns a value of 6 to `$a`.</span></span> <span data-ttu-id="cf211-142">第二个赋值语句将值12赋给 `$a` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-142">The second assignment statement assigns a value of 12 to `$a`.</span></span> <span data-ttu-id="cf211-143">第一个语句创建新变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-143">The first statement creates a new variable.</span></span> <span data-ttu-id="cf211-144">第二个语句仅更改其值：</span><span class="sxs-lookup"><span data-stu-id="cf211-144">The second statement changes only its value:</span></span>

```powershell
$a = 6
$a = 12
```

<span data-ttu-id="cf211-145">PowerShell 中的变量不具有特定的数据类型，除非你强制转换它们。</span><span class="sxs-lookup"><span data-stu-id="cf211-145">Variables in PowerShell do not have a specific data type unless you cast them.</span></span>
<span data-ttu-id="cf211-146">当变量只包含一个对象时，该变量将采用该对象的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-146">When a variable contains only one object, the variable takes the data type of that object.</span></span> <span data-ttu-id="cf211-147">当变量包含一个对象集合时，该变量的数据类型为 System.object。</span><span class="sxs-lookup"><span data-stu-id="cf211-147">When a variable contains a collection of objects, the variable has the System.Object data type.</span></span> <span data-ttu-id="cf211-148">因此，可以将任何类型的对象分配给集合。</span><span class="sxs-lookup"><span data-stu-id="cf211-148">Therefore, you can assign any type of object to the collection.</span></span> <span data-ttu-id="cf211-149">下面的示例演示可以将进程对象、服务对象、字符串和整数添加到变量中，而不会生成错误：</span><span class="sxs-lookup"><span data-stu-id="cf211-149">The following example shows that you can add process objects, service objects, strings, and integers to a variable without generating an error:</span></span>

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

<span data-ttu-id="cf211-150">由于赋值运算符的 `=` 优先级低于管道运算符 `|` ，因此不需要使用括号将命令管道的结果分配给变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-150">Because the assignment operator `=` has a lower precedence than the pipeline operator `|`, parentheses are not required to assign the result of a command pipeline to a variable.</span></span> <span data-ttu-id="cf211-151">例如，以下命令将对计算机上的服务进行排序，然后将已排序的服务分配给 `$a` 变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-151">For example, the following command sorts the services on the computer and then assigns the sorted services to the `$a` variable:</span></span>

```powershell
$a = Get-Service | Sort-Object -Property name
```

<span data-ttu-id="cf211-152">还可以将语句创建的值分配给变量，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-152">You can also assign the value created by a statement to a variable, as in the following example:</span></span>

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

<span data-ttu-id="cf211-153">`$a`如果的值小于零，则此示例将零赋给该变量 `$b` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-153">This example assigns zero to the `$a` variable if the value of `$b` is less than zero.</span></span> <span data-ttu-id="cf211-154">`$b` `$a` 如果的值不小于零，则它将的值分配给 `$b` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-154">It assigns the value of `$b` to `$a` if the value of `$b` is not less than zero.</span></span>

### <a name="the-assignment-operator"></a><span data-ttu-id="cf211-155">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="cf211-155">The assignment operator</span></span>

<span data-ttu-id="cf211-156">赋值运算符将 `=` 值分配给变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-156">The assignment operator `=` assigns values to variables.</span></span> <span data-ttu-id="cf211-157">如果该变量已经具有值，则赋值运算符将 `=` 替换该值，而不会发出警告。</span><span class="sxs-lookup"><span data-stu-id="cf211-157">If the variable already has a value, the assignment operator `=` replaces the value without warning.</span></span>

<span data-ttu-id="cf211-158">以下语句将整数值6赋给 `$a` 变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-158">The following statement assigns the integer value 6 to the `$a` variable:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="cf211-159">若要为变量赋值，请将字符串值用引号引起来，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-159">To assign a string value to a variable, enclose the string value in quotation marks, as follows:</span></span>

```powershell
$a = "baseball"
```

<span data-ttu-id="cf211-160">若要将数组 (多个值) 赋给一个变量，请使用逗号分隔这些值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-160">To assign an array (multiple values) to a variable, separate the values with commas, as follows:</span></span>

```powershell
$a = "apple", "orange", "lemon", "grape"
```

<span data-ttu-id="cf211-161">若要为变量分配哈希表，请在 PowerShell 中使用标准哈希表表示法。</span><span class="sxs-lookup"><span data-stu-id="cf211-161">To assign a hash table to a variable, use the standard hash table notation in PowerShell.</span></span> <span data-ttu-id="cf211-162">键入一个 at 符号， `@` 后跟用分号分隔的键/值对， `;` 并将其括在大括号中 `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-162">Type an at sign `@` followed by key/value pairs that are separated by semicolons `;` and enclosed in braces `{ }`.</span></span> <span data-ttu-id="cf211-163">例如，若要为该变量分配一个哈希表 `$a` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="cf211-163">For example, to assign a hash table to the `$a` variable, type:</span></span>

```powershell
$a = @{one=1; two=2; three=3}
```

<span data-ttu-id="cf211-164">若要为变量指定十六进制值，请在值前面加上 `0x` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-164">To assign hexadecimal values to a variable, precede the value with `0x`.</span></span>
<span data-ttu-id="cf211-165">PowerShell 将 (0x10) 的十六进制值转换为十进制值 (在本例中为 16) 并将该值分配给 `$a` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-165">PowerShell converts the hexadecimal value (0x10) to a decimal value (in this case, 16) and assigns that value to the `$a` variable.</span></span> <span data-ttu-id="cf211-166">例如，若要将0x10 的值分配给 `$a` 变量，请键入：</span><span class="sxs-lookup"><span data-stu-id="cf211-166">For example, to assign a value of 0x10 to the `$a` variable, type:</span></span>

```powershell
$a = 0x10
```

<span data-ttu-id="cf211-167">若要为某个变量分配一个指数值，请键入该根号码、字母 `e` 和一个表示10的倍数的数字。</span><span class="sxs-lookup"><span data-stu-id="cf211-167">To assign an exponential value to a variable, type the root number, the letter `e`, and a number that represents a multiple of 10.</span></span> <span data-ttu-id="cf211-168">例如，若要将3.1415 的1000幂赋值给 `$a` 变量，请键入：</span><span class="sxs-lookup"><span data-stu-id="cf211-168">For example, to assign a value of 3.1415 to the power of 1,000 to the `$a` variable, type:</span></span>

```powershell
$a = 3.1415e3
```

<span data-ttu-id="cf211-169">PowerShell 还可以将千字节 `KB` 、兆字节 `MB` 和 gb 数转换为 `GB` 字节。</span><span class="sxs-lookup"><span data-stu-id="cf211-169">PowerShell can also convert kilobytes `KB`, megabytes `MB`, and gigabytes `GB` into bytes.</span></span> <span data-ttu-id="cf211-170">例如，若要为该变量分配 10 kb 值 `$a` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="cf211-170">For example, to assign a value of 10 kilobytes to the `$a` variable, type:</span></span>

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a><span data-ttu-id="cf211-171">赋值 by 加法运算符</span><span class="sxs-lookup"><span data-stu-id="cf211-171">The assignment by addition operator</span></span>

<span data-ttu-id="cf211-172">加法运算符赋值会 `+=` 递增变量的值，或将指定值追加到现有值。</span><span class="sxs-lookup"><span data-stu-id="cf211-172">The assignment by addition operator `+=` either increments the value of a variable or appends the specified value to the existing value.</span></span> <span data-ttu-id="cf211-173">操作取决于变量是否具有数值类型或字符串类型，以及变量是否包含单个值 (标量) 或 (集合) 的多个值。</span><span class="sxs-lookup"><span data-stu-id="cf211-173">The action depends on whether the variable has a numeric or string type and whether the variable contains a single value (a scalar) or multiple values (a collection).</span></span>

<span data-ttu-id="cf211-174">`+=`运算符组合了两个操作。</span><span class="sxs-lookup"><span data-stu-id="cf211-174">The `+=` operator combines two operations.</span></span> <span data-ttu-id="cf211-175">首先，它添加，然后分配。</span><span class="sxs-lookup"><span data-stu-id="cf211-175">First, it adds, and then it assigns.</span></span>
<span data-ttu-id="cf211-176">因此，以下语句是等效的：</span><span class="sxs-lookup"><span data-stu-id="cf211-176">Therefore, the following statements are equivalent:</span></span>

```powershell
$a += 2
$a = ($a + 2)
```

<span data-ttu-id="cf211-177">当变量包含单个数值时， `+=` 运算符会按运算符右侧的量递增现有值。</span><span class="sxs-lookup"><span data-stu-id="cf211-177">When the variable contains a single numeric value, the `+=` operator increments the existing value by the amount on the right side of the operator.</span></span> <span data-ttu-id="cf211-178">然后，运算符将生成的值分配给变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-178">Then, the operator assigns the resulting value to the variable.</span></span> <span data-ttu-id="cf211-179">下面的示例演示如何使用 `+=` 运算符增加变量的值：</span><span class="sxs-lookup"><span data-stu-id="cf211-179">The following example shows how to use the `+=` operator to increase the value of a variable:</span></span>

```powershell
$a = 4
$a += 2
$a
```

```
6
```

<span data-ttu-id="cf211-180">当变量的值是一个字符串时，运算符右侧的值将追加到字符串，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-180">When the value of the variable is a string, the value on the right side of the operator is appended to the string, as follows:</span></span>

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

<span data-ttu-id="cf211-181">当变量的值为数组时， `+=` 运算符将运算符右侧的值追加到数组中。</span><span class="sxs-lookup"><span data-stu-id="cf211-181">When the value of the variable is an array, the `+=` operator appends the values on the right side of the operator to the array.</span></span> <span data-ttu-id="cf211-182">除非通过强制转换来显式键入数组，否则可将任何类型的值追加到数组，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-182">Unless the array is explicitly typed by casting, you can append any type of value to the array, as follows:</span></span>

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

<span data-ttu-id="cf211-183">and</span><span class="sxs-lookup"><span data-stu-id="cf211-183">and</span></span>

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

<span data-ttu-id="cf211-184">当变量的值是一个哈希表时， `+=` 运算符将运算符右侧的值追加到哈希表中。</span><span class="sxs-lookup"><span data-stu-id="cf211-184">When the value of a variable is a hash table, the `+=` operator appends the value on the right side of the operator to the hash table.</span></span> <span data-ttu-id="cf211-185">但是，因为可以添加到哈希表中的唯一类型是另一个哈希表，所有其他赋值都将失败。</span><span class="sxs-lookup"><span data-stu-id="cf211-185">However, because the only type that you can add to a hash table is another hash table, all other assignments fail.</span></span>

<span data-ttu-id="cf211-186">例如，下面的命令将一个哈希表分配给该 `$a` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-186">For example, the following command assigns a hash table to the `$a` variable.</span></span>
<span data-ttu-id="cf211-187">然后，它使用 `+=` 运算符将其他哈希表追加到现有哈希表，从而有效地将新的键/值对添加到现有哈希表中。</span><span class="sxs-lookup"><span data-stu-id="cf211-187">Then, it uses the `+=` operator to append another hash table to the existing hash table, effectively adding a new key/value pair to the existing hash table.</span></span>
<span data-ttu-id="cf211-188">此命令成功，如输出中所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-188">This command succeeds, as shown in the output:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

<span data-ttu-id="cf211-189">以下命令尝试将整数 "1" 追加到变量中的哈希表 `$a` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-189">The following command attempts to append an integer "1" to the hash table in the `$a` variable.</span></span> <span data-ttu-id="cf211-190">此命令失败：</span><span class="sxs-lookup"><span data-stu-id="cf211-190">This command fails:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a><span data-ttu-id="cf211-191">通过减法运算符赋值</span><span class="sxs-lookup"><span data-stu-id="cf211-191">The assignment by subtraction operator</span></span>

<span data-ttu-id="cf211-192">通过减法运算符赋值， `-=` 按运算符右侧指定的值递减变量的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-192">The assignment by subtraction operator `-=` decrements the value of a variable by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="cf211-193">此运算符不能与字符串变量一起使用，并且不能用于从集合中移除元素。</span><span class="sxs-lookup"><span data-stu-id="cf211-193">This operator cannot be used with string variables, and it cannot be used to remove an element from a collection.</span></span>

<span data-ttu-id="cf211-194">`-=`运算符组合了两个操作。</span><span class="sxs-lookup"><span data-stu-id="cf211-194">The `-=` operator combines two operations.</span></span> <span data-ttu-id="cf211-195">首先，它减去，然后分配。</span><span class="sxs-lookup"><span data-stu-id="cf211-195">First, it subtracts, and then it assigns.</span></span> <span data-ttu-id="cf211-196">因此，以下语句是等效的：</span><span class="sxs-lookup"><span data-stu-id="cf211-196">Therefore, the following statements are equivalent:</span></span>

```powershell
$a -= 2
$a = ($a - 2)
```

<span data-ttu-id="cf211-197">下面的示例演示如何使用 `-=` 运算符来减小变量的值：</span><span class="sxs-lookup"><span data-stu-id="cf211-197">The following example shows how to use of the `-=` operator to decrease the value of a variable:</span></span>

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

<span data-ttu-id="cf211-198">还可以使用 `-=` 赋值运算符来减小数值数组成员的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-198">You can also use the `-=` assignment operator to decrease the value of a member of a numeric array.</span></span> <span data-ttu-id="cf211-199">为此，请指定要更改的数组元素的索引。</span><span class="sxs-lookup"><span data-stu-id="cf211-199">To do this, specify the index of the array element that you want to change.</span></span> <span data-ttu-id="cf211-200">在下面的示例中，数组的第三个元素的值 (元素 2) 减1：</span><span class="sxs-lookup"><span data-stu-id="cf211-200">In the following example, the value of the third element of an array (element 2) is decreased by 1:</span></span>

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

<span data-ttu-id="cf211-201">不能使用 `-=` 运算符来删除变量的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-201">You cannot use the `-=` operator to delete the values of a variable.</span></span> <span data-ttu-id="cf211-202">若要删除分配给变量的所有值，请使用 " [清除项](xref:Microsoft.PowerShell.Management.Clear-Item) " 或 " [清除变量](xref:Microsoft.PowerShell.Utility.Clear-Variable) " cmdlet 将或的值分配 `$null` 给 `""` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-202">To delete all the values that are assigned to a variable, use the [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) or [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) cmdlets to assign a value of `$null` or `""` to the variable.</span></span>

```powershell
$a = $null
```

<span data-ttu-id="cf211-203">若要从数组中删除某个特定值，请使用数组表示法将值分配给 `$null` 特定项。</span><span class="sxs-lookup"><span data-stu-id="cf211-203">To delete a particular value from an array, use array notation to assign a value of `$null` to the particular item.</span></span> <span data-ttu-id="cf211-204">例如，下面的语句从数组中删除索引位置 1)  (第二个值：</span><span class="sxs-lookup"><span data-stu-id="cf211-204">For example, the following statement deletes the second value (index position 1) from an array:</span></span>

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

<span data-ttu-id="cf211-205">若要删除某个变量，请使用 " [删除变量](xref:Microsoft.PowerShell.Utility.Remove-Variable) " cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf211-205">To delete a variable, use the [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) cmdlet.</span></span> <span data-ttu-id="cf211-206">当变量显式转换为特定数据类型，并且您需要非类型化的变量时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="cf211-206">This method is useful when the variable is explicitly cast to a particular data type, and you want an untyped variable.</span></span> <span data-ttu-id="cf211-207">以下命令删除 `$a` 变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-207">The following command deletes the `$a` variable:</span></span>

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a><span data-ttu-id="cf211-208">乘法运算符赋值</span><span class="sxs-lookup"><span data-stu-id="cf211-208">The assignment by multiplication operator</span></span>

<span data-ttu-id="cf211-209">乘法运算符的赋值将 `*=` 数值相乘，或追加变量的字符串值的指定副本数。</span><span class="sxs-lookup"><span data-stu-id="cf211-209">The assignment by multiplication operator `*=` multiplies a numeric value or appends the specified number of copies of the string value of a variable.</span></span>

<span data-ttu-id="cf211-210">当变量包含单个数值时，该值将乘以运算符右侧的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-210">When a variable contains a single numeric value, that value is multiplied by the value on the right side of the operator.</span></span> <span data-ttu-id="cf211-211">例如，下面的示例演示如何使用 `*=` 运算符将变量的值相乘：</span><span class="sxs-lookup"><span data-stu-id="cf211-211">For example, the following example shows how to use the `*=` operator to multiply the value of a variable:</span></span>

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

<span data-ttu-id="cf211-212">在这种情况下， `*=` 运算符组合了两个操作。</span><span class="sxs-lookup"><span data-stu-id="cf211-212">In this case, the `*=` operator combines two operations.</span></span> <span data-ttu-id="cf211-213">首先，它将相乘，然后分配。</span><span class="sxs-lookup"><span data-stu-id="cf211-213">First, it multiplies, and then it assigns.</span></span> <span data-ttu-id="cf211-214">因此，以下语句是等效的：</span><span class="sxs-lookup"><span data-stu-id="cf211-214">Therefore, the following statements are equivalent:</span></span>

```powershell
$a *= 2
$a = ($a * 2)
```

<span data-ttu-id="cf211-215">当变量包含字符串值时，PowerShell 会将指定数量的字符串追加到值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-215">When a variable contains a string value, PowerShell appends the specified number of strings to the value, as follows:</span></span>

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

<span data-ttu-id="cf211-216">若要相乘数组的元素，请使用索引来标识要相乘的元素。</span><span class="sxs-lookup"><span data-stu-id="cf211-216">To multiply an element of an array, use an index to identify the element that you want to multiply.</span></span> <span data-ttu-id="cf211-217">例如，以下命令将数组中的第一个元素乘以 (索引位置 0) 2：</span><span class="sxs-lookup"><span data-stu-id="cf211-217">For example, the following command multiplies the first element in the array (index position 0) by 2:</span></span>

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a><span data-ttu-id="cf211-218">按除法运算符赋值</span><span class="sxs-lookup"><span data-stu-id="cf211-218">The assignment by division operator</span></span>

<span data-ttu-id="cf211-219">按除法运算符赋值 `/=` 可将数值除以运算符右侧指定的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-219">The assignment by division operator `/=` divides a numeric value by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="cf211-220">运算符不能与字符串变量一起使用。</span><span class="sxs-lookup"><span data-stu-id="cf211-220">The operator cannot be used with string variables.</span></span>

<span data-ttu-id="cf211-221">`/=`运算符组合了两个操作。</span><span class="sxs-lookup"><span data-stu-id="cf211-221">The `/=` operator combines two operations.</span></span> <span data-ttu-id="cf211-222">首先，它将除以，然后分配。</span><span class="sxs-lookup"><span data-stu-id="cf211-222">First, it divides, and then it assigns.</span></span> <span data-ttu-id="cf211-223">因此，下面两个语句是等效的：</span><span class="sxs-lookup"><span data-stu-id="cf211-223">Therefore, the following two statements are equivalent:</span></span>

```powershell
$a /= 2
$a = ($a / 2)
```

<span data-ttu-id="cf211-224">例如，下面的命令使用 `/=` 运算符来除以变量的值：</span><span class="sxs-lookup"><span data-stu-id="cf211-224">For example, the following command uses the `/=` operator to divide the value of a variable:</span></span>

```powershell
$a = 8
$a /=2
$a
```

```
4
```

<span data-ttu-id="cf211-225">若要拆分数组的元素，请使用索引来标识要更改的元素。</span><span class="sxs-lookup"><span data-stu-id="cf211-225">To divide an element of an array, use an index to identify the element that you want to change.</span></span> <span data-ttu-id="cf211-226">例如，下面的命令将数组中的第二个元素除以 (索引位置 1) 2：</span><span class="sxs-lookup"><span data-stu-id="cf211-226">For example, the following command divides the second element in the array (index position 1) by 2:</span></span>

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a><span data-ttu-id="cf211-227">取模运算符赋值</span><span class="sxs-lookup"><span data-stu-id="cf211-227">The assignment by modulus operator</span></span>

<span data-ttu-id="cf211-228">取模运算符赋值会将 `%=` 变量的值除以运算符右边的值。</span><span class="sxs-lookup"><span data-stu-id="cf211-228">The assignment by modulus operator `%=` divides the value of a variable by the value on the right side of the operator.</span></span> <span data-ttu-id="cf211-229">然后， `%=` 运算符将 (称为取模) 分配给变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-229">Then, the `%=` operator assigns the remainder (known as the modulus) to the variable.</span></span> <span data-ttu-id="cf211-230">仅当变量包含单个数值时，才能使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="cf211-230">You can use this operator only when a variable contains a single numeric value.</span></span> <span data-ttu-id="cf211-231">当变量包含字符串变量或数组时，不能使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="cf211-231">You cannot use this operator when a variable contains a string variable or an array.</span></span>

<span data-ttu-id="cf211-232">`%=`运算符组合了两个操作。</span><span class="sxs-lookup"><span data-stu-id="cf211-232">The `%=` operator combines two operations.</span></span> <span data-ttu-id="cf211-233">首先，它会分割并确定余数，然后将余数赋给该变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-233">First, it divides and determines the remainder, and then it assigns the remainder to the variable.</span></span> <span data-ttu-id="cf211-234">因此，以下语句是等效的：</span><span class="sxs-lookup"><span data-stu-id="cf211-234">Therefore, the following statements are equivalent:</span></span>

```powershell
$a %= 2
$a = ($a % 2)
```

<span data-ttu-id="cf211-235">下面的示例演示如何使用 `%=` 运算符保存商的模数：</span><span class="sxs-lookup"><span data-stu-id="cf211-235">The following example shows how to use the `%=` operator to save the modulus of a quotient:</span></span>

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a><span data-ttu-id="cf211-236">递增和递减运算符</span><span class="sxs-lookup"><span data-stu-id="cf211-236">The increment and decrement operators</span></span>

<span data-ttu-id="cf211-237">递增运算符将 `++` 变量的值增加1。</span><span class="sxs-lookup"><span data-stu-id="cf211-237">The increment operator `++` increases the value of a variable by 1.</span></span> <span data-ttu-id="cf211-238">在简单语句中使用递增运算符时，不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="cf211-238">When you use the increment operator in a simple statement, no value is returned.</span></span> <span data-ttu-id="cf211-239">若要查看结果，请显示变量的值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-239">To view the result, display the value of the variable, as follows:</span></span>

```powershell
$a = 7
++$a
$a
```

```
8
```

<span data-ttu-id="cf211-240">若要强制返回值，请将变量和运算符括在括号中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-240">To force a value to be returned, enclose the variable and the operator in parentheses, as follows:</span></span>

```powershell
$a = 7
(++$a)
```

```
8
```

<span data-ttu-id="cf211-241">递增运算符可以放置在 (前缀) 之前，也可以放在 (后缀) 变量之后。</span><span class="sxs-lookup"><span data-stu-id="cf211-241">The increment operator can be placed before (prefix) or after (postfix) a variable.</span></span> <span data-ttu-id="cf211-242">在语句中使用变量之前，该运算符的前缀版本会递增变量，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-242">The prefix version of the operator increments a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

<span data-ttu-id="cf211-243">在语句中使用变量值后，该运算符的后缀版本会递增该变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-243">The postfix version of the operator increments a variable after its value is used in the statement.</span></span> <span data-ttu-id="cf211-244">在下面的示例中， `$c` 和 `$a` 变量具有不同的值，因为在进行更改之前将值分配给 `$c` `$a` ：</span><span class="sxs-lookup"><span data-stu-id="cf211-244">In the following example, the `$c` and `$a` variables have different values because the value is assigned to `$c` before `$a` changes:</span></span>

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

<span data-ttu-id="cf211-245">减量运算符将 `--` 变量的值减少1。</span><span class="sxs-lookup"><span data-stu-id="cf211-245">The decrement operator `--` decreases the value of a variable by 1.</span></span> <span data-ttu-id="cf211-246">与递增运算符一样，在简单语句中使用运算符时不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="cf211-246">As with the increment operator, no value is returned when you use the operator in a simple statement.</span></span> <span data-ttu-id="cf211-247">使用括号返回值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-247">Use parentheses to return a value, as follows:</span></span>

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

<span data-ttu-id="cf211-248">在语句中使用变量之前，该运算符的前缀版本会递减变量，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-248">The prefix version of the operator decrements a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

<span data-ttu-id="cf211-249">在语句中使用变量值后，该运算符的后缀版本会递减变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-249">The postfix version of the operator decrements a variable after its value is used in the statement.</span></span> <span data-ttu-id="cf211-250">在下面的示例中， `$d` 和 `$a` 变量具有不同的值，因为在进行更改之前将值分配给 `$d` `$a` ：</span><span class="sxs-lookup"><span data-stu-id="cf211-250">In the following example, the `$d` and `$a` variables have different values because the value is assigned to `$d` before `$a` changes:</span></span>

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a><span data-ttu-id="cf211-251">Microsoft .NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="cf211-251">Microsoft .NET Framework types</span></span>

<span data-ttu-id="cf211-252">默认情况下，当变量只有一个值时，赋给变量的值将确定该变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-252">By default, when a variable has only one value, the value that is assigned to the variable determines the data type of the variable.</span></span> <span data-ttu-id="cf211-253">例如，以下命令将创建一个具有 "Integer" () 类型的变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-253">For example, the following command creates a variable that has the "Integer" (System.Int32) type:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="cf211-254">若要查找变量的 .NET Framework 类型，请使用 **GetType** 方法及其 **FullName** 属性，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cf211-254">To find the .NET Framework type of a variable, use the **GetType** method and its **FullName** property, as follows.</span></span> <span data-ttu-id="cf211-255">请确保在 **GetType** 方法名称后面加上括号，即使方法调用没有参数：</span><span class="sxs-lookup"><span data-stu-id="cf211-255">Be sure to include the parentheses after the **GetType** method name, even though the method call has no arguments:</span></span>

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

<span data-ttu-id="cf211-256">若要创建包含字符串的变量，请为该变量分配一个字符串值。</span><span class="sxs-lookup"><span data-stu-id="cf211-256">To create a variable that contains a string, assign a string value to the variable.</span></span> <span data-ttu-id="cf211-257">若要指示值为字符串，请将其括在引号中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-257">To indicate that the value is a string, enclose it in quotation marks, as follows:</span></span>

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

<span data-ttu-id="cf211-258">如果分配给变量的第一个值为字符串，则 PowerShell 会将所有操作视为字符串操作，并将新值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="cf211-258">If the first value that is assigned to the variable is a string, PowerShell treats all operations as string operations and casts new values to strings.</span></span>
<span data-ttu-id="cf211-259">在以下示例中，会发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="cf211-259">This occurs in the following example:</span></span>

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

<span data-ttu-id="cf211-260">如果第一个值是整数，则 PowerShell 会将所有操作视为整数操作，并将新值转换为整数。</span><span class="sxs-lookup"><span data-stu-id="cf211-260">If the first value is an integer, PowerShell treats all operations as integer operations and casts new values to integers.</span></span> <span data-ttu-id="cf211-261">在以下示例中，会发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="cf211-261">This occurs in the following example:</span></span>

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

<span data-ttu-id="cf211-262">可以通过将类型名称放在变量名称或第一个赋值值之前的方括号中，将新的标量变量转换为任意 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-262">You can cast a new scalar variable as any .NET Framework type by placing the type name in brackets that precede either the variable name or the first assignment value.</span></span> <span data-ttu-id="cf211-263">转换变量时，可以确定变量中可以存储的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-263">When you cast a variable, you can determine the types of data that can be stored in the variable.</span></span> <span data-ttu-id="cf211-264">而且，您可以在操作变量时确定变量的行为方式。</span><span class="sxs-lookup"><span data-stu-id="cf211-264">And, you can determine how the variable behaves when you manipulate it.</span></span>

<span data-ttu-id="cf211-265">例如，以下命令将变量强制转换为字符串类型：</span><span class="sxs-lookup"><span data-stu-id="cf211-265">For example, the following command casts the variable as a string type:</span></span>

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

<span data-ttu-id="cf211-266">下面的示例将转换第一个值，而不是强制转换变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-266">The following example casts the first value, instead of casting the variable:</span></span>

```powershell
$a = [string]27
```

<span data-ttu-id="cf211-267">将变量强制转换为特定类型时，常见的约定是强制转换变量，而不是转换值。</span><span class="sxs-lookup"><span data-stu-id="cf211-267">When you cast a variable to a specific type, the common convention is to cast the variable, not the value.</span></span> <span data-ttu-id="cf211-268">但是，如果不能将现有变量的值转换为新的数据类型，则不能重塑该变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-268">However, you cannot recast the data type of an existing variable if its value cannot be converted to the new data type.</span></span> <span data-ttu-id="cf211-269">若要更改数据类型，必须替换其值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-269">To change the data type, you must replace its value, as follows:</span></span>

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

<span data-ttu-id="cf211-270">此外，在使用数据类型的变量名称前面之前，该变量的类型将被锁定，除非通过指定另一种数据类型显式重写该类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-270">In addition, when you precede a variable name with a data type, the type of that variable is locked unless you explicitly override the type by specifying another data type.</span></span> <span data-ttu-id="cf211-271">如果尝试分配的值与现有的类型不兼容，并且不显式重写该类型，则 PowerShell 会显示错误，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-271">If you try to assign a value that is incompatible with the existing type, and you do not explicitly override the type, PowerShell displays an error, as shown in the following example:</span></span>

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

<span data-ttu-id="cf211-272">在 PowerShell 中，在数组中包含多个项的变量的数据类型的处理方式与包含单个项的变量的数据类型不同。</span><span class="sxs-lookup"><span data-stu-id="cf211-272">In PowerShell, the data types of variables that contain multiple items in an array are handled differently from the data types of variables that contain a single item.</span></span> <span data-ttu-id="cf211-273">除非将数据类型专门赋给数组变量，否则数据类型始终为 `System.Object []` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-273">Unless a data type is specifically assigned to an array variable, the data type is always `System.Object []`.</span></span> <span data-ttu-id="cf211-274">此数据类型特定于数组。</span><span class="sxs-lookup"><span data-stu-id="cf211-274">This data type is specific to arrays.</span></span>

<span data-ttu-id="cf211-275">有时，可以通过指定其他类型来重写默认类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-275">Sometimes, you can override the default type by specifying another type.</span></span> <span data-ttu-id="cf211-276">例如，以下命令将变量强制转换为 `string []` 数组类型：</span><span class="sxs-lookup"><span data-stu-id="cf211-276">For example, the following command casts the variable as a `string []` array type:</span></span>

```powershell
[string []] $a = "one", "two", "three"
```

<span data-ttu-id="cf211-277">PowerShell 变量可以是任何 .NET Framework 数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-277">PowerShell variables can be any .NET Framework data type.</span></span> <span data-ttu-id="cf211-278">此外，您可以分配在当前过程中可用的任何完全限定的 .NET Framework 数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf211-278">In addition, you can assign any fully qualified .NET Framework data type that is available in the current process.</span></span> <span data-ttu-id="cf211-279">例如，以下命令指定了 `System.DateTime` 数据类型：</span><span class="sxs-lookup"><span data-stu-id="cf211-279">For example, the following command specifies a `System.DateTime` data type:</span></span>

```powershell
[System.DateTime]$a = "5/31/2005"
```

<span data-ttu-id="cf211-280">将为该变量分配一个符合数据类型的值 `System.DateTime` 。</span><span class="sxs-lookup"><span data-stu-id="cf211-280">The variable will be assigned a value that conforms to the `System.DateTime` data type.</span></span> <span data-ttu-id="cf211-281">变量的值将 `$a` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf211-281">The value of the `$a` variable would be the following:</span></span>

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a><span data-ttu-id="cf211-282">分配多个变量</span><span class="sxs-lookup"><span data-stu-id="cf211-282">Assigning multiple variables</span></span>

<span data-ttu-id="cf211-283">在 PowerShell 中，可以使用单个命令将值分配给多个变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-283">In PowerShell, you can assign values to multiple variables by using a single command.</span></span> <span data-ttu-id="cf211-284">赋值值的第一个元素分配给第一个变量，第二个元素分配给第二个变量，第三个元素分配给第三个变量，依此类推。</span><span class="sxs-lookup"><span data-stu-id="cf211-284">The first element of the assignment value is assigned to the first variable, the second element is assigned to the second variable, the third element to the third variable, and so on.</span></span> <span data-ttu-id="cf211-285">例如，以下命令将值1赋给 `$a` 变量，将值2赋给变量，将值3赋给 `$b` `$c` 变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-285">For example, the following command assigns the value 1 to the `$a` variable, the value 2 to the `$b` variable, and the value 3 to the `$c` variable:</span></span>

```powershell
$a, $b, $c = 1, 2, 3
```

<span data-ttu-id="cf211-286">如果分配值包含的元素多于变量，则所有剩余的值都将分配给最后一个变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-286">If the assignment value contains more elements than variables, all the remaining values are assigned to the last variable.</span></span> <span data-ttu-id="cf211-287">例如，下面的命令包含三个变量和五个值：</span><span class="sxs-lookup"><span data-stu-id="cf211-287">For example, the following command contains three variables and five values:</span></span>

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

<span data-ttu-id="cf211-288">因此，PowerShell 将值1赋给 `$a` 变量，将值2赋给该 `$b` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-288">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="cf211-289">它将值3、4和5分配给 `$c` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-289">It assigns the values 3, 4, and 5 to the `$c` variable.</span></span>
<span data-ttu-id="cf211-290">若要将变量中的值分配 `$c` 给其他三个变量，请使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="cf211-290">To assign the values in the `$c` variable to three other variables, use the following format:</span></span>

```powershell
$d, $e, $f = $c
```

<span data-ttu-id="cf211-291">此命令将值3赋给 `$d` 变量，将值4赋给变量 `$e` ，将值5赋给该 `$f` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-291">This command assigns the value 3 to the `$d` variable, the value 4 to the `$e` variable, and the value 5 to the `$f` variable.</span></span>

<span data-ttu-id="cf211-292">如果赋值值所包含的元素少于变量，则不会为末尾的所有剩余变量分配任何值。</span><span class="sxs-lookup"><span data-stu-id="cf211-292">If the assignment value contains less elements than variables, all the remaining variables at the end are not assigned any values.</span></span> <span data-ttu-id="cf211-293">例如，下面的命令包含三个变量和两个值：</span><span class="sxs-lookup"><span data-stu-id="cf211-293">For example, the following command contains three variables and two values:</span></span>

```powershell
$a, $b, $c = 1, 2
```

<span data-ttu-id="cf211-294">因此，PowerShell 将值1赋给 `$a` 变量，将值2赋给该 `$b` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-294">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="cf211-295">它不会将任何值分配给 `$c` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-295">It will not assign any value to the `$c` variable.</span></span>

<span data-ttu-id="cf211-296">还可以通过链接变量将单个值分配给多个变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-296">You can also assign a single value to multiple variables by chaining the variables.</span></span> <span data-ttu-id="cf211-297">例如，以下命令将值 "3" 赋给所有四个变量：</span><span class="sxs-lookup"><span data-stu-id="cf211-297">For example, the following command assigns a value of "three" to all four variables:</span></span>

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a><span data-ttu-id="cf211-298">与变量相关的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf211-298">Variable-related cmdlets</span></span>

<span data-ttu-id="cf211-299">除了使用赋值运算设置变量值以外，还可以使用 " [变量集](xref:Microsoft.PowerShell.Utility.Set-Variable) " cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf211-299">In addition to using an assignment operation to set a variable value, you can also use the [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) cmdlet.</span></span> <span data-ttu-id="cf211-300">例如，下面的命令使用将 `Set-Variable` 1，2，3的数组分配给 `$a` 变量。</span><span class="sxs-lookup"><span data-stu-id="cf211-300">For example, the following command uses `Set-Variable` to assign an array of 1, 2, 3 to the `$a` variable.</span></span>

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a><span data-ttu-id="cf211-301">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf211-301">See also</span></span>

[<span data-ttu-id="cf211-302">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="cf211-302">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="cf211-303">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="cf211-303">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="cf211-304">about_Variables</span><span class="sxs-lookup"><span data-stu-id="cf211-304">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="cf211-305">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="cf211-305">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[<span data-ttu-id="cf211-306">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="cf211-306">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[<span data-ttu-id="cf211-307">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="cf211-307">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
