---
description: 介绍 PowerShell 调试器。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: c53229752a26428ff4bc47fd5cecf039bdef7275
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200403"
---
# <a name="about-debuggers"></a><span data-ttu-id="1e732-104">关于调试器</span><span class="sxs-lookup"><span data-stu-id="1e732-104">About Debuggers</span></span>

## <a name="short-description"></a><span data-ttu-id="1e732-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="1e732-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1e732-106">介绍 PowerShell 调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-106">Describes the PowerShell debugger.</span></span>

## <a name="long-description"></a><span data-ttu-id="1e732-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="1e732-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1e732-108">调试是检查正在运行的脚本的过程，用于识别和更正脚本指令中的错误。</span><span class="sxs-lookup"><span data-stu-id="1e732-108">Debugging is the process of examining a script while it is running to identify and correct errors in the script instructions.</span></span> <span data-ttu-id="1e732-109">PowerShell 调试器可帮助你检查和确定脚本、函数、命令、PowerShell Desired State Configuration (DSC) 配置或表达式中的错误和低效。</span><span class="sxs-lookup"><span data-stu-id="1e732-109">The PowerShell debugger can help you examine and identify errors and inefficiencies in your scripts, functions, commands, PowerShell Desired State Configuration (DSC) configurations, or expressions.</span></span>

<span data-ttu-id="1e732-110">从 PowerShell 5.0 开始，已更新 PowerShell 调试器，以调试在远程计算机上的控制台或 Windows PowerShell ISE 中运行的脚本、函数、命令、配置或表达式。</span><span class="sxs-lookup"><span data-stu-id="1e732-110">Starting in PowerShell 5.0, the PowerShell debugger has been updated to debug scripts, functions, commands, configurations, or expressions that are running in either the console or Windows PowerShell ISE on remote computers.</span></span> <span data-ttu-id="1e732-111">您可以运行 `Enter-PSSession` 以启动交互式远程 PowerShell 会话，在该会话中，您可以在远程计算机上设置断点以及调试脚本文件和命令。</span><span class="sxs-lookup"><span data-stu-id="1e732-111">You can run `Enter-PSSession` to start an interactive remote PowerShell session in which you can set breakpoints and debug script files and commands on the remote computer.</span></span> <span data-ttu-id="1e732-112">`Enter-PSSession` 已更新功能，使你可以重新连接到并进入远程计算机上运行脚本或命令的断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="1e732-112">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running a script or command on a remote computer.</span></span> <span data-ttu-id="1e732-113">如果正在运行的脚本命中了断点，则客户端会话会自动启动调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-113">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span> <span data-ttu-id="1e732-114">如果运行脚本的断开连接的会话已命中断点，并在断点处停止， `Enter-PSSession` 则在重新连接到该会话之后，将自动启动命令行调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-114">If the disconnected session that is running a script has already hit a breakpoint, and is stopped at the breakpoint, `Enter-PSSession` automatically starts the command-line debugger, after you reconnect to the session.</span></span>

<span data-ttu-id="1e732-115">使用 PowerShell 调试器的功能，可以在 PowerShell 脚本、函数、命令或表达式运行时对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="1e732-115">You can use the features of the PowerShell debugger to examine a PowerShell script, function, command, or expression while it is running.</span></span> <span data-ttu-id="1e732-116">PowerShell 调试器包含一组 cmdlet，可用于设置断点、管理断点和查看调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1e732-116">The PowerShell debugger includes a set of cmdlets that let you set breakpoints, manage breakpoints, and view the call stack.</span></span>

## <a name="debugger-cmdlets"></a><span data-ttu-id="1e732-117">调试器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1e732-117">Debugger Cmdlets</span></span>

<span data-ttu-id="1e732-118">PowerShell 调试器包含以下 cmdlet 集：</span><span class="sxs-lookup"><span data-stu-id="1e732-118">The PowerShell debugger includes the following set of cmdlets:</span></span>

- <span data-ttu-id="1e732-119">`Set-PSBreakpoint`：对行、变量和命令设置断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-119">`Set-PSBreakpoint`: Sets breakpoints on lines, variables, and commands.</span></span>
- <span data-ttu-id="1e732-120">`Get-PSBreakpoint`：获取当前会话中的断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-120">`Get-PSBreakpoint`: Gets breakpoints in the current session.</span></span>
- <span data-ttu-id="1e732-121">`Disable-PSBreakpoint`：关闭当前会话中的断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-121">`Disable-PSBreakpoint`: Turns off breakpoints in the current session.</span></span>
- <span data-ttu-id="1e732-122">`Enable-PSBreakpoint`：在当前会话中重新启用断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-122">`Enable-PSBreakpoint`: Re-enables breakpoints in the current session.</span></span>
- <span data-ttu-id="1e732-123">`Remove-PSBreakpoint`：从当前会话中删除断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-123">`Remove-PSBreakpoint`: Deletes breakpoints from the current session.</span></span>
- <span data-ttu-id="1e732-124">`Get-PSCallStack`：显示当前的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1e732-124">`Get-PSCallStack`: Displays the current call stack.</span></span>

## <a name="starting-and-stopping-the-debugger"></a><span data-ttu-id="1e732-125">启动和停止调试器</span><span class="sxs-lookup"><span data-stu-id="1e732-125">Starting and Stopping the Debugger</span></span>

<span data-ttu-id="1e732-126">若要启动调试器，请设置一个或多个断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-126">To start the debugger, set one or more breakpoints.</span></span> <span data-ttu-id="1e732-127">然后，运行要调试的脚本、命令或函数。</span><span class="sxs-lookup"><span data-stu-id="1e732-127">Then, run the script, command, or function that you want to debug.</span></span>

<span data-ttu-id="1e732-128">到达断点时，将停止执行，并将控制权转变成调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-128">When you reach a breakpoint, execution stops, and control is turned over to the debugger.</span></span>

<span data-ttu-id="1e732-129">若要停止调试器，请运行脚本、命令或函数，直到完成。</span><span class="sxs-lookup"><span data-stu-id="1e732-129">To stop the debugger, run the script, command, or function until it is complete.</span></span> <span data-ttu-id="1e732-130">或者，键入 `stop` 或 `t` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-130">Or, type `stop` or `t`.</span></span>

### <a name="debugger-commands"></a><span data-ttu-id="1e732-131">调试器命令</span><span class="sxs-lookup"><span data-stu-id="1e732-131">Debugger Commands</span></span>

<span data-ttu-id="1e732-132">在 PowerShell 控制台中使用调试程序时，请使用以下命令来控制执行。</span><span class="sxs-lookup"><span data-stu-id="1e732-132">When you use the debugger in the PowerShell console, use the following commands to control the execution.</span></span> <span data-ttu-id="1e732-133">在 Windows PowerShell ISE 中，使用 "调试" 菜单上的命令。</span><span class="sxs-lookup"><span data-stu-id="1e732-133">In Windows PowerShell ISE, use commands on the Debug menu.</span></span>

<span data-ttu-id="1e732-134">注意：有关如何在其他宿主应用程序中使用调试器的信息，请参阅宿主应用程序文档。</span><span class="sxs-lookup"><span data-stu-id="1e732-134">Note: For information about how to use the debugger in other host applications, see the host application documentation.</span></span>

- <span data-ttu-id="1e732-135">`s`， `StepInto` ：执行下一个语句，然后停止。</span><span class="sxs-lookup"><span data-stu-id="1e732-135">`s`, `StepInto`: Executes the next statement and then stops.</span></span>

- <span data-ttu-id="1e732-136">`v`， `StepOver` ：执行下一语句，但跳过函数和调用。</span><span class="sxs-lookup"><span data-stu-id="1e732-136">`v`, `StepOver`: Executes the next statement, but skips functions and invocations.</span></span> <span data-ttu-id="1e732-137">将执行跳过的语句，但不会单步遍历。</span><span class="sxs-lookup"><span data-stu-id="1e732-137">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="1e732-138">`Ctrl+Break`： (将 ISE 中的所有项全部中断) 在 PowerShell 控制台内进入正在运行的脚本，或者 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="1e732-138">`Ctrl+Break`: (Break All in ISE) Breaks into a running script within either the PowerShell console, or Windows PowerShell ISE.</span></span> <span data-ttu-id="1e732-139">请注意<kbd>Ctrl</kbd>， + 在 Windows PowerShell 2.0、3.0 和4.0 中的 Ctrl<kbd>Break</kbd>会关闭程序。</span><span class="sxs-lookup"><span data-stu-id="1e732-139">Note that <kbd>Ctrl</kbd>+<kbd>Break</kbd> in Windows PowerShell 2.0, 3.0, and 4.0 closes the program.</span></span> <span data-ttu-id="1e732-140">全部中断都适用于本地和远程运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-140">Break All works on both local and remote interactively-running scripts.</span></span>

- <span data-ttu-id="1e732-141">`o`， `StepOut` ：跳出当前函数; 如果嵌套，则为一级。</span><span class="sxs-lookup"><span data-stu-id="1e732-141">`o`, `StepOut`: Steps out of the current function; up one level if nested.</span></span> <span data-ttu-id="1e732-142">如果在主体中，它将继续到末尾或下一个断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-142">If in the main body, it continues to the end or the next breakpoint.</span></span> <span data-ttu-id="1e732-143">将执行跳过的语句，但不会单步遍历。</span><span class="sxs-lookup"><span data-stu-id="1e732-143">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="1e732-144">`c``Continue`：将继续运行，直到脚本完成，或者到达下一个断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-144">`c`, `Continue`: Continues to run until the script is complete or until the next breakpoint is reached.</span></span> <span data-ttu-id="1e732-145">将执行跳过的语句，但不会单步遍历。</span><span class="sxs-lookup"><span data-stu-id="1e732-145">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="1e732-146">`l``List`：显示正在执行的脚本部分。</span><span class="sxs-lookup"><span data-stu-id="1e732-146">`l`, `List`: Displays the part of the script that is executing.</span></span> <span data-ttu-id="1e732-147">默认情况下，它显示当前行、前面的五行和10个后续行。</span><span class="sxs-lookup"><span data-stu-id="1e732-147">By default, it displays the current line, five previous lines, and 10 subsequent lines.</span></span>
  <span data-ttu-id="1e732-148">若要继续列出脚本，请按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="1e732-148">To continue listing the script, press ENTER.</span></span>

- <span data-ttu-id="1e732-149">`l <m>``List`：显示以指定的行号开头的16行脚本 `<m>` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-149">`l <m>`, `List`: Displays 16 lines of the script beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="1e732-150">`l <m> <n>``List`：显示 `<n>` 脚本的行，以指定的行号开头 `<m>` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-150">`l <m> <n>`, `List`: Displays `<n>` lines of the script, beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="1e732-151">`q`、 `Stop` 、 `Exit` ：停止执行脚本，并退出调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-151">`q`, `Stop`, `Exit`: Stops executing the script, and exits the debugger.</span></span> <span data-ttu-id="1e732-152">如果正在通过运行 cmdlet 调试作业 `Debug-Job` ，则该命令将 `Exit` 分离调试器，并允许作业继续运行。</span><span class="sxs-lookup"><span data-stu-id="1e732-152">If you are debugging a job by running the `Debug-Job` cmdlet, the `Exit` command detaches the debugger, and allows the job to continue running.</span></span>

- <span data-ttu-id="1e732-153">`k``Get-PsCallStack`：显示当前调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1e732-153">`k`, `Get-PsCallStack`: Displays the current call stack.</span></span>

- <span data-ttu-id="1e732-154">`<Enter>`：如果为 Step (s) 、跨距 (v) 或 List (l) ，则重复最后一个命令。</span><span class="sxs-lookup"><span data-stu-id="1e732-154">`<Enter>`: Repeats the last command if it was Step (s), StepOver (v), or List (l).</span></span> <span data-ttu-id="1e732-155">否则，表示提交操作。</span><span class="sxs-lookup"><span data-stu-id="1e732-155">Otherwise, represents a submit action.</span></span>

- <span data-ttu-id="1e732-156">`?``h`：显示调试器命令帮助。</span><span class="sxs-lookup"><span data-stu-id="1e732-156">`?`, `h`: Displays the debugger command Help.</span></span>

<span data-ttu-id="1e732-157">若要退出调试器，可以使用 Stop (q) 。</span><span class="sxs-lookup"><span data-stu-id="1e732-157">To exit the debugger, you can use Stop (q).</span></span>

<span data-ttu-id="1e732-158">从 PowerShell 5.0 开始，可以运行 Exit 命令，以退出通过运行或启动的嵌套调试会话 `Debug-Job` `Debug-Runspace` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-158">Starting in PowerShell 5.0, you can run the Exit command to exit a nested debugging session that you started by running either `Debug-Job` or `Debug-Runspace`.</span></span>

<span data-ttu-id="1e732-159">通过使用这些调试程序命令，你可以运行脚本，在关注点时停止，检查变量的值和系统状态，然后继续运行脚本，直到发现问题为止。</span><span class="sxs-lookup"><span data-stu-id="1e732-159">By using these debugger commands, you can run a script, stop on a point of concern, examine the values of variables and the state of the system, and continue running the script until you have identified a problem.</span></span>

<span data-ttu-id="1e732-160">注意：如果单步执行包含重定向运算符（如 ">"）的语句，则 PowerShell 调试器会逐过程执行该脚本中的所有剩余语句。</span><span class="sxs-lookup"><span data-stu-id="1e732-160">NOTE: If you step into a statement with a redirection operator, such as ">", the PowerShell debugger steps over all remaining statements in the script.</span></span>

<span data-ttu-id="1e732-161">显示脚本变量的值</span><span class="sxs-lookup"><span data-stu-id="1e732-161">Displaying the Values of script Variables</span></span>

<span data-ttu-id="1e732-162">在调试器中时，还可以在命令行中输入命令、显示变量值、使用 cmdlet 和运行脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-162">While you are in the debugger, you can also enter commands, display the value of variables, use cmdlets, and run scripts at the command line.</span></span>

<span data-ttu-id="1e732-163">除了以下自动变量以外，你还可以在正在调试的脚本中显示所有变量的当前值：</span><span class="sxs-lookup"><span data-stu-id="1e732-163">You can display the current value of all variables in the script that is being debugged, except for the following automatic variables:</span></span>

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

<span data-ttu-id="1e732-164">如果你尝试显示这些变量中的任何一个的值，你将获取调试器使用的内部管道中变量的值，而不是脚本中变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e732-164">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span>

<span data-ttu-id="1e732-165">若要为正在调试的脚本显示这些变量的值，请在脚本中，将自动变量的值分配给一个新变量。</span><span class="sxs-lookup"><span data-stu-id="1e732-165">To display the value these variables for the script that is being debugged, in the script, assign the value of the automatic variable to a new variable.</span></span> <span data-ttu-id="1e732-166">然后，可以显示新变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e732-166">Then you can display the value of the new variable.</span></span>

<span data-ttu-id="1e732-167">例如，</span><span class="sxs-lookup"><span data-stu-id="1e732-167">For example,</span></span>

```powershell
$scriptArgs = $Args
$scriptArgs
```

<span data-ttu-id="1e732-168">在本主题的示例中，变量的值 `$MyInvocation` 是重新分配的，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e732-168">In the example in this topic, the value of the `$MyInvocation` variable is reassigned as follows:</span></span>

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a><span data-ttu-id="1e732-169">调试器环境</span><span class="sxs-lookup"><span data-stu-id="1e732-169">The Debugger Environment</span></span>

<span data-ttu-id="1e732-170">到达断点时，将进入调试器环境。</span><span class="sxs-lookup"><span data-stu-id="1e732-170">When you reach a breakpoint, you enter the debugger environment.</span></span> <span data-ttu-id="1e732-171">命令提示符将发生更改，使其以 "[DBG]：" 开头。</span><span class="sxs-lookup"><span data-stu-id="1e732-171">The command prompt changes so that it begins with "[DBG]:".</span></span>

<span data-ttu-id="1e732-172">有关自定义提示的详细信息，请参阅 [about_Prompts](about_prompts.md)。</span><span class="sxs-lookup"><span data-stu-id="1e732-172">For more information about customizing the prompt, see [about_Prompts](about_prompts.md).</span></span>

<span data-ttu-id="1e732-173">此外，在某些主机应用程序（例如 PowerShell 控制台）中， (但不在 Windows PowerShell 集成脚本环境 [ISE] ) 中，会打开一个嵌套提示来进行调试。</span><span class="sxs-lookup"><span data-stu-id="1e732-173">Also, in some host applications, such as the PowerShell console, (but not in Windows PowerShell Integrated Scripting Environment [ISE]), a nested prompt opens for debugging.</span></span> <span data-ttu-id="1e732-174">您可以通过在命令提示符下出现 (ASCII 62) 的重复大于字符来检测嵌套提示。</span><span class="sxs-lookup"><span data-stu-id="1e732-174">You can detect the nested prompt by the repeating greater-than characters (ASCII 62) that appear at the command prompt.</span></span>

<span data-ttu-id="1e732-175">例如，以下是 PowerShell 控制台中的默认调试提示：</span><span class="sxs-lookup"><span data-stu-id="1e732-175">For example, the following is the default debugging prompt in the PowerShell console:</span></span>

```
[DBG]: PS (get-location)>>>
```

<span data-ttu-id="1e732-176">您可以通过使用自动变量来查找嵌套级别 `$NestedPromptLevel` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-176">You can find the nesting level by using the `$NestedPromptLevel` automatic variable.</span></span>

<span data-ttu-id="1e732-177">此外，自动变量 `$PSDebugContext` 在本地范围中定义。</span><span class="sxs-lookup"><span data-stu-id="1e732-177">Additionally, an automatic variable, `$PSDebugContext`, is defined in the local scope.</span></span> <span data-ttu-id="1e732-178">您可以使用变量的状态 `$PsDebugContext` 来确定是否在调试器中。</span><span class="sxs-lookup"><span data-stu-id="1e732-178">You can use the presence of the `$PsDebugContext` variable to determine whether you are in the debugger.</span></span>

<span data-ttu-id="1e732-179">例如：</span><span class="sxs-lookup"><span data-stu-id="1e732-179">For example:</span></span>

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

<span data-ttu-id="1e732-180">您可以 `$PSDebugContext` 在调试中使用变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e732-180">You can use the value of the `$PSDebugContext` variable in your debugging.</span></span>

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a><span data-ttu-id="1e732-181">调试和作用域</span><span class="sxs-lookup"><span data-stu-id="1e732-181">Debugging and Scope</span></span>

<span data-ttu-id="1e732-182">中断调试器不会更改您在其中运行的范围，但当您在脚本中到达断点时，将移动到脚本范围。</span><span class="sxs-lookup"><span data-stu-id="1e732-182">Breaking into the debugger does not change the scope in which you are operating, but when you reach a breakpoint in a script, you move into the script scope.</span></span> <span data-ttu-id="1e732-183">脚本作用域是运行调试器的作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="1e732-183">The script scope is a child of the scope in which you ran the debugger.</span></span>

<span data-ttu-id="1e732-184">若要查找在脚本作用域中定义的变量和别名，请使用或 cmdlet 的作用域参数 `Get-Alias` `Get-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-184">To find the variables and aliases that are defined in the script scope, use the Scope parameter of the `Get-Alias` or `Get-Variable` cmdlets.</span></span>

<span data-ttu-id="1e732-185">例如，以下命令将获取本地 (脚本) 范围中的变量：</span><span class="sxs-lookup"><span data-stu-id="1e732-185">For example, the following command gets the variables in the local (script) scope:</span></span>

```powershell
Get-Variable -scope 0
```

<span data-ttu-id="1e732-186">可以将命令缩写为：</span><span class="sxs-lookup"><span data-stu-id="1e732-186">You can abbreviate the command as:</span></span>

```powershell
gv -s 0
```

<span data-ttu-id="1e732-187">这是一种非常有用的方法，用于仅查看您在脚本中定义的变量以及在调试时定义的变量。</span><span class="sxs-lookup"><span data-stu-id="1e732-187">This is a useful way to see only the variables that you defined in the script and that you defined while debugging.</span></span>

<span data-ttu-id="1e732-188">在命令行调试</span><span class="sxs-lookup"><span data-stu-id="1e732-188">Debugging at the Command Line</span></span>

<span data-ttu-id="1e732-189">设置变量断点或命令断点时，只能在脚本文件中设置断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-189">When you set a variable breakpoint or a command breakpoint, you can set the breakpoint only in a script file.</span></span> <span data-ttu-id="1e732-190">但是，默认情况下，将在当前会话中运行的任何内容上设置断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-190">However, by default, the breakpoint is set on anything that runs in the current session.</span></span>

<span data-ttu-id="1e732-191">例如，如果您在变量上设置了断点 `$name` ，则调试器将在 `$name` 您禁用或删除断点之前运行的任何脚本、命令、函数、脚本 cmdlet 或表达式中的任何变量上中断。</span><span class="sxs-lookup"><span data-stu-id="1e732-191">For example, if you set a breakpoint on the `$name` variable, the debugger breaks on any `$name` variable in any script, command, function, script cmdlet or expression that you run until you disable or remove the breakpoint.</span></span>

<span data-ttu-id="1e732-192">这使您可以在一个更现实的上下文中调试脚本，这些脚本可能会受到会话中和用户配置文件中的函数、变量和其他脚本的影响。</span><span class="sxs-lookup"><span data-stu-id="1e732-192">This allows you to debug your scripts in a more realistic context in which they might be affected by functions, variables, and other scripts in the session and in the user's profile.</span></span>

<span data-ttu-id="1e732-193">行断点特定于脚本文件，因此它们只在脚本文件中进行设置。</span><span class="sxs-lookup"><span data-stu-id="1e732-193">Line breakpoints are specific to script files, so they are set only in script files.</span></span>

## <a name="debugging-functions"></a><span data-ttu-id="1e732-194">调试函数</span><span class="sxs-lookup"><span data-stu-id="1e732-194">Debugging Functions</span></span>

<span data-ttu-id="1e732-195">在具有、和部分的函数上设置断点 `Begin` 时 `Process` `End` ，调试器会在每个部分的第一行处中断。</span><span class="sxs-lookup"><span data-stu-id="1e732-195">When you set a breakpoint on a function that has `Begin`, `Process`, and `End` sections, the debugger breaks at the first line of each section.</span></span>

<span data-ttu-id="1e732-196">例如：</span><span class="sxs-lookup"><span data-stu-id="1e732-196">For example:</span></span>

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a><span data-ttu-id="1e732-197">调试远程脚本</span><span class="sxs-lookup"><span data-stu-id="1e732-197">Debugging Remote Scripts</span></span>

<span data-ttu-id="1e732-198">从 PowerShell 5.0 开始，你可以在远程会话、控制台或 Windows PowerShell ISE 中运行 PowerShell 调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-198">Starting in PowerShell 5.0, you can run the PowerShell debugger in a remote session, in either the console, or Windows PowerShell ISE.</span></span>
<span data-ttu-id="1e732-199">`Enter-PSSession` 已更新功能，使你可以重新连接到并输入远程计算机上运行的断开连接的会话，并且当前正在运行脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-199">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running on a remote computer, and currently running a script.</span></span> <span data-ttu-id="1e732-200">如果正在运行的脚本命中了断点，则客户端会话会自动启动调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-200">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span>

<span data-ttu-id="1e732-201">下面是一个示例，演示了如何工作，并在脚本的第6、11、22和25行中设置了断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-201">The following is an example that shows how this works, with breakpoints set in a script at lines 6, 11, 22, and 25.</span></span> <span data-ttu-id="1e732-202">请注意，在该示例中，当调试器启动时，有两个标识提示：正在运行会话的计算机的名称，以及可让您了解处于调试模式的 DBG 提示。</span><span class="sxs-lookup"><span data-stu-id="1e732-202">Note that in the example, when the debugger starts, there are two identifying prompts: the name of the computer on which the session is running, and the DBG prompt that lets you know you are in debugging mode.</span></span>

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a><span data-ttu-id="1e732-203">示例</span><span class="sxs-lookup"><span data-stu-id="1e732-203">Examples</span></span>

<span data-ttu-id="1e732-204">此测试脚本检测操作系统的版本，并显示系统相应的消息。</span><span class="sxs-lookup"><span data-stu-id="1e732-204">This test script detects the version of the operating system and displays a system-appropriate message.</span></span> <span data-ttu-id="1e732-205">它包括函数、函数调用和变量。</span><span class="sxs-lookup"><span data-stu-id="1e732-205">It includes a function, a function call, and a variable.</span></span>

<span data-ttu-id="1e732-206">以下命令显示测试脚本文件的内容：</span><span class="sxs-lookup"><span data-stu-id="1e732-206">The following command displays the contents of the test script file:</span></span>

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

<span data-ttu-id="1e732-207">若要开始，请在脚本中的相关点设置断点，例如行、命令、变量或函数。</span><span class="sxs-lookup"><span data-stu-id="1e732-207">To start, set a breakpoint at a point of interest in the script, such as a line, command, variable, or function.</span></span>

<span data-ttu-id="1e732-208">首先在当前目录中 Test.ps1 脚本的第一行上创建行断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-208">Start by creating a line breakpoint on the first line of the Test.ps1 script in the current directory.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

<span data-ttu-id="1e732-209">可将此命令缩写为：</span><span class="sxs-lookup"><span data-stu-id="1e732-209">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

<span data-ttu-id="1e732-210">命令返回 ( **system.management.automation.linebreakpoint** ) 的行断点对象。</span><span class="sxs-lookup"><span data-stu-id="1e732-210">The command returns a line-breakpoint object ( **System.Management.Automation.LineBreakpoint** ).</span></span>

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

<span data-ttu-id="1e732-211">现在，启动脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-211">Now, start the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
```

<span data-ttu-id="1e732-212">当脚本到达第一个断点时，断点消息指示调试器处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1e732-212">When the script reaches the first breakpoint, the breakpoint message indicates that the debugger is active.</span></span> <span data-ttu-id="1e732-213">它描述断点并预览脚本的第一行（即函数声明）。</span><span class="sxs-lookup"><span data-stu-id="1e732-213">It describes the breakpoint and previews the first line of the script, which is a function declaration.</span></span> <span data-ttu-id="1e732-214">命令提示符还会发生更改，以指示调试器具有控制。</span><span class="sxs-lookup"><span data-stu-id="1e732-214">The command prompt also changes to indicate that the debugger has control.</span></span>

<span data-ttu-id="1e732-215">预览行包括脚本名称和预览命令的行号。</span><span class="sxs-lookup"><span data-stu-id="1e732-215">The preview line includes the script name and the line number of the previewed command.</span></span>

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

<span data-ttu-id="1e732-216">使用 Step 命令 (s) 执行脚本中的第一条语句并预览下一条语句。</span><span class="sxs-lookup"><span data-stu-id="1e732-216">Use the Step command (s) to execute the first statement in the script and to preview the next statement.</span></span> <span data-ttu-id="1e732-217">下一条语句使用 `$MyInvocation` 自动变量将该变量的值设置 `$scriptName` 为该脚本文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="1e732-217">The next statement uses the `$MyInvocation` automatic variable to set the value of the `$scriptName` variable to the path and file name of the script file.</span></span>

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

<span data-ttu-id="1e732-218">此时， `$scriptName` 不会填充变量，但可以通过显示变量值来验证变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e732-218">At this point, the `$scriptName` variable is not populated, but you can verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="1e732-219">在本例中，该值为 `$null`。</span><span class="sxs-lookup"><span data-stu-id="1e732-219">In this case, the value is `$null`.</span></span>

```powershell
DBG> $scriptname
# DBG>
```

<span data-ttu-id="1e732-220">使用另一个步骤命令 (s) 执行当前语句并预览脚本中的下一个语句。</span><span class="sxs-lookup"><span data-stu-id="1e732-220">Use another Step command (s) to execute the current statement and to preview the next statement in the script.</span></span> <span data-ttu-id="1e732-221">下一条语句将调用 PsVersion 函数。</span><span class="sxs-lookup"><span data-stu-id="1e732-221">The next statement calls the PsVersion function.</span></span>

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="1e732-222">此时，将 `$scriptName` 填充变量，但通过显示变量值来验证变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e732-222">At this point, the `$scriptName` variable is populated, but you verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="1e732-223">在这种情况下，值设置为脚本路径。</span><span class="sxs-lookup"><span data-stu-id="1e732-223">In this case, the value is set to the script path.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

<span data-ttu-id="1e732-224">使用另一个步骤命令执行函数调用。</span><span class="sxs-lookup"><span data-stu-id="1e732-224">Use another Step command to execute the function call.</span></span> <span data-ttu-id="1e732-225">按 ENTER，或键入 "s" 进行步骤。</span><span class="sxs-lookup"><span data-stu-id="1e732-225">Press ENTER, or type "s" for Step.</span></span>

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

<span data-ttu-id="1e732-226">调试消息包括函数中语句的预览。</span><span class="sxs-lookup"><span data-stu-id="1e732-226">The debug message includes a preview of the statement in the function.</span></span> <span data-ttu-id="1e732-227">若要执行此语句并预览函数中的下一条语句，可以使用 `Step` 命令。</span><span class="sxs-lookup"><span data-stu-id="1e732-227">To execute this statement and to preview the next statement in the function, you can use a `Step` command.</span></span> <span data-ttu-id="1e732-228">但在这种情况下，请使用 (o) 的 StepOut 命令。</span><span class="sxs-lookup"><span data-stu-id="1e732-228">But, in this case, use a StepOut command (o).</span></span> <span data-ttu-id="1e732-229">它将完成函数的执行 (除非该函数到达断点) 并执行该脚本中的下一条语句。</span><span class="sxs-lookup"><span data-stu-id="1e732-229">It completes the execution of the function (unless it reaches a breakpoint) and steps to the next statement in the script.</span></span>

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="1e732-230">由于我们在脚本中的最后一个语句上，因此 "Step"、"StepOut" 和 "Continue" 命令具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="1e732-230">Because we are on the last statement in the script, the Step, StepOut, and Continue commands have the same effect.</span></span> <span data-ttu-id="1e732-231">在这种情况下，请使用 StepOut (o) 。</span><span class="sxs-lookup"><span data-stu-id="1e732-231">In this case, use StepOut (o).</span></span>

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

<span data-ttu-id="1e732-232">StepOut 命令执行最后一个命令。</span><span class="sxs-lookup"><span data-stu-id="1e732-232">The StepOut command executes the last command.</span></span> <span data-ttu-id="1e732-233">标准命令提示符指示调试器已退出并返回到命令处理器。</span><span class="sxs-lookup"><span data-stu-id="1e732-233">The standard command prompt indicates that the debugger has exited and returned control to the command processor.</span></span>

<span data-ttu-id="1e732-234">现在，再次运行调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-234">Now, run the debugger again.</span></span> <span data-ttu-id="1e732-235">首先，若要删除当前断点，请使用 `Get-PsBreakpoint` 和 `Remove-PsBreakpoint` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e732-235">First, to delete the current breakpoint, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span> <span data-ttu-id="1e732-236"> (如果你认为可能重复使用该断点，则使用 `Disable-PsBreakpoint` cmdlet 而不是 `Remove-PsBreakpoint` 。 ) </span><span class="sxs-lookup"><span data-stu-id="1e732-236">(If you think you might reuse the breakpoint, use the `Disable-PsBreakpoint` cmdlet instead of `Remove-PsBreakpoint`.)</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="1e732-237">可将此命令缩写为：</span><span class="sxs-lookup"><span data-stu-id="1e732-237">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> gbp | rbp
```

<span data-ttu-id="1e732-238">或者，通过编写函数来运行命令，如以下函数：</span><span class="sxs-lookup"><span data-stu-id="1e732-238">Or, run the command by writing a function, such as the following function:</span></span>

```powershell
function delbr { gbp | rbp }
```

<span data-ttu-id="1e732-239">现在，请在变量上创建断点 `$scriptname` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-239">Now, create a breakpoint on the `$scriptname` variable.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

<span data-ttu-id="1e732-240">可以将命令缩写为：</span><span class="sxs-lookup"><span data-stu-id="1e732-240">You can abbreviate the command as:</span></span>

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

<span data-ttu-id="1e732-241">现在，启动脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-241">Now, start the script.</span></span> <span data-ttu-id="1e732-242">脚本将到达变量断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-242">The script reaches the variable breakpoint.</span></span> <span data-ttu-id="1e732-243">默认模式是 "写入"，因此，在更改变量的值的语句之前，执行将停止。</span><span class="sxs-lookup"><span data-stu-id="1e732-243">The default mode is Write, so execution stops just before the statement that changes the value of the variable.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

<span data-ttu-id="1e732-244">显示变量的当前值 `$scriptName` ，即 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-244">Display the current value of the `$scriptName` variable, which is `$null`.</span></span>

```powershell
DBG> $scriptName
# DBG>
```

<span data-ttu-id="1e732-245">使用步骤命令 (s) 执行填充变量的语句。</span><span class="sxs-lookup"><span data-stu-id="1e732-245">Use a Step command (s) to execute the statement that populates the variable.</span></span>
<span data-ttu-id="1e732-246">然后，显示变量的新值 `$scriptName` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-246">Then, display the new value of the `$scriptName` variable.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="1e732-247">下一条语句是对 PsVersion 函数的调用。</span><span class="sxs-lookup"><span data-stu-id="1e732-247">The next statement is a call to the PsVersion function.</span></span> <span data-ttu-id="1e732-248">若要跳过函数但仍执行该函数，请使用跨距命令 (v) 。</span><span class="sxs-lookup"><span data-stu-id="1e732-248">To skip the function but still execute it, use a StepOver command (v).</span></span> <span data-ttu-id="1e732-249">如果使用跨距时已在该函数中，则无效。</span><span class="sxs-lookup"><span data-stu-id="1e732-249">If you are already in the function when you use StepOver, it is not effective.</span></span> <span data-ttu-id="1e732-250">将显示函数调用，但不执行它。</span><span class="sxs-lookup"><span data-stu-id="1e732-250">The function call is displayed, but it is not executed.</span></span>

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="1e732-251">跨距命令执行该函数，并预览脚本中的下一条语句，该语句将输出最后一行。</span><span class="sxs-lookup"><span data-stu-id="1e732-251">The StepOver command executes the function, and it previews the next statement in the script, which prints the final line.</span></span>

<span data-ttu-id="1e732-252">使用 Stop 命令 (t) 退出调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-252">Use a Stop command (t) to exit the debugger.</span></span> <span data-ttu-id="1e732-253">命令提示符会恢复为标准命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1e732-253">The command prompt reverts to the standard command prompt.</span></span>

```powershell
C:\ps-test>
```

<span data-ttu-id="1e732-254">若要删除断点，请使用 `Get-PsBreakpoint` 和 `Remove-PsBreakpoint` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e732-254">To delete the breakpoints, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="1e732-255">在 PsVersion 函数上创建新的命令断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-255">Create a new command breakpoint on the PsVersion function.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

<span data-ttu-id="1e732-256">可以将此命令缩写为：</span><span class="sxs-lookup"><span data-stu-id="1e732-256">You can abbreviate this command to:</span></span>

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

<span data-ttu-id="1e732-257">现在，运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-257">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

<span data-ttu-id="1e732-258">脚本在函数调用时到达断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-258">The script reaches the breakpoint at the function call.</span></span> <span data-ttu-id="1e732-259">此时，尚未调用函数。</span><span class="sxs-lookup"><span data-stu-id="1e732-259">At this point, the function has not yet been called.</span></span> <span data-ttu-id="1e732-260">这使您有机会使用的操作参数 `Set-PSBreakpoint` 设置断点的执行条件，或执行准备或诊断任务，如启动日志或调用诊断或安全脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-260">This gives you the opportunity to use the Action parameter of `Set-PSBreakpoint` to set conditions for the execution of the breakpoint or to perform preparatory or diagnostic tasks, such as starting a log or invoking a diagnostic or security script.</span></span>

<span data-ttu-id="1e732-261">若要设置操作，请使用 Continue 命令 (c) 退出脚本，并使用 `Remove-PsBreakpoint` 命令删除当前断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-261">To set an action, use a Continue command (c) to exit the script, and a `Remove-PsBreakpoint` command to delete the current breakpoint.</span></span> <span data-ttu-id="1e732-262"> (断点是只读的，因此无法将操作添加到当前断点。 ) </span><span class="sxs-lookup"><span data-stu-id="1e732-262">(Breakpoints are read-only, so you cannot add an action to the current breakpoint.)</span></span>

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

<span data-ttu-id="1e732-263">现在，使用操作创建新的命令断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-263">Now, create a new command breakpoint with an action.</span></span> <span data-ttu-id="1e732-264">下面的命令使用 `$scriptName` 在调用函数时记录变量值的操作设置命令断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-264">The following command sets a command breakpoint with an action that logs the value of the `$scriptName` variable when the function is called.</span></span> <span data-ttu-id="1e732-265">由于操作中未使用 Break 关键字，因此执行不会停止。</span><span class="sxs-lookup"><span data-stu-id="1e732-265">Because the Break keyword is not used in the action, execution does not stop.</span></span> <span data-ttu-id="1e732-266"> (反撇号 (') 为行继续符。 ) </span><span class="sxs-lookup"><span data-stu-id="1e732-266">(The backtick (\`) is the line-continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

<span data-ttu-id="1e732-267">你还可以添加为断点设置条件的操作。</span><span class="sxs-lookup"><span data-stu-id="1e732-267">You can also add actions that set conditions for the breakpoint.</span></span> <span data-ttu-id="1e732-268">在下面的命令中，仅当执行策略设置为 RemoteSigned （仍允许运行脚本的最严格的策略）时，才执行命令断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-268">In the following command, the command breakpoint is executed only if the execution policy is set to RemoteSigned, the most restrictive policy that still permits you to run scripts.</span></span> <span data-ttu-id="1e732-269"> (反撇号 (") 是继续符。 ) </span><span class="sxs-lookup"><span data-stu-id="1e732-269">(The backtick (\`) is the continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

<span data-ttu-id="1e732-270">操作中的 Break 关键字指示调试器执行断点。</span><span class="sxs-lookup"><span data-stu-id="1e732-270">The Break keyword in the action directs the debugger to execute the breakpoint.</span></span>
<span data-ttu-id="1e732-271">你还可以使用 Continue 关键字指示调试器无中断地执行。</span><span class="sxs-lookup"><span data-stu-id="1e732-271">You can also use the Continue keyword to direct the debugger to execute without breaking.</span></span> <span data-ttu-id="1e732-272">由于 default 关键字为 Continue，因此必须指定 Break 来停止执行。</span><span class="sxs-lookup"><span data-stu-id="1e732-272">Because the default keyword is Continue, you must specify Break to stop execution.</span></span>

<span data-ttu-id="1e732-273">现在，运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="1e732-273">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

<span data-ttu-id="1e732-274">由于执行策略设置为 **RemoteSigned** ，因此会在函数调用处停止执行。</span><span class="sxs-lookup"><span data-stu-id="1e732-274">Because the execution policy is set to **RemoteSigned** , execution stops at the function call.</span></span>

<span data-ttu-id="1e732-275">此时，你可能需要检查调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1e732-275">At this point, you might want to check the call stack.</span></span> <span data-ttu-id="1e732-276">使用 `Get-PsCallStack` cmdlet 或 `Get-PsCallStack` 调试器命令 (k) 。</span><span class="sxs-lookup"><span data-stu-id="1e732-276">Use the `Get-PsCallStack` cmdlet or the `Get-PsCallStack` debugger command (k).</span></span> <span data-ttu-id="1e732-277">以下命令将获取当前调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1e732-277">The following command gets the current call stack.</span></span>

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

<span data-ttu-id="1e732-278">此示例演示了使用 PowerShell 调试器的多种方法中的几种方法。</span><span class="sxs-lookup"><span data-stu-id="1e732-278">This example demonstrates just a few of the many ways to use the PowerShell debugger.</span></span>

<span data-ttu-id="1e732-279">有关调试器 cmdlet 的详细信息，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="1e732-279">For more information about the debugger cmdlets, type the following command:</span></span>

```powershell
help <cmdlet-name> -full
```

<span data-ttu-id="1e732-280">例如，键入：</span><span class="sxs-lookup"><span data-stu-id="1e732-280">For example, type:</span></span>

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a><span data-ttu-id="1e732-281">PowerShell 中的其他调试功能</span><span class="sxs-lookup"><span data-stu-id="1e732-281">Other Debugging Features in PowerShell</span></span>

<span data-ttu-id="1e732-282">除了 PowerShell 调试程序外，PowerShell 还包括可用于调试脚本和函数的多个其他功能。</span><span class="sxs-lookup"><span data-stu-id="1e732-282">In addition to the PowerShell debugger, PowerShell includes several other features that you can use to debug scripts and functions.</span></span>

- <span data-ttu-id="1e732-283">Windows PowerShell ISE 包含交互式图形调试器。</span><span class="sxs-lookup"><span data-stu-id="1e732-283">Windows PowerShell ISE includes an interactive graphical debugger.</span></span> <span data-ttu-id="1e732-284">有关详细信息，请启动 Windows PowerShell ISE 并按 F1。</span><span class="sxs-lookup"><span data-stu-id="1e732-284">For more information, start Windows PowerShell ISE and press F1.</span></span>

- <span data-ttu-id="1e732-285">`Set-PSDebug`Cmdlet 提供了非常基本的脚本调试功能，包括单步执行和跟踪。</span><span class="sxs-lookup"><span data-stu-id="1e732-285">The `Set-PSDebug` cmdlet offers very basic script debugging features, including stepping and tracing.</span></span>

- <span data-ttu-id="1e732-286">使用 `Set-StrictMode` cmdlet 来检测对未初始化的变量的引用、对对象的不存在属性的引用以及函数无效的语法。</span><span class="sxs-lookup"><span data-stu-id="1e732-286">Use the `Set-StrictMode` cmdlet to detect references to uninitialized variables, to references to non-existent properties of an object, and to function syntax that is not valid.</span></span>

- <span data-ttu-id="1e732-287">将诊断语句添加到脚本，例如显示变量值的语句、从命令行读取输入的语句或报告当前说明的语句。</span><span class="sxs-lookup"><span data-stu-id="1e732-287">Add diagnostic statements to a script, such as statements that display the value of variables, statements that read input from the command line, or statements that report the current instruction.</span></span> <span data-ttu-id="1e732-288">使用包含此任务的写入谓词的 cmdlet，例如 `Write-Host` 、、 `Write-Debug` `Write-Warning` 和 `Write-Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="1e732-288">Use the cmdlets that contain the Write verb for this task, such as `Write-Host`, `Write-Debug`, `Write-Warning`, and `Write-Verbose`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e732-289">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e732-289">SEE ALSO</span></span>

- [<span data-ttu-id="1e732-290">Set-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="1e732-290">Disable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [<span data-ttu-id="1e732-291">Set-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="1e732-291">Enable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [<span data-ttu-id="1e732-292">Set-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="1e732-292">Get-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [<span data-ttu-id="1e732-293">Get-pscallstack</span><span class="sxs-lookup"><span data-stu-id="1e732-293">Get-PsCallStack</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [<span data-ttu-id="1e732-294">Set-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="1e732-294">Remove-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [<span data-ttu-id="1e732-295">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1e732-295">Set-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [<span data-ttu-id="1e732-296">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="1e732-296">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="1e732-297">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="1e732-297">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
