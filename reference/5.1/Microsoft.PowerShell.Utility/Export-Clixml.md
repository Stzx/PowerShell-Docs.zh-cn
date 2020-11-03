---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197946"
---
# Export-Clixml

## 摘要
创建一个或多个对象的基于 XML 的表示形式，并将其存储在文件中。

## SYNTAX

### ByPath（默认值）

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Export-Clixml`Cmdlet (CLI) 基于 XML 的对象或对象的表示形式创建公共语言基础结构，并将其存储在文件中。 然后，可以使用 `Import-Clixml` cmdlet 基于该文件的内容重新创建已保存的对象。
有关 CLI 的详细信息，请参阅 [语言独立性](/dotnet/standard/language-independence)。

此 cmdlet 类似于 `ConvertTo-Xml` ，不同之处在于将 `Export-Clixml` 生成的 XML 存储在文件中。 `ConvertTo-XML` 返回 XML，因此你可以继续在 PowerShell 中处理它。

Windows 计算机上的一个有价值的用途 `Export-Clixml` 是将凭据和安全字符串作为 XML 安全地导出。 有关示例，请参阅示例3。

## 示例

### 示例1：将字符串导出到 XML 文件

此示例将创建一个 XML 文件，该文件存储在当前目录中， **这是一个测试** 字符串的表示形式。

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

**这是一种测试** 的字符串。 `Export-Clixml` 使用 **Path** 参数 `sample.xml` 在当前目录中创建一个名为的 XML 文件。

### 示例2：将对象导出到 XML 文件

此示例演示如何将对象导出到 XML 文件，然后通过从该文件导入 XML 来创建对象。

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

`Get-Acl`Cmdlet 将获取该文件的安全描述符 `Test.txt` 。 它将对象向下发送到管道，以将安全描述符传递给 `Export-Clixml` 。 对象的基于 XML 的表示形式存储在名为的文件中 `FileACL.xml` 。

`Import-Clixml`Cmdlet 可从该文件中的 XML 创建对象 `FileACL.xml` 。 然后，它将对象保存在 `$fileacl` 变量中。

### 示例3：加密导出的凭据对象

在此示例中，给定通过运行 cmdlet 存储在变量中的凭据 `$Credential` `Get-Credential` ，可以运行 `Export-Clixml` cmdlet 将凭据保存到磁盘。

> [!IMPORTANT]
> `Export-Clixml` 仅导出 Windows 上的加密凭据。 在非 Windows 操作系统（如 macOS 和 Linux）上，凭据以纯文本格式导出。

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

`Export-Clixml`Cmdlet 使用 Windows[数据保护 API](/previous-versions/windows/apps/hh464970(v=win.10))加密凭据对象。
加密可确保只有该计算机上的用户帐户才能解密 credential 对象的内容。 导出的 `CLIXML` 文件不能用于其他计算机或其他用户。

在此示例中，存储凭据的文件由表示 `TestScript.ps1.credential` 。 将 **TestScript** 替换为要在其中加载凭据的脚本的名称。

将凭据对象向下发送到管道 `Export-Clixml` ，并将其保存到在 `$Credxmlpath` 第一个命令中指定的路径。

若要将凭据自动导入脚本，请运行最后两个命令。 运行 `Import-Clixml` 将受保护的凭据对象导入脚本。 此导入消除了在脚本中公开纯文本密码的风险。

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

### -Depth

指定 XML 表示形式中所包含的包含对象的级别数。 默认值是 `2`。

对于文件中的对象类型，可以重写默认值 `Types.ps1xml` 。 有关详细信息，请参阅 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

指定目标文件的编码类型。 默认值为 **Unicode** 。

此参数可接受的值如下所示：

- `ASCII` 使用 ASCII (7 位) 字符集。
- `BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。
- `Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。
- `OEM` 使用与系统的当前 OEM 代码页相对应的编码。
- `Unicode` 使用带有小 endian 字节顺序的 UTF-16。
- `UTF7` 使用 UTF-8。
- `UTF8` 使用 UTF-8。
- `UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

强制运行命令而不要求用户确认。

使该 cmdlet 清除输出文件的只读属性（如有必要）。 该 cmdlet 将在命令完成时尝试重置只读属性。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

指定要转换的对象。 输入一个包含对象的变量，或键入可获取对象的命令或表达式。 还可以通过管道将对象传递给 `Export-Clixml` 。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

指定指向将存储对象的 XML 表示形式的文件的路径。 与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。 不会将任何字符解释为通配符。 如果路径包括转义符，请将其括在单引号中。 单引号指示 PowerShell 不要将任何字符解释为转义序列。

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

指示该 cmdlet 不会覆盖现有文件的内容。 默认情况下，如果指定路径中存在文件，则 `Export-Clixml` 将覆盖该文件而不发出警告。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定指向将存储对象的 XML 表示形式的文件的路径。

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。 cmdlet 未运行。

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

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.Management.Automation.PSObject

可以将任何对象通过管道进行管道 `Export-Clixml` 。

## 输出

### System.IO.FileInfo

`Export-Clixml` 创建包含 XML 的文件。

## 注释

## 相关链接

[ConvertTo-Html](ConvertTo-Html.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Csv](Export-Csv.md)

[Import-Clixml](Import-Clixml.md)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)（将凭据安全存储到磁盘）

[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)（使用 PowerShell 将凭据传递到旧系统）

[Windows.Security.Cryptography.DataProtection](/uwp/api/windows.security.cryptography.dataprotection)
