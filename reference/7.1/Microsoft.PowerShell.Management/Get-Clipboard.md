---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: e3c762f1d88efce9e7a126840e2c4348abe3648c
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "93199444"
---
# <span data-ttu-id="fe294-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="fe294-103">Get-Clipboard</span></span>

## <span data-ttu-id="fe294-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fe294-104">SYNOPSIS</span></span>
<span data-ttu-id="fe294-105">获取剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="fe294-105">Gets the contents of the clipboard.</span></span>

[!NOTE]
> <span data-ttu-id="fe294-106">在 Linux 上，此 cmdlet 要求 `xclip` 实用工具在路径中。</span><span class="sxs-lookup"><span data-stu-id="fe294-106">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="fe294-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe294-107">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="fe294-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fe294-108">DESCRIPTION</span></span>

<span data-ttu-id="fe294-109">`Get-Clipboard`Cmdlet 将剪贴板的内容作为文本获取。</span><span class="sxs-lookup"><span data-stu-id="fe294-109">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="fe294-110">多行文本作为字符串数组返回，类似于 `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="fe294-110">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

## <span data-ttu-id="fe294-111">示例</span><span class="sxs-lookup"><span data-stu-id="fe294-111">EXAMPLES</span></span>

### <span data-ttu-id="fe294-112">示例1：获取剪贴板的内容并将其显示在命令行中</span><span class="sxs-lookup"><span data-stu-id="fe294-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="fe294-113">在此示例中，我们已将文本 "hello" 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="fe294-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="fe294-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe294-114">PARAMETERS</span></span>

### <span data-ttu-id="fe294-115">-Raw</span><span class="sxs-lookup"><span data-stu-id="fe294-115">-Raw</span></span>

<span data-ttu-id="fe294-116">获取剪贴板的全部内容。</span><span class="sxs-lookup"><span data-stu-id="fe294-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="fe294-117">多行文本以单个多行字符串而不是字符串数组的形式返回。</span><span class="sxs-lookup"><span data-stu-id="fe294-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="fe294-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fe294-118">CommonParameters</span></span>

<span data-ttu-id="fe294-119">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fe294-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe294-120">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fe294-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe294-121">输入</span><span class="sxs-lookup"><span data-stu-id="fe294-121">INPUTS</span></span>

## <span data-ttu-id="fe294-122">输出</span><span class="sxs-lookup"><span data-stu-id="fe294-122">OUTPUTS</span></span>

### <span data-ttu-id="fe294-123">System.String</span><span class="sxs-lookup"><span data-stu-id="fe294-123">System.String</span></span>

## <span data-ttu-id="fe294-124">注释</span><span class="sxs-lookup"><span data-stu-id="fe294-124">NOTES</span></span>

## <span data-ttu-id="fe294-125">相关链接</span><span class="sxs-lookup"><span data-stu-id="fe294-125">RELATED LINKS</span></span>

[<span data-ttu-id="fe294-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="fe294-126">Set-Clipboard</span></span>](Set-Clipboard.md)

