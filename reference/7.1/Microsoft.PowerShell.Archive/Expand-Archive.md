---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 6b89512ebc786a47ae47dd2cd8f51cb532382e02
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "93198948"
---
# <span data-ttu-id="af55f-103">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="af55f-103">Expand-Archive</span></span>

## <span data-ttu-id="af55f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="af55f-104">SYNOPSIS</span></span>
<span data-ttu-id="af55f-105"> (zipped) 文件从指定的存档中提取文件。</span><span class="sxs-lookup"><span data-stu-id="af55f-105">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="af55f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af55f-106">SYNTAX</span></span>

### <span data-ttu-id="af55f-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="af55f-107">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="af55f-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="af55f-108">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="af55f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af55f-109">DESCRIPTION</span></span>

<span data-ttu-id="af55f-110">`Expand-Archive`Cmdlet 可将指定的压缩存档文件中的文件提取到指定的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="af55f-110">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="af55f-111">存档文件允许将多个文件打包，还可选择性地将其压缩为单个压缩文件以便分发和存储。</span><span class="sxs-lookup"><span data-stu-id="af55f-111">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="af55f-112">示例</span><span class="sxs-lookup"><span data-stu-id="af55f-112">EXAMPLES</span></span>

### <span data-ttu-id="af55f-113">示例1：提取存档内容</span><span class="sxs-lookup"><span data-stu-id="af55f-113">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="af55f-114">此示例将现有存档文件的内容提取到 **DestinationPath** 参数指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="af55f-114">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="af55f-115">在此示例中，使用了 **LiteralPath** 参数，因为文件名中包含可解释为通配符的字符。</span><span class="sxs-lookup"><span data-stu-id="af55f-115">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="af55f-116">示例2：提取当前文件夹中的存档内容</span><span class="sxs-lookup"><span data-stu-id="af55f-116">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="af55f-117">此示例将当前文件夹中现有存档文件的内容提取到 **DestinationPath** 参数指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="af55f-117">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="af55f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af55f-118">PARAMETERS</span></span>

### <span data-ttu-id="af55f-119">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="af55f-119">-DestinationPath</span></span>

<span data-ttu-id="af55f-120">默认情况下，将 `Expand-Archive` 在当前位置创建与 ZIP 文件同名的文件夹。</span><span class="sxs-lookup"><span data-stu-id="af55f-120">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="af55f-121">使用参数可以指定其他文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="af55f-121">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="af55f-122">如果目标文件夹不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="af55f-122">The target folder is created if it does not exist.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af55f-123">-Force</span><span class="sxs-lookup"><span data-stu-id="af55f-123">-Force</span></span>

<span data-ttu-id="af55f-124">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="af55f-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="af55f-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="af55f-125">-LiteralPath</span></span>

<span data-ttu-id="af55f-126">指定存档文件的路径。</span><span class="sxs-lookup"><span data-stu-id="af55f-126">Specifies the path to an archive file.</span></span> <span data-ttu-id="af55f-127">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="af55f-127">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="af55f-128">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="af55f-128">Wildcard characters are not supported.</span></span> <span data-ttu-id="af55f-129">如果路径包含转义符，请将每个转义符括在单引号内，以指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="af55f-129">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af55f-130">-PassThru</span><span class="sxs-lookup"><span data-stu-id="af55f-130">-PassThru</span></span>

<span data-ttu-id="af55f-131">使 cmdlet 输出从存档扩展的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="af55f-131">Causes the cmdlet to output a list of the files expanded from the archive.</span></span>

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

### <span data-ttu-id="af55f-132">-Path</span><span class="sxs-lookup"><span data-stu-id="af55f-132">-Path</span></span>

<span data-ttu-id="af55f-133">指定存档文件的路径。</span><span class="sxs-lookup"><span data-stu-id="af55f-133">Specifies the path to the archive file.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="af55f-134">-Confirm</span><span class="sxs-lookup"><span data-stu-id="af55f-134">-Confirm</span></span>

<span data-ttu-id="af55f-135">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="af55f-135">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af55f-136">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="af55f-136">-WhatIf</span></span>

<span data-ttu-id="af55f-137">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="af55f-137">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="af55f-138">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="af55f-138">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af55f-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af55f-139">CommonParameters</span></span>
<span data-ttu-id="af55f-140">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="af55f-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af55f-141">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="af55f-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af55f-142">输入</span><span class="sxs-lookup"><span data-stu-id="af55f-142">INPUTS</span></span>

### <span data-ttu-id="af55f-143">System.String</span><span class="sxs-lookup"><span data-stu-id="af55f-143">System.String</span></span>

<span data-ttu-id="af55f-144">可以通过管道将包含路径的字符串传递给现有存档文件。</span><span class="sxs-lookup"><span data-stu-id="af55f-144">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="af55f-145">输出</span><span class="sxs-lookup"><span data-stu-id="af55f-145">OUTPUTS</span></span>

### <span data-ttu-id="af55f-146">FileSystemInfo</span><span class="sxs-lookup"><span data-stu-id="af55f-146">System.IO.FileSystemInfo</span></span>

<span data-ttu-id="af55f-147">`-PassThru`使用参数时，该 cmdlet 将输出从存档扩展的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="af55f-147">When the `-PassThru` parameter is used, the cmdlet outputs a list of files that were expanded from the archive.</span></span>

## <span data-ttu-id="af55f-148">注释</span><span class="sxs-lookup"><span data-stu-id="af55f-148">NOTES</span></span>

<span data-ttu-id="af55f-149">[ZIP 文件规范](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)未指定对包含非 ASCII 字符的文件名进行编码的标准方法。</span><span class="sxs-lookup"><span data-stu-id="af55f-149">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="af55f-150">`Compress-Archive`Cmdlet 使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="af55f-150">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="af55f-151">其他 ZIP 存档工具可以使用其他编码方案。</span><span class="sxs-lookup"><span data-stu-id="af55f-151">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="af55f-152">当使用不是使用 UTF-8 编码存储的文件名提取文件时， `Expand-Archive` 将使用存档中找到的原始值。</span><span class="sxs-lookup"><span data-stu-id="af55f-152">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="af55f-153">这可能会导致文件名不同于存储在存档中的源文件名。</span><span class="sxs-lookup"><span data-stu-id="af55f-153">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="af55f-154">相关链接</span><span class="sxs-lookup"><span data-stu-id="af55f-154">RELATED LINKS</span></span>

[<span data-ttu-id="af55f-155">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="af55f-155">Compress-Archive</span></span>](compress-archive.md)