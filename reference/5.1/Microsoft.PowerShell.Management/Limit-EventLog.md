---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198096"
---
# <span data-ttu-id="10bb8-103">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-103">Limit-EventLog</span></span>

## <span data-ttu-id="10bb8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="10bb8-104">SYNOPSIS</span></span>
<span data-ttu-id="10bb8-105">设置限制事件日志大小及其条目存在时间的事件日志属性。</span><span class="sxs-lookup"><span data-stu-id="10bb8-105">Sets the event log properties that limit the size of the event log and the age of its entries.</span></span>

## <span data-ttu-id="10bb8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10bb8-106">SYNTAX</span></span>

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="10bb8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10bb8-107">DESCRIPTION</span></span>
<span data-ttu-id="10bb8-108">" **限制-EventLog** " cmdlet 设置典型事件日志的最大大小，每个事件必须保留多长时间，当日志达到其最大值时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="10bb8-108">The **Limit-EventLog** cmdlet sets the maximum size of a classic event log, how long each event must be retained, and what happens when the log reaches its maximum size.</span></span>
<span data-ttu-id="10bb8-109">你可以使用它来限制本地或远程计算机上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="10bb8-109">You can use it to limit the event logs on local or remote computers.</span></span>

<span data-ttu-id="10bb8-110">包含 EventLog 名词的 cmdlet (EventLog cmdlet) 仅适用于传统事件日志。</span><span class="sxs-lookup"><span data-stu-id="10bb8-110">The cmdlets that contain the EventLog noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="10bb8-111">若要从使用 Windows Vista 以及 Windows 更高版本中的 Windows 事件日志技术的日志中获取事件，请使用 Get-WinEvent。</span><span class="sxs-lookup"><span data-stu-id="10bb8-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use Get-WinEvent.</span></span>

## <span data-ttu-id="10bb8-112">示例</span><span class="sxs-lookup"><span data-stu-id="10bb8-112">EXAMPLES</span></span>

### <span data-ttu-id="10bb8-113">示例 1：增加事件日志的大小</span><span class="sxs-lookup"><span data-stu-id="10bb8-113">Example 1: Increase the size of an event log</span></span>

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

<span data-ttu-id="10bb8-114">此命令将本地计算机上的 Windows PowerShell 事件日志的最大大小增加到 20480 字节 (20 KB)。</span><span class="sxs-lookup"><span data-stu-id="10bb8-114">This command increases the maximum size of the Windows PowerShell event log on the local computer to 20480 bytes (20 KB).</span></span>

### <span data-ttu-id="10bb8-115">示例 2：在指定持续时间内保留事件日志</span><span class="sxs-lookup"><span data-stu-id="10bb8-115">Example 2: Retain an event log for a specified duration</span></span>

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

<span data-ttu-id="10bb8-116">此命令确保计算机 Server01 和 Server02 上的安全日志中的事件至少保留 7 天。</span><span class="sxs-lookup"><span data-stu-id="10bb8-116">This command ensures that events in the Security log on the Server01 and Server02 computers are retained for at least 7 days.</span></span>

### <span data-ttu-id="10bb8-117">示例 3：更改所有事件日志的溢出操作</span><span class="sxs-lookup"><span data-stu-id="10bb8-117">Example 3: Change the overflow action of all event logs</span></span>

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

<span data-ttu-id="10bb8-118">此示例将本地计算机上所有事件日志的溢出操作更改为 OverwriteOlder。</span><span class="sxs-lookup"><span data-stu-id="10bb8-118">This example changes the overflow action of all event logs on the local computer to OverwriteOlder.</span></span>

<span data-ttu-id="10bb8-119">第一条命令获取本地计算机上所有日志的日志名称。</span><span class="sxs-lookup"><span data-stu-id="10bb8-119">The first command gets the log names of all of the logs on the local computer.</span></span>
<span data-ttu-id="10bb8-120">第二条命令设置溢出操作。</span><span class="sxs-lookup"><span data-stu-id="10bb8-120">The second command sets the overflow action.</span></span>
<span data-ttu-id="10bb8-121">第三条命令显示结果。</span><span class="sxs-lookup"><span data-stu-id="10bb8-121">The third command displays the results.</span></span>

## <span data-ttu-id="10bb8-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10bb8-122">PARAMETERS</span></span>

### <span data-ttu-id="10bb8-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="10bb8-123">-ComputerName</span></span>
<span data-ttu-id="10bb8-124">指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="10bb8-124">Specifies remote computers.</span></span>
<span data-ttu-id="10bb8-125">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="10bb8-125">The default is the local computer.</span></span>

<span data-ttu-id="10bb8-126">键入远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="10bb8-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="10bb8-127">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="10bb8-127">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="10bb8-128">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="10bb8-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="10bb8-129">即使你的计算机未配置为运行远程命令，你也可以使用 **Limit-EventLog** 的 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="10bb8-129">You can use the *ComputerName* parameter of **Limit-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10bb8-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="10bb8-130">-LogName</span></span>
<span data-ttu-id="10bb8-131">指定事件日志。</span><span class="sxs-lookup"><span data-stu-id="10bb8-131">Specifies the event logs.</span></span>
<span data-ttu-id="10bb8-132">输入一个或多个事件日志的日志名称（Log 属性的值；而非 LogDisplayName），名称之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="10bb8-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="10bb8-133">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="10bb8-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="10bb8-134">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="10bb8-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10bb8-135">-MaximumSize</span><span class="sxs-lookup"><span data-stu-id="10bb8-135">-MaximumSize</span></span>
<span data-ttu-id="10bb8-136">指定事件日志的最大大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="10bb8-136">Specifies the maximum size of the event logs in bytes.</span></span>
<span data-ttu-id="10bb8-137">输入一个介于 64 千字节 (KB) 和 4 千兆字节 (GB) 之间的值。</span><span class="sxs-lookup"><span data-stu-id="10bb8-137">Enter a value between 64 kilobytes (KB) and 4 gigabytes (GB).</span></span>
<span data-ttu-id="10bb8-138">该值必须能够被 64 KB (65536) 整除。</span><span class="sxs-lookup"><span data-stu-id="10bb8-138">The value must be divisible by 64 KB (65536).</span></span>

<span data-ttu-id="10bb8-139">此参数指定表示传统事件日志的 **MaximumKilobytes** **对象的** "属性" 属性的值。</span><span class="sxs-lookup"><span data-stu-id="10bb8-139">This parameter specifies the value of the **MaximumKilobytes** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10bb8-140">-OverflowAction</span><span class="sxs-lookup"><span data-stu-id="10bb8-140">-OverflowAction</span></span>
<span data-ttu-id="10bb8-141">指定事件日志达到其最大大小时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="10bb8-141">Specifies what happens when the event log reaches its maximum size.</span></span>

<span data-ttu-id="10bb8-142">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="10bb8-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="10bb8-143">DoNotOverwrite：保留现有条目并丢弃新条目。</span><span class="sxs-lookup"><span data-stu-id="10bb8-143">DoNotOverwrite:  Existing entries are retained and new entries are discarded.</span></span>
- <span data-ttu-id="10bb8-144">OverwriteAsNeeded：每个新条目覆盖最旧条目。</span><span class="sxs-lookup"><span data-stu-id="10bb8-144">OverwriteAsNeeded:  Each new entry overwrites the oldest entry.</span></span>
- <span data-ttu-id="10bb8-145">OverwriteOlder：新事件覆盖早于 **MinimumRetentionDays** 属性指定的值的事件。</span><span class="sxs-lookup"><span data-stu-id="10bb8-145">OverwriteOlder:  New events overwrite events older than the value specified by the **MinimumRetentionDays** property.</span></span> <span data-ttu-id="10bb8-146">如果没有 **MinimumRetentionDays** 属性值指定的任何事件，则将丢弃新的事件。</span><span class="sxs-lookup"><span data-stu-id="10bb8-146">If there are no events older than specified by the **MinimumRetentionDays** property value, new events are discarded.</span></span>

<span data-ttu-id="10bb8-147">此参数指定表示传统事件日志的 **OverflowAction** **对象的** "属性" 属性的值。</span><span class="sxs-lookup"><span data-stu-id="10bb8-147">This parameter specifies the value of the **OverflowAction** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10bb8-148">-RetentionDays</span><span class="sxs-lookup"><span data-stu-id="10bb8-148">-RetentionDays</span></span>
<span data-ttu-id="10bb8-149">指定事件必须保留在事件日志中的最短天数。</span><span class="sxs-lookup"><span data-stu-id="10bb8-149">Specifies the minimum number of days that an event must remain in the event log.</span></span>

<span data-ttu-id="10bb8-150">此参数指定表示传统事件日志的 **MinimumRetentionDays** **对象的** "属性" 属性的值。</span><span class="sxs-lookup"><span data-stu-id="10bb8-150">This parameter specifies the value of the **MinimumRetentionDays** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10bb8-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="10bb8-151">-Confirm</span></span>
<span data-ttu-id="10bb8-152">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="10bb8-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="10bb8-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="10bb8-153">-WhatIf</span></span>
<span data-ttu-id="10bb8-154">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="10bb8-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="10bb8-155">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="10bb8-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="10bb8-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10bb8-156">CommonParameters</span></span>
<span data-ttu-id="10bb8-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="10bb8-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10bb8-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="10bb8-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10bb8-159">输入</span><span class="sxs-lookup"><span data-stu-id="10bb8-159">INPUTS</span></span>

### <span data-ttu-id="10bb8-160">无</span><span class="sxs-lookup"><span data-stu-id="10bb8-160">None</span></span>
<span data-ttu-id="10bb8-161">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="10bb8-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="10bb8-162">输出</span><span class="sxs-lookup"><span data-stu-id="10bb8-162">OUTPUTS</span></span>

### <span data-ttu-id="10bb8-163">无</span><span class="sxs-lookup"><span data-stu-id="10bb8-163">None</span></span>
<span data-ttu-id="10bb8-164">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="10bb8-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="10bb8-165">注释</span><span class="sxs-lookup"><span data-stu-id="10bb8-165">NOTES</span></span>

* <span data-ttu-id="10bb8-166">若要在 Windows Vista 及 Windows 的更高版本上使用此 cmdlet，请使用“以管理员身份运行”选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="10bb8-166">To use this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="10bb8-167">此 cmdlet 可更改表示传统事件日志的 **System.Diagnostics.EventLog** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="10bb8-167">This cmdlet changes the properties of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>
<span data-ttu-id="10bb8-168">若要查看事件日志属性的当前设置，请键入 `Get-EventLog -List`。</span><span class="sxs-lookup"><span data-stu-id="10bb8-168">To see the current settings of the event log properties, type `Get-EventLog -List`.</span></span>

*

## <span data-ttu-id="10bb8-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="10bb8-169">RELATED LINKS</span></span>

[<span data-ttu-id="10bb8-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="10bb8-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="10bb8-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="10bb8-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="10bb8-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="10bb8-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="10bb8-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="10bb8-176">Write-EventLog</span></span>](Write-EventLog.md)
