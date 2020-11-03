---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell、cmdlet、markdown
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: efa5e65566e3b80f12f3de5ebd1277bf68c03ff0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198639"
---
# <span data-ttu-id="f06f1-103">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="f06f1-103">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="f06f1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f06f1-104">SYNOPSIS</span></span>
<span data-ttu-id="f06f1-105">将字符串或文件的内容转换为 **MarkdownInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f06f1-105">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="f06f1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f06f1-106">SYNTAX</span></span>

### <span data-ttu-id="f06f1-107">PathParamSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="f06f1-107">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="f06f1-108">LiteralParamSet</span><span class="sxs-lookup"><span data-stu-id="f06f1-108">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="f06f1-109">InputObjParamSet</span><span class="sxs-lookup"><span data-stu-id="f06f1-109">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="f06f1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f06f1-110">DESCRIPTION</span></span>

<span data-ttu-id="f06f1-111">此 cmdlet 将指定的内容转换为 **MarkdownInfo** 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-111">This cmdlet converts the specified content into a **MarkdownInfo** .</span></span> <span data-ttu-id="f06f1-112">如果为 **path** 参数指定了文件路径，则会转换文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="f06f1-112">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="f06f1-113">Output 对象具有三个属性：</span><span class="sxs-lookup"><span data-stu-id="f06f1-113">The output object has three properties:</span></span>

- <span data-ttu-id="f06f1-114">**标记** 属性的抽象语法树 (转换对象的 AST) </span><span class="sxs-lookup"><span data-stu-id="f06f1-114">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="f06f1-115">**Html** 属性具有指定输入的 html 转换</span><span class="sxs-lookup"><span data-stu-id="f06f1-115">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="f06f1-116">如果指定 **AsVT100EncodedString** 参数，则 **VT100ENCODEDSTRING** 属性具有 ANSI (VT100) 转义序列的转换后的字符串</span><span class="sxs-lookup"><span data-stu-id="f06f1-116">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="f06f1-117">此 cmdlet 是在 PowerShell 6.1 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f06f1-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="f06f1-118">示例</span><span class="sxs-lookup"><span data-stu-id="f06f1-118">EXAMPLES</span></span>

### <span data-ttu-id="f06f1-119">示例1：将包含 Markdown 内容的文件转换为 HTML</span><span class="sxs-lookup"><span data-stu-id="f06f1-119">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="f06f1-120">返回 **MarkdownInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f06f1-120">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f06f1-121">**标记** 属性包含文件的已转换内容的 AST `README.md` 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-121">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="f06f1-122">**Html** 属性包含文件的 html 转换内容 `README.md` 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-122">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="f06f1-123">示例2：将包含 Markdown 内容的文件转换为 VT100 编码的字符串</span><span class="sxs-lookup"><span data-stu-id="f06f1-123">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="f06f1-124">返回 **MarkdownInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f06f1-124">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f06f1-125">**标记** 属性包含文件的已转换内容的 AST `README.md` 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-125">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="f06f1-126">**VT100EncodedString** 属性具有 FILE 的 VT100 编码的字符串转换后的内容 `README.md` 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-126">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="f06f1-127">示例3：将包含 Markdown 内容的输入对象转换为 VT100 编码的字符串</span><span class="sxs-lookup"><span data-stu-id="f06f1-127">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="f06f1-128">返回 **MarkdownInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f06f1-128">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f06f1-129">中的 **FileInfo** 对象 `Get-Item` 将转换为 VT100 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="f06f1-129">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="f06f1-130">**标记** 属性包含文件的已转换内容的 AST `README.md` 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-130">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="f06f1-131">**VT100EncodedString** 属性具有 FILE 的 VT100 编码的字符串转换后的内容 `README.md` 。</span><span class="sxs-lookup"><span data-stu-id="f06f1-131">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="f06f1-132">示例4：将包含 Markdown 内容的字符串转换为 VT100 编码的字符串</span><span class="sxs-lookup"><span data-stu-id="f06f1-132">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="f06f1-133">返回 **MarkdownInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f06f1-133">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f06f1-134">指定的字符串 `**Bold text**` 转换为 VT100 编码的字符串，并在 **VT100EncodedString** 属性中提供。</span><span class="sxs-lookup"><span data-stu-id="f06f1-134">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="f06f1-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f06f1-135">PARAMETERS</span></span>

### <span data-ttu-id="f06f1-136">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="f06f1-136">-AsVT100EncodedString</span></span>

<span data-ttu-id="f06f1-137">指定是否应使用 VT100 转义代码将输出编码为字符串。</span><span class="sxs-lookup"><span data-stu-id="f06f1-137">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="f06f1-138">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f06f1-138">-InputObject</span></span>

<span data-ttu-id="f06f1-139">指定要转换的对象。</span><span class="sxs-lookup"><span data-stu-id="f06f1-139">Specifies the object to be converted.</span></span> <span data-ttu-id="f06f1-140">指定 **string 类型的对象时，** 将转换字符串。</span><span class="sxs-lookup"><span data-stu-id="f06f1-140">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="f06f1-141">如果指定了类型为 **FileInfo** 的对象，则将转换由该对象指定的文件的内容。</span><span class="sxs-lookup"><span data-stu-id="f06f1-141">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="f06f1-142">任何其他类型的对象都会导致错误。</span><span class="sxs-lookup"><span data-stu-id="f06f1-142">Objects of any other type result in an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f06f1-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f06f1-143">-LiteralPath</span></span>

<span data-ttu-id="f06f1-144">指定要转换的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f06f1-144">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f06f1-145">-Path</span><span class="sxs-lookup"><span data-stu-id="f06f1-145">-Path</span></span>

<span data-ttu-id="f06f1-146">指定要转换的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f06f1-146">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f06f1-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f06f1-147">CommonParameters</span></span>

<span data-ttu-id="f06f1-148">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f06f1-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f06f1-149">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f06f1-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f06f1-150">输入</span><span class="sxs-lookup"><span data-stu-id="f06f1-150">INPUTS</span></span>

### <span data-ttu-id="f06f1-151">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="f06f1-151">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="f06f1-152">输出</span><span class="sxs-lookup"><span data-stu-id="f06f1-152">OUTPUTS</span></span>

### <span data-ttu-id="f06f1-153">MarkdownRender. MarkdownInfo</span><span class="sxs-lookup"><span data-stu-id="f06f1-153">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="f06f1-154">注释</span><span class="sxs-lookup"><span data-stu-id="f06f1-154">NOTES</span></span>

## <span data-ttu-id="f06f1-155">相关链接</span><span class="sxs-lookup"><span data-stu-id="f06f1-155">RELATED LINKS</span></span>

[<span data-ttu-id="f06f1-156">Markdown 分析器</span><span class="sxs-lookup"><span data-stu-id="f06f1-156">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="f06f1-157">ANSI 转义码</span><span class="sxs-lookup"><span data-stu-id="f06f1-157">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)
