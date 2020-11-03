---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 64275e72f8c21942179431b3aed4a17d328aa2e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198611"
---
# Format-Hex

## 摘要

将文件或其他输入显示为十六进制。

## SYNTAX

### Path（默认值）

```
Format-Hex [-Path] <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### InputObject

```
Format-Hex -InputObject <psobject> [-Encoding <Encoding>] [-Count <long>] [-Offset <long>] [-Raw] [<CommonParameters>]
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

若要测试以下命令，请在本地计算机上创建现有 PDF 文件的副本，并将复制的文件重命名为 `File.t7f` 。

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

`Format-Hex`Cmdlet 使用 **Path** 参数来指定当前目录 **t7f** 中的文件名。 文件扩展名 **t7f** 不常见，但十六进制输出 **% PDF** 显示它是 PDF 文件。

## PARAMETERS

### -Encoding

指定输出的编码。 这仅适用于 `[string]` 输入。 参数对数值类型不起作用。 默认值是 `utf8NoBOM`。

此参数可接受的值如下所示：

- `ascii`：使用 ASCII (7 位) 字符集的编码。
- `bigendianunicode`：使用大字节序字节顺序对 UTF-16 格式进行编码。
- `oem`：使用 MS-DOS 和控制台程序的默认编码。
- `unicode`：使用小 endian 字节顺序对 UTF-16 格式进行编码。
- `utf7`：以 UTF-7 格式进行编码。
- `utf8`：以 UTF-8 格式进行编码。
- `utf8BOM`：以 UTF-8 格式编码 (BOM) 
- `utf8NoBOM`：以 UTF-8 格式编码，而不包含字节顺序标记 (BOM) 
- `utf32`：以32格式编码。

从 PowerShell 6.2 开始， **Encoding** 参数还允许已注册代码页的数字 id (如 `-Encoding 1251` (如) 所注册代码页的) 或字符串名称 `-Encoding "windows-1251"` 。 有关详细信息，请参阅 .NET 文档中的[编码。](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)

```yaml
Type: Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

用于管道输入。 管道输入仅支持特定于管道的标量类型和 `[system.io.fileinfo]` 实例 `Get-ChildItem` 。

支持的标量类型为：

- `[string]`, `[char]`
- `[byte]`, `[sbyte]`
- `[int16]`, `[uint16]`, `[short]`, `[ushort]`
- `[int]`, `[uint]`, `[int32]`, `[uint32]`,
- `[long]`, `[ulong]`, `[int64]`, `[uint64]`
- `[single]`, `[float]`, `[double]`

```yaml
Type: System.Management.Automation.PSObject
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
Aliases: PSPath, LP

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

此参数不再执行任何操作。 它保留用于脚本兼容性。

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

### -Offset

这表示要从十六进制输出中跳过的字节数。

此参数是在 PowerShell 6.2 中引入的。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Count

这表示要包含在十六进制输出中的字节数。

此参数是在 PowerShell 6.2 中引入的。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
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

输出的最右侧列尝试将字节呈现为 ASCII 字符：

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
