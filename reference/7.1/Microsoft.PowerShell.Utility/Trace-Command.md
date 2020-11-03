---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: c26e1c46db8f7c6eeeb5c970bc17921622cd023e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197367"
---
# <span data-ttu-id="0bea1-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="0bea1-103">Trace-Command</span></span>

## <span data-ttu-id="0bea1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0bea1-104">SYNOPSIS</span></span>
<span data-ttu-id="0bea1-105">配置并启动对指定表达式或命令的跟踪。</span><span class="sxs-lookup"><span data-stu-id="0bea1-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="0bea1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bea1-106">SYNTAX</span></span>

### <span data-ttu-id="0bea1-107">expressionSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="0bea1-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="0bea1-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="0bea1-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="0bea1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bea1-109">DESCRIPTION</span></span>
<span data-ttu-id="0bea1-110">`Trace-Command`Cmdlet 配置并启动对指定表达式或命令的跟踪。</span><span class="sxs-lookup"><span data-stu-id="0bea1-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="0bea1-111">其工作方式与 Set-TraceSource 相似，但仅适用于指定的命令。</span><span class="sxs-lookup"><span data-stu-id="0bea1-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="0bea1-112">示例</span><span class="sxs-lookup"><span data-stu-id="0bea1-112">EXAMPLES</span></span>

### <span data-ttu-id="0bea1-113">示例 1：跟踪元数据处理、参数绑定和表达式</span><span class="sxs-lookup"><span data-stu-id="0bea1-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="0bea1-114">此示例启动对表达式的元数据处理、参数绑定以及 cmdlet 创建和析构的跟踪 `Get-Process Notepad` 。</span><span class="sxs-lookup"><span data-stu-id="0bea1-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="0bea1-115">它使用 **Name** 参数来指定跟踪源，使用 **Expression** 参数指定命令，并使用 **PSHost** 参数将输出发送到控制台。</span><span class="sxs-lookup"><span data-stu-id="0bea1-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="0bea1-116">由于该命令未指定任何跟踪选项或侦听器选项，因此该命令使用默认值：</span><span class="sxs-lookup"><span data-stu-id="0bea1-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="0bea1-117">跟踪选项的所有</span><span class="sxs-lookup"><span data-stu-id="0bea1-117">All for the tracing options</span></span>
- <span data-ttu-id="0bea1-118">侦听器选项均无</span><span class="sxs-lookup"><span data-stu-id="0bea1-118">None for the listener options</span></span>

### <span data-ttu-id="0bea1-119">示例 2：跟踪 ParameterBinding 操作</span><span class="sxs-lookup"><span data-stu-id="0bea1-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="0bea1-120">此示例在处理 **ParameterBinding** `Get-Alias` 从管道中获取输入的表达式时，跟踪 PowerShell 的 ParameterBinding 操作的操作。</span><span class="sxs-lookup"><span data-stu-id="0bea1-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="0bea1-121">在中 `Trace-Command` ， **InputObject** 参数将对象传递给要在跟踪期间处理的表达式。</span><span class="sxs-lookup"><span data-stu-id="0bea1-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="0bea1-122">第一个命令将字符串存储 `i*` 在 `$A` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0bea1-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="0bea1-123">第二个命令将 `Trace-Command` cmdlet 与 ParameterBinding 跟踪源一起使用。</span><span class="sxs-lookup"><span data-stu-id="0bea1-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="0bea1-124">**PSHost** 参数将输出发送到控制台。</span><span class="sxs-lookup"><span data-stu-id="0bea1-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="0bea1-125">正在处理的表达式为 `Get-Alias $Input` ，其中的 `$Input` 变量与 **InputObject** 参数关联。</span><span class="sxs-lookup"><span data-stu-id="0bea1-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="0bea1-126">**InputObject** 参数将变量传递 `$A` 给表达式。</span><span class="sxs-lookup"><span data-stu-id="0bea1-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="0bea1-127">实际上，在跟踪期间处理的命令是 `Get-Alias -InputObject $A" or "$A | Get-Alias`。</span><span class="sxs-lookup"><span data-stu-id="0bea1-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="0bea1-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bea1-128">PARAMETERS</span></span>

### <span data-ttu-id="0bea1-129">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="0bea1-129">-ArgumentList</span></span>

<span data-ttu-id="0bea1-130">为要跟踪的命令指定参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="0bea1-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="0bea1-131">**ArgumentList** 的别名是 **Args** 。</span><span class="sxs-lookup"><span data-stu-id="0bea1-131">The alias for **ArgumentList** is **Args** .</span></span> <span data-ttu-id="0bea1-132">对于调试动态参数，此功能尤其有用。</span><span class="sxs-lookup"><span data-stu-id="0bea1-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="0bea1-133">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="0bea1-133">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-134">-Command</span><span class="sxs-lookup"><span data-stu-id="0bea1-134">-Command</span></span>

<span data-ttu-id="0bea1-135">指定要在跟踪期间处理的命令。</span><span class="sxs-lookup"><span data-stu-id="0bea1-135">Specifies a command that is being processed during the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-136">-Debugger</span><span class="sxs-lookup"><span data-stu-id="0bea1-136">-Debugger</span></span>

<span data-ttu-id="0bea1-137">指示 cmdlet 将跟踪输出发送到调试程序。</span><span class="sxs-lookup"><span data-stu-id="0bea1-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="0bea1-138">可以在任何用户模式或内核模式调试程序或者 Visual Studio 中查看输出。</span><span class="sxs-lookup"><span data-stu-id="0bea1-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="0bea1-139">此参数还将选择默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bea1-139">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="0bea1-140">-Expression</span><span class="sxs-lookup"><span data-stu-id="0bea1-140">-Expression</span></span>

<span data-ttu-id="0bea1-141">指定要在跟踪期间处理的表达式。</span><span class="sxs-lookup"><span data-stu-id="0bea1-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="0bea1-142">将表达式括在大括号中， (`{}`) 。</span><span class="sxs-lookup"><span data-stu-id="0bea1-142">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="0bea1-143">-FilePath</span></span>

<span data-ttu-id="0bea1-144">指定 cmdlet 将跟踪输出发送到的文件。</span><span class="sxs-lookup"><span data-stu-id="0bea1-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="0bea1-145">此参数还将选择文件跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bea1-145">This parameter also selects the file trace listener.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-146">-Force</span><span class="sxs-lookup"><span data-stu-id="0bea1-146">-Force</span></span>

<span data-ttu-id="0bea1-147">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="0bea1-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="0bea1-148">与 **FilePath** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="0bea1-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="0bea1-149">即使使用 **Force** 参数，该 cmdlet 也无法覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="0bea1-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="0bea1-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0bea1-150">-InputObject</span></span>

<span data-ttu-id="0bea1-151">为要在跟踪期间处理的表达式指定输入。</span><span class="sxs-lookup"><span data-stu-id="0bea1-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="0bea1-152">可以输入表示表达式接受的输入的变量，或通过管道传递对象。</span><span class="sxs-lookup"><span data-stu-id="0bea1-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-153">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="0bea1-153">-ListenerOption</span></span>

<span data-ttu-id="0bea1-154">向输出中的每条跟踪消息的前缀指定可选数据。</span><span class="sxs-lookup"><span data-stu-id="0bea1-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="0bea1-155">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="0bea1-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0bea1-156">无</span><span class="sxs-lookup"><span data-stu-id="0bea1-156">None</span></span>
- <span data-ttu-id="0bea1-157">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="0bea1-157">LogicalOperationStack</span></span>
- <span data-ttu-id="0bea1-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="0bea1-158">DateTime</span></span>
- <span data-ttu-id="0bea1-159">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0bea1-159">Timestamp</span></span>
- <span data-ttu-id="0bea1-160">ProcessId</span><span class="sxs-lookup"><span data-stu-id="0bea1-160">ProcessId</span></span>
- <span data-ttu-id="0bea1-161">ThreadId</span><span class="sxs-lookup"><span data-stu-id="0bea1-161">ThreadId</span></span>
- <span data-ttu-id="0bea1-162">Callstack</span><span class="sxs-lookup"><span data-stu-id="0bea1-162">Callstack</span></span>

<span data-ttu-id="0bea1-163">默认值为 **None** 。</span><span class="sxs-lookup"><span data-stu-id="0bea1-163">**None** is the default.</span></span>

<span data-ttu-id="0bea1-164">若要指定多个选项，请使用逗号分隔这些选项，但不要带有空格，并将这些选项括在引号中，例如“ProcessID,ThreadID”。</span><span class="sxs-lookup"><span data-stu-id="0bea1-164">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-165">-Name</span><span class="sxs-lookup"><span data-stu-id="0bea1-165">-Name</span></span>

<span data-ttu-id="0bea1-166">指定所跟踪的 PowerShell 组件的数组。</span><span class="sxs-lookup"><span data-stu-id="0bea1-166">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="0bea1-167">请输入各个组件的跟踪源的名称。</span><span class="sxs-lookup"><span data-stu-id="0bea1-167">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="0bea1-168">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0bea1-168">Wildcards are permitted.</span></span> <span data-ttu-id="0bea1-169">若要在计算机上查找跟踪源，请键入 `Get-TraceSource`。</span><span class="sxs-lookup"><span data-stu-id="0bea1-169">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-170">-Option</span><span class="sxs-lookup"><span data-stu-id="0bea1-170">-Option</span></span>

<span data-ttu-id="0bea1-171">确定要跟踪的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="0bea1-171">Determines the type of events that are traced.</span></span> <span data-ttu-id="0bea1-172">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="0bea1-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0bea1-173">无</span><span class="sxs-lookup"><span data-stu-id="0bea1-173">None</span></span>
- <span data-ttu-id="0bea1-174">构造函数</span><span class="sxs-lookup"><span data-stu-id="0bea1-174">Constructor</span></span>
- <span data-ttu-id="0bea1-175">释放</span><span class="sxs-lookup"><span data-stu-id="0bea1-175">Dispose</span></span>
- <span data-ttu-id="0bea1-176">终结器</span><span class="sxs-lookup"><span data-stu-id="0bea1-176">Finalizer</span></span>
- <span data-ttu-id="0bea1-177">方法</span><span class="sxs-lookup"><span data-stu-id="0bea1-177">Method</span></span>
- <span data-ttu-id="0bea1-178">属性</span><span class="sxs-lookup"><span data-stu-id="0bea1-178">Property</span></span>
- <span data-ttu-id="0bea1-179">委托</span><span class="sxs-lookup"><span data-stu-id="0bea1-179">Delegates</span></span>
- <span data-ttu-id="0bea1-180">事件</span><span class="sxs-lookup"><span data-stu-id="0bea1-180">Events</span></span>
- <span data-ttu-id="0bea1-181">异常</span><span class="sxs-lookup"><span data-stu-id="0bea1-181">Exception</span></span>
- <span data-ttu-id="0bea1-182">Lock</span><span class="sxs-lookup"><span data-stu-id="0bea1-182">Lock</span></span>
- <span data-ttu-id="0bea1-183">错误</span><span class="sxs-lookup"><span data-stu-id="0bea1-183">Error</span></span>
- <span data-ttu-id="0bea1-184">错误</span><span class="sxs-lookup"><span data-stu-id="0bea1-184">Errors</span></span>
- <span data-ttu-id="0bea1-185">警告</span><span class="sxs-lookup"><span data-stu-id="0bea1-185">Warning</span></span>
- <span data-ttu-id="0bea1-186">“详细”</span><span class="sxs-lookup"><span data-stu-id="0bea1-186">Verbose</span></span>
- <span data-ttu-id="0bea1-187">WriteLine</span><span class="sxs-lookup"><span data-stu-id="0bea1-187">WriteLine</span></span>
- <span data-ttu-id="0bea1-188">数据</span><span class="sxs-lookup"><span data-stu-id="0bea1-188">Data</span></span>
- <span data-ttu-id="0bea1-189">范围</span><span class="sxs-lookup"><span data-stu-id="0bea1-189">Scope</span></span>
- <span data-ttu-id="0bea1-190">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="0bea1-190">ExecutionFlow</span></span>
- <span data-ttu-id="0bea1-191">Assert</span><span class="sxs-lookup"><span data-stu-id="0bea1-191">Assert</span></span>
- <span data-ttu-id="0bea1-192">全部</span><span class="sxs-lookup"><span data-stu-id="0bea1-192">All</span></span>

<span data-ttu-id="0bea1-193">默认值为“All”。</span><span class="sxs-lookup"><span data-stu-id="0bea1-193">All is the default.</span></span>

<span data-ttu-id="0bea1-194">以下值是其他值的组合：</span><span class="sxs-lookup"><span data-stu-id="0bea1-194">The following values are combinations of other values:</span></span>

- <span data-ttu-id="0bea1-195">ExecutionFlow：（Constructor、Dispose、Finalizer、Method、Delegates、Events 和 Scope）</span><span class="sxs-lookup"><span data-stu-id="0bea1-195">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="0bea1-196">Data：（Constructor、Dispose、Finalizer、Property、Verbose 和 WriteLine）</span><span class="sxs-lookup"><span data-stu-id="0bea1-196">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="0bea1-197">Errors：（Error 和 Exception）。</span><span class="sxs-lookup"><span data-stu-id="0bea1-197">Errors: (Error and Exception).</span></span>

<span data-ttu-id="0bea1-198">若要指定多个选项，请使用逗号分隔这些选项，但不要带有空格，并将这些选项括在引号中，例如“Constructor,Dispose”。</span><span class="sxs-lookup"><span data-stu-id="0bea1-198">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bea1-199">-PSHost</span><span class="sxs-lookup"><span data-stu-id="0bea1-199">-PSHost</span></span>

<span data-ttu-id="0bea1-200">指示 cmdlet 将跟踪输出发送到 PowerShell 主机。</span><span class="sxs-lookup"><span data-stu-id="0bea1-200">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="0bea1-201">此参数还将选择 PSHost 跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bea1-201">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="0bea1-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bea1-202">CommonParameters</span></span>

<span data-ttu-id="0bea1-203">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0bea1-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bea1-204">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0bea1-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bea1-205">输入</span><span class="sxs-lookup"><span data-stu-id="0bea1-205">INPUTS</span></span>

### <span data-ttu-id="0bea1-206">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0bea1-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0bea1-207">可以通过管道将表示表达式输入的对象传递给 `Trace-Command` 。</span><span class="sxs-lookup"><span data-stu-id="0bea1-207">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="0bea1-208">输出</span><span class="sxs-lookup"><span data-stu-id="0bea1-208">OUTPUTS</span></span>

### <span data-ttu-id="0bea1-209">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0bea1-209">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0bea1-210">在调试流中返回命令跟踪。</span><span class="sxs-lookup"><span data-stu-id="0bea1-210">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="0bea1-211">注释</span><span class="sxs-lookup"><span data-stu-id="0bea1-211">NOTES</span></span>

- <span data-ttu-id="0bea1-212">跟踪是开发人员用于调试和优化程序的一种方法。</span><span class="sxs-lookup"><span data-stu-id="0bea1-212">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="0bea1-213">在跟踪过程中，程序将生成有关其内部处理过程中每个步骤的详细消息。</span><span class="sxs-lookup"><span data-stu-id="0bea1-213">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="0bea1-214">PowerShell 跟踪 cmdlet 专为帮助 PowerShell 开发人员而设计，但是它们可供所有用户使用。</span><span class="sxs-lookup"><span data-stu-id="0bea1-214">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="0bea1-215">使用这些 cmdlet，你可以监视 shell 功能的几乎每个方面。</span><span class="sxs-lookup"><span data-stu-id="0bea1-215">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="0bea1-216">若要查找为跟踪启用的 PowerShell 组件，请键入 `Get-Help Get-TraceSource` 。</span><span class="sxs-lookup"><span data-stu-id="0bea1-216">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="0bea1-217">跟踪源是每个 PowerShell 组件的一部分，用于管理跟踪并为组件生成跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="0bea1-217">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="0bea1-218">若要跟踪某个组件，你应标识其跟踪源。</span><span class="sxs-lookup"><span data-stu-id="0bea1-218">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="0bea1-219">跟踪侦听器接收跟踪的输出并将其显示给用户。</span><span class="sxs-lookup"><span data-stu-id="0bea1-219">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="0bea1-220">你可以选择将跟踪数据发送到用户模式或内核模式调试程序、主机或控制台、文件或从 **TraceListener** 类派生的自定义侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bea1-220">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="0bea1-221">当你使用 commandSet 参数集时，PowerShell 将处理命令，就像在管道中处理此命令一样。</span><span class="sxs-lookup"><span data-stu-id="0bea1-221">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="0bea1-222">例如，不对每个传入对象重复执行命令发现。</span><span class="sxs-lookup"><span data-stu-id="0bea1-222">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="0bea1-223">**Name** 、 **Expression** 、 **Option** 和 **Command** 参数的名称是可选的。</span><span class="sxs-lookup"><span data-stu-id="0bea1-223">The names of the **Name** , **Expression** , **Option** , and **Command** parameters are optional.</span></span> <span data-ttu-id="0bea1-224">如果省略参数名称，则未命名参数值必须按以下顺序出现：Name  、Expression  、Option  或 Name  、Command  、Option  。</span><span class="sxs-lookup"><span data-stu-id="0bea1-224">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name** , **Expression** , **Option** or **Name** , **Command** , **Option** .</span></span> <span data-ttu-id="0bea1-225">如果包括参数名称，则参数能够以任何顺序出现。</span><span class="sxs-lookup"><span data-stu-id="0bea1-225">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="0bea1-226">相关链接</span><span class="sxs-lookup"><span data-stu-id="0bea1-226">RELATED LINKS</span></span>

[<span data-ttu-id="0bea1-227">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="0bea1-227">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="0bea1-228">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="0bea1-228">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="0bea1-229">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="0bea1-229">Set-TraceSource</span></span>](Set-TraceSource.md)

