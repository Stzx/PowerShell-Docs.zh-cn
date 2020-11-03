---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 897029cab790487f6834d021bfc447060fd39812
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198048"
---
# Set-Content

## 摘要
写入新内容或替换文件中的现有内容。

## SYNTAX

### Path（默认值）

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### LiteralPath

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## DESCRIPTION

`Set-Content` 是一个字符串处理 cmdlet，用于写入新内容或替换文件中的内容。 `Set-Content` 替换现有内容，不同于将 `Add-Content` 内容追加到文件的 cmdlet。 若要将内容发送到 `Set-Content` ，可以在命令行上使用 **Value** 参数或通过管道发送内容。

如果需要为以下示例创建文件或目录，请参阅 " [新建项](New-Item.md)"。

## 示例

### 示例1：替换目录中多个文件的内容

此示例替换当前目录中多个文件的内容。

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

`Get-ChildItem`Cmdlet 使用 **Path** 参数列出以当前目录开头的 **.txt** 文件。 `Test*` `Set-Content`Cmdlet 使用 **Path** 参数指定 `Test*.txt` 文件。 **Value** 参数提供替换每个文件中的现有内容的文本字符串 **Hello、World** 。 `Get-Content`Cmdlet 使用 **Path** 参数指定 `Test*.txt` 文件，并在 PowerShell 控制台中显示每个文件的内容。

### 示例2：创建新文件并写入内容

此示例将创建一个新文件，并将当前日期和时间写入文件。

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

`Set-Content` 使用 **Path** 和 **Value** 参数在当前目录中创建一个名为 **DateTime.txt** 的新文件。 **值** 参数用于 `Get-Date` 获取当前日期和时间。
`Set-Content` 将 **DateTime** 对象作为字符串写入到文件中。 `Get-Content`Cmdlet 使用 **Path** 参数在 PowerShell 控制台中显示 **DateTime.txt** 的内容。

### 示例 3：在文件中替换文本

此命令替换现有文件中的所有 word 实例。

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

`Get-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的 **Notice.txt** 文件。 `Get-Content`命令用括号括起来，以便命令在管道下发送前完成。

**Notice.txt** 文件的内容将通过管道向下发送到 `ForEach-Object` cmdlet。
`ForEach-Object`使用自动变量 `$_` ，并将每次出现 **Warning** 的警告 **Caution** 替换为警告。 对象通过管道向下发送到 `Set-Content` cmdlet。 `Set-Content` 使用 **Path** 参数指定 **Notice.txt** 文件，并将更新的内容写入文件。

最后一个 `Get-Content` cmdlet 在 PowerShell 控制台中显示更新的文件内容。

### 示例4：使用筛选器与 Set-Content

可以为 cmdlet 指定筛选器 `Set-Content` 。 使用筛选器限定 **路径** 参数时，需要包含一个尾随星号 (`*`) ，以指示路径的内容。

以下命令将目录中的所有文件的内容设置 `*.txt` `C:\Temp` 为空 **值** 。

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## PARAMETERS

### -Credential

> [!NOTE]
> 随 PowerShell 一起安装的任何提供程序都不支持此参数。
> 若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。

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

Encoding 是 FileSystem 提供程序添加到的动态参数 `Set-Content` 。 此参数仅在文件系统驱动器中有效。

此参数可接受的值如下所示：

- `Ascii` 使用 ASCII (7 位) 字符集。
- `BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。
- `BigEndianUTF32` 使用带有大字节序字节顺序的 32 UTF-8。
- `Byte` 将一组字符编码为一个字节序列。
- `Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。
- `Oem` 使用与系统的当前 OEM 代码页相对应的编码。
- `String` 与 `Unicode` 相同。
- `Unicode` 使用带有小 endian 字节顺序的 UTF-16。
- `Unknown` 与 `Unicode` 相同。
- `UTF7` 使用 UTF-8。
- `UTF8` 使用 UTF-8。
- `UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。

Encoding 是 FileSystem 提供程序添加到的动态参数 `Set-Content` 。 此参数仅在文件系统驱动器中有效。

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

指定为字符串数组，此 cmdlet 在操作中排除的项。 此参数值使 **Path** 参数有效。 请输入路径元素或模式，例如 `*.txt`。 允许使用通配符。 仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。

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

指定用于限定 **路径** 参数的筛选器。 [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。 可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。
筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。

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

强制该 cmdlet 设置文件内容（即使该文件是只读的）。 不同提供程序有不同的实现。 有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。
**Force** 参数不会覆盖安全限制。

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

指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。 此参数值使 **Path** 参数有效。 请输入路径元素或模式，例如 `"*.txt"`。 允许使用通配符。 仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。

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

指定一个或多个位置的路径。 **LiteralPath** 的值严格按照所键入的形式使用。 不会将任何字符解释为通配符。 如果路径包括转义符，请将其括在单引号中。 单引号指示 PowerShell 不要将任何字符解释为转义序列。

有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。

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

返回一个表示内容的对象。 默认情况下，此 cmdlet 将不产生任何输出。

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

指定接受内容的项的路径。
允许使用通配符。

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

**Stream** 是 **FileSystem** 提供程序添加到的动态参数 `Set-Content` 。 此参数仅在文件系统驱动器中有效。

可以使用 `Set-Content` cmdlet 更改区域的内容 **。标识符** 备用数据流。 但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。 如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。

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

为项指定新的内容。

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

此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。
有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.Object

可以通过管道将包含项的新值的对象传递给 `Set-Content` 。

## 输出

### None 或 System.String

当使用 **PassThru** 参数时，将 `Set-Content` 生成表示内容的 **system.string** 对象。 否则，此 cmdlet 将不生成任何输出。

## 注释

- 还可以 `Set-Content` 通过其内置别名来引用 `sc` 。
  有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。
- `Set-Content` 用于字符串处理。 如果将非字符串对象通过管道传递给 `Set-Content` ，它会在写入之前将对象转换为字符串。 若要将对象写入文件，请使用 `Out-File` 。
- `Set-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。 若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。 有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。

## 相关链接

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Automatic_Variables md](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-Content](Get-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[New-Item](New-Item.md)
