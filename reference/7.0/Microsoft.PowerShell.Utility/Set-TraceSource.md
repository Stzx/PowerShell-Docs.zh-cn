---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 7a1f7e2879b0eeefe8771a5e5a8bf763e48ff106
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196904"
---
# <span data-ttu-id="cc264-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="cc264-103">Set-TraceSource</span></span>

## <span data-ttu-id="cc264-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cc264-104">SYNOPSIS</span></span>
<span data-ttu-id="cc264-105">配置、启动和停止 PowerShell 组件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="cc264-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cc264-106">SYNTAX</span></span>

### <span data-ttu-id="cc264-107">optionsSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="cc264-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="cc264-108">removeAllListenersSet</span><span class="sxs-lookup"><span data-stu-id="cc264-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="cc264-109">removeFileListenersSet</span><span class="sxs-lookup"><span data-stu-id="cc264-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="cc264-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cc264-110">DESCRIPTION</span></span>

<span data-ttu-id="cc264-111">**TraceSource** cmdlet 配置、启动和停止 PowerShell 组件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-111">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="cc264-112">你可以使用它来指定要跟踪的组件以及将跟踪输出发送到的位置。</span><span class="sxs-lookup"><span data-stu-id="cc264-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="cc264-113">示例</span><span class="sxs-lookup"><span data-stu-id="cc264-113">EXAMPLES</span></span>

### <span data-ttu-id="cc264-114">示例1：跟踪 ParameterBinding 组件</span><span class="sxs-lookup"><span data-stu-id="cc264-114">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="cc264-115">此命令启动对 PowerShell 的 ParameterBinding 组件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="cc264-116">它使用 *Name* 参数来指定跟踪源、使用 *Option* 参数选择 ExecutionFlow 跟踪事件，并使用 *PSHost* 参数选择 PowerShell 主机侦听器，该侦听器会将输出发送到控制台。</span><span class="sxs-lookup"><span data-stu-id="cc264-116">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="cc264-117">*ListenerOption* 参数将 ProcessID 和 TimeStamp 值添加到跟踪消息前缀。</span><span class="sxs-lookup"><span data-stu-id="cc264-117">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="cc264-118">示例2：停止跟踪</span><span class="sxs-lookup"><span data-stu-id="cc264-118">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="cc264-119">此命令停止跟踪 PowerShell 的 ParameterBinding 组件。</span><span class="sxs-lookup"><span data-stu-id="cc264-119">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="cc264-120">它使用 *Name* 参数来标识要跟踪的组件，并使用 *RemoveListener* 参数来标识跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="cc264-120">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="cc264-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cc264-121">PARAMETERS</span></span>

### <span data-ttu-id="cc264-122">-Debugger</span><span class="sxs-lookup"><span data-stu-id="cc264-122">-Debugger</span></span>

<span data-ttu-id="cc264-123">指示 cmdlet 将跟踪输出发送到调试程序。</span><span class="sxs-lookup"><span data-stu-id="cc264-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="cc264-124">可以在任何用户模式或内核模式调试程序或者 Microsoft Visual Studio 中查看输出。</span><span class="sxs-lookup"><span data-stu-id="cc264-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="cc264-125">此参数还将选择默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="cc264-125">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="cc264-126">-FilePath</span></span>

<span data-ttu-id="cc264-127">指定此 cmdlet 将跟踪输出发送到的文件。</span><span class="sxs-lookup"><span data-stu-id="cc264-127">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="cc264-128">此参数还将选择文件跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="cc264-128">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="cc264-129">如果使用此参数启动跟踪，请使用 *RemoveFileListener* 参数停止跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-129">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-130">-Force</span><span class="sxs-lookup"><span data-stu-id="cc264-130">-Force</span></span>

<span data-ttu-id="cc264-131">指示该 cmdlet 将覆盖只读文件。</span><span class="sxs-lookup"><span data-stu-id="cc264-131">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="cc264-132">与 *FilePath* 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="cc264-132">Use with the *FilePath* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-133">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="cc264-133">-ListenerOption</span></span>

<span data-ttu-id="cc264-134">向输出中的每条跟踪消息的前缀指定可选数据。</span><span class="sxs-lookup"><span data-stu-id="cc264-134">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="cc264-135">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="cc264-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cc264-136">无</span><span class="sxs-lookup"><span data-stu-id="cc264-136">None</span></span>
- <span data-ttu-id="cc264-137">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="cc264-137">LogicalOperationStack</span></span>
- <span data-ttu-id="cc264-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="cc264-138">DateTime</span></span>
- <span data-ttu-id="cc264-139">Timestamp</span><span class="sxs-lookup"><span data-stu-id="cc264-139">Timestamp</span></span>
- <span data-ttu-id="cc264-140">ProcessId</span><span class="sxs-lookup"><span data-stu-id="cc264-140">ProcessId</span></span>
- <span data-ttu-id="cc264-141">ThreadId</span><span class="sxs-lookup"><span data-stu-id="cc264-141">ThreadId</span></span>
- <span data-ttu-id="cc264-142">Callstack</span><span class="sxs-lookup"><span data-stu-id="cc264-142">Callstack</span></span>

<span data-ttu-id="cc264-143">默认值为“None”。</span><span class="sxs-lookup"><span data-stu-id="cc264-143">None is the default.</span></span>

<span data-ttu-id="cc264-144">若要指定多个选项，请使用逗号分隔这些选项，但不要带有空格，并将这些选项括在引号中，例如“ProcessID,ThreadID”。</span><span class="sxs-lookup"><span data-stu-id="cc264-144">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-145">-Name</span><span class="sxs-lookup"><span data-stu-id="cc264-145">-Name</span></span>

<span data-ttu-id="cc264-146">指定要跟踪的组件。</span><span class="sxs-lookup"><span data-stu-id="cc264-146">Specifies which components are traced.</span></span>
<span data-ttu-id="cc264-147">请输入各个组件的跟踪源的名称。</span><span class="sxs-lookup"><span data-stu-id="cc264-147">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="cc264-148">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="cc264-148">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="cc264-149">-Option</span><span class="sxs-lookup"><span data-stu-id="cc264-149">-Option</span></span>

<span data-ttu-id="cc264-150">指定要跟踪的事件类型。</span><span class="sxs-lookup"><span data-stu-id="cc264-150">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="cc264-151">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="cc264-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cc264-152">无</span><span class="sxs-lookup"><span data-stu-id="cc264-152">None</span></span>
- <span data-ttu-id="cc264-153">构造函数</span><span class="sxs-lookup"><span data-stu-id="cc264-153">Constructor</span></span>
- <span data-ttu-id="cc264-154">释放</span><span class="sxs-lookup"><span data-stu-id="cc264-154">Dispose</span></span>
- <span data-ttu-id="cc264-155">终结器</span><span class="sxs-lookup"><span data-stu-id="cc264-155">Finalizer</span></span>
- <span data-ttu-id="cc264-156">方法</span><span class="sxs-lookup"><span data-stu-id="cc264-156">Method</span></span>
- <span data-ttu-id="cc264-157">属性</span><span class="sxs-lookup"><span data-stu-id="cc264-157">Property</span></span>
- <span data-ttu-id="cc264-158">委托</span><span class="sxs-lookup"><span data-stu-id="cc264-158">Delegates</span></span>
- <span data-ttu-id="cc264-159">事件</span><span class="sxs-lookup"><span data-stu-id="cc264-159">Events</span></span>
- <span data-ttu-id="cc264-160">异常</span><span class="sxs-lookup"><span data-stu-id="cc264-160">Exception</span></span>
- <span data-ttu-id="cc264-161">Lock</span><span class="sxs-lookup"><span data-stu-id="cc264-161">Lock</span></span>
- <span data-ttu-id="cc264-162">错误</span><span class="sxs-lookup"><span data-stu-id="cc264-162">Error</span></span>
- <span data-ttu-id="cc264-163">错误</span><span class="sxs-lookup"><span data-stu-id="cc264-163">Errors</span></span>
- <span data-ttu-id="cc264-164">警告</span><span class="sxs-lookup"><span data-stu-id="cc264-164">Warning</span></span>
- <span data-ttu-id="cc264-165">“详细”</span><span class="sxs-lookup"><span data-stu-id="cc264-165">Verbose</span></span>
- <span data-ttu-id="cc264-166">WriteLine</span><span class="sxs-lookup"><span data-stu-id="cc264-166">WriteLine</span></span>
- <span data-ttu-id="cc264-167">数据</span><span class="sxs-lookup"><span data-stu-id="cc264-167">Data</span></span>
- <span data-ttu-id="cc264-168">范围</span><span class="sxs-lookup"><span data-stu-id="cc264-168">Scope</span></span>
- <span data-ttu-id="cc264-169">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="cc264-169">ExecutionFlow</span></span>
- <span data-ttu-id="cc264-170">Assert</span><span class="sxs-lookup"><span data-stu-id="cc264-170">Assert</span></span>
- <span data-ttu-id="cc264-171">全部</span><span class="sxs-lookup"><span data-stu-id="cc264-171">All</span></span>

<span data-ttu-id="cc264-172">默认值为“All”。</span><span class="sxs-lookup"><span data-stu-id="cc264-172">All is the default.</span></span>

<span data-ttu-id="cc264-173">以下值是其他值的组合：</span><span class="sxs-lookup"><span data-stu-id="cc264-173">The following values are combinations of other values:</span></span>

- <span data-ttu-id="cc264-174">ExecutionFlow：（Constructor、Dispose、Finalizer、Method、Delegates、Events 和 Scope）</span><span class="sxs-lookup"><span data-stu-id="cc264-174">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="cc264-175">Data：（Constructor、Dispose、Finalizer、Property、Verbose 和 WriteLine）</span><span class="sxs-lookup"><span data-stu-id="cc264-175">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="cc264-176">Errors：（Error 和 Exception）。</span><span class="sxs-lookup"><span data-stu-id="cc264-176">Errors: (Error and Exception).</span></span>

<span data-ttu-id="cc264-177">若要指定多个选项，请使用逗号分隔这些选项，但不要带有空格，并将这些选项括在引号中，例如“Constructor,Dispose”。</span><span class="sxs-lookup"><span data-stu-id="cc264-177">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cc264-178">-PassThru</span></span>

<span data-ttu-id="cc264-179">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="cc264-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="cc264-180">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="cc264-180">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-181">-PSHost</span><span class="sxs-lookup"><span data-stu-id="cc264-181">-PSHost</span></span>

<span data-ttu-id="cc264-182">指示，此 cmdlet 将跟踪输出发送到 PowerShell 主机。</span><span class="sxs-lookup"><span data-stu-id="cc264-182">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="cc264-183">此参数还将选择 PSHost 跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="cc264-183">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-184">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="cc264-184">-RemoveFileListener</span></span>

<span data-ttu-id="cc264-185">通过删除与指定文件关联的文件跟踪侦听器来停止跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-185">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="cc264-186">输入跟踪输出文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="cc264-186">Enter the path and file name of the trace output file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-187">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="cc264-187">-RemoveListener</span></span>

<span data-ttu-id="cc264-188">通过删除跟踪侦听器来停止跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-188">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="cc264-189">对 *RemoveListener* 使用以下值：</span><span class="sxs-lookup"><span data-stu-id="cc264-189">Use the following values with *RemoveListener* :</span></span>

- <span data-ttu-id="cc264-190">若要删除 PSHost (console) ，请键入 `Host` 。</span><span class="sxs-lookup"><span data-stu-id="cc264-190">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="cc264-191">若要删除调试程序，请键入 `Debug` 。</span><span class="sxs-lookup"><span data-stu-id="cc264-191">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="cc264-192">若要删除所有跟踪侦听器，请键入 `*` 。</span><span class="sxs-lookup"><span data-stu-id="cc264-192">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="cc264-193">若要删除文件跟踪侦听器，请使用 *RemoveFileListener* 参数。</span><span class="sxs-lookup"><span data-stu-id="cc264-193">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc264-194">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cc264-194">CommonParameters</span></span>

<span data-ttu-id="cc264-195">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cc264-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cc264-196">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="cc264-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cc264-197">输入</span><span class="sxs-lookup"><span data-stu-id="cc264-197">INPUTS</span></span>

### <span data-ttu-id="cc264-198">System.String</span><span class="sxs-lookup"><span data-stu-id="cc264-198">System.String</span></span>

<span data-ttu-id="cc264-199">可以通过管道将包含名称的字符串传递给 **TraceSource** 。</span><span class="sxs-lookup"><span data-stu-id="cc264-199">You can pipe a string that contains a name to **Set-TraceSource** .</span></span>

## <span data-ttu-id="cc264-200">输出</span><span class="sxs-lookup"><span data-stu-id="cc264-200">OUTPUTS</span></span>

### <span data-ttu-id="cc264-201">无或 System.Management.Automation.PSTraceSource</span><span class="sxs-lookup"><span data-stu-id="cc264-201">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="cc264-202">当使用 *PassThru* 参数时， **TraceSource 将** 生成一个表示跟踪会话的 **system.management.automation.pstracesource** 对象。</span><span class="sxs-lookup"><span data-stu-id="cc264-202">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="cc264-203">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="cc264-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cc264-204">注释</span><span class="sxs-lookup"><span data-stu-id="cc264-204">NOTES</span></span>

* <span data-ttu-id="cc264-205">跟踪是开发人员用于调试和优化程序的一种方法。</span><span class="sxs-lookup"><span data-stu-id="cc264-205">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="cc264-206">在跟踪过程中，程序将生成有关其内部处理过程中每个步骤的详细消息。</span><span class="sxs-lookup"><span data-stu-id="cc264-206">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="cc264-207">PowerShell 跟踪 cmdlet 专为帮助 PowerShell 开发人员而设计，但是它们可供所有用户使用。</span><span class="sxs-lookup"><span data-stu-id="cc264-207">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="cc264-208">它们允许你监视 PowerShell 功能的几乎每个方面。</span><span class="sxs-lookup"><span data-stu-id="cc264-208">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="cc264-209">跟踪源是每个 PowerShell 组件的一部分，用于管理跟踪并为组件生成跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="cc264-209">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="cc264-210">若要跟踪某个组件，你应标识其跟踪源。</span><span class="sxs-lookup"><span data-stu-id="cc264-210">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="cc264-211">跟踪侦听器接收跟踪的输出并将其显示给用户。</span><span class="sxs-lookup"><span data-stu-id="cc264-211">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="cc264-212">你可以选择将跟踪数据发送给用户模式或内核模式调试程序、控制台、文件或从 **TraceListener** 类派生的自定义侦听器。。</span><span class="sxs-lookup"><span data-stu-id="cc264-212">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="cc264-213">若要启动跟踪，请使用 *Name* 参数指定跟踪源、 *FilePath* 、 *调试器* 或 *PSHost* 参数，以指定 (输出) 的目标侦听器。</span><span class="sxs-lookup"><span data-stu-id="cc264-213">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath* , *Debugger* , or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="cc264-214">使用 *Options* 参数确定要跟踪的事件类型，并使用 *ListenerOption* 参数配置跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="cc264-214">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="cc264-215">若要更改跟踪的配置，请输入 **TraceSource** 命令来启动跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-215">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="cc264-216">PowerShell 可识别跟踪源已被跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-216">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="cc264-217">它将停止跟踪、添加新配置，然后启动或重新启动该跟踪。</span><span class="sxs-lookup"><span data-stu-id="cc264-217">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="cc264-218">若要停止跟踪，请使用 *RemoveListener* 参数。</span><span class="sxs-lookup"><span data-stu-id="cc264-218">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="cc264-219">若要停止使用文件侦听器的跟踪 (使用 *FilePath* 参数) 启动的跟踪，请使用 *RemoveFileListener* 参数。</span><span class="sxs-lookup"><span data-stu-id="cc264-219">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="cc264-220">删除该侦听器后，跟踪将停止。</span><span class="sxs-lookup"><span data-stu-id="cc264-220">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="cc264-221">若要确定可以跟踪哪些组件，请使用 Get-TraceSource。</span><span class="sxs-lookup"><span data-stu-id="cc264-221">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="cc264-222">当组件正在使用时，将自动加载每个模块的跟踪源，并且它们显示在 **TraceSource** 的输出中。</span><span class="sxs-lookup"><span data-stu-id="cc264-222">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource** .</span></span>

## <span data-ttu-id="cc264-223">相关链接</span><span class="sxs-lookup"><span data-stu-id="cc264-223">RELATED LINKS</span></span>

[<span data-ttu-id="cc264-224">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="cc264-224">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="cc264-225">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="cc264-225">Trace-Command</span></span>](Trace-Command.md)
