---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: 1c6a21880bba0f074388c6e32baa8e1c7e93413d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200696"
---
# <span data-ttu-id="8172f-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="8172f-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="8172f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8172f-104">SYNOPSIS</span></span>
<span data-ttu-id="8172f-105">删除键绑定。</span><span class="sxs-lookup"><span data-stu-id="8172f-105">Removes a key binding.</span></span>

## <span data-ttu-id="8172f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8172f-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="8172f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8172f-107">DESCRIPTION</span></span>

<span data-ttu-id="8172f-108">`Remove-PSReadLineKeyHandler`Cmdlet 将删除指定的键绑定。</span><span class="sxs-lookup"><span data-stu-id="8172f-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="8172f-109">示例</span><span class="sxs-lookup"><span data-stu-id="8172f-109">EXAMPLES</span></span>

### <span data-ttu-id="8172f-110">示例1：删除绑定</span><span class="sxs-lookup"><span data-stu-id="8172f-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="8172f-111">此命令从键组合或弦形中删除绑定 `Ctrl+B` 。</span><span class="sxs-lookup"><span data-stu-id="8172f-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="8172f-112">`Ctrl+B`在项目中创建了弦 `Set-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="8172f-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="8172f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8172f-113">PARAMETERS</span></span>

### <span data-ttu-id="8172f-114">-弦</span><span class="sxs-lookup"><span data-stu-id="8172f-114">-Chord</span></span>

<span data-ttu-id="8172f-115">指定要删除的键或键序列的数组。</span><span class="sxs-lookup"><span data-stu-id="8172f-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="8172f-116">单个绑定使用单个字符串指定。</span><span class="sxs-lookup"><span data-stu-id="8172f-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="8172f-117">如果绑定是键序列，请用逗号分隔键，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8172f-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="8172f-118">此参数接受字符串数组。</span><span class="sxs-lookup"><span data-stu-id="8172f-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="8172f-119">每个字符串都是一个单独的绑定，而不是单个绑定的键序列。</span><span class="sxs-lookup"><span data-stu-id="8172f-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8172f-120">-ViMode</span><span class="sxs-lookup"><span data-stu-id="8172f-120">-ViMode</span></span>

<span data-ttu-id="8172f-121">指定绑定应用于哪种 vi 模式。</span><span class="sxs-lookup"><span data-stu-id="8172f-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="8172f-122">可能的值为： Insert、Command。</span><span class="sxs-lookup"><span data-stu-id="8172f-122">Possible values are: Insert, Command.</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8172f-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8172f-123">CommonParameters</span></span>

<span data-ttu-id="8172f-124">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8172f-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8172f-125">有关详细信息，请参阅 [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8172f-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8172f-126">输入</span><span class="sxs-lookup"><span data-stu-id="8172f-126">INPUTS</span></span>

### <span data-ttu-id="8172f-127">无</span><span class="sxs-lookup"><span data-stu-id="8172f-127">None</span></span>

<span data-ttu-id="8172f-128">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8172f-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="8172f-129">输出</span><span class="sxs-lookup"><span data-stu-id="8172f-129">OUTPUTS</span></span>

### <span data-ttu-id="8172f-130">无</span><span class="sxs-lookup"><span data-stu-id="8172f-130">None</span></span>

## <span data-ttu-id="8172f-131">注释</span><span class="sxs-lookup"><span data-stu-id="8172f-131">NOTES</span></span>

## <span data-ttu-id="8172f-132">相关链接</span><span class="sxs-lookup"><span data-stu-id="8172f-132">RELATED LINKS</span></span>

[<span data-ttu-id="8172f-133">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="8172f-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="8172f-134">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="8172f-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="8172f-135">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="8172f-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="8172f-136">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="8172f-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
