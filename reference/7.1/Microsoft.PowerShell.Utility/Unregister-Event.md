---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 9373cb1c5080b95317925937ccf04baa3d335bea
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344144"
---
# <span data-ttu-id="9cc3c-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="9cc3c-103">Unregister-Event</span></span>

## <span data-ttu-id="9cc3c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9cc3c-104">SYNOPSIS</span></span>
<span data-ttu-id="9cc3c-105">取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="9cc3c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9cc3c-106">SYNTAX</span></span>

### <span data-ttu-id="9cc3c-107">BySource（默认值）</span><span class="sxs-lookup"><span data-stu-id="9cc3c-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9cc3c-108">ById</span><span class="sxs-lookup"><span data-stu-id="9cc3c-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9cc3c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9cc3c-109">DESCRIPTION</span></span>

<span data-ttu-id="9cc3c-110">`Unregister-Event`Cmdlet 将取消使用 `Register-EngineEvent` 、 `Register-ObjectEvent` 或 cmdlet 创建的事件订阅 `Register-WmiEvent` 。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-110">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="9cc3c-111">取消事件订阅后，将从会话中删除事件订阅服务器，并且不再将订阅的事件添加到事件队列中。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="9cc3c-112">当你取消对使用 cmdlet 创建的事件的订阅时 `New-Event` ，还将从会话中删除新事件。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-112">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="9cc3c-113">`Unregister-Event` 不会从事件队列中删除事件。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-113">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="9cc3c-114">若要删除事件，请使用 `Remove-Event` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-114">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="9cc3c-115">示例</span><span class="sxs-lookup"><span data-stu-id="9cc3c-115">EXAMPLES</span></span>

### <span data-ttu-id="9cc3c-116">示例 1：按源标识符取消事件订阅</span><span class="sxs-lookup"><span data-stu-id="9cc3c-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="9cc3c-117">此命令将取消源标识符为 ProcessStarted 的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="9cc3c-118">若要查找事件的源标识符，请使用 `Get-Event` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-118">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="9cc3c-119">若要查找事件订阅的源标识符，请使用 `Get-EventSubscriber` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-119">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="9cc3c-120">示例 2：按订阅标识符取消事件订阅</span><span class="sxs-lookup"><span data-stu-id="9cc3c-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="9cc3c-121">此命令将取消订阅标识符为 2 的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="9cc3c-122">若要查找事件订阅的订阅标识符，请使用 `Get-EventSubscriber` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-122">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="9cc3c-123">示例 3：取消所有事件订阅</span><span class="sxs-lookup"><span data-stu-id="9cc3c-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="9cc3c-124">此命令将取消会话中的所有事件订阅。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="9cc3c-125">该命令使用 `Get-EventSubscriber` cmdlet 来获取会话中的所有事件订阅服务器对象，包括通过使用事件注册 cmdlet 的 **SupportEvent** 参数隐藏的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-125">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="9cc3c-126">它使用管道运算符 (`|`) 将订阅服务器对象发送到 `Unregister-Event` ，后者将从会话中删除这些对象。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-126">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="9cc3c-127">若要完成任务，还需要在上执行 **Force** 参数 `Unregister-Event` 。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-127">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="9cc3c-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9cc3c-128">PARAMETERS</span></span>

### <span data-ttu-id="9cc3c-129">-Force</span><span class="sxs-lookup"><span data-stu-id="9cc3c-129">-Force</span></span>

<span data-ttu-id="9cc3c-130">取消所有事件订阅，包括通过使用、和的 **SupportEvent** 参数隐藏的订阅 `Register-ObjectEvent` `Register-WmiEvent` `Register-EngineEvent` 。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-130">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="9cc3c-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="9cc3c-131">-SourceIdentifier</span></span>

<span data-ttu-id="9cc3c-132">指定此 cmdlet 取消事件订阅的源标识符。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="9cc3c-133">必须在每个命令中都包含 SourceIdentifier 或 SubscriptionId 参数。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-133">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9cc3c-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="9cc3c-134">-SubscriptionId</span></span>

<span data-ttu-id="9cc3c-135">指定此 cmdlet 取消事件订阅的源标识符 ID。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="9cc3c-136">必须在每个命令中都包含 SourceIdentifier 或 SubscriptionId 参数。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-136">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9cc3c-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9cc3c-137">-Confirm</span></span>

<span data-ttu-id="9cc3c-138">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9cc3c-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9cc3c-139">-WhatIf</span></span>

<span data-ttu-id="9cc3c-140">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-140">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9cc3c-141">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9cc3c-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9cc3c-142">CommonParameters</span></span>

<span data-ttu-id="9cc3c-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9cc3c-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9cc3c-145">输入</span><span class="sxs-lookup"><span data-stu-id="9cc3c-145">INPUTS</span></span>

### <span data-ttu-id="9cc3c-146">System.Management.Automation.PSEventSubscriber</span><span class="sxs-lookup"><span data-stu-id="9cc3c-146">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="9cc3c-147">你可以通过管道将输出传递 `Get-EventSubscriber` 给 `Unregister-Event` 。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-147">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="9cc3c-148">输出</span><span class="sxs-lookup"><span data-stu-id="9cc3c-148">OUTPUTS</span></span>

### <span data-ttu-id="9cc3c-149">None</span><span class="sxs-lookup"><span data-stu-id="9cc3c-149">None</span></span>

<span data-ttu-id="9cc3c-150">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="9cc3c-151">注释</span><span class="sxs-lookup"><span data-stu-id="9cc3c-151">NOTES</span></span>

<span data-ttu-id="9cc3c-152">Linux 或 macOS 平台上没有可用的事件源。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-152">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="9cc3c-153">事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-153">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="9cc3c-154">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-154">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="9cc3c-155">`Unregister-Event` 不能删除使用 cmdlet 创建的事件 `New-Event` ，除非你已使用 cmdlet 订阅了该事件 `Register-EngineEvent` 。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-155">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="9cc3c-156">若要从会话中删除自定义事件，必须以编程方式删除事件或关闭会话。</span><span class="sxs-lookup"><span data-stu-id="9cc3c-156">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="9cc3c-157">相关链接</span><span class="sxs-lookup"><span data-stu-id="9cc3c-157">RELATED LINKS</span></span>

[<span data-ttu-id="9cc3c-158">Get-Event</span><span class="sxs-lookup"><span data-stu-id="9cc3c-158">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="9cc3c-159">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="9cc3c-159">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="9cc3c-160">New-Event</span><span class="sxs-lookup"><span data-stu-id="9cc3c-160">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="9cc3c-161">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="9cc3c-161">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="9cc3c-162">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="9cc3c-162">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="9cc3c-163">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="9cc3c-163">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="9cc3c-164">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="9cc3c-164">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="9cc3c-165">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="9cc3c-165">Wait-Event</span></span>](Wait-Event.md)
