---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "93199438"
---
# Get-Clipboard

## 摘要
获取当前 Windows 剪贴板条目。

## SYNTAX

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Get-Clipboard`Cmdlet 将获取当前 Windows 剪贴板条目。 多行文本作为字符串数组返回，类似于 `Get-Content` 。

## 示例

### 示例1：获取剪贴板的内容并将其显示在命令行中

在此示例中，我们已右键单击浏览器中的图像，然后选择 " **复制** " 操作。 以下命令显示存储在剪贴板中的图像的链接（作为 URL）。

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### 示例2：获取特定格式的剪贴板内容

在此示例中，我们将文件复制到 Windows Explorerby 中的剪贴板，并将其选中并按 <kbd>ctrl-c</kbd>。 使用以下命令，你可以将剪贴板的内容作为文件列表进行访问：

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## PARAMETERS

### -Format

指定剪贴板的类型或格式。 此参数的可接受值为：

- 文本
- FileDropList
- 映像
- 音频

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -TextFormatType

指定剪贴板的文本数据格式类型。 此参数的可接受值为：

- 文本
- UnicodeText
- Rtf
- Html
- CommaSeparatedValue

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

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

### System.string、FileInfo、system.web、system.web、system.web、system.web. Image

## 注释

## 相关链接

[Set-Clipboard](Set-Clipboard.md)
