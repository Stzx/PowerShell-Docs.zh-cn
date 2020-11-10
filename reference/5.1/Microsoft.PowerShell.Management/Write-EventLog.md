---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: 4044453cb46b407344619f1edd3227213bf67250
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388240"
---
# <span data-ttu-id="a4dba-103">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-103">Write-EventLog</span></span>

## <span data-ttu-id="a4dba-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a4dba-104">SYNOPSIS</span></span>
<span data-ttu-id="a4dba-105">将事件写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="a4dba-105">Writes an event to an event log.</span></span>

## <span data-ttu-id="a4dba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4dba-106">SYNTAX</span></span>

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## <span data-ttu-id="a4dba-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a4dba-107">DESCRIPTION</span></span>
<span data-ttu-id="a4dba-108">`Write-EventLog`Cmdlet 将事件写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="a4dba-108">The `Write-EventLog` cmdlet writes an event to an event log.</span></span>

<span data-ttu-id="a4dba-109">若要将事件写入事件日志，则计算机上必须存在该事件日志，并且必须为该事件日志注册来源。</span><span class="sxs-lookup"><span data-stu-id="a4dba-109">To write an event to an event log, the event log must exist on the computer and the source must be registered for the event log.</span></span>

<span data-ttu-id="a4dba-110"> ( **eventlog** Cmdlet 包含 **eventlog** 名词的 cmdlet) 仅适用于经典事件日志。</span><span class="sxs-lookup"><span data-stu-id="a4dba-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span> <span data-ttu-id="a4dba-111">若要从使用 windows Vista 和更高版本的 windows 操作系统中的 Windows 事件日志技术的日志中获取事件，请使用 `Get-WinEvent` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4dba-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the `Get-WinEvent` cmdlet.</span></span>

## <span data-ttu-id="a4dba-112">示例</span><span class="sxs-lookup"><span data-stu-id="a4dba-112">EXAMPLES</span></span>

### <span data-ttu-id="a4dba-113">示例1：向应用程序事件日志写入事件</span><span class="sxs-lookup"><span data-stu-id="a4dba-113">Example 1: Write an event to the Application event log</span></span>

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

<span data-ttu-id="a4dba-114">此命令将一个事件从 MyApp 源写入应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="a4dba-114">This command writes an event from the MyApp source to the Application event log.</span></span>

### <span data-ttu-id="a4dba-115">示例2：向远程计算机的应用程序事件日志写入事件</span><span class="sxs-lookup"><span data-stu-id="a4dba-115">Example 2: Write an event to the Application event log of a remote computer</span></span>

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

<span data-ttu-id="a4dba-116">此命令将一个事件从 MyApp 源写入远程计算机 Server01 上的应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="a4dba-116">This command writes an event from the MyApp source to the Application event log on the Server01 remote computer.</span></span>

## <span data-ttu-id="a4dba-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4dba-117">PARAMETERS</span></span>

### <span data-ttu-id="a4dba-118">-Category</span><span class="sxs-lookup"><span data-stu-id="a4dba-118">-Category</span></span>

<span data-ttu-id="a4dba-119">指定事件的任务类别。</span><span class="sxs-lookup"><span data-stu-id="a4dba-119">Specifies a task category for the event.</span></span> <span data-ttu-id="a4dba-120">请输入一个与事件日志的类别消息文件中的字符串相关联的整数。</span><span class="sxs-lookup"><span data-stu-id="a4dba-120">Enter an integer that is associated with the strings in the category message file for the event log.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-121">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a4dba-121">-ComputerName</span></span>

<span data-ttu-id="a4dba-122">指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="a4dba-122">Specifies a remote computer.</span></span> <span data-ttu-id="a4dba-123">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="a4dba-123">The default is the local computer.</span></span>

<span data-ttu-id="a4dba-124">键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="a4dba-124">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="a4dba-125">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="a4dba-125">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="a4dba-126">**ComputerName** `Get-EventLog` 即使你的计算机未配置为运行远程命令，你也可以使用该 cmdlet 的 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="a4dba-126">You can use the **ComputerName** parameter of the `Get-EventLog` cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-127">-EntryType</span><span class="sxs-lookup"><span data-stu-id="a4dba-127">-EntryType</span></span>

<span data-ttu-id="a4dba-128">指定事件的条目类型。</span><span class="sxs-lookup"><span data-stu-id="a4dba-128">Specifies the entry type of the event.</span></span> <span data-ttu-id="a4dba-129">此参数可接受的值包括： Error、Warning、Information、SuccessAudit 和 FailureAudit。</span><span class="sxs-lookup"><span data-stu-id="a4dba-129">The acceptable values for this parameter are: Error, Warning, Information, SuccessAudit, and FailureAudit.</span></span> <span data-ttu-id="a4dba-130">默认值为 Information。</span><span class="sxs-lookup"><span data-stu-id="a4dba-130">The default value is Information.</span></span>

<span data-ttu-id="a4dba-131">有关值的说明，请参阅 [System.diagnostics.eventlogentrytype 枚举](/dotnet/api/system.diagnostics.eventlogentrytype)。</span><span class="sxs-lookup"><span data-stu-id="a4dba-131">For a description of the values, see [EventLogEntryType Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype).</span></span>

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-132">-EventId</span><span class="sxs-lookup"><span data-stu-id="a4dba-132">-EventId</span></span>

<span data-ttu-id="a4dba-133">指定事件标识符。</span><span class="sxs-lookup"><span data-stu-id="a4dba-133">Specifies the event identifier.</span></span> <span data-ttu-id="a4dba-134">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a4dba-134">This parameter is required.</span></span> <span data-ttu-id="a4dba-135">**EventId** 参数的最大值为65535。</span><span class="sxs-lookup"><span data-stu-id="a4dba-135">The maximum value for the **EventId** parameter is 65535.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-136">-LogName</span><span class="sxs-lookup"><span data-stu-id="a4dba-136">-LogName</span></span>

<span data-ttu-id="a4dba-137">指定要向其中写入事件的日志的名称。</span><span class="sxs-lookup"><span data-stu-id="a4dba-137">Specifies the name of the log to which the event is written.</span></span> <span data-ttu-id="a4dba-138">输入日志名称。</span><span class="sxs-lookup"><span data-stu-id="a4dba-138">Enter the log name.</span></span> <span data-ttu-id="a4dba-139">日志名称是 **log** 属性的值，而不是 **LogDisplayName** 。</span><span class="sxs-lookup"><span data-stu-id="a4dba-139">The log name is the value of the **Log** property, not the **LogDisplayName**.</span></span> <span data-ttu-id="a4dba-140">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a4dba-140">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="a4dba-141">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a4dba-141">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-142">-Message</span><span class="sxs-lookup"><span data-stu-id="a4dba-142">-Message</span></span>

<span data-ttu-id="a4dba-143">指定事件消息。</span><span class="sxs-lookup"><span data-stu-id="a4dba-143">Specifies the event message.</span></span> <span data-ttu-id="a4dba-144">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a4dba-144">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-145">-RawData</span><span class="sxs-lookup"><span data-stu-id="a4dba-145">-RawData</span></span>

<span data-ttu-id="a4dba-146">指定与事件关联的二进制数据，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="a4dba-146">Specifies the binary data that is associated with the event, in bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-147">-Source</span><span class="sxs-lookup"><span data-stu-id="a4dba-147">-Source</span></span>

<span data-ttu-id="a4dba-148">指定事件来源，这通常是将事件写入日志的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a4dba-148">Specifies the event source, which is typically the name of the application that is writing the event to the log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4dba-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a4dba-149">CommonParameters</span></span>

<span data-ttu-id="a4dba-150">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a4dba-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4dba-151">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a4dba-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4dba-152">输入</span><span class="sxs-lookup"><span data-stu-id="a4dba-152">INPUTS</span></span>

### <span data-ttu-id="a4dba-153">无</span><span class="sxs-lookup"><span data-stu-id="a4dba-153">None</span></span>
<span data-ttu-id="a4dba-154">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4dba-154">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a4dba-155">输出</span><span class="sxs-lookup"><span data-stu-id="a4dba-155">OUTPUTS</span></span>

### <span data-ttu-id="a4dba-156">System.Diagnostics.EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="a4dba-156">System.Diagnostics.EventLogEntry</span></span>
<span data-ttu-id="a4dba-157">此 cmdlet 将返回表示日志中的事件的对象。</span><span class="sxs-lookup"><span data-stu-id="a4dba-157">This cmdlet returns objects that represents the events in the logs.</span></span>

## <span data-ttu-id="a4dba-158">注释</span><span class="sxs-lookup"><span data-stu-id="a4dba-158">NOTES</span></span>

<span data-ttu-id="a4dba-159">若要使用 `Write-EventLog` ，请使用 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a4dba-159">To use `Write-EventLog`, start Windows PowerShell by using the Run as administrator option.</span></span>

## <span data-ttu-id="a4dba-160">相关链接</span><span class="sxs-lookup"><span data-stu-id="a4dba-160">RELATED LINKS</span></span>

[<span data-ttu-id="a4dba-161">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-161">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="a4dba-162">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-162">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="a4dba-163">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-163">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="a4dba-164">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-164">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="a4dba-165">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-165">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="a4dba-166">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-166">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="a4dba-167">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="a4dba-167">Write-EventLog</span></span>](Write-EventLog.md)
