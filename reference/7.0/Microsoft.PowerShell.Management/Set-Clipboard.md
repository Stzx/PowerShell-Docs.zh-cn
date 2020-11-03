---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/09/2019
online version: https://go.microsoft.com/fwlink/?linkid=526220
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: c4a4d4c98f0da892d16a9953b2cdc890dda41bd0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197240"
---
# <span data-ttu-id="e8378-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="e8378-103">Set-Clipboard</span></span>

## <span data-ttu-id="e8378-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e8378-104">SYNOPSIS</span></span>
<span data-ttu-id="e8378-105">设置剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="e8378-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="e8378-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8378-106">SYNTAX</span></span>

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e8378-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e8378-107">DESCRIPTION</span></span>

<span data-ttu-id="e8378-108">`Set-Clipboard`Cmdlet 设置剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="e8378-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

[!NOTE]
> <span data-ttu-id="e8378-109">在 Linux 上，此 cmdlet 要求 `xclip` 实用工具在路径中。</span><span class="sxs-lookup"><span data-stu-id="e8378-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="e8378-110">示例</span><span class="sxs-lookup"><span data-stu-id="e8378-110">EXAMPLES</span></span>

### <span data-ttu-id="e8378-111">示例1：将文本复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="e8378-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

## <span data-ttu-id="e8378-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8378-112">PARAMETERS</span></span>

### <span data-ttu-id="e8378-113">-Append</span><span class="sxs-lookup"><span data-stu-id="e8378-113">-Append</span></span>

<span data-ttu-id="e8378-114">指示 cmdlet 不清除剪贴板，并向其追加内容。</span><span class="sxs-lookup"><span data-stu-id="e8378-114">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="e8378-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e8378-115">-Confirm</span></span>

<span data-ttu-id="e8378-116">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e8378-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e8378-117">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e8378-117">-WhatIf</span></span>

<span data-ttu-id="e8378-118">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e8378-118">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e8378-119">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e8378-119">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e8378-120">-Value</span><span class="sxs-lookup"><span data-stu-id="e8378-120">-Value</span></span>

<span data-ttu-id="e8378-121">要添加到剪贴板中的字符串值。</span><span class="sxs-lookup"><span data-stu-id="e8378-121">The string values to be added to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e8378-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e8378-122">CommonParameters</span></span>

<span data-ttu-id="e8378-123">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e8378-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e8378-124">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e8378-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e8378-125">输入</span><span class="sxs-lookup"><span data-stu-id="e8378-125">INPUTS</span></span>

### <span data-ttu-id="e8378-126">System.String[]</span><span class="sxs-lookup"><span data-stu-id="e8378-126">System.String[]</span></span>

## <span data-ttu-id="e8378-127">输出</span><span class="sxs-lookup"><span data-stu-id="e8378-127">OUTPUTS</span></span>

## <span data-ttu-id="e8378-128">注释</span><span class="sxs-lookup"><span data-stu-id="e8378-128">NOTES</span></span>

<span data-ttu-id="e8378-129">在极少数情况下 `Set-Clipboard` ，当快速连续使用具有大量值的情况（例如在循环中）时，可能偶尔会从剪贴板获取空白值。</span><span class="sxs-lookup"><span data-stu-id="e8378-129">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="e8378-130">可以通过在循环中使用来解决此情况 `Start-Sleep -Milliseconds 1` 。</span><span class="sxs-lookup"><span data-stu-id="e8378-130">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="e8378-131">相关链接</span><span class="sxs-lookup"><span data-stu-id="e8378-131">RELATED LINKS</span></span>

[<span data-ttu-id="e8378-132">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="e8378-132">Get-Clipboard</span></span>](Get-Clipboard.md)
