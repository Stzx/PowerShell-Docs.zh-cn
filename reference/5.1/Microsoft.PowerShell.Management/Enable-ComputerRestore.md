---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198303"
---
# Enable-ComputerRestore

## 摘要
在指定的文件系统驱动器上启用系统还原功能。

## SYNTAX

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Disable-computerrestore** cmdlet 将在一个或多个文件系统驱动器上启用系统还原功能。
因此，可以使用工具（如 Restore-Computer cmdlet）将计算机还原到先前的状态。

默认情况下，系统还原在符合条件的所有驱动器上都处于启用状态，不过你可以禁用系统还原，例如使用 Disable-ComputerRestore cmdlet 来禁用。
若要在任何驱动器上启用（或重新启用）系统还原，则必须首先或同时在系统驱动器上启用系统还原。
若要查找每个驱动器的系统还原状态，请使用 Rstrui.exe。

系统还原点和 ComputerRestore cmdlet 仅在客户端操作系统（例如 Windows 7、Windows Vista 和 Windows XP）上受支持。

## 示例

### 示例1：在指定的驱动器上启用系统还原

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

此命令在本地计算机的 C: 驱动器上启用系统还原。

### 示例2：在多个驱动器上启用系统还原

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

此命令在本地计算机的 C: 和 D: 驱动器上启用系统还原。

## PARAMETERS

### -Drive
指定文件系统驱动器。
输入一个或多个文件系统驱动器号，每个驱动器号后面跟一个冒号和一个反斜杠，并用引号引起来，例如 C：\或 D:\。
此参数是必需的。

无法使用此 cmdlet 在远程网络驱动器上启用系统还原，即使该驱动器映射到本地计算机也是如此，并且无法在不符合系统还原条件的驱动器（如外部驱动器）上启用系统还原。

若要在任何驱动器上启用系统还原，则必须首先或同时在系统驱动器上启用系统还原。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
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
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无
不能通过管道将对象传递给此 cmdlet。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* 若要在 Windows Vista 和更高版本的 Windows 上运行此 cmdlet，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。

  若要查找符合系统还原条件的文件系统驱动器，请在 "控制面板" 的 "系统" 中查看 "系统保护" 选项卡。若要在 Windows PowerShell 中打开此选项卡，请键入 `SystemPropertiesProtection` 。

  此 cmdlet 使用 (WMI) **SystemRestore** 类的 Windows Management Instrumentation。

*

## 相关链接

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)
