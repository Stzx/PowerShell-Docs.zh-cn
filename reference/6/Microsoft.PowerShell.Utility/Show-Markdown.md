---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: 2d88b24519f472f0c167dc5138450ab542a8b7cf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198485"
---
# <span data-ttu-id="2cb34-103">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="2cb34-103">Show-Markdown</span></span>

## <span data-ttu-id="2cb34-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2cb34-104">SYNOPSIS</span></span>
<span data-ttu-id="2cb34-105">使用 VT100 转义序列或使用 HTML 在浏览器中以友好方式显示控制台中的 Markdown 文件或字符串。</span><span class="sxs-lookup"><span data-stu-id="2cb34-105">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="2cb34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2cb34-106">SYNTAX</span></span>

### <span data-ttu-id="2cb34-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="2cb34-107">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="2cb34-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="2cb34-108">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="2cb34-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2cb34-109">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="2cb34-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2cb34-110">DESCRIPTION</span></span>

<span data-ttu-id="2cb34-111">`Show-Markdown`Cmdlet 用于在终端或浏览器中以用户可读格式呈现 Markdown。</span><span class="sxs-lookup"><span data-stu-id="2cb34-111">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="2cb34-112">`Show-Markdown` 如果支持将 VT100 转义序列)  (，则可以返回一个字符串，其中包含终端呈现的 VT100 转义序列。</span><span class="sxs-lookup"><span data-stu-id="2cb34-112">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="2cb34-113">这主要用于查看终端中的 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="2cb34-113">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="2cb34-114">还可以通过 `ConvertFrom-Markdown` 指定 **AsVT100EncodedString** 参数获取此字符串。</span><span class="sxs-lookup"><span data-stu-id="2cb34-114">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="2cb34-115">`Show-Markdown` 还可以打开浏览器并显示 Markdown 的呈现版本。</span><span class="sxs-lookup"><span data-stu-id="2cb34-115">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="2cb34-116">它通过将其转换为 HTML 并在默认浏览器中打开 HTML 文件来呈现 Markdown。</span><span class="sxs-lookup"><span data-stu-id="2cb34-116">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="2cb34-117">可以 `Show-Markdown` 通过使用更改在终端中呈现 Markdown 的方式 `Set-MarkdownOption` 。</span><span class="sxs-lookup"><span data-stu-id="2cb34-117">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="2cb34-118">此 cmdlet 是在 PowerShell 6.1 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2cb34-118">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="2cb34-119">示例</span><span class="sxs-lookup"><span data-stu-id="2cb34-119">EXAMPLES</span></span>

### <span data-ttu-id="2cb34-120">示例1：指定路径的简单示例</span><span class="sxs-lookup"><span data-stu-id="2cb34-120">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="2cb34-121">示例2：指定字符串的简单示例</span><span class="sxs-lookup"><span data-stu-id="2cb34-121">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="2cb34-122">示例2：在浏览器中打开 Markdown</span><span class="sxs-lookup"><span data-stu-id="2cb34-122">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="2cb34-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2cb34-123">PARAMETERS</span></span>

### <span data-ttu-id="2cb34-124">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2cb34-124">-InputObject</span></span>

<span data-ttu-id="2cb34-125">将显示在终端中的 Markdown 字符串。</span><span class="sxs-lookup"><span data-stu-id="2cb34-125">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="2cb34-126">如果未传入受支持的格式， `Show-Markdown` 则将发出错误。</span><span class="sxs-lookup"><span data-stu-id="2cb34-126">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2cb34-127">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2cb34-127">-LiteralPath</span></span>

<span data-ttu-id="2cb34-128">指定 Markdown 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2cb34-128">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="2cb34-129">与 Path 参数不同，LiteralPath 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="2cb34-129">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="2cb34-130">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="2cb34-130">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2cb34-131">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="2cb34-131">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2cb34-132">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="2cb34-132">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2cb34-133">-Path</span><span class="sxs-lookup"><span data-stu-id="2cb34-133">-Path</span></span>

<span data-ttu-id="2cb34-134">指定要呈现的 Markdown 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2cb34-134">Specifies the path to a Markdown file to be rendered.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="2cb34-135">-UseBrowser</span><span class="sxs-lookup"><span data-stu-id="2cb34-135">-UseBrowser</span></span>

<span data-ttu-id="2cb34-136">将 Markdown 输入编译为 HTML，并在默认浏览器中打开它。</span><span class="sxs-lookup"><span data-stu-id="2cb34-136">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2cb34-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2cb34-137">CommonParameters</span></span>

<span data-ttu-id="2cb34-138">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2cb34-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2cb34-139">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2cb34-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2cb34-140">输入</span><span class="sxs-lookup"><span data-stu-id="2cb34-140">INPUTS</span></span>

### <span data-ttu-id="2cb34-141">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="2cb34-141">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="2cb34-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="2cb34-142">System.String[]</span></span>

## <span data-ttu-id="2cb34-143">输出</span><span class="sxs-lookup"><span data-stu-id="2cb34-143">OUTPUTS</span></span>

### <span data-ttu-id="2cb34-144">System.String</span><span class="sxs-lookup"><span data-stu-id="2cb34-144">System.String</span></span>

## <span data-ttu-id="2cb34-145">注释</span><span class="sxs-lookup"><span data-stu-id="2cb34-145">NOTES</span></span>

## <span data-ttu-id="2cb34-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="2cb34-146">RELATED LINKS</span></span>

[<span data-ttu-id="2cb34-147">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="2cb34-147">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)
