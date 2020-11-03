---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198285"
---
# Get-ItemProperty

## 摘要
获取指定项的属性。

## SYNTAX

### Path（默认值）

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`Get-ItemProperty`Cmdlet 将获取指定项的属性。
例如，你可以使用此 cmdlet 来获取文件对象的 LastAccessTime 属性的值。
你还可以使用此 cmdlet 查看注册表项及其值。

## 示例

### 示例1：获取有关特定目录的信息

此命令获取有关 "C：\Windows" 目录的信息。

```powershell
Get-ItemProperty C:\Windows
```

### 示例2：获取特定文件的属性

此命令将获取 "C:\Test\Weather.xls" 文件的属性。
将结果输送到 cmdlet， `Format-List` 以将输出显示为列表。

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### 示例3：在注册表子项中显示注册表项的值名称和数据

此命令显示 "CurrentVersion" 注册表子项中包含的每个注册表项的值名称和数据。
请注意，该命令要求有一个名为的 PowerShell 驱动器 `HKLM:` ，该驱动器映射到注册表的 "HKEY_LOCAL_MACHINE" hive。
默认情况下，具有该名称和映射的驱动器在 PowerShell 中可用。
或者，可以通过使用以下替代路径指定此注册表子项的路径（替代路径以提供程序名称开头，后跟两个冒号）：

"Registry：： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion"。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### 示例4：获取注册表子项中的注册表项的值名称和数据

此命令将获取 "CurrentVersion" 注册表子项中的 "ProgramFilesDir" 注册表项的值名称和数据。
该命令使用 **Path** 参数来指定子项，使用 name 参数来指定条目的值名称。

该命令使用后退计时或重音符 (\`) （PowerShell 继续符）在第二行继续执行命令。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### 示例5：获取注册表项中的注册表项的值名称和数据

此命令将获取 "PowerShellEngine" 注册表项中的注册表项的值名称和数据。
结果显示在下面的示例输出中。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### 示例6：获取、格式化和显示注册表值和数据的结果

此示例演示如何设置列表中命令的输出的格式， `Get-ItemProperty` 以方便查看注册表值和数据，并使其易于解释结果。

第一个命令使用 `Get-ItemProperty` cmdlet 来获取 **Microsoft PowerShell** 子项中的注册表项。
此子项存储用于 PowerShell 的默认 shell 的选项。
结果显示在下面的示例输出中。

输出显示有两个注册表项： "路径" 和 "Set-executionpolicy"。
如果注册表项中包含的条目少于 5 个，则默认情况下，将以表的形式显示它，但通常列表形式更易于查看。

第二个命令使用相同的 `Get-ItemProperty` 命令。
但这次，该命令使用管道运算符 () 将 `|` 命令的结果发送到 `Format-List` cmdlet。
该 `Format-List` 命令使用值为 "*" 的属性参数 (所有) 在列表中显示对象的所有属性。
结果显示在下面的示例输出中。

生成的显示将显示 "路径" 和 "Set-executionpolicy" 注册表项，以及注册表项对象的几个不太熟悉的属性。
以 PS 为前缀的其他属性是 PowerShell 自定义对象（例如表示注册表项的对象）的属性。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## PARAMETERS

### -Credential

指定有权执行此操作的用户帐户。
默认为当前用户。

键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。
如果键入用户名，则将提示你输入密码。

> [!WARNING]
> 随同 Windows PowerShell 一起安装的任何提供程序都不支持此参数。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude

指定此 cmdlet 将从操作中排除的一个项或多个项（作为一个字符串数组）。
此参数值使 **Path** 参数有效。
请输入路径元素或模式，例如“*.txt”。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

以提供程序的格式或语言指定筛选器。
此参数值使 **Path** 参数有效。

筛选器的语法（包括通配符字符的使用），具体取决于提供程序。
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

### -Include

指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。
此参数值使 **Path** 参数有效。
请输入路径元素或模式，例如“*.txt”。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

指定此属性的当前位置的路径。
与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。
不会将任何字符解释为通配符。
如果路径包括转义符，请将其括在单引号中。
单引号指示 PowerShell 不要将任何字符解释为转义序列。

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

### -Name

指定要检索的属性的名称。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定一个或多个项的路径。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction

在活动事务中使用该命令。
仅当正在执行事务时，此参数才有效。
有关详细信息，请参阅“在活动事务中使用该命令”。
仅当正在执行事务时，此参数才有效。
有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。

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

### CommonParameters

此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.String

可以通过管道将包含路径的字符串传递给 `Get-ItemProperty` 。

## 输出

### System.Boolean、System.String、System.DateTime

`Get-ItemProperty` 为它获取的每个项属性返回一个对象。
对象类型取决于检索的对象。
例如，在文件系统驱动器中，它可能会返回一个文件或文件夹。

## 注释

`Get-ItemProperty`Cmdlet 设计用于处理由任何提供程序公开的数据。 若要列出会话中可用的提供程序，请键入 " `Get-PSProvider` "。 有关详细信息，请参阅 about_Providers。

## 相关链接

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)
