---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198069"
---
# <span data-ttu-id="7435f-103">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-103">Remove-EventLog</span></span>

## <span data-ttu-id="7435f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7435f-104">SYNOPSIS</span></span>
<span data-ttu-id="7435f-105">删除事件日志或注销事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-105">Deletes an event log or unregisters an event source.</span></span>

## <span data-ttu-id="7435f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7435f-106">SYNTAX</span></span>

### <span data-ttu-id="7435f-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="7435f-107">Default (Default)</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7435f-108">源</span><span class="sxs-lookup"><span data-stu-id="7435f-108">Source</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7435f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7435f-109">DESCRIPTION</span></span>
<span data-ttu-id="7435f-110">**删除-EventLog** cmdlet 从本地或远程计算机中删除事件日志文件，并将该日志的所有事件源注销。</span><span class="sxs-lookup"><span data-stu-id="7435f-110">The **Remove-EventLog** cmdlet deletes an event log file from a local or remote computer and unregisters all its event sources for the log.</span></span>
<span data-ttu-id="7435f-111">你还可以使用此 cmdlet 注销事件源，而无需删除任何事件日志。</span><span class="sxs-lookup"><span data-stu-id="7435f-111">You can also use this cmdlet to unregister event sources without deleting any event logs.</span></span>

<span data-ttu-id="7435f-112">包含 **eventlog** 名词的 Cmdlet （ **eventlog** cmdlet）仅适用于经典事件日志。</span><span class="sxs-lookup"><span data-stu-id="7435f-112">The cmdlets that contain the **EventLog** noun, the **EventLog** cmdlets, work only on classic event logs.</span></span>
<span data-ttu-id="7435f-113">若要从使用 windows Vista 和更高版本的 windows 操作系统中的 Windows 事件日志技术的日志中获取事件，请使用 Get-winevent。</span><span class="sxs-lookup"><span data-stu-id="7435f-113">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use Get-WinEvent.</span></span>

<span data-ttu-id="7435f-114">警告：此 cmdlet 可以删除操作系统事件日志，这可能会导致应用程序失败和意外的系统行为。</span><span class="sxs-lookup"><span data-stu-id="7435f-114">CAUTION: This cmdlet can delete operating system event logs, which might cause application failures and unexpected system behavior.</span></span>

## <span data-ttu-id="7435f-115">示例</span><span class="sxs-lookup"><span data-stu-id="7435f-115">EXAMPLES</span></span>

### <span data-ttu-id="7435f-116">示例1：从本地计算机中删除事件日志</span><span class="sxs-lookup"><span data-stu-id="7435f-116">Example 1: Remove an event log from the local computer</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

<span data-ttu-id="7435f-117">此命令从本地计算机中删除 MyLog 事件日志并注销其事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-117">This command deletes the MyLog event log from the local computer and unregisters its event sources.</span></span>

### <span data-ttu-id="7435f-118">示例2：从多台计算机中删除事件日志</span><span class="sxs-lookup"><span data-stu-id="7435f-118">Example 2: Remove an event log from several computers</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="7435f-119">此命令从本地计算机和 Server01 和 Server02 远程计算机中删除 MyLog 和 TestLog 事件日志。</span><span class="sxs-lookup"><span data-stu-id="7435f-119">This command deletes the MyLog and TestLog event logs from the local computer and the Server01 and Server02 remote computers.</span></span>
<span data-ttu-id="7435f-120">该命令也将注销这些日志的事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-120">The command also unregisters the event sources for these logs.</span></span>

### <span data-ttu-id="7435f-121">示例3：删除事件源</span><span class="sxs-lookup"><span data-stu-id="7435f-121">Example 3: Delete an event source</span></span>

```
PS C:\> Remove-EventLog -Source "MyApp"
```

<span data-ttu-id="7435f-122">此命令从本地计算机上的日志中删除 MyApp 事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-122">This command deletes the MyApp event source from the logs on the local computer.</span></span>
<span data-ttu-id="7435f-123">命令完成后，MyApp 程序将无法写入任何事件日志。</span><span class="sxs-lookup"><span data-stu-id="7435f-123">When the command finishes, the MyApp program cannot write to any event logs.</span></span>

### <span data-ttu-id="7435f-124">示例4：删除事件日志并确认操作</span><span class="sxs-lookup"><span data-stu-id="7435f-124">Example 4: Remove an event log and confirm the action</span></span>

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

<span data-ttu-id="7435f-125">这些命令显示了如何列出计算机上的事件日志，并验证是否已成功 **删除 EventLog** 命令。</span><span class="sxs-lookup"><span data-stu-id="7435f-125">These commands show how to list the event logs on a computer and verify that a **Remove-EventLog** command was successful.</span></span>

### <span data-ttu-id="7435f-126">示例5：删除事件源并确认操作</span><span class="sxs-lookup"><span data-stu-id="7435f-126">Example 5: Remove an event source and confirm the action</span></span>

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

<span data-ttu-id="7435f-127">这些命令使用 Get-WmiObject cmdlet 列出本地计算机上的事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-127">These commands use the Get-WmiObject cmdlet to list the event sources on the local computer.</span></span>
<span data-ttu-id="7435f-128">可以使用这些命令验证用于删除事件源的命令是否成功。</span><span class="sxs-lookup"><span data-stu-id="7435f-128">You can these commands to verify the success of a command or to delete an event source.</span></span>

<span data-ttu-id="7435f-129">第一个命令获取本地计算机上 TestLog event 日志的事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-129">The first command gets the event sources of the TestLog event log on the local computer.</span></span>
<span data-ttu-id="7435f-130">MyApp 就是其中一个事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-130">MyApp is one of the sources.</span></span>

<span data-ttu-id="7435f-131">第二个命令使用 **Remove-EventLog** 的 *Source* 参数删除 MyApp 事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-131">The second command uses the *Source* parameter of **Remove-EventLog** to delete the MyApp event source.</span></span>

<span data-ttu-id="7435f-132">第三个命令与第一个命令相同。</span><span class="sxs-lookup"><span data-stu-id="7435f-132">The third command is identical to the first.</span></span>
<span data-ttu-id="7435f-133">它显示 MyApp 事件源已删除。</span><span class="sxs-lookup"><span data-stu-id="7435f-133">It shows that the MyApp event source was deleted.</span></span>

## <span data-ttu-id="7435f-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7435f-134">PARAMETERS</span></span>

### <span data-ttu-id="7435f-135">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7435f-135">-ComputerName</span></span>
<span data-ttu-id="7435f-136">指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7435f-136">Specifies a remote computer.</span></span>
<span data-ttu-id="7435f-137">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7435f-137">The default is the local computer.</span></span>

<span data-ttu-id="7435f-138">键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="7435f-138">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="7435f-139">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="7435f-139">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="7435f-140">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="7435f-140">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="7435f-141">即使你的计算机未配置为运行远程命令，你也可以使用 " **删除-EventLog** " 的 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="7435f-141">You can use the *ComputerName* parameter of **Remove-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7435f-142">-LogName</span><span class="sxs-lookup"><span data-stu-id="7435f-142">-LogName</span></span>
<span data-ttu-id="7435f-143">指定事件日志。</span><span class="sxs-lookup"><span data-stu-id="7435f-143">Specifies the event logs.</span></span>
<span data-ttu-id="7435f-144">输入一个或多个事件日志的日志名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="7435f-144">Enter the log name of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="7435f-145">日志名称是 **log** 属性的值，而不是 *LogDisplayName* ，不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="7435f-145">The log name is the value of the **Log** property, not the *LogDisplayName* , Wildcard characters are not permitted.</span></span>
<span data-ttu-id="7435f-146">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="7435f-146">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7435f-147">-Source</span><span class="sxs-lookup"><span data-stu-id="7435f-147">-Source</span></span>
<span data-ttu-id="7435f-148">指定此 cmdlet 取消注册的事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-148">Specifies the event sources that this cmdlet unregisters.</span></span>
<span data-ttu-id="7435f-149">输入源名称，而不是可执行文件名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="7435f-149">Enter the source names, not the executable name, separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7435f-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7435f-150">-Confirm</span></span>
<span data-ttu-id="7435f-151">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="7435f-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7435f-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7435f-152">-WhatIf</span></span>
<span data-ttu-id="7435f-153">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7435f-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7435f-154">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="7435f-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7435f-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7435f-155">CommonParameters</span></span>
<span data-ttu-id="7435f-156">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7435f-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7435f-157">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7435f-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7435f-158">输入</span><span class="sxs-lookup"><span data-stu-id="7435f-158">INPUTS</span></span>

### <span data-ttu-id="7435f-159">无</span><span class="sxs-lookup"><span data-stu-id="7435f-159">None</span></span>
<span data-ttu-id="7435f-160">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7435f-160">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7435f-161">输出</span><span class="sxs-lookup"><span data-stu-id="7435f-161">OUTPUTS</span></span>

### <span data-ttu-id="7435f-162">无</span><span class="sxs-lookup"><span data-stu-id="7435f-162">None</span></span>
<span data-ttu-id="7435f-163">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="7435f-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="7435f-164">注释</span><span class="sxs-lookup"><span data-stu-id="7435f-164">NOTES</span></span>

* <span data-ttu-id="7435f-165">若要在 Windows Vista 和更高版本的 Windows 操作系统上使用 **删除事件日志** ，请使用 "以管理员身份运行" 选项启动 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7435f-165">To use **Remove-EventLog** on Windows Vista and later versions of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

  <span data-ttu-id="7435f-166">如果删除了事件日志然后又重新创建该日志，则无法注册相同的事件源。</span><span class="sxs-lookup"><span data-stu-id="7435f-166">If you remove an event log and then re-create the log, you will not be able to register the same event sources.</span></span>
<span data-ttu-id="7435f-167">使用这些事件源将条目写入原始日志的应用程序将无法再写入新日志。</span><span class="sxs-lookup"><span data-stu-id="7435f-167">Applications that used the events sources to write entries to the original log will not be able to write to the new log.</span></span>

* <span data-ttu-id="7435f-168">当注销特定日志的事件源时，该事件源将无法在其他事件日志中写入条目。</span><span class="sxs-lookup"><span data-stu-id="7435f-168">When you unregister an event source for a particular log, the event source might be prevented from writing entries in other event logs.</span></span>

## <span data-ttu-id="7435f-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="7435f-169">RELATED LINKS</span></span>

[<span data-ttu-id="7435f-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="7435f-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="7435f-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="7435f-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="7435f-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="7435f-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="7435f-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="7435f-176">Write-EventLog</span></span>](Write-EventLog.md)
