---
title: 关于 if 语句的各项须知内容
description: 与许多其他语言一样，PowerShell 提供了用于在脚本中有条件地执行代码的语句。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: b6bafb99bfb8ecd0152bae841e5c58d4c27ccd3e
ms.sourcegitcommit: 0afff6edbe560e88372dd5f1cdf51d77f9349972
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "86469746"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a>关于 `if` 语句的各项须知内容

与许多其他语言一样，PowerShell 提供了用于在脚本中有条件地执行代码的语句。 其中一个语句是 [If][] 语句。 今天，我们将深入探讨 PowerShell 中最基本的命令之一。

> [!NOTE]
> 本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。 PowerShell 团队感谢 Kevin 与我们分享这篇文章。 请前往 [PowerShellExplained.com][] 访问他的博客。

## <a name="conditional-execution"></a>条件执行

你的脚本通常需要做出决策，并根据这些决策执行不同的逻辑。
这就是条件执行的意思。 需要计算一个语句或值，然后根据该计算结果执行不同的代码段。 这正是 `if` 语句的作用。

## <a name="the-if-statement"></a>`if` 语句

下面是 `if` 语句的基本示例：

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

`if` 语句执行的第一步是计算括号中的表达式。 如果计算结果为 `$true`，则执行大括号中的 `scriptblock`。 如果值为 `$false`，则会跳过该脚本块。

在上面的示例中，`if` 语句仅计算 `$condition` 变量。 其计算结果为 `$true`，将在脚本块内执行 `Write-Output` 命令。

在某些语言中，可以在 `if` 语句后放置一行代码，它将会得以执行。 在 PowerShell 中情况并非如此。 必须提供带大括号的完整 `scriptblock` 才能使其正常工作。

## <a name="comparison-operators"></a>比较运算符

`if` 语句最常见的用法是比较两个项。 PowerShell 具有特殊运算符，可用于不同的比较方案。 当使用比较运算符时，会将左右两侧的值进行比较。

### <a name="-eq-for-equality"></a>-eq（等于）

`-eq` 在两个值之间执行相等检查，以确保它们彼此相等。

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

在此示例中，我采用已知值 `5`，并将其与 `$value` 进行比较，以确定它们是否匹配。

一个可能的用例是在对值执行操作之前检查值的状态。 你可以获得一种服务，并检查状态是否正在运行，然后再对其调用 `Restart-Service`。

在其他语言（如 C#）中，通常使用 `==` 检查是否相等（例如：`5 == $value`），但此方法不适用于 PowerShell。 人们常犯的另一种错误是保留等号（例如：`5 = $value`）来为变量赋值。 将已知值放在左侧就可以避免发生这种错误。

此运算符（以及其他运算符）具有几个变体。

- `-eq` 等于（不区分大小写）
- `-ieq` 等于（不区分大小写）
- `-ceq` 等于（区分大小写）

### <a name="-ne-not-equal"></a>-ne（不等于）

许多运算符都有一个相关的运算符，用于检查相反的结果。 `-ne` 用于验证这些值是否相互不相等。

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

使用此方法可确保仅在值不等于 `5` 时才执行操作。 一个很好的用例是，在尝试启动服务之前检查服务是否处于运行状态。

变体：

- `-ne` 不等于（不区分大小写）
- `-ine` 不等于（不区分大小写）
- `-cne` 不等于（区分大小写）

这些是 `-eq` 的反向变体。 在列出其他运算符的变体时，我会把这些类型分组。

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a>-gt -ge -lt -le（大于或小于）

检查某个值是否大于或小于另一个值时，将使用这些运算符。
`-gt -ge -lt -le` 代表 GreaterThan、GreaterThanOrEqual、LessThan 和 LessThanOrEqual。

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

变体：

- `-gt` 大于
- `-igt` 大于（不区分大小写）
- `-cgt` 大于（区分大小写）
- `-ge` 大于或等于
- `-ige` 大于或等于（不区分大小写）
- `-cge` 大于或等于（区分大小写）
- `-lt` 小于
- `-ilt` 小于（不区分大小写）
- `-clt` 小于（区分大小写）
- `-le` 小于或等于
- `-ile` 小于或等于（不区分大小写）
- `-cle` 小于或等于（区分大小写）

我不知道为什么要为这些运算符使用区分大小写和不区分大小写的选项。

### <a name="-like-wildcard-matches"></a>-like（通配符匹配）

PowerShell 具有其自己的通配符模式匹配语法，你可以将其与 `-like` 运算符一起使用。 这些通配符模式都非常基本。

- `?` 匹配任何单个字符
- `*` 匹配任意数量的字符

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

必须指出的是，该模式与整个字符串匹配。 如果需要匹配字符串中间的某些内容，则需要在字符串的两端放置 `*`。

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

变体：

- `-like` 通配符（不区分大小写）
- `-ilike` 通配符（不区分大小写）
- `-clike` 通配符（区分大小写）
- `-notlike` 通配符不匹配（不区分大小写）
- `-inotlike` 通配符不匹配（不区分大小写）
- `-cnotlike` 通配符不匹配（区分大小写）

### <a name="-match-regular-expression"></a>-match（正则表达式）

使用 `-match` 运算符可以检查字符串中是否有基于正则表达式的匹配项。 当你觉得通配符模式不够灵活时，请使用此模式。

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

默认情况下，正则表达式模式匹配字符串中的任意位置。 因此，你可以指定希望匹配的子字符串，如下所示：

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

正则表达式是一种复杂的语言，值得研究。 我在另一篇文章中详细介绍了 `-match` 和[使用正则表达式的多种方式][]。

变体：

- `-match` 正则表达式（不区分大小写）
- `-imatch` 正则表达式（不区分大小写）
- `-cmatch` 正则表达式（区分大小写）
- `-notmatch` 正则表达式不匹配（不区分大小写）
- `-inotmatch` 正则表达式不匹配（不区分大小写）
- `-cnotmatch` 正则表达式不匹配（区分大小写）

### <a name="-is-of-type"></a>-is（属于类型）

你可以使用 `-is` 运算符检查值的类型。

```powershell
if ( $value -is [string] )
{
    # do something
}
```

在使用类或通过管道接受各种对象时，可以使用此项。 可以将服务或服务名称作为输入。 然后，查看是否有服务并提取服务（如果只有名称）。

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

变体：

- `-is` 属于类型
- `-isnot` 不属于类型

## <a name="collection-operators"></a>集合运算符

对单个值使用前面的运算符时，结果为 `$true` 或 `$false`。 处理集合时，方式略有不同。 将计算集合中的每一项，运算符将返回计算结果为 `$true` 的每个值。

```powershell
PS> 1,2,3,4 -eq 3
3
```

这在 `if` 语句中仍能正常运行。 因此运算符返回一个值，则整个语句为 `$true`。

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

我需要指出的是，这里有一个小陷阱隐藏在细节中。以这种方式使用 `-ne` 运算符时，很容易错误地向后查看逻辑。 如果集合中的任何项与你的值都不匹配，则对集合使用 `-ne` 将返回 `$true`。

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

这个花招看起来巧妙，但我们通过运算符 `-contains` 和 `-in` 可以更高效地处理这种情况。 并且 `-notcontains` 会执行你期望的操作。

### <a name="-contains"></a>-contains

`-contains` 运算符会针对你的值检查集合。 找到匹配项后，将返回 `$true`。

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

这是查看集合是否包含你的值的首选方法。 使用 `Where-Object`（或 `-eq`）时，每次都会遍历整个列表，且速度显著降低。

变体：

- `-contains` 匹配（不区分大小写）
- `-icontains` 匹配（不区分大小写）
- `-ccontains` 匹配（区分大小写）
- `-notcontains` 不匹配（不区分大小写）
- `-inotcontains` 不匹配（不区分大小写）
- `-cnotcontains` 不匹配（区分大小写）

### <a name="-in"></a>-in

`-in` 运算符与 `-contains` 运算符类似，只是集合位于右侧。

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

变体：

- `-in` 匹配（不区分大小写）
- `-iin` 匹配（不区分大小写）
- `-cin` 匹配（区分大小写）
- `-notin` 不匹配（不区分大小写）
- `-inotin` 不匹配（不区分大小写）
- `-cnotin` 不匹配（区分大小写）

## <a name="logical-operators"></a>逻辑运算符

逻辑运算符用于反转或合并其他表达式。

### <a name="-not"></a>-not

`-not` 运算符将表达式从 `$false` 翻转到 `$true` 或从 `$true` 翻转到 `$false`。 下面是一个示例，我们希望在 `Test-Path` 为 `$false` 时执行一个操作。

```powershell
if ( -not ( Test-Path -Path $path ) )
```

我们讨论的大多数运算符都有一种变体，因而无需使用 `-not` 运算符。 但它还是有用武之地。

### <a name="-operator"></a>! 运算符后的表达式

你可以使用 `!` 作为 `-not` 的别名。

```powershell
if ( -not $value ){}
if ( !$value ){}
```

你可能会发现其他语言（如 C#）的用户使用 `!` 更多。 我更喜欢把它打出来，因为我发现在快速查看脚本时很难看清。

### <a name="-and"></a>-and

可以将表达式与 `-and` 运算符组合在一起。 当你这样做时，两侧都应为 `$true`，这样整个表达式才能为 `$true`。

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

在此示例中，左侧的 `$age` 必须大于等于 13，右侧的则必须小于 55。 在这个例子中，我添加了额外的括号以使其更清晰，但只要表达式简单，括号是可有可无的。 下面是同一个示例没有额外添加括号的情况。

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

计算从左到右进行。 如果第一项的计算结果为 `$false`，它将提前退出，并且不会执行正确的比较。 如果你在使用值之前需要确保该值存在，这非常方便。 例如，如果为 `Test-Path` 提供 `$null` 路径，则会引发错误。

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a>-or

`-or` 允许指定两个表达式，并在其中任一个表达式为 `$true` 时返回 `$true`。

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

与 `-and` 运算符一样，计算从左到右进行。 例外情况是，如果第一部分为 `$true`，则整个语句为 `$true`，且其不会处理表达式的其余部分。

另外，请注意涉及这些运算符的语法是如何工作的。 需要两个单独的表达式。 我见过用户尝试执行类似于此 `$value -eq 5 -or 6` 的操作，但他们却没有意识到自己的错误。

### <a name="-xor-exclusive-or"></a>-xor 异或

这个运算符有点不寻常。 `-xor` 仅允许一个表达式的计算结果为 `$true`。 因此，如果两个项均为 `$false` 或者均为 `$true`，则整个表达式为 `$false`。 另一种看待此问题的方法是，仅当表达式的结果不同时，表达式才为 `$true`。

很少有人会使用此逻辑运算符，我也举不出一个好的使用示例。

## <a name="bitwise-operators"></a>位运算符

位运算符会对值中的位执行计算，并生成一个新值作为结果。 讲授[位运算符][]超出了本文的范围，下面仅列出这些运算符，不做详述。

- `-band` 二进制和
- `-bor` 二进制或
- `-bxor` 二进制异或
- `-bnot` 二进制非
- `-shl` 左移
- `-shr` 右移

## <a name="powershell-expressions"></a>PowerShell 表达式

可以在条件语句中使用常规 PowerShell。

```powershell
if ( Test-Path -Path $Path )
```

执行 `Test-Path` 时会返回 `$true` 或 `$false`。 这也适用于返回其他值的命令。

```powershell
if ( Get-Process Notepad* )
```

其计算结果为 `$true`（如果有返回的进程）和 `$false`（如果不返回任何结果）。 使用管道表达式或其他 PowerShell 语句非常有效，如下所示：

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

这些表达式可以与 `-and` 和 `-or` 运算符相互组合在一起，但你可能必须使用括号将它们拆分为子表达式。

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a>检查 $null

在 `if` 语句中，如果没有结果或有 `$null` 值，则计算结果为 `$false`。 专门检查 `$null` 时，最佳做法是将 `$null` 放在左侧。

```powershell
if ( $null -eq $value )
```

在 PowerShell 中处理 `$null` 值时，有很多细微差别。 如果你有兴趣深入研究，请参阅我写的一篇相关文章：[关于 $null 的各项须知内容][]。

### <a name="variable-assignment"></a>变量赋值

多亏 [Prasoon Karunan V][] 的提醒，我差点忘了添加这一内容。

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

通常，在为变量赋值时，该值不会传递到管道或控制台。 在子表达式中执行变量赋值时，它会传递到管道。

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

看到 `$first` 赋值没有输出，而 `$second` 赋值却有输出了吗？ 当在 `if` 语句中完成赋值时，它的执行方式就像上述 `$second` 赋值一样。 下面是一个关于其使用方法的简单示例：

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

如果 `$process` 被赋值，则语句为 `$true` 且 `$process` 将停止。

请确保不要将这种情况与 `-eq` 混淆，因为这不是相等检查。 这是一项更为隐蔽的功能，大多数人不会以这种方式实现此功能。

## <a name="alternate-execution-path"></a>替代执行路径

使用 `if` 语句，不仅可以在语句为 `$true` 时指定操作，还可以在语句为 `$false` 时指定操作。 这正是 `else` 语句的用武之地。

### <a name="else"></a>else

使用时，`else` 语句始终是 `if` 语句的最后一部分。

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

在此示例中，我们将检查 `$path`，确保它是一个文件。 如果找到该文件，则将其移动。 如果未找到，我们就编写一个警告。 这种类型的分支逻辑非常常见。

### <a name="nested-if"></a>嵌套 if

`if` 和 `else` 语句采用脚本块，因此可以将任何 PowerShell 命令放入其中，包括另一个 `if` 语句。 这使你可以使用更复杂的逻辑。

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

在此示例中，我们首先测试愉快路径，然后对其执行操作。 如果失败，我们会进行另一个检查，并为用户提供更详细的信息。

### <a name="elseif"></a>elseif

我们不局限于单个条件检查。 我们可以将 `if` 和 `else` 语句链接在一起，而不是使用 `elseif` 语句来嵌套它们。

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

执行按自上而下的顺序进行。 首先计算顶级 `if` 语句。 如果其结果为 `$false`，则会向下移动到列表中的下一个 `elseif` 或 `else`。 最后一个 `else` 是在其他任何语句未返回 `$true` 时要执行的默认操作。

### <a name="switch"></a>开关

现在，我要提到 `switch` 语句。 它提供了一个替代语法，用于对值执行多个比较。 使用 `switch`，你可以指定一个表达式，并将结果与多个不同值进行比较。 如果其中一个值匹配，则执行匹配的代码块。 请看下面的示例：

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

有三个可能的值可与 `$itemType` 匹配。 在本例中，它与 `Role` 匹配。 我使用了一个简单的示例来让你了解一下 `switch` 运算符。 我在另一篇文章[关于 switch 语句的各项须知内容][]中介绍了更多内容。

## <a name="pipeline"></a>管道

管道是 PowerShell 一项独特的重要功能。 未禁止或赋给变量的任何值都将放在管道中。 `if` 为我们提供了一种利用管道的方式，但这种方式并不总是显而易见的。

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

每个脚本块将结果、命令或值放入管道。 然后，将 `if` 语句的结果赋给 `$discount` 变量。 该示例可以在每个脚本块中轻松地直接将这些值赋给 `$discount` 变量。 我不能说我经常将此方法与 `if` 语句一起使用，但我确实有一个最近使用的例子。

### <a name="array-inline"></a>数组内联

我有一个名为 [Invoke-SnowSql][] 的函数，该函数使用几个命令行参数启动可执行文件。 下面是此函数中的一个片段，我在其中生成了参数数组。

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

`$Debug` 和 `$Path` 变量是由最终用户提供的函数的参数。
我在初始化数组时以内联方式计算其结果。 如果 `$Debug` 为 true，则这些值将落入 `$snowSqlParam` 中的正确位置。 `$Path` 变量情况相同。

## <a name="simplify-complex-operations"></a>简化复杂操作

你不可避免会遇到这样的情况：要检查的比较太多，以致于 `If` 语句从屏幕右侧滚出。

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

它们不便阅读，这使你更容易出错。 对此，我们可以进行一些操作。

### <a name="line-continuation"></a>续行符

PowerShell 中提供了一些运算符，可让你将命令换行到下一行。 如果要将表达式分为多行，则逻辑运算符 `-and` 和 `-or` 是理想的运算符。

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

虽然还有很多项内容，但将每项单独放一行会带来很大不同。
当我进行两次以上的比较，或者如果我必须向右滚动来阅读任何逻辑时，我通常会使用此方法。

### <a name="pre-calculating-results"></a>预先计算结果

我们可以将该语句从 `if` 语句中取出并仅检查结果。

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

这样感觉比上一个示例简洁得多。 你还可以使用变量名称来解释你真正检查的内容。 这也是一个可节省不必要注释的自文档化代码的示例。

### <a name="multiple-if-statements"></a>多个 if 语句

我们可以将此语句分为多个语句，并一次查看一个语句。 在本例中，我们使用标志或跟踪变量来合并结果。

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

我不得不对逻辑进行反转以使标志逻辑正常工作。 每个计算都是单个 `if` 语句。 这样做的优点是，当进行调试时，你可以确切地判断逻辑的作用。 我能够同时添加更好的详细程度。

明显的缺点是，要编写的代码太多。 代码读起来更复杂，因为它采用单行逻辑，并分解成 25 行或更多行。

### <a name="using-functions"></a>使用函数

我们还可以将所有验证逻辑移到一个函数中。 看看这样看起来多清爽。

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

你仍必须创建函数来执行验证，但它使得此代码更容易使用。 它使代码更易于测试。 在测试中，可以模拟对 `Test-ADDriveConfiguration` 的调用，且只需对此函数进行两次测试。 其中一个返回 `$true`，另一个返回 `$false`。 测试其他函数更简单，因为它非常小。

该函数的主体仍然可以是我们开始时使用的单行命令或我们在上一部分中使用的分解逻辑。 这适用于这两种情况，并使你能够在以后轻松地更改该实现。

## <a name="error-handling"></a>错误处理。

`if` 语句的一项重要用途是在出现错误之前检查错误条件。 一个不错的示例是，在尝试创建文件夹之前检查文件夹是否已存在。

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

我想说的是，如果你预计会发生异常，那么它就不是真正的异常。 因此，请检查你的值并在可能的地方验证你的条件。

如果想要更深入地了解实际异常处理，请参阅我写的另一篇文章[关于异常的各项须知内容][]。

## <a name="final-words"></a>结束语

`if` 语句非常简单，但它是 PowerShell 不可或缺的一个基本部分。 你会发现在自己编写的几乎每个脚本中都会多次使用这个语句。 希望本文能让你比以往更深入地理解这一语句。

<!-- link references -->
[原始版本]: https://powershellexplained.com/2019-08-11-Powershell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if
[位运算符]: /powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[使用正则表达式的多种方式]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[关于异常的各项须知内容]: everything-about-exceptions.md
[关于 $null 的各项须知内容]: everything-about-null.md
[Prasoon Karunan V]: https://twitter.com/prasoonkarunan
[关于 switch 语句的各项须知内容]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
