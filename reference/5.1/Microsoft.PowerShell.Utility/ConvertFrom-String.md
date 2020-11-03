---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "93199379"
---
# ConvertFrom-String

## 摘要
从字符串内容中提取并分析结构化对象。

## SYNTAX

### ByDelimiter（默认值）

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### TemplateParsing

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

**ConvertFrom-String** cmdlet 提取并分析字符串内容中的结构化属性。
此 cmdlet 通过分析传统文本流中的文本，生成对象。
对于管道中的每个字符串，该 cmdlet 通过分隔符或分析表达式拆分输入，然后将属性名称分配给每个由此得到的拆分元素。
可提供这些属性名称；如果不提供，它们将自动生成。

该 cmdlet 的默认参数集 **ByDelimiter** 严格通过正则表达式分隔符进行拆分。
与 cmdlet 一样，它不执行引号匹配或分隔符转义 `Import-Csv` 。

该 cmdlet 的可选参数集 TemplateParsing  从正则表达式捕获的组中生成元素。 有关正则表达式的详细信息，请参阅 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)。

此 cmdlet 支持两种模式：基本分隔分析和自动生成的示例驱动的分析。

默认情况下，分隔分析会在空格处将输入拆分，并为得到的组分配属性名称。

可以通过将结果通过管道传递 `ConvertFrom-String` 到其中一个 cmdlet 来自定义分隔符 `Format-*` ，也可以使用 **分隔符** 参数。

该 cmdlet 还支持 [Microsoft Research 的 FlashExtract 研究工作](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/)的自动生成的示例驱动的分析。

## 示例

### 示例 1：生成具有默认属性名称的对象

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

此命令将生成具有默认属性名称 **P1** 和 **P2** 的对象。

### 示例 1A：了解生成对象

此命令生成一个对象，属性为 **P1** ， **P2** ;默认情况下，这两个属性均为 **字符串** 类型。

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### 示例 2：使用分隔符生成具有默认属性名称的对象

此命令使用反斜杠 () 作为分隔符，生成包含域和用户名的对象 `\` 。 使用正则表达式时，反斜杠字符必须使用另一个反斜杠进行转义。

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### 示例 3：生成包含两个命名属性的对象

下面的示例从 Windows hosts 文件项创建对象。

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

`Get-Content`Cmdlet 将 Windows hosts 文件的内容存储在中 `$content` 。 第二个命令使用与不以 () 开头的任何行匹配的正则表达式删除 hosts 文件开头的所有注释 `#` 。 最后一个命令将剩余文本转换为具有 **服务器** 和 **IP** 属性的对象。

### 示例 4：将表达式用作 TemplateContent 参数的值，将结果保存到变量中。

此命令将表达式用作 TemplateContent  参数的值。
为简单起见，表达式保存在变量中。
Windows PowerShell 现在知道，管道上用于的字符串 `ConvertFrom-String` 具有三个属性：

- **名称**
- **phone**
- **年**

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

输入中的每一行都按样本匹配项进行计算。 如果行与模式中给定的示例匹配，则提取值并将其传递给输出变量。

示例数据 `$template` 提供了两种不同的电话格式：

- `425-123-6789`
- `(206) 987-4321`

示例数据还提供了两种不同的 age 格式：

- `6`
- `12`

这意味着将无法识别像这样的手机 `(206) 987 4321` ，因为没有与该模式匹配的示例数据，因为没有连字符。

### 示例 5：为生成的属性指定数据类型

此示例与上面的示例4相同。
不同之处在于模式字符串包含每个所需属性的数据类型。

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

`Get-Member`Cmdlet 用于显示 **age** 属性为整数。

## PARAMETERS

### -Delimiter

指定用于标识元素之间边界的正则表达式。
通过拆分创建的元素将成为生成的对象中的属性。
在对类型的 **Split** 方法的调用中，将最终使用分隔符 `[System.Text.RegularExpressions.RegularExpression]` 。

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeExtent

指示此 cmdlet 包括默认删除的扩展文本属性。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

指定从管道接收到的字符串，或包含字符串对象的变量。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PropertyNames

指定要向其分配生成对象中的拆分值的属性名称数组。
拆分或分析的每个文本行将生成表示属性值的元素。
如果该元素是捕获组的结果，并且该捕获组命名为 (例如 `(?<name>)` 或 `(?'name')` ) ，则该捕获组的名称将分配给该属性。

如果提供 PropertyName  数组中的任何元素，则这些名称将分配给尚未命名的属性。

如果提供的属性名称比字段多，则 PowerShell 将忽略额外的属性名称。 如果未指定足够的属性名称来命名所有字段，则 PowerShell 会自动将数值属性名称分配给任何未命名的属性： **P1** 、 **P2** 等。

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateContent

指定一个表达式，或一个保存为变量的表达式，用于描述此 cmdlet 会将字符串分配到的属性。 模板字段规范的语法如下所示： `{[optional-typecast]<name>:<example-value>}` 。

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFile

将文件指定为数组，包含所需的字符串分析的模板。
在模板文件中，属性及其值括在括号中，如下所示。
如果多次显示某个属性（如 **Name** 属性及其关联的其他属性），则可以添加一个星号 (`*`) ，以指示这会导致多个记录。 这样可避免将多个属性提取到单个记录中。

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateTemplate

指示此 cmdlet 将学习算法的结果保存到模板文件中的注释内。
这可加快算法学习过程的速度。
若要使用此参数，还必须指定具有 TemplateFile  参数的模板文件。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.String

## 输出

## 注释

## 相关链接

[ConvertFrom-String: Example-based text parsing](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)（ConvertFrom-String：基于示例的文本分析）

[ConvertFrom-StringData](ConvertFrom-StringData.md)

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Xml](ConvertTo-Xml.md)
