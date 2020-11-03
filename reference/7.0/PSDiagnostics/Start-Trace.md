---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: 646d186b34e31aa2572aeefa12cc73d941076a13
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196984"
---
# <span data-ttu-id="bc375-103">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="bc375-103">Start-Trace</span></span>

## <span data-ttu-id="bc375-104">摘要</span><span class="sxs-lookup"><span data-stu-id="bc375-104">SYNOPSIS</span></span>
<span data-ttu-id="bc375-105">启动事件跟踪日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="bc375-105">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="bc375-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc375-106">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="bc375-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc375-107">DESCRIPTION</span></span>
<span data-ttu-id="bc375-108">此 cmdlet 将启动 Windows 事件跟踪日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="bc375-108">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="bc375-109">以下 cmdlet 使用此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bc375-109">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="bc375-110">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bc375-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="bc375-111">示例</span><span class="sxs-lookup"><span data-stu-id="bc375-111">EXAMPLES</span></span>

### <span data-ttu-id="bc375-112">示例1：启动 WSMan 跟踪日志记录会话</span><span class="sxs-lookup"><span data-stu-id="bc375-112">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="bc375-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc375-113">PARAMETERS</span></span>

### <span data-ttu-id="bc375-114">-BufferSizeInKB</span><span class="sxs-lookup"><span data-stu-id="bc375-114">-BufferSizeInKB</span></span>
<span data-ttu-id="bc375-115">事件跟踪会话缓冲区大小（kb） (KB) 。</span><span class="sxs-lookup"><span data-stu-id="bc375-115">Event Trace Session buffer size in kilobytes (KB).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-116">-ETS</span><span class="sxs-lookup"><span data-stu-id="bc375-116">-ETS</span></span>
<span data-ttu-id="bc375-117">直接将命令发送到事件跟踪会话，无需保存或计划。</span><span class="sxs-lookup"><span data-stu-id="bc375-117">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="bc375-118">-Format</span><span class="sxs-lookup"><span data-stu-id="bc375-118">-Format</span></span>
<span data-ttu-id="bc375-119">指定数据收集器的日志格式。</span><span class="sxs-lookup"><span data-stu-id="bc375-119">Specifies the log format for the data collector.</span></span> <span data-ttu-id="bc375-120">对于 SQL 数据库格式，必须在命令行中使用 **OutputFilePath** 选项，其值为 `dsn!log` 。</span><span class="sxs-lookup"><span data-stu-id="bc375-120">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="bc375-121">默认值为 binary (bin) 。</span><span class="sxs-lookup"><span data-stu-id="bc375-121">The default is binary (bin).</span></span> <span data-ttu-id="bc375-122">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="bc375-122">The possible values are:</span></span>

- <span data-ttu-id="bc375-123">bin-二进制</span><span class="sxs-lookup"><span data-stu-id="bc375-123">bin - binary</span></span>
- <span data-ttu-id="bc375-124">bincirc-二进制与循环日志记录</span><span class="sxs-lookup"><span data-stu-id="bc375-124">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="bc375-125">csv-逗号分隔值</span><span class="sxs-lookup"><span data-stu-id="bc375-125">csv - Comma-separated values</span></span>
- <span data-ttu-id="bc375-126">tsv-制表符分隔值</span><span class="sxs-lookup"><span data-stu-id="bc375-126">tsv - Tab-separated values</span></span>
- <span data-ttu-id="bc375-127">sql-SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="bc375-127">sql - SQL database</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: bin, bincirc, csv, tsv, sql

Required: False
Position: Named
Default value: bin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-128">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="bc375-128">-MaxBuffers</span></span>
<span data-ttu-id="bc375-129">设置事件跟踪会话缓冲区的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bc375-129">Sets the maximum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-130">-MaxLogFileSizeInMB</span><span class="sxs-lookup"><span data-stu-id="bc375-130">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="bc375-131">以 mb 为单位设置最大日志文件大小 (MB) 或 SQL 日志的记录数。</span><span class="sxs-lookup"><span data-stu-id="bc375-131">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0 (no limit)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-132">-MinBuffers</span><span class="sxs-lookup"><span data-stu-id="bc375-132">-MinBuffers</span></span>
<span data-ttu-id="bc375-133">设置事件跟踪会话缓冲区的最小数目。</span><span class="sxs-lookup"><span data-stu-id="bc375-133">Sets the minimum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-134">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="bc375-134">-OutputFilePath</span></span>
<span data-ttu-id="bc375-135">输出日志文件的路径，或 SQL 数据库中的 DSN 和日志集名称。</span><span class="sxs-lookup"><span data-stu-id="bc375-135">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="bc375-136">默认路径为 `$env:systemdrive\PerfLogs\Admin`。</span><span class="sxs-lookup"><span data-stu-id="bc375-136">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:systemdrive\PerfLogs\Admin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-137">-ProviderFilePath</span><span class="sxs-lookup"><span data-stu-id="bc375-137">-ProviderFilePath</span></span>
<span data-ttu-id="bc375-138">列出多个要启用的事件跟踪提供程序的文件。</span><span class="sxs-lookup"><span data-stu-id="bc375-138">File listing multiple Event Trace providers to enable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc375-139">-SessionName</span><span class="sxs-lookup"><span data-stu-id="bc375-139">-SessionName</span></span>
<span data-ttu-id="bc375-140">事件跟踪会话的名称。</span><span class="sxs-lookup"><span data-stu-id="bc375-140">The name of the Event Trace session.</span></span> <span data-ttu-id="bc375-141">若要停止跟踪会话，必须知道会话名称。</span><span class="sxs-lookup"><span data-stu-id="bc375-141">To stop a trace session you must know the session name.</span></span>

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

### <span data-ttu-id="bc375-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bc375-142">CommonParameters</span></span>

<span data-ttu-id="bc375-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="bc375-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc375-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="bc375-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc375-145">输入</span><span class="sxs-lookup"><span data-stu-id="bc375-145">INPUTS</span></span>

### <span data-ttu-id="bc375-146">无</span><span class="sxs-lookup"><span data-stu-id="bc375-146">None</span></span>

## <span data-ttu-id="bc375-147">输出</span><span class="sxs-lookup"><span data-stu-id="bc375-147">OUTPUTS</span></span>

### <span data-ttu-id="bc375-148">无</span><span class="sxs-lookup"><span data-stu-id="bc375-148">None</span></span>

## <span data-ttu-id="bc375-149">注释</span><span class="sxs-lookup"><span data-stu-id="bc375-149">NOTES</span></span>

## <span data-ttu-id="bc375-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="bc375-150">RELATED LINKS</span></span>

[<span data-ttu-id="bc375-151">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="bc375-151">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="bc375-152">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="bc375-152">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="bc375-153">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="bc375-153">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="bc375-154">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="bc375-154">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="bc375-155">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="bc375-155">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="bc375-156">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="bc375-156">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
