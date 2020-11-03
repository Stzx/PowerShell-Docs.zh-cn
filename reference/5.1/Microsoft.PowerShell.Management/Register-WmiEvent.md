---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "93199192"
---
# <span data-ttu-id="7a686-103">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="7a686-103">Register-WmiEvent</span></span>

## <span data-ttu-id="7a686-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7a686-104">SYNOPSIS</span></span>
<span data-ttu-id="7a686-105">订阅 Windows Management Instrumentation (WMI) 事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-105">Subscribes to a Windows Management Instrumentation (WMI) event.</span></span>

## <span data-ttu-id="7a686-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7a686-106">SYNTAX</span></span>

### <span data-ttu-id="7a686-107">class（默认值）</span><span class="sxs-lookup"><span data-stu-id="7a686-107">class (Default)</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="7a686-108">query</span><span class="sxs-lookup"><span data-stu-id="7a686-108">query</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="7a686-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7a686-109">DESCRIPTION</span></span>

<span data-ttu-id="7a686-110">`Register-WmiEvent`Cmdlet 订阅本地计算机或远程计算机上的 Windows Management Instrumentation (WMI) 事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-110">The `Register-WmiEvent` cmdlet subscribes to Windows Management Instrumentation (WMI) events on the local computer or on a remote computer.</span></span>

<span data-ttu-id="7a686-111">当引发订阅的 WMI 事件时，会将该事件添加到本地会话的事件队列中，即使该事件是在远程计算机上发生的也是如此。</span><span class="sxs-lookup"><span data-stu-id="7a686-111">When the subscribed WMI event is raised, it is added to the event queue in your local session even if the event occurs on a remote computer.</span></span> <span data-ttu-id="7a686-112">若要获取事件队列中的事件，请使用 `Get-Event` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a686-112">To get events in the event queue, use the `Get-Event` cmdlet.</span></span>

<span data-ttu-id="7a686-113">您可以使用的参数 `Register-WmiEvent` 订阅远程计算机上的事件，并指定可帮助您在队列中标识事件的事件的属性值。</span><span class="sxs-lookup"><span data-stu-id="7a686-113">You can use the parameters of `Register-WmiEvent` to subscribe to events on remote computers and to specify the property values of the events that can help you identify the event in the queue.</span></span> <span data-ttu-id="7a686-114">你还可以使用 **Action** 参数指定在引发订阅事件时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7a686-114">You can also use the **Action** parameter to specify actions to take when a subscribed event is raised.</span></span>

<span data-ttu-id="7a686-115">订阅事件时，会向会话中添加一个事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="7a686-115">When you subscribe to an event, an event subscriber is added to your session.</span></span> <span data-ttu-id="7a686-116">若要获取会话中的事件订阅程序，请使用 `Get-EventSubscriber` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a686-116">To get the event subscribers in the session, use the `Get-EventSubscriber` cmdlet.</span></span> <span data-ttu-id="7a686-117">若要取消订阅，请使用 `Unregister-Event` cmdlet，该 cmdlet 将从会话中删除事件订阅程序。</span><span class="sxs-lookup"><span data-stu-id="7a686-117">To cancel the subscription, use the `Unregister-Event` cmdlet, which deletes the event subscriber from the session.</span></span>

<span data-ttu-id="7a686-118">新通用信息模型 (CIM) cmdlet，引入了 Windows PowerShell 3.0，执行与 WMI cmdlet 相同的任务。</span><span class="sxs-lookup"><span data-stu-id="7a686-118">New Common Information Model (CIM) cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="7a686-119">CIM cmdlet 符合 WS-Management (WSMan) 标准以及 CIM 标准，这使 cmdlet 能够使用相同的技术来管理运行 Windows 操作系统的计算机和运行其他操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="7a686-119">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those that run other operating systems.</span></span> <span data-ttu-id="7a686-120">请 `Register-WmiEvent` 考虑使用 [CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet，而不是使用。</span><span class="sxs-lookup"><span data-stu-id="7a686-120">Instead of using `Register-WmiEvent`, consider using the [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet.</span></span>

## <span data-ttu-id="7a686-121">示例</span><span class="sxs-lookup"><span data-stu-id="7a686-121">EXAMPLES</span></span>

### <span data-ttu-id="7a686-122">示例1：订阅类生成的事件</span><span class="sxs-lookup"><span data-stu-id="7a686-122">Example 1: Subscribe to events generated by a class</span></span>

<span data-ttu-id="7a686-123">此命令订阅由 **Win32_ProcessStartTrace** 类生成的事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-123">This command subscribes to the events generated by the **Win32_ProcessStartTrace** class.</span></span> <span data-ttu-id="7a686-124">只要进程启动，此类就会引发一个事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-124">This class raises an event whenever a process starts.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="7a686-125">示例2：订阅进程的创建事件</span><span class="sxs-lookup"><span data-stu-id="7a686-125">Example 2: Subscribe to creation events for a process</span></span>

<span data-ttu-id="7a686-126">此命令使用一个查询订阅 Win32_process 实例创建事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-126">This command uses a query to subscribe to Win32_process instance creation events.</span></span>

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### <span data-ttu-id="7a686-127">示例3：使用操作来响应事件</span><span class="sxs-lookup"><span data-stu-id="7a686-127">Example 3: Use an action to respond to an event</span></span>

<span data-ttu-id="7a686-128">此示例说明如何使用操作来响应事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-128">This example shows how to use an action to respond to an event.</span></span> <span data-ttu-id="7a686-129">在这种情况下，当进程启动时， `Start-Process` 当前会话中的所有命令都将写入 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7a686-129">In this case, when a process starts, any `Start-Process` commands in the current session are written to an XML file.</span></span>

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

<span data-ttu-id="7a686-130">使用 **Action** 参数时，将 `Register-WmiEvent` 返回表示事件操作的后台作业。</span><span class="sxs-lookup"><span data-stu-id="7a686-130">When you use the **Action** parameter, `Register-WmiEvent` returns a background job that represents the event action.</span></span> <span data-ttu-id="7a686-131">可以使用 **作业** cmdlet （如 `Get-Job` 和 `Receive-Job` ）来管理事件作业。</span><span class="sxs-lookup"><span data-stu-id="7a686-131">You can use the **Job** cmdlets, such as `Get-Job` and `Receive-Job`, to manage the event job.</span></span>

<span data-ttu-id="7a686-132">有关详细信息，请参阅 about_Jobs。</span><span class="sxs-lookup"><span data-stu-id="7a686-132">For more information, see about_Jobs.</span></span>

### <span data-ttu-id="7a686-133">示例4：注册远程计算机上的事件</span><span class="sxs-lookup"><span data-stu-id="7a686-133">Example 4: Register for events on a remote computer</span></span>

<span data-ttu-id="7a686-134">此示例注册远程计算机 Server01 上的事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-134">This example registers for events on the Server01 remote computer.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

<span data-ttu-id="7a686-135">WMI 将这些事件返回到本地计算机并将其存储在当前会话的事件队列中。</span><span class="sxs-lookup"><span data-stu-id="7a686-135">WMI returns the events to the local computer and stores them in the event queue in the current session.</span></span> <span data-ttu-id="7a686-136">若要检索这些事件，请运行本地 `Get-Event` 命令。</span><span class="sxs-lookup"><span data-stu-id="7a686-136">To retrieve the events, run a local `Get-Event` command.</span></span>

## <span data-ttu-id="7a686-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7a686-137">PARAMETERS</span></span>

### <span data-ttu-id="7a686-138">-Action</span><span class="sxs-lookup"><span data-stu-id="7a686-138">-Action</span></span>

<span data-ttu-id="7a686-139">指定用于处理事件的命令。</span><span class="sxs-lookup"><span data-stu-id="7a686-139">Specifies commands that handle the events.</span></span> <span data-ttu-id="7a686-140">**操作** 参数中的命令在引发事件时运行，而不是将事件发送到事件队列。</span><span class="sxs-lookup"><span data-stu-id="7a686-140">The commands in the **Action** parameter run when an event is raised instead of sending the event to the event queue.</span></span> <span data-ttu-id="7a686-141">将命令括在大括号中， (`{}`) 创建脚本块。</span><span class="sxs-lookup"><span data-stu-id="7a686-141">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="7a686-142">**Action** 的值可以包括 `$Event` 、 `$EventSubscriber` 、 `$Sender` 、 `$EventArgs` 和 `$Args` 自动变量，这些变量向 **操作** 脚本块提供有关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="7a686-142">The value of **Action** can include the `$Event`, `$EventSubscriber`, `$Sender`, `$EventArgs`, and `$Args` automatic variables, which provide information about the event to the **Action** script block.</span></span> <span data-ttu-id="7a686-143">有关详细信息，请参阅 about_Automatic_Variables。</span><span class="sxs-lookup"><span data-stu-id="7a686-143">For more information, see about_Automatic_Variables.</span></span>

<span data-ttu-id="7a686-144">指定操作时， `Register-WmiEvent` 将返回表示该操作的事件作业对象。</span><span class="sxs-lookup"><span data-stu-id="7a686-144">When you specify an action, `Register-WmiEvent` returns an event job object that represents that action.</span></span> <span data-ttu-id="7a686-145">你可以使用包含 **job 名词 (作业 cmdlet** **) 的 cmdlet** 来管理事件作业。</span><span class="sxs-lookup"><span data-stu-id="7a686-145">You can use the cmdlets that contain the **Job** noun (the **Job** cmdlets) to manage the event job.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-146">-Class</span><span class="sxs-lookup"><span data-stu-id="7a686-146">-Class</span></span>

<span data-ttu-id="7a686-147">指定要订阅的事件。</span><span class="sxs-lookup"><span data-stu-id="7a686-147">Specifies the event to which you are subscribing.</span></span> <span data-ttu-id="7a686-148">请输入用于生成这些事件的 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="7a686-148">Enter the WMI class that generates the events.</span></span> <span data-ttu-id="7a686-149">每个命令中都需要 **类** 或 **查询** 参数。</span><span class="sxs-lookup"><span data-stu-id="7a686-149">A **Class** or **Query** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7a686-150">-ComputerName</span></span>

<span data-ttu-id="7a686-151">指定在其上运行命令的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="7a686-151">Specifies the name of the computer on which the command runs.</span></span> <span data-ttu-id="7a686-152">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7a686-152">The default is the local computer.</span></span>

<span data-ttu-id="7a686-153">键入计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="7a686-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of the computer.</span></span> <span data-ttu-id="7a686-154">若要指定本地计算机，请键入计算机名、点 (`.`) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="7a686-154">To specify the local computer, type the computer name, a dot (`.`), or localhost.</span></span>

<span data-ttu-id="7a686-155">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="7a686-155">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="7a686-156">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="7a686-156">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="7a686-157">-Credential</span></span>

<span data-ttu-id="7a686-158">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7a686-158">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="7a686-159">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="7a686-159">The default is the current user.</span></span>

<span data-ttu-id="7a686-160">键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="7a686-160">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="7a686-161">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="7a686-161">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-162">-Forward</span><span class="sxs-lookup"><span data-stu-id="7a686-162">-Forward</span></span>

<span data-ttu-id="7a686-163">指示此 cmdlet 将此订阅的事件发送到本地计算机上的会话。</span><span class="sxs-lookup"><span data-stu-id="7a686-163">Indicates that this cmdlet sends events for this subscription to the session on the local computer.</span></span>
<span data-ttu-id="7a686-164">如果要在远程计算机或远程会话中注册事件，可使用此参数。</span><span class="sxs-lookup"><span data-stu-id="7a686-164">Use this parameter when you are registering for events on a remote computer or in a remote session.</span></span>

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

### <span data-ttu-id="7a686-165">-MaxTriggerCount</span><span class="sxs-lookup"><span data-stu-id="7a686-165">-MaxTriggerCount</span></span>

<span data-ttu-id="7a686-166">指定最大触发器计数。</span><span class="sxs-lookup"><span data-stu-id="7a686-166">Specifies the maximum trigger count.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-167">-MessageData</span><span class="sxs-lookup"><span data-stu-id="7a686-167">-MessageData</span></span>

<span data-ttu-id="7a686-168">指定将与此事件订阅关联的任何额外数据。</span><span class="sxs-lookup"><span data-stu-id="7a686-168">Specifies any additional data to be associated with this event subscription.</span></span> <span data-ttu-id="7a686-169">此参数的值出现在与此订阅关联的所有事件的 **MessageData** 属性中。</span><span class="sxs-lookup"><span data-stu-id="7a686-169">The value of this parameter appears in the **MessageData** property of all events associated with this subscription.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-170">-Namespace</span><span class="sxs-lookup"><span data-stu-id="7a686-170">-Namespace</span></span>

<span data-ttu-id="7a686-171">指定 WMI 类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7a686-171">Specifies the namespace of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-172">-Query</span><span class="sxs-lookup"><span data-stu-id="7a686-172">-Query</span></span>

<span data-ttu-id="7a686-173">指定 WMI 查询语言 (WQL) 标识 WMI 事件类的查询，例如： `select * from __InstanceDeletionEvent` 。</span><span class="sxs-lookup"><span data-stu-id="7a686-173">Specifies a query in WMI Query Language (WQL) that identifies the WMI event class, such as: `select * from __InstanceDeletionEvent`.</span></span>

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-174">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="7a686-174">-SourceIdentifier</span></span>

<span data-ttu-id="7a686-175">指定你为订阅选择的名称。</span><span class="sxs-lookup"><span data-stu-id="7a686-175">Specifies a name that you select for the subscription.</span></span> <span data-ttu-id="7a686-176">你选择的名称必须在当前会话中唯一。</span><span class="sxs-lookup"><span data-stu-id="7a686-176">The name that you select must be unique in the current session.</span></span> <span data-ttu-id="7a686-177">默认值为 Windows PowerShell 指定的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7a686-177">The default value is the GUID that Windows PowerShell assigns.</span></span>

<span data-ttu-id="7a686-178">此参数的值显示在订阅服务器对象以及与此订阅关联的所有事件对象的 **SourceIdentifier** 属性值中。</span><span class="sxs-lookup"><span data-stu-id="7a686-178">The value of this parameter appears in the value of the **SourceIdentifier** property of the subscriber object and of all event objects associated with this subscription.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-179">-SupportEvent</span><span class="sxs-lookup"><span data-stu-id="7a686-179">-SupportEvent</span></span>

<span data-ttu-id="7a686-180">指示此 cmdlet 隐藏事件订阅。</span><span class="sxs-lookup"><span data-stu-id="7a686-180">Indicates that this cmdlet hides the event subscription.</span></span> <span data-ttu-id="7a686-181">在当前订阅是更复杂的事件注册机制的一部分并且不应单独发现时，可使用此参数。</span><span class="sxs-lookup"><span data-stu-id="7a686-181">Use this parameter when the current subscription is part of a more complex event registration mechanism and it should not be discovered independently.</span></span>

<span data-ttu-id="7a686-182">若要查看或取消使用 **SupportEvent** 参数创建的订阅，请指定和 Cmdlet 的 **Force** 参数 `Get-EventSubscriber` `Unregister-Event` 。</span><span class="sxs-lookup"><span data-stu-id="7a686-182">To view or cancel a subscription that was created by using the **SupportEvent** parameter, specify the **Force** parameter of the `Get-EventSubscriber` and `Unregister-Event` cmdlets.</span></span>

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

### <span data-ttu-id="7a686-183">-Timeout</span><span class="sxs-lookup"><span data-stu-id="7a686-183">-Timeout</span></span>

<span data-ttu-id="7a686-184">指定 Windows PowerShell 等待此命令完成的时间。</span><span class="sxs-lookup"><span data-stu-id="7a686-184">Specifies how long Windows PowerShell waits for this command to finish.</span></span>

<span data-ttu-id="7a686-185">默认值为 0（零），表示没有超时，这将导致 Windows PowerShell 无限期地等待。</span><span class="sxs-lookup"><span data-stu-id="7a686-185">The default value, 0 (zero), means that there is no time-out, and it causes Windows PowerShell to wait indefinitely.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a686-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7a686-186">CommonParameters</span></span>

<span data-ttu-id="7a686-187">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7a686-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7a686-188">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7a686-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7a686-189">输入</span><span class="sxs-lookup"><span data-stu-id="7a686-189">INPUTS</span></span>

### <span data-ttu-id="7a686-190">无</span><span class="sxs-lookup"><span data-stu-id="7a686-190">None</span></span>

<span data-ttu-id="7a686-191">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a686-191">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="7a686-192">输出</span><span class="sxs-lookup"><span data-stu-id="7a686-192">OUTPUTS</span></span>

### <span data-ttu-id="7a686-193">无</span><span class="sxs-lookup"><span data-stu-id="7a686-193">None</span></span>

<span data-ttu-id="7a686-194">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="7a686-194">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7a686-195">注释</span><span class="sxs-lookup"><span data-stu-id="7a686-195">NOTES</span></span>

<span data-ttu-id="7a686-196">若要在 Windows Vista 或更高版本的 Windows 操作系统中使用此 cmdlet，请使用 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7a686-196">To use this cmdlet in Windows Vista or a later version of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="7a686-197">事件、事件订阅和事件队列仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="7a686-197">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="7a686-198">如果关闭当前会话，将丢弃事件队列并取消事件订阅。</span><span class="sxs-lookup"><span data-stu-id="7a686-198">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="7a686-199">相关链接</span><span class="sxs-lookup"><span data-stu-id="7a686-199">RELATED LINKS</span></span>
