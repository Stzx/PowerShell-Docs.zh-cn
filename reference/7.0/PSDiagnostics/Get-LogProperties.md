---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
Locale: en-US
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 08638749b7a5bb57bee804fccf9de17f50fd6736
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197106"
---
# Get-LogProperties

## 摘要
检索 Windows 事件日志的属性。

## SYNTAX

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## DESCRIPTION

此 cmdlet 将获取 Windows 事件日志的配置设置。 此 cmdlet 由 `Enable-PSTrace` 和 `Disable-PSTrace` cmdlet 使用。

## 示例

### 示例1：获取 Windows PowerShell 事件日志的配置设置

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## PARAMETERS

### -Name

事件提供程序的名称。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String

## 输出

### LogDetails。

**PSDiagnostics** 模块将 **LogDetails** 类添加到 `Microsoft.PowerShell.Diagnostics` 命名空间。

## 注释

## 相关链接

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)

[Disable-PSTrace](Disable-PSTrace.md)
