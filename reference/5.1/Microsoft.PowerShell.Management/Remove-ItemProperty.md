---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198067"
---
# Remove-ItemProperty

## 摘要
从注册表项中删除属性及其值。

## SYNTAX

### Path（默认值）

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`Remove-ItemProperty`Cmdlet 可从项中删除属性及其值。
你可以使用它删除注册表值及其存储的数据。

## 示例

### 示例 1：删除注册表值

此命令从 "HKEY_LOCAL_MACHINE\Software" 注册表项的 "SmpApplication" 子项中删除 "SmpProperty" 注册表值及其数据。

由于命令是从文件系统驱动器 `PS C:\>` （ () ）发出的，因此它包括 "SmpApplication" 子项的完全限定路径，包括驱动器、 `HKLM:` 和 "软件" 键。

它使用 **Name** 参数来标识要删除的注册表值。

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### 示例 2：从 HKCU 位置删除注册表值

这些命令从 "HKEY_CURRENT_USER\Software\MyCompany" 的 "MyApp" 子项删除 "Options" 注册表值及其数据。

第一个命令使用 `Set-Location` cmdlet 将当前位置更改为 **HKEY_CURRENT_USER** 驱动器 (`HKCU:`) 和 "Software\MyCompany\MyApp" 子项。

第二个命令使用 `Remove-ItemProperty` 从 "MyApp" 子项中删除 "Options" 注册表值及其数据。
由于 **路径** 是必需的，因此该命令使用点 ( "。") 指示当前位置。
它使用 Name  来指定要删除的注册表值。
它使用 **Confirm** 参数在删除值之前请求用户提示。

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### 示例 3：使用管道删除注册表值

此命令从 "HKLM\Software\MyCompany" 注册表项中删除 "NoOfEmployees" 注册表值及其数据。

该命令使用 `Get-Item` cmdlet 来获取表示该注册表项的项。
它使用管道运算符 (`|`) 将对象发送到 `Remove-ItemProperty` 。
然后，它使用的 **name** 参数 `Remove-ItemProperty` 来指定注册表值的名称。

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
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
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude

指定此 cmdlet 省略的项。
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
Accept wildcard characters: True
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

### -Force

强制 cmdlet 删除用户非此不能访问的对象的属性。
不同提供程序有不同的实现。
有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。

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
Accept wildcard characters: True
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

指定要删除的属性的名称。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Path

指定要删除其属性的项的路径。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UseTransaction

在活动事务中使用该命令。
仅当正在执行事务时，此参数才有效。
有关详细信息，请参阅 about_Transactions。

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

显示运行该 cmdlet 时会发生什么情况。
此 cmdlet 未运行。

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

此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.String

可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。

## 输出

### 无

此 cmdlet 不返回任何输出。

## 注释

在 PowerShell 注册表提供程序中，注册表值被视为注册表项或子项的属性。 可以使用 **set-itemproperty** cmdlet 来管理这些值。

`Remove-ItemProperty` 设计用于处理由任何提供程序公开的数据。 若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。 有关详细信息，请参阅 about_Providers。

## 相关链接

[Get-Item](Get-Item.md)

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-Item](Remove-Item.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
