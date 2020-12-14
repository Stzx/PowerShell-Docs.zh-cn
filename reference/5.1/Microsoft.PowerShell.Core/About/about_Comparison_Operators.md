---
description: 描述在 PowerShell 中比较值的运算符。
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: ba671ae51d458a2e0074a85d4de859795c20a3d5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "97069897"
---
# <a name="about-comparison-operators"></a>关于比较运算符

## <a name="short-description"></a>简短说明
描述在 PowerShell 中比较值的运算符。

## <a name="long-description"></a>长说明

比较运算符使你可以指定比较值和查找与指定模式匹配的值的条件。 若要使用比较运算符，请指定要与这些值分隔的运算符进行比较的值。

PowerShell 包含以下比较运算符：

| 类型        | 运算符    | 说明                                 |
| ----------- | ------------ | --------------------------------------------|
| 相等    | -eq          | equals                                      |
|             | -ne          | 不等于                                  |
|             | -gt          | 大于                                |
|             | -ge          | 大于或等于                       |
|             | -lt          | 小于                                   |
|             | -le          | 小于或等于                          |
|             |              |                                             |
| Matching    | -like        | 如果字符串匹配通配符，则返回 true   |
|             |              | pattern                                     |
|             | -notlike     | 如果字符串不匹配，则返回 true     |
|             |              | 通配符模式                            |
|             | -match       | 如果字符串与正则表达式匹配，则返回 true      |
|             |              | 化$matches 包含匹配的字符串 |
|             | -notmatch    | 如果字符串不匹配，则返回 true     |
|             |              | regex 模式;$matches 包含匹配   |
|             |              | 字符串                                     |
|             |              |                                             |
| Containment | -contains    | 如果引用值包含，则返回 true |
|             |              | 在集合中                             |
|             | -notcontains | 如果引用值不为，则返回 true       |
|             |              | 包含在集合中                   |
|             | -in          | 如果中包含的测试值为 |
|             |              | collection                                  |
|             | -notin       | 如果测试值不包含，则返回 true  |
|             |              | 在集合中                             |
|             |              |                                             |
| Replacement | -replace     | 替换字符串模式                   |
|             |              |                                             |
| 类型        | -为          | 如果两个对象相同，则返回 true    |
|             |              | 类型                                        |
|             | -isnot       | 如果对象不相同，则返回 true|
|             |              | 类型                                        |

默认情况下，所有比较运算符都不区分大小写。 若要使比较运算符区分大小写，请在运算符名称之前加 `c` 。 例如，区分大小写的版本 `-eq` 为 `-ceq` 。 若要使不区分大小写的显式，请在运算符前面加上 `i` 。 例如，的显式不区分大小写的版本 `-eq` 为 `-ieq` 。

当运算符的输入是标量值时，比较运算符将返回一个布尔值。 当输入是值的集合时，比较运算符返回任何匹配值。 如果集合中没有匹配项，则比较运算符返回空数组。

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

例外情况包括：包含运算符、In 运算符和类型运算符，它们始终返回 **布尔** 值。

> [!NOTE]
> 如果需要比较值， `$null` 应将该值放 `$null` 在比较的左侧。 当与 `$null` **对象 []** 进行比较时，结果为 **False** ，因为比较对象是一个数组。 将数组与进行比较时 `$null` ，比较筛选出 `$null` 存储在数组中的所有值。 例如：
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a>相等运算符

相等运算符 (`-eq` ， `-ne`) 在一个或多个输入值与指定模式相同时返回值或匹配项。 整个模式必须匹配整个值。

示例：

### <a name="-eq"></a>-eq

说明：等于。 包含相同的值。

示例：

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

### <a name="-ne"></a>-ne

说明：不等于。 包含不同的值。

示例：

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

### <a name="-gt"></a>-gt

说明：大于。

示例：

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> 这不应与 `>` 其他许多编程语言中的大于运算符混淆。 在 PowerShell 中， `>` 用于重定向。 有关详细信息，请参阅 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)。

### <a name="-ge"></a>-ge

说明：大于或等于。

示例：

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a>-lt

说明：小于。

示例：

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a>-le

说明：小于或等于。

示例：

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a>匹配运算符

Like 运算符 (`-like` 和 `-notlike`) 使用通配符表达式查找匹配或与指定模式不匹配的元素。

语法为：

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

匹配运算符 (`-match` 和 `-notmatch`) 使用正则表达式查找匹配或与指定模式不匹配的元素。

`$Matches`当输入 (左侧参数) 为单个标量对象时，匹配运算符将填充自动变量。 当输入是标量时， `-match` 和 `-notmatch` 运算符将返回一个布尔值，并将自动变量的值设置 `$Matches` 为参数的匹配组件。

语法为：

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a>-like

说明：使用通配符)  (匹配 \* 。

示例：

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a>-notlike

说明：使用通配符 () 不匹配 \* 。

示例：

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a>-match

说明：使用正则表达式匹配字符串。 当输入是标量时，它将填充 `$Matches` 自动变量。

如果输入是集合，则 `-match` 和 `-notmatch` 运算符返回该集合的匹配成员，但是运算符不填充该 `$Matches` 变量。

例如，以下命令将字符串的集合提交给 `-match` 运算符。 `-match`运算符返回集合中的匹配项。 它不填充 `$Matches` 自动变量。

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

与此相反，以下命令将单个字符串提交给 `-match` 运算符。 `-match`运算符返回布尔值并填充 `$Matches` 自动变量。 `$Matches`自动变量是 **哈希表**。 如果未使用分组或捕获，则只填充一个键。
`0`键表示匹配的所有文本。 有关使用正则表达式进行分组和捕获的详细信息，请参阅 [about_Regular_Expressions](about_Regular_Expressions.md)。

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

请注意， `$Matches` 哈希表只包含任何匹配模式的第一个匹配项。

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> `0`该键是一个 **整数**。 您可以使用任何 **哈希表** 方法来访问存储的值。
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

`-notmatch` `$Matches` 当输入是标量时，运算符将填充自动变量，并且在检测到匹配项时，结果为 False。

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

### <a name="-notmatch"></a>-notmatch

说明：不匹配字符串。 使用正则表达式。 当输入是标量时，它将填充 `$Matches` 自动变量。

示例：

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

## <a name="containment-operators"></a>包含运算符

包含运算符 (`-contains` 和 `-notcontains`) 类似于相等运算符。 但是，包含运算符始终返回布尔值，即使输入是集合也是如此。

另外，与相等运算符不同，包含运算符在检测到第一个匹配项后就会返回一个值。 相等运算符计算所有输入，然后返回集合中的所有匹配项。

### <a name="-contains"></a>-contains

Description：包含运算符。 指示引用值的集合是否包含一个测试值。 始终返回一个布尔值。 仅当测试值与至少一个引用值完全匹配时才返回 TRUE。

如果测试值是集合，则 Contains 运算符使用引用相等性。 仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。

在非常大的集合中， `-contains` 运算符比等于运算符更快地返回结果。

语法：

`<Reference-values> -contains <Test-value>`

示例：

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

### <a name="-notcontains"></a>-notcontains

Description：包含运算符。 指示引用值的集合是否包含一个测试值。 始终返回一个布尔值。 如果测试值不是至少一个引用值的完全匹配项，则返回 TRUE。

如果测试值是集合，则 NotContains 运算符使用引用相等性。

语法：

`<Reference-values> -notcontains <Test-value>`

示例：

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

### <a name="-in"></a>-in

说明： In 运算符。 指示测试值是否显示在引用值的集合中。 始终以布尔值的形式返回。 仅当测试值与至少一个引用值完全匹配时才返回 TRUE。

如果测试值是集合，则 In 运算符使用引用相等性。
仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。

此 `-in` 操作员是在 PowerShell 3.0 中引入的。

语法：

`<Test-value> -in <Reference-values>`

示例：

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

### <a name="-notin"></a>-notin

说明：指示测试值是否显示在引用值的集合中。 始终返回一个布尔值。 如果测试值不是至少一个引用值的完全匹配项，则返回 TRUE。

如果测试值是集合，则 In 运算符使用引用相等性。
仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。

此 `-notin` 操作员是在 PowerShell 3.0 中引入的。

语法：

`<Test-value> -notin <Reference-values>`

示例：

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

## <a name="replacement-operator"></a>替换运算符

`-replace`运算符具有以下语法：

`<input> -replace <original>, <substitute>`

`<original>`占位符是与要替换的字符匹配的正则表达式。 `<substitute>`占位符是替换它们的文本字符串。

使用正则表达式将运算符替换为指定值的全部或部分值。 对于许多管理任务（如重命名文件），都可以使用运算符。 例如，以下命令将所有文件的文件扩展名更改 `.txt` 为 `.log` ：

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a>区分大小写的匹配

默认情况下， `-replace` 运算符不区分大小写。 若要区分大小写，请使用 `-creplace` 。 若要使它显式不区分大小写，请使用 `-ireplace` 。

请开考虑以下示例：

```powershell
PS> "book" -replace "B", "C"
Cook
```

```powershell
PS> "book" -ireplace "B", "C"
Cook
```

```powershell
PS> "book" -creplace "B", "C"
book
```

### <a name="substitutions-in-regular-expressions"></a>正则表达式中的替换

还可以使用正则表达式，使用捕获组和替换动态替换文本。 可以 `<substitute>` 使用分组标识符之前的美元符号 () 字符，在字符串中引用捕获组 `$` 。

捕获组可以按 **数字** 或 **名称** 引用

- 按 **编号** 捕获组按从左到右的顺序进行编号。

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- 通过 **名称** ，也可以按名称引用捕获组。

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> 由于 `$` 字符是在字符串扩展中使用的，因此必须使用文本字符串或对 `$` 字符进行转义。
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> 此外，由于 `$` 字符用于替换，因此必须对字符串中的任何实例进行转义。
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

若要了解详细信息，请参阅[正则表达式中的](/dotnet/standard/base-types/substitutions-in-regular-expressions) [about_Regular_Expressions](about_Regular_Expressions.md)和替换

### <a name="substituting-in-a-collection"></a>在集合中替换

如果 `<input>` 到运算符为 `-replace` 集合，则 PowerShell 会将替换应用于集合中的每个值。 例如：

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

## <a name="type-comparison"></a>类型比较

 (和) 的类型比较运算符 `-is` `-isnot` 用于确定对象是否为特定类型。

### <a name="-is"></a>-为

语法：

`<object> -is <type reference>`

例如：

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a>-isnot

语法：

`<object> -isnot <type reference>`

例如：

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a>请参阅

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [Foreach-对象](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
