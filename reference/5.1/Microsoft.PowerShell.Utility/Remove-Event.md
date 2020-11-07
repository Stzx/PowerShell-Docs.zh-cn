---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 35d5d75cad2855753504549262abd2e14af200c0
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344484"
---
# <span data-ttu-id="0e009-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="0e009-103">Remove-Event</span></span>

## <span data-ttu-id="0e009-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0e009-104">SYNOPSIS</span></span>
<span data-ttu-id="0e009-105">从事件队列中删除事件。</span><span class="sxs-lookup"><span data-stu-id="0e009-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="0e009-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e009-106">SYNTAX</span></span>

### <span data-ttu-id="0e009-107">BySource（默认值）</span><span class="sxs-lookup"><span data-stu-id="0e009-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e009-108">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="0e009-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e009-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e009-109">DESCRIPTION</span></span>

<span data-ttu-id="0e009-110">`Remove-Event`Cmdlet 从当前会话中的事件队列中删除事件。</span><span class="sxs-lookup"><span data-stu-id="0e009-110">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="0e009-111">此 cmdlet 仅删除当前位于队列中的事件。</span><span class="sxs-lookup"><span data-stu-id="0e009-111">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="0e009-112">若要取消事件注册或取消订阅，请使用 `Unregister-Event` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e009-112">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="0e009-113">示例</span><span class="sxs-lookup"><span data-stu-id="0e009-113">EXAMPLES</span></span>

### <span data-ttu-id="0e009-114">示例1：按源标识符删除事件</span><span class="sxs-lookup"><span data-stu-id="0e009-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="0e009-115">此命令从事件队列中删除源标识符为 "进程" 的事件。</span><span class="sxs-lookup"><span data-stu-id="0e009-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="0e009-116">示例2：按事件标识符删除事件</span><span class="sxs-lookup"><span data-stu-id="0e009-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="0e009-117">此命令从事件队列中删除事件 ID 为 30 的事件。</span><span class="sxs-lookup"><span data-stu-id="0e009-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="0e009-118">示例3：删除所有事件</span><span class="sxs-lookup"><span data-stu-id="0e009-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="0e009-119">此命令从事件队列中删除所有事件。</span><span class="sxs-lookup"><span data-stu-id="0e009-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="0e009-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e009-120">PARAMETERS</span></span>

### <span data-ttu-id="0e009-121">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="0e009-121">-EventIdentifier</span></span>

<span data-ttu-id="0e009-122">指定 cmdlet 删除的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="0e009-122">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="0e009-123">每个命令中都需要 **EventIdentifier** 或 **SourceIdentifier** 参数。</span><span class="sxs-lookup"><span data-stu-id="0e009-123">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e009-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="0e009-124">-SourceIdentifier</span></span>

<span data-ttu-id="0e009-125">指定此 cmdlet 从中删除事件的源标识符。</span><span class="sxs-lookup"><span data-stu-id="0e009-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="0e009-126">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0e009-126">Wildcards are not permitted.</span></span> <span data-ttu-id="0e009-127">每个命令中都需要 **EventIdentifier** 或 **SourceIdentifier** 参数。</span><span class="sxs-lookup"><span data-stu-id="0e009-127">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e009-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e009-128">-Confirm</span></span>

<span data-ttu-id="0e009-129">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="0e009-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e009-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e009-130">-WhatIf</span></span>

<span data-ttu-id="0e009-131">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="0e009-131">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0e009-132">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="0e009-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e009-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e009-133">CommonParameters</span></span>

<span data-ttu-id="0e009-134">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0e009-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e009-135">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0e009-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e009-136">输入</span><span class="sxs-lookup"><span data-stu-id="0e009-136">INPUTS</span></span>

### <span data-ttu-id="0e009-137">System.Management.Automation.PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="0e009-137">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="0e009-138">可以通过管道将事件传递 `Get-Event` 给 `Remove-Event` 。</span><span class="sxs-lookup"><span data-stu-id="0e009-138">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="0e009-139">输出</span><span class="sxs-lookup"><span data-stu-id="0e009-139">OUTPUTS</span></span>

### <span data-ttu-id="0e009-140">None</span><span class="sxs-lookup"><span data-stu-id="0e009-140">None</span></span>

<span data-ttu-id="0e009-141">该 cmdlet 不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="0e009-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0e009-142">注释</span><span class="sxs-lookup"><span data-stu-id="0e009-142">NOTES</span></span>

<span data-ttu-id="0e009-143">事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="0e009-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="0e009-144">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="0e009-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="0e009-145">相关链接</span><span class="sxs-lookup"><span data-stu-id="0e009-145">RELATED LINKS</span></span>

[<span data-ttu-id="0e009-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="0e009-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="0e009-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="0e009-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="0e009-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="0e009-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="0e009-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="0e009-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="0e009-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="0e009-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="0e009-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="0e009-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="0e009-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="0e009-152">Wait-Event</span></span>](Wait-Event.md)
