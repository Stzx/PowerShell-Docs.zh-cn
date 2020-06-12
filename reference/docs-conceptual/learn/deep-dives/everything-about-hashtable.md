---
title: 关于哈希表的各项须知内容
description: 哈希表在 PowerShell 中非常重要，因此最好对它们进行全面的了解。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 336c32cca351cc7d87f3300364c075ba7bd8aaeb
ms.sourcegitcommit: 0b9268e7b92fb76b47169b72e28de43e4bfe7fbf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307123"
---
# <a name="everything-you-wanted-to-know-about-hashtables"></a><span data-ttu-id="3cc03-103">关于哈希表的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="3cc03-103">Everything you wanted to know about hashtables</span></span>

<span data-ttu-id="3cc03-104">我想退后一步来讲讲[哈希表][]。</span><span class="sxs-lookup"><span data-stu-id="3cc03-104">I want to take a step back and talk about [hashtables][].</span></span> <span data-ttu-id="3cc03-105">我现在一直在用它们。</span><span class="sxs-lookup"><span data-stu-id="3cc03-105">I use them all the time now.</span></span> <span data-ttu-id="3cc03-106">在昨晚的用户组会议后，我给一个人教了哈希表的知识，我发现他现在对哈希表的困惑正是我以前经历过的。</span><span class="sxs-lookup"><span data-stu-id="3cc03-106">I was teaching someone about them after our user group meeting last night and I realized I had the same confusion about them as he had.</span></span> <span data-ttu-id="3cc03-107">哈希表在 PowerShell 中非常重要，因此最好对它们进行全面的了解。</span><span class="sxs-lookup"><span data-stu-id="3cc03-107">Hashtables are really important in PowerShell so it's good to have a solid understanding of them.</span></span>

> [!NOTE]
> <span data-ttu-id="3cc03-108">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="3cc03-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="3cc03-109">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="3cc03-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="3cc03-110">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="3cc03-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="hashtable-as-a-collection-of-things"></a><span data-ttu-id="3cc03-111">哈希表是一个项的集合</span><span class="sxs-lookup"><span data-stu-id="3cc03-111">Hashtable as a collection of things</span></span>

<span data-ttu-id="3cc03-112">首先，从哈希表的传统定义来说，我希望你将哈希表视为一个集合。</span><span class="sxs-lookup"><span data-stu-id="3cc03-112">I want you to first see a **Hashtable** as a collection in the traditional definition of a hashtable.</span></span> <span data-ttu-id="3cc03-113">此定义使你在以后将它们用于更高级的内容时对其工作原理有一个基本了解。</span><span class="sxs-lookup"><span data-stu-id="3cc03-113">This definition gives you a fundamental understanding of how they work when they get used for more advanced stuff later.</span></span> <span data-ttu-id="3cc03-114">缺乏这种了解通常是产生困惑的根源。</span><span class="sxs-lookup"><span data-stu-id="3cc03-114">Skipping this understanding is often a source of confusion.</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="3cc03-115">什么是数组？</span><span class="sxs-lookup"><span data-stu-id="3cc03-115">What is an array?</span></span>

<span data-ttu-id="3cc03-116">在开始介绍哈希表之前，我需要首先介绍一下[数组][]。</span><span class="sxs-lookup"><span data-stu-id="3cc03-116">Before I jump into what a **Hashtable** is, I need to mention [arrays][] first.</span></span> <span data-ttu-id="3cc03-117">在本讨论中，数组是值或对象的列表或集合。</span><span class="sxs-lookup"><span data-stu-id="3cc03-117">For the purpose of this discussion, an array is a list or collection of values or objects.</span></span>

```powershell
$array = @(1,2,3,5,7,11)
```

<span data-ttu-id="3cc03-118">将项放入数组后，可以使用 `foreach` 来循环访问该列表，或者使用索引访问数组中的各个元素。</span><span class="sxs-lookup"><span data-stu-id="3cc03-118">Once you have your items into an array, you can either use `foreach` to iterate over the list or use an index to access individual elements in the array.</span></span>

```powershell
foreach($item in $array)
{
    Write-Output $item
}

Write-Output $array[3]
```

<span data-ttu-id="3cc03-119">还可以使用索引以相同方式更新值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-119">You can also update values using an index in the same way.</span></span>

```powershell
$array[2] = 13
```

<span data-ttu-id="3cc03-120">刚刚只是介绍了数组的一点皮毛，但在继续介绍哈希表之前，这是必备的背景知识。</span><span class="sxs-lookup"><span data-stu-id="3cc03-120">I just scratched the surface on arrays but that should put them into the right context as I move onto hashtables.</span></span>

## <a name="what-is-a-hashtable"></a><span data-ttu-id="3cc03-121">什么是哈希表？</span><span class="sxs-lookup"><span data-stu-id="3cc03-121">What is a hashtable?</span></span>

<span data-ttu-id="3cc03-122">在介绍 PowerShell 使用哈希表的其他方式之前，我将首先介绍一般意义上哈希表的基本技术描述。</span><span class="sxs-lookup"><span data-stu-id="3cc03-122">I'm going to start with a basic technical description of what hashtables are, in the general sense, before I shift into the other ways PowerShell uses them.</span></span>

<span data-ttu-id="3cc03-123">哈希表是一种数据结构，与数组非常相似，只不过是使用键存储每个值（对象）。</span><span class="sxs-lookup"><span data-stu-id="3cc03-123">A hashtable is a data structure, much like an array, except you store each value (object) using a key.</span></span> <span data-ttu-id="3cc03-124">它是一个基本的键/值存储。</span><span class="sxs-lookup"><span data-stu-id="3cc03-124">It's a basic key/value store.</span></span> <span data-ttu-id="3cc03-125">首先，我们创建一个空哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-125">First, we create an empty hashtable.</span></span>

```powershell
$ageList = @{}
```

<span data-ttu-id="3cc03-126">请注意，使用大括号（而不是括号）定义哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-126">Notice that braces, instead of parentheses, are used to define a hashtable.</span></span> <span data-ttu-id="3cc03-127">然后，使用如下所示的键添加项：</span><span class="sxs-lookup"><span data-stu-id="3cc03-127">Then we add an item using a key like this:</span></span>

```powershell
$key = 'Kevin'
$value = 36
$ageList.add( $key, $value )

$ageList.add( 'Alex', 9 )
```

<span data-ttu-id="3cc03-128">人员的名称为键，其年龄是我想要保存的值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-128">The person's name is the key and their age is the value that I want to save.</span></span>

## <a name="using-the-brackets-for-access"></a><span data-ttu-id="3cc03-129">使用括号进行访问</span><span class="sxs-lookup"><span data-stu-id="3cc03-129">Using the brackets for access</span></span>

<span data-ttu-id="3cc03-130">将值添加到哈希表后，可以使用相同的键（而不是使用数字索引，就像对数组使用的一样）取回这些值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-130">Once you add your values to the hashtable, you can pull them back out using that same key (instead of using a numeric index like you would have for an array).</span></span>

```powershell
$ageList['Kevin']
$ageList['Alex']
```

<span data-ttu-id="3cc03-131">如果需要 Kevin 的年龄，我会使用其名称进行访问。</span><span class="sxs-lookup"><span data-stu-id="3cc03-131">When I want Kevin's age, I use his name to access it.</span></span> <span data-ttu-id="3cc03-132">我们也可以使用此方法将值添加或更新到哈希表中。</span><span class="sxs-lookup"><span data-stu-id="3cc03-132">We can use this approach to add or update values into the hashtable too.</span></span> <span data-ttu-id="3cc03-133">这与使用上述 `add()` 函数相同。</span><span class="sxs-lookup"><span data-stu-id="3cc03-133">This is just like using the `add()` function above.</span></span>

```powershell
$ageList = @{}

$key = 'Kevin'
$value = 36
$ageList[$key] = $value

$ageList['Alex'] = 9
```

<span data-ttu-id="3cc03-134">你可以使用另一个语法来访问和更新将在后面部分中介绍的值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-134">There's another syntax you can use for accessing and updating values that I'll cover in a later section.</span></span> <span data-ttu-id="3cc03-135">如果从另一种语言转到 PowerShell，这些示例应与你之前使用哈希表的方式相符。</span><span class="sxs-lookup"><span data-stu-id="3cc03-135">If you're coming to PowerShell from another language, these examples should fit in with how you may have used hashtables before.</span></span>

### <a name="creating-hashtables-with-values"></a><span data-ttu-id="3cc03-136">用值创建哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-136">Creating hashtables with values</span></span>

<span data-ttu-id="3cc03-137">到目前为止，我已经为这些示例创建了一个空哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-137">So far I've created an empty hashtable for these examples.</span></span> <span data-ttu-id="3cc03-138">你可以在创建键和值时预先填充它们。</span><span class="sxs-lookup"><span data-stu-id="3cc03-138">You can pre-populate the keys and values when you create them.</span></span>

```powershell
$ageList = @{
    Kevin = 36
    Alex  = 9
}
```

### <a name="as-a-lookup-table"></a><span data-ttu-id="3cc03-139">作为查找表</span><span class="sxs-lookup"><span data-stu-id="3cc03-139">As a lookup table</span></span>

<span data-ttu-id="3cc03-140">此类型的哈希表的实际值可用作查找表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-140">The real value of this type of a hashtable is that you can use them as a lookup table.</span></span> <span data-ttu-id="3cc03-141">下面是一个简单的示例。</span><span class="sxs-lookup"><span data-stu-id="3cc03-141">Here is a simple example.</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}

$server = $environments[$env]
```

<span data-ttu-id="3cc03-142">在此示例中，将为 `$env` 变量指定环境，它会选择正确的服务器。</span><span class="sxs-lookup"><span data-stu-id="3cc03-142">In this example, you specify an environment for the `$env` variable and it will pick the correct server.</span></span> <span data-ttu-id="3cc03-143">你可以使用 `switch($env){...}` 来实现这样的选择，但哈希表是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="3cc03-143">You could use a `switch($env){...}` for a selection like this but a hashtable is a nice option.</span></span>

<span data-ttu-id="3cc03-144">当你动态构建查找表以供以后使用时，这样会更好。</span><span class="sxs-lookup"><span data-stu-id="3cc03-144">This gets even better when you dynamically build the lookup table to use it later.</span></span> <span data-ttu-id="3cc03-145">因此，当你需要交叉引用内容时，请考虑使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-145">So think about using this approach when you need to cross reference something.</span></span> <span data-ttu-id="3cc03-146">我发现，如果 PowerShell 使用 `Where-Object` 在管道上进行筛选时表现不太好，就会出现更多这种情况。</span><span class="sxs-lookup"><span data-stu-id="3cc03-146">I think we would see this even more if PowerShell wasn't so good at filtering on the pipe with `Where-Object`.</span></span> <span data-ttu-id="3cc03-147">如果遇到性能问题，则需要考虑使用此方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-147">If you're ever in a situation where performance matters, this approach needs to be considered.</span></span>

<span data-ttu-id="3cc03-148">我不会说它速度更快，但它符合一条原则：[如果性能很重要，请对其进行测试][]。</span><span class="sxs-lookup"><span data-stu-id="3cc03-148">I won't say that it's faster, but it does fit into the rule of [If performance matters, test it][].</span></span>

#### <a name="multiselection"></a><span data-ttu-id="3cc03-149">多选</span><span class="sxs-lookup"><span data-stu-id="3cc03-149">Multiselection</span></span>

<span data-ttu-id="3cc03-150">通常，可以将哈希表视为键/值对，其中提供一个键并获得一个值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-150">Generally, you think of a hashtable as a key/value pair, where you provide one key and get one value.</span></span> <span data-ttu-id="3cc03-151">PowerShell 允许提供一组键来获取多个值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-151">PowerShell allows you to provide an array of keys to get multiple values.</span></span>

```powershell
$environments[@('QA','DEV')]
$environments[('QA','DEV')]
$environments['QA','DEV']
```

<span data-ttu-id="3cc03-152">在此示例中，我使用与上述相同的查找哈希表，并提供三个不同的数组样式来获取匹配项。</span><span class="sxs-lookup"><span data-stu-id="3cc03-152">In this example, I use the same lookup hashtable from above and provide three different array styles to get the matches.</span></span> <span data-ttu-id="3cc03-153">这是 PowerShell 中的隐藏 gem，大多数人都不知道。</span><span class="sxs-lookup"><span data-stu-id="3cc03-153">This is a hidden gem in PowerShell that most people aren't aware of.</span></span>

## <a name="iterating-hashtables"></a><span data-ttu-id="3cc03-154">循环访问哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-154">Iterating hashtables</span></span>

<span data-ttu-id="3cc03-155">由于哈希表是键/值对的集合，因此，对其进行循环访问的方式与对数组或普通项列表的方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="3cc03-155">Because a hashtable is a collection of key/value pairs, you iterate over it differently than you do for an array or a normal list of items.</span></span>

<span data-ttu-id="3cc03-156">首先要注意的是，如果你使用管道传输哈希表，管道会将其视为一个对象，</span><span class="sxs-lookup"><span data-stu-id="3cc03-156">The first thing to notice is that if you pipe your hashtable, the pipe treats it like one object.</span></span>

```powershell
PS> $ageList | Measure-Object
count : 1
```

<span data-ttu-id="3cc03-157">不管 `.count` 属性告诉你它包含多少个值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-157">Even though the `.count` property tells you how many values it contains.</span></span>

```powershell
PS> $ageList.count
2
```

<span data-ttu-id="3cc03-158">如果只是需要值，可以使用 `.values` 属性来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="3cc03-158">You get around this issue by using the `.values` property if all you need is just the values.</span></span>

```powershell
PS> $ageList.values | Measure-Object -Average
Count   : 2
Average : 22.5
```

<span data-ttu-id="3cc03-159">枚举键并使用它们来访问值通常更有用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-159">It's often more useful to enumerate the keys and use them to access the values.</span></span>

```powershell
PS> $ageList.keys | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_, $ageList[$_]
    Write-Output $message
}
Kevin is 36 years old
Alex is 9 years old
```

<span data-ttu-id="3cc03-160">下面是同一个含有 `foreach(){...}` 循环的示例。</span><span class="sxs-lookup"><span data-stu-id="3cc03-160">Here is the same example with a `foreach(){...}` loop.</span></span>

```powershell
foreach($key in $ageList.keys)
{
    $message = '{0} is {1} years old' -f $key, $ageList[$key]
    Write-Output $message
}
```

<span data-ttu-id="3cc03-161">我们正在遍历哈希表中的每个键，然后使用它来访问值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-161">We are walking each key in the hashtable and then using it to access the value.</span></span> <span data-ttu-id="3cc03-162">当使用哈希表作为集合时，这是一种常见模式。</span><span class="sxs-lookup"><span data-stu-id="3cc03-162">This is a common pattern when working with hashtables as a collection.</span></span>

### <a name="getenumerator"></a><span data-ttu-id="3cc03-163">GetEnumerator()</span><span class="sxs-lookup"><span data-stu-id="3cc03-163">GetEnumerator()</span></span>

<span data-ttu-id="3cc03-164">接下来，我们将使用 `GetEnumerator()` 来循环访问哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-164">That brings us to `GetEnumerator()` for iterating over our hashtable.</span></span>

```powershell
$ageList.GetEnumerator() | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_.key, $_.value
    Write-Output $message
}
```

<span data-ttu-id="3cc03-165">枚举器依次为你提供每个键/值对。</span><span class="sxs-lookup"><span data-stu-id="3cc03-165">The enumerator gives you each key/value pair one after another.</span></span> <span data-ttu-id="3cc03-166">它专为此用例而设计。</span><span class="sxs-lookup"><span data-stu-id="3cc03-166">It was designed specifically for this use case.</span></span> <span data-ttu-id="3cc03-167">感谢 [Mark Kraus](https://get-PowerShellblog.blogspot.com) 提醒我这一点。</span><span class="sxs-lookup"><span data-stu-id="3cc03-167">Thank you to [Mark Kraus](https://get-PowerShellblog.blogspot.com) for reminding me of this one.</span></span>

### <a name="badenumeration"></a><span data-ttu-id="3cc03-168">BadEnumeration</span><span class="sxs-lookup"><span data-stu-id="3cc03-168">BadEnumeration</span></span>

<span data-ttu-id="3cc03-169">一个重要的细节是，在枚举哈希表时，无法进行修改。</span><span class="sxs-lookup"><span data-stu-id="3cc03-169">One important detail is that you can't modify a hashtable while it's being enumerated.</span></span> <span data-ttu-id="3cc03-170">如果我们从基本的 `$environments` 示例开始：</span><span class="sxs-lookup"><span data-stu-id="3cc03-170">If we start with our basic `$environments` example:</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}
```

<span data-ttu-id="3cc03-171">尝试将每个键设置为相同的服务器值失败。</span><span class="sxs-lookup"><span data-stu-id="3cc03-171">And trying to set every key to the same server value fails.</span></span>

```powershell
$environments.Keys | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}

An error occurred while enumerating through a collection: Collection was modified; enumeration operation may not execute.
+ CategoryInfo          : InvalidOperation: tableEnumerator:HashtableEnumerator) [], RuntimeException
+ FullyQualifiedErrorId : BadEnumeration
```

<span data-ttu-id="3cc03-172">这样也会失败，即使它看起来也应该很正常：</span><span class="sxs-lookup"><span data-stu-id="3cc03-172">This will also fail even though it looks like it should also be fine:</span></span>

```powershell
foreach($key in $environments.keys) {
    $environments[$key] = 'SrvDev03'
}

Collection was modified; enumeration operation may not execute.
    + CategoryInfo          : OperationStopped: (:) [], InvalidOperationException
    + FullyQualifiedErrorId : System.InvalidOperationException
```

<span data-ttu-id="3cc03-173">应对这种情况的技巧是在执行枚举之前克隆键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-173">The trick to this situation is to clone the keys before doing the enumeration.</span></span>

```powershell
$environments.Keys.Clone() | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}
```

## <a name="hashtable-as-a-collection-of-properties"></a><span data-ttu-id="3cc03-174">作为属性集合的哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-174">Hashtable as a collection of properties</span></span>

<span data-ttu-id="3cc03-175">到目前为止，我们在哈希表中放置的对象类型都属于相同的对象类型。</span><span class="sxs-lookup"><span data-stu-id="3cc03-175">So far the type of objects we placed in our hashtable were all the same type of object.</span></span> <span data-ttu-id="3cc03-176">我在所有这些示例中使用的是年龄，键是人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="3cc03-176">I used ages in all those examples and the key was the person's name.</span></span> <span data-ttu-id="3cc03-177">如果每个对象集合都有一个名称，这是一个查看它的好方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-177">This is a great way to look at it when your collection of objects each have a name.</span></span> <span data-ttu-id="3cc03-178">在 PowerShell 中使用哈希表的另一种常见方法是保存属性集合，其中键是属性名称。</span><span class="sxs-lookup"><span data-stu-id="3cc03-178">Another common way to use hashtables in PowerShell is to hold a collection of properties where the key is the name of the property.</span></span> <span data-ttu-id="3cc03-179">在下一个示例中，我将深入探讨这一方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-179">I'll step into that idea in this next example.</span></span>

### <a name="property-based-access"></a><span data-ttu-id="3cc03-180">基于属性的访问</span><span class="sxs-lookup"><span data-stu-id="3cc03-180">Property-based access</span></span>

<span data-ttu-id="3cc03-181">使用基于属性的访问会更改哈希表的动态，以及其在 PowerShell 中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="3cc03-181">The use of property-based access changes the dynamics of hashtables and how you can use them in PowerShell.</span></span> <span data-ttu-id="3cc03-182">这是我们在上面常见的例子，在其中键被视为属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-182">Here is our usual example from above treating the keys as properties.</span></span>

```powershell
$ageList = @{}
$ageList.Kevin = 35
$ageList.Alex = 9
```

<span data-ttu-id="3cc03-183">正如上面的例子所示，如果哈希表中不存在这些键，则此示例将添加这些键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-183">Just like the examples above, this example adds those keys if they don't exist in the hashtable already.</span></span> <span data-ttu-id="3cc03-184">根据你定义键的方式以及你的值，这可能有点奇怪，也可能完全合适。</span><span class="sxs-lookup"><span data-stu-id="3cc03-184">Depending on how you defined your keys and what your values are, this is either a little strange or a perfect fit.</span></span> <span data-ttu-id="3cc03-185">在此之前，年龄列表示例运行良好。</span><span class="sxs-lookup"><span data-stu-id="3cc03-185">The age list example has worked great up until this point.</span></span> <span data-ttu-id="3cc03-186">为此，我们需要一个新的示例，以供今后使用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-186">We need a new example for this to feel right going forward.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="3cc03-187">我们可以像这样在 `$person` 上添加和访问属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-187">And we can add and access attributes on the `$person` like this.</span></span>

```powershell
$person.city = 'Austin'
$person.state = 'TX'
```

<span data-ttu-id="3cc03-188">此哈希表的外观和行为突然变得与对象一样。</span><span class="sxs-lookup"><span data-stu-id="3cc03-188">All of a sudden this hashtable starts to feel and act like an object.</span></span> <span data-ttu-id="3cc03-189">它仍是项的集合，因此以上所有示例仍适用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-189">It's still a collection of things, so all the examples above still apply.</span></span> <span data-ttu-id="3cc03-190">我们只是从不同的角度来看。</span><span class="sxs-lookup"><span data-stu-id="3cc03-190">We just approach it from a different point of view.</span></span>

### <a name="checking-for-keys-and-values"></a><span data-ttu-id="3cc03-191">检查键和值</span><span class="sxs-lookup"><span data-stu-id="3cc03-191">Checking for keys and values</span></span>

<span data-ttu-id="3cc03-192">在大多数情况下，只需按如下所示测试值：</span><span class="sxs-lookup"><span data-stu-id="3cc03-192">In most cases, you can just test for the value with something like this:</span></span>

```powershell
if( $person.age ){...}
```

<span data-ttu-id="3cc03-193">这很简单，但由于我在逻辑中忽视了一个重要的细节，所以我曾遇到过很多 bug。</span><span class="sxs-lookup"><span data-stu-id="3cc03-193">It's simple but has been the source of many bugs for me because I was overlooking one important detail in my logic.</span></span> <span data-ttu-id="3cc03-194">我开始使用它来测试键是否存在。</span><span class="sxs-lookup"><span data-stu-id="3cc03-194">I started to use it to test if a key was present.</span></span> <span data-ttu-id="3cc03-195">如果值为 `$false` 或零，则该语句将意外返回 `$false`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-195">When the value was `$false` or zero, that statement would return `$false` unexpectedly.</span></span>

```powershell
if( $person.age -ne $null ){...}
```

<span data-ttu-id="3cc03-196">这会解决此零值问题，但不能解决 $null 与键不存在的问题。</span><span class="sxs-lookup"><span data-stu-id="3cc03-196">This works around that issue for zero values but not $null vs non-existent keys.</span></span> <span data-ttu-id="3cc03-197">大多数情况不需要进行这种区分，但当你这么做时会提供一些函数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-197">Most of the time you don't need to make that distinction but there are functions for when you do.</span></span>

```powershell
if( $person.ContainsKey('age') ){...}
```

<span data-ttu-id="3cc03-198">对于需要在不知道键或循环访问整个集合的情况下测试值的情况，还有一个 `ContainsValue()`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-198">We also have a `ContainsValue()` for the situation where you need to test for a value without knowing the key or iterating the whole collection.</span></span>

### <a name="removing-and-clearing-keys"></a><span data-ttu-id="3cc03-199">删除和清除键</span><span class="sxs-lookup"><span data-stu-id="3cc03-199">Removing and clearing keys</span></span>

<span data-ttu-id="3cc03-200">可以使用 `.Remove()` 函数删除键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-200">You can remove keys with the `.Remove()` function.</span></span>

```powershell
$person.remove('age')
```

<span data-ttu-id="3cc03-201">向它们分配 `$null` 值后，你将拥有一个具有 `$null` 值的键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-201">Assigning them a `$null` value just leaves you with a key that has a `$null` value.</span></span>

<span data-ttu-id="3cc03-202">清除哈希表的常用方法是将其初始化为空哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-202">A common way to clear a hashtable is to just initialize it to an empty hashtable.</span></span>

```powershell
$person = @{}
```

<span data-ttu-id="3cc03-203">虽然这样做确实有用，但请尝试改用 `clear()` 函数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-203">While that does work, try to use the `clear()` function instead.</span></span>

```powershell
$person.clear()
```

<span data-ttu-id="3cc03-204">这是使用该函数创建自文档化代码的实例之一，它使代码的意图非常清晰。</span><span class="sxs-lookup"><span data-stu-id="3cc03-204">This is one of those instances where using the function creates self-documenting code and it makes the intentions of the code very clean.</span></span>

## <a name="all-the-fun-stuff"></a><span data-ttu-id="3cc03-205">所有趣味内容</span><span class="sxs-lookup"><span data-stu-id="3cc03-205">All the fun stuff</span></span>

### <a name="ordered-hashtables"></a><span data-ttu-id="3cc03-206">排序哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-206">Ordered hashtables</span></span>

<span data-ttu-id="3cc03-207">默认情况下，哈希表不进行排序（或排列）。</span><span class="sxs-lookup"><span data-stu-id="3cc03-207">By default, hashtables aren't ordered (or sorted).</span></span> <span data-ttu-id="3cc03-208">在传统的上下文中，当你始终使用键来访问值时，顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="3cc03-208">In the traditional context, the order doesn't matter when you always use a key to access values.</span></span> <span data-ttu-id="3cc03-209">你可能会发现，你希望属性按你定义的顺序保持不变。</span><span class="sxs-lookup"><span data-stu-id="3cc03-209">You may find that you want the properties to stay in the order that you define them.</span></span> <span data-ttu-id="3cc03-210">令人欣慰的是，有一种方法可以使用 `ordered` 关键字实现此目的。</span><span class="sxs-lookup"><span data-stu-id="3cc03-210">Thankfully, there's a way to do that with the `ordered` keyword.</span></span>

```powershell
$person = [ordered]@{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="3cc03-211">现在，当你枚举键和值时，它们会保持该顺序。</span><span class="sxs-lookup"><span data-stu-id="3cc03-211">Now when you enumerate the keys and values, they stay in that order.</span></span>

### <a name="inline-hashtables"></a><span data-ttu-id="3cc03-212">内联哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-212">Inline hashtables</span></span>

<span data-ttu-id="3cc03-213">在一行上定义哈希表时，可以用分号分隔键/值对。</span><span class="sxs-lookup"><span data-stu-id="3cc03-213">When you're defining a hashtable on one line, you can separate the key/value pairs with a semicolon.</span></span>

```powershell
$person = @{ name = 'kevin'; age = 36; }
```

<span data-ttu-id="3cc03-214">如果要在管道上创建它们，这会很方便。</span><span class="sxs-lookup"><span data-stu-id="3cc03-214">This will come in handy if you're creating them on the pipe.</span></span>

### <a name="custom-expressions-in-common-pipeline-commands"></a><span data-ttu-id="3cc03-215">常见管道命令中的自定义表达式</span><span class="sxs-lookup"><span data-stu-id="3cc03-215">Custom expressions in common pipeline commands</span></span>

<span data-ttu-id="3cc03-216">有一些 cmdlet 支持使用哈希表创建自定义属性或计算属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-216">There are a few cmdlets that support the use of hashtables to create custom or calculated properties.</span></span> <span data-ttu-id="3cc03-217">通常为 `Select-Object` 和 `Format-Table`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-217">You commonly see this with `Select-Object` and `Format-Table`.</span></span> <span data-ttu-id="3cc03-218">当哈希表完全展开时，将具有一种特殊的语法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-218">The hashtables have a special syntax that looks like this when fully expanded.</span></span>

```powershell
$property = @{
    name = 'totalSpaceGB'
    expression = { ($_.used + $_.free) / 1GB }
}
```

<span data-ttu-id="3cc03-219">该 cmdlet 会将此列标记为 `name`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-219">The `name` is what the cmdlet would label that column.</span></span> <span data-ttu-id="3cc03-220">`expression` 是一个脚本块，它在当 `$_` 是管道上对象的值时执行。</span><span class="sxs-lookup"><span data-stu-id="3cc03-220">The `expression` is a script block that is executed where `$_` is the value of the object on the pipe.</span></span> <span data-ttu-id="3cc03-221">下面是运行的脚本：</span><span class="sxs-lookup"><span data-stu-id="3cc03-221">Here is that script in action:</span></span>

```powershell
$drives = Get-PSDrive | Where Used
$drives | Select-Object -Properties name, $property

Name     totalSpaceGB
----     ------------
C    238.472652435303
```

<span data-ttu-id="3cc03-222">我将它放在一个变量中，但可以轻松地将其定义为内联，并且你可以将 `name` 缩写为 `n`，将 `expression` 缩写为 `e`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-222">I placed that in a variable but it could easily be defined inline and you can shorten `name` to `n` and `expression` to `e` while you're at it.</span></span>

```powershell
$drives | Select-Object -properties name, @{n='totalSpaceGB';e={($_.used + $_.free) / 1GB}}
```

<span data-ttu-id="3cc03-223">就我个人而言，我不喜欢命令执行的时间太长，而且它经常会引发一些我不会涉及的不良行为。</span><span class="sxs-lookup"><span data-stu-id="3cc03-223">I personally don't like how long that makes commands and it often promotes some bad behaviors that I won't get into.</span></span> <span data-ttu-id="3cc03-224">我更有可能使用所需的所有字段和属性创建新的哈希表或 `pscustomobject`，而不是在脚本中使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-224">I'm more likely to create a new hashtable or `pscustomobject` with all the fields and properties that I want instead of using this approach in scripts.</span></span> <span data-ttu-id="3cc03-225">但有很多代码可以做到这一点，因此我希望你能了解。</span><span class="sxs-lookup"><span data-stu-id="3cc03-225">But there's a lot of code out there that does this so I wanted you to be aware of it.</span></span> <span data-ttu-id="3cc03-226">稍后我会讨论如何创建 `pscustomobject`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-226">I talk about creating a `pscustomobject` later on.</span></span>

### <a name="custom-sort-expression"></a><span data-ttu-id="3cc03-227">自定义排序表达式</span><span class="sxs-lookup"><span data-stu-id="3cc03-227">Custom sort expression</span></span>

<span data-ttu-id="3cc03-228">如果对象具有要排序的数据，则可以很容易地对集合进行排序。</span><span class="sxs-lookup"><span data-stu-id="3cc03-228">It's easy to sort a collection if the objects have the data that you want to sort on.</span></span> <span data-ttu-id="3cc03-229">可以在给对象排序之前将数据添加到对象，也可以为 `Sort-Object` 创建自定义表达式。</span><span class="sxs-lookup"><span data-stu-id="3cc03-229">You can either add the data to the object before you sort it or create a custom expression for `Sort-Object`.</span></span>

```powershell
Get-ADUser | Sort-Object -Parameter @{ e={ Get-TotalSales $_.Name } }
```

<span data-ttu-id="3cc03-230">在此示例中，我将使用一个用户列表，并使用一些自定义 cmdlet 获取更多有关排序的信息。</span><span class="sxs-lookup"><span data-stu-id="3cc03-230">In this example I'm taking a list of users and using some custom cmdlet to get additional information just for the sort.</span></span>

#### <a name="sort-a-list-of-hashtables"></a><span data-ttu-id="3cc03-231">对哈希表列表排序</span><span class="sxs-lookup"><span data-stu-id="3cc03-231">Sort a list of Hashtables</span></span>

<span data-ttu-id="3cc03-232">如果你有想要排序的哈希表列表，你会发现 `Sort-Object` 不会将你的键视为属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-232">If you have a list of hashtables that you want to sort, you'll find that the `Sort-Object` doesn't treat your keys as properties.</span></span> <span data-ttu-id="3cc03-233">我们可以通过使用自定义排序表达式来实现舍入。</span><span class="sxs-lookup"><span data-stu-id="3cc03-233">We can get a round that by using a custom sort expression.</span></span>

```powershell
$data = @(
    @{name='a'}
    @{name='c'}
    @{name='e'}
    @{name='f'}
    @{name='d'}
    @{name='b'}
)

$data | Sort-Object -Property @{e={$_.name}}
```

## <a name="splatting-hashtables-at-cmdlets"></a><span data-ttu-id="3cc03-234">在执行 cmdlet 时展开哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-234">Splatting hashtables at cmdlets</span></span>

<span data-ttu-id="3cc03-235">关于哈希表这是我最喜欢的一点，很多人以前都没有发现。</span><span class="sxs-lookup"><span data-stu-id="3cc03-235">This is one of my favorite things about hashtables that many people don't discover early on.</span></span>
<span data-ttu-id="3cc03-236">其思路是，无需在一行上向 cmdlet 提供所有属性，而是先将它们打包为一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-236">The idea is that instead of providing all the properties to a cmdlet on one line, you can instead pack them into a hashtable first.</span></span> <span data-ttu-id="3cc03-237">然后，你可以通过一种特殊方式向该函数分配哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-237">Then you can give the hashtable to the function in a special way.</span></span>
<span data-ttu-id="3cc03-238">下面是以常规方式创建 DHCP 作用域的示例。</span><span class="sxs-lookup"><span data-stu-id="3cc03-238">Here is an example of creating a DHCP scope the normal way.</span></span>

```powershell
Add-DhcpServerv4Scope -Name 'TestNetwork' -StartRange'10.0.0.2' -EndRange '10.0.0.254' -SubnetMask '255.255.255.0' -Description 'Network for testlab A' -LeaseDuration (New-TimeSpan -Days 8) -Type "Both"
```

<span data-ttu-id="3cc03-239">如果不使用[展开][]，则需要在一行上定义所有这些内容。</span><span class="sxs-lookup"><span data-stu-id="3cc03-239">Without using [splatting][], all those things need to be defined on a single line.</span></span> <span data-ttu-id="3cc03-240">它会在屏幕上滚动或进行换行。</span><span class="sxs-lookup"><span data-stu-id="3cc03-240">It either scrolls off the screen or will wrap where ever it feels like.</span></span> <span data-ttu-id="3cc03-241">现在将其与使用展开的命令进行比较。</span><span class="sxs-lookup"><span data-stu-id="3cc03-241">Now compare that to a command that uses splatting.</span></span>

```powershell
$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    SubnetMask  = '255.255.255.0'
    Description = 'Network for testlab A'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}
Add-DhcpServerv4Scope @DHCPScope
```

<span data-ttu-id="3cc03-242">使用 `@` 符号而非 `$` 会调用展开操作。</span><span class="sxs-lookup"><span data-stu-id="3cc03-242">The use of the `@` sign instead of the `$` is what invokes the splat operation.</span></span>

<span data-ttu-id="3cc03-243">请花点时间来了解一下该示例有多容易读取。</span><span class="sxs-lookup"><span data-stu-id="3cc03-243">Just take a moment to appreciate how easy that example is to read.</span></span> <span data-ttu-id="3cc03-244">它们是具有所有相同值的完全相同的命令。</span><span class="sxs-lookup"><span data-stu-id="3cc03-244">They are the exact same command with all the same values.</span></span> <span data-ttu-id="3cc03-245">第二个更易于理解和维护。</span><span class="sxs-lookup"><span data-stu-id="3cc03-245">The second one is easier to understand and maintain going forward.</span></span>

<span data-ttu-id="3cc03-246">我会在命令太长时使用展开。</span><span class="sxs-lookup"><span data-stu-id="3cc03-246">I use splatting anytime the command gets too long.</span></span> <span data-ttu-id="3cc03-247">我定义得太长，导致窗口向右滚动。</span><span class="sxs-lookup"><span data-stu-id="3cc03-247">I define too long as causing my window to scroll right.</span></span> <span data-ttu-id="3cc03-248">如果我遇到了某个函数的三个属性，则有可能会使用展开哈希表来重写它。</span><span class="sxs-lookup"><span data-stu-id="3cc03-248">If I hit three properties for a function, odds are that I'll rewrite it using a splatted hashtable.</span></span>

### <a name="splatting-for-optional-parameters"></a><span data-ttu-id="3cc03-249">可选参数的展开</span><span class="sxs-lookup"><span data-stu-id="3cc03-249">Splatting for optional parameters</span></span>

<span data-ttu-id="3cc03-250">我使用展开的最常见方式之一是处理来自我的脚本中某个位置的可选参数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-250">One of the most common ways I use splatting is to deal with optional parameters that come from some place else in my script.</span></span> <span data-ttu-id="3cc03-251">假设有一个函数，该函数包装了具有可选 `$Credential` 参数的 `Get-CIMInstance` 调用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-251">Let's say I have a function that wraps a `Get-CIMInstance` call that has an optional `$Credential` argument.</span></span>

```powershell
$CIMParams = @{
    ClassName = 'Win32_Bios'
    ComputerName = $ComputerName
}

if($Credential)
{
    $CIMParams.Credential = $Credential
}

Get-CIMInstance @CIMParams
```

<span data-ttu-id="3cc03-252">首先，使用常见参数创建我的哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-252">I start by creating my hashtable with common parameters.</span></span> <span data-ttu-id="3cc03-253">然后添加 `$Credential`（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="3cc03-253">Then I add the `$Credential` if it exists.</span></span>
<span data-ttu-id="3cc03-254">因为我使用的是展开，所以我只需调用一次代码中的 `Get-CIMInstance`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-254">Because I'm using splatting here, I only need to have the call to `Get-CIMInstance` in my code once.</span></span> <span data-ttu-id="3cc03-255">此设计模式非常整洁，可以轻松地处理许多可选参数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-255">This design pattern is very clean and can handle lots of optional parameters easily.</span></span>

<span data-ttu-id="3cc03-256">一般情况下，可以编写命令来允许参数的值为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-256">To be fair, you could write your commands to allow `$null` values for parameters.</span></span> <span data-ttu-id="3cc03-257">只是你不会始终控制你要调用的其他命令。</span><span class="sxs-lookup"><span data-stu-id="3cc03-257">You just don't always have control over the other commands you're calling.</span></span>

### <a name="multiple-splats"></a><span data-ttu-id="3cc03-258">多次展开</span><span class="sxs-lookup"><span data-stu-id="3cc03-258">Multiple splats</span></span>

<span data-ttu-id="3cc03-259">可以将多个哈希表展开到同一个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cc03-259">You can splat multiple hashtables to the same cmdlet.</span></span> <span data-ttu-id="3cc03-260">如果我们重新访问原始的展开示例：</span><span class="sxs-lookup"><span data-stu-id="3cc03-260">If we revisit our original splatting example:</span></span>

```powershell
$Common = @{
    SubnetMask  = '255.255.255.0'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}

$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    Description = 'Network for testlab A'
}

Add-DhcpServerv4Scope @DHCPScope @Common
```

<span data-ttu-id="3cc03-261">当我有一组要传递给许多命令的通用参数时，我会使用这个方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-261">I'll use this method when I have a common set of parameters that I'm passing to lots of commands.</span></span>

### <a name="splatting-for-clean-code"></a><span data-ttu-id="3cc03-262">展开以获得干净代码</span><span class="sxs-lookup"><span data-stu-id="3cc03-262">Splatting for clean code</span></span>

<span data-ttu-id="3cc03-263">如果可以使代码更简洁，那么展开单个参数没有什么问题。</span><span class="sxs-lookup"><span data-stu-id="3cc03-263">There's nothing wrong with splatting a single parameter if makes you code cleaner.</span></span>

```powershell
$log = @{Path = '.\logfile.log'}
Add-Content "logging this command" @log
```

### <a name="splatting-executables"></a><span data-ttu-id="3cc03-264">展开可执行文件</span><span class="sxs-lookup"><span data-stu-id="3cc03-264">Splatting executables</span></span>

<span data-ttu-id="3cc03-265">展开也适用于使用 `/param:value` 语法的某些可执行文件。</span><span class="sxs-lookup"><span data-stu-id="3cc03-265">Splatting also works on some executables that use a `/param:value` syntax.</span></span> <span data-ttu-id="3cc03-266">例如，`Robocopy.exe` 具有一些如下所示的参数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-266">`Robocopy.exe`, for example, has some parameters like this.</span></span>

```powershell
$robo = @{R=1;W=1;MT=8}
robocopy source destination @robo
```

<span data-ttu-id="3cc03-267">我不知道这是不是有用，但我发现它很有趣。</span><span class="sxs-lookup"><span data-stu-id="3cc03-267">I don't know that this is all that useful, but I found it interesting.</span></span>

## <a name="adding-hashtables"></a><span data-ttu-id="3cc03-268">添加哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-268">Adding hashtables</span></span>

<span data-ttu-id="3cc03-269">哈希表支持加法运算符以组合两个哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-269">Hashtables support the addition operator to combine two hashtables.</span></span>

```powershell
$person += @{Zip = '78701'}
```

<span data-ttu-id="3cc03-270">这仅适用于两个哈希表不共享某个键的情况。</span><span class="sxs-lookup"><span data-stu-id="3cc03-270">This only works if the two hashtables don't share a key.</span></span>

## <a name="nested-hashtables"></a><span data-ttu-id="3cc03-271">嵌套哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-271">Nested hashtables</span></span>

<span data-ttu-id="3cc03-272">我们可以将哈希表用作哈希表中的值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-272">We can use hashtables as values inside a hashtable.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
$person.location = @{}
$person.location.city = 'Austin'
$person.location.state = 'TX'
```

<span data-ttu-id="3cc03-273">我首先使用一个包含两个键的基本哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-273">I started with a basic hashtable containing two keys.</span></span> <span data-ttu-id="3cc03-274">我添加了一个包含空哈希表、名为 `location` 的键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-274">I added a key called `location` with an empty hashtable.</span></span> <span data-ttu-id="3cc03-275">然后，将最后两项添加到 `location` 哈希表中。</span><span class="sxs-lookup"><span data-stu-id="3cc03-275">Then I added the last two items to that `location` hashtable.</span></span> <span data-ttu-id="3cc03-276">我们也可以用内联的方式完成此操作。</span><span class="sxs-lookup"><span data-stu-id="3cc03-276">We can do this all inline too.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
    location = @{
        city  = 'Austin'
        state = 'TX'
    }
}
```

<span data-ttu-id="3cc03-277">这会创建上面看到的相同哈希表，并以相同的方式访问属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-277">This creates the same hashtable that we saw above and can access the properties the same way.</span></span>

```powershell
$person.location.city
Austin
```

<span data-ttu-id="3cc03-278">可以通过多种方式处理对象的结构。</span><span class="sxs-lookup"><span data-stu-id="3cc03-278">There are many ways to approach the structure of your objects.</span></span> <span data-ttu-id="3cc03-279">下面是查看嵌套哈希表的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-279">Here is a second way to look at a nested hashtable.</span></span>

```powershell
$people = @{
    Kevin = @{
        age  = 36
        city = 'Austin'
    }
    Alex = @{
        age  = 9
        city = 'Austin'
    }
}
```

<span data-ttu-id="3cc03-280">这混合了使用哈希表作为对象集合和属性集合的概念。</span><span class="sxs-lookup"><span data-stu-id="3cc03-280">This mixes the concept of using hashtables as a collection of objects and a collection of properties.</span></span> <span data-ttu-id="3cc03-281">即使这些值是使用你喜欢的任何方法进行嵌套的，它们仍可以轻松访问。</span><span class="sxs-lookup"><span data-stu-id="3cc03-281">The values are still easy to access even when they're nested using whatever approach you prefer.</span></span>

```powershell
PS> $people.kevin.age
36
PS> $people.kevin['city']
Austin
PS> $people['Alex'].age
9
PS> $people['Alex']['City']
Austin
```

<span data-ttu-id="3cc03-282">当我把它当作属性时，我倾向于使用点属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-282">I tend to use the dot property when I'm treating it like a property.</span></span> <span data-ttu-id="3cc03-283">这些通常是我在代码中静态定义的内容，而且我对它们非常了解。</span><span class="sxs-lookup"><span data-stu-id="3cc03-283">Those are generally things I've defined statically in my code and I know them off the top of my head.</span></span> <span data-ttu-id="3cc03-284">如果我需要遍历列表或以编程方式访问键，我会使用括号提供键名。</span><span class="sxs-lookup"><span data-stu-id="3cc03-284">If I need to walk the list or programmatically access the keys, I use the brackets to provide the key name.</span></span>

```powershell
foreach($name in $people.keys)
{
    $person = $people[$name]
    '{0}, age {1}, is in {2}' -f $name, $person.age, $person.city
}
```

<span data-ttu-id="3cc03-285">能够嵌套哈希表提供了很多灵活性和选项。</span><span class="sxs-lookup"><span data-stu-id="3cc03-285">Having the ability to nest hashtables gives you a lot of flexibility and options.</span></span>

### <a name="looking-at-nested-hashtables"></a><span data-ttu-id="3cc03-286">查看嵌套的哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-286">Looking at nested hashtables</span></span>

<span data-ttu-id="3cc03-287">开始嵌套哈希表后，你将需要一种简单的方法来从控制台中查看它们。</span><span class="sxs-lookup"><span data-stu-id="3cc03-287">As soon as you start nesting hashtables, you're going to need an easy way to look at them from the console.</span></span> <span data-ttu-id="3cc03-288">如果我采用最后一个哈希表，则会得到如下所示的输出，它将会深入：</span><span class="sxs-lookup"><span data-stu-id="3cc03-288">If I take that last hashtable, I get an output that looks like this and it only goes so deep:</span></span>

```powershell
PS> $people
Name                           Value
----                           -----
Kevin                          {age, city}
Alex                           {age, city}
```

<span data-ttu-id="3cc03-289">用于查看这些内容的 go to 命令是 `ConvertTo-JSON`，因为它非常干净，我经常对其他内容使用 JSON。</span><span class="sxs-lookup"><span data-stu-id="3cc03-289">My go to command for looking at these things is `ConvertTo-JSON` because it's very clean and I frequently use JSON on other things.</span></span>

```powershell
PS> $people | ConvertTo-Json
{
    "Kevin":  {
                "age":  36,
                "city":  "Austin"
            },
    "Alex":  {
                "age":  9,
                "city":  "Austin"
            }
}
```

<span data-ttu-id="3cc03-290">即使你不知道 JSON，也应该能够看到你要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="3cc03-290">Even if you don't know JSON, you should be able to see what you're looking for.</span></span> <span data-ttu-id="3cc03-291">对于类似于这样的结构化数据，还有一个 `Format-Custom` 命令，但我还是更喜欢 JSON 视图。</span><span class="sxs-lookup"><span data-stu-id="3cc03-291">There's a `Format-Custom` command for structured data like this but I still like the JSON view better.</span></span>

## <a name="creating-objects"></a><span data-ttu-id="3cc03-292">创建对象</span><span class="sxs-lookup"><span data-stu-id="3cc03-292">Creating objects</span></span>

<span data-ttu-id="3cc03-293">有时，只需有一个对象，而使用哈希表保存属性无法完成工作。</span><span class="sxs-lookup"><span data-stu-id="3cc03-293">Sometimes you just need to have an object and using a hashtable to hold properties just isn't getting the job done.</span></span> <span data-ttu-id="3cc03-294">最常见的情况是，你想要将键视为列名称。</span><span class="sxs-lookup"><span data-stu-id="3cc03-294">Most commonly you want to see the keys as column names.</span></span> <span data-ttu-id="3cc03-295">`pscustomobject` 使其变得简单。</span><span class="sxs-lookup"><span data-stu-id="3cc03-295">A `pscustomobject` makes that easy.</span></span>

```powershell
$person = [pscustomobject]@{
    name = 'Kevin'
    age  = 36
}

$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="3cc03-296">即使最初并未将其创建为 `pscustomobject`，也可以在以后需要时对其进行强制转换。</span><span class="sxs-lookup"><span data-stu-id="3cc03-296">Even if you don't create it as a `pscustomobject` initially, you can always cast it later when needed.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}

[pscustomobject]$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="3cc03-297">我已经为 [pscustomobject][] 编写了详细的内容，你可以在读完本文后阅读。</span><span class="sxs-lookup"><span data-stu-id="3cc03-297">I already have detailed write-up for [pscustomobject][] that you should go read after this one.</span></span> <span data-ttu-id="3cc03-298">它基于此处所述的许多内容构建。</span><span class="sxs-lookup"><span data-stu-id="3cc03-298">It builds on a lot of the things learned here.</span></span>

## <a name="reading-and-writing-hashtables-to-file"></a><span data-ttu-id="3cc03-299">在文件中读取和写入哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-299">Reading and writing hashtables to file</span></span>

### <a name="saving-to-csv"></a><span data-ttu-id="3cc03-300">保存到 CSV</span><span class="sxs-lookup"><span data-stu-id="3cc03-300">Saving to CSV</span></span>

<span data-ttu-id="3cc03-301">将哈希表保存到 CSV 是我上面提到的困难之一。</span><span class="sxs-lookup"><span data-stu-id="3cc03-301">Struggling with getting a hashtable to save to a CSV is one of the difficulties that I was referring to above.</span></span> <span data-ttu-id="3cc03-302">将哈希表转换为 `pscustomobject`，它将正确保存到 CSV。</span><span class="sxs-lookup"><span data-stu-id="3cc03-302">Convert your hashtable to a `pscustomobject` and it will save correctly to CSV.</span></span> <span data-ttu-id="3cc03-303">这有助于你开始使用 `pscustomobject` 以便保留列顺序。</span><span class="sxs-lookup"><span data-stu-id="3cc03-303">It helps if you start with a `pscustomobject` so the column order is preserved.</span></span> <span data-ttu-id="3cc03-304">但如果需要，可以将其强制转换为 `pscustomobject` 内联。</span><span class="sxs-lookup"><span data-stu-id="3cc03-304">But you can cast it to a `pscustomobject` inline if needed.</span></span>

```powershell
$person | ForEach-Object{ [pscustomobject]$_ } | Export-CSV -Path $path
```

<span data-ttu-id="3cc03-305">同样，请查看我使用 [pscustomobject][] 撰写的内容。</span><span class="sxs-lookup"><span data-stu-id="3cc03-305">Again, check out my write-up on using a [pscustomobject][].</span></span>

### <a name="saving-a-nested-hashtable-to-file"></a><span data-ttu-id="3cc03-306">将嵌套哈希表保存到文件</span><span class="sxs-lookup"><span data-stu-id="3cc03-306">Saving a nested hashtable to file</span></span>

<span data-ttu-id="3cc03-307">如果需要将嵌套哈希表保存到文件，然后再次将其读入，我会使用 JSON cmdlet 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3cc03-307">If I need to save a nested hashtable to a file and then read it back in again, I use the JSON cmdlets to do it.</span></span>

```powershell
$people | ConvertTo-JSON | Set-Content -Path $path
$people = Get-Content -Path $path -Raw | ConvertFrom-JSON
```

<span data-ttu-id="3cc03-308">此方法有两个重要方面。</span><span class="sxs-lookup"><span data-stu-id="3cc03-308">There are two important points about this method.</span></span> <span data-ttu-id="3cc03-309">首先，JSON 写成了多行，因此我需要使用 `-Raw` 选项将其读回到单个字符串中。</span><span class="sxs-lookup"><span data-stu-id="3cc03-309">First is that the JSON is written out multiline so I need to use the `-Raw` option to read it back into a single string.</span></span> <span data-ttu-id="3cc03-310">第二个情况是导入的对象不再是 `[hashtable]`。</span><span class="sxs-lookup"><span data-stu-id="3cc03-310">The Second is that the imported object is no longer a `[hashtable]`.</span></span> <span data-ttu-id="3cc03-311">它现在是 `[pscustomobject]`，如果你不希望是这样，可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="3cc03-311">It's now a `[pscustomobject]` and that can cause issues if you don't expect it.</span></span>

<span data-ttu-id="3cc03-312">观察深度嵌套的哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-312">Watch for deeply-nested hashtables.</span></span> <span data-ttu-id="3cc03-313">将其转换为 JSON 时，可能无法获得预期结果。</span><span class="sxs-lookup"><span data-stu-id="3cc03-313">When you convert it to JSON you might not get the results you expect.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json

{
  "a": {
    "b": {
      "c": "System.Collections.Hashtable"
    }
  }
}
```

<span data-ttu-id="3cc03-314">使用 Depth 参数，确保已展开所有嵌套的哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-314">Use **Depth** parameter to ensure that you have expanded all the nested hashtables.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json -Depth 3

{
  "a": {
    "b": {
      "c": {
        "d": "e"
      }
    }
  }
}
```

<span data-ttu-id="3cc03-315">如果需要在导入时为 `[hashtable]`，则需要使用 `Export-CliXml` 和 `Import-CliXml` 命令。</span><span class="sxs-lookup"><span data-stu-id="3cc03-315">If you need it to be a `[hashtable]` on import, then you need to use the `Export-CliXml` and `Import-CliXml` commands.</span></span>

### <a name="converting-json-to-hashtable"></a><span data-ttu-id="3cc03-316">将 JSON 转换为哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-316">Converting JSON to Hashtable</span></span>

<span data-ttu-id="3cc03-317">如果需要将 JSON 转换为 `[hashtable]`，我知道有一种方法可以使用 .NET 中的 [JavaScriptSerializer][] 实现此目的。</span><span class="sxs-lookup"><span data-stu-id="3cc03-317">If you need to convert JSON to a `[hashtable]`, there's one way that I know of to do it with the [JavaScriptSerializer][] in .NET.</span></span>

```powershell
[Reflection.Assembly]::LoadWithPartialName("System.Web.Script.Serialization")
$JSSerializer = [System.Web.Script.Serialization.JavaScriptSerializer]::new()
$JSSerializer.Deserialize($json,'Hashtable')
```

<span data-ttu-id="3cc03-318">从 PowerShell v6 开始，JSON 支持使用了 NewtonSoft JSON.NET ，并添加了哈希表支持。</span><span class="sxs-lookup"><span data-stu-id="3cc03-318">Beginning in PowerShell v6, JSON support uses the NewtonSoft JSON.NET and adds hashtable support.</span></span>

```powershell
'{ "a": "b" }' | ConvertFrom-Json -AsHashtable

Name      Value
----      -----
a         b
```

<span data-ttu-id="3cc03-319">PowerShell 6.2 向 `ConvertFrom-Json` 添加了 Depth 参数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-319">PowerShell 6.2 added the **Depth** parameter to `ConvertFrom-Json`.</span></span> <span data-ttu-id="3cc03-320">Depth 的默认值为 1024。</span><span class="sxs-lookup"><span data-stu-id="3cc03-320">The default **Depth** is 1024.</span></span>

### <a name="reading-directly-from-a-file"></a><span data-ttu-id="3cc03-321">直接从文件读取</span><span class="sxs-lookup"><span data-stu-id="3cc03-321">Reading directly from a file</span></span>

<span data-ttu-id="3cc03-322">如果你有一个使用 PowerShell 语法包含哈希表的文件，那么可以直接导入它。</span><span class="sxs-lookup"><span data-stu-id="3cc03-322">If you have a file that contains a hashtable using PowerShell syntax, there's a way to import it directly.</span></span>

```powershell
$content = Get-Content -Path $Path -Raw -ErrorAction Stop
$scriptBlock = [scriptblock]::Create( $content )
$scriptBlock.CheckRestrictedLanguage( $allowedCommands, $allowedVariables, $true )
$hashtable = ( & $scriptBlock )
```

<span data-ttu-id="3cc03-323">它将文件的内容导入到 `scriptblock` 中，然后在执行之前进行检查以确保它没有任何其他 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3cc03-323">It imports the contents of the file into a `scriptblock`, then checks to make sure it doesn't have any other PowerShell commands in it before it executes it.</span></span>

<span data-ttu-id="3cc03-324">在这种情况下，你是否知道模块清单（psd1 文件）只是一个哈希表？</span><span class="sxs-lookup"><span data-stu-id="3cc03-324">On that note, did you know that a module manifest (the psd1 file) is just a hashtable?</span></span>

## <a name="keys-can-be-any-object"></a><span data-ttu-id="3cc03-325">键可以是任何对象</span><span class="sxs-lookup"><span data-stu-id="3cc03-325">Keys can be any object</span></span>

<span data-ttu-id="3cc03-326">大多数情况下，键只是字符串。</span><span class="sxs-lookup"><span data-stu-id="3cc03-326">Most of the time, the keys are just strings.</span></span> <span data-ttu-id="3cc03-327">这样，我们就可以给任何内容加上引号，并使其成为一个键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-327">So we can put quotes around anything and make it a key.</span></span>

```powershell
$person = @{
    'full name' = 'Kevin Marquette'
    '#' = 3978
}
$person['full name']
```

<span data-ttu-id="3cc03-328">可以执行一些你可能想不到的奇怪操作。</span><span class="sxs-lookup"><span data-stu-id="3cc03-328">You can do some odd things that you may not have realized you could do.</span></span>

```powershell
$person.'full name'

$key = 'full name'
$person.$key
```

<span data-ttu-id="3cc03-329">仅仅因为你能做某事，并不意味着你应该做。</span><span class="sxs-lookup"><span data-stu-id="3cc03-329">Just because you can do something, it doesn't mean that you should.</span></span> <span data-ttu-id="3cc03-330">最后一个看起来就像是一个等待发生的 bug，读取代码的任何人都很容易对其产生误解。</span><span class="sxs-lookup"><span data-stu-id="3cc03-330">That last one just looks like a bug waiting to happen and would be easily misunderstood by anyone reading your code.</span></span>

<span data-ttu-id="3cc03-331">从技术上说，你的键不一定是字符串，但如果你只使用字符串，就更容易考虑。</span><span class="sxs-lookup"><span data-stu-id="3cc03-331">Technically your key doesn't have to be a string but they're easier to think about if you only use strings.</span></span> <span data-ttu-id="3cc03-332">但是，索引不适合用于复杂的键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-332">However, indexing doesn't work well with the complex keys.</span></span>

```powershell
$ht = @{ @(1,2,3) = "a" }
$ht

Name                           Value
----                           -----
{1, 2, 3}                      a
```

<span data-ttu-id="3cc03-333">按值的键访问哈希表中的值并非始终适用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-333">Accessing a value in the hashtable by its key doesn't always work.</span></span> <span data-ttu-id="3cc03-334">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc03-334">For example:</span></span>

```powershell
$key = $ht.keys[0]
$ht.$key
$ht[$key]
a
```

<span data-ttu-id="3cc03-335">使用成员访问 (`.`) 表示法不会返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="3cc03-335">Using the member access (`.`) notation returns nothing.</span></span> <span data-ttu-id="3cc03-336">但可以使用数组索引 (`[]`) 表示法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-336">But using the array index (`[]`) notation works.</span></span>

## <a name="use-in-automatic-variables"></a><span data-ttu-id="3cc03-337">在自动变量中使用</span><span class="sxs-lookup"><span data-stu-id="3cc03-337">Use in automatic variables</span></span>

### <a name="psboundparameters"></a><span data-ttu-id="3cc03-338">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="3cc03-338">$PSBoundParameters</span></span>

<span data-ttu-id="3cc03-339">[$PSBoundParameters][] 是只存在于函数上下文中的自动变量。</span><span class="sxs-lookup"><span data-stu-id="3cc03-339">[$PSBoundParameters][] is an automatic variable that only exists inside the context of a function.</span></span>
<span data-ttu-id="3cc03-340">它包含调用函数时所用的所有参数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-340">It contains all the parameters that the function was called with.</span></span> <span data-ttu-id="3cc03-341">这并不是确切的哈希表，但足够接近，可以将其视为一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-341">This isn't exactly a hashtable but close enough that you can treat it like one.</span></span>

<span data-ttu-id="3cc03-342">这包括删除键并将其展开到其他函数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-342">That includes removing keys and splatting it to other functions.</span></span> <span data-ttu-id="3cc03-343">如果你发现自己正在编写代理函数，请仔细查看这个函数。</span><span class="sxs-lookup"><span data-stu-id="3cc03-343">If you find yourself writing proxy functions, take a closer look at this one.</span></span>

<span data-ttu-id="3cc03-344">有关更多详细信息，请参阅 [about_Automatic_Variables][]。</span><span class="sxs-lookup"><span data-stu-id="3cc03-344">See [about_Automatic_Variables][] for more details.</span></span>

### <a name="psboundparameters-gotcha"></a><span data-ttu-id="3cc03-345">PSBoundParameters 难点</span><span class="sxs-lookup"><span data-stu-id="3cc03-345">PSBoundParameters gotcha</span></span>

<span data-ttu-id="3cc03-346">需要注意的一个重要事项是，这只包括作为参数传入的值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-346">One important thing to remember is that this only includes the values that are passed in as parameters.</span></span> <span data-ttu-id="3cc03-347">如果你还具有使用默认值但不是由调用方传入的参数，则 `$PSBoundParameters` 不包含这些值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-347">If you also have parameters with default values but aren't passed in by the caller, `$PSBoundParameters` doesn't contain those values.</span></span> <span data-ttu-id="3cc03-348">这通常会被忽略。</span><span class="sxs-lookup"><span data-stu-id="3cc03-348">This is commonly overlooked.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="3cc03-349">$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="3cc03-349">$PSDefaultParameterValues</span></span>

<span data-ttu-id="3cc03-350">此自动变量使你可以将默认值分配给任何 cmdlet，而无需更改 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cc03-350">This automatic variable lets you assign default values to any cmdlet without changing the cmdlet.</span></span>
<span data-ttu-id="3cc03-351">请查看此示例。</span><span class="sxs-lookup"><span data-stu-id="3cc03-351">Take a look at this example.</span></span>

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "UTF8"
```

<span data-ttu-id="3cc03-352">这会将一个条目添加到 `$PSDefaultParameterValues` 哈希表中，该哈希表将 `UTF8` 设置为 `Out-File -Encoding` 参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-352">This adds an entry to the `$PSDefaultParameterValues` hashtable that sets `UTF8` as the default value for the `Out-File -Encoding` parameter.</span></span> <span data-ttu-id="3cc03-353">这是特定于会话的，因此应将其放在 `$profile` 中。</span><span class="sxs-lookup"><span data-stu-id="3cc03-353">This is session-specific so you should place it in your `$profile`.</span></span>

<span data-ttu-id="3cc03-354">我经常使用此值来预分配我经常键入的值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-354">I use this often to pre-assign values that I type quite often.</span></span>

```powershell
$PSDefaultParameterValues[ "Connect-VIServer:Server" ] = 'VCENTER01.contoso.local'
```

<span data-ttu-id="3cc03-355">此值也接受通配符，以便你可以批量设置值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-355">This also accepts wildcards so you can set values in bulk.</span></span> <span data-ttu-id="3cc03-356">下面是一些可以使用的方法：</span><span class="sxs-lookup"><span data-stu-id="3cc03-356">Here are some ways you can use that:</span></span>

```powershell
$PSDefaultParameterValues[ "Get-*:Verbose" ] = $true
$PSDefaultParameterValues[ "*:Credential" ] = Get-Credential
```

<span data-ttu-id="3cc03-357">有关更深入的详细信息，请参阅 [Michael Sorens][] 撰写的关于[自动默认值][]的这篇精彩文章。</span><span class="sxs-lookup"><span data-stu-id="3cc03-357">For a more in-depth breakdown, see this great article on [Automatic Defaults][] by [Michael Sorens][].</span></span>

## <a name="regex-matches"></a><span data-ttu-id="3cc03-358">正则表达式 $Matches</span><span class="sxs-lookup"><span data-stu-id="3cc03-358">Regex $Matches</span></span>

<span data-ttu-id="3cc03-359">使用 `-match` 运算符时，将创建一个名为 `$matches` 的自动变量，其中包含匹配项的结果。</span><span class="sxs-lookup"><span data-stu-id="3cc03-359">When you use the `-match` operator, an automatic variable called `$matches` is created with the results of the match.</span></span> <span data-ttu-id="3cc03-360">如果正则表达式中包含任何子表达式，还会列出这些子匹配项。</span><span class="sxs-lookup"><span data-stu-id="3cc03-360">If you have any sub expressions in your regex, those sub matches are also listed.</span></span>

```powershell
$message = 'My SSN is 123-45-6789.'

$message -match 'My SSN is (.+)\.'
$Matches[0]
$Matches[1]
```

### <a name="named-matches"></a><span data-ttu-id="3cc03-361">命名匹配项</span><span class="sxs-lookup"><span data-stu-id="3cc03-361">Named matches</span></span>

<span data-ttu-id="3cc03-362">这是我最喜欢的功能之一，但大多数人却不知道。</span><span class="sxs-lookup"><span data-stu-id="3cc03-362">This is one of my favorite features that most people don't know about.</span></span> <span data-ttu-id="3cc03-363">如果使用命名正则表达式匹配项，则可以按名称对匹配项进行访问。</span><span class="sxs-lookup"><span data-stu-id="3cc03-363">If you use a named regex match, then you can access that match by name on the matches.</span></span>

```powershell
$message = 'My Name is Kevin and my SSN is 123-45-6789.'

if($message -match 'My Name is (?<Name>.+) and my SSN is (?<SSN>.+)\.')
{
    $Matches.Name
    $Matches.SSN
}
```

<span data-ttu-id="3cc03-364">在上面的示例中，`(?<Name>.*)` 是一个命名的子表达式。</span><span class="sxs-lookup"><span data-stu-id="3cc03-364">In the example above, the `(?<Name>.*)` is a named sub expression.</span></span> <span data-ttu-id="3cc03-365">然后，此值将被置于 `$Matches.Name` 属性中。</span><span class="sxs-lookup"><span data-stu-id="3cc03-365">This value is then placed in the `$Matches.Name` property.</span></span>

## <a name="group-object--ashashtable"></a><span data-ttu-id="3cc03-366">Group-Object -AsHashtable</span><span class="sxs-lookup"><span data-stu-id="3cc03-366">Group-Object -AsHashtable</span></span>

<span data-ttu-id="3cc03-367">`Group-Object` 的一个鲜为人知的功能是，它可以将一些数据集转换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-367">One little known feature of `Group-Object` is that it can turn some datasets into a hashtable for you.</span></span>

```powershell
Import-CSV $Path | Group-Object -AsHashtable -Property email
```

<span data-ttu-id="3cc03-368">这会将每一行都添加到哈希表中，并使用指定的属性作为访问它的键。</span><span class="sxs-lookup"><span data-stu-id="3cc03-368">This will add each row into a hashtable and use the specified property as the key to access it.</span></span>

## <a name="copying-hashtables"></a><span data-ttu-id="3cc03-369">复制哈希表</span><span class="sxs-lookup"><span data-stu-id="3cc03-369">Copying Hashtables</span></span>

<span data-ttu-id="3cc03-370">需要注意的一个重要事项是哈希表是对象。</span><span class="sxs-lookup"><span data-stu-id="3cc03-370">One important thing to know is that hashtables are objects.</span></span> <span data-ttu-id="3cc03-371">每个变量只是对对象的引用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-371">And each variable is just a reference to an object.</span></span> <span data-ttu-id="3cc03-372">这意味着，生成哈希表的有效副本需要执行更多的工作。</span><span class="sxs-lookup"><span data-stu-id="3cc03-372">This means that it takes more work to make a valid copy of a hashtable.</span></span>

### <a name="assigning-reference-types"></a><span data-ttu-id="3cc03-373">分配引用类型</span><span class="sxs-lookup"><span data-stu-id="3cc03-373">Assigning reference types</span></span>

<span data-ttu-id="3cc03-374">如果有一个哈希表并将其分配给第二个变量，则这两个变量都指向同一哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-374">When you have one hashtable and assign it to a second variable, both variables point to the same hashtable.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="3cc03-375">这强调了它们是相同的，因为更改一个哈希表中的值也会更改另一个中的值。</span><span class="sxs-lookup"><span data-stu-id="3cc03-375">This highlights that they're the same because altering the values in one will also alter the values in the other.</span></span> <span data-ttu-id="3cc03-376">这也适用于将哈希表传递到其他函数的情况。</span><span class="sxs-lookup"><span data-stu-id="3cc03-376">This also applies when passing hashtables into other functions.</span></span> <span data-ttu-id="3cc03-377">如果这些函数对该哈希表进行了更改，则原始值也会更改。</span><span class="sxs-lookup"><span data-stu-id="3cc03-377">If those functions make changes to that hashtable, your original is also altered.</span></span>

### <a name="shallow-copies-single-level"></a><span data-ttu-id="3cc03-378">卷影副本，单一级别</span><span class="sxs-lookup"><span data-stu-id="3cc03-378">Shallow copies, single level</span></span>

<span data-ttu-id="3cc03-379">如果我们有一个上例所示的简单哈希表，则可以使用 `.Clone()` 进行卷影复制。</span><span class="sxs-lookup"><span data-stu-id="3cc03-379">If we have a simple hashtable like our example above, we can use `.Clone()` to make a shallow copy.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig.Clone()
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [orig]
```

<span data-ttu-id="3cc03-380">这样，我们就可以在不影响其他项的情况下进行一些基本更改。</span><span class="sxs-lookup"><span data-stu-id="3cc03-380">This will allow us to make some basic changes to one that don't impact the other.</span></span>

### <a name="shallow-copies-nested"></a><span data-ttu-id="3cc03-381">卷影副本，嵌套</span><span class="sxs-lookup"><span data-stu-id="3cc03-381">Shallow copies, nested</span></span>

<span data-ttu-id="3cc03-382">之所以称为卷影副本是因为它只复制基本级别的属性。</span><span class="sxs-lookup"><span data-stu-id="3cc03-382">The reason why it's called a shallow copy is because it only copies the base level properties.</span></span> <span data-ttu-id="3cc03-383">如果其中一个属性是引用类型（如其他哈希表），则这些嵌套对象仍将指向彼此。</span><span class="sxs-lookup"><span data-stu-id="3cc03-383">If one of those properties is a reference type (like another hashtable), then those nested objects will still point to each other.</span></span>

```powershell
PS> $orig = @{
        person=@{
            name='orig'
        }
    }
PS> $copy = $orig.Clone()
PS> $copy.person.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.person.name
PS> 'Orig: [{0}]' -f $orig.person.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="3cc03-384">你可以看到，即使克隆了哈希表，也不会克隆对 `person` 的引用。</span><span class="sxs-lookup"><span data-stu-id="3cc03-384">So you can see that even though I cloned the hashtable, the reference to `person` wasn't cloned.</span></span> <span data-ttu-id="3cc03-385">我们需要进行深层复制，确保第二个哈希表未链接到第一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="3cc03-385">We need to make a deep copy to truly have a second hashtable that isn't linked to the first.</span></span>

### <a name="deep-copies"></a><span data-ttu-id="3cc03-386">深层副本</span><span class="sxs-lookup"><span data-stu-id="3cc03-386">Deep copies</span></span>

<span data-ttu-id="3cc03-387">撰写本文时，我还不知道有什么快捷方法可以仅创建哈希表的深层副本（并将其保存为哈希表）。</span><span class="sxs-lookup"><span data-stu-id="3cc03-387">At the time of writing this, I'm not aware of any clever ways to just make a deep copy of a hashtable (and keep it as a hashtable).</span></span> <span data-ttu-id="3cc03-388">这只是需要编写的其中一项内容。</span><span class="sxs-lookup"><span data-stu-id="3cc03-388">That's just one of those things that someone needs to write.</span></span>
<span data-ttu-id="3cc03-389">下面是执行此操作的快速方法。</span><span class="sxs-lookup"><span data-stu-id="3cc03-389">Here is a quick method to do that.</span></span>

```powershell
function Get-DeepClone
{
    [CmdletBinding()]
    param(
        $InputObject
    )
    process
    {
        if($InputObject -is [hashtable]) {
            $clone = @{}
            foreach($key in $InputObject.keys)
            {
                $clone[$key] = Get-DeepClone $InputObject[$key]
            }
            return $clone
        } else {
            return $InputObject
        }
    }
}
```

<span data-ttu-id="3cc03-390">它不处理任何其他引用类型或数组，但它是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="3cc03-390">It doesn't handle any other reference types or arrays, but it's a good starting point.</span></span>

## <a name="anything-else"></a><span data-ttu-id="3cc03-391">任何其他内容？</span><span class="sxs-lookup"><span data-stu-id="3cc03-391">Anything else?</span></span>

<span data-ttu-id="3cc03-392">我已经快速介绍了很多内容。</span><span class="sxs-lookup"><span data-stu-id="3cc03-392">I covered a lot of ground quickly.</span></span> <span data-ttu-id="3cc03-393">希望你每次阅读本文时都能学到新知识或有新的理解。</span><span class="sxs-lookup"><span data-stu-id="3cc03-393">My hope is that you walk away leaning something new or understanding it better every time you read this.</span></span> <span data-ttu-id="3cc03-394">因为我介绍的是此功能的全部内容，所以有些方面现在可能不适用于你。</span><span class="sxs-lookup"><span data-stu-id="3cc03-394">Because I covered the full spectrum of this feature, there are aspects that just may not apply to you right now.</span></span> <span data-ttu-id="3cc03-395">这完全正常并且是意料之中，具体况取决于你对 PowerShell 的使用程度。</span><span class="sxs-lookup"><span data-stu-id="3cc03-395">That is perfectly OK and is kind of expected depending on how much you work with PowerShell.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[original version]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[哈希表]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[hashtables]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[数组]: /powershell/module/microsoft.powershell.core/about/about_arrays
[arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[如果性能很重要，请对其进行测试]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best%20Practices/Performance.md
[If performance matters, test it]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best%20Practices/Performance.md
[展开]: /powershell/module/microsoft.powershell.core/about/about_splatting
[splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[pscustomobject]: everything-about-pscustomobject.md
[JavaScriptSerializer]: /dotnet/api/system.web.script.serialization.javascriptserializer?view=netframework-4.8
[PSBoundParameters]: https://tommymaynard.com/the-psboundparameters-automatic-variable-2016/
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[自动默认值]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Automatic Defaults]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Michael Sorens]: http://cleancode.sourceforge.net/wwwdoc/about.html
