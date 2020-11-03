---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: e7e70637afcf53f84c719b489575f5267f9048b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197384"
---
# <span data-ttu-id="9c769-101">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="9c769-101">Set-MarkdownOption</span></span>

## <span data-ttu-id="9c769-102">摘要</span><span class="sxs-lookup"><span data-stu-id="9c769-102">SYNOPSIS</span></span>
<span data-ttu-id="9c769-103">设置用于在控制台中呈现 Markdown 内容的颜色和样式。</span><span class="sxs-lookup"><span data-stu-id="9c769-103">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="9c769-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c769-104">SYNTAX</span></span>

### <span data-ttu-id="9c769-105">IndividualSetting (默认值) </span><span class="sxs-lookup"><span data-stu-id="9c769-105">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="9c769-106">主题</span><span class="sxs-lookup"><span data-stu-id="9c769-106">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="9c769-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="9c769-107">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="9c769-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c769-108">DESCRIPTION</span></span>

<span data-ttu-id="9c769-109">设置用于在控制台中呈现 Markdown 内容的颜色和样式。</span><span class="sxs-lookup"><span data-stu-id="9c769-109">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="9c769-110">使用 ANSI 转义代码定义这些样式，这些代码将更改要呈现的 Markdown 文本的颜色和样式。</span><span class="sxs-lookup"><span data-stu-id="9c769-110">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="9c769-111">有关 Markdown 的详细信息，请参阅 [CommonMark](https://commonmark.org/) 网站。</span><span class="sxs-lookup"><span data-stu-id="9c769-111">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="9c769-112">设置中使用的字符串值是位于 **转义** 符后面的字符，该字符用于 `[char]0x1B` ANSI 转义序列 () 。</span><span class="sxs-lookup"><span data-stu-id="9c769-112">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="9c769-113">不要在字符串中包含 **转义** 字符。</span><span class="sxs-lookup"><span data-stu-id="9c769-113">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="9c769-114">有关 ANSI 转义代码工作的详细信息，请参阅 [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)。</span><span class="sxs-lookup"><span data-stu-id="9c769-114">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="9c769-115">示例</span><span class="sxs-lookup"><span data-stu-id="9c769-115">EXAMPLES</span></span>

### <span data-ttu-id="9c769-116">示例 1-切换到浅色主题</span><span class="sxs-lookup"><span data-stu-id="9c769-116">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="9c769-117">此示例选择 **浅** 主题，并使用 **PassThru** 参数显示新配置。</span><span class="sxs-lookup"><span data-stu-id="9c769-117">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

```powershell
Set-MarkdownOption -Theme Light -PassThru
```

```Output
Header1         : [7m
Header2         : [4;33m
Header3         : [4;34m
Header4         : [4;35m
Header5         : [4;36m
Header6         : [4;30m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

### <span data-ttu-id="9c769-118">示例 2-自定义颜色和样式设置</span><span class="sxs-lookup"><span data-stu-id="9c769-118">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="9c769-119">此示例更改 Markdown 标头的转义码。</span><span class="sxs-lookup"><span data-stu-id="9c769-119">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="9c769-120">标头的默认配置将其呈现为各种颜色的带下划线的文本。</span><span class="sxs-lookup"><span data-stu-id="9c769-120">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="9c769-121">此更改将删除下划线样式。</span><span class="sxs-lookup"><span data-stu-id="9c769-121">This change removes the underline style.</span></span>

```powershell
$mdOptions = Get-MarkdownOption
$mdOptions.Header2 = '[93m'
$mdOptions.Header3 = '[94m'
$mdOptions.Header4 = '[95m'
$mdOptions.Header5 = '[96m'
$mdOptions.Header6 = '[97m'
Set-MarkdownOption -InputObject $mdOptions -PassThru
```

```Output
Header1         : [7m
Header2         : [93m
Header3         : [94m
Header4         : [95m
Header5         : [96m
Header6         : [97m
Code            : [48;2;155;155;155;38;2;30;30;31m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

## <span data-ttu-id="9c769-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c769-122">PARAMETERS</span></span>

### <span data-ttu-id="9c769-123">-BoldForegroundColor</span><span class="sxs-lookup"><span data-stu-id="9c769-123">-BoldForegroundColor</span></span>

<span data-ttu-id="9c769-124">设置用于呈现粗体显示的 Markdown 文本的前景色。</span><span class="sxs-lookup"><span data-stu-id="9c769-124">Sets the foreground color for rendering bold Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-125">-代码</span><span class="sxs-lookup"><span data-stu-id="9c769-125">-Code</span></span>

<span data-ttu-id="9c769-126">设置在 Markdown 文本中呈现代码块和范围的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-126">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-127">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="9c769-127">-Header1Color</span></span>

<span data-ttu-id="9c769-128">设置用于在 Markdown 文本中呈现 Header1 块的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-128">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-129">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="9c769-129">-Header2Color</span></span>

<span data-ttu-id="9c769-130">设置用于在 Markdown 文本中呈现 .Header2 块的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-130">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-131">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="9c769-131">-Header3Color</span></span>

<span data-ttu-id="9c769-132">设置用于在 Markdown 文本中呈现 Header3 块的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-132">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-133">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="9c769-133">-Header4Color</span></span>

<span data-ttu-id="9c769-134">设置用于在 Markdown 文本中呈现 Header4 块的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-134">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-135">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="9c769-135">-Header5Color</span></span>

<span data-ttu-id="9c769-136">设置用于在 Markdown 文本中呈现 Header5 块的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-136">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-137">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="9c769-137">-Header6Color</span></span>

<span data-ttu-id="9c769-138">设置用于在 Markdown 文本中呈现 Header6 块的颜色。</span><span class="sxs-lookup"><span data-stu-id="9c769-138">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-139">-ImageAltTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="9c769-139">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="9c769-140">设置用于呈现 Markdown 文本中图像元素的备用文本的前景色。</span><span class="sxs-lookup"><span data-stu-id="9c769-140">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9c769-141">-InputObject</span></span>

<span data-ttu-id="9c769-142">包含要设置的配置的 **PSMarkdownOptionInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c769-142">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-143">-ItalicsForegroundColor</span><span class="sxs-lookup"><span data-stu-id="9c769-143">-ItalicsForegroundColor</span></span>

<span data-ttu-id="9c769-144">设置用于呈现 Markdown 文本中斜体的前景色。</span><span class="sxs-lookup"><span data-stu-id="9c769-144">Sets the foreground color for rendering the italics in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-145">-LinkForegroundColor</span><span class="sxs-lookup"><span data-stu-id="9c769-145">-LinkForegroundColor</span></span>

<span data-ttu-id="9c769-146">设置用于呈现 Markdown 文本中的超链接的前景色。</span><span class="sxs-lookup"><span data-stu-id="9c769-146">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9c769-147">-PassThru</span></span>

<span data-ttu-id="9c769-148">使 cmdlet 输出包含新配置的 **PSMarkdownOptionInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c769-148">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

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

### <span data-ttu-id="9c769-149">-主题</span><span class="sxs-lookup"><span data-stu-id="9c769-149">-Theme</span></span>

<span data-ttu-id="9c769-150">选择包含预定义颜色设置的主题。</span><span class="sxs-lookup"><span data-stu-id="9c769-150">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="9c769-151">可能的值为 **深色** 和 **浅色** 。</span><span class="sxs-lookup"><span data-stu-id="9c769-151">The possible values are **Dark** and **Light** .</span></span>

```yaml
Type: System.String
Parameter Sets: Theme
Aliases:
Accepted values: Dark, Light

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c769-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c769-152">CommonParameters</span></span>

<span data-ttu-id="9c769-153">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9c769-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c769-154">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9c769-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c769-155">输入</span><span class="sxs-lookup"><span data-stu-id="9c769-155">INPUTS</span></span>

### <span data-ttu-id="9c769-156">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="9c769-156">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="9c769-157">输出</span><span class="sxs-lookup"><span data-stu-id="9c769-157">OUTPUTS</span></span>

### <span data-ttu-id="9c769-158">MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="9c769-158">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="9c769-159">注释</span><span class="sxs-lookup"><span data-stu-id="9c769-159">NOTES</span></span>

<span data-ttu-id="9c769-160">用于定义颜色和样式的字符串值必须与正则表达式匹配 `^\[*[0-9;]*?m{1}` 。</span><span class="sxs-lookup"><span data-stu-id="9c769-160">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="9c769-161">相关链接</span><span class="sxs-lookup"><span data-stu-id="9c769-161">RELATED LINKS</span></span>

[<span data-ttu-id="9c769-162">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="9c769-162">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="9c769-163">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="9c769-163">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="9c769-164">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="9c769-164">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="9c769-165">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="9c769-165">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="9c769-166">CommonMark</span><span class="sxs-lookup"><span data-stu-id="9c769-166">CommonMark</span></span>](https://commonmark.org/)

