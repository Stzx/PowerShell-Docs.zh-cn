---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 9ab8ff192b150811b3cef7035c60f509e1fb5570
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197885"
---
# <span data-ttu-id="061a0-103">New-Event</span><span class="sxs-lookup"><span data-stu-id="061a0-103">New-Event</span></span>

## <span data-ttu-id="061a0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="061a0-104">SYNOPSIS</span></span>
<span data-ttu-id="061a0-105">创建新事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-105">Creates a new event.</span></span>

## <span data-ttu-id="061a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="061a0-106">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="061a0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="061a0-107">DESCRIPTION</span></span>
<span data-ttu-id="061a0-108">**New-Event** cmdlet 创建新的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-108">The **New-Event** cmdlet creates a new custom event.</span></span>

<span data-ttu-id="061a0-109">你可以使用自定义事件通知用户你程序中的状态更改以及你的程序可以检测到的任何更改，包括硬件或系统状况、应用程序状态、磁盘状态、网络状态或后台作业的完成。</span><span class="sxs-lookup"><span data-stu-id="061a0-109">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="061a0-110">每次引发自定义事件时，它们都会自动添加到会话中的事件队列；你无需订阅这些事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-110">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span>
<span data-ttu-id="061a0-111">但是，如果你希望将事件转发到本地会话或指定一个操作来响应该事件，请使用 Register-EngineEvent cmdlet 来订阅自定义事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-111">However, if you want to forward an event to the local session or specify an action to respond to the event, use the Register-EngineEvent cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="061a0-112">订阅自定义事件时，会向会话中添加事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="061a0-112">When you subscribe to a custom event, the event subscriber is added to your session.</span></span>
<span data-ttu-id="061a0-113">如果通过使用 Unregister-Event cmdlet 取消事件订阅，将从会话中删除事件订阅服务器和自定义事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-113">If you cancel the event subscription by using the Unregister-Event cmdlet, the event subscriber and custom event are deleted from the session.</span></span>
<span data-ttu-id="061a0-114">如果不订阅自定义事件，若要删除事件，必须更改程序状况或关闭 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="061a0-114">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the Windows PowerShell session.</span></span>

## <span data-ttu-id="061a0-115">示例</span><span class="sxs-lookup"><span data-stu-id="061a0-115">EXAMPLES</span></span>

### <span data-ttu-id="061a0-116">示例1：在事件队列中创建新事件</span><span class="sxs-lookup"><span data-stu-id="061a0-116">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="061a0-117">此命令在 Windows PowerShell 事件队列中创建一个新事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-117">This command creates a new event in the Windows PowerShell event queue.</span></span>
<span data-ttu-id="061a0-118">它使用 **Windows Timer** 对象发送事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-118">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="061a0-119">示例2：引发事件以响应另一个事件</span><span class="sxs-lookup"><span data-stu-id="061a0-119">Example 2: Raise an event in response to another event</span></span>

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

<span data-ttu-id="061a0-120">此示例函数使用 **新的-event** cmdlet 引发事件以响应另一个事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-120">This sample function uses the **New-Event** cmdlet to raise an event in response to another event.</span></span>
<span data-ttu-id="061a0-121">该命令使用 Register-ObjectEvent cmdlet 来订阅创建新进程时引发的 Windows Management Instrumentation (WMI) 事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-121">The command uses the Register-ObjectEvent cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span>
<span data-ttu-id="061a0-122">该命令使用 cmdlet 的 *Action* 参数来调用将创建新事件的 **新事件** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="061a0-122">The command uses the *Action* parameter of the cmdlet to call the **New-Event** cmdlet, which creates the new event.</span></span>

<span data-ttu-id="061a0-123">由于 **新事件** 引发的事件将自动添加到 Windows PowerShellevent 队列，因此你不需要注册该事件。</span><span class="sxs-lookup"><span data-stu-id="061a0-123">Because the events that **New-Event** raises are automatically added to the Windows PowerShellevent queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="061a0-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="061a0-124">PARAMETERS</span></span>

### <span data-ttu-id="061a0-125">-EventArguments</span><span class="sxs-lookup"><span data-stu-id="061a0-125">-EventArguments</span></span>
<span data-ttu-id="061a0-126">指定包含事件选项的对象。</span><span class="sxs-lookup"><span data-stu-id="061a0-126">Specifies an object that contains options for the event.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="061a0-127">-MessageData</span><span class="sxs-lookup"><span data-stu-id="061a0-127">-MessageData</span></span>
<span data-ttu-id="061a0-128">指定与事件关联的其他数据。</span><span class="sxs-lookup"><span data-stu-id="061a0-128">Specifies additional data associated with the event.</span></span>
<span data-ttu-id="061a0-129">此参数的值显示在事件对象的 **MessageData** 属性中。</span><span class="sxs-lookup"><span data-stu-id="061a0-129">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="061a0-130">-发送方</span><span class="sxs-lookup"><span data-stu-id="061a0-130">-Sender</span></span>
<span data-ttu-id="061a0-131">指定引发事件的对象。</span><span class="sxs-lookup"><span data-stu-id="061a0-131">Specifies the object that raises the event.</span></span>
<span data-ttu-id="061a0-132">默认值为 Windows PowerShell 引擎。</span><span class="sxs-lookup"><span data-stu-id="061a0-132">The default is the Windows PowerShell engine.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="061a0-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="061a0-133">-SourceIdentifier</span></span>
<span data-ttu-id="061a0-134">指定新事件的名称。</span><span class="sxs-lookup"><span data-stu-id="061a0-134">Specifies a name for the new event.</span></span>
<span data-ttu-id="061a0-135">此参数是必需的，并且在会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="061a0-135">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="061a0-136">此参数的值显示在事件的 **SourceIdentifier** 属性中。</span><span class="sxs-lookup"><span data-stu-id="061a0-136">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="061a0-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="061a0-137">CommonParameters</span></span>
<span data-ttu-id="061a0-138">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="061a0-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="061a0-139">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="061a0-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="061a0-140">输入</span><span class="sxs-lookup"><span data-stu-id="061a0-140">INPUTS</span></span>

### <span data-ttu-id="061a0-141">无</span><span class="sxs-lookup"><span data-stu-id="061a0-141">None</span></span>
<span data-ttu-id="061a0-142">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="061a0-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="061a0-143">输出</span><span class="sxs-lookup"><span data-stu-id="061a0-143">OUTPUTS</span></span>

### <span data-ttu-id="061a0-144">System.Management.Automation.PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="061a0-144">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="061a0-145">注释</span><span class="sxs-lookup"><span data-stu-id="061a0-145">NOTES</span></span>

<span data-ttu-id="061a0-146">新自定义事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="061a0-146">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span> <span data-ttu-id="061a0-147">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="061a0-147">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="061a0-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="061a0-148">RELATED LINKS</span></span>

[<span data-ttu-id="061a0-149">Get-Event</span><span class="sxs-lookup"><span data-stu-id="061a0-149">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="061a0-150">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="061a0-150">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="061a0-151">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="061a0-151">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="061a0-152">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="061a0-152">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="061a0-153">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="061a0-153">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="061a0-154">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="061a0-154">Wait-Event</span></span>](Wait-Event.md)
