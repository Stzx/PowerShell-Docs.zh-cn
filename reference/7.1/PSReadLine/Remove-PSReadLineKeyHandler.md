---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: a13677035581a081df51917bc6b82efec0ff2156
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200686"
---
# Remove-PSReadLineKeyHandler

## 摘要
删除键绑定。

## SYNTAX

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## DESCRIPTION

`Remove-PSReadLineKeyHandler`Cmdlet 将删除指定的键绑定。

## 示例

### 示例1：删除绑定

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

此命令从键组合或弦形中删除绑定 `Ctrl+B` 。 `Ctrl+B`在项目中创建了弦 `Set-PSReadLineKeyHandler` 。

## PARAMETERS

### -弦

指定要删除的键或键序列的数组。 单个绑定使用单个字符串指定。 如果绑定是键序列，请用逗号分隔键，如以下示例中所示：

`Ctrl+x,Ctrl+l`

此参数接受字符串数组。 每个字符串都是一个单独的绑定，而不是单个绑定的键序列。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ViMode

指定绑定应用于哪种 vi 模式。 可能的值为： Insert、Command。

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

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

不能通过管道将对象传递给此 cmdlet。

## 输出

### 无

## 注释

## 相关链接

[PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[PSReadLineOption](Get-PSReadLineOption.md)

[PSReadLineOption](Set-PSReadLineOption.md)

[PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)

