---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: 52c0a94304156a7c1cf89bbc5ae98a0668789bd2
ms.sourcegitcommit: 23ea4a36ee85f923684657de5313a5adf0b6b094
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "93194624"
---
# Get-MarkdownOption

## 摘要
返回用于在控制台中呈现 Markdown 内容的当前颜色和样式。

## SYNTAX

```
Get-MarkdownOption [<CommonParameters>]
```

## DESCRIPTION

返回用于在控制台中呈现 Markdown 内容的当前颜色和样式。 此 cmdlet 的输出中显示的字符串包含用于更改呈现的 Markdown 文本的颜色和样式的 ANSI 转义码。

有关 Markdown 的详细信息，请参阅 [CommonMark](https://commonmark.org/) 网站。

## 示例

### 示例 1-获取当前颜色和样式

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> 输出中显示的字符串值为 ANSI 转义序列 () 后面 **的字符** `[char]0x1B` 。 有关 ANSI 转义代码工作的详细信息，请参阅 [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)。

## PARAMETERS

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

## 输出

### MarkdownRender. PSMarkdownOptionInfo

## 注释

## 相关链接

[Set-MarkdownOption](Set-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)

