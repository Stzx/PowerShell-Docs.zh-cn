---
description: 介绍数组，数组是设计用于存储项集合的数据结构。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 96e3798d4ff0a737421bb6211b809b192afa96f0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200168"
---
# <a name="about-arrays"></a><span data-ttu-id="ebee0-104">关于数组</span><span class="sxs-lookup"><span data-stu-id="ebee0-104">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="ebee0-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ebee0-105">Short Description</span></span>
<span data-ttu-id="ebee0-106">介绍数组，数组是设计用于存储项集合的数据结构。</span><span class="sxs-lookup"><span data-stu-id="ebee0-106">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="ebee0-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="ebee0-107">Long Description</span></span>

<span data-ttu-id="ebee0-108">数组是一种数据结构，用于存储项的集合。</span><span class="sxs-lookup"><span data-stu-id="ebee0-108">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="ebee0-109">项可以是同一类型，也可以是不同的类型。</span><span class="sxs-lookup"><span data-stu-id="ebee0-109">The items can be the same type or different types.</span></span>

<span data-ttu-id="ebee0-110">从 Windows PowerShell 3.0 开始，零个或一个对象的集合具有数组的某些属性。</span><span class="sxs-lookup"><span data-stu-id="ebee0-110">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="ebee0-111">创建和初始化数组</span><span class="sxs-lookup"><span data-stu-id="ebee0-111">Creating and initializing an array</span></span>

<span data-ttu-id="ebee0-112">若要创建并初始化数组，请将多个值分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="ebee0-112">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="ebee0-113">存储在数组中的值用逗号分隔，赋值运算符将其与变量名称隔开 (`=`) 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-113">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="ebee0-114">例如，若要创建一个名为 `$A` 的数组，该数组包含七个数值 (int) 值22、5、10、8、12、9和80，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-114">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="ebee0-115">还可以通过将逗号置于单个项之前来初始化单个项数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-115">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="ebee0-116">例如，若要创建名为 `$B` 包含单值7的单个项数组，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-116">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="ebee0-117">还可以通过使用范围运算符 () 来创建和初始化数组 `..` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-117">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="ebee0-118">下面的示例创建一个包含值5到8的数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-118">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="ebee0-119">因此， `$C` 包含四个值：5、6、7和8。</span><span class="sxs-lookup"><span data-stu-id="ebee0-119">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="ebee0-120">如果未指定数据类型，则 PowerShell 会将每个数组作为对象数组创建 ( **system.object []** ) 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-120">When no data type is specified, PowerShell creates each array as an object array ( **System.Object[]** ).</span></span> <span data-ttu-id="ebee0-121">若要确定数组的数据类型，请使用 **GetType ( # B1** 方法。</span><span class="sxs-lookup"><span data-stu-id="ebee0-121">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="ebee0-122">例如，若要确定数组的数据类型 `$A` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-122">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="ebee0-123">若要创建强类型化数组（即，只可包含特定类型的值的数组），请将该变量强制转换为数组类型，如 **string []** 、 **long []** 或 **int32 []** 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-123">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]** , **long[]** , or **int32[]** .</span></span> <span data-ttu-id="ebee0-124">若要强制转换数组，请在变量名称之前加上括号内的数组类型。</span><span class="sxs-lookup"><span data-stu-id="ebee0-124">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="ebee0-125">例如，若要创建一个名为的32位整数数组，该数组 `$ia` 包含四个整数 (1500、2230、3350和 4000) ，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-125">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="ebee0-126">因此， `$ia` 数组只能包含整数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-126">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="ebee0-127">你可以创建在 Microsoft .NET 框架中强制转换为任何支持的类型的数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-127">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="ebee0-128">例如， `Get-Process` 检索以表示进程的对象属于 **system.object** 类型。</span><span class="sxs-lookup"><span data-stu-id="ebee0-128">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="ebee0-129">若要创建进程对象的强类型数组，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ebee0-129">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="ebee0-130">数组子表达式运算符</span><span class="sxs-lookup"><span data-stu-id="ebee0-130">The array sub-expression operator</span></span>

<span data-ttu-id="ebee0-131">"数组" 子表达式运算符从它内部的语句创建一个数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-131">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="ebee0-132">如果运算符中的语句生成，运算符会将其放在数组中。</span><span class="sxs-lookup"><span data-stu-id="ebee0-132">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="ebee0-133">即使有零个或一个对象。</span><span class="sxs-lookup"><span data-stu-id="ebee0-133">Even if there is zero or one object.</span></span>

<span data-ttu-id="ebee0-134">数组运算符的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="ebee0-134">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="ebee0-135">可以使用 array 运算符创建零个或一个对象的数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-135">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="ebee0-136">例如：</span><span class="sxs-lookup"><span data-stu-id="ebee0-136">For example:</span></span>

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

<span data-ttu-id="ebee0-137">当您获取对象时，array 运算符非常有用，但不知道您获取了多少个对象。</span><span class="sxs-lookup"><span data-stu-id="ebee0-137">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="ebee0-138">例如：</span><span class="sxs-lookup"><span data-stu-id="ebee0-138">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="ebee0-139">有关数组子表达式运算符的详细信息，请参阅 [about_Operators](about_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="ebee0-139">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="ebee0-140">访问和使用数组元素</span><span class="sxs-lookup"><span data-stu-id="ebee0-140">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="ebee0-141">读取数组</span><span class="sxs-lookup"><span data-stu-id="ebee0-141">Reading an array</span></span>

<span data-ttu-id="ebee0-142">可以通过使用数组的变量名称来引用它。</span><span class="sxs-lookup"><span data-stu-id="ebee0-142">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="ebee0-143">若要显示数组中的所有元素，请键入数组名称。</span><span class="sxs-lookup"><span data-stu-id="ebee0-143">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="ebee0-144">例如，假设 `$a` 是包含整数0、1、2和9的数组，则键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-144">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="ebee0-145">从位置0开始，可以使用索引引用数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="ebee0-145">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="ebee0-146">将索引号括在括号中。</span><span class="sxs-lookup"><span data-stu-id="ebee0-146">Enclose the index number in brackets.</span></span> <span data-ttu-id="ebee0-147">例如，若要显示数组中的第一个元素 `$a` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-147">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="ebee0-148">若要显示数组中的第三个元素 `$a` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-148">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="ebee0-149">您可以使用索引的范围运算符来检索部分数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-149">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="ebee0-150">例如，若要检索数组的第二到第五个元素，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-150">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="ebee0-151">负数从数组末尾开始计数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-151">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="ebee0-152">例如，"-1" 指数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="ebee0-152">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="ebee0-153">若要显示数组的最后三个元素，请在 "索引升序" 中键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-153">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="ebee0-154">如果按降序键入负索引，则输出会发生变化。</span><span class="sxs-lookup"><span data-stu-id="ebee0-154">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="ebee0-155">但是，使用此表示法时要格外小心。</span><span class="sxs-lookup"><span data-stu-id="ebee0-155">However, be cautious when using this notation.</span></span> <span data-ttu-id="ebee0-156">表示法从结束边界到数组的开头。</span><span class="sxs-lookup"><span data-stu-id="ebee0-156">The notation cycles from the end boundary to the beginning of the array.</span></span>

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

<span data-ttu-id="ebee0-157">此外，一个常见错误是 `$a[0..-2]` 指引用数组的所有元素（最后一个元素除外）。</span><span class="sxs-lookup"><span data-stu-id="ebee0-157">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="ebee0-158">它引用数组中的第一个、最后一个和第二个元素。</span><span class="sxs-lookup"><span data-stu-id="ebee0-158">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="ebee0-159">您可以使用加号运算符 (`+`) 将范围与数组中的元素列表组合在一起。</span><span class="sxs-lookup"><span data-stu-id="ebee0-159">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="ebee0-160">例如，若要在索引位置0、2和4到6显示元素，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-160">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

<span data-ttu-id="ebee0-161">此外，若要列出多个范围和单个元素，可以使用加号运算符。</span><span class="sxs-lookup"><span data-stu-id="ebee0-161">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="ebee0-162">例如，若要列出元素0到2、4到6以及第8个位置的元素，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ebee0-162">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a><span data-ttu-id="ebee0-163">数组元素的迭代</span><span class="sxs-lookup"><span data-stu-id="ebee0-163">Iterations over array elements</span></span>

<span data-ttu-id="ebee0-164">你还可以使用循环构造，如 ForEach、For 和 While 循环，以引用数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="ebee0-164">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="ebee0-165">例如，若要使用 ForEach 循环显示数组中的元素 `$a` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-165">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="ebee0-166">Foreach 循环会循环访问数组并返回数组中的每个值，直到到达数组的末尾。</span><span class="sxs-lookup"><span data-stu-id="ebee0-166">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="ebee0-167">当您在检查数组中的元素时递增计数器时，For 循环非常有用。</span><span class="sxs-lookup"><span data-stu-id="ebee0-167">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="ebee0-168">例如，若要使用 For 循环来返回数组中的每个其他值，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-168">For example, to use a For loop to return every other value in an array, type:</span></span>

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

<span data-ttu-id="ebee0-169">您可以使用 While 循环来显示数组中的元素，直至定义的条件不再为 true 为止。</span><span class="sxs-lookup"><span data-stu-id="ebee0-169">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="ebee0-170">例如，若要在 `$a` 数组索引小于4的情况下显示数组中的元素，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-170">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a><span data-ttu-id="ebee0-171">数组属性</span><span class="sxs-lookup"><span data-stu-id="ebee0-171">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="ebee0-172">Count 或 Length 或 LongLength</span><span class="sxs-lookup"><span data-stu-id="ebee0-172">Count or Length or LongLength</span></span>

<span data-ttu-id="ebee0-173">若要确定数组中有多少项，请使用 `Length` 属性或其 `Count` 别名。</span><span class="sxs-lookup"><span data-stu-id="ebee0-173">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="ebee0-174">`Longlength` 如果数组包含的元素超过2147483647，则会很有用。</span><span class="sxs-lookup"><span data-stu-id="ebee0-174">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="ebee0-175">级别</span><span class="sxs-lookup"><span data-stu-id="ebee0-175">Rank</span></span>

<span data-ttu-id="ebee0-176">返回数组中的维数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-176">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="ebee0-177">PowerShell 中的大多数数组仅具有一个维度。</span><span class="sxs-lookup"><span data-stu-id="ebee0-177">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="ebee0-178">即使您认为要生成多维数组，类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="ebee0-178">Even when you think you are building a multidimensional array; like the following example:</span></span>

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

<span data-ttu-id="ebee0-179">下面的示例演示如何使用 .Net Framework 创建一个真正的多维数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-179">The following example shows how to create a truly multidimensional array using the .Net Framework.</span></span>

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a><span data-ttu-id="ebee0-180">数组方法</span><span class="sxs-lookup"><span data-stu-id="ebee0-180">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="ebee0-181">清除</span><span class="sxs-lookup"><span data-stu-id="ebee0-181">Clear</span></span>

<span data-ttu-id="ebee0-182">将所有元素值设置为数组元素类型的 _默认值_ 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-182">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="ebee0-183">Clear ( # A1 方法不会重置数组的大小。</span><span class="sxs-lookup"><span data-stu-id="ebee0-183">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="ebee0-184">在下面的示例中 `$a` ，是一个对象数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-184">In the following example `$a` is an array of objects.</span></span>

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

<span data-ttu-id="ebee0-185">在此示例中， `$intA` 显式键入以包含整数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-185">In this example, `$intA` is explicitly typed to contain integers.</span></span>

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a><span data-ttu-id="ebee0-186">ForEach</span><span class="sxs-lookup"><span data-stu-id="ebee0-186">ForEach</span></span>

<span data-ttu-id="ebee0-187">允许遍历数组中的所有元素，并为数组的每个元素执行给定操作。</span><span class="sxs-lookup"><span data-stu-id="ebee0-187">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="ebee0-188">ForEach 方法具有多个执行不同操作的重载。</span><span class="sxs-lookup"><span data-stu-id="ebee0-188">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="ebee0-189">ForEach (scriptblock 表达式) </span><span class="sxs-lookup"><span data-stu-id="ebee0-189">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="ebee0-190">ForEach (scriptblock 表达式，object [] 参数) </span><span class="sxs-lookup"><span data-stu-id="ebee0-190">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="ebee0-191">此方法是在 PowerShell v4 中添加的。</span><span class="sxs-lookup"><span data-stu-id="ebee0-191">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="ebee0-192">语法要求使用脚本块。</span><span class="sxs-lookup"><span data-stu-id="ebee0-192">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="ebee0-193">如果 scriptblock 是唯一的参数，则括号是可选的。</span><span class="sxs-lookup"><span data-stu-id="ebee0-193">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="ebee0-194">此外，在方法和左括号或大括号之间不得有空格。</span><span class="sxs-lookup"><span data-stu-id="ebee0-194">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="ebee0-195">下面的示例演示如何使用 foreach 方法。</span><span class="sxs-lookup"><span data-stu-id="ebee0-195">The following example shows how use the foreach method.</span></span> <span data-ttu-id="ebee0-196">在此示例中，目的是生成数组中元素的平方值。</span><span class="sxs-lookup"><span data-stu-id="ebee0-196">In this case the intent is to generate the square value of the elements in the array.</span></span>

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

<span data-ttu-id="ebee0-197">与的 `-ArgumentList` 参数一样 `ForEach-Object` ， `arguments` 参数允许将参数数组传递到配置为接受它们的脚本块。</span><span class="sxs-lookup"><span data-stu-id="ebee0-197">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="ebee0-198">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="ebee0-198">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="ebee0-199">ForEach (类型 convertToType) </span><span class="sxs-lookup"><span data-stu-id="ebee0-199">ForEach(type convertToType)</span></span>

<span data-ttu-id="ebee0-200">`ForEach`方法可用于快速将元素强制转换为另一种类型; 下面的示例演示如何将字符串日期的列表转换为 `[DateTime]` 类型。</span><span class="sxs-lookup"><span data-stu-id="ebee0-200">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="ebee0-201">ForEach (string propertyName) </span><span class="sxs-lookup"><span data-stu-id="ebee0-201">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="ebee0-202">ForEach (string propertyName，object [] newValue) </span><span class="sxs-lookup"><span data-stu-id="ebee0-202">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="ebee0-203">`ForEach`方法还可用于快速检索或设置集合中每个项的属性值。</span><span class="sxs-lookup"><span data-stu-id="ebee0-203">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="ebee0-204">ForEach (字符串方法名称) </span><span class="sxs-lookup"><span data-stu-id="ebee0-204">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="ebee0-205">ForEach (string 方法，object [] 参数) </span><span class="sxs-lookup"><span data-stu-id="ebee0-205">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="ebee0-206">最后， `ForEach` 可使用方法对集合中的每个项执行方法。</span><span class="sxs-lookup"><span data-stu-id="ebee0-206">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="ebee0-207">与的 `-ArgumentList` 参数一样 `ForEach-Object` ， `arguments` 参数允许将参数数组传递到配置为接受它们的脚本块。</span><span class="sxs-lookup"><span data-stu-id="ebee0-207">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="ebee0-208">从 Windows PowerShell 3.0 中开始，还可以使用 "标量对象和集合的方法" 来完成为集合中的每个项检索属性和执行方法的操作，可以在此处 [about_methods](about_methods.md)获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebee0-208">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="ebee0-209">其中</span><span class="sxs-lookup"><span data-stu-id="ebee0-209">Where</span></span>

<span data-ttu-id="ebee0-210">允许筛选或选择数组的元素。</span><span class="sxs-lookup"><span data-stu-id="ebee0-210">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="ebee0-211">脚本的计算结果必须为：零 (0) ，空字符串，或要 `$false` 在 `$null``Where`</span><span class="sxs-lookup"><span data-stu-id="ebee0-211">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="ebee0-212">此方法有一个定义 `Where` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-212">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="ebee0-213">语法要求使用脚本块。</span><span class="sxs-lookup"><span data-stu-id="ebee0-213">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="ebee0-214">如果 scriptblock 是唯一的参数，则括号是可选的。</span><span class="sxs-lookup"><span data-stu-id="ebee0-214">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="ebee0-215">此外，在方法和左括号或大括号之间不得有空格。</span><span class="sxs-lookup"><span data-stu-id="ebee0-215">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="ebee0-216">`Expression`是筛选所需的 scriptblock， `mode` 可选参数允许其他选择功能， `numberToReturn` 可选参数允许限制从筛选器返回的项数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-216">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="ebee0-217">的可接受值为 `mode` ：</span><span class="sxs-lookup"><span data-stu-id="ebee0-217">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="ebee0-218">默认 (0) -返回所有项</span><span class="sxs-lookup"><span data-stu-id="ebee0-218">Default (0) - Return all items</span></span>
- <span data-ttu-id="ebee0-219">第一 (1) -返回第一项</span><span class="sxs-lookup"><span data-stu-id="ebee0-219">First (1) - Return the first item</span></span>
- <span data-ttu-id="ebee0-220">最后 (2) -返回最后一项</span><span class="sxs-lookup"><span data-stu-id="ebee0-220">Last (2) - Return the last item</span></span>
- <span data-ttu-id="ebee0-221">跳到 (3) -跳过项，直到 condition 为 true，返回剩余项</span><span class="sxs-lookup"><span data-stu-id="ebee0-221">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="ebee0-222">到 (4) 之前-返回所有项，直到 condition 为 true</span><span class="sxs-lookup"><span data-stu-id="ebee0-222">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="ebee0-223">拆分 (5) -返回两个元素组成的数组</span><span class="sxs-lookup"><span data-stu-id="ebee0-223">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="ebee0-224">第一个元素包含匹配项</span><span class="sxs-lookup"><span data-stu-id="ebee0-224">The first element contains matching items</span></span>
  - <span data-ttu-id="ebee0-225">第二个元素包含剩余项</span><span class="sxs-lookup"><span data-stu-id="ebee0-225">The second element contains the remaining items</span></span>

<span data-ttu-id="ebee0-226">下面的示例演示如何从数组中选择所有奇数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-226">The following example shows how to select all odd numbers from the array.</span></span>

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

<span data-ttu-id="ebee0-227">此示例演示如何选择不为空的字符串。</span><span class="sxs-lookup"><span data-stu-id="ebee0-227">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="ebee0-228">默认</span><span class="sxs-lookup"><span data-stu-id="ebee0-228">Default</span></span>

<span data-ttu-id="ebee0-229">`Default`模式使用 scriptblock 筛选项 `Expression` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-229">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="ebee0-230">如果 `numberToReturn` 提供了，则它指定要返回的最大项数。</span><span class="sxs-lookup"><span data-stu-id="ebee0-230">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="ebee0-231">`Default`模式和模式都 `First` 返回第一个 (`numberToReturn`) 项，可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="ebee0-231">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="ebee0-232">上一个</span><span class="sxs-lookup"><span data-stu-id="ebee0-232">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="ebee0-233">跳到</span><span class="sxs-lookup"><span data-stu-id="ebee0-233">SkipUntil</span></span>

<span data-ttu-id="ebee0-234">`SkipUntil`模式将跳过集合中的所有对象，直到对象传递脚本块表达式筛选器。</span><span class="sxs-lookup"><span data-stu-id="ebee0-234">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="ebee0-235">然后，它将返回 **所有** 剩余的集合项而不测试它们。</span><span class="sxs-lookup"><span data-stu-id="ebee0-235">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="ebee0-236">_仅测试一个传递项_ 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-236">_Only one passing item is tested_ .</span></span>

<span data-ttu-id="ebee0-237">这意味着返回的集合包含未经过测试的 _传递_ 和 _非传递_ 项。</span><span class="sxs-lookup"><span data-stu-id="ebee0-237">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="ebee0-238">通过将值传递给参数，可以限制返回的项数 `numberToReturn` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-238">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="ebee0-239">Until</span><span class="sxs-lookup"><span data-stu-id="ebee0-239">Until</span></span>

<span data-ttu-id="ebee0-240">`Until`模式反转 `SkipUntil` 模式。</span><span class="sxs-lookup"><span data-stu-id="ebee0-240">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="ebee0-241">它将返回集合中的 **所有** 项，直到某个项通过脚本块表达式。</span><span class="sxs-lookup"><span data-stu-id="ebee0-241">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="ebee0-242">在项 _传递_ scriptblock 表达式后，该 `Where` 方法将停止处理项。</span><span class="sxs-lookup"><span data-stu-id="ebee0-242">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="ebee0-243">这意味着从方法接收第一组 _非传递_ 项 `Where` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-243">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="ebee0-244">一项通过 _后_ ，就不会测试或返回其余的项。</span><span class="sxs-lookup"><span data-stu-id="ebee0-244">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="ebee0-245">通过将值传递给参数，可以限制返回的项数 `numberToReturn` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-245">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> <span data-ttu-id="ebee0-246">`Until`和 `SkipUntil` 在不测试一批项目的前提下运行。</span><span class="sxs-lookup"><span data-stu-id="ebee0-246">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="ebee0-247">`Until`返回第一个 _阶段_**之前** 的项。</span><span class="sxs-lookup"><span data-stu-id="ebee0-247">`Until` returns the items **BEFORE** the first _pass_ .</span></span>
>
> <span data-ttu-id="ebee0-248">`SkipUntil`返回第一次 _传递_**后** 的所有项，包括第一次传递项。</span><span class="sxs-lookup"><span data-stu-id="ebee0-248">`SkipUntil` returns all the items **AFTER** the first _pass_ , including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="ebee0-249">拆分</span><span class="sxs-lookup"><span data-stu-id="ebee0-249">Split</span></span>

<span data-ttu-id="ebee0-250">`Split`模式将集合项拆分为两个单独的集合。</span><span class="sxs-lookup"><span data-stu-id="ebee0-250">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="ebee0-251">传递 scriptblock 表达式的和不是的那些表达式。</span><span class="sxs-lookup"><span data-stu-id="ebee0-251">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="ebee0-252">如果 `numberToReturn` 指定了，则第一个集合包含 _传递_ 项，而不是超过指定的值。</span><span class="sxs-lookup"><span data-stu-id="ebee0-252">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="ebee0-253">其余的对象（甚至是那些 **传递** 表达式筛选器的对象）在第二个集合中返回。</span><span class="sxs-lookup"><span data-stu-id="ebee0-253">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="ebee0-254">获取数组的成员</span><span class="sxs-lookup"><span data-stu-id="ebee0-254">Get the members of an array</span></span>

<span data-ttu-id="ebee0-255">若要获取数组的属性和方法（如 Length 属性和 **SetValue** 方法），请使用 Cmdlet 的 **InputObject** 参数 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-255">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="ebee0-256">将数组传递给时 `Get-Member` ，PowerShell 将一次发送一个项并 `Get-Member` 返回数组中每个项的类型 (忽略重复项) 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-256">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="ebee0-257">当使用 **InputObject** 参数时，将 `Get-Member` 返回数组的成员。</span><span class="sxs-lookup"><span data-stu-id="ebee0-257">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="ebee0-258">例如，以下命令将获取 `$a` 数组变量的成员。</span><span class="sxs-lookup"><span data-stu-id="ebee0-258">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="ebee0-259">还可以通过在将管道传递给 cmdlet 的值之前键入逗号 )  ( 来获取数组的成员 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-259">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="ebee0-260">逗号使数组成为数组的数组中的第二项。</span><span class="sxs-lookup"><span data-stu-id="ebee0-260">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="ebee0-261">PowerShell 将每次一个数组传递到数组，并 `Get-Member` 返回数组的成员。</span><span class="sxs-lookup"><span data-stu-id="ebee0-261">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="ebee0-262">类似于接下来的两个示例。</span><span class="sxs-lookup"><span data-stu-id="ebee0-262">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="ebee0-263">操作数组</span><span class="sxs-lookup"><span data-stu-id="ebee0-263">Manipulating an array</span></span>

<span data-ttu-id="ebee0-264">您可以更改数组中的元素，将元素添加到数组，并将两个数组中的值合并为第三个数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-264">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="ebee0-265">若要更改数组中特定元素的值，请指定要更改的元素的数组名称和索引，然后使用赋值运算符 (`=`) 为该元素指定一个新值。</span><span class="sxs-lookup"><span data-stu-id="ebee0-265">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="ebee0-266">例如，若要更改数组中第二项的值 `$a` (索引位置 1) 为10，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-266">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="ebee0-267">还可以使用数组的 **SetValue** 方法来更改值。</span><span class="sxs-lookup"><span data-stu-id="ebee0-267">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="ebee0-268">下面的示例将数组的第二个值 (索引位置 1) 更改 `$a` 为500：</span><span class="sxs-lookup"><span data-stu-id="ebee0-268">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="ebee0-269">可以使用 `+=` 运算符将元素添加到数组中。</span><span class="sxs-lookup"><span data-stu-id="ebee0-269">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="ebee0-270">下面的示例演示如何将元素添加到 `$a` 数组中。</span><span class="sxs-lookup"><span data-stu-id="ebee0-270">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="ebee0-271">使用 `+=` 运算符时，PowerShell 实际上会创建一个新数组，其中包含原始数组的值和所添加的值。</span><span class="sxs-lookup"><span data-stu-id="ebee0-271">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="ebee0-272">如果多次重复操作或数组大小太大，则这可能会导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="ebee0-272">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="ebee0-273">从数组中删除元素并不容易，但你可以创建一个新的数组，其中仅包含现有数组的选定元素。</span><span class="sxs-lookup"><span data-stu-id="ebee0-273">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="ebee0-274">例如，若要创建数组 `$t` ，其中包含 `$a` 数组中除索引位置2处的值之外的所有元素，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebee0-274">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="ebee0-275">若要将两个数组合并成单个数组，请使用加运算符 (`+`) 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-275">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="ebee0-276">下面的示例创建两个数组，并将它们组合在一起，然后显示生成的合并数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-276">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="ebee0-277">因此，该 `$z` 数组包含1、3、5和9。</span><span class="sxs-lookup"><span data-stu-id="ebee0-277">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="ebee0-278">若要删除数组，请将值分配 `$null` 给数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-278">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="ebee0-279">以下命令删除变量中的数组 `$a` 。</span><span class="sxs-lookup"><span data-stu-id="ebee0-279">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="ebee0-280">你还可以使用 `Remove-Item` cmdlet，但赋予的值 `$null` 更快，尤其是对于大型数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-280">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="ebee0-281">零或一的数组</span><span class="sxs-lookup"><span data-stu-id="ebee0-281">Arrays of zero or one</span></span>

<span data-ttu-id="ebee0-282">从 Windows PowerShell 3.0 开始，零个或一个对象的集合具有 Count 和 Length 属性。</span><span class="sxs-lookup"><span data-stu-id="ebee0-282">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="ebee0-283">此外，还可以为一个对象的数组编制索引。</span><span class="sxs-lookup"><span data-stu-id="ebee0-283">Also, you can index into an array of one object.</span></span> <span data-ttu-id="ebee0-284">此功能可帮助您避免在需要集合的命令获取的项少于两个项时出现脚本错误。</span><span class="sxs-lookup"><span data-stu-id="ebee0-284">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="ebee0-285">下面的示例演示了此功能。</span><span class="sxs-lookup"><span data-stu-id="ebee0-285">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="ebee0-286">零个对象</span><span class="sxs-lookup"><span data-stu-id="ebee0-286">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="ebee0-287">一个对象</span><span class="sxs-lookup"><span data-stu-id="ebee0-287">One object</span></span>

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a><span data-ttu-id="ebee0-288">对 System.object 对象的索引支持</span><span class="sxs-lookup"><span data-stu-id="ebee0-288">Indexing support for System.Tuple objects</span></span>

<span data-ttu-id="ebee0-289">PowerShell 6.1 添加了对 **元组** 对象的索引访问的支持，类似于数组。</span><span class="sxs-lookup"><span data-stu-id="ebee0-289">PowerShell 6.1 added the support for indexed access of **Tuple** objects, similar to arrays.</span></span>
<span data-ttu-id="ebee0-290">例如：</span><span class="sxs-lookup"><span data-stu-id="ebee0-290">For example:</span></span>

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

<span data-ttu-id="ebee0-291">与数组和其他集合对象不同，当通过管道或支持对象数组的参数传递元组对象时，会将 **元组** 对象视为单个对象。</span><span class="sxs-lookup"><span data-stu-id="ebee0-291">Unlike arrays and other collection objects, **Tuple** objects are treated as a single object when passed through the pipeline or by parameters that support arrays of objects.</span></span>

<span data-ttu-id="ebee0-292">有关详细信息，请参阅 [system.object](/dotnet/api/system.tuple)。</span><span class="sxs-lookup"><span data-stu-id="ebee0-292">For more information, see [System.Tuple](/dotnet/api/system.tuple).</span></span>

## <a name="see-also"></a><span data-ttu-id="ebee0-293">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebee0-293">See also</span></span>

- [<span data-ttu-id="ebee0-294">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="ebee0-294">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="ebee0-295">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="ebee0-295">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="ebee0-296">about_Operators</span><span class="sxs-lookup"><span data-stu-id="ebee0-296">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="ebee0-297">about_For</span><span class="sxs-lookup"><span data-stu-id="ebee0-297">about_For</span></span>](about_For.md)
- [<span data-ttu-id="ebee0-298">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="ebee0-298">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="ebee0-299">about_While</span><span class="sxs-lookup"><span data-stu-id="ebee0-299">about_While</span></span>](about_While.md)

