---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 748ef22203f59090be6f5491ea76b50d54930a95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198821"
---
# <span data-ttu-id="4f027-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4f027-103">Unregister-Event</span></span>

## <span data-ttu-id="4f027-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4f027-104">SYNOPSIS</span></span>
<span data-ttu-id="4f027-105">取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="4f027-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f027-106">SYNTAX</span></span>

### <span data-ttu-id="4f027-107">BySource（默认值）</span><span class="sxs-lookup"><span data-stu-id="4f027-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4f027-108">ById</span><span class="sxs-lookup"><span data-stu-id="4f027-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4f027-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4f027-109">DESCRIPTION</span></span>
<span data-ttu-id="4f027-110">**Unregister-Event** cmdlet 可取消使用 Register-EngineEventt、Register-ObjectEvent 或 Register-WmiEvent cmdlet 创建的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-110">The **Unregister-Event** cmdlet cancels an event subscription that was created by using the Register-EngineEvent, Register-ObjectEvent, or Register-WmiEvent cmdlet.</span></span>

<span data-ttu-id="4f027-111">取消事件订阅后，将从会话中删除事件订阅服务器，并且不再将订阅的事件添加到事件队列中。</span><span class="sxs-lookup"><span data-stu-id="4f027-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span>
<span data-ttu-id="4f027-112">取消使用 New-Event cmdlet 创建的事件订阅后，还将从会话中删除新的事件。</span><span class="sxs-lookup"><span data-stu-id="4f027-112">When you cancel a subscription to an event created by using the New-Event cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="4f027-113">**Unregister-Event** 不会从事件队列中删除事件。</span><span class="sxs-lookup"><span data-stu-id="4f027-113">**Unregister-Event** does not delete events from the event queue.</span></span>
<span data-ttu-id="4f027-114">若要删除事件，请使用 Remove-Event cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f027-114">To delete events, use the Remove-Event cmdlet.</span></span>

## <span data-ttu-id="4f027-115">示例</span><span class="sxs-lookup"><span data-stu-id="4f027-115">EXAMPLES</span></span>

### <span data-ttu-id="4f027-116">示例 1：按源标识符取消事件订阅</span><span class="sxs-lookup"><span data-stu-id="4f027-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="4f027-117">此命令将取消源标识符为 ProcessStarted 的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="4f027-118">若要查找事件的源标识符，请使用 Get-Event cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f027-118">To find the source identifier of an event, use the Get-Event cmdlet.</span></span>
<span data-ttu-id="4f027-119">若要查找事件订阅的源标识符，请使用 **Get-EventSubscriber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f027-119">To find the source identifier of an event subscription, use the **Get-EventSubscriber** cmdlet.</span></span>

### <span data-ttu-id="4f027-120">示例 2：按订阅标识符取消事件订阅</span><span class="sxs-lookup"><span data-stu-id="4f027-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="4f027-121">此命令将取消订阅标识符为 2 的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="4f027-122">若要查找事件订阅的订阅标识符，请使用 **Get-EventSubscriber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f027-122">To find the subscription identifier of an event subscription, use the **Get-EventSubscriber** cmdlet.</span></span>

### <span data-ttu-id="4f027-123">示例 3：取消所有事件订阅</span><span class="sxs-lookup"><span data-stu-id="4f027-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="4f027-124">此命令将取消会话中的所有事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="4f027-125">该命令使用  参数隐藏的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="4f027-125">The command uses the **Get-EventSubscriber** cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the *SupportEvent* parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="4f027-126">它使用管道运算符 (|) 将订阅服务器对象发送到 **Unregister-Event** ，后者将它们从会话中删除。</span><span class="sxs-lookup"><span data-stu-id="4f027-126">It uses a pipeline operator (|) to send the subscriber objects to **Unregister-Event** , which deletes them from the session.</span></span>
<span data-ttu-id="4f027-127">若要完成该任务，还需要在  参数。</span><span class="sxs-lookup"><span data-stu-id="4f027-127">To complete the task, the *Force* parameter is also required on **Unregister-Event** .</span></span>

## <span data-ttu-id="4f027-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f027-128">PARAMETERS</span></span>

### <span data-ttu-id="4f027-129">-Force</span><span class="sxs-lookup"><span data-stu-id="4f027-129">-Force</span></span>
<span data-ttu-id="4f027-130">取消所有事件订阅，包括通过使用  参数隐藏的订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-130">Cancels all event subscriptions, including subscriptions that were hidden by using the *SupportEvent* parameter of **Register-ObjectEvent** , **Register-WmiEvent** , and **Register-EngineEvent** .</span></span>

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

### <span data-ttu-id="4f027-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4f027-131">-SourceIdentifier</span></span>
<span data-ttu-id="4f027-132">指定此 cmdlet 取消事件订阅的源标识符。</span><span class="sxs-lookup"><span data-stu-id="4f027-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="4f027-133">必须在每个命令中都包含 SourceIdentifier  或 SubscriptionId  参数。</span><span class="sxs-lookup"><span data-stu-id="4f027-133">A *SourceIdentifier* or *SubscriptionId* parameter must be included in every command.</span></span>

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

### <span data-ttu-id="4f027-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="4f027-134">-SubscriptionId</span></span>
<span data-ttu-id="4f027-135">指定此 cmdlet 取消事件订阅的源标识符 ID。</span><span class="sxs-lookup"><span data-stu-id="4f027-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="4f027-136">必须在每个命令中都包含 SourceIdentifier  或 SubscriptionId  参数。</span><span class="sxs-lookup"><span data-stu-id="4f027-136">A *SourceIdentifier* or *SubscriptionId* parameter must be included in every command.</span></span>

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

### <span data-ttu-id="4f027-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4f027-137">-Confirm</span></span>
<span data-ttu-id="4f027-138">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="4f027-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4f027-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4f027-139">-WhatIf</span></span>
<span data-ttu-id="4f027-140">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="4f027-140">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4f027-141">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="4f027-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4f027-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4f027-142">CommonParameters</span></span>
<span data-ttu-id="4f027-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4f027-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f027-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4f027-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4f027-145">输入</span><span class="sxs-lookup"><span data-stu-id="4f027-145">INPUTS</span></span>

### <span data-ttu-id="4f027-146">System.Management.Automation.PSEventSubscriber</span><span class="sxs-lookup"><span data-stu-id="4f027-146">System.Management.Automation.PSEventSubscriber</span></span>
<span data-ttu-id="4f027-147">可以通过管道将输出从 Get-EventSubscriber 传递给 **Unregister-Event** 。</span><span class="sxs-lookup"><span data-stu-id="4f027-147">You can pipe the output from Get-EventSubscriber to **Unregister-Event** .</span></span>

## <span data-ttu-id="4f027-148">输出</span><span class="sxs-lookup"><span data-stu-id="4f027-148">OUTPUTS</span></span>

### <span data-ttu-id="4f027-149">无</span><span class="sxs-lookup"><span data-stu-id="4f027-149">None</span></span>
<span data-ttu-id="4f027-150">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="4f027-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4f027-151">注释</span><span class="sxs-lookup"><span data-stu-id="4f027-151">NOTES</span></span>

* <span data-ttu-id="4f027-152">事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="4f027-152">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4f027-153">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4f027-153">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="4f027-154">**取消注册-事件** 无法删除使用 New-Event cmdlet 创建的事件，除非你已使用 **register-engineevent** cmdlet 订阅了该事件。</span><span class="sxs-lookup"><span data-stu-id="4f027-154">**Unregister-Event** cannot delete events created by using the New-Event cmdlet unless you have subscribed to the event by using the **Register-EngineEvent** cmdlet.</span></span>
<span data-ttu-id="4f027-155">若要从会话中删除自定义事件，必须以编程方式删除事件或关闭会话。</span><span class="sxs-lookup"><span data-stu-id="4f027-155">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

*

## <span data-ttu-id="4f027-156">相关链接</span><span class="sxs-lookup"><span data-stu-id="4f027-156">RELATED LINKS</span></span>

[<span data-ttu-id="4f027-157">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4f027-157">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="4f027-158">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="4f027-158">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="4f027-159">New-Event</span><span class="sxs-lookup"><span data-stu-id="4f027-159">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="4f027-160">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4f027-160">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4f027-161">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4f027-161">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4f027-162">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4f027-162">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4f027-163">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4f027-163">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4f027-164">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4f027-164">Wait-Event</span></span>](Wait-Event.md)

