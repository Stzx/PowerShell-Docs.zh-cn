---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198049"
---
# Restore-Computer

## 摘要
在本地计算机上启动系统还原。

## SYNTAX

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
" **还原-计算机** " cmdlet 将本地计算机还原到指定的系统还原点。

**还原-计算机** 重启计算机。
在重新启动操作期间完成还原。

仅在客户端操作系统（例如 Windows 7、Windows Vista 和 Windows XP）上支持系统还原点和 **还原计算机** 。

## 示例

### 示例1：还原本地计算机

```
PS C:\> Restore-Computer -RestorePoint 253
```

此命令将本地计算机还原到序列号为253的还原点。

### 示例2：还原本地计算机的确认

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

此命令将本地计算机还原到序列号为255的还原点。
它使用 *Confirm* 参数在实际执行操作前提示用户。

### 示例3：还原计算机并检查状态

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

这些命令运行系统还原，然后检查其状态。

第一个命令使用 **get-computerrestorepoint** 获取本地计算机上的还原点。

第二个命令将计算机还原到序号为255的还原点。

第三个命令使用 *get-computerrestorepoint* Cmdlet 的 *LastStatus* 参数检查还原操作的状态。
因为 **还原计算机** 强制重新启动，所以在计算机重新启动后，将会输入此命令。

## PARAMETERS

### -RestorePoint
指定还原点的序号。
若要查找序列号，请使用 Get-ComputerRestorePoint cmdlet。
此参数是必需的。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

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
不能通过管道将输入传递给此 cmdlet。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* 若要在 Windows Vista 和更高版本的 Windows 操作系统上运行 Restore-Computer 命令，请使用 "以管理员身份运行" 选项打开 Windows PowerShell。
* 此 cmdlet 使用 (WMI) **SystemRestore** 类的 Windows Management Instrumentation。

## 相关链接

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)
