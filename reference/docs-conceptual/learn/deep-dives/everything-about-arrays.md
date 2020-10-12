---
title: 关于数组的各项须知内容
description: 数组是大多数编程语言的一项基本语言功能。
ms.date: 10/08/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: b26aa11aadbeea1984b2754cfcad061c7fa3ff1e
ms.sourcegitcommit: 3445a343e0683124652f64abef6fe911f9eb989f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "91852555"
---
# <a name="everything-you-wanted-to-know-about-arrays"></a>关于数组的各项须知内容

[数组][]是大多数编程语言的一项基本语言功能。 它们是值或对象的集合，在编程中难免会用到。 让我们来深入了解一下数组以及它们提供的一切。

> [!NOTE]
> 本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。 PowerShell 团队感谢 Kevin 与我们分享这篇文章。 请前往 [PowerShellExplained.com][] 访问他的博客。

## <a name="what-is-an-array"></a>什么是数组？

在介绍 PowerShell 使用数组的其他方式之前，我将首先介绍数组的基本技术描述，以及大多数编程语言使用数组的方式。

数组是一种作为多个项集合的数据结构。 你可以循环访问数组或使用索引来访问单个项。 数组是作为一个连续的内存块创建的，其中每个值存储在相邻位置。

接下来，我将逐一进行详细介绍。

## <a name="basic-usage"></a>基本用法

数组是 PowerShell 的一项基本功能，在 PowerShell 中使用时有一个简单的语法。

### <a name="create-an-array"></a>创建数组

使用 `@()` 可创建空数组

```powershell
PS> $data = @()
PS> $data.count
0
```

只需将值放在 `@()` 括号中，即可创建一个数组，并将其作为种子。

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

此数组有 4 个项。 当我们调用 `$data` 变量时，我们将看到项列表。 如果它是字符串数组，则每个字符串占一行。

我们可以在多行上声明一个数组。 在这种情况下，逗号是可选的，通常会省略。

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
```

我更喜欢像这样在多行上声明数组。 当你有多个项时，不仅可以更轻松地读取，还可以在使用源代码管理时更轻松地与以前的版本进行比较。

#### <a name="other-syntax"></a>其他语法

人们通常认为 `@()` 是用于创建数组的语法，但是以逗号分隔的列表在大多数时候都是有效的。

```powershell
$data = 'Zero','One','Two','Three'
```

#### <a name="write-output-to-create-arrays"></a>使用 Write-Output 创建数组

有一个值得一提的小技巧是，你可以使用 `Write-Output` 在控制台中快速创建字符串。

```powershell
$data = Write-Output Zero One Two Three
```

这很方便，因为当参数接受字符串时，无需在字符串两侧加上引号。 我决不会在脚本中这样做，但在控制台中是可以的。

### <a name="accessing-items"></a>访问项

现在，你有了一个包含项的数组，你可能想要访问和更新这些项。

#### <a name="offset"></a>Offset

若要访问各项，可使用方括号 `[]`，且偏移值从 0 开始。 以下是我们获取数组中第一项的方式：

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data[0]
Zero
```

此处使用零的原因是，第一项位于列表的开头，因此我们使用 0 个项的偏移量来获取它。 若要访问第二项，需要使用偏移量 1 来跳过第一项。

```powershell
PS> $data[1]
One
```

这意味着最后一项的偏移量为 3。

```powershell
PS> $data[3]
Three
```

#### <a name="index"></a>索引

现在，你可以看到我在此示例中选取这些值的原因。 我把它当作一个偏移量来介绍，因为它确实是，但这个偏移量通常被称为索引。 从 `0` 开始的索引。 在本文的其余部分，我会把偏移称为索引。

#### <a name="special-index-tricks"></a>特殊索引技巧

在大多数语言中，只能将单个数字指定为索引，然后返回单个项。
PowerShell 则更加灵活。 你可以一次使用多个索引。 通过提供一系列索引，我们可以选择多个项。

```powershell
PS> $data[0,2,3]
Zero
Two
Three
```

根据提供的索引顺序会返回项。 如果复制某个索引，则会两次获得该项。

```powershell
PS> $data[3,0,3]
Three
Zero
Three
```

可以使用内置 `..` 运算符来指定数字序列，

```powershell
PS> $data[1..3]
One
Two
Three
```

反之亦然。

```powershell
PS> $data[3..1]
Three
Two
One
```

可以使用负索引值从末尾进行偏移。 因此，如果需要列表中的最后一项，可以使用 `-1`。

```powershell
PS> $data[-1]
Three
```

关于 `..` 运算符，有一点需要注意。 序列 `0..-1` 和 `-1..0` 的计算结果为值 `0,-1` 和 `-1,0`。 如果忘记了这一细节，就很容易看到 `$data[0..-1]`，并认为它会枚举所有项。 通过提供数组中的第一项和最后一项（其他值都不提供），`$data[0..-1]` 可提供与 `$data[0,-1]` 相同的值。

#### <a name="out-of-bounds"></a>超出范围

在大多数语言中，如果尝试访问超出数组末尾的项的索引，则会出现某种类型的错误或异常。 PowerShell 不会返回任何内容且无提示。

```powershell
PS> $null -eq $data[9000]
True
```

#### <a name="cannot-index-into-a-null-array"></a>不能为空数组建立索引

如果你的变量是 `$null`，并且尝试按数组的方式对其建立索引，则会出现 `System.Management.Automation.RuntimeException` 异常，并显示消息 `Cannot index into a null array`。

```powershell
PS> $empty = $null
SP> $empty[0]
Error: Cannot index into a null array.
```

因此，在尝试访问数组中的元素之前，请确保数组不是 `$null`。

#### <a name="count"></a>Count

数组和其他集合具有计数属性，可告知数组中有多少项。

```powershell
PS> $data.count
4
```

PowerShell 3.0 向大多数对象添加了计数属性。 你可以使用单个对象，它应该会提供计数 `1`。

```powershell
PS> $date = Get-Date
PS> $date.count
1
```

甚至 `$null` 也有计数属性，但它会返回 `0`。

```powershell
PS> $null.count
0
```

这里有一些陷阱，我将在本文稍后介绍检查 `$null` 或空数组时再来介绍。

#### <a name="off-by-one-errors"></a>大小差一错误

因为数组从索引 0 开始，所以产生了一个常见的编程错误。 大小差一错误可能通过两种方式引入。

第一种是，想要第二项并使用索引 `2` 但实际获取了第三项。 或者，假设你有四个项并且想要最后一项，因此使用计数来访问最后一项。

```powershell
$data[ $data.count ]
```

PowerShell 完全可以让你做到这一点，并为你准确提供索引 4 中存在的项：`$null`。 你应该使用 `$data.count - 1` 或我们在前面学到的 `-1`。

```powershell
PS> $data[ $data.count - 1 ]
Three
```

在这里，可以使用 `-1` 索引获取最后一个元素。

```powershell
PS> $data[ -1 ]
Three
```

Lee Dailey 还向我指出，我们可以使用 `$data.GetUpperBound(0)` 获取最大索引号。

```powershell
PS> $data.GetUpperBound(0)
3
PS> $data[ $data.GetUpperBound(0) ]
Three
```

第二种最常见的方式是，在循环访问列表时未在正确的时间停止。 当我们谈到使用 `for` 循环时，我会再来讨论这一点。

### <a name="updating-items"></a>更新项

我们可以使用同一索引来更新数组中的现有项。 这样，我们就可以直接访问并更新各个项。

```powershell
$data[2] = 'dos'
$data[3] = 'tres'
```

如果我们尝试更新的项超出最后一个元素，则会出现 `Index was outside the bounds of the array.` 错误。

```powershell
PS> $data[4] = 'four'
Index was outside the bounds of the array.
At line:1 char:1
+ $data[4] = 'four'
+ ~~~~~~~~~~~~~
+ CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
+ FullyQualifiedErrorId : System.IndexOutOfRangeException
```

稍后介绍如何使数组变大时，我会再来说明这一点。

### <a name="iteration"></a>迭代

在某些时候，你可能需要遍历或循环访问整个列表，并对数组中的每一项执行一些操作。

#### <a name="pipeline"></a>管道

数组和 PowerShell 管道是相互适用的。 这是处理这些值最简单的方法之一。 将数组传递给管道时，数组中的每个项将得到单独处理。

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data | ForEach-Object {"Item: [$PSItem]"}
Item: [Zero]
Item: [One]
Item: [Two]
Item: [Three]
```

如果你之前未见过 `$PSItem`，只需知道它与 `$_` 相同。 你可以使用其中任何一个，因为它们都表示管道中的当前对象。

#### <a name="foreach-loop"></a>ForEach 循环

`ForEach` 循环适用于集合。 使用以下语法：`foreach ( <variable> in <collection> )`

```powershell
foreach ( $node in $data )
{
    "Item: [$node]"
}
```

#### <a name="foreach-method"></a>ForEach 方法

我很容易忘记这一点，但它很适合简单的操作。 PowerShell 允许你对集合调用 `.ForEach()`。

```powershell
PS> $data.foreach({"Item [$PSItem]"})
Item [Zero]
Item [One]
Item [Two]
Item [Three]
```

`.foreach()` 采用了一个是脚本块的参数。 你可以删除括号，只提供脚本块。

```powershell
$data.foreach{"Item [$PSItem]"}
```

这是一个少为人知的语法，但它的工作方式完全相同。 这个 `foreach` 方法是在 PowerShell 4.0 中添加的。

#### <a name="for-loop"></a>For 循环

在大多数其他语言中，`for` 循环的使用非常广泛，但在 PowerShell 中却很少见。 通常在遍历数组的上下文中才会看到此循环。

```powershell
for ( $index = 0; $index -lt $data.count; $index++)
{
    "Item: [{0}]" -f $data[$index]
}
```

我们要做的第一件事是，将 `0` 初始化为 `$index`。 然后添加 `$index` 必须小于 `$data.count` 的条件。 最后，我们指定，每次循环时，索引必须增加 `1`。 在本例中，`$index++` 为 `$index = $index + 1` 的缩写。

无论何时使用 `for` 循环，都需要特别注意条件。 我在这里使用了 `$index -lt $data.count`。 条件很容易出现轻微错误，从而使逻辑中出现大小差一错误。 使用 `$index -le $data.count` 或 `$index -lt ($data.count - 1)` 会出现轻微错误。 这会导致你的结果处理的项过多或过少。 这就是典型的大小差一错误。

#### <a name="switch-loop"></a>Switch 循环

这一点很容易被忽略。 如果向 [switch 语句][]提供一个数组，它将检查数组中的每一项。

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

我们可以使用 switch 语句来完成很多工作。 我在另一篇文章中有专门介绍。

- [关于 switch 语句的各项须知内容][switch 语句]

#### <a name="updating-values"></a>更新值

当数组是字符串或整数（值类型）的集合时，有时你可能希望在循环访问时更新数组中的值。 上面的大多数循环中都使用了一个保存值副本的变量。 如果更新该变量，将不会更新数组中的原始值。

该语句的例外是 `for` 循环。 如果要遍历某个数组并更新其中的值，那么 `for` 循环就是你要找的结果。

```powershell
for ( $index = 0; $index -lt $data.count; $index++ )
{
    $data[$index] = "Item: [{0}]" -f $data[$index]
}
```

此示例通过索引获取一个值，进行一些更改，然后使用同一个索引将其分配回去。

## <a name="arrays-of-objects"></a>对象数组

到目前为止，我们在数组中放置的唯一内容是值类型，但数组也可以包含对象。

```powershell
$data = @(
    [pscustomobject]@{FirstName='Kevin';LastName='Marquette'}
    [pscustomobject]@{FirstName='John'; LastName='Doe'}
)
```

当你将它们分配给变量时，许多 cmdlet 将对象集合作为数组返回。

```powershell
$processList = Get-Process
```

我们已经讨论的所有基本功能仍适用于对象数组，但有几个细节需要注意。

### <a name="accessing-properties"></a>访问属性

可以使用索引访问集合中的单个项，就像使用值类型一样。

```powershell
PS> $data[0]

FirstName LastName
-----     ----
Kevin     Marquette
```

可以直接访问和更新属性。

```powershell
PS> $data[0].FirstName

Kevin

PS> $data[0].FirstName = 'Jay'
PS> $data[0]

FirstName LastName
-----     ----
Jay       Marquette
```

#### <a name="array-properties"></a>数组属性

通常，必须按如下所示枚举整个列表才能访问所有属性：

```powershell
PS> $data | ForEach-Object {$_.LastName}

Marquette
Doe
```

或通过使用 `Select-Object -ExpandProperty` cmdlet 来实现。

```powershell
PS> $data | Select-Object -ExpandProperty LastName

Marquette
Doe
```

但 PowerShell 提供了直接请求 `LastName` 的功能。 PowerShell 会将它们全部枚举出来，并返回一个干净的列表。

```powershell
PS> $data.LastName

Marquette
Doe
```

枚举仍然发生，但我们看不到它背后的复杂操作。

### <a name="where-object-filtering"></a>Where-Object 筛选

这就是 `Where-Object` 的作用：我们可以根据对象的属性，从数组中筛选并选择需要的内容。

```powershell
PS> $data | Where-Object {$_.FirstName -eq 'Kevin'}

FirstName LastName
-----     ----
Kevin     Marquette
```

我们可以编写相同的查询来获取所需的 `FirstName`。

```powershell
$data | Where FirstName -eq Kevin
```

#### <a name="where"></a>Where()

数组中有一个 `Where()` 方法，允许你为筛选器指定一个 `scriptblock`。

```powershell
$data.Where({$_.FirstName -eq 'Kevin'})
```

此功能是在 PowerShell 4.0 中添加的。

### <a name="updating-objects-in-loops"></a>更新循环中的对象

对于值类型，更新数组的唯一方法是使用 for 循环，因为我们需要知道替换值的索引。 由于对象是引用类型，因此我们有更多选择。 下面是一个简短的示例：

```powershell
foreach($person in $data)
{
    $person.FirstName = 'Kevin'
}
```

此循环将遍历 `$data` 数组中的每个对象。 由于对象是引用类型，因此 `$person` 变量会引用数组中完全相同的对象。 因此，更新属性即会更新原始对象。

仍无法以这种方式替换整个对象。 如果尝试将一个新对象分配给 `$person` 变量，则会将变量引用更新为不再指向数组中原始对象的其他对象。 这并不像预期那样：

```powershell
foreach($person in $data)
{
    $person = [pscustomobject]@{
        FirstName='Kevin'
        LastName='Marquette'
    }
}
```

## <a name="operators"></a>运算符

PowerShell 中的运算符也适用于数组。 其中一些的工作方式略有不同。

### <a name="-join"></a>-join

`-join` 运算符最明显，让我们先来看一下。 我非常喜欢 `-join` 运算符并且经常使用。 它能将数组中的所有元素与你指定的字符或字符串联接在一起。

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join '-'
1-2-3-4
PS> $data -join ','
1,2,3,4
```

我喜欢 `-join` 运算符的一项功能是它能处理单个项。

```powershell
PS> 1 -join '-'
1
```

我会在日志记录和详细消息中使用它。

```powershell
PS> $data = @(1,2,3,4)
PS> "Data is $($data -join ',')."
Data is 1,2,3,4.
```

#### <a name="-join-array"></a>-join $array

Lee Dailey 向我介绍了一个妙招。 如果你希望无需分隔符即可联接所有内容，请不要这样做：

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join $null
1234
```

可以将数组作为不带前缀的参数与 `-join` 一起使用。 具体请看下面的示例。

```powershell
PS> $data = @(1,2,3,4)
PS> -join $data
1234
```

### <a name="-replace-and--split"></a>-replace 和 -split

其他运算符（如 `-replace` 和 `-split`）会对数组中的每个项执行。 我不能说我都用过它们，但这里有一个示例。

```powershell
PS> $data = @('ATX-SQL-01','ATX-SQL-02','ATX-SQL-03')
PS> $data -replace 'ATX','LAX'
LAX-SQL-01
LAX-SQL-02
LAX-SQL-03
```

### <a name="-contains"></a>-contains

使用 `-contains` 运算符可以检查值数组，以查看其是否包含指定值。

```powershell
PS> $data = @('red','green','blue')
PS> $data -contains 'green'
True
```

### <a name="-in"></a>-in

如果要验证的单个值与几个值中的一个相匹配，则可以使用 `-in` 运算符。 该值位于运算符的左侧，而数组位于右侧。

```powershell
PS> $data = @('red','green','blue')
PS> 'green' -in $data
True
```

如果列表很大，这可能会占用大量资源。 如果要检查多个值，我经常使用正则表达式模式。

```powershell
PS> $data = @('red','green','blue')
PS> $pattern = "^({0})$" -f ($data -join '|')
PS> $pattern
^(red|green|blue)$

PS> 'green' -match $pattern
True
```

### <a name="-eq-and--ne"></a>-eq 和 -ne

等式和数组相结合可能会变得复杂。 当数组位于左侧时，将对每个项进行比较。 它将返回匹配的对象，而不是返回 `True`。

```powershell
PS> $data = @('red','green','blue')
PS> $data -eq 'green'
green
```

使用 `-ne` 运算符时，将获得不等于我们指定值的所有值。

```powershell
PS> $data = @('red','green','blue')
PS> $data -ne 'green'
red
blue
```

在 `if()` 语句中使用此运算符时，返回的值为 `True` 值。 如果未返回任何值，则它是 `False` 值。 下面这两个语句的计算结果都是 `True`。

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

当我们讨论 `$null` 测试时会来回顾这一点。

### <a name="-match"></a>-match

`-match` 运算符会尝试匹配集合中的每一项。

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

将 `-match` 与单个值结合使用时，将使用匹配信息填充一个特殊变量 `$Matches`。 当以这种方式处理数组时，情况就不同了。

我们可以采用与 `Select-String` 相同的方法。

```powershell
$servers | Select-String SQL
```

在另一篇名为[使用正则表达式的多种方式][]的文章中，我详细介绍了 `Select-String`、`-match` 和 `$matches` 变量。

### <a name="null-or-empty"></a>$null 或空

测试 `$null` 或空数组可能比较棘手。 下面是一些常见的数组陷阱。

这个语句乍一看似乎可行。

```powershell
if ( $array -eq $null)
{
    'Array is $null'
}
```

但我刚刚讲了 `-eq` 如何检查数组中的每一项。 因此，我们可以有一个由几个项组成的数组，其中只有一个 $null 值，它的值将为 `$true`

```powershell
$array = @('one',$null,'three')
if ( $array -eq $null)
{
    'I think Array is $null, but I would be wrong'
}
```

这就是最好将 `$null` 放置在运算符左侧的原因。 这样此方案将不会出现任何问题。

```powershell
if ( $null -eq $array )
{
    'Array actually is $null'
}
```

`$null` 数组与空数组不同。 如果知道有一个数组，请检查其中对象的计数。 如果数组为 `$null`，则计数为 `0`。

```powershell
if ( $array.count -gt 0 )
{
    "Array isn't empty"
}
```

还有一个陷阱需要注意。 即使有单个对象，也可以使用 `count`，除非该对象是 `PSCustomObject`。 这是在 PowerShell 6.1 中修复的 bug。
这是个不错的消息，但有很多人仍在使用 5.1，因此需要注意。

```powershell
PS> $object = [PSCustomObject]@{Name='TestObject'}
PS> $object.count
$null
```

如果仍在使用 PowerShell 5.1，则可以在检查计数之前将对象包装在数组中，以获取准确的计数。

```powershell
if ( @($array).count -gt 0 )
{
    "Array isn't empty"
}
```

稳妥起见，请检查是否有 `$null`，然后再检查计数。

```powershell
if ( $null -ne $array -and @($array).count -gt 0 )
{
    "Array isn't empty"
}
```

### <a name="all--eq"></a>All -eq

我最近看到有人询问[如何验证数组中的每个值是否与给定值匹配][]。
Reddit 用户 /u/bis 提供了一个巧妙的[解决方案][]，该解决方案将检查是否存在不正确的值，然后翻转结果。

```powershell
$results = Test-Something
if ( -not ( $results -ne 'Passed') )
{
    'All results a Passed'
}
```

## <a name="adding-to-arrays"></a>添加到数组

现在，你开始想知道如何向数组中添加项。 简单回答是，不能添加。 数组在内存中具有固定大小。 如果需要对其进行扩展或向其中添加单个项，则需要创建新数组，并从旧数组中复制所有值。 这听起来似乎工作量很大，但 PowerShell 隐藏了创建新数组的复杂性。 PowerShell 为数组实现了加法运算符 (`+`)。

> [!NOTE]
> PowerShell 未实现减法运算。 如果需要一个灵活的数组替代项，需要使用[泛型 `List`](#generic-list) 对象。

### <a name="array-addition"></a>数组加法

可以对数组使用加法运算符来创建新数组。 假设有以下两个数组：

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

我们可以将它们加起来获得一个新数组。

```powershell
PS> $first + $second

Zero
One
Two
Three
```

### <a name="plus-equals-"></a>加等于 + =

我们可以就地创建新数组，并向其添加一个项，如下所示：

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
$data += 'four'
```

请记住，每次使用 `+=` 时，都会复制并创建一个新数组。 对于小型数据集，这并不是问题，但缩放性极差。

### <a name="pipeline-assignment"></a>管道分配

可以将任何管道的结果分配到变量中。 它是一个包含多个项的数组。

```powershell
$array = 1..5 | ForEach-Object {
    "ATX-SQL-$PSItem"
}
```

通常，当我们考虑使用管道时，我们会想到典型的 PowerShell 单行命令。 可以通过 `foreach()` 语句和其他循环来利用管道。 因此，我们可以将项放到管道中，而不是在循环中向数组添加项。

```powershell
$array = foreach ( $node in (1..5))
{
    "ATX-SQL-$node"
}
```

## <a name="array-types"></a>数组类型

默认情况下，PowerShell 中的数组按 `[PSObject[]]` 类型创建。 这使它可以包含任何类型的对象或值。 这是因为所有一切都是从 `PSObject` 类型继承的。

### <a name="strongly-typed-arrays"></a>强类型数组

你可以使用类似的语法来创建任意类型的数组。 创建强类型数组时，它只能包含指定类型的值或对象。

```powershell
PS> [int[]] $numbers = 1,2,3
PS> [int[]] $numbers2 = 'one','two','three'
ERROR: Cannot convert value "one" to type "System.Int32". Input string was not in a correct format."

PS> [string[]] $strings = 'one','two','three'
```

### <a name="arraylist"></a>ArrayList

向数组中添加项是其最大限制之一，但还有其他一些集合可以解决此问题。

当我们需要一个可以更快使用的数组时，我们通常首先会想到 `ArrayList`。 它类似于一个对象数组，会在我们需要它的每一个地方，但它可以快速添加项。

下面介绍如何创建 `ArrayList` 并向其中添加项。

```powershell
$myarray = [System.Collections.ArrayList]::new()
[void]$myArray.Add('Value')
```

我们正在调用 .NET 以获取此类型。 在本例中，我们将使用默认构造函数来创建它。 然后调用 `Add` 方法向其中添加项。

我在行首使用 `[void]` 是为了禁用返回代码。 某些 .NET 调用会这么做，并可能会产生意外输出。

如果数组中的唯一数据是字符串，那么还可以使用 [StringBuilder][]。 它几乎是一样的，但有一些仅用于处理字符串的方法。 `StringBuilder` 专为性能而设计。

人们从数组转向 `ArrayList` 非常常见。 但它来自于 C# 尚未获得广泛支持的时代。 `ArrayList` 在泛型 `List[]` 获得支持后弃用

### <a name="generic-list"></a>泛型列表

泛型类型是 C# 中的一种特殊类型，用于定义通用类，用户会在创建时指定它所使用的数据类型。 因此，如果需要一系列数字或字符串，则应定义想要的 `int` 或 `string` 类型列表。

下面介绍如何创建字符串列表：

```powershell
$mylist = [System.Collections.Generic.List[string]]::new()
```

或数字列表：

```powershell
$mylist = [System.Collections.Generic.List[int]]::new()
```

我们可以将现有数组强制转换为类似于这样的列表，而无需先创建对象：

```powershell
$mylist = [System.Collections.Generic.List[int]]@(1,2,3)
```

可以通过 PowerShell 5 和更高版本中的 `using namespace` 语句缩短语法。 `using` 语句需是脚本的第一行。 通过声明命名空间，PowerShell 允许你在引用数据类型时不使用命名空间。

```powershell
using namespace System.Collections.Generic
$myList = [List[int]]@(1,2,3)
```

这使 `List` 更有用。

你可以使用类似的 `Add` 方法。 与 ArrayList 不同，`Add` 方法没有返回值，因此我们不必使用 `void`。

```powershell
$myList.Add(10)
```

我们仍然可以像访问其他数组一样访问元素。

```powershell
PS> $myList[-1]
10
```

#### <a name="listpsobject"></a>List[PSObject]

你可以使用任何类型的列表，但如果不知道对象的类型，可以使用 `[List[PSObject]]` 来包含它们。

```powershell
$list = [List[PSObject]]::new()
```

#### <a name="remove"></a>Remove()

`ArrayList` 和泛型 `List[]` 均支持从集合中移除项。

```powershell
using namespace System.Collections.Generic
$myList = [List[string]]@('Zero','One','Two','Three')
[void]$myList.Remove("Two")
Zero
One
Three
```

使用值类型时，它会从列表中删除第一个值。 你可以反复调用它来删除该值。 如果是引用类型，则必须提供要删除的对象。

```powershell
[list[System.Management.Automation.PSDriveInfo]]$drives = Get-PSDrive
$drives.remove($drives[2])
```

```powershell
$delete = $drives[2]
$drives.remove($delete)
```

如果此移除方法能够查找并删除集合中的项，则将返回 `true`。

### <a name="more-collections"></a>更多集合

还有很多其他可以使用的集合，但这些是正常的泛型数组替换。
如果有兴趣详细了解这些选项，请查看 [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) 总结的 [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c)。

## <a name="other-nuances"></a>其他细微差别

现在，我已经介绍了所有主要功能，在结束本文之前，我还想介绍一些其他内容。

### <a name="pre-sized-arrays"></a>预调整数组大小

我提到过，数组一旦创建就不能更改它的大小。 通过使用 `new($size)` 构造函数调用它，我们可以创建一个预先确定大小的数组。

```powershell
$data = [Object[]]::new(4)
$data.count
4
```

### <a name="multiplying-arrays"></a>数组倍增

一个有趣的小技巧是你可以将数组与整数相乘。

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

### <a name="initialize-with-0"></a>用 0 初始化

一个常见的情况是，你想要创建一个全为零的数组。 如果只打算包含整数，则强类型整数数组的默认值均为零。

```powershell
PS> [int[]]::new(4)
0
0
0
0
```

我们也可以使用乘法技巧来实现这一点。

```powershell
PS> $data = @(0) * 4
PS> $data
0
0
0
0
```

乘法的妙处在于可以使用任何值。 因此，如果你希望将 `255` 用作默认值，那么这是一种很好的方法。

```powershell
PS> $data = @(255) * 4
PS> $data
255
255
255
255
```

### <a name="nested-arrays"></a>嵌套数组

数组中的数组称为“嵌套数组”。 我在 PowerShell 中很少使用这些，在其他语言中用得更多。 当数据适合类似网格的模式时，请考虑使用数组的数组。

可以通过两种方法创建二维数组。

```powershell
$data = @(@(1,2,3),@(4,5,6),@(7,8,9))

$data2 = @(
    @(1,2,3),
    @(4,5,6),
    @(7,8,9)
)
```

在这些示例中，逗号非常重要。 我前面给出了一个多行普通数组的示例，其中的逗号是可选的。 多维数组则不是这样。

现在，我们有了一个嵌套数组，使用索引表示法的方式会略有变化。 使用上面的 `$data`，这就是我们访问值 3 的方式。

```powershell
PS> $outside = 0
PS> $inside = 2
PS> $data[$outside][$inside]
3
```

为每一级的数组嵌套添加一组方括号。 第一组方括号适用于最外层的数组，然后你可以从那里开始。

### <a name="write-output--noenumerate"></a>Write-Output -NoEnumerate

PowerShell 倾向于展开或枚举数组。 这是 PowerShell 使用管道的核心环节，但有时你并不希望这么做。

我通常会通过管道将对象传递给 `Get-Member` 来了解关于它们的更多信息。 当我向其传递一个数组时，数组将展开，Get-Member 将看到数组的成员而不是实际的数组。

```powershell
PS> $data = @('red','green','blue')
PS> $data | Get-Member
TypeName: System.String
...
```

若要防止数组展开，可以使用 `Write-Object -NoEnumerate`。

```powershell
PS> Write-Output -NoEnumerate $data | Get-Member
TypeName: System.Object[]
...
```

我的第二种方法更像是黑客行为（我会尽量避免这类行为）。 在用管道传输之前，可以在数组前面放一个逗号。

```powershell
PS> ,$data | Get-Member
TypeName: System.Object[]
...
```

### <a name="return-an-array"></a>返回数组

当从函数输出或返回值时，也会发生这种数组展开的情况。 如果将输出分配给变量，则仍可获取一个数组，所以这通常不是问题。

问题是你有了一个新数组。 如果出现这个问题，可以使用 `Write-Output -NoEnumerate $array` 或 `return ,$array` 来解决。

## <a name="anything-else"></a>任何其他内容？

我知道所有这些都是需要消化吸收的。 希望你每次阅读本文时都能有所收获，并在未来一段时间内把它作为一项有价值的参考资料。 如果你认为本文有用，请把它分享给你认为可能会从中获益的其他人。

在这里，我建议你查看我写的一篇类似的关于[哈希表][]的文章。

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[数组]: /powershell/module/microsoft.powershell.core/about/about_arrays
[switch 语句]: everything-about-switch.md
[哈希表]: everything-about-hashtable.md
[使用正则表达式的多种方式]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[如何验证数组中的每个值是否与给定值匹配]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[解决方案]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[StringBuilder]: https://powershellexplained.com/2017-11-20-Powershell-StringBuilder/
