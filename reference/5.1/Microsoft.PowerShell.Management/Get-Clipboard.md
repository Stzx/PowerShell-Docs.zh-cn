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
# <span data-ttu-id="cf852-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="cf852-103">Get-Clipboard</span></span>

## <span data-ttu-id="cf852-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cf852-104">SYNOPSIS</span></span>
<span data-ttu-id="cf852-105">获取当前 Windows 剪贴板条目。</span><span class="sxs-lookup"><span data-stu-id="cf852-105">Gets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="cf852-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cf852-106">SYNTAX</span></span>

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="cf852-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cf852-107">DESCRIPTION</span></span>

<span data-ttu-id="cf852-108">`Get-Clipboard`Cmdlet 将获取当前 Windows 剪贴板条目。</span><span class="sxs-lookup"><span data-stu-id="cf852-108">The `Get-Clipboard` cmdlet gets the current Windows clipboard entry.</span></span> <span data-ttu-id="cf852-109">多行文本作为字符串数组返回，类似于 `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="cf852-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

## <span data-ttu-id="cf852-110">示例</span><span class="sxs-lookup"><span data-stu-id="cf852-110">EXAMPLES</span></span>

### <span data-ttu-id="cf852-111">示例1：获取剪贴板的内容并将其显示在命令行中</span><span class="sxs-lookup"><span data-stu-id="cf852-111">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="cf852-112">在此示例中，我们已右键单击浏览器中的图像，然后选择 " **复制** " 操作。</span><span class="sxs-lookup"><span data-stu-id="cf852-112">In this example we have right-clicked on an image in a browser and chose the **Copy** action.</span></span> <span data-ttu-id="cf852-113">以下命令显示存储在剪贴板中的图像的链接（作为 URL）。</span><span class="sxs-lookup"><span data-stu-id="cf852-113">The following command displays the link, as a URL, of the image that is stored in the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### <span data-ttu-id="cf852-114">示例2：获取特定格式的剪贴板内容</span><span class="sxs-lookup"><span data-stu-id="cf852-114">Example 2: Get the content of the clipboard in a specific format</span></span>

<span data-ttu-id="cf852-115">在此示例中，我们将文件复制到 Windows Explorerby 中的剪贴板，并将其选中并按 <kbd>ctrl-c</kbd>。</span><span class="sxs-lookup"><span data-stu-id="cf852-115">In this example we copied files to the clipboard in Windows Explorerby selecting them and pressing <kbd>Ctrl-C</kbd>.</span></span> <span data-ttu-id="cf852-116">使用以下命令，你可以将剪贴板的内容作为文件列表进行访问：</span><span class="sxs-lookup"><span data-stu-id="cf852-116">Using the following command, you can access the contents of the clipboard as a list of files:</span></span>

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

## <span data-ttu-id="cf852-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cf852-117">PARAMETERS</span></span>

### <span data-ttu-id="cf852-118">-Format</span><span class="sxs-lookup"><span data-stu-id="cf852-118">-Format</span></span>

<span data-ttu-id="cf852-119">指定剪贴板的类型或格式。</span><span class="sxs-lookup"><span data-stu-id="cf852-119">Specifies the type, or format, of the clipboard.</span></span> <span data-ttu-id="cf852-120">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="cf852-120">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cf852-121">文本</span><span class="sxs-lookup"><span data-stu-id="cf852-121">Text</span></span>
- <span data-ttu-id="cf852-122">FileDropList</span><span class="sxs-lookup"><span data-stu-id="cf852-122">FileDropList</span></span>
- <span data-ttu-id="cf852-123">映像</span><span class="sxs-lookup"><span data-stu-id="cf852-123">Image</span></span>
- <span data-ttu-id="cf852-124">音频</span><span class="sxs-lookup"><span data-stu-id="cf852-124">Audio</span></span>

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

### <span data-ttu-id="cf852-125">-Raw</span><span class="sxs-lookup"><span data-stu-id="cf852-125">-Raw</span></span>

<span data-ttu-id="cf852-126">获取剪贴板的全部内容。</span><span class="sxs-lookup"><span data-stu-id="cf852-126">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="cf852-127">多行文本以单个多行字符串而不是字符串数组的形式返回。</span><span class="sxs-lookup"><span data-stu-id="cf852-127">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="cf852-128">-TextFormatType</span><span class="sxs-lookup"><span data-stu-id="cf852-128">-TextFormatType</span></span>

<span data-ttu-id="cf852-129">指定剪贴板的文本数据格式类型。</span><span class="sxs-lookup"><span data-stu-id="cf852-129">Specifies the text data format type of the clipboard.</span></span> <span data-ttu-id="cf852-130">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="cf852-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cf852-131">文本</span><span class="sxs-lookup"><span data-stu-id="cf852-131">Text</span></span>
- <span data-ttu-id="cf852-132">UnicodeText</span><span class="sxs-lookup"><span data-stu-id="cf852-132">UnicodeText</span></span>
- <span data-ttu-id="cf852-133">Rtf</span><span class="sxs-lookup"><span data-stu-id="cf852-133">Rtf</span></span>
- <span data-ttu-id="cf852-134">Html</span><span class="sxs-lookup"><span data-stu-id="cf852-134">Html</span></span>
- <span data-ttu-id="cf852-135">CommaSeparatedValue</span><span class="sxs-lookup"><span data-stu-id="cf852-135">CommaSeparatedValue</span></span>

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

### <span data-ttu-id="cf852-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cf852-136">CommonParameters</span></span>

<span data-ttu-id="cf852-137">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cf852-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cf852-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="cf852-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cf852-139">输入</span><span class="sxs-lookup"><span data-stu-id="cf852-139">INPUTS</span></span>

## <span data-ttu-id="cf852-140">输出</span><span class="sxs-lookup"><span data-stu-id="cf852-140">OUTPUTS</span></span>

### <span data-ttu-id="cf852-141">System.string、FileInfo、system.web、system.web、system.web、system.web. Image</span><span class="sxs-lookup"><span data-stu-id="cf852-141">System.String, System.IO.FileInfo, System.IO.Stream, System.Drawing.Image</span></span>

## <span data-ttu-id="cf852-142">注释</span><span class="sxs-lookup"><span data-stu-id="cf852-142">NOTES</span></span>

## <span data-ttu-id="cf852-143">相关链接</span><span class="sxs-lookup"><span data-stu-id="cf852-143">RELATED LINKS</span></span>

[<span data-ttu-id="cf852-144">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="cf852-144">Set-Clipboard</span></span>](Set-Clipboard.md)
