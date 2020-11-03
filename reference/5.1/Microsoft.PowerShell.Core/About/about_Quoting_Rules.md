---
description: 描述在 PowerShell 中使用单引号和双引号的规则。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 3a858039a9128235d1b920223ca0fcc3d0b0f6c0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200085"
---
# <a name="about-quoting-rules"></a>关于报价规则

## <a name="short-description"></a>简短说明
描述在 PowerShell 中使用单引号和双引号的规则。

## <a name="long-description"></a>详细说明

引号用于指定文本字符串。 可以用单引号将字符串括起来 (`'`) 或双引号 (`"`) 。

引号还用于创建此处字符串。 此处-字符串是用单引号或双引号括起来的字符串，其中的引号按原义解释。 此处的字符串可以跨多个行。 此处字符串中的所有行都被解释为字符串，即使它们没有用引号引起来。

在远程计算机的命令中，引号定义在远程计算机上运行的命令的各个部分。 在远程会话中，引号还确定命令中的变量是在本地计算机上还是在远程计算机上首先解释。

### <a name="single-and-double-quoted-strings"></a>单引号和双引号字符串

用双引号将字符串括起来时 (用双引号引起来) ，在将 `$` 字符串传递到命令进行处理之前，将用变量的值替换前面带有美元符号 () 的变量名称。

例如：

```powershell
$i = 5
"The value of $i is $i."
```

此命令的输出为：

```Output
The value of 5 is 5.
```

此外，在带双引号的字符串中，将计算表达式，并将结果插入字符串中。 例如：

```powershell
"The value of $(2+3) is 5."
```

此命令的输出为：

```Output
The value of 5 is 5.
```

如果将字符串括在单引号中 (单引号的字符串) ，则该字符串将与你键入的内容完全相同。 不执行任何替换。 例如：

```powershell
$i = 5
'The value of $i is $i.'
```

此命令的输出为：

```Output
The value $i is $i.
```

同样，不计算用单引号字符串括起来的表达式。 它们被解释为文本。 例如：

```powershell
'The value of $(2+3) is 5.'
```

此命令的输出为：

```Output
The value of $(2+3) is 5.
```

若要防止用双引号替换变量值，请使用反撇号字符 (`` ` ``) # B2 ASCII 96) ，这是 PowerShell 转义符。

在下面的示例中，第一个 $i 变量之前的反撇号字符会阻止 PowerShell 将变量名称替换为其值。
例如：

```powershell
$i = 5
"The value of `$i is $i."
```

此命令的输出为：

```Output
The value $i is 5.
```

若要使双引号出现在字符串中，请将整个字符串用单引号引起来。 例如：

```powershell
'As they say, "live and learn."'
```

此命令的输出为：

```Output
As they say, "live and learn."
```

还可以在带引号的字符串中包含单引号字符串。 例如：

```powershell
"As they say, 'live and learn.'"
```

此命令的输出为：

```Output
As they say, 'live and learn.'
```

或者，用双引号将引号括起来。 例如：

```powershell
"As they say, ""live and learn."""
```

此命令的输出为：

```Output
As they say, "live and learn."
```

若要在单引号字符串中包含单引号，请使用第二个连续的单引号。 例如：

```powershell
'don''t'
```

此命令的输出为：

```Output
don't
```

若要强制 PowerShell 按字面解释双引号，请使用反撇号字符。 这会阻止 PowerShell 将引号解释为字符串分隔符。 例如：

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

由于单引号字符串的内容按原义解释，因此，反撇号字符被视为文本字符并显示在输出中。

### <a name="here-strings"></a>此处-字符串

此处的引号规则与字符串略有不同。

此处-字符串是用单引号或双引号括起来的字符串，其中的引号按原义解释。 此处的字符串可以跨多个行。 此处字符串中的所有行都被解释为字符串，即使它们没有用引号引起来。

与规则字符串一样，变量在此处用双引号引起来。 在此处使用单引号的字符串中，变量的值不会被替换。

对于任何文本，您可以使用此处的字符串，但对于以下类型的文本特别有用：

- 包含文本引号的文本
- 多行文本，如 HTML 或 XML 中的文本
- 脚本或函数文档的帮助文本

此处的字符串可以采用以下两种格式之一，其中 `<Enter>` 表示按下 <kbd>enter</kbd> 键时添加的换行符或换行符。

双引号：

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

单引号：

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

无论采用哪种格式，右引号都必须是行中的第一个字符。

此处-字符串包含两个隐藏字符之间的所有文本。 在此处字符串中，所有引号都按原义解释。 例如：

```powershell
@"
For help, type "get-help"
"@
```

此命令的输出为：

```Output
For help, type "get-help"
```

使用此处字符串可简化在命令中使用字符串的情况。 例如：

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

此命令的输出为：

```Output
Use a quotation mark (') to begin a string.
```

在此处用单引号括起来的字符串中，变量按原义解释和重现。 例如：

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

此命令的输出为：

```Output
The $profile variable contains the path
of your PowerShell profile.
```

在后面加双引号的字符串中，变量被替换为其值。 例如：

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

此命令的输出为：

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

此处-通常使用字符串将多个行分配给一个变量。 例如，下面的字符串将一个 XML 页分配给 $page 变量。

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

此处-对于向 cmdlet 进行的输入，字符串也是一种方便的格式，这种格式会 `ConvertFrom-StringData` 将字符串转换为哈希表。
有关详细信息，请参阅 `ConvertFrom-StringData`。

## <a name="see-also"></a>另请参阅

[about_Special_Characters](about_Special_Characters.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
