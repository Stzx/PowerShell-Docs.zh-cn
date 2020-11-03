---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198085"
---
# <span data-ttu-id="3d5c2-103">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-103">New-EventLog</span></span>

## <span data-ttu-id="3d5c2-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3d5c2-104">SYNOPSIS</span></span>
<span data-ttu-id="3d5c2-105">在本地或远程计算机上创建新事件日志和新事件源。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-105">Creates a new event log and a new event source on a local or remote computer.</span></span>

## <span data-ttu-id="3d5c2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d5c2-106">SYNTAX</span></span>

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## <span data-ttu-id="3d5c2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d5c2-107">DESCRIPTION</span></span>

<span data-ttu-id="3d5c2-108">此 cmdlet 在本地或远程计算机上创建新的传统事件日志。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-108">This cmdlet creates a new classic event log on a local or remote computer.</span></span> <span data-ttu-id="3d5c2-109">此外，它还会注册写入新日志或现有日志的事件源。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-109">It can also register an event source that writes to the new log or to an existing log.</span></span>

<span data-ttu-id="3d5c2-110">包含 EventLog 名词的 cmdlet (EventLog cmdlet) 仅适用于传统事件日志。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-110">The cmdlets that contain the EventLog noun (the Event log cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="3d5c2-111">若要从使用 windows Vista 和更高版本 Windows 中的 Windows 事件日志技术的日志中获取事件，请使用 `Get-WinEvent` 。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use `Get-WinEvent`.</span></span>

## <span data-ttu-id="3d5c2-112">示例</span><span class="sxs-lookup"><span data-stu-id="3d5c2-112">EXAMPLES</span></span>

### <span data-ttu-id="3d5c2-113">示例 1-创建新的事件日志</span><span class="sxs-lookup"><span data-stu-id="3d5c2-113">Example 1 - create a new event log</span></span>

<span data-ttu-id="3d5c2-114">此命令在本地计算机上创建 TestLog 事件日志并为该日志注册新源。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-114">This command creates the TestLog event log on the local computer and registers a new source for it.</span></span>

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### <span data-ttu-id="3d5c2-115">示例 2-向现有日志添加新的事件源</span><span class="sxs-lookup"><span data-stu-id="3d5c2-115">Example 2 - add a new event source to an existing log</span></span>

<span data-ttu-id="3d5c2-116">此命令将一个新事件源 NewTestApp 添加到 Server01 远程计算机上的应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-116">This command adds a new event source, NewTestApp, to the Application log on the Server01 remote computer.</span></span>

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

<span data-ttu-id="3d5c2-117">该命令要求 NewTestApp.dll 文件位于 Server01 计算机上。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-117">The command requires that the NewTestApp.dll file is located on the Server01 computer.</span></span>

## <span data-ttu-id="3d5c2-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d5c2-118">PARAMETERS</span></span>

### <span data-ttu-id="3d5c2-119">-CategoryResourceFile</span><span class="sxs-lookup"><span data-stu-id="3d5c2-119">-CategoryResourceFile</span></span>

<span data-ttu-id="3d5c2-120">指定某一文件的路径，该文件包含源事件的类别字符串。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-120">Specifies the path to the file that contains category strings for the source events.</span></span> <span data-ttu-id="3d5c2-121">此文件也称为“类别消息文件”。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-121">This file is also known as the Category Message File.</span></span>

<span data-ttu-id="3d5c2-122">文件必须存在于正在创建事件日志的计算机上。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-122">The file must be present on the computer on which the event log is being created.</span></span> <span data-ttu-id="3d5c2-123">此参数不会创建或移动文件。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-123">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d5c2-124">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3d5c2-124">-ComputerName</span></span>

<span data-ttu-id="3d5c2-125">在指定计算机上创建新事件日志。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-125">Creates the new event logs on the specified computers.</span></span> <span data-ttu-id="3d5c2-126">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-126">The default is the local computer.</span></span>

<span data-ttu-id="3d5c2-127">远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-127">The NetBIOS name, IP address, or fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="3d5c2-128">若要指定本地计算机，请键入该计算机名称、句点 (.) 或“localhost”。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-128">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="3d5c2-129">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-129">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="3d5c2-130">**ComputerName** `Get-EventLog` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-130">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d5c2-131">-LogName</span><span class="sxs-lookup"><span data-stu-id="3d5c2-131">-LogName</span></span>

<span data-ttu-id="3d5c2-132">指定事件日志的名称。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-132">Specifies the name of the event log.</span></span>

<span data-ttu-id="3d5c2-133">如果日志不存在，则 `New-EventLog` 创建日志，并将此值用于新事件日志的 **Log** 和 **LogDisplayName** 属性。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-133">If the log does not exist, `New-EventLog` creates the log and uses this value for the **Log** and **LogDisplayName** properties of the new event log.</span></span> <span data-ttu-id="3d5c2-134">如果该日志存在，则 `New-EventLog` 注册事件日志的新源。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-134">If the log exists, `New-EventLog` registers a new source for the event log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d5c2-135">-MessageResourceFile</span><span class="sxs-lookup"><span data-stu-id="3d5c2-135">-MessageResourceFile</span></span>

<span data-ttu-id="3d5c2-136">指定某一文件的路径，该文件包含源事件的消息格式设置字符串。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-136">Specifies the path to the file that contains message formatting strings for the source events.</span></span>
<span data-ttu-id="3d5c2-137">此文件也称为“事件消息文件”。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-137">This file is also known as the Event Message File.</span></span>

<span data-ttu-id="3d5c2-138">文件必须存在于正在创建事件日志的计算机上。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-138">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="3d5c2-139">此参数不会创建或移动文件。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-139">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d5c2-140">-ParameterResourceFile</span><span class="sxs-lookup"><span data-stu-id="3d5c2-140">-ParameterResourceFile</span></span>

<span data-ttu-id="3d5c2-141">指定某一文件的路径，该文件包含用于事件说明中的参数替换的字符串。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-141">Specifies the path to the file that contains strings used for parameter substitutions in event descriptions.</span></span> <span data-ttu-id="3d5c2-142">此文件也称为“参数消息文件”。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-142">This file is also known as the Parameter Message File.</span></span>

<span data-ttu-id="3d5c2-143">文件必须存在于正在创建事件日志的计算机上。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-143">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="3d5c2-144">此参数不会创建或移动文件。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-144">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d5c2-145">-Source</span><span class="sxs-lookup"><span data-stu-id="3d5c2-145">-Source</span></span>

<span data-ttu-id="3d5c2-146">指定事件日志源（如写入事件日志的应用程序）的名称。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-146">Specifies the names of the event log sources, such as application programs that write to the event log.</span></span> <span data-ttu-id="3d5c2-147">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-147">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d5c2-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3d5c2-148">CommonParameters</span></span>

<span data-ttu-id="3d5c2-149">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d5c2-150">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3d5c2-151">输入</span><span class="sxs-lookup"><span data-stu-id="3d5c2-151">INPUTS</span></span>

### <span data-ttu-id="3d5c2-152">无</span><span class="sxs-lookup"><span data-stu-id="3d5c2-152">None</span></span>

<span data-ttu-id="3d5c2-153">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3d5c2-154">输出</span><span class="sxs-lookup"><span data-stu-id="3d5c2-154">OUTPUTS</span></span>

### <span data-ttu-id="3d5c2-155">System.Diagnostics.EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="3d5c2-155">System.Diagnostics.EventLogEntry</span></span>

## <span data-ttu-id="3d5c2-156">注释</span><span class="sxs-lookup"><span data-stu-id="3d5c2-156">NOTES</span></span>

<span data-ttu-id="3d5c2-157">若要 `New-EventLog` 在 Windows Vista 和更高版本的 windows 上使用，请使用 "以管理员身份运行" 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-157">To use `New-EventLog` on Windows Vista and later versions of Windows, open PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="3d5c2-158">若要在 Windows Vista、Windows XP Professional 或 Windows Server 2003 中创建事件源，则你必须是计算机上 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-158">To create an event source in Windows Vista, Windows XP Professional, or Windows Server 2003, you must be a member of the Administrators group on the computer.</span></span>

<span data-ttu-id="3d5c2-159">创建新事件日志和新事件源时，系统会为新日志注册新源，但只有在新日志中写入首个条目时才会创建该日志。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-159">When you create a new event log and a new event source, the system registers the new source for the new log, but the log is not created until the first entry is written to it.</span></span>

<span data-ttu-id="3d5c2-160">操作系统将事件日志存储为文件。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-160">The operating system stores event logs as files.</span></span>

<span data-ttu-id="3d5c2-161">创建新的事件日志时，会将关联的文件存储在 `$env:SystemRoot\System32\Config` 指定计算机上的目录中。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-161">When you create a new event log, the associated file is stored in the `$env:SystemRoot\System32\Config` directory on the specified computer.</span></span>

<span data-ttu-id="3d5c2-162">文件名是带有 .evt 文件扩展名的 **Log** 属性的前八个字符。</span><span class="sxs-lookup"><span data-stu-id="3d5c2-162">The file name is the first eight characters of the **Log** property with an .evt file name extension.</span></span>

## <span data-ttu-id="3d5c2-163">相关链接</span><span class="sxs-lookup"><span data-stu-id="3d5c2-163">RELATED LINKS</span></span>

[<span data-ttu-id="3d5c2-164">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-164">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="3d5c2-165">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-165">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="3d5c2-166">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="3d5c2-166">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="3d5c2-167">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-167">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="3d5c2-168">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-168">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="3d5c2-169">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-169">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="3d5c2-170">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-170">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="3d5c2-171">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="3d5c2-171">Write-EventLog</span></span>](Write-EventLog.md)
