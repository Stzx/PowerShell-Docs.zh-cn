---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197937"
---
# Format-Hex

## 摘要

将文件或其他输入显示为十六进制。

## SYNTAX

### Path（默认值）

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### ByInputObject

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Format-Hex`Cmdlet 将文件或其他输入显示为十六进制值。 若要确定输出中的字符的偏移量，请将行最左侧的数字与该字符所在列顶部的数字相加。

此 `Format-Hex` cmdlet 可帮助你确定损坏文件的文件类型或可能不具有文件扩展名的文件。 您可以运行此 cmdlet，然后读取十六进制输出以获取文件信息。

`Format-Hex`对文件使用时，该 cmdlet 将忽略换行符，并将保留了换行符的文件中的全部内容返回。

## 示例

### 示例 1：获取字符串的十六进制表示形式

此命令返回字符串的十六进制值。

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

字符串 **Hello World** 会沿管道向下发送到 `Format-Hex` cmdlet。 的十六进制输出 `Format-Hex` 显示字符串中每个字符的值。

### 示例2：从十六进制输出中查找文件类型

此示例使用十六进制输出来确定文件类型。 Cmdlet 显示文件的完整路径和十六进制值。

若要测试以下命令，请在本地计算机上创建现有 PDF 文件的副本，并将复制的文件重命名为 **t7f** 。

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

`Format-Hex`Cmdlet 使用 **Path** 参数来指定当前目录中的文件名 `File.t7f` 。 文件扩展名 `.t7f` 不常见，但十六进制输出 `%PDF` 显示它是 PDF 文件。

### 示例3：显示原始十六进制输出

默认情况下， `Format-Hex` 对于数值数据类型，可以使用单字节和双字节序列。 **原始** 参数停用此行为。

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

请注意输出中的差异。 **Raw** 参数将数字显示为4字节值，将其值显示为 **Int32** 类型。

## PARAMETERS

### -Encoding

指定输出的编码。 这仅适用于 `[string]` 输入。 参数对数值类型不起作用。 默认值是 `ASCII`。

此参数可接受的值如下所示：

- `Ascii` 使用 ASCII (7 位) 字符集。
- `BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。
- `Unicode` 使用带有小 endian 字节顺序的 UTF-16。
- `UTF7` 使用 UTF-8。
- `UTF8` 使用 UTF-8。
- `UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。

输入中的非 ASCII 字符输出为原义 `?` 字符，导致信息丢失。

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

用于管道输入。 管道输入仅支持特定于管道的标量类型和 `[system.io.fileinfo]` 实例 `Get-ChildItem` 。

支持的标量类型为：

- `[string]`
- `[byte]`
- `[int]`, `[int32]`
- `[long]`, `[int64]`

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

指定文件的完整路径。 **LiteralPath** 的值严格按照所键入的形式使用。
此参数不接受通配符。 若要指定文件的多个路径，请使用逗号分隔这些路径。 如果 **LiteralPath** 参数包含转义符，请将路径用单引号引起来。 PowerShell 不会将单个带引号的字符串中的任何字符解释为转义序列。 有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定文件的路径。 使用点)  (`.` 指定当前位置。 通配符 (`*`) 是可接受的，并且可用于指定位置中的所有项。 如果 **path** 参数包含转义符，请将路径用单引号引起来。 若要指定文件的多个路径，请使用逗号分隔这些路径。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Raw

默认情况下， `Format-Hex` 对于数值数据类型，可以使用单字节和双字节序列。 **原始** 参数停用此行为。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
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

### System.String

可以通过管道将字符串传递给此 cmdlet。

## 输出

### Microsoft.PowerShell.Commands.ByteCollection

此 cmdlet 返回 **ByteCollection** 。 此对象表示字节的集合。 它包含一些方法，这些方法可将字节的集合转换为格式类似于返回的每个输出行的字符串 `Format-Hex` 。 如果指定 Path  或 LiteralPath  参数，则该对象还包含其中含有每个字节的文件的路径。

## 注释

输出的最右侧列尝试将字节呈现为字符：

通常，每个字节都被解释为 Unicode 码位，这意味着：

- 可打印的 ASCII 字符始终正确呈现
- 多字节 UTF-8 字符永远无法正确呈现
- 只有在高序位字节发生的情况下，UTF-16 字符才会正确呈现 `NUL` 。

## 相关链接

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Format-Custom](Format-Custom.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
