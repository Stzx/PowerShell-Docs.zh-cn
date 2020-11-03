---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197445"
---
# Export-Console

## 摘要
将当前会话中的管理单元的名称导出到控制台文件。

## SYNTAX

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**导出控制台** cmdlet 将当前会话中的 windows powershell 管理单元的名称导出到 ( 的 windows powershell 控制台文件。 .psc1) 。
可以使用此 cmdlet 来保存管理单元，以供在以后的会话中使用。

若要将 .psc1 控制台文件中的管理单元添加到会话中，请使用 Cmd.exe 或其他 Windows PowerShell 会话在命令行上启动 Windows PowerShell ( # A0) ，然后使用 Powershell.exe 的 *PSConsoleFile* 参数指定控制台文件。

有关 Windows PowerShell 管理单元的详细信息，请参阅 about_PSSnapins。

## 示例

### 示例1：导出当前会话中的管理单元的名称

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

此命令将当前会话中的 Windows PowerShell 管理单元的名称导出到 Windows PowerShell 安装文件夹的控制台文件夹中的 Consoles1.psc1 .psc1 文件，$pshome。

### 示例2：将管理单元的名称导出到最近的控制台文件

```
PS C:\> Export-Console
```

此命令将当前会话中的 Windows PowerShell 管理单元的名称导出到最近在当前会话中使用的 Windows PowerShell 控制台文件中。
它会覆盖以前的文件内容。

如果你尚未在当前会话期间导出控制台文件，则系统将提示你需要相应权限才能继续操作，然后提示你输入文件名。

### 示例3：添加管理单元并导出管理单元的名称

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

这些命令将 NewPSSnapin Windows PowerShell 管理单元添加到当前会话中、将当前会话中的 Windows PowerShell 管理单元的名称导出到控制台文件中，然后使用该控制台文件启动 Windows PowerShell 会话。

第一个命令使用 **add-pssnapin** Cmdlet 将 NewPSSnapin 管理单元添加到当前会话中。
你可以仅添加已在你的系统上注册的 Windows PowerShell 管理单元。

第二个命令将 Windows PowerShell 管理单元名称导出到 NewPSSnapinConsole.psc1 文件中。

第三个命令使用 NewPSSnapinConsole.psc1 文件启动 Windows PowerShell。
因为该控制台文件包含 Windows PowerShell 管理单元名称，所以该管理单元中的 cmdlet 和提供程序在当前会话中可用。

### 示例4：将管理单元的名称导出到指定位置

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

此命令会将当前会话中的 Windows PowerShell 管理单元的名称导出到当前目录下的 Console01.psc1 文件中。

第二个命令将在记事本中显示 Console01.psc1 文件的内容。

### 示例5：确定要更新的控制台文件

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

此示例演示如何使用 $ConsoleFileName 自动变量来确定在使用不带 *Path* 参数值的 **导出** 时将更新的控制台文件。

第一个命令使用 PowerShell.exe 的 *PSConsoleFile* 参数来打开包含 .psc1 文件的 Windows PowerShell。

第二个命令使用 **add-pssnapin** Cmdlet 将 MySnapin Windows PowerShell 管理单元添加到当前会话中。

第三个命令使用 **export-Console** cmdlet 将会话中的所有 Windows PowerShell 管理单元的名称导出到 newconsole.psc1. .psc1 文件中。

第四个命令显示 $ConsoleFileName 变量。
它包含最近使用过的控制台文件。
示例输出显示 NewConsole.ps1 是最近使用的文件。

第五个命令将 SnapIn03 添加到当前控制台中。

第六个命令使用不带 *Path* 参数的 **导出控制台** cmdlet。
此命令会将当前会话中的所有 Windows PowerShell 管理单元的名称导出到最近使用的文件 NewConsole.psc1 中。

## PARAMETERS

### -Force
指示此 cmdlet 将在不发出警告的情况下覆盖控制台文件中的数据，即使该文件具有只读属性也是如此。
只读属性已更改，并且在命令完成时不会重置。

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

### -NoClobber
指示此 cmdlet 不会覆盖现有的控制台文件。
默认情况下，如果文件出现在指定的路径中，则 **导出控制台** 将覆盖文件而不发出警告。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
指定控制台文件 (*.psc1） 的路径和文件名。
输入可选的路径和名称。
不允许使用通配符。

如果仅指定文件名，则 **导出控制台** 将在当前目录中创建一个具有该名称的文件和一个 .psc1 文件扩展名。

除非你已使用 *PSConsoleFile* 参数打开 Windows PowerShell 或在当前会话期间导出了控制台文件，否则此参数是必需的。
当你使用 *NoClobber* 参数以防止覆盖当前控制台文件时，也需要使用该参数。

如果省略此参数，则 **导出控制台** 将覆盖最近在此会话中使用的控制台文件。
最近使用的控制台文件的路径存储在 $ConsoleFileName 自动变量的值中。
有关详细信息，请参阅 about_Automatic_Variables。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
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
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String
可以通过管道将路径字符串传递给此 cmdlet。

## 输出

### System.IO.FileInfo
此 cmdlet 将创建一个包含导出的别名的文件。

## 注释

* 当控制台文件 (.psc1) 用于启动会话时，该控制台文件的名称会自动存储在 $ConsoleFileName 自动变量中。 当你使用 **Export** 的 *Path* 参数指定一个新的控制台文件时，将更新 $ConsoleFileName 的值。 当没有使用控制台文件时，$ConsoleFileName ($Null) 没有值。

  若要在新会话中使用 Windows PowerShell 控制台文件，请使用以下语法来启动 Windows PowerShell：

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  还可以通过将 Add-PSSnapin 命令添加到你的 Windows PowerShell 配置文件中，来保存 Windows PowerShell 管理单元，以供以后的会话使用。
有关详细信息，请参阅 about_Profiles。


## 相关链接

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
