---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 81244e9c32ca1f1d4824bdb8559607b44222c7bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197704"
---
# <span data-ttu-id="d71e6-103">Get-Event</span><span class="sxs-lookup"><span data-stu-id="d71e6-103">Get-Event</span></span>

## <span data-ttu-id="d71e6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d71e6-104">SYNOPSIS</span></span>
<span data-ttu-id="d71e6-105">获取事件队列中的事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-105">Gets the events in the event queue.</span></span>

## <span data-ttu-id="d71e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d71e6-106">SYNTAX</span></span>

### <span data-ttu-id="d71e6-107">BySource（默认值）</span><span class="sxs-lookup"><span data-stu-id="d71e6-107">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="d71e6-108">ById</span><span class="sxs-lookup"><span data-stu-id="d71e6-108">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="d71e6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d71e6-109">DESCRIPTION</span></span>

<span data-ttu-id="d71e6-110">**获取事件** cmdlet 获取当前会话的 PowerShell 事件队列中的事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-110">The **Get-Event** cmdlet gets events in the PowerShell event queue for the current session.</span></span>
<span data-ttu-id="d71e6-111">可以获取所有事件，也可以使用 EventIdentifier  或 SourceIdentifier  参数指定事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-111">You can get all events or use the *EventIdentifier* or *SourceIdentifier* parameter to specify the events.</span></span>

<span data-ttu-id="d71e6-112">当发生某个事件时，会将其添加到事件队列中。</span><span class="sxs-lookup"><span data-stu-id="d71e6-112">When an event occurs, it is added to the event queue.</span></span>
<span data-ttu-id="d71e6-113">事件队列包括已注册的事件、使用 New-Event cmdlet 创建的事件，以及 PowerShell 退出时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-113">The event queue includes events for which you have registered, events created by using the New-Event cmdlet, and the event that is raised when PowerShell exits.</span></span>
<span data-ttu-id="d71e6-114">可以使用 **Get 事件** 或 Wait-Event 获取这些事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-114">You can use **Get-Event** or Wait-Event to get the events.</span></span>

<span data-ttu-id="d71e6-115">此 cmdlet 不会从“事件查看器”日志获取事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-115">This cmdlet does not get events from the Event Viewer logs.</span></span>
<span data-ttu-id="d71e6-116">若要获取这些事件，请使用 Get-WinEvent 或 Get-EventLog。</span><span class="sxs-lookup"><span data-stu-id="d71e6-116">To get those events, use Get-WinEvent or Get-EventLog.</span></span>

## <span data-ttu-id="d71e6-117">示例</span><span class="sxs-lookup"><span data-stu-id="d71e6-117">EXAMPLES</span></span>

### <span data-ttu-id="d71e6-118">示例 1：获取所有事件</span><span class="sxs-lookup"><span data-stu-id="d71e6-118">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="d71e6-119">此命令将获取事件队列中的所有事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-119">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="d71e6-120">示例 2：按源标识符获取事件</span><span class="sxs-lookup"><span data-stu-id="d71e6-120">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="d71e6-121">此命令将获取 SourceIdentifier 属性的值为 PowerShell.ProcessCreated 的事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-121">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="d71e6-122">示例 3：基于事件的生成时间获取事件</span><span class="sxs-lookup"><span data-stu-id="d71e6-122">Example 3: Get an event based on the time it was generated</span></span>

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

<span data-ttu-id="d71e6-123">此示例显示了如何通过使用属性（而不是 SourceIdentifier）来获取事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-123">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="d71e6-124">第一个命令将获取事件队列中的所有事件，并将其保存在 $Events 变量中。</span><span class="sxs-lookup"><span data-stu-id="d71e6-124">The first command gets all events in the event queue and saves them in the $Events variable.</span></span>

<span data-ttu-id="d71e6-125">第二个命令使用数组表示法来获取 $Events 变量的数组中的第一个（索引为 0）事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-125">The second command uses array notation to get the first (0-index) event in the array in the $Events variable.</span></span>
<span data-ttu-id="d71e6-126">该命令使用管道运算符 (|) 将事件发送到 Format-List 命令，后者将在列表中显示该事件的所有属性。</span><span class="sxs-lookup"><span data-stu-id="d71e6-126">The command uses a pipeline operator (|) to send the event to the Format-List command, which displays all properties of the event in a list.</span></span>
<span data-ttu-id="d71e6-127">这使你可以检查事件对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d71e6-127">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="d71e6-128">第三个命令显示了如何使用 Where-Object cmdlet 来基于事件的生成时间获取事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-128">The third command shows how to use the Where-Object cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="d71e6-129">示例 4：按标识符获取事件</span><span class="sxs-lookup"><span data-stu-id="d71e6-129">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="d71e6-130">此命令将获取事件标识符为 2 的事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-130">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="d71e6-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d71e6-131">PARAMETERS</span></span>

### <span data-ttu-id="d71e6-132">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="d71e6-132">-EventIdentifier</span></span>

<span data-ttu-id="d71e6-133">指定此 cmdlet 可为其获取事件的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="d71e6-133">Specifies the event identifiers for which this cmdlet gets events.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d71e6-134">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="d71e6-134">-SourceIdentifier</span></span>

<span data-ttu-id="d71e6-135">指定此 cmdlet 可为其获取事件的源标识符。</span><span class="sxs-lookup"><span data-stu-id="d71e6-135">Specifies source identifiers for which this cmdlet gets events.</span></span>
<span data-ttu-id="d71e6-136">默认值为事件队列中的所有事件。</span><span class="sxs-lookup"><span data-stu-id="d71e6-136">The default is all events in the event queue.</span></span>
<span data-ttu-id="d71e6-137">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="d71e6-137">Wildcards are not permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d71e6-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d71e6-138">CommonParameters</span></span>

<span data-ttu-id="d71e6-139">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d71e6-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d71e6-140">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d71e6-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d71e6-141">输入</span><span class="sxs-lookup"><span data-stu-id="d71e6-141">INPUTS</span></span>

### <span data-ttu-id="d71e6-142">无</span><span class="sxs-lookup"><span data-stu-id="d71e6-142">None</span></span>

<span data-ttu-id="d71e6-143">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d71e6-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d71e6-144">输出</span><span class="sxs-lookup"><span data-stu-id="d71e6-144">OUTPUTS</span></span>

### <span data-ttu-id="d71e6-145">System.Management.Automation.PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="d71e6-145">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="d71e6-146">**获取-事件** 返回每个事件的 **PSEventArgs** 对象。</span><span class="sxs-lookup"><span data-stu-id="d71e6-146">**Get-Event** returns a **PSEventArgs** object for each event.</span></span>
<span data-ttu-id="d71e6-147">若要查看此对象的说明，请键入 `Get-Help Get-Event -Full`，并查看帮助主题的“注释”部分。</span><span class="sxs-lookup"><span data-stu-id="d71e6-147">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="d71e6-148">注释</span><span class="sxs-lookup"><span data-stu-id="d71e6-148">NOTES</span></span>

* <span data-ttu-id="d71e6-149">事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="d71e6-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="d71e6-150">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="d71e6-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="d71e6-151">PSEventArgs **cmdlet 将** 返回具有以下属性的 **PSEventArgs** 对象 ( **PSEventArgs** ) ：</span><span class="sxs-lookup"><span data-stu-id="d71e6-151">The **Get-Event** cmdlet returns a **PSEventArgs** object ( **System.Management.Automation.PSEventArgs** ) with the following properties:</span></span>

  - <span data-ttu-id="d71e6-152">ComputerName。</span><span class="sxs-lookup"><span data-stu-id="d71e6-152">ComputerName.</span></span>
<span data-ttu-id="d71e6-153">发生该事件的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="d71e6-153">The name of the computer on which the event occurred.</span></span>
<span data-ttu-id="d71e6-154">仅当从远程计算机转发事件时，才填充此属性值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="d71e6-155">RunspaceId。</span><span class="sxs-lookup"><span data-stu-id="d71e6-155">RunspaceId.</span></span>
<span data-ttu-id="d71e6-156">一个 GUID，用于唯一标识该事件发生时所在的会话。</span><span class="sxs-lookup"><span data-stu-id="d71e6-156">A GUID that uniquely identifies the session in which the event occurred.</span></span>
<span data-ttu-id="d71e6-157">仅当从远程计算机转发事件时，才填充此属性值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="d71e6-158">EventIdentifier。</span><span class="sxs-lookup"><span data-stu-id="d71e6-158">EventIdentifier.</span></span>
<span data-ttu-id="d71e6-159">一个整数 (Int32)，用于唯一标识当前会话中的事件通知。</span><span class="sxs-lookup"><span data-stu-id="d71e6-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

  - <span data-ttu-id="d71e6-160">Sender。</span><span class="sxs-lookup"><span data-stu-id="d71e6-160">Sender.</span></span>
<span data-ttu-id="d71e6-161">生成该事件的对象。</span><span class="sxs-lookup"><span data-stu-id="d71e6-161">The object that generated the event.</span></span>
<span data-ttu-id="d71e6-162">在 *Action* 参数的值中，$Sender 自动变量包含发件人对象。</span><span class="sxs-lookup"><span data-stu-id="d71e6-162">In the value of the *Action* parameter, the $Sender automatic variable contains the sender object.</span></span>

  - <span data-ttu-id="d71e6-163">SourceEventArgs。</span><span class="sxs-lookup"><span data-stu-id="d71e6-163">SourceEventArgs.</span></span>
<span data-ttu-id="d71e6-164">派生自 EventArgs 的第一个参数（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="d71e6-164">The first parameter that derives from EventArgs, if it exists.</span></span>
<span data-ttu-id="d71e6-165">例如，在签名形式为 Object sender, Timers.ElapsedEventArgs e 的 Timer Elapsed 事件中，SourceEventArgs 属性会包含 Timers.ElapsedEventArgs。</span><span class="sxs-lookup"><span data-stu-id="d71e6-165">For example, in a timer elapsed event in which the signature has the form Object sender, Timers.ElapsedEventArgs e, the SourceEventArgs property would contain the Timers.ElapsedEventArgs.</span></span>
<span data-ttu-id="d71e6-166">在 *Action* 参数的值中，$EventArgs 自动变量包含此值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-166">In the value of the *Action* parameter, the $EventArgs automatic variable contains this value.</span></span>

  - <span data-ttu-id="d71e6-167">SourceArgs。</span><span class="sxs-lookup"><span data-stu-id="d71e6-167">SourceArgs.</span></span>
<span data-ttu-id="d71e6-168">原始事件签名的所有参数。</span><span class="sxs-lookup"><span data-stu-id="d71e6-168">All parameters of the original event signature.</span></span>
<span data-ttu-id="d71e6-169">对于标准事件签名，$Args\[0\] 表示发件人，$Args\[1\] 表示 SourceEventArgs。</span><span class="sxs-lookup"><span data-stu-id="d71e6-169">For a standard event signature, $Args\[0\] represents the sender, and $Args\[1\] represents the SourceEventArgs.</span></span>
<span data-ttu-id="d71e6-170">在 *Action* 参数的值中，$Args 自动变量包含此值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-170">In the value of the *Action* parameter, the $Args automatic variable contains this value.</span></span>

  - <span data-ttu-id="d71e6-171">SourceIdentifier。</span><span class="sxs-lookup"><span data-stu-id="d71e6-171">SourceIdentifier.</span></span>
<span data-ttu-id="d71e6-172">用于标识事件订阅的字符串。</span><span class="sxs-lookup"><span data-stu-id="d71e6-172">A string that identifies the event subscription.</span></span>
<span data-ttu-id="d71e6-173">在 *Action* 参数的值中，$Event 自动变量的 SourceIdentifier 属性包含此值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-173">In the value of the *Action* parameter, the SourceIdentifier property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="d71e6-174">TimeGenerated。</span><span class="sxs-lookup"><span data-stu-id="d71e6-174">TimeGenerated.</span></span>
<span data-ttu-id="d71e6-175">一个 **DateTime** 对象，用于表示事件的生成时间。</span><span class="sxs-lookup"><span data-stu-id="d71e6-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
<span data-ttu-id="d71e6-176">在 *Action* 参数的值中，$Event 自动变量的 TimeGenerated 属性包含此值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-176">In the value of the *Action* parameter, the TimeGenerated property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="d71e6-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="d71e6-177">MessageData.</span></span>
<span data-ttu-id="d71e6-178">与事件订阅关联的数据。</span><span class="sxs-lookup"><span data-stu-id="d71e6-178">Data associated with the event subscription.</span></span>
<span data-ttu-id="d71e6-179">当用户注册事件时，将指定此数据。</span><span class="sxs-lookup"><span data-stu-id="d71e6-179">Users specify this data when they register an event.</span></span>
<span data-ttu-id="d71e6-180">在 *Action* 参数的值中，$Event 自动变量的 MessageData 属性包含此值。</span><span class="sxs-lookup"><span data-stu-id="d71e6-180">In the value of the *Action* parameter, the MessageData property of the $Event automatic variable contains this value.</span></span>

## <span data-ttu-id="d71e6-181">相关链接</span><span class="sxs-lookup"><span data-stu-id="d71e6-181">RELATED LINKS</span></span>

[<span data-ttu-id="d71e6-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="d71e6-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="d71e6-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="d71e6-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="d71e6-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="d71e6-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="d71e6-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="d71e6-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="d71e6-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="d71e6-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="d71e6-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="d71e6-187">Wait-Event</span></span>](Wait-Event.md)

