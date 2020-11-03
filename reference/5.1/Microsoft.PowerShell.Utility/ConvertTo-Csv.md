---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7d399661e4514c0a39ad00601d554c41c2897ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197964"
---
# ConvertTo-Csv

## 摘要
将 .NET 对象转换为一系列逗号分隔值 (CSV) 字符串。

## SYNTAX

### Delimiter（默认值）

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### UseCulture

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## DESCRIPTION

`ConvertTo-CSV`Cmdlet 将返回一系列逗号分隔值 (CSV) 字符串，这些字符串表示你提交的对象。 然后，可以使用 `ConvertFrom-Csv` cmdlet 从 CSV 字符串重新创建对象。 从 CSV 转换的对象是包含属性值和没有方法的原始对象的字符串值。

可以使用 `Export-Csv` cmdlet 将对象转换为 CSV 字符串。 `Export-CSV` 类似于 `ConvertTo-CSV` ，只不过它将 CSV 字符串保存到文件。

`ConvertTo-CSV`Cmdlet 具有参数以指定逗号以外的分隔符，或使用当前区域性作为分隔符。

## 示例

### 示例1：将对象转换为 CSV

此示例将 **进程** 对象转换为 CSV 字符串。

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

该 `Get-Process` cmdlet 将获取 **Process** 对象，并使用 **Name** 参数来指定 PowerShell 进程。 进程对象将通过管道向下发送到 `ConvertTo-CSV` cmdlet。 `ConvertTo-CSV`Cmdlet 可将对象转换为 CSV 字符串。 **NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。

### 示例2：将 DateTime 对象转换为 CSV

此示例将 **DateTime** 对象转换为 CSV 字符串。

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

该 `Get-Date` cmdlet 将获取 **DateTime** 对象并将其保存在 `$Date` 变量中。 `ConvertTo-Csv`Cmdlet 将 **DateTime** 对象转换为字符串。 **InputObject** 参数使用存储在变量中的 **DateTime** 对象 `$Date` 。 **分隔符** 参数指定用分号分隔字符串值。 **NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。

### 示例3：将 PowerShell 事件日志转换为 CSV

此示例将 PowerShell 的 Windows 事件日志转换为一系列 CSV 字符串。

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

该 `Get-Culture` cmdlet 使用嵌套属性 **TextInfo** 和 **ListSeparator** ，并显示当前区域性的默认列表分隔符。 该 `Get-WinEvent` cmdlet 将获取事件日志对象，并使用 **LogName** 参数来指定日志文件名。 事件日志对象通过管道发送到 `ConvertTo-Csv` cmdlet。 `ConvertTo-Csv`Cmdlet 将事件日志对象转换为一系列 CSV 字符串。 **UseCulture** 参数使用当前区域性的默认列表分隔符作为分隔符。 **NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。

## PARAMETERS

### -Delimiter

指定分隔 CSV 字符串中的属性值的分隔符。 默认值为逗号 (`,`) 。 输入一个字符，例如冒号 (`:`) 。 若要指定分号 (`;`) 将其括在单引号内。

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

指定转换为 CSV 字符串的对象。 输入一个包含对象的变量，或键入可获取对象的命令或表达式。 还可以通过管道将对象传递给 `ConvertTo-CSV` 。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -NoTypeInformation

从输出中删除 **#TYPE** 信息标头。 此参数已成为 PowerShell 6.0 中的默认参数，包含它是为了向后兼容。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCulture

将当前区域性的列表分隔符用作项分隔符。 若要查找区域性的列表分隔符，请使用以下命令： `(Get-Culture).TextInfo.ListSeparator` 。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.Management.Automation.PSObject

可以通过管道将具有扩展类型系统 (ETS) 适配器的任何对象传递给 `ConvertTo-CSV` 。

## 输出

### System.String

CSV 输出将作为字符串集合返回。

## 注释

采用 CSV 格式时，通过以逗号分隔的对象属性值列表来表示每个对象。 使用对象的 **ToString ( # B1** 方法将属性值转换为字符串。 字符串由属性值名称表示。 `ConvertTo-CSV` 不导出对象的方法。

CSV 字符串的输出如下所示：

- 默认情况下，第一个字符串包含后跟对象类型的完全限定名称的 **#TYPE** 信息标头。 例如， **#TYPE** "。
- 如果使用 **NoTypeInformation** ，则第一个字符串包括列标题。 标头以逗号分隔的列表的形式包含第一个对象的属性名称。
- 其余字符串包含每个对象的属性值的逗号分隔列表。

当您将多个对象提交到时 `ConvertTo-CSV` ，将 `ConvertTo-CSV` 根据您提交的第一个对象的属性对字符串进行排序。 如果剩余的对象没有指定的属性之一，则该对象的属性值为 Null，由两个连续的逗号表示。 如果剩余的对象具有其他属性，则忽略这些属性值。

## 相关链接

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[Export-Csv](Export-Csv.md)

[Import-Csv](Import-Csv.md)
