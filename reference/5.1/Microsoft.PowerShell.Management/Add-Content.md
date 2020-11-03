---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198333"
---
# Add-Content

## 摘要
向指定的项中添加内容，如向文件中添加字词。

## SYNTAX

### Path（默认值）

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## DESCRIPTION

`Add-Content`Cmdlet 将内容追加到指定项或文件。 可以通过在命令中键入内容或通过指定包含内容的对象来指定内容。

如果需要为以下示例创建文件或目录，请参阅 " [新建项](New-Item.md)"。

## 示例

### 示例1：向所有文本文件添加字符串，但出现异常

此示例将一个值附加到当前目录中的文本文件，但基于文件的文件名排除文件。

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

`Add-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的所有 .txt 文件。 **Exclude** 参数将忽略与指定模式匹配的文件名。 **值** 参数指定写入文件的文本字符串。

使用 " [获取内容](Get-Content.md) " 显示这些文件的内容。

### 示例2：将日期添加到指定文件的末尾

此示例将日期附加到当前目录中的文件，并在 PowerShell 控制台中显示日期。

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

`Add-Content`Cmdlet 使用 **Path** 和 **Value** 参数在当前目录中创建两个新文件。 **值** 参数指定 `Get-Date` 用于获取日期并将日期传递到的 cmdlet `Add-Content` 。 `Add-Content`Cmdlet 将日期写入每个文件。 **PassThru** 参数传递表示 date 对象的对象。 由于没有其他 cmdlet 接收传递的对象，因此它显示在 PowerShell 控制台中。 `Get-Content`Cmdlet 将显示更新的文件 DateTimeFile1。

### 示例3：将指定文件的内容添加到另一个文件

此示例从文件中获取内容，并将该内容附加到另一个文件中。

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

`Add-Content`Cmdlet 使用 **Path** 参数指定当前目录中的新文件，CopyToFile.txt。 **Value** 参数使用 `Get-Content` cmdlet 来获取文件的内容，CopyFromFile.txt。 Cmdlet 两边的括号 `Get-Content` 可确保命令在命令开始前完成 `Add-Content` 。 **值** 参数传递给 `Add-Content` 。 `Add-Content`Cmdlet 将数据追加到 CopyToFile.txt 文件中。 `Get-Content`Cmdlet 将显示更新后的文件 CopyToFile.txt。

### 示例4：使用变量将指定文件的内容添加到另一个文件

此示例从文件中获取内容，并将内容存储在变量中。 变量用于将内容追加到另一个文件中。

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

`Get-Content`Cmdlet 将获取 CopyFromFile.txt 的内容，并将内容存储在 `$From` 变量中。 `Add-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的 CopyToFile.txt 文件。 **值** 参数使用 `$From` 变量，并将内容传递给 `Add-Content` 。 `Add-Content`Cmdlet 将更新 CopyToFile.txt 文件。 `Get-Content`Cmdlet 将显示 CopyToFile.txt。

### 示例5：创建新文件并复制内容

此示例将创建一个新文件，并将现有文件的内容复制到新文件中。

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

`Add-Content`Cmdlet 使用 **Path** 和 **Value** 参数在当前目录中创建一个新文件。 **Value** 参数使用 `Get-Content` cmdlet 获取现有文件的内容，CopyFromFile.txt。 Cmdlet 两边的括号 `Get-Content` 可确保命令在命令开始前完成 `Add-Content` 。 **Value** 参数传递 `Add-Content` 更新 NewFile.txt 文件的内容。 `Get-Content`Cmdlet 将显示新文件的内容，NewFile.txt。

### 示例6：向只读文件中添加内容

即使 **IsReadOnly** 文件属性设置为 True，此命令也会将该值添加到文件。
示例中包含创建只读文件的步骤。

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

`New-Item`Cmdlet 使用 **Path** 和 **ItemType** 参数在当前目录中创建 IsReadOnlyTextFile.txt 的文件。 `Set-ItemProperty`Cmdlet 使用 **Name** 和 **Value** 参数将文件的 **IsReadOnly** 属性更改为 True。 该 `Get-ChildItem` cmdlet 显示文件为空 (0) 并且 () 具有只读属性 `r` 。 `Add-Content`Cmdlet 使用 **Path** 参数指定文件。 **Value** 参数包含要追加到文件中的文本字符串。 **Force** 参数将文本写入只读文件。 `Get-Content`Cmdlet 使用 **Path** 参数显示文件的内容。

若要删除只读属性，请使用命令， `Set-ItemProperty` 并将 **Value** 参数设置为 `False` 。

## PARAMETERS

### -Confirm

提示你在运行 cmdlet 之前进行确认。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认为当前用户。

键入用户名（如 **User01** 或 **Domain01\User01** ）或输入 PSCredential 对象，例如由 Cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。 如果键入用户名，则将提示你输入密码。

> [!WARNING]
> 随 PowerShell 一起安装的任何提供程序都不支持此参数。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Encoding

指定目标文件的编码类型。 默认值是 `Default`。

此参数可接受的值如下所示：

- `Ascii` 使用 ASCII (7 位) 字符集。
- `BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。
- `BigEndianUTF32` 使用带有大字节序字节顺序的 32 UTF-8。
- `Byte` 将一组字符编码为一个字节序列。
- `Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。
- `Oem` 使用与系统的当前 OEM 代码页相对应的编码。
- `String` 与 **Unicode** 相同。
- `Unicode` 使用带有小 endian 字节顺序的 UTF-16。
- `Unknown` 与 **Unicode** 相同。
- `UTF7` 使用 UTF-8。
- `UTF8` 使用 UTF-8。
- `UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。

Encoding 是 FileSystem 提供程序添加到 cmdlet 的动态参数 `Add-Content` 。 此参数仅在文件系统驱动器中有效。

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

忽略指定项。 此参数值使 **Path** 参数有效。 输入路径元素或模式，例如 **\* .txt** 。 允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

以提供程序的格式或语言指定筛选器。 此参数值使 **Path** 参数有效。 筛选器的语法（包括通配符的使用）取决于提供程序。 **筛选器** 比其他参数更有效，因为提供程序在检索对象时应用筛选器。 否则，PowerShell 将在检索对象后处理筛选器。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

覆盖只读属性，从而允许你向只读文件中添加内容。 例如， **Force** 将覆盖只读属性或创建目录来完成文件路径，但它不会尝试更改文件权限。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

只添加指定项。 此参数值使 **Path** 参数有效。 输入路径元素或模式，例如 **\* .txt** 。 允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LiteralPath

指定用于接收其他内容的项的路径。 不同于 **Path** ， **LiteralPath** 的值严格按照所键入的形式使用。 不会将任何字符解释为通配符。 如果路径包括转义符，请将其括在单引号中。 单引号指示 PowerShell 不要将任何字符解释为转义序列。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoNewline

指示此 cmdlet 不会将新的行或回车添加到内容。

输入对象的字符串表示形式连接起来以形成输出。 不会在输出字符串之间插入空格或换行符。 在最后一个输出字符串之后不添加任何行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

返回一个表示所添加内容的对象。 默认情况下，此 cmdlet 将不产生任何输出。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定用于接收其他内容的项的路径。 允许使用通配符。 如果指定多个路径，请使用逗号分隔这些路径。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Stream

指定内容的备用数据流。 如果该流不存在，则此 cmdlet 将创建它。 不支持通配符。

**Stream** 是 FileSystem 提供程序添加到的动态参数 `Add-Content` 。 此参数仅在文件系统驱动器中有效。

可以使用 `Add-Content` cmdlet 更改区域的内容 **。标识符** 备用数据流。 但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。 如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。

此参数是在 PowerShell 3.0 中引入的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction

在活动事务中使用该命令。 仅当正在执行事务时，此参数才有效。 有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

指定要添加的内容。 键入带引号的字符串，如 **此数据仅供内部使用** ，或指定包含内容的对象，例如生成的 **DateTime** 对象 `Get-Date` 。

不能通过键入文件路径来指定文件内容，因为路径只是一个字符串。
您可以使用 `Get-Content` 命令获取内容并将其传递给 **Value** 参数。

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。 此 cmdlet 未运行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.web、System.web 和 System.object

可以通过管道将值、路径或凭据传递给 `Set-Content` 。

## 输出

### None 或 System.String

当使用 **PassThru** 参数时，将 `Add-Content` 生成表示内容的 **system.string** 对象。 否则，此 cmdlet 将不生成任何输出。

## 注释

将对象通过管道传递给时 `Add-Content` ，对象会在添加到项之前转换为字符串。 对象类型决定字符串格式，但该格式可能不同于该对象的默认显示。 若要控制字符串格式，请使用发送 cmdlet 的格式设置参数。

还可以 `Add-Content` 通过其内置别名来引用 `ac` 。 有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。

`Add-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。 若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。 有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。

## 相关链接

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
