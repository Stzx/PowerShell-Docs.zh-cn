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
# <a name="everything-you-wanted-to-know-about-null"></a>关于 $null 的各项须知内容

PowerShell `$null` 通常看起来很简单，但却有很多细微的差别。 我们来详细了解一下 `$null`，这样你就知道当意外遇到 `$null` 值时将发生的情况。

> [!NOTE]
> 本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。 PowerShell 团队感谢 Kevin 与我们分享这篇文章。 请前往 [PowerShellExplained.com][] 访问他的博客。

## <a name="what-is-null"></a>什么是 NULL？

可以将 NULL 视为未知值或空值。 在为变量赋值或分配对象之前，该变量为 NULL。 这一点非常重要，因为某些命令需要值，并在值为 NULL 时生成错误。

### <a name="powershell-null"></a>PowerShell $null

`$null` 是 PowerShell 中用于表示 NULL 的自动变量。 可以将其分配给变量，将其用于比较，以及将其用作集合中 NULL 值的占位符。

PowerShell 将 `$null` 视为具有 NULL 值的对象。 如果你使用其他语言，则这会与你的预期不同。

## <a name="examples-of-null"></a>$null 示例

任何时候尝试使用尚未初始化的变量时，值都为 `$null`。 这是 `$null` 值进入代码的最常见方式之一。

```powershell
PS> $null -eq $undefinedVariable
True
```

如果变量名称键入错误，PowerShell 会将其视为不同的变量，且值为 `$null`。

查找 `$null` 值的另一种方法是，当它们来自不提供任何结果的其他命令时。

```powershell
PS> function Get-Nothing {}
PS> $value = Get-Nothing
PS> $null -eq $value
True
```

## <a name="impact-of-null"></a>$null 的影响

`$null` 值会以不同方式影响代码，具体取决于它们显示的位置。

### <a name="in-strings"></a>在字符串中

如果在字符串中使用 `$null`，则其为空值（或空字符串）。

```powershell
PS> $value = $null
PS> Write-Output "The value is $value"
The value is
```

这是我在日志消息中使用变量时喜欢将变量用括号括起来的原因之一。 当值位于字符串的末尾时，识别变量值的边缘更为重要。

```powershell
PS> $value = $null
PS> Write-Output "The value is [$value]"
The value is []
```

这会使空字符串和 `$null` 值易于发现。

### <a name="in-numeric-equation"></a>在数值公式中

当数值公式中使用 `$null` 值时，如果未生成错误，则结果无效。 有时 `$null` 的计算结果为 `0`，而其他时间生成完整结果 `$null`。
下面是一个包含乘法的示例，其生成 0 或 `$null`，具体取决于值的顺序。

```powershell
PS> $null * 5
PS> $null -eq ( $null * 5 )
True

PS> 5 * $null
0
PS> $null -eq ( 5 * $null )
False
```

### <a name="in-place-of-a-collection"></a>取代集合

集合允许你使用索引来访问值。 如果尝试对实际为 `null` 的集合建立索引，将生成此错误：`Cannot index into a null array`。

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

如果你有一个集合，但尝试访问不在此集合中的元素，将生成 `$null` 结果。

```powershell
$array = @( 'one','two','three' )
$null -eq $array[100]
True
```

### <a name="in-place-of-an-object"></a>取代对象

如果尝试访问不含指定属性的对象的某个属性或子属性，将得到 `$null` 值，就像使用未定义的变量一样。 在此情况中，变量为 `$null` 或实际对象无关紧要。

```powershell
PS> $null -eq $undefined.some.fake.property
True

PS> $date = Get-Date
PS> $null -eq $date.some.fake.property
True
```

### <a name="method-on-a-null-valued-expression"></a>null 值表达式上的方法

在 `$null` 对象上调用方法将引发 `RuntimeException`。

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

每当我看到这句 `You cannot call a method on a null-valued expression` 时，我首先会查找在变量上调用方法的位置，而不是检查是否有 `$null`。

## <a name="checking-for-null"></a>检查 $null

你可能已注意到，在我的示例中，检查 `$null` 时，始终会将 `$null` 放在左侧。 这是有意为之，并被视为 PowerShell 最佳实践。 在某些情况下，将其放在右侧不会生成预期结果。

查看下一个示例，并尝试预测结果：

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

如果我未定义 `$value`，则第一个的计算结果为 `$true`，消息为 `The array is $null`。 这里的陷阱是，可以创建一个 `$value`，使两者都为 `$false`。

```powershell
$value = @( $null )
```

在这种情况下，`$value` 是一个包含 `$null` 的数组。 `-eq` 检查数组中的每个值，并返回匹配的 `$null`。 其计算结果为 `$false`。 `-ne` 返回与 `$null` 不匹配的所有内容，在这种情况下不会生成任何结果（计算结果也为 `$false`）。 没有一项的计算结果为 `$true`，尽管看起来其中一个应该是这个结果。

我们不仅可以创建一个值来使这两项的计算结果为 `$false`，还可以创建一个值使这两项的计算结果为 `$true`。 Mathias Jessen (@IISResetMe) 发表了一篇[好文章][]，深入探究了这种方案。

### <a name="psscriptanalyzer-and-vscode"></a>PSScriptAnalyzer 和 VSCode

[PSScriptAnalyzer][] 模块具有一个检查此问题的规则，称为 `PSPossibleIncorrectComparisonWithNull`。

```powershell
PS> Invoke-ScriptAnalyzer ./myscript.ps1

RuleName                              Message
--------                              -------
PSPossibleIncorrectComparisonWithNull $null should be on the left side of equality comparisons.
```

由于 VS Code 也使用 PSScriptAnalyser 规则，因此它也会在脚本中突出显示或将其标识为问题。

### <a name="simple-if-check"></a>简单 if 检查

检查非 $null 值的常见方法是使用简单的 `if()` 语句，而不进行比较。

```powershell
if ( $value )
{
    Do-Something
}
```

如果值为 `$null`，则计算结果为 `$false`。 此值易于读取，但请注意，它会准确地查找你希望它查找的内容。 我将该行代码解读为：

> 如果 `$value` 具有值。

但这并不是完整内容。 该行的实际内容为：

> 如果 `$value` 不是 `$null` 或 `0` 或 `$false` 或 `empty string`

下面是该语句的一个更完整的示例。

```powershell
if ( $null -ne $value -and
        $value -ne 0 -and
        $value -ne '' -and
        $value -ne $false )
{
    Do-Something
}
```

只要你记住其他值被视为 `$false` 而不只是变量具有值，就完全可以使用基本 `if` 检查。

几天前重构某些代码时，我遇到了此问题。 它的基本属性检查如下所示。

```powershell
if ( $object.property )
{
    $object.property = $value
}
```

仅当对象属性存在时，我才希望为其分配值。 在大多数情况下，原始对象的值在 `if` 语句中的计算结果为 `$true`。 但我遇到了一个问题，即偶尔未设置此值。 我调试了代码，发现该对象具有属性，但它是一个空字符串值。 这会阻止其使用以前的逻辑进行更新。 因此，我添加了一个适当的 `$null` 检查，一切正常。

```powershell
if ( $null -ne $object.property )
{
    $object.property = $value
}
```

这类小 bug 很难发现，也促使我主动检查 `$null` 值。

## <a name="nullcount"></a>$null.Count

如果尝试访问 `$null` 值的属性，则该属性也为 `$null`。 `count` 属性是此规则的例外情况。

```powershell
PS> $value = $null
PS> $value.count
0
```

如果有 `$null` 值，则 `count` 为 `0`。 PowerShell 会添加此特殊属性。

### <a name="pscustomobject-count"></a>[PSCustomObject] 计数

PowerShell 中的几乎所有对象均具有该计数属性。 一个重要的例外是 Windows PowerShell 5.1 中的 `[PSCustomObject]`（此问题在 PowerShell 6.0 中得以修复）。 它没有计数属性，因此如果你尝试使用它，将得到 `$null` 值。 我在这里提到这一点，这样你就不会尝试使用 `.Count` 代替 `$null` 检查。

在 Windows PowerShell 5.1 和 PowerShell 6.0 上运行此示例可生成不同的结果。

```powershell
$value = [PSCustomObject]@{Name='MyObject'}
if ( $value.count -eq 1 )
{
    "We have a value"
}
```

## <a name="empty-null"></a>空 null 值

有一种特殊类型的 `$null`，其行为与其他类型不同。 我要称它为空 `$null`，但它实际上是 [System.Management.Automation.Internal.AutomationNull][]。 此空 `$null` 是从不返回任何值的函数或脚本块得到的结（空结果）。

```powershell
PS> function Get-Nothing {}
PS> $nothing = Get-Nothing
PS> $null -eq $nothing
True
```

如果将其与 `$null` 比较，将得到值 `$null`。 在需要值的计算中使用时，此值始终为 `$null`。 但如果将其放在数组中，则会将其视为与空数组相同。

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

你可以有一个数组，其包含一个 `$null` 值，且其 `count` 为 `1`。 但如果将空结果置于数组中，则不会将其计为一个项。 计数为 `0`。

如果将空 `$null` 视为集合，则它为空。

### <a name="pipeline"></a>管道

出现差异的主要地方是使用管道时。 可以通过管道传递 `$null` 值，但不能传递空 `$null` 值。

```powershell
PS> $null | ForEach-Object{ Write-Output 'NULL Value' }
'NULL Value'
PS> $nothing | ForEach-Object{ Write-Output 'No Value' }
```

根据你的代码，你应在逻辑中考虑 `$null`。

先检查 `$null`

- 筛选出管道上的 null (`... | Where {$null -ne $_} | ...`)
- 在管道函数中进行处理

## <a name="foreach"></a>foreach

我最喜欢的 `foreach` 功能之一是它不会枚举 `$null` 集合。

```powershell
foreach ( $node in $null )
{
    #skipped
}
```

这样，我就不必在枚举前对集合执行 `$null` 检查。 如果你有一个 `$null` 值的集合，`$node` 仍可以为 `$null`。

从 PowerShell 3.0 起，Foreach 开始以此方式运行。 如果你使用的是较低版本，则不会出现这种情况。 在向后移植代码以实现 2.0 兼容性时，这是要注意的重要更改之一。

## <a name="value-types"></a>值类型

在技术上，只有引用类型可以为 `$null`。 但 PowerShell 非常宽松，允许变量为任意类型。 如果决定强键入值类型，其不能为 `$null`。
PowerShell 会将 `$null` 转换为许多类型的默认值。

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

某些类型从 `$null` 转换无效。 这些类型会生成 `Cannot convert null to type` 错误。

```powershell
PS> [datetime]$date = $null
Cannot convert null to type "System.DateTime".
At line:1 char:1
+ [datetime]$date = $null
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : MetadataError: (:) [], ArgumentTransformationMetadataException
    + FullyQualifiedErrorId : RuntimeException
```

### <a name="function-parameters"></a>函数参数

在函数参数中使用强类型值非常常见。 我们通常学习了如何定义参数的类型，即使我们倾向于不在脚本中定义其他变量的类型也是如此。 函数中可能已有一些强类型变量，你甚至可能没有意识到。

```powershell
function Do-Something
{
    param(
        [String] $Value
    )
}
```

将参数类型设置为 `string` 后，值永远不得为 `$null`。 通常会检查值是否为 `$null`，以了解用户是否提供了值。

```powershell
if ( $null -ne $Value ){...}
```

如果未提供任何值，则 `$Value` 为空字符串 `''`。 改为使用自动变量 `$PSBoundParameters.Value`。

```powershell
if ( $null -ne $PSBoundParameters.Value ){...}
```

`$PSBoundParameters` 仅包含调用函数时指定的参数。
你还可以使用 `ContainsKey` 方法来检查属性。

```powershell
if ( $PSBoundParameters.ContainsKey('Value') ){...}
```

### <a name="isnotnullorempty"></a>IsNotNullOrEmpty

如果值为字符串，则可以同时使用静态字符串函数检查值为 `$null` 还是空字符串。

```powershell
if ( -not [string]::IsNullOrEmpty( $value ) ){...}
```

在我知道值类型应为字符串时，我发现自己经常使用这种方法。

## <a name="when-i-null-check"></a>当我检查 $null 时

我是一个防守型脚本编写者。 每次调用函数并将其分配给变量时，我都会在其中检查 `$null`。

```powershell
$userList = Get-ADUser kevmar
if ($null -ne $userList){...}
```

与 `try/catch` 相比，我更喜欢使用 `if` 或 `foreach`。 别误会，我仍然会大量使用 `try/catch`。 但如果我可以测试错误条件或空结果集，则可以使我的异常处理用于真正的异常。

在对值编制索引或为对象调用方法之前，我还倾向于检查 `$null`。 对 `$null` 对象执行这两个操作失败，因此，我发现最好先对其进行验证。 我已经在本文前面介绍了这些方案。

### <a name="no-results-scenario"></a>无结果方案

了解这一点很重要：不同的函数和命令以不同方式处理无结果方案。 许多 PowerShell 命令返回空 `$null` 和错误流中的一个错误。 但其他命令会引发异常或向你提供状态对象。 但你仍可以决定是否要了解你所使用的命令如何处理无结果和错误方案。

## <a name="initializing-to-null"></a>初始化至 $null

我养成的一个习惯是，在使用之前初始化所有变量。 在其他语言中必须执行此操作。 在函数顶部或在输入 foreach 循环时，我会定义正在使用的所有值。

下面是一个方案，希望你能详细了解。 以下是我之前追踪的一个 bug 示例。

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

这里的预期目标是 `Get-Something` 返回一个结果或空 `$null`。 如果出现错误，我们会记录。 然后我们进行检查，以确保在处理之前得到了有效的结果。

隐藏在此代码中的 bug 是当 `Get-Something` 引发异常且未给 `$result` 赋值时。 它在赋值之前就失败了，因此我们不会将 `$null` 赋予 `$result` 变量。 `$result` 仍包含之前来自其他迭代的有效 `$result`。
`Update-Something` 在此示例中对同一对象执行多次。

我在 foreach 循环内部将 `$result` 设置为 `$null`，然后使用它来缓解此问题。

```powershell
foreach ( $node in 1..6 )
{
    $result = $null
    try
    {
        ...
```

### <a name="scope-issues"></a>作用域问题

这也有助于缓解作用域问题。 在该示例中，我们在循环中反复将值赋予 `$result`。 但由于 PowerShell 允许来自函数外部的变量值渗透到当前函数的作用域中，因此在函数内初始化它们可减少可能通过这种方式引入的 bug。

如果函数中未初始化的变量在父作用域中设置为一个值，其不会为 `$null`。
父作用域可能是调用你的函数并使用相同变量名称的另一个函数。

如果我使用同一个 `Do-something` 示例并删除循环，最终就会看到类似于以下示例的内容：

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

如果对 `Get-Something` 的调用引发了异常，则我的 `$null` 检查将从 `Invoke-Something` 查找 `$result`。 初始化函数内的值会缓解此问题。

命名变量很难，因此，作者通常会在多个函数中使用相同的变量名称。 我一直在使用 `$node`、`$result` 和 `$data`。 因此，来自不同作用域的值很容易出现在它们不该出现的地方。

## <a name="redirect-output-to-null"></a>将输出重定向到 $null

我们通篇都在讨论 `$null` 值，但如果不提将输出重定向到 `$null`，那么这个主题就不算完整。 有时，一些命令会输出你要禁止显示的信息或对象。 将输出重定向到 `$null` 会有此行为。

### <a name="out-null"></a>Out-Null

Out-Null 命令是将管道数据重定向到 `$null` 的内置方法。

```powershell
New-Item -Type Directory -Path $path | Out-Null
```

### <a name="assign-to-null"></a>分配给 $null

可以将命令的结果分配给 `$null`，以获得与使用 `Out-Null` 相同的结果。

```powershell
$null = New-Item -Type Directory -Path $path
```

由于 `$null` 是常量值，因此永远不能覆盖它。 我不喜欢它在代码中的显示方式，但它的执行速度通常比 `Out-Null` 快。

### <a name="redirect-to-null"></a>重定向到 $null

你还可以使用重定向运算符将输出发送到 `$null`。

```powershell
New-Item -Type Directory -Path $path > $null
```

如果要处理在不同流上输出的命令行可执行文件。 可以将所有输出流重定向到 `$null`，如下所示：

```powershell
git status *> $null
```

## <a name="summary"></a>总结

我在本文中介绍了许多有关此值的基础知识，但我知道这比我的大部分深入研究零碎得多。 这是因为 `$null` 值可以在 PowerShell 中的许多不同位置弹出，并且所有细微差别都特定于它的位置。 希望你在读完本文后能够更好地了解 `$null`，并意识到你可能会遇到更令人费解的情形。

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[好文章]: https://blog.iisreset.me/schrodingers-argumentlist
[PSScriptAnalyzer]: https://www.powershellgallery.com/packages/PSScriptAnalyzer
[System.Management.Automation.Internal.AutomationNull]: /dotnet/api/system.management.automation.internal.automationnull
