---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 3f99869825b2255d3f5487c48b6eaa90a4ae901f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197546"
---
# Disable-PSTrace

## 摘要
禁用 Microsoft Windows PowerShell 事件提供程序日志。

## SYNTAX

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## DESCRIPTION

此 cmdlet 将禁用 Microsoft Windows PowerShell 事件提供程序的操作和分析事件日志。

必须从提升的 PowerShell 会话中运行此 cmdlet。

## 示例

### 示例1：禁用 PowerShell 的分析事件日志

下面的示例仅禁用 Microsoft Windows PowerShell 提供程序的分析事件日志。

```powershell
Disable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -AnalyticOnly

使用此参数时，该 cmdlet 将禁用 Microsoft Windows PowerShell 提供程序的分析事件日志。 不会更改操作事件日志。

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

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

## 输出

### 无

## 注释

此 cmdlet 使用 `Get-LogProperties` 和 `Set-LogProperties` cmdlet。

必须从提升的 PowerShell 会话中运行此 cmdlet。

## 相关链接

[Get-LogProperties](Get-LogProperties.md)

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)
