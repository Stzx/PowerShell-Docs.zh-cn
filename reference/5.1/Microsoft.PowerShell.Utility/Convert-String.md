---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197967"
---
# Convert-String

## 摘要
格式化字符串以匹配示例。

## SYNTAX

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## DESCRIPTION

**转换字符串** cmdlet 将字符串的格式设置为与示例格式匹配。

## 示例

### 示例1：转换字符串格式

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

第一个命令创建一个包含名字和姓氏的数组。

第二个命令根据示例设置名称的格式。
它将姓放在输出中，后跟一个初始。

### 示例2：简化字符串的格式

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

第一个命令创建一个包含名字、中间名和姓氏的数组。
请注意，最后一个条目没有中间名。

第二个命令根据示例设置名称的格式。
它将姓氏置于输出的开头，后接名字。
删除所有中间名;没有中间名的条目得到正确处理。

### 示例3：当字符串不匹配示例时的输出管理

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

第一个命令创建一个包含名字、中间名和姓氏的数组。
请注意，最后一个条目没有中间名。

第二个命令根据示例设置名称的格式。
它将 **中间名** 放在输出的开头，后跟名字。
将跳过 **$Composers** 中的最后一项，因为它不匹配示例模式：它没有中间名。

### 示例4：对美空格注意事项

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

第一个命令创建名字和姓氏的数组。
请注意，第二个和第四项在姓氏之后有多余的尾随空格。

第二个命令将转换与示例模式匹配的所有字符串： _单词、空格、单词和最后尾随空格，并_ 在等号之前进行。
另外，请注意输出中的前导空格。

### 示例5：设置具有多个模式的进程信息的格式

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

**$ExamplePatterns** 通过示例定义数据中的不同预期模式。

第一种模式是 `@{before='"Hello","World"'; after='World: Hello'}` 按如下所示读取：应为这样 _的字符串：字词括在双引号中，然后是逗号，_ 
 _最后是括在引号中的第二个和最后一个单词。_ 
_字符串中没有空格。输出：在不使用引号的情况下，首先放置第二个单词，_ 
 _不使用引号，然后输入单个空格和第一个单词。_

第二种模式是 `@{before='"Hello","1"'; after='1: Hello'}` 按如下所示读取：应为这样 _的字符串：字词括在双引号中，然后是逗号，_ 然后 
 _是用引号引起来的数字;_ 
_字符串中没有空格。在输出上：将数字置于第一，_ 
 _不使用引号，然后是单个空格，然后是不带引号的单词。_

第三种模式是按如下所示 `@{before='"Hello-World","22"'; after='22: Hello-World'}` 读取： _需要字符串，其中两个单词之间有连字符，中间用双引号括起来_ 
 _，然后是逗号，然后是用引号引起来的数字。_ 
_逗号和第三个双引号之间没有空格。_ 
_在输出上：首先放置数字，不使用引号，然后输入单个空格，_ 
再 _加上带引号的单词。_

第四个和最后一种模式，如下所示 `@{before='"hello world","333"'; after='333: hello world'}` ： _需要字符串，其中两个单词之间有一个空格，中间用双引号括起来_ 
 _，然后是逗号，然后是用引号引起来的数字。_ 
_逗号和第三个双引号之间没有空格。_ 
_在输出上：首先放置数字，不使用引号，然后输入单个空格，_ 
然后 _是带有空格的单词，无引号。_

第一个命令使用 Get-Process cmdlet 获取所有进程。
命令将它们传递给 Select-Object cmdlet，后者将选择进程名称和进程 ID。 在管道的末尾，命令使用 ConvertTo-Csv cmdlet 将输出转换为逗号分隔值，而不包含类型信息。
该命令将结果存储在 **$Processes** 变量中。
**$Processes** 现在包含进程名称和 PID。

第二个命令指定更改输入项顺序的示例变量。
该命令将 **$Processes** 中的每个字符串。

>**注意** 第四种模式隐式指出了两个或多个由空格分隔的单词。
>
>如果没有第四种模式，则仅匹配括在双引号中的字符串的第一个单词。

## PARAMETERS

### -示例

指定目标格式的示例列表。
指定由相等 (=) 符号分隔的对，左侧有源模式，右侧有目标模式，如以下示例中所示：

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

>**注意** 第二个示例使用模式列表

另外 **，还可** 指定包含 **前后** 属性的哈希表的列表。

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

>**警告** 避免在等号前后使用空格，因为它们被视为模式的一部分。

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

指定要设置格式的字符串。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 字符串

可以通过管道将字符串传递给此 cmdlet。

## 输出

### 字符串

此 cmdlet 将返回一个字符串。

## 注释

## 相关链接

[ConvertFrom-String](ConvertFrom-String.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Out-String](Out-String.md)

[Select-Object](Select-Object.md)
