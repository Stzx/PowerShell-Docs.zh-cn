---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: c1cf126e41a5e918afffbc41d30f957e650efdf5
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564496"
---
# <span data-ttu-id="0e16d-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="0e16d-102">Set-Clipboard</span></span>

## <span data-ttu-id="0e16d-103">摘要</span><span class="sxs-lookup"><span data-stu-id="0e16d-103">SYNOPSIS</span></span>
<span data-ttu-id="0e16d-104">设置当前 Windows 剪贴板条目。</span><span class="sxs-lookup"><span data-stu-id="0e16d-104">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="0e16d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e16d-105">SYNTAX</span></span>

### <span data-ttu-id="0e16d-106">String (默认值) </span><span class="sxs-lookup"><span data-stu-id="0e16d-106">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e16d-107">值</span><span class="sxs-lookup"><span data-stu-id="0e16d-107">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e16d-108">路径</span><span class="sxs-lookup"><span data-stu-id="0e16d-108">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e16d-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0e16d-109">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e16d-110">说明</span><span class="sxs-lookup"><span data-stu-id="0e16d-110">DESCRIPTION</span></span>

<span data-ttu-id="0e16d-111">`Set-Clipboard`Cmdlet 用于设置当前 Windows 剪贴板条目。</span><span class="sxs-lookup"><span data-stu-id="0e16d-111">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="0e16d-112">示例</span><span class="sxs-lookup"><span data-stu-id="0e16d-112">EXAMPLES</span></span>

### <span data-ttu-id="0e16d-113">示例1：将文本复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="0e16d-113">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="0e16d-114">示例2：将目录的内容复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="0e16d-114">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="0e16d-115">此示例将指定文件夹的内容复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0e16d-115">This example copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

### <span data-ttu-id="0e16d-116">示例3：将文件的内容复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="0e16d-116">Example 3: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="0e16d-117">此示例将文件的内容传输到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0e16d-117">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="0e16d-118">在此示例中，我们将获得一个公共 ssh 密钥，以便可以将其粘贴到其他应用程序（例如 GitHub）中。</span><span class="sxs-lookup"><span data-stu-id="0e16d-118">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="0e16d-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e16d-119">PARAMETERS</span></span>

### <span data-ttu-id="0e16d-120">-Append</span><span class="sxs-lookup"><span data-stu-id="0e16d-120">-Append</span></span>

<span data-ttu-id="0e16d-121">指示 cmdlet 不清除剪贴板，并向其追加内容。</span><span class="sxs-lookup"><span data-stu-id="0e16d-121">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="0e16d-122">-AsHtml</span><span class="sxs-lookup"><span data-stu-id="0e16d-122">-AsHtml</span></span>

<span data-ttu-id="0e16d-123">指示该 cmdlet 将内容以 HTML 格式呈现到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0e16d-123">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="0e16d-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0e16d-124">-LiteralPath</span></span>

<span data-ttu-id="0e16d-125">指定复制到剪贴板的项的路径。</span><span class="sxs-lookup"><span data-stu-id="0e16d-125">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="0e16d-126">不同于 **Path**，**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="0e16d-126">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0e16d-127">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="0e16d-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0e16d-128">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="0e16d-128">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0e16d-129">单引号会告知 Windows PowerShell 不要将所有字符都解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="0e16d-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="0e16d-130">-Path</span><span class="sxs-lookup"><span data-stu-id="0e16d-130">-Path</span></span>

<span data-ttu-id="0e16d-131">指定复制到剪贴板的项的路径。</span><span class="sxs-lookup"><span data-stu-id="0e16d-131">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="0e16d-132">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0e16d-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0e16d-133">-Value</span><span class="sxs-lookup"><span data-stu-id="0e16d-133">-Value</span></span>

<span data-ttu-id="0e16d-134">指定要复制到剪贴板的内容（作为字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="0e16d-134">Specifies, as a string array, the content to copy to the clipboard.</span></span>

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

### <span data-ttu-id="0e16d-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e16d-135">-Confirm</span></span>

<span data-ttu-id="0e16d-136">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="0e16d-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e16d-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e16d-137">-WhatIf</span></span>

<span data-ttu-id="0e16d-138">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="0e16d-138">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0e16d-139">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="0e16d-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e16d-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e16d-140">CommonParameters</span></span>

<span data-ttu-id="0e16d-141">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0e16d-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e16d-142">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0e16d-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e16d-143">输入</span><span class="sxs-lookup"><span data-stu-id="0e16d-143">INPUTS</span></span>

### <span data-ttu-id="0e16d-144">System.String[]</span><span class="sxs-lookup"><span data-stu-id="0e16d-144">System.String[]</span></span>

## <span data-ttu-id="0e16d-145">输出</span><span class="sxs-lookup"><span data-stu-id="0e16d-145">OUTPUTS</span></span>

## <span data-ttu-id="0e16d-146">注释</span><span class="sxs-lookup"><span data-stu-id="0e16d-146">NOTES</span></span>

<span data-ttu-id="0e16d-147">在极少数情况下 `Set-Clipboard` ，当快速连续使用具有大量值的情况（例如在循环中）时，可能偶尔会从剪贴板获取空白值。</span><span class="sxs-lookup"><span data-stu-id="0e16d-147">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="0e16d-148">可以通过在循环中使用来解决此情况 `Start-Sleep -Milliseconds 1` 。</span><span class="sxs-lookup"><span data-stu-id="0e16d-148">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="0e16d-149">相关链接</span><span class="sxs-lookup"><span data-stu-id="0e16d-149">RELATED LINKS</span></span>

[<span data-ttu-id="0e16d-150">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="0e16d-150">Get-Clipboard</span></span>](Get-Clipboard.md)
