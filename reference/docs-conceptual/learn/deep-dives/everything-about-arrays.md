---
title: 关于数组的各项须知内容
description: 数组是大多数编程语言的一项基本语言功能。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 5cab354a99b122401f8f8119de24e075cf9d21f8
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149600"
---
# <a name="everything-you-wanted-to-know-about-arrays"></a><span data-ttu-id="856a3-103">关于数组的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="856a3-103">Everything you wanted to know about arrays</span></span>

<span data-ttu-id="856a3-104">[数组][]是大多数编程语言的一项基本语言功能。</span><span class="sxs-lookup"><span data-stu-id="856a3-104">[Arrays][] are a fundamental language feature of most programming languages.</span></span> <span data-ttu-id="856a3-105">它们是值或对象的集合，在编程中难免会用到。</span><span class="sxs-lookup"><span data-stu-id="856a3-105">They're a collection of values or objects that are difficult to avoid.</span></span> <span data-ttu-id="856a3-106">让我们来深入了解一下数组以及它们提供的一切。</span><span class="sxs-lookup"><span data-stu-id="856a3-106">Let's take a close look at arrays and everything they have to offer.</span></span>

> [!NOTE]
> <span data-ttu-id="856a3-107">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="856a3-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="856a3-108">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="856a3-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="856a3-109">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="856a3-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="856a3-110">什么是数组？</span><span class="sxs-lookup"><span data-stu-id="856a3-110">What is an array?</span></span>

<span data-ttu-id="856a3-111">在介绍 PowerShell 使用数组的其他方式之前，我将首先介绍数组的基本技术描述，以及大多数编程语言使用数组的方式。</span><span class="sxs-lookup"><span data-stu-id="856a3-111">I'm going to start with a basic technical description of what arrays are and how they are used by most programming languages before I shift into the other ways PowerShell makes use of them.</span></span>

<span data-ttu-id="856a3-112">数组是一种作为多个项集合的数据结构。</span><span class="sxs-lookup"><span data-stu-id="856a3-112">An array is a data structure that serves as a collection of multiple items.</span></span> <span data-ttu-id="856a3-113">你可以循环访问数组或使用索引来访问单个项。</span><span class="sxs-lookup"><span data-stu-id="856a3-113">You can iterate over the array or access individual items using an index.</span></span> <span data-ttu-id="856a3-114">数组是作为一个连续的内存块创建的，其中每个值存储在相邻位置。</span><span class="sxs-lookup"><span data-stu-id="856a3-114">The array is created as a sequential chunk of memory where each value is stored right next to the other.</span></span>

<span data-ttu-id="856a3-115">接下来，我将逐一进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="856a3-115">I'll touch on each of those details as we go.</span></span>

## <a name="basic-usage"></a><span data-ttu-id="856a3-116">基本用法</span><span class="sxs-lookup"><span data-stu-id="856a3-116">Basic usage</span></span>

<span data-ttu-id="856a3-117">数组是 PowerShell 的一项基本功能，在 PowerShell 中使用时有一个简单的语法。</span><span class="sxs-lookup"><span data-stu-id="856a3-117">Because arrays are such a basic feature of PowerShell, there is a simple syntax for working with them in PowerShell.</span></span>

### <a name="create-an-array"></a><span data-ttu-id="856a3-118">创建数组</span><span class="sxs-lookup"><span data-stu-id="856a3-118">Create an array</span></span>

<span data-ttu-id="856a3-119">使用 `@()` 可创建空数组</span><span class="sxs-lookup"><span data-stu-id="856a3-119">An empty array can be created by using `@()`</span></span>

```powershell
PS> $data = @()
PS> $data.count
0
```

<span data-ttu-id="856a3-120">只需将值放在 `@()` 括号中，即可创建一个数组，并将其作为种子。</span><span class="sxs-lookup"><span data-stu-id="856a3-120">We can create an array and seed it with values just by placing them in the `@()` parentheses.</span></span>

```powershell
PS> $data = @('Zero','One','Two','Three')
PS> $data.count
4

PS> $data
Zero
One
Two
Three
```

<span data-ttu-id="856a3-121">此数组有 4 个项。</span><span class="sxs-lookup"><span data-stu-id="856a3-121">This array has 4 items.</span></span> <span data-ttu-id="856a3-122">当我们调用 `$data` 变量时，我们将看到项列表。</span><span class="sxs-lookup"><span data-stu-id="856a3-122">When we call the `$data` variable, we see the list of our items.</span></span> <span data-ttu-id="856a3-123">如果它是字符串数组，则每个字符串占一行。</span><span class="sxs-lookup"><span data-stu-id="856a3-123">If it's an array of strings, then we get one line per string.</span></span>

<span data-ttu-id="856a3-124">我们可以在多行上声明一个数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-124">We can declare an array on multiple lines.</span></span> <span data-ttu-id="856a3-125">在这种情况下，逗号是可选的，通常会省略。</span><span class="sxs-lookup"><span data-stu-id="856a3-125">The comma is optional in this case and generally left out.</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
```

<span data-ttu-id="856a3-126">我更喜欢像这样在多行上声明数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-126">I prefer to declare my arrays on multiple lines like that.</span></span> <span data-ttu-id="856a3-127">当你有多个项时，不仅可以更轻松地读取，还可以在使用源代码管理时更轻松地与以前的版本进行比较。</span><span class="sxs-lookup"><span data-stu-id="856a3-127">Not only does it get easier to read when you have multiple items, it also makes it easier to compare to previous versions when using source control.</span></span>

#### <a name="other-syntax"></a><span data-ttu-id="856a3-128">其他语法</span><span class="sxs-lookup"><span data-stu-id="856a3-128">Other syntax</span></span>

<span data-ttu-id="856a3-129">人们通常认为 `@()` 是用于创建数组的语法，但是以逗号分隔的列表在大多数时候都是有效的。</span><span class="sxs-lookup"><span data-stu-id="856a3-129">It's commonly understood that `@()` is the syntax for creating an array, but comma-separated lists work most of the time.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
```

#### <a name="write-output-to-create-arrays"></a><span data-ttu-id="856a3-130">使用 Write-Output 创建数组</span><span class="sxs-lookup"><span data-stu-id="856a3-130">Write-Output to create arrays</span></span>

<span data-ttu-id="856a3-131">有一个值得一提的小技巧是，你可以使用 `Write-Output` 在控制台中快速创建字符串。</span><span class="sxs-lookup"><span data-stu-id="856a3-131">One cool little trick worth mentioning is that you can use `Write-Output` to quickly create strings at the console.</span></span>

```powershell
$data = Write-Output Zero One Two Three
```

<span data-ttu-id="856a3-132">这很方便，因为当参数接受字符串时，无需在字符串两侧加上引号。</span><span class="sxs-lookup"><span data-stu-id="856a3-132">This is handy because you don't have to put quotes around the strings when the parameter accepts strings.</span></span> <span data-ttu-id="856a3-133">我决不会在脚本中这样做，但在控制台中是可以的。</span><span class="sxs-lookup"><span data-stu-id="856a3-133">I would never do this in a script but it's fair game in the console.</span></span>

### <a name="accessing-items"></a><span data-ttu-id="856a3-134">访问项</span><span class="sxs-lookup"><span data-stu-id="856a3-134">Accessing items</span></span>

<span data-ttu-id="856a3-135">现在，你有了一个包含项的数组，你可能想要访问和更新这些项。</span><span class="sxs-lookup"><span data-stu-id="856a3-135">Now that you have an array with items in it, you may want to access and update those items.</span></span>

#### <a name="offset"></a><span data-ttu-id="856a3-136">Offset</span><span class="sxs-lookup"><span data-stu-id="856a3-136">Offset</span></span>

<span data-ttu-id="856a3-137">若要访问各项，可使用方括号 `[]`，且偏移值从 0 开始。</span><span class="sxs-lookup"><span data-stu-id="856a3-137">To access individual items, we use the brackets `[]` with an offset value starting at 0.</span></span> <span data-ttu-id="856a3-138">以下是我们获取数组中第一项的方式：</span><span class="sxs-lookup"><span data-stu-id="856a3-138">This is how we get the first item in our array:</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data[0]
Zero
```

<span data-ttu-id="856a3-139">此处使用零的原因是，第一项位于列表的开头，因此我们使用 0 个项的偏移量来获取它。</span><span class="sxs-lookup"><span data-stu-id="856a3-139">The reason why we use zero here is because the first item is at the beginning of the list so we use an offset of 0 items to get to it.</span></span> <span data-ttu-id="856a3-140">若要访问第二项，需要使用偏移量 1 来跳过第一项。</span><span class="sxs-lookup"><span data-stu-id="856a3-140">To get to the second item, we would need to use an offset of 1 to skip the first item.</span></span>

```powershell
PS> $data[1]
One
```

<span data-ttu-id="856a3-141">这意味着最后一项的偏移量为 3。</span><span class="sxs-lookup"><span data-stu-id="856a3-141">This would mean that the last item is at offset 3.</span></span>

```powershell
PS> $data[3]
Three
```

#### <a name="index"></a><span data-ttu-id="856a3-142">索引</span><span class="sxs-lookup"><span data-stu-id="856a3-142">Index</span></span>

<span data-ttu-id="856a3-143">现在，你可以看到我在此示例中选取这些值的原因。</span><span class="sxs-lookup"><span data-stu-id="856a3-143">Now you can see why I picked the values that I did for this example.</span></span> <span data-ttu-id="856a3-144">我把它当作一个偏移量来介绍，因为它确实是，但这个偏移量通常被称为索引。</span><span class="sxs-lookup"><span data-stu-id="856a3-144">I introduced this as an offset because that is what it really is, but this offset is more commonly referred to as an index.</span></span> <span data-ttu-id="856a3-145">从 `0` 开始的索引。</span><span class="sxs-lookup"><span data-stu-id="856a3-145">An index that starts at `0`.</span></span> <span data-ttu-id="856a3-146">在本文的其余部分，我会把偏移称为索引。</span><span class="sxs-lookup"><span data-stu-id="856a3-146">For the rest of this article I will call the offset an index.</span></span>

#### <a name="special-index-tricks"></a><span data-ttu-id="856a3-147">特殊索引技巧</span><span class="sxs-lookup"><span data-stu-id="856a3-147">Special index tricks</span></span>

<span data-ttu-id="856a3-148">在大多数语言中，只能将单个数字指定为索引，然后返回单个项。</span><span class="sxs-lookup"><span data-stu-id="856a3-148">In most languages, you can only specify a single number as the index and you get a single item back.</span></span>
<span data-ttu-id="856a3-149">PowerShell 则更加灵活。</span><span class="sxs-lookup"><span data-stu-id="856a3-149">PowerShell is much more flexible.</span></span> <span data-ttu-id="856a3-150">你可以一次使用多个索引。</span><span class="sxs-lookup"><span data-stu-id="856a3-150">You can use multiple indexes at once.</span></span> <span data-ttu-id="856a3-151">通过提供一系列索引，我们可以选择多个项。</span><span class="sxs-lookup"><span data-stu-id="856a3-151">By providing a list of indexes, we can select several items.</span></span>

```powershell
PS> $data[0,2,3]
Zero
Two
Three
```

<span data-ttu-id="856a3-152">根据提供的索引顺序会返回项。</span><span class="sxs-lookup"><span data-stu-id="856a3-152">The items are returned based on the order of the indexes provided.</span></span> <span data-ttu-id="856a3-153">如果复制某个索引，则会两次获得该项。</span><span class="sxs-lookup"><span data-stu-id="856a3-153">If you duplicate an index, you get that item both times.</span></span>

```powershell
PS> $data[3,0,3]
Three
Zero
Three
```

<span data-ttu-id="856a3-154">可以使用内置 `..` 运算符来指定数字序列，</span><span class="sxs-lookup"><span data-stu-id="856a3-154">We can specify a sequence of numbers with the built-in `..` operator.</span></span>

```powershell
PS> $data[1..3]
One
Two
Three
```

<span data-ttu-id="856a3-155">反之亦然。</span><span class="sxs-lookup"><span data-stu-id="856a3-155">This works in reverse too.</span></span>

```powershell
PS> $data[3..1]
Three
Two
One
```

<span data-ttu-id="856a3-156">可以使用负索引值从末尾进行偏移。</span><span class="sxs-lookup"><span data-stu-id="856a3-156">You can use negative index values to offset from the end.</span></span> <span data-ttu-id="856a3-157">因此，如果需要列表中的最后一项，可以使用 `-1`。</span><span class="sxs-lookup"><span data-stu-id="856a3-157">So if you need the last item in the list, you can use `-1`.</span></span>

```powershell
PS> $data[-1]
Three
```

<span data-ttu-id="856a3-158">关于 `..` 运算符，有一点需要注意。</span><span class="sxs-lookup"><span data-stu-id="856a3-158">One word of caution here with the `..` operator.</span></span> <span data-ttu-id="856a3-159">序列 `0..-1` 和 `-1..0` 的计算结果为值 `0,-1` 和 `-1,0`。</span><span class="sxs-lookup"><span data-stu-id="856a3-159">The sequence `0..-1` and `-1..0` evaluate to the values `0,-1` and `-1,0`.</span></span> <span data-ttu-id="856a3-160">如果忘记了这一细节，就很容易看到 `$data[0..-1]`，并认为它会枚举所有项。</span><span class="sxs-lookup"><span data-stu-id="856a3-160">It's easy to see `$data[0..-1]` and think it would enumerate all items if you forget this detail.</span></span> <span data-ttu-id="856a3-161">通过提供数组中的第一项和最后一项（其他值都不提供），`$data[0..-1]` 可提供与 `$data[0,-1]` 相同的值。</span><span class="sxs-lookup"><span data-stu-id="856a3-161">`$data[0..-1]` gives you the same value as `$data[0,-1]` by giving you the first and last item in the array (and none of the other values).</span></span>

#### <a name="out-of-bounds"></a><span data-ttu-id="856a3-162">超出范围</span><span class="sxs-lookup"><span data-stu-id="856a3-162">Out of bounds</span></span>

<span data-ttu-id="856a3-163">在大多数语言中，如果尝试访问超出数组末尾的项的索引，则会出现某种类型的错误或异常。</span><span class="sxs-lookup"><span data-stu-id="856a3-163">In most languages, if you try to access an index of an item that is past the end of the array, you would get some type of error or an exception.</span></span> <span data-ttu-id="856a3-164">PowerShell 不会返回任何内容且无提示。</span><span class="sxs-lookup"><span data-stu-id="856a3-164">PowerShell silently returns nothing.</span></span>

```powershell
PS> $null -eq $data[9000]
True
```

#### <a name="cannot-index-into-a-null-array"></a><span data-ttu-id="856a3-165">不能为空数组建立索引</span><span class="sxs-lookup"><span data-stu-id="856a3-165">Cannot index into a null array</span></span>

<span data-ttu-id="856a3-166">如果你的变量是 `$null`，并且尝试按数组的方式对其建立索引，则会出现 `System.Management.Automation.RuntimeException` 异常，并显示消息 `Cannot index into a null array`。</span><span class="sxs-lookup"><span data-stu-id="856a3-166">If your variable is `$null` and you try to index it like an array, you get a `System.Management.Automation.RuntimeException` exception with the message `Cannot index into a null array`.</span></span>

```powershell
PS> $empty = $null
SP> $empty[0]
Error: Cannot index into a null array.
```

<span data-ttu-id="856a3-167">因此，在尝试访问数组中的元素之前，请确保数组不是 `$null`。</span><span class="sxs-lookup"><span data-stu-id="856a3-167">So make sure your arrays are not `$null` before you try to access elements inside them.</span></span>

#### <a name="count"></a><span data-ttu-id="856a3-168">Count</span><span class="sxs-lookup"><span data-stu-id="856a3-168">Count</span></span>

<span data-ttu-id="856a3-169">数组和其他集合具有计数属性，可告知数组中有多少项。</span><span class="sxs-lookup"><span data-stu-id="856a3-169">Arrays and other collections have a count property that tells you how many items are in the array.</span></span>

```powershell
PS> $data.count
4
```

<span data-ttu-id="856a3-170">PowerShell 3.0 向大多数对象添加了计数属性。</span><span class="sxs-lookup"><span data-stu-id="856a3-170">PowerShell 3.0 added a count property to most objects.</span></span> <span data-ttu-id="856a3-171">你可以使用单个对象，它应该会提供计数 `1`。</span><span class="sxs-lookup"><span data-stu-id="856a3-171">you can have a single object and it should give you a count of `1`.</span></span>

```powershell
PS> $date = Get-Date
PS> $date.count
1
```

<span data-ttu-id="856a3-172">甚至 `$null` 也有计数属性，但它会返回 `0`。</span><span class="sxs-lookup"><span data-stu-id="856a3-172">Even `$null` has a count property except it returns `0`.</span></span>

```powershell
PS> $null.count
0
```

<span data-ttu-id="856a3-173">这里有一些陷阱，我将在本文稍后介绍检查 `$null` 或空数组时再来介绍。</span><span class="sxs-lookup"><span data-stu-id="856a3-173">There are some traps here that I will revisit when I cover checking for `$null` or empty arrays later on in this article.</span></span>

#### <a name="off-by-one-errors"></a><span data-ttu-id="856a3-174">大小差一错误</span><span class="sxs-lookup"><span data-stu-id="856a3-174">Off-by-one errors</span></span>

<span data-ttu-id="856a3-175">因为数组从索引 0 开始，所以产生了一个常见的编程错误。</span><span class="sxs-lookup"><span data-stu-id="856a3-175">A common programming error is created because arrays start at index 0.</span></span> <span data-ttu-id="856a3-176">大小差一错误可能通过两种方式引入。</span><span class="sxs-lookup"><span data-stu-id="856a3-176">Off-by-one errors can be introduced in two ways.</span></span>

<span data-ttu-id="856a3-177">第一种是，想要第二项并使用索引 `2` 但实际获取了第三项。</span><span class="sxs-lookup"><span data-stu-id="856a3-177">The first is by mentally thinking you want the second item and using an index of `2` and really getting the third item.</span></span> <span data-ttu-id="856a3-178">或者，假设你有四个项并且想要最后一项，因此使用计数来访问最后一项。</span><span class="sxs-lookup"><span data-stu-id="856a3-178">Or by thinking that you have four items and you want last item, so you use the count to access the last item.</span></span>

```powershell
$data[ $data.count ]
```

<span data-ttu-id="856a3-179">PowerShell 完全可以让你做到这一点，并为你准确提供索引 4 中存在的项：`$null`。</span><span class="sxs-lookup"><span data-stu-id="856a3-179">PowerShell is perfectly happy to let you do that and give you exactly what item exists at index 4: `$null`.</span></span> <span data-ttu-id="856a3-180">你应该使用 `$data.count - 1` 或我们在前面学到的 `-1`。</span><span class="sxs-lookup"><span data-stu-id="856a3-180">You should be using `$data.count - 1` or the `-1` that we learned about above.</span></span>

```powershell
PS> $data[ $data.count - 1 ]
Three
```

<span data-ttu-id="856a3-181">在这里，可以使用 `-1` 索引获取最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="856a3-181">This is where you can use the `-1` index to get the last element.</span></span>

```powershell
PS> $data[ -1 ]
Three
```

<span data-ttu-id="856a3-182">Lee Dailey 还向我指出，我们可以使用 `$data.GetUpperBound(0)` 获取最大索引号。</span><span class="sxs-lookup"><span data-stu-id="856a3-182">Lee Dailey also pointed out to me that we can use `$data.GetUpperBound(0)` to get the max index number.</span></span>

```powershell
PS> $data.GetUpperBound(0)
Three
```

<span data-ttu-id="856a3-183">第二种最常见的方式是，在循环访问列表时未在正确的时间停止。</span><span class="sxs-lookup"><span data-stu-id="856a3-183">The second most common way is when iterating the list and not stopping at the right time.</span></span> <span data-ttu-id="856a3-184">当我们谈到使用 `for` 循环时，我会再来讨论这一点。</span><span class="sxs-lookup"><span data-stu-id="856a3-184">I'll revisit this when we talk about using the `for` loop.</span></span>

### <a name="updating-items"></a><span data-ttu-id="856a3-185">更新项</span><span class="sxs-lookup"><span data-stu-id="856a3-185">Updating items</span></span>

<span data-ttu-id="856a3-186">我们可以使用同一索引来更新数组中的现有项。</span><span class="sxs-lookup"><span data-stu-id="856a3-186">We can use the same index to update existing items in the array.</span></span> <span data-ttu-id="856a3-187">这样，我们就可以直接访问并更新各个项。</span><span class="sxs-lookup"><span data-stu-id="856a3-187">This gives us direct access to update individual items.</span></span>

```powershell
$data[2] = 'dos'
$data[3] = 'tres'
```

<span data-ttu-id="856a3-188">如果我们尝试更新的项超出最后一个元素，则会出现 `Index was outside the bounds of the array.` 错误。</span><span class="sxs-lookup"><span data-stu-id="856a3-188">If we try to update an item that is past the last element, then we get an `Index was outside the bounds of the array.` error.</span></span>

```powershell
PS> $data[4] = 'four'
Index was outside the bounds of the array.
At line:1 char:1
+ $data[4] = 'four'
+ ~~~~~~~~~~~~~
+ CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
+ FullyQualifiedErrorId : System.IndexOutOfRangeException
```

<span data-ttu-id="856a3-189">稍后介绍如何使数组变大时，我会再来说明这一点。</span><span class="sxs-lookup"><span data-stu-id="856a3-189">I'll revisit this later when I talk about how to make an array larger.</span></span>

### <a name="iteration"></a><span data-ttu-id="856a3-190">迭代</span><span class="sxs-lookup"><span data-stu-id="856a3-190">Iteration</span></span>

<span data-ttu-id="856a3-191">在某些时候，你可能需要遍历或循环访问整个列表，并对数组中的每一项执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="856a3-191">At some point, you might need to walk or iterate the entire list and perform some action for each item in the array.</span></span>

#### <a name="pipeline"></a><span data-ttu-id="856a3-192">管道</span><span class="sxs-lookup"><span data-stu-id="856a3-192">Pipeline</span></span>

<span data-ttu-id="856a3-193">数组和 PowerShell 管道是相互适用的。</span><span class="sxs-lookup"><span data-stu-id="856a3-193">Arrays and the PowerShell pipeline are meant for each other.</span></span> <span data-ttu-id="856a3-194">这是处理这些值最简单的方法之一。</span><span class="sxs-lookup"><span data-stu-id="856a3-194">This is one of the simplest ways to process over those values.</span></span> <span data-ttu-id="856a3-195">将数组传递给管道时，数组中的每个项将得到单独处理。</span><span class="sxs-lookup"><span data-stu-id="856a3-195">When you pass an array to a pipeline, each item inside the array is processed individually.</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data | ForEach-Object {"Item: [$PSItem]"}
Item: [Zero]
Item: [One]
Item: [Two]
Item: [Three]
```

<span data-ttu-id="856a3-196">如果你之前未见过 `$PSItem`，只需知道它与 `$_` 相同。</span><span class="sxs-lookup"><span data-stu-id="856a3-196">If you have not seen `$PSItem` before, just know that it's the same thing as `$_`.</span></span> <span data-ttu-id="856a3-197">你可以使用其中任何一个，因为它们都表示管道中的当前对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-197">You can use either one because they both represent the current object in the pipeline.</span></span>

#### <a name="foreach-loop"></a><span data-ttu-id="856a3-198">ForEach 循环</span><span class="sxs-lookup"><span data-stu-id="856a3-198">ForEach loop</span></span>

<span data-ttu-id="856a3-199">`ForEach` 循环适用于集合。</span><span class="sxs-lookup"><span data-stu-id="856a3-199">The `ForEach` loop works well with collections.</span></span> <span data-ttu-id="856a3-200">使用以下语法：`foreach ( <variable> in <collection> )`</span><span class="sxs-lookup"><span data-stu-id="856a3-200">Using the syntax: `foreach ( <variable> in <collection> )`</span></span>

```powershell
foreach ( $node in $data )
{
    "Item: [$node]"
}
```

#### <a name="foreach-method"></a><span data-ttu-id="856a3-201">ForEach 方法</span><span class="sxs-lookup"><span data-stu-id="856a3-201">ForEach method</span></span>

<span data-ttu-id="856a3-202">我很容易忘记这一点，但它很适合简单的操作。</span><span class="sxs-lookup"><span data-stu-id="856a3-202">I tend to forget about this one but it works well for simple operations.</span></span> <span data-ttu-id="856a3-203">PowerShell 允许你对集合调用 `.ForEach()`。</span><span class="sxs-lookup"><span data-stu-id="856a3-203">PowerShell allows you to call `.ForEach()` on a collection.</span></span>

```powershell
PS> $data.foreach({"Item [$PSItem]"})
Item [Zero]
Item [One]
Item [Two]
Item [Three]
```

<span data-ttu-id="856a3-204">`.foreach()` 采用了一个是脚本块的参数。</span><span class="sxs-lookup"><span data-stu-id="856a3-204">The `.foreach()` takes a parameter that is a script block.</span></span> <span data-ttu-id="856a3-205">你可以删除括号，只提供脚本块。</span><span class="sxs-lookup"><span data-stu-id="856a3-205">You can drop the parentheses and just provide the script block.</span></span>

```powershell
$data.foreach{"Item [$PSItem]"}
```

<span data-ttu-id="856a3-206">这是一个少为人知的语法，但它的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="856a3-206">This is a lesser known syntax but it works just the same.</span></span> <span data-ttu-id="856a3-207">这个 `foreach` 方法是在 PowerShell 4.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="856a3-207">This `foreach` method was added in PowerShell 4.0.</span></span>

#### <a name="for-loop"></a><span data-ttu-id="856a3-208">For 循环</span><span class="sxs-lookup"><span data-stu-id="856a3-208">For loop</span></span>

<span data-ttu-id="856a3-209">在大多数其他语言中，`for` 循环的使用非常广泛，但在 PowerShell 中却很少见。</span><span class="sxs-lookup"><span data-stu-id="856a3-209">The `for` loop is used heavily in most other languages but you don’t see it much in PowerShell.</span></span> <span data-ttu-id="856a3-210">通常在遍历数组的上下文中才会看到此循环。</span><span class="sxs-lookup"><span data-stu-id="856a3-210">When you do see it, it's often in the context of walking an array.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++)
{
    "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="856a3-211">我们要做的第一件事是，将 `0` 初始化为 `$index`。</span><span class="sxs-lookup"><span data-stu-id="856a3-211">The first thing we do is initialize an `$index` to `0`.</span></span> <span data-ttu-id="856a3-212">然后添加 `$index` 必须小于 `$data.count` 的条件。</span><span class="sxs-lookup"><span data-stu-id="856a3-212">Then we add the condition that `$index` must be less than `$data.count`.</span></span> <span data-ttu-id="856a3-213">最后，我们指定，每次循环时，索引必须增加 `1`。</span><span class="sxs-lookup"><span data-stu-id="856a3-213">Finally, we specify that every time we loop that me must increase the index by `1`.</span></span> <span data-ttu-id="856a3-214">在本例中，`$index++` 为 `$index = $index + 1` 的缩写。</span><span class="sxs-lookup"><span data-stu-id="856a3-214">In this case `$index++` is short for `$index = $index + 1`.</span></span>

<span data-ttu-id="856a3-215">无论何时使用 `for` 循环，都需要特别注意条件。</span><span class="sxs-lookup"><span data-stu-id="856a3-215">Whenever you're using a `for` loop, pay special attention to the condition.</span></span> <span data-ttu-id="856a3-216">我在这里使用了 `$index -lt $data.count`。</span><span class="sxs-lookup"><span data-stu-id="856a3-216">I used `$index -lt $data.count` here.</span></span> <span data-ttu-id="856a3-217">条件很容易出现轻微错误，从而使逻辑中出现大小差一错误。</span><span class="sxs-lookup"><span data-stu-id="856a3-217">It's easy to get the condition slightly wrong to get an off-by-one error in your logic.</span></span> <span data-ttu-id="856a3-218">使用 `$index -le $data.count` 或 `$index -lt ($data.count - 1)` 会出现轻微错误。</span><span class="sxs-lookup"><span data-stu-id="856a3-218">Using `$index -le $data.count` or `$index -lt ($data.count - 1)` are ever so slightly wrong.</span></span> <span data-ttu-id="856a3-219">这会导致你的结果处理的项过多或过少。</span><span class="sxs-lookup"><span data-stu-id="856a3-219">That would cause your result to process too many or too few items.</span></span> <span data-ttu-id="856a3-220">这就是典型的大小差一错误。</span><span class="sxs-lookup"><span data-stu-id="856a3-220">This is the classic off-by-one error.</span></span>

#### <a name="switch-loop"></a><span data-ttu-id="856a3-221">Switch 循环</span><span class="sxs-lookup"><span data-stu-id="856a3-221">Switch loop</span></span>

<span data-ttu-id="856a3-222">这一点很容易被忽略。</span><span class="sxs-lookup"><span data-stu-id="856a3-222">This is one that is easy to overlook.</span></span> <span data-ttu-id="856a3-223">如果向 [switch 语句][]提供一个数组，它将检查数组中的每一项。</span><span class="sxs-lookup"><span data-stu-id="856a3-223">If you provide an array to a [switch statement][], it checks each item in the array.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
switch( $data )
{
    'One'
    {
        'Tock'
    }
    'Three'
    {
        'Tock'
    }
    Default
    {
        'Tick'
    }
}
```

```Output
Tick
Tock
Tick
Tock
```

<span data-ttu-id="856a3-224">我们可以使用 switch 语句来完成很多工作。</span><span class="sxs-lookup"><span data-stu-id="856a3-224">There are a lot of cool things that we can do with the switch statement.</span></span> <span data-ttu-id="856a3-225">我在另一篇文章中有专门介绍。</span><span class="sxs-lookup"><span data-stu-id="856a3-225">I have another article dedicated to this.</span></span>

- <span data-ttu-id="856a3-226">[关于 switch 语句的各项须知内容][switch 语句]</span><span class="sxs-lookup"><span data-stu-id="856a3-226">[Everything you ever wanted to know about the switch statement][switch statement]</span></span>

#### <a name="updating-values"></a><span data-ttu-id="856a3-227">更新值</span><span class="sxs-lookup"><span data-stu-id="856a3-227">Updating values</span></span>

<span data-ttu-id="856a3-228">当数组是字符串或整数（值类型）的集合时，有时你可能希望在循环访问时更新数组中的值。</span><span class="sxs-lookup"><span data-stu-id="856a3-228">When your array is a collection of string or integers (value types), sometimes you may want to update the values in the array as you loop over them.</span></span> <span data-ttu-id="856a3-229">上面的大多数循环中都使用了一个保存值副本的变量。</span><span class="sxs-lookup"><span data-stu-id="856a3-229">Most of the loops above use a variable in the loop that holds a copy of the value.</span></span> <span data-ttu-id="856a3-230">如果更新该变量，将不会更新数组中的原始值。</span><span class="sxs-lookup"><span data-stu-id="856a3-230">If you update that variable, the original value in the array is not updated.</span></span>

<span data-ttu-id="856a3-231">该语句的例外是 `for` 循环。</span><span class="sxs-lookup"><span data-stu-id="856a3-231">The exception to that statement is the `for` loop.</span></span> <span data-ttu-id="856a3-232">如果要遍历某个数组并更新其中的值，那么 `for` 循环就是你要找的结果。</span><span class="sxs-lookup"><span data-stu-id="856a3-232">If you want to walk an array and update values inside it, then the `for` loop is what you're looking for.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++ )
{
    $data[$index] = "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="856a3-233">此示例通过索引获取一个值，进行一些更改，然后使用同一个索引将其分配回去。</span><span class="sxs-lookup"><span data-stu-id="856a3-233">This example takes a value by index, makes a few changes, and then uses that same index to assign it back.</span></span>

## <a name="arrays-of-objects"></a><span data-ttu-id="856a3-234">对象数组</span><span class="sxs-lookup"><span data-stu-id="856a3-234">Arrays of Objects</span></span>

<span data-ttu-id="856a3-235">到目前为止，我们在数组中放置的唯一内容是值类型，但数组也可以包含对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-235">So far, the only thing we've placed in an array is a value type, but arrays can also contain objects.</span></span>

```powershell
$data = @(
    [pscustomobject]@{FirstName='Kevin';LastName='Marquette'}
    [pscustomobject]@{FirstName='John'; LastName='Doe'}
)
```

<span data-ttu-id="856a3-236">当你将它们分配给变量时，许多 cmdlet 将对象集合作为数组返回。</span><span class="sxs-lookup"><span data-stu-id="856a3-236">Many cmdlets return collections of objects as arrays when you assign them to a variable.</span></span>

```powershell
$processList = Get-Process
```

<span data-ttu-id="856a3-237">我们已经讨论的所有基本功能仍适用于对象数组，但有几个细节需要注意。</span><span class="sxs-lookup"><span data-stu-id="856a3-237">All of the basic features we already talked about still apply to arrays of objects with a few details worth pointing out.</span></span>

### <a name="accessing-properties"></a><span data-ttu-id="856a3-238">访问属性</span><span class="sxs-lookup"><span data-stu-id="856a3-238">Accessing properties</span></span>

<span data-ttu-id="856a3-239">可以使用索引访问集合中的单个项，就像使用值类型一样。</span><span class="sxs-lookup"><span data-stu-id="856a3-239">We can use an index to access an individual item in a collection just like with value types.</span></span>

```powershell
PS> $data[0]

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="856a3-240">可以直接访问和更新属性。</span><span class="sxs-lookup"><span data-stu-id="856a3-240">We can access and update properties directly.</span></span>

```powershell
PS> $data[0].FirstName

Kevin

PS> $data[0].FirstName = 'Jay'
PS> $data[0]

FirstName LastName
-----     ----
Jay       Marquette
```

#### <a name="array-properties"></a><span data-ttu-id="856a3-241">数组属性</span><span class="sxs-lookup"><span data-stu-id="856a3-241">Array properties</span></span>

<span data-ttu-id="856a3-242">通常，必须按如下所示枚举整个列表才能访问所有属性：</span><span class="sxs-lookup"><span data-stu-id="856a3-242">Normally you would have to enumerate the whole list like this to access all the properties:</span></span>

```powershell
PS> $data | ForEach-Object {$_.LastName}

Marquette
Doe
```

<span data-ttu-id="856a3-243">或通过使用 `Select-Object -ExpandProperty` cmdlet 来实现。</span><span class="sxs-lookup"><span data-stu-id="856a3-243">Or by using the `Select-Object -ExpandProperty` cmdlet.</span></span>

```powershell
PS> $data | Select-Object -ExpandProperty LastName

Marquette
Doe
```

<span data-ttu-id="856a3-244">但 PowerShell 提供了直接请求 `LastName` 的功能。</span><span class="sxs-lookup"><span data-stu-id="856a3-244">But PowerShell offers us the ability to request `LastName` directly.</span></span> <span data-ttu-id="856a3-245">PowerShell 会将它们全部枚举出来，并返回一个干净的列表。</span><span class="sxs-lookup"><span data-stu-id="856a3-245">PowerShell enumerates them all for us and returns a clean list.</span></span>

```powershell
PS> $data.LastName

Marquette
Doe
```

<span data-ttu-id="856a3-246">枚举仍然发生，但我们看不到它背后的复杂操作。</span><span class="sxs-lookup"><span data-stu-id="856a3-246">The enumeration still happens but we don't see the complexity behind it.</span></span>

### <a name="where-object-filtering"></a><span data-ttu-id="856a3-247">Where-Object 筛选</span><span class="sxs-lookup"><span data-stu-id="856a3-247">Where-Object filtering</span></span>

<span data-ttu-id="856a3-248">这就是 `Where-Object` 的作用：我们可以根据对象的属性，从数组中筛选并选择需要的内容。</span><span class="sxs-lookup"><span data-stu-id="856a3-248">This is where `Where-Object` comes in so we can filter and select what we want out of the array based on the properties of the object.</span></span>

```powershell
PS> $data | Where-Object {$_.FirstName -eq 'Kevin'}

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="856a3-249">我们可以编写相同的查询来获取所需的 `FirstName`。</span><span class="sxs-lookup"><span data-stu-id="856a3-249">We can write that same query to get the `FirstName` we are looking for.</span></span>

```powershell
$data | Where FirstName -eq Kevin
```

#### <a name="where"></a><span data-ttu-id="856a3-250">Where()</span><span class="sxs-lookup"><span data-stu-id="856a3-250">Where()</span></span>

<span data-ttu-id="856a3-251">数组中有一个 `Where()` 方法，允许你为筛选器指定一个 `scriptblock`。</span><span class="sxs-lookup"><span data-stu-id="856a3-251">Arrays have a `Where()` method on them that allows you to specify a `scriptblock` for the filter.</span></span>

```powershell
$data.Where({$_.FirstName -eq 'Kevin'})
```

<span data-ttu-id="856a3-252">此功能是在 PowerShell 4.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="856a3-252">This feature was added in PowerShell 4.0.</span></span>

### <a name="updating-objects-in-loops"></a><span data-ttu-id="856a3-253">更新循环中的对象</span><span class="sxs-lookup"><span data-stu-id="856a3-253">Updating objects in loops</span></span>

<span data-ttu-id="856a3-254">对于值类型，更新数组的唯一方法是使用 for 循环，因为我们需要知道替换值的索引。</span><span class="sxs-lookup"><span data-stu-id="856a3-254">With value types, the only way to update the array is to use a for loop because we need to know the index to replace the value.</span></span> <span data-ttu-id="856a3-255">由于对象是引用类型，因此我们有更多选择。</span><span class="sxs-lookup"><span data-stu-id="856a3-255">We have more options with objects because they are reference types.</span></span> <span data-ttu-id="856a3-256">下面是一个简短的示例：</span><span class="sxs-lookup"><span data-stu-id="856a3-256">Here is a quick example:</span></span>

```powershell
foreach($person in $data)
{
    $person.FirstName = 'Kevin'
}
```

<span data-ttu-id="856a3-257">此循环将遍历 `$data` 数组中的每个对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-257">This loop is walking every object in the `$data` array.</span></span> <span data-ttu-id="856a3-258">由于对象是引用类型，因此 `$person` 变量会引用数组中完全相同的对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-258">Because objects are reference types, the `$person` variable references the exact same object that is in the array.</span></span> <span data-ttu-id="856a3-259">因此，更新属性即会更新原始对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-259">So updates to its properties do update the original.</span></span>

<span data-ttu-id="856a3-260">仍无法以这种方式替换整个对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-260">You still can't replace the whole object this way.</span></span> <span data-ttu-id="856a3-261">如果尝试将一个新对象分配给 `$person` 变量，则会将变量引用更新为不再指向数组中原始对象的其他对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-261">If you try to assign a new object to the `$person` variable, you're updating the variable reference to something else that no longer points to the original object in the array.</span></span> <span data-ttu-id="856a3-262">这并不像预期那样：</span><span class="sxs-lookup"><span data-stu-id="856a3-262">This doesn't work like you would expect:</span></span>

```powershell
foreach($person in $data)
{
    $person = [pscustomobject]@{
        FirstName='Kevin'
        LastName='Marquette'
    }
}
```

## <a name="operators"></a><span data-ttu-id="856a3-263">运算符</span><span class="sxs-lookup"><span data-stu-id="856a3-263">Operators</span></span>

<span data-ttu-id="856a3-264">PowerShell 中的运算符也适用于数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-264">The operators in PowerShell also work on arrays.</span></span> <span data-ttu-id="856a3-265">其中一些的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="856a3-265">Some of them work slightly differently.</span></span>

### <a name="-join"></a><span data-ttu-id="856a3-266">-join</span><span class="sxs-lookup"><span data-stu-id="856a3-266">-join</span></span>

<span data-ttu-id="856a3-267">`-join` 运算符最明显，让我们先来看一下。</span><span class="sxs-lookup"><span data-stu-id="856a3-267">The `-join` operator is the most obvious one so let's look at it first.</span></span> <span data-ttu-id="856a3-268">我非常喜欢 `-join` 运算符并且经常使用。</span><span class="sxs-lookup"><span data-stu-id="856a3-268">I like the `-join` operator and use it often.</span></span> <span data-ttu-id="856a3-269">它能将数组中的所有元素与你指定的字符或字符串联接在一起。</span><span class="sxs-lookup"><span data-stu-id="856a3-269">It joins all elements in the array with the character or string that you specify.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join '-'
1-2-3-4
PS> $data -join ','
1,2,3,4
```

<span data-ttu-id="856a3-270">我喜欢 `-join` 运算符的一项功能是它能处理单个项。</span><span class="sxs-lookup"><span data-stu-id="856a3-270">One of the features that I like about the `-join` operator is that it handles single items.</span></span>

```powershell
PS> 1 -join '-'
1
```

<span data-ttu-id="856a3-271">我会在日志记录和详细消息中使用它。</span><span class="sxs-lookup"><span data-stu-id="856a3-271">I use this inside logging and verbose messages.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> "Data is $($data -join ',')."
Data is 1,2,3,4.
```

#### <a name="-join-array"></a><span data-ttu-id="856a3-272">-join $array</span><span class="sxs-lookup"><span data-stu-id="856a3-272">-join $array</span></span>

<span data-ttu-id="856a3-273">Lee Dailey 向我介绍了一个妙招。</span><span class="sxs-lookup"><span data-stu-id="856a3-273">Here is a clever trick that Lee Dailey pointed out to me.</span></span> <span data-ttu-id="856a3-274">如果你希望无需分隔符即可联接所有内容，请不要这样做：</span><span class="sxs-lookup"><span data-stu-id="856a3-274">If you ever want to join everything without a delimiter, instead of doing this:</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join $null
1234
```

<span data-ttu-id="856a3-275">可以将数组作为不带前缀的参数与 `-join` 一起使用。</span><span class="sxs-lookup"><span data-stu-id="856a3-275">You can use `-join` with the array as the parameter with no prefix.</span></span> <span data-ttu-id="856a3-276">具体请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="856a3-276">Take a look at this example to see that I'm talking about.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> -join $data
1234
```

### <a name="-replace-and--split"></a><span data-ttu-id="856a3-277">-replace 和 -split</span><span class="sxs-lookup"><span data-stu-id="856a3-277">-replace and -split</span></span>

<span data-ttu-id="856a3-278">其他运算符（如 `-replace` 和 `-split`）会对数组中的每个项执行。</span><span class="sxs-lookup"><span data-stu-id="856a3-278">The other operators like `-replace` and `-split` execute on each item in the array.</span></span> <span data-ttu-id="856a3-279">我不能说我都用过它们，但这里有一个示例。</span><span class="sxs-lookup"><span data-stu-id="856a3-279">I can't say that I have ever used them this way but here is an example.</span></span>

```powershell
PS> $data = @('ATX-SQL-01','ATX-SQL-02','ATX-SQL-03')
PS> $data -replace 'ATX','LAX'
LAX-SQL-01
LAX-SQL-02
LAX-SQL-03
```

### <a name="-contains"></a><span data-ttu-id="856a3-280">-contains</span><span class="sxs-lookup"><span data-stu-id="856a3-280">-contains</span></span>

<span data-ttu-id="856a3-281">使用 `-contains` 运算符可以检查值数组，以查看其是否包含指定值。</span><span class="sxs-lookup"><span data-stu-id="856a3-281">The `-contains` operator allows you to check an array of values to see if it contains a specified value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -contains 'green'
True
```

### <a name="-in"></a><span data-ttu-id="856a3-282">-in</span><span class="sxs-lookup"><span data-stu-id="856a3-282">-in</span></span>

<span data-ttu-id="856a3-283">如果要验证的单个值与几个值中的一个相匹配，则可以使用 `-in` 运算符。</span><span class="sxs-lookup"><span data-stu-id="856a3-283">When you have a single value that you would like to verify matches one of several values, you can use the `-in` operator.</span></span> <span data-ttu-id="856a3-284">该值位于运算式的左侧，而数组位于右侧。</span><span class="sxs-lookup"><span data-stu-id="856a3-284">The value would be on the left and the array on the right-hand side of the operation.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> 'green' -in $data
True
```

<span data-ttu-id="856a3-285">如果列表很大，这可能会占用大量资源。</span><span class="sxs-lookup"><span data-stu-id="856a3-285">This can get expensive if the list is large.</span></span> <span data-ttu-id="856a3-286">如果要检查多个值，我经常使用正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="856a3-286">I often use a regex pattern if I'm checking more than a few values.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $pattern = "^({0})$" -f ($data -join '|')
PS> $pattern
^(red|green|blue)$

PS> 'green' -match $pattern
True
```

### <a name="-eq-and--ne"></a><span data-ttu-id="856a3-287">-eq 和 -ne</span><span class="sxs-lookup"><span data-stu-id="856a3-287">-eq and -ne</span></span>

<span data-ttu-id="856a3-288">等式和数组相结合可能会变得复杂。</span><span class="sxs-lookup"><span data-stu-id="856a3-288">Equality and arrays can get complicated.</span></span> <span data-ttu-id="856a3-289">当数组位于左侧时，将对每个项进行比较。</span><span class="sxs-lookup"><span data-stu-id="856a3-289">When the array is on the left side, every item gets compared.</span></span> <span data-ttu-id="856a3-290">它将返回匹配的对象，而不是返回 `True`。</span><span class="sxs-lookup"><span data-stu-id="856a3-290">Instead of returning `True`, it returns the object that matches.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -eq 'green'
green
```

<span data-ttu-id="856a3-291">使用 `-ne` 运算符时，将获得不等于我们指定值的所有值。</span><span class="sxs-lookup"><span data-stu-id="856a3-291">When you use the `-ne` operator, we get all the values that are not equal to our value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -ne 'green'
red
blue
```

<span data-ttu-id="856a3-292">在 `if()` 语句中使用此运算符时，返回的值为 `True` 值。</span><span class="sxs-lookup"><span data-stu-id="856a3-292">When you use this in an `if()` statement, a value that is returned is a `True` value.</span></span> <span data-ttu-id="856a3-293">如果未返回任何值，则它是 `False` 值。</span><span class="sxs-lookup"><span data-stu-id="856a3-293">If no value is returned, then it's a `False` value.</span></span> <span data-ttu-id="856a3-294">下面这两个语句的计算结果都是 `True`。</span><span class="sxs-lookup"><span data-stu-id="856a3-294">Both of these next statements evaluate to `True`.</span></span>

```powershell
$data = @('red','green','blue')
if ( $data -eq 'green' )
{
    'Green was found'
}
if ( $data -ne 'green' )
{
    'And green was not found'
}
```

<span data-ttu-id="856a3-295">当我们讨论 `$null` 测试时会来回顾这一点。</span><span class="sxs-lookup"><span data-stu-id="856a3-295">I'll revisit this in a moment when we talk about testing for `$null`.</span></span>

### <a name="-match"></a><span data-ttu-id="856a3-296">-match</span><span class="sxs-lookup"><span data-stu-id="856a3-296">-match</span></span>

<span data-ttu-id="856a3-297">`-match` 运算符会尝试匹配集合中的每一项。</span><span class="sxs-lookup"><span data-stu-id="856a3-297">The `-match` operator tries to match each item in the collection.</span></span>

```powershell
PS> $servers = @(
    'LAX-SQL-01'
    'LAX-API-01'
    'ATX-SQL-01'
    'ATX-API-01'
)
PS> $servers -match 'SQL'
LAX-SQL-01
ATX-SQL-01
```

<span data-ttu-id="856a3-298">将 `-match` 与单个值结合使用时，将使用匹配信息填充一个特殊变量 `$Matches`。</span><span class="sxs-lookup"><span data-stu-id="856a3-298">When you use `-match` with a single value, a special variable `$Matches` gets populated with match info.</span></span> <span data-ttu-id="856a3-299">当以这种方式处理数组时，情况就不同了。</span><span class="sxs-lookup"><span data-stu-id="856a3-299">This isn't the case when an array is processed this way.</span></span>

<span data-ttu-id="856a3-300">我们可以采用与 `Select-String` 相同的方法。</span><span class="sxs-lookup"><span data-stu-id="856a3-300">We can take the same approach with `Select-String`.</span></span>

```powershell
$servers | Select-String SQL
```

<span data-ttu-id="856a3-301">在另一篇名为[使用正则表达式的多种方式][]的文章中，我详细介绍了 `Select-String`、`-match` 和 `$matches` 变量。</span><span class="sxs-lookup"><span data-stu-id="856a3-301">I take a closer look at `Select-String`,`-match` and the `$matches` variable in another post called [The many ways to use regex][].</span></span>

### <a name="null-or-empty"></a><span data-ttu-id="856a3-302">$null 或空</span><span class="sxs-lookup"><span data-stu-id="856a3-302">$null or empty</span></span>

<span data-ttu-id="856a3-303">测试 `$null` 或空数组可能比较棘手。</span><span class="sxs-lookup"><span data-stu-id="856a3-303">Testing for `$null` or empty arrays can be tricky.</span></span> <span data-ttu-id="856a3-304">下面是一些常见的数组陷阱。</span><span class="sxs-lookup"><span data-stu-id="856a3-304">Here are the common traps with arrays.</span></span>

<span data-ttu-id="856a3-305">这个语句乍一看似乎可行。</span><span class="sxs-lookup"><span data-stu-id="856a3-305">At a glance, this statement looks like it should work.</span></span>

```powershell
if ( $array -eq $null)
{
    'Array is $null'
}
```

<span data-ttu-id="856a3-306">但我刚刚讲了 `-eq` 如何检查数组中的每一项。</span><span class="sxs-lookup"><span data-stu-id="856a3-306">But I just went over how `-eq` checks each item in the array.</span></span> <span data-ttu-id="856a3-307">因此，我们可以有一个由几个项组成的数组，其中只有一个 $null 值，它的值将为 `$true`</span><span class="sxs-lookup"><span data-stu-id="856a3-307">So we can have an array of several items with a single $null value and it would evaluate to `$true`</span></span>

```powershell
$array = @('one',$null,'three')
if ( $array -eq $null)
{
    'I think Array is $null, but I would be wrong'
}
```

<span data-ttu-id="856a3-308">这就是最好将 `$null` 放置在运算符左侧的原因。</span><span class="sxs-lookup"><span data-stu-id="856a3-308">This is why it's a best practice to place the `$null` on the left side of the operator.</span></span> <span data-ttu-id="856a3-309">这样此方案将不会出现任何问题。</span><span class="sxs-lookup"><span data-stu-id="856a3-309">This makes this scenario a non-issue.</span></span>

```powershell
if ( $null -eq $array )
{
    'Array actually is $null'
}
```

<span data-ttu-id="856a3-310">`$null` 数组与空数组不同。</span><span class="sxs-lookup"><span data-stu-id="856a3-310">A `$null` array isn't the same thing as an empty array.</span></span> <span data-ttu-id="856a3-311">如果知道有一个数组，请检查其中对象的计数。</span><span class="sxs-lookup"><span data-stu-id="856a3-311">If you know you have an array, check the count of objects in it.</span></span> <span data-ttu-id="856a3-312">如果数组为 `$null`，则计数为 `0`。</span><span class="sxs-lookup"><span data-stu-id="856a3-312">If the array is `$null`, the count is `0`.</span></span>

```powershell
if ( $array.count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="856a3-313">还有一个陷阱需要注意。</span><span class="sxs-lookup"><span data-stu-id="856a3-313">There is one more trap to watch out for here.</span></span> <span data-ttu-id="856a3-314">即使有单个对象，也可以使用 `count`，除非该对象是 `PSCustomObject`。</span><span class="sxs-lookup"><span data-stu-id="856a3-314">You can use the `count` even if you have a single object, unless that object is a `PSCustomObject`.</span></span> <span data-ttu-id="856a3-315">这是在 PowerShell 6.1 中修复的 bug。</span><span class="sxs-lookup"><span data-stu-id="856a3-315">This is a bug that is fixed in PowerShell 6.1.</span></span>
<span data-ttu-id="856a3-316">这是个不错的消息，但有很多人仍在使用 5.1，因此需要注意。</span><span class="sxs-lookup"><span data-stu-id="856a3-316">That's good news, but a lot of people are still on 5.1 and need to watch out for it.</span></span>

```powershell
PS> $object = [PSCustomObject]@{Name='TestObject'}
PS> $object.count
$null
```

<span data-ttu-id="856a3-317">如果仍在使用 PowerShell 5.1，则可以在检查计数之前将对象包装在数组中，以获取准确的计数。</span><span class="sxs-lookup"><span data-stu-id="856a3-317">If you're still on PowerShell 5.1, you can wrap the object in an array before checking the count to get an accurate count.</span></span>

```powershell
if ( @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="856a3-318">稳妥起见，请检查是否有 `$null`，然后再检查计数。</span><span class="sxs-lookup"><span data-stu-id="856a3-318">To fully play it safe, check for `$null`, then check the count.</span></span>

```powershell
if ( $null -ne $array -and @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

### <a name="all--eq"></a><span data-ttu-id="856a3-319">All -eq</span><span class="sxs-lookup"><span data-stu-id="856a3-319">All -eq</span></span>

<span data-ttu-id="856a3-320">我最近看到有人询问[如何验证数组中的每个值是否与给定值匹配][]。</span><span class="sxs-lookup"><span data-stu-id="856a3-320">I recently saw someone ask [how to verify that every value in an array matches a given value][].</span></span>
<span data-ttu-id="856a3-321">Reddit 用户 /u/bis 提供了一个巧妙的[解决方案][]，该解决方案将检查是否存在不正确的值，然后翻转结果。</span><span class="sxs-lookup"><span data-stu-id="856a3-321">Reddit user **/u/bis** had this clever [solution][] that checks for any incorrect values and then flips the result.</span></span>

```powershell
$results = Test-Something
if ( -not ( $results -ne 'Passed') )
{
    'All results a Passed'
}
```

## <a name="adding-to-arrays"></a><span data-ttu-id="856a3-322">添加到数组</span><span class="sxs-lookup"><span data-stu-id="856a3-322">Adding to arrays</span></span>

<span data-ttu-id="856a3-323">现在，你开始想知道如何向数组中添加项。</span><span class="sxs-lookup"><span data-stu-id="856a3-323">At this point, you're starting to wonder how to add items to an array.</span></span> <span data-ttu-id="856a3-324">简单回答是，不能添加。</span><span class="sxs-lookup"><span data-stu-id="856a3-324">The quick answer is that you can't.</span></span> <span data-ttu-id="856a3-325">数组在内存中具有固定大小。</span><span class="sxs-lookup"><span data-stu-id="856a3-325">An array is a fixed size in memory.</span></span> <span data-ttu-id="856a3-326">如果需要对其进行扩展或向其中添加单个项，则需要创建新数组，并从旧数组中复制所有值。</span><span class="sxs-lookup"><span data-stu-id="856a3-326">If you need to grow it or add a single item to it, then you need to create a new array and copy all the values over from the old array.</span></span> <span data-ttu-id="856a3-327">这听起来非常昂贵，而且工作量很大，但 PowerShell 隐藏了创建新数组的复杂性。</span><span class="sxs-lookup"><span data-stu-id="856a3-327">This sounds expensive and like a lot of work, however, PowerShell hides the complexity of creating the new array.</span></span>

### <a name="array-addition"></a><span data-ttu-id="856a3-328">数组加法</span><span class="sxs-lookup"><span data-stu-id="856a3-328">Array addition</span></span>

<span data-ttu-id="856a3-329">可以对数组使用加法运算符来创建新数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-329">We can use the addition operator with arrays to create a new array.</span></span> <span data-ttu-id="856a3-330">假设有以下两个数组：</span><span class="sxs-lookup"><span data-stu-id="856a3-330">So given these two arrays:</span></span>

```powershell
$first = @(
    'Zero'
    'One'
)
$second = @(
    'Two'
    'Three'
)
```

<span data-ttu-id="856a3-331">我们可以将它们加起来获得一个新数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-331">We can add them together to get a new array.</span></span>

```powershell
PS> $first + $second

Zero
One
Two
Three
```

### <a name="plus-equals-"></a><span data-ttu-id="856a3-332">加等于 + =</span><span class="sxs-lookup"><span data-stu-id="856a3-332">Plus equals +=</span></span>

<span data-ttu-id="856a3-333">我们可以就地创建新数组，并向其添加一个项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="856a3-333">We can create a new array in place and add an item to it like this:</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
$data += 'four'
```

<span data-ttu-id="856a3-334">请记住，每次使用 `+=` 时，都会复制并创建一个新数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-334">Just remember that every time you use `+=` that you're duplicating and creating a new array.</span></span> <span data-ttu-id="856a3-335">对于小型数据集，这并不是问题，但缩放性极差。</span><span class="sxs-lookup"><span data-stu-id="856a3-335">This is a not an issue for small datasets but it scales extremely poorly.</span></span>

### <a name="pipeline-assignment"></a><span data-ttu-id="856a3-336">管道分配</span><span class="sxs-lookup"><span data-stu-id="856a3-336">Pipeline assignment</span></span>

<span data-ttu-id="856a3-337">可以将任何管道的结果分配到变量中。</span><span class="sxs-lookup"><span data-stu-id="856a3-337">You can assign the results of any pipeline into a variable.</span></span> <span data-ttu-id="856a3-338">它是一个包含多个项的数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-338">It's an array if it contains multiple items.</span></span>

```powershell
$array = 1..5 | ForEach-Object {
    "ATX-SQL-$PSItem"
}
```

<span data-ttu-id="856a3-339">通常，当我们考虑使用管道时，我们会想到典型的 PowerShell 单行命令。</span><span class="sxs-lookup"><span data-stu-id="856a3-339">Normally when we think of using the pipeline, we think of the typical PowerShell one-liners.</span></span> <span data-ttu-id="856a3-340">可以通过 `foreach()` 语句和其他循环来利用管道。</span><span class="sxs-lookup"><span data-stu-id="856a3-340">We can leverage the pipeline with `foreach()` statements and other loops.</span></span> <span data-ttu-id="856a3-341">因此，我们可以将项放到管道中，而不是在循环中向数组添加项。</span><span class="sxs-lookup"><span data-stu-id="856a3-341">So instead of adding items to an array in a loop, we can drop items onto the pipeline.</span></span>

```powershell
$array = foreach ( $node in (1..5))
{
    "ATX-SQL-$node"
}
```

<span data-ttu-id="856a3-342">通过将 `foreach` 的结果分配给一个变量，我们会捕获所有对象并创建一个数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-342">By assigning the results of the `foreach` to a variable, we capture all the objects and create a single array.</span></span>

## <a name="array-types"></a><span data-ttu-id="856a3-343">数组类型</span><span class="sxs-lookup"><span data-stu-id="856a3-343">Array Types</span></span>

<span data-ttu-id="856a3-344">默认情况下，PowerShell 中的数组按 `[PSObject[]]` 类型创建。</span><span class="sxs-lookup"><span data-stu-id="856a3-344">By default, an array in PowerShell is created as a `[PSObject[]]` type.</span></span> <span data-ttu-id="856a3-345">这使它可以包含任何类型的对象或值。</span><span class="sxs-lookup"><span data-stu-id="856a3-345">This allows it to contain any type of object or value.</span></span> <span data-ttu-id="856a3-346">这是因为所有一切都是从 `PSObject` 类型继承的。</span><span class="sxs-lookup"><span data-stu-id="856a3-346">This works because everything is inherited from the `PSObject` type.</span></span>

### <a name="strongly-typed-arrays"></a><span data-ttu-id="856a3-347">强类型数组</span><span class="sxs-lookup"><span data-stu-id="856a3-347">Strongly typed arrays</span></span>

<span data-ttu-id="856a3-348">你可以使用类似的语法来创建任意类型的数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-348">You can create an array of any type using a similar syntax.</span></span> <span data-ttu-id="856a3-349">创建强类型数组时，它只能包含指定类型的值或对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-349">When you create a strongly typed array, it can only contain values or objects the specified type.</span></span>

```powershell
PS> [int[]] $numbers = 1,2,3
PS> [int[]] $numbers2 = 'one','two','three'
ERROR: Cannot convert value "one" to type "System.Int32". Input string was not in a correct format."

PS> [string[]] $strings = 'one','two','three'
```

### <a name="arraylist"></a><span data-ttu-id="856a3-350">ArrayList</span><span class="sxs-lookup"><span data-stu-id="856a3-350">ArrayList</span></span>

<span data-ttu-id="856a3-351">向数组中添加项是其最大限制之一，但还有其他一些集合可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="856a3-351">Adding items to an array is one of its biggest limitations, but there are a few other collections that we can turn to that solve this problem.</span></span>

<span data-ttu-id="856a3-352">当我们需要一个可以更快使用的数组时，我们通常首先会想到 `ArrayList`。</span><span class="sxs-lookup"><span data-stu-id="856a3-352">The `ArrayList` is commonly one of the first things that we think of when we need an array that is faster to work with.</span></span> <span data-ttu-id="856a3-353">它类似于一个对象数组，会在我们需要它的每一个地方，但它可以快速添加项。</span><span class="sxs-lookup"><span data-stu-id="856a3-353">It acts like an object array every place that we need it, but it handles adding items quickly.</span></span>

<span data-ttu-id="856a3-354">下面介绍如何创建 `ArrayList` 并向其中添加项。</span><span class="sxs-lookup"><span data-stu-id="856a3-354">Here is how we create an `ArrayList` and add items to it.</span></span>

```powershell
$myarray = [System.Collections.ArrayList]::new()
[void]$myArray.Add('Value')
```

<span data-ttu-id="856a3-355">我们正在调用 .NET 以获取此类型。</span><span class="sxs-lookup"><span data-stu-id="856a3-355">We are calling into .NET to get this type.</span></span> <span data-ttu-id="856a3-356">在本例中，我们将使用默认构造函数来创建它。</span><span class="sxs-lookup"><span data-stu-id="856a3-356">In this case, we are using the default constructor to create it.</span></span> <span data-ttu-id="856a3-357">然后调用 `Add` 方法向其中添加项。</span><span class="sxs-lookup"><span data-stu-id="856a3-357">Then we call the `Add` method to add an item to it.</span></span>

<span data-ttu-id="856a3-358">我在行首使用 `[void]` 是为了禁用返回代码。</span><span class="sxs-lookup"><span data-stu-id="856a3-358">The reason I'm using `[void]` at the beginning of the line is to suppress the return code.</span></span> <span data-ttu-id="856a3-359">某些 .NET 调用会这么做，并可能会产生意外输出。</span><span class="sxs-lookup"><span data-stu-id="856a3-359">Some .NET calls do this and can create unexpected output.</span></span>

<span data-ttu-id="856a3-360">如果数组中的唯一数据是字符串，那么还可以使用 [StringBuilder][]。</span><span class="sxs-lookup"><span data-stu-id="856a3-360">If the only data that you have in your array is strings, then also take a look at using [StringBuilder][].</span></span> <span data-ttu-id="856a3-361">它几乎是一样的，但有一些仅用于处理字符串的方法。</span><span class="sxs-lookup"><span data-stu-id="856a3-361">It's almost the same thing but has some methods that are just for dealing with strings.</span></span> <span data-ttu-id="856a3-362">`StringBuilder` 专为性能而设计。</span><span class="sxs-lookup"><span data-stu-id="856a3-362">The `StringBuilder` is specially designed for performance.</span></span>

<span data-ttu-id="856a3-363">人们从数组转向 `ArrayList` 非常常见。</span><span class="sxs-lookup"><span data-stu-id="856a3-363">It's common to see people move to `ArrayList` from arrays.</span></span> <span data-ttu-id="856a3-364">但它来自于 C# 尚未获得广泛支持的时代。</span><span class="sxs-lookup"><span data-stu-id="856a3-364">But it comes from a time where C# didn't have generic support.</span></span> <span data-ttu-id="856a3-365">支持泛型 `List[]` 后，`ArrayList` 已过时</span><span class="sxs-lookup"><span data-stu-id="856a3-365">The `ArrayList` is depreciated in support for the generic `List[]`</span></span>

### <a name="generic-list"></a><span data-ttu-id="856a3-366">泛型列表</span><span class="sxs-lookup"><span data-stu-id="856a3-366">Generic List</span></span>

<span data-ttu-id="856a3-367">泛型类型是 C# 中的一种特殊类型，用于定义通用类，用户会在创建时指定它所使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="856a3-367">A generic type is a special type in C# that defines a generalized class and the user specifies the data types it uses when created.</span></span> <span data-ttu-id="856a3-368">因此，如果需要一系列数字或字符串，则应定义想要的 `int` 或 `string` 类型列表。</span><span class="sxs-lookup"><span data-stu-id="856a3-368">So if you want a list of numbers or strings, you would define that you want list of `int` or `string` types.</span></span>

<span data-ttu-id="856a3-369">下面介绍如何创建字符串列表：</span><span class="sxs-lookup"><span data-stu-id="856a3-369">Here is how you create a List for strings.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[string]]::new()
```

<span data-ttu-id="856a3-370">或数字列表：</span><span class="sxs-lookup"><span data-stu-id="856a3-370">Or a list for numbers.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]::new()
```

<span data-ttu-id="856a3-371">我们可以将现有数组强制转换为类似于这样的列表，而无需先创建对象：</span><span class="sxs-lookup"><span data-stu-id="856a3-371">We can cast an existing array to a list like this without creating the object first:</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]@(1,2,3)
```

<span data-ttu-id="856a3-372">可以通过 PowerShell 5 和更高版本中的 `using namespace` 语句缩短语法。</span><span class="sxs-lookup"><span data-stu-id="856a3-372">We can shorten the syntax with the `using namespace` statement in PowerShell 5 and newer.</span></span> <span data-ttu-id="856a3-373">`using` 语句需是脚本的第一行。</span><span class="sxs-lookup"><span data-stu-id="856a3-373">The `using` statement needs to be the first line of your script.</span></span> <span data-ttu-id="856a3-374">通过声明命名空间，PowerShell 允许你在引用数据类型时不使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="856a3-374">By declaring a namespace, PowerShell lets you leave it off of the data types when you reference them.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[int]]@(1,2,3)
```

<span data-ttu-id="856a3-375">这使 `List` 更有用。</span><span class="sxs-lookup"><span data-stu-id="856a3-375">This makes the `List` much more usable.</span></span>

<span data-ttu-id="856a3-376">你可以使用类似的 `Add` 方法。</span><span class="sxs-lookup"><span data-stu-id="856a3-376">You have a similar `Add` method available to you.</span></span> <span data-ttu-id="856a3-377">与 ArrayList 不同，`Add` 方法没有返回值，因此我们不必使用 `void`。</span><span class="sxs-lookup"><span data-stu-id="856a3-377">Unlike the ArrayList, there is no return value on the `Add` method so we don't have to `void` it.</span></span>

```powershell
$myList.Add(10)
```

<span data-ttu-id="856a3-378">我们仍然可以像访问其他数组一样访问元素。</span><span class="sxs-lookup"><span data-stu-id="856a3-378">And we can still access the elements like other arrays.</span></span>

```powershell
PS> $myList[-1]
10
```

#### <a name="listpsobject"></a><span data-ttu-id="856a3-379">List[PSObject]</span><span class="sxs-lookup"><span data-stu-id="856a3-379">List[PSObject]</span></span>

<span data-ttu-id="856a3-380">你可以使用任何类型的列表，但当你不知道对象的类型时，可以使用 `[List[PSObject]]` 来包含它们。</span><span class="sxs-lookup"><span data-stu-id="856a3-380">You can have a list of any type, but when you don’t know the type of objects, you can use `[List[PSObject]]` to contain them.</span></span>

```powershell
$list = [List[PSObject]]::new()
```

#### <a name="remove"></a><span data-ttu-id="856a3-381">Remove()</span><span class="sxs-lookup"><span data-stu-id="856a3-381">Remove()</span></span>

<span data-ttu-id="856a3-382">`ArrayList` 和泛型 `List[]` 均支持从集合中移除项。</span><span class="sxs-lookup"><span data-stu-id="856a3-382">The `ArrayList` and the generic `List[]` both support removing items from the collection.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[string]]@('Zero','One','Two','Three')
[void]$myList.Remove("Two")
Zero
One
Three
```

<span data-ttu-id="856a3-383">使用值类型时，它会从列表中删除第一个值。</span><span class="sxs-lookup"><span data-stu-id="856a3-383">When working with value types, it removes the first one from the list.</span></span> <span data-ttu-id="856a3-384">你可以反复调用它来删除该值。</span><span class="sxs-lookup"><span data-stu-id="856a3-384">You can call it over and over again to keep removing that value.</span></span> <span data-ttu-id="856a3-385">如果是引用类型，则必须提供要删除的对象。</span><span class="sxs-lookup"><span data-stu-id="856a3-385">If you have reference types, you have to provide the object that you want removed.</span></span>

```powershell
[list[System.Management.Automation.PSDriveInfo]]$drives = Get-PSDrive
$drives.remove($drives[2])
```

```powershell
$delete = $drives[2]
$drives.remove($delete)
```

<span data-ttu-id="856a3-386">如果此移除方法能够查找并删除集合中的项，则将返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="856a3-386">The remove method returns `true` if it was able to find and remove the item from the collection.</span></span>

### <a name="more-collections"></a><span data-ttu-id="856a3-387">更多集合</span><span class="sxs-lookup"><span data-stu-id="856a3-387">More collections</span></span>

<span data-ttu-id="856a3-388">还有很多其他可以使用的集合，但这些是正常的泛型数组替换。</span><span class="sxs-lookup"><span data-stu-id="856a3-388">There are many other collections that can be used but these are the good generic array replacements.</span></span>
<span data-ttu-id="856a3-389">如果有兴趣详细了解这些选项，请查看 [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) 总结的 [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c)。</span><span class="sxs-lookup"><span data-stu-id="856a3-389">If you're interested in learning about more of these options, take a look at this [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) that [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) put together.</span></span>

## <a name="other-nuances"></a><span data-ttu-id="856a3-390">其他细微差别</span><span class="sxs-lookup"><span data-stu-id="856a3-390">Other nuances</span></span>

<span data-ttu-id="856a3-391">现在，我已经介绍了所有主要功能，在结束本文之前，我还想介绍一些其他内容。</span><span class="sxs-lookup"><span data-stu-id="856a3-391">Now that I have covered all the major functionality, here are a few more things that I wanted to mention before I wrap this up.</span></span>

### <a name="pre-sized-arrays"></a><span data-ttu-id="856a3-392">预调整数组大小</span><span class="sxs-lookup"><span data-stu-id="856a3-392">Pre-sized arrays</span></span>

<span data-ttu-id="856a3-393">我提到过，数组一旦创建就不能更改它的大小。</span><span class="sxs-lookup"><span data-stu-id="856a3-393">I mentioned that you can't change the size of an array once it's created.</span></span> <span data-ttu-id="856a3-394">通过使用 `new($size)` 构造函数调用它，我们可以创建一个预先确定大小的数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-394">We can create an array of a pre-determined size by calling it with the `new($size)` constructor.</span></span>

```powershell
$data = [Object[]]::new(4)
$data.count
4
```

### <a name="multiplying-arrays"></a><span data-ttu-id="856a3-395">数组倍增</span><span class="sxs-lookup"><span data-stu-id="856a3-395">Multiplying arrays</span></span>

<span data-ttu-id="856a3-396">一个有趣的小技巧是你可以将数组与整数相乘。</span><span class="sxs-lookup"><span data-stu-id="856a3-396">An interesting little trick is that you can multiply an array by an integer.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data * 3
red
green
blue
red
green
blue
red
green
blue
```

### <a name="initialize-with-0"></a><span data-ttu-id="856a3-397">用 0 初始化</span><span class="sxs-lookup"><span data-stu-id="856a3-397">Initialize with 0</span></span>

<span data-ttu-id="856a3-398">一个常见的情况是，你想要创建一个全为零的数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-398">A common scenario is that you want to create an array with all zeros.</span></span> <span data-ttu-id="856a3-399">如果只打算包含整数，则强类型整数数组的默认值均为零。</span><span class="sxs-lookup"><span data-stu-id="856a3-399">If you're only going to have integers, a strongly typed array of integers defaults to all zeros.</span></span>

```powershell
PS> [int[]]::new(4)
0
0
0
0
```

<span data-ttu-id="856a3-400">我们也可以使用乘法技巧来实现这一点。</span><span class="sxs-lookup"><span data-stu-id="856a3-400">We can use the multiplying trick to do this too.</span></span>

```powershell
PS> $data = @(0) * 4
PS> $data
0
0
0
0
```

<span data-ttu-id="856a3-401">乘法的妙处在于可以使用任何值。</span><span class="sxs-lookup"><span data-stu-id="856a3-401">The nice thing about the multiplying trick is that you can use any value.</span></span> <span data-ttu-id="856a3-402">因此，如果你希望将 `255` 用作默认值，那么这是一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="856a3-402">So if you would rather have `255` as your default value, this would be a good way to do it.</span></span>

```powershell
PS> $data = @(255) * 4
PS> $data
255
255
255
255
```

### <a name="nested-arrays"></a><span data-ttu-id="856a3-403">嵌套数组</span><span class="sxs-lookup"><span data-stu-id="856a3-403">Nested arrays</span></span>

<span data-ttu-id="856a3-404">数组中的数组称为“嵌套数组”。</span><span class="sxs-lookup"><span data-stu-id="856a3-404">An array inside an array is called a nested array.</span></span> <span data-ttu-id="856a3-405">我在 PowerShell 中很少使用这些，在其他语言中用得更多。</span><span class="sxs-lookup"><span data-stu-id="856a3-405">I don't use these much in PowerShell but I have used them more in other languages.</span></span> <span data-ttu-id="856a3-406">当数据适合类似网格的模式时，请考虑使用数组的数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-406">Consider using an array of arrays when your data fits in a grid like pattern.</span></span>

<span data-ttu-id="856a3-407">可以通过两种方法创建二维数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-407">Here are two ways we can create a two-dimensional array.</span></span>

```powershell
$data = @(@(1,2,3),@(4,5,6),@(7,8,9))

$data2 = @(
    @(1,2,3),
    @(4,5,6),
    @(7,8,9)
)
```

<span data-ttu-id="856a3-408">在这些示例中，逗号非常重要。</span><span class="sxs-lookup"><span data-stu-id="856a3-408">The comma is very important in those examples.</span></span> <span data-ttu-id="856a3-409">我前面给出了一个多行普通数组的示例，其中的逗号是可选的。</span><span class="sxs-lookup"><span data-stu-id="856a3-409">I gave an earlier example of a normal array on multiple lines where the comma was optional.</span></span> <span data-ttu-id="856a3-410">多维数组则不是这样。</span><span class="sxs-lookup"><span data-stu-id="856a3-410">That isn't the case with a multi-dimensional array.</span></span>

<span data-ttu-id="856a3-411">现在，我们有了一个嵌套数组，使用索引表示法的方式会略有变化。</span><span class="sxs-lookup"><span data-stu-id="856a3-411">The way we use the index notation changes slightly now that we've a nested array.</span></span> <span data-ttu-id="856a3-412">使用上面的 `$data`，这就是我们访问值 3 的方式。</span><span class="sxs-lookup"><span data-stu-id="856a3-412">Using the `$data` above, this is how we would access the value 3.</span></span>

```powershell
PS> $outside = 0
PS> $inside = 2
PS> $data[$outside][$inside]
3
```

<span data-ttu-id="856a3-413">为每一级的数组嵌套添加一组方括号。</span><span class="sxs-lookup"><span data-stu-id="856a3-413">Add a set of bracket for each level of array nesting.</span></span> <span data-ttu-id="856a3-414">第一组方括号适用于最外层的数组，然后你可以从那里开始。</span><span class="sxs-lookup"><span data-stu-id="856a3-414">The first set of brackets is for the outer most array and then you work your way in from there.</span></span>

### <a name="write-output--noenumerate"></a><span data-ttu-id="856a3-415">Write-Output -NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="856a3-415">Write-Output -NoEnumerate</span></span>

<span data-ttu-id="856a3-416">PowerShell 倾向于展开或枚举数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-416">PowerShell likes to unwrap or enumerate arrays.</span></span> <span data-ttu-id="856a3-417">这是 PowerShell 使用管道的核心环节，但有时你并不希望这么做。</span><span class="sxs-lookup"><span data-stu-id="856a3-417">This is a core aspect of the way PowerShell uses the pipeline but there are times that you don't want that to happen.</span></span>

<span data-ttu-id="856a3-418">我通常会通过管道将对象传递给 `Get-Member` 来了解关于它们的更多信息。</span><span class="sxs-lookup"><span data-stu-id="856a3-418">I commonly pipe objects to `Get-Member` to learn more about them.</span></span> <span data-ttu-id="856a3-419">当我向其传递一个数组时，数组将展开，Get-Member 将看到数组的成员而不是实际的数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-419">When I pipe an array to it, it gets unwrapped and Get-Member sees the members of the array and not the actual array.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data | Get-Member
TypeName: System.String
...
```

<span data-ttu-id="856a3-420">若要防止数组展开，可以使用 `Write-Object -NoEnumerate`。</span><span class="sxs-lookup"><span data-stu-id="856a3-420">To prevent that unwrap of the array, you can use `Write-Object -NoEnumerate`.</span></span>

```powershell
PS> Write-Output -NoEnumerate $data | Get-Member
TypeName: System.Object[]
...
```

<span data-ttu-id="856a3-421">我的第二种方法更像是黑客行为（我会尽量避免这类行为）。</span><span class="sxs-lookup"><span data-stu-id="856a3-421">I have a second way that's more of a hack (and I try to avoid hacks like this).</span></span> <span data-ttu-id="856a3-422">在用管道传输之前，可以在数组前面放一个逗号。</span><span class="sxs-lookup"><span data-stu-id="856a3-422">You can place a comma in front of the array before you pipe it.</span></span>

```powershell
PS> ,$data | Get-Member
TypeName: System.Object[]
...
```

### <a name="return-an-array"></a><span data-ttu-id="856a3-423">返回数组</span><span class="sxs-lookup"><span data-stu-id="856a3-423">Return an array</span></span>

<span data-ttu-id="856a3-424">当从函数输出或返回值时，也会发生这种数组展开的情况。</span><span class="sxs-lookup"><span data-stu-id="856a3-424">This unwrapping of arrays also happens when you output or return values from a function.</span></span> <span data-ttu-id="856a3-425">如果将输出分配给变量，则仍可获取一个数组，所以这通常不是问题。</span><span class="sxs-lookup"><span data-stu-id="856a3-425">You can still get an array if you assign the output to a variable so this isn't commonly an issue.</span></span>

<span data-ttu-id="856a3-426">问题是你有了一个新数组。</span><span class="sxs-lookup"><span data-stu-id="856a3-426">The catch is that you have a new array.</span></span> <span data-ttu-id="856a3-427">如果出现这个问题，可以使用 `Write-Output -NoEnumerate $array` 或 `return ,$array` 来解决。</span><span class="sxs-lookup"><span data-stu-id="856a3-427">If that is ever a problem, you can use `Write-Output -NoEnumerate $array` or `return ,$array` to work around it.</span></span>

## <a name="anything-else"></a><span data-ttu-id="856a3-428">任何其他内容？</span><span class="sxs-lookup"><span data-stu-id="856a3-428">Anything else?</span></span>

<span data-ttu-id="856a3-429">我知道所有这些都是需要消化吸收的。</span><span class="sxs-lookup"><span data-stu-id="856a3-429">I know this is all a lot to take in.</span></span> <span data-ttu-id="856a3-430">希望你每次阅读本文时都能有所收获，并在未来一段时间内把它作为一项有价值的参考资料。</span><span class="sxs-lookup"><span data-stu-id="856a3-430">My hope is that you learn something from this article every time you read it and that it turns out to be a good reference for you for a long time to come.</span></span> <span data-ttu-id="856a3-431">如果你认为本文有用，请把它分享给你认为可能会从中获益的其他人。</span><span class="sxs-lookup"><span data-stu-id="856a3-431">If you found this to be helpful, please share it with others you think may get value out of it.</span></span>

<span data-ttu-id="856a3-432">在这里，我建议你查看我写的一篇类似的关于[哈希表][]的文章。</span><span class="sxs-lookup"><span data-stu-id="856a3-432">From here, I would recommend you check out a similar post that I wrote about [hashtables][].</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[数组]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[switch 语句]: everything-about-switch.md
[switch statement]: everything-about-switch.md
[哈希表]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
[使用正则表达式的多种方式]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[如何验证数组中的每个值是否与给定值匹配]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[how to verify that every value in an array matches a given value]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[解决方案]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[solution]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[StringBuilder]: https://powershellexplained.com/2017-11-20-Powershell-StringBuilder/
