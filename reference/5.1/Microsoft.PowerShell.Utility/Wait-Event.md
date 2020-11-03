---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: 55fa54521a6c2e9d37b333a27af4572c6a34913a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197834"
---
# <span data-ttu-id="2f62e-103">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="2f62e-103">Wait-Event</span></span>

## <span data-ttu-id="2f62e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2f62e-104">SYNOPSIS</span></span>
<span data-ttu-id="2f62e-105">等待，直到在继续运行之前引发特定事件。</span><span class="sxs-lookup"><span data-stu-id="2f62e-105">Waits until a particular event is raised before continuing to run.</span></span>

## <span data-ttu-id="2f62e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f62e-106">SYNTAX</span></span>

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="2f62e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f62e-107">DESCRIPTION</span></span>

<span data-ttu-id="2f62e-108">`Wait-Event`Cmdlet 将挂起脚本或函数的执行，直到引发特定事件。</span><span class="sxs-lookup"><span data-stu-id="2f62e-108">The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised.</span></span> <span data-ttu-id="2f62e-109">在检测到事件后会继续执行。</span><span class="sxs-lookup"><span data-stu-id="2f62e-109">Execution resumes when the event is detected.</span></span> <span data-ttu-id="2f62e-110">若要取消等待，请按<kbd>CTRL</kbd> + <kbd>C</kbd>。</span><span class="sxs-lookup"><span data-stu-id="2f62e-110">To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="2f62e-111">此功能为事件的轮询提供了一种替代方法。</span><span class="sxs-lookup"><span data-stu-id="2f62e-111">This feature provides an alternative to polling for an event.</span></span> <span data-ttu-id="2f62e-112">它还允许你通过两种不同的方式确定对事件的响应：</span><span class="sxs-lookup"><span data-stu-id="2f62e-112">It also allows you to determine the response to an event in two different ways:</span></span>

- <span data-ttu-id="2f62e-113">使用事件订阅的 **Action** 参数</span><span class="sxs-lookup"><span data-stu-id="2f62e-113">using the **Action** parameter of the event subscription</span></span>
- <span data-ttu-id="2f62e-114">等待事件返回，然后使用操作进行响应</span><span class="sxs-lookup"><span data-stu-id="2f62e-114">waiting for an event to return and then respond with an action</span></span>

## <span data-ttu-id="2f62e-115">示例</span><span class="sxs-lookup"><span data-stu-id="2f62e-115">EXAMPLES</span></span>

### <span data-ttu-id="2f62e-116">示例1：等待下一个事件</span><span class="sxs-lookup"><span data-stu-id="2f62e-116">Example 1: Wait for the next event</span></span>

<span data-ttu-id="2f62e-117">此示例将等待引发的下一个事件。</span><span class="sxs-lookup"><span data-stu-id="2f62e-117">This example waits for the next event that is raised.</span></span>

```powershell
Wait-Event
```

### <span data-ttu-id="2f62e-118">示例2：等待具有指定源标识符的事件</span><span class="sxs-lookup"><span data-stu-id="2f62e-118">Example 2: Wait for an event with a specified source identifier</span></span>

<span data-ttu-id="2f62e-119">此示例将等待引发并且源标识符为 ProcessStarted 的下一个事件。</span><span class="sxs-lookup"><span data-stu-id="2f62e-119">This example waits for the next event that is raised and that has a source identifier of ProcessStarted.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="2f62e-120">示例3：等待计时器已用事件</span><span class="sxs-lookup"><span data-stu-id="2f62e-120">Example 3: Wait for a timer elapsed event</span></span>

<span data-ttu-id="2f62e-121">此示例使用 `Wait-Event` cmdlet 等待为2000毫秒设置的计时器的计时器事件。</span><span class="sxs-lookup"><span data-stu-id="2f62e-121">This example uses the `Wait-Event` cmdlet to wait for a timer event on a timer that is set for 2000 milliseconds.</span></span>

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### <span data-ttu-id="2f62e-122">示例4：在指定的超时后等待事件</span><span class="sxs-lookup"><span data-stu-id="2f62e-122">Example 4: Wait for an event after a specified timeout</span></span>

<span data-ttu-id="2f62e-123">此示例为引发并且源标识符为 **ProcessStarted** 的下一个事件等待最长90秒。</span><span class="sxs-lookup"><span data-stu-id="2f62e-123">This example waits up to 90 seconds for the next event that is raised and that has a source identifier of **ProcessStarted** .</span></span> <span data-ttu-id="2f62e-124">如果达到该指定时间，则等待结束。</span><span class="sxs-lookup"><span data-stu-id="2f62e-124">If the specified time expires, the wait ends.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## <span data-ttu-id="2f62e-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2f62e-125">PARAMETERS</span></span>

### <span data-ttu-id="2f62e-126">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="2f62e-126">-SourceIdentifier</span></span>

<span data-ttu-id="2f62e-127">指定此 cmdlet 等待事件的源标识符。</span><span class="sxs-lookup"><span data-stu-id="2f62e-127">Specifies the source identifier that this cmdlet waits for events.</span></span>
<span data-ttu-id="2f62e-128">默认情况下， `Wait-Event` 等待任何事件。</span><span class="sxs-lookup"><span data-stu-id="2f62e-128">By default, `Wait-Event` waits for any event.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2f62e-129">-Timeout</span><span class="sxs-lookup"><span data-stu-id="2f62e-129">-Timeout</span></span>

<span data-ttu-id="2f62e-130">指定等待事件发生的最长时间（以秒为单位） `Wait-Event` 。</span><span class="sxs-lookup"><span data-stu-id="2f62e-130">Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur.</span></span> <span data-ttu-id="2f62e-131">默认值为 -1，表示无限期地等待。</span><span class="sxs-lookup"><span data-stu-id="2f62e-131">The default, -1, waits indefinitely.</span></span> <span data-ttu-id="2f62e-132">提交命令时，将开始计时 `Wait-Event` 。</span><span class="sxs-lookup"><span data-stu-id="2f62e-132">The timing starts when you submit the `Wait-Event` command.</span></span>

<span data-ttu-id="2f62e-133">如果超过指定时间，则等待结束，并返回命令提示符，即使尚未引发事件也是如此。</span><span class="sxs-lookup"><span data-stu-id="2f62e-133">If the specified time is exceeded, the wait ends and the command prompt returns, even if the event has not been raised.</span></span> <span data-ttu-id="2f62e-134">不显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="2f62e-134">No error message is displayed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f62e-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2f62e-135">CommonParameters</span></span>

<span data-ttu-id="2f62e-136">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2f62e-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f62e-137">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2f62e-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f62e-138">输入</span><span class="sxs-lookup"><span data-stu-id="2f62e-138">INPUTS</span></span>

### <span data-ttu-id="2f62e-139">System.String</span><span class="sxs-lookup"><span data-stu-id="2f62e-139">System.String</span></span>

## <span data-ttu-id="2f62e-140">输出</span><span class="sxs-lookup"><span data-stu-id="2f62e-140">OUTPUTS</span></span>

### <span data-ttu-id="2f62e-141">System.Management.Automation.PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="2f62e-141">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="2f62e-142">注释</span><span class="sxs-lookup"><span data-stu-id="2f62e-142">NOTES</span></span>

<span data-ttu-id="2f62e-143">事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="2f62e-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="2f62e-144">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="2f62e-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="2f62e-145">相关链接</span><span class="sxs-lookup"><span data-stu-id="2f62e-145">RELATED LINKS</span></span>

[<span data-ttu-id="2f62e-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="2f62e-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="2f62e-147">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="2f62e-147">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="2f62e-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="2f62e-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="2f62e-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="2f62e-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="2f62e-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="2f62e-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="2f62e-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="2f62e-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="2f62e-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="2f62e-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="2f62e-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="2f62e-153">Wait-Event</span></span>](Wait-Event.md)
