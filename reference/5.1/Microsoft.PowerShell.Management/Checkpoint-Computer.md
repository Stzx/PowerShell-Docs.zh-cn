---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198332"
---
# Checkpoint-Computer

## 摘要
在本地计算机上创建系统还原点。

## SYNTAX

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## DESCRIPTION

`Checkpoint-Computer`Cmdlet 在本地计算机上创建系统还原点。

系统还原点和 `Checkpoint-Computer` cmdlet 仅在客户端操作系统（如 windows 8、windows 7、Windows Vista 和 WINDOWS XP）上受支持。

从 Windows 8 开始， `Checkpoint-Computer` 每日创建的检查点不能超过一个。

## 示例

### 示例 1：创建系统还原点

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

此命令将创建一个名为 Install MyApp 的系统还原点。
它使用默认的 APPLICATION_INSTALL 还原点类型。

### 示例 2：创建系统 MODIFY_SETTINGS 还原点

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

此命令将创建一个名为“ChangeNetSettings”的 MODIFY_SETTINGS 系统还原点。

## PARAMETERS

### -Description

指定还原点的描述性名称。
此参数是必需的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePointType

指定还原点的类型。
默认值为 APPLICATION_INSTALL。

此参数的可接受值为：

- APPLICATION_INSTALL
- APPLICATION_UNINSTALL
- DEVICE_DRIVER_INSTALL
- MODIFY_SETTINGS
- CANCELLED_OPERATION

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### 无

不能通过管道将对象传递给 `Checkpoint-Computer` 。

## 输出

### 无

此 cmdlet 将不生成任何输出。

## 注释

- 此 cmdlet 将 **SystemRestore** 类的 **CreateRestorePoint** 方法与 **BEGIN_SYSTEM_CHANGE** 事件一起使用。
- 从 Windows 8 开始， `Checkpoint-Computer` 每天无法创建多个系统还原点。 如果你尝试在 24 小时内再创建一个新的还原点，则 Windows PowerShell 将生成以下错误：

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## 相关链接

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restore-Computer](Restore-Computer.md)
