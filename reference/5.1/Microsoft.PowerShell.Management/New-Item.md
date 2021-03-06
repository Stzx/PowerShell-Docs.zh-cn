---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198084"
---
# New-Item

## 摘要
创建新项。

## SYNTAX

### pathSet（默认值）

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### nameSet

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`New-Item`Cmdlet 将创建新项并设置其值。 可以创建的项的类型取决于项的位置。 例如，在文件系统中 `New-Item` 创建文件和文件夹。 在注册表中 `New-Item` 创建注册表项和条目。

`New-Item` 还可以设置它创建的项的值。 例如，在创建新文件时， `New-Item` 可以将初始内容添加到文件中。

## 示例

### 示例1：在当前目录中创建文件

此命令将在当前目录中创建一个名为 "testfile1.txt" 的文本文件。 点 ( "." **Path** 参数的值中的 ) 指示当前目录。 在 **值** 参数之后的带引号文本将作为内容添加到文件中。

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### 示例2：创建目录

此命令在驱动器中创建一个名为 "日志" 的目录 `C:` 。 **ItemType** 参数指定新项是目录，而不是文件或其他文件系统对象。

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### 示例3：创建配置文件

此命令在由变量指定的路径中创建 PowerShell 配置文件 `$profile` 。

可以使用配置文件自定义 PowerShell。 `$profile` 是一个自动 (内置) 变量，用于存储 "CurrentUser/CurrentHost" 配置文件的路径和文件名。 默认情况下，配置文件不存在，即使 PowerShell 为其存储路径和文件名。

在此命令中， `$profile` 变量表示文件的路径。 **ItemType** 参数指定该命令创建一个文件。 **Force** 参数允许你在配置文件路径中创建文件，即使路径中的目录不存在也是如此。

创建配置文件后，可以在配置文件中输入别名、函数和脚本来自定义 shell。

有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 和 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> 使用此方法创建文件时，会将生成的文件编码为 UTF-8，而不会将字节顺序标记 (BOM) 。

### 示例4：在不同的目录中创建目录

此示例将在 "C:\PS-Test" 目录中创建新的 Scripts 目录。

新目录项的名称 "Scripts" 包含在 **Path** 参数的值中，而不是在 **名称** 的值中指定。 根据语法，任一种命令形式都是有效的。

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### 示例5：创建多个文件

此示例在两个不同的目录中创建文件。 由于 **路径** 采用多个字符串，因此可以使用它来创建多个项。

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### 示例6：使用-Force 参数尝试重新创建文件夹

此示例创建一个文件夹，其中包含中的文件。 然后，尝试使用创建相同的文件夹 `-Force` 。 它不会覆盖文件夹，只需返回现有的文件夹对象，文件创建的文件也会原封不动。

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### 示例7：使用-Force 参数覆盖现有文件

此示例创建一个具有值的文件，然后使用重新创建该文件 `-Force` 。 这将覆盖现有文件，并且它将丢失其内容，正如您可以看到的 "长度" 属性所示

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> 当使用 `New-Item` 带有 `-Force` 开关的来创建注册表项时，该命令的行为与覆盖文件时的行为相同。 如果注册表项已存在，则将使用空的注册表项覆盖该项和所有属性和值。

## PARAMETERS

### -Credential

> [!NOTE]
> 随 PowerShell 一起安装的任何提供程序都不支持此参数。 若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 `Invoke-Command` 。

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

### -Force

强制此 cmdlet 创建一个写入现有只读项的项。 不同提供程序有不同的实现。 即使使用 **Force** 参数，该 cmdlet 也无法覆盖安全限制。

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

### -ItemType

指定提供程序指定的新项的类型。 此参数的可用值取决于当前使用的提供程序。

如果位置在 `FileSystem` 驱动器中，则允许以下值：

- 文件
- Directory
- SymbolicLink
- 交接点
- 硬

使用此方法创建文件时，会将生成的文件编码为 UTF-8，而不会将字节顺序标记 (BOM) 。

在 `Certificate` 驱动器中，可以指定以下值：

- Certificate 提供程序
- 证书
- 应用商店
- StoreLocation

有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

指定新项的名称。 您可以在 **name** 或 **path** 参数值中指定新项的名称，并且可以在 " **名称** " 或 " **路径** " 值中指定新项的路径。 使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

指定新项的位置的路径。 如果省略 **路径** ，则默认值为当前位置。 可以在 " **名称** " 中指定新项的名称，也可以将其包含在 " **路径** " 中。 使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。

对于此 cmdlet， **路径** 参数的工作方式类似于其他 Cmdlet 的 **LiteralPath** 参数。
不解释通配符。 所有字符将传递到位置的提供程序。 提供程序可能不支持所有字符。 例如，你不能创建包含星号 () 字符的文件名 `*` 。

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
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

指定新项的值。 还可以通过管道将值传递给 `New-Item` 。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
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

### System.Object

可以通过管道将新项的值传递给此 cmdlet。

## 输出

### System.Object

此 cmdlet 将返回它创建的项。

## 注释

`New-Item` 设计用于处理由任何提供程序公开的数据。 若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。 有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。

## 相关链接

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
