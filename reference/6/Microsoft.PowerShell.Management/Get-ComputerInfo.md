---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: 55e7831112d6385b6d449123973ca4b877faa7fd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198516"
---
# Get-ComputerInfo

## 摘要
获取系统属性和操作系统属性的合并对象。

## SYNTAX

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ComputerInfo`Cmdlet 将获取系统属性和操作系统属性的合并对象。
此 cmdlet 是在 Windows PowerShell 5.1 中引入的。

## 示例

### 示例1：获取所有计算机属性

```powershell
Get-ComputerInfo
```

此命令从计算机中获取所有系统属性和操作系统属性。

### 示例2：获取所有计算机操作系统属性

```powershell
Get-ComputerInfo -Property "os*"
```

此命令从计算机中获取所有操作系统属性。

## PARAMETERS

### -Property

以字符串数组的形式指定此 cmdlet 显示的计算机属性。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.String[]

## 输出

### ComputerInfo。

## 注释

## 相关链接
