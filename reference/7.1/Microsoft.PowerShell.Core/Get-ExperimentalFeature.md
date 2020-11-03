---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 2d91c36c6fd6d2e1281fdadf95c3b83e27c36f60
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198861"
---
# Get-ExperimentalFeature

## 摘要
获取实验性功能。

## SYNTAX

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ExperimentalFeature`Cmdlet 将返回 PowerShell 发现的所有实验性功能。
实验功能可以来自模块或 PowerShell 引擎。 利用实验功能，用户可以安全地测试新功能，并通过 GitHub) 提供反馈 (在将设计视为已完成之前，任何更改都可能会成为重大更改。

## 示例

### 示例 1

获取当前注册的实验功能及其当前状态的列表。

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## PARAMETERS

### -Name

要返回的特定实验功能的名称或名称。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String[]

要返回的实验功能的名称或名称。

## 输出

### ExperimentalFeature

如果未指定名称，则返回与请求的名称或所有实验性功能匹配的实例。

## 相关链接

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)

