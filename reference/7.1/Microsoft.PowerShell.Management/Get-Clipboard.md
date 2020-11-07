---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 5fce0c872871006dd760ee8df2fb692faaa1aab9
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342359"
---
# Get-Clipboard

## 摘要
获取剪贴板的内容。

## SYNTAX

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Get-Clipboard`Cmdlet 将剪贴板的内容作为文本获取。 多行文本作为字符串数组返回，类似于 `Get-Content` 。

> [!NOTE]
> 在 Linux 上，此 cmdlet 要求 `xclip` 实用工具在路径中。 MacOS 上不支持此 cmdlet。

## 示例

### 示例1：获取剪贴板的内容并将其显示在命令行中

在此示例中，我们已将文本 "hello" 复制到剪贴板。

```powershell
Get-Clipboard
```

```Output
hello
```

## PARAMETERS

### -Raw

获取剪贴板的全部内容。 多行文本以单个多行字符串而不是字符串数组的形式返回。

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

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

## 输出

### System.String

## 注释

## 相关链接

[Set-Clipboard](Set-Clipboard.md)
