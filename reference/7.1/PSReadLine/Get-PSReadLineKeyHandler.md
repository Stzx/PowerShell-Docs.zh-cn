---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineKeyHandler
ms.openlocfilehash: 09a34993df29ab06a9d25e6d66770e5774bd28b0
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200675"
---
# <span data-ttu-id="6fddb-103">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="6fddb-103">Get-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="6fddb-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6fddb-104">SYNOPSIS</span></span>
<span data-ttu-id="6fddb-105">获取 PSReadLine 模块的绑定键函数。</span><span class="sxs-lookup"><span data-stu-id="6fddb-105">Gets the bound key functions for the PSReadLine module.</span></span>

## <span data-ttu-id="6fddb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6fddb-106">SYNTAX</span></span>

### <span data-ttu-id="6fddb-107">FullListing (默认值) </span><span class="sxs-lookup"><span data-stu-id="6fddb-107">FullListing (default)</span></span>

```
Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]
```

### <span data-ttu-id="6fddb-108">SpecificBindings</span><span class="sxs-lookup"><span data-stu-id="6fddb-108">SpecificBindings</span></span>

```
Get-PSReadLineKeyHandler [-Chord] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="6fddb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6fddb-109">DESCRIPTION</span></span>

<span data-ttu-id="6fddb-110">如果未指定参数，则返回 PSReadLine 模块的当前绑定键函数。</span><span class="sxs-lookup"><span data-stu-id="6fddb-110">If no parameter is specified, returns the currently bound key functions for the PSReadLine module.</span></span>

<span data-ttu-id="6fddb-111">如果指定了 **弦** 参数，则该 cmdlet 将返回特定的绑定键。</span><span class="sxs-lookup"><span data-stu-id="6fddb-111">If **Chord** parameter is specified, the cmdlet returns the specific bound keys.</span></span>

## <span data-ttu-id="6fddb-112">示例</span><span class="sxs-lookup"><span data-stu-id="6fddb-112">EXAMPLES</span></span>

### <span data-ttu-id="6fddb-113">示例1：获取所有键映射</span><span class="sxs-lookup"><span data-stu-id="6fddb-113">Example 1: Get all key mappings</span></span>

<span data-ttu-id="6fddb-114">此命令返回所有键映射、绑定和未绑定。</span><span class="sxs-lookup"><span data-stu-id="6fddb-114">This command returns all key mappings, bound and unbound.</span></span>

```powershell
Get-PSReadLineKeyHandler -Bound -Unbound
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
Shift+Tab             TabCompletePrevious     Complete the input using the previous completion
Ctrl+a                SelectAll               Select the entire line. Moves the cursor to the end of the line
Ctrl+c                CopyOrCancelLine        Either copy selected text to the clipboard, or if no text is selected, cancel editing the line with Cancel...
Ctrl+C                Copy                    Copy selected region to the system clipboard.  If no region is selected, copy the whole line
Ctrl+l                ClearScreen             Clear the screen and redraw the current line at the top of the screen
Ctrl+r                ReverseSearchHistory    Search history backwards interactively
...
```

### <span data-ttu-id="6fddb-115">示例2：获取绑定密钥</span><span class="sxs-lookup"><span data-stu-id="6fddb-115">Example 2: Get bound keys</span></span>

<span data-ttu-id="6fddb-116">此命令仅返回绑定键和组合键。</span><span class="sxs-lookup"><span data-stu-id="6fddb-116">This command returns only bound keys and key combinations.</span></span>

```powershell
Get-PSReadLineKeyHandler
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
...
```

### <span data-ttu-id="6fddb-117">示例3：获取特定的键绑定</span><span class="sxs-lookup"><span data-stu-id="6fddb-117">Example 3: Get specific key bindings</span></span>

<span data-ttu-id="6fddb-118">此命令仅返回指定密钥的绑定。</span><span class="sxs-lookup"><span data-stu-id="6fddb-118">This command returns only the bindings for the specified keys.</span></span>

```powershell
Get-PSReadLineKeyHandler -Chord Enter, Shift+Enter
```

```Output
Key         Function   Description
---         --------   -----------
Enter       AcceptLine Accept the input or move to the next line if input is missing a closing token.
Shift+Enter AddLine    Move the cursor to the next line without attempting to execute the input
...
```

## <span data-ttu-id="6fddb-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6fddb-119">PARAMETERS</span></span>

### <span data-ttu-id="6fddb-120">-绑定</span><span class="sxs-lookup"><span data-stu-id="6fddb-120">-Bound</span></span>

<span data-ttu-id="6fddb-121">指示此 cmdlet 返回绑定的函数。</span><span class="sxs-lookup"><span data-stu-id="6fddb-121">Indicates that this cmdlet returns functions that are bound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FullListing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fddb-122">-未绑定</span><span class="sxs-lookup"><span data-stu-id="6fddb-122">-Unbound</span></span>

<span data-ttu-id="6fddb-123">指示此 cmdlet 返回未绑定的函数。</span><span class="sxs-lookup"><span data-stu-id="6fddb-123">Indicates that this cmdlet returns functions that are unbound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FullListing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fddb-124">-弦</span><span class="sxs-lookup"><span data-stu-id="6fddb-124">-Chord</span></span>

<span data-ttu-id="6fddb-125">仅返回绑定到特定键或序列的函数。</span><span class="sxs-lookup"><span data-stu-id="6fddb-125">Return only functions bound to specific keys or sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SpecificBindings
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fddb-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6fddb-126">CommonParameters</span></span>

<span data-ttu-id="6fddb-127">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6fddb-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6fddb-128">有关详细信息，请参阅 [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6fddb-128">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6fddb-129">输入</span><span class="sxs-lookup"><span data-stu-id="6fddb-129">INPUTS</span></span>

### <span data-ttu-id="6fddb-130">无</span><span class="sxs-lookup"><span data-stu-id="6fddb-130">None</span></span>

<span data-ttu-id="6fddb-131">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6fddb-131">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="6fddb-132">输出</span><span class="sxs-lookup"><span data-stu-id="6fddb-132">OUTPUTS</span></span>

### <span data-ttu-id="6fddb-133">KeyHandler</span><span class="sxs-lookup"><span data-stu-id="6fddb-133">Microsoft.PowerShell.KeyHandler</span></span>

## <span data-ttu-id="6fddb-134">注释</span><span class="sxs-lookup"><span data-stu-id="6fddb-134">NOTES</span></span>

## <span data-ttu-id="6fddb-135">相关链接</span><span class="sxs-lookup"><span data-stu-id="6fddb-135">RELATED LINKS</span></span>

[<span data-ttu-id="6fddb-136">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="6fddb-136">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="6fddb-137">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="6fddb-137">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="6fddb-138">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="6fddb-138">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="6fddb-139">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="6fddb-139">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

