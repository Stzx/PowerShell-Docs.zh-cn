---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 85e4ac857135a6df8215dcfe415057dd8aacde86
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197027"
---
# <span data-ttu-id="2e497-103">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="2e497-103">Clear-RecycleBin</span></span>

## <span data-ttu-id="2e497-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2e497-104">SYNOPSIS</span></span>
<span data-ttu-id="2e497-105">清除回收站的内容。</span><span class="sxs-lookup"><span data-stu-id="2e497-105">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="2e497-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e497-106">SYNTAX</span></span>

### <span data-ttu-id="2e497-107">全部</span><span class="sxs-lookup"><span data-stu-id="2e497-107">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2e497-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e497-108">DESCRIPTION</span></span>

<span data-ttu-id="2e497-109">`Clear-RecycleBin`Cmdlet 删除计算机回收站的内容。</span><span class="sxs-lookup"><span data-stu-id="2e497-109">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="2e497-110">此操作类似于使用 Windows **空回收站** 。</span><span class="sxs-lookup"><span data-stu-id="2e497-110">This action is like using Windows **Empty Recycle Bin** .</span></span>

<span data-ttu-id="2e497-111">此 cmdlet 已在 PowerShell 7 中 readded。</span><span class="sxs-lookup"><span data-stu-id="2e497-111">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="2e497-112">示例</span><span class="sxs-lookup"><span data-stu-id="2e497-112">EXAMPLES</span></span>

### <span data-ttu-id="2e497-113">1：清除所有回收站</span><span class="sxs-lookup"><span data-stu-id="2e497-113">1: Clear all recycle bins</span></span>

<span data-ttu-id="2e497-114">在此示例中，所有本地计算机的回收站都将被清除。</span><span class="sxs-lookup"><span data-stu-id="2e497-114">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="2e497-115">`Clear-RecycleBin` 提示用户确认是否要清除本地计算机上的所有回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-115">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="2e497-116">2：清除指定的回收站</span><span class="sxs-lookup"><span data-stu-id="2e497-116">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="2e497-117">此示例将为指定驱动器号清除回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-117">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="2e497-118">`Clear-RecycleBin` 使用 **驱动器号** 参数在 **C** 卷上指定回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-118">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="2e497-119">系统将提示用户进行确认以运行该命令。</span><span class="sxs-lookup"><span data-stu-id="2e497-119">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="2e497-120">3：清除所有回收站而不进行确认</span><span class="sxs-lookup"><span data-stu-id="2e497-120">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="2e497-121">此示例不会提示确认是否要清除本地计算机的回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-121">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="2e497-122">`Clear-RecycleBin` 使用 **Force** 参数，而不提示用户确认清除本地计算机上的所有回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-122">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="2e497-123">替代方法是将替换 `-Force` 为 `-Confirm:$false` 。</span><span class="sxs-lookup"><span data-stu-id="2e497-123">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="2e497-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e497-124">PARAMETERS</span></span>

### <span data-ttu-id="2e497-125">-驱动器号</span><span class="sxs-lookup"><span data-stu-id="2e497-125">-DriveLetter</span></span>

<span data-ttu-id="2e497-126">指定为单个驱动器号或驱动器号数组清除的回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-126">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2e497-127">-Force</span><span class="sxs-lookup"><span data-stu-id="2e497-127">-Force</span></span>

<span data-ttu-id="2e497-128">指定不提示用户确认是否要清除回收站。</span><span class="sxs-lookup"><span data-stu-id="2e497-128">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span>

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

### <span data-ttu-id="2e497-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2e497-129">-Confirm</span></span>

<span data-ttu-id="2e497-130">在运行 cmdlet 之前提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="2e497-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="2e497-131">即使未指定 **Confirm** 参数，也会提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="2e497-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="2e497-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2e497-132">-WhatIf</span></span>

<span data-ttu-id="2e497-133">显示运行时将发生 `Clear-RecycleBin` 的情况。</span><span class="sxs-lookup"><span data-stu-id="2e497-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="2e497-134">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2e497-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2e497-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e497-135">CommonParameters</span></span>

<span data-ttu-id="2e497-136">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2e497-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e497-137">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2e497-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e497-138">输入</span><span class="sxs-lookup"><span data-stu-id="2e497-138">INPUTS</span></span>

## <span data-ttu-id="2e497-139">输出</span><span class="sxs-lookup"><span data-stu-id="2e497-139">OUTPUTS</span></span>

### <span data-ttu-id="2e497-140">无</span><span class="sxs-lookup"><span data-stu-id="2e497-140">None</span></span>

## <span data-ttu-id="2e497-141">注释</span><span class="sxs-lookup"><span data-stu-id="2e497-141">NOTES</span></span>

## <span data-ttu-id="2e497-142">相关链接</span><span class="sxs-lookup"><span data-stu-id="2e497-142">RELATED LINKS</span></span>
