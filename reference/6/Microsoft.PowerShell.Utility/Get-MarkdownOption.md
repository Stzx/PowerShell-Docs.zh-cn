---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-6&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: df141d99080a0d893d72691f6032684097dfd966
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "93194622"
---
# <span data-ttu-id="fa4df-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="fa4df-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="fa4df-102">摘要</span><span class="sxs-lookup"><span data-stu-id="fa4df-102">SYNOPSIS</span></span>
<span data-ttu-id="fa4df-103">返回用于在控制台中呈现 Markdown 内容的当前颜色和样式。</span><span class="sxs-lookup"><span data-stu-id="fa4df-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="fa4df-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa4df-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="fa4df-105">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa4df-105">DESCRIPTION</span></span>

<span data-ttu-id="fa4df-106">返回用于在控制台中呈现 Markdown 内容的当前颜色和样式。</span><span class="sxs-lookup"><span data-stu-id="fa4df-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="fa4df-107">此 cmdlet 的输出中显示的字符串包含用于更改呈现的 Markdown 文本的颜色和样式的 ANSI 转义码。</span><span class="sxs-lookup"><span data-stu-id="fa4df-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="fa4df-108">有关 Markdown 的详细信息，请参阅 [CommonMark](https://commonmark.org/) 网站。</span><span class="sxs-lookup"><span data-stu-id="fa4df-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="fa4df-109">示例</span><span class="sxs-lookup"><span data-stu-id="fa4df-109">EXAMPLES</span></span>

### <span data-ttu-id="fa4df-110">示例 1-获取当前颜色和样式</span><span class="sxs-lookup"><span data-stu-id="fa4df-110">Example 1 - Get the current colors and style</span></span>

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
> <span data-ttu-id="fa4df-111">输出中显示的字符串值为 ANSI 转义序列 () 后面 **的字符** `[char]0x1B` 。</span><span class="sxs-lookup"><span data-stu-id="fa4df-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="fa4df-112">有关 ANSI 转义代码工作的详细信息，请参阅 [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)。</span><span class="sxs-lookup"><span data-stu-id="fa4df-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="fa4df-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa4df-113">PARAMETERS</span></span>

### <span data-ttu-id="fa4df-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fa4df-114">CommonParameters</span></span>

<span data-ttu-id="fa4df-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fa4df-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa4df-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fa4df-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa4df-117">输入</span><span class="sxs-lookup"><span data-stu-id="fa4df-117">INPUTS</span></span>

### <span data-ttu-id="fa4df-118">无</span><span class="sxs-lookup"><span data-stu-id="fa4df-118">None</span></span>

## <span data-ttu-id="fa4df-119">输出</span><span class="sxs-lookup"><span data-stu-id="fa4df-119">OUTPUTS</span></span>

### <span data-ttu-id="fa4df-120">MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="fa4df-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="fa4df-121">注释</span><span class="sxs-lookup"><span data-stu-id="fa4df-121">NOTES</span></span>

## <span data-ttu-id="fa4df-122">相关链接</span><span class="sxs-lookup"><span data-stu-id="fa4df-122">RELATED LINKS</span></span>

[<span data-ttu-id="fa4df-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="fa4df-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="fa4df-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="fa4df-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="fa4df-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="fa4df-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="fa4df-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="fa4df-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="fa4df-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="fa4df-127">CommonMark</span></span>](https://commonmark.org/)
