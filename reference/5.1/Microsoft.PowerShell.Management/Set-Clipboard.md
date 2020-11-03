---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198047"
---
# <span data-ttu-id="045c9-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="045c9-103">Set-Clipboard</span></span>

## <span data-ttu-id="045c9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="045c9-104">SYNOPSIS</span></span>
<span data-ttu-id="045c9-105">设置当前 Windows 剪贴板条目。</span><span class="sxs-lookup"><span data-stu-id="045c9-105">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="045c9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="045c9-106">SYNTAX</span></span>

### <span data-ttu-id="045c9-107">String (默认值) </span><span class="sxs-lookup"><span data-stu-id="045c9-107">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="045c9-108">Value</span><span class="sxs-lookup"><span data-stu-id="045c9-108">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="045c9-109">`Path`</span><span class="sxs-lookup"><span data-stu-id="045c9-109">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="045c9-110">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="045c9-110">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="045c9-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="045c9-111">DESCRIPTION</span></span>

<span data-ttu-id="045c9-112">`Set-Clipboard`Cmdlet 用于设置当前 Windows 剪贴板条目。</span><span class="sxs-lookup"><span data-stu-id="045c9-112">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="045c9-113">示例</span><span class="sxs-lookup"><span data-stu-id="045c9-113">EXAMPLES</span></span>

### <span data-ttu-id="045c9-114">示例1：将文本复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="045c9-114">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="045c9-115">示例2：将目录的内容复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="045c9-115">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="045c9-116">此命令将指定文件夹的内容复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="045c9-116">This command copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## <span data-ttu-id="045c9-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="045c9-117">PARAMETERS</span></span>

### <span data-ttu-id="045c9-118">-Append</span><span class="sxs-lookup"><span data-stu-id="045c9-118">-Append</span></span>

<span data-ttu-id="045c9-119">指示 cmdlet 不清除剪贴板，并向其追加内容。</span><span class="sxs-lookup"><span data-stu-id="045c9-119">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="045c9-120">-AsHtml</span><span class="sxs-lookup"><span data-stu-id="045c9-120">-AsHtml</span></span>

<span data-ttu-id="045c9-121">指示该 cmdlet 将内容以 HTML 格式呈现到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="045c9-121">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="045c9-122">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="045c9-122">-LiteralPath</span></span>

<span data-ttu-id="045c9-123">指定复制到剪贴板的项的路径。</span><span class="sxs-lookup"><span data-stu-id="045c9-123">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="045c9-124">不同于 **Path** ， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="045c9-124">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="045c9-125">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="045c9-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="045c9-126">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="045c9-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="045c9-127">单引号会告知 Windows PowerShell 不要将所有字符都解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="045c9-127">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="045c9-128">-Path</span><span class="sxs-lookup"><span data-stu-id="045c9-128">-Path</span></span>

<span data-ttu-id="045c9-129">指定复制到剪贴板的项的路径。</span><span class="sxs-lookup"><span data-stu-id="045c9-129">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="045c9-130">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="045c9-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="045c9-131">-Value</span><span class="sxs-lookup"><span data-stu-id="045c9-131">-Value</span></span>

<span data-ttu-id="045c9-132">指定要复制到剪贴板的内容（作为字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="045c9-132">Specifies, as a string array, the content to copy to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="045c9-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="045c9-133">-Confirm</span></span>

<span data-ttu-id="045c9-134">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="045c9-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="045c9-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="045c9-135">-WhatIf</span></span>

<span data-ttu-id="045c9-136">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="045c9-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="045c9-137">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="045c9-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="045c9-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="045c9-138">CommonParameters</span></span>

<span data-ttu-id="045c9-139">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="045c9-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="045c9-140">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="045c9-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="045c9-141">输入</span><span class="sxs-lookup"><span data-stu-id="045c9-141">INPUTS</span></span>

### <span data-ttu-id="045c9-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="045c9-142">System.String[]</span></span>

## <span data-ttu-id="045c9-143">输出</span><span class="sxs-lookup"><span data-stu-id="045c9-143">OUTPUTS</span></span>

## <span data-ttu-id="045c9-144">注释</span><span class="sxs-lookup"><span data-stu-id="045c9-144">NOTES</span></span>

<span data-ttu-id="045c9-145">在极少数情况下 `Set-Clipboard` ，当快速连续使用具有大量值的情况（例如在循环中）时，可能偶尔会从剪贴板获取空白值。</span><span class="sxs-lookup"><span data-stu-id="045c9-145">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="045c9-146">可以通过在循环中使用来解决此情况 `Start-Sleep -Milliseconds 1` 。</span><span class="sxs-lookup"><span data-stu-id="045c9-146">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="045c9-147">相关链接</span><span class="sxs-lookup"><span data-stu-id="045c9-147">RELATED LINKS</span></span>

[<span data-ttu-id="045c9-148">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="045c9-148">Get-Clipboard</span></span>](Get-Clipboard.md)
