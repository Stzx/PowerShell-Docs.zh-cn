---
description: 描述存储 PowerShell 的状态信息的变量。 这些变量由 PowerShell 创建和维护。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: e7525ad8acd6dd5aa2dc65a8d49d03c1c6260bea
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199621"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="b9b9d-105">关于自动变量</span><span class="sxs-lookup"><span data-stu-id="b9b9d-105">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="b9b9d-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="b9b9d-106">Short description</span></span>

<span data-ttu-id="b9b9d-107">描述存储 PowerShell 的状态信息的变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-107">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="b9b9d-108">这些变量由 PowerShell 创建和维护。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-108">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b9b9d-109">长说明</span><span class="sxs-lookup"><span data-stu-id="b9b9d-109">Long description</span></span>

<span data-ttu-id="b9b9d-110">从概念上讲，这些变量被视为只读。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-110">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="b9b9d-111">即使 **可** 将它们写入到中，但 **不应** 将其写入到后向兼容性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-111">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="b9b9d-112">下面是 PowerShell 中自动变量的列表：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-112">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="b9b9d-113">包含会话收到的最后一行中的最后一个标记。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-113">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="b9b9d-114">$?</span><span class="sxs-lookup"><span data-stu-id="b9b9d-114">$?</span></span>

<span data-ttu-id="b9b9d-115">包含最后一个命令的执行状态。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-115">Contains the execution status of the last command.</span></span> <span data-ttu-id="b9b9d-116">如果最后一个命令成功，则 **为 True;** 否则为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-116">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="b9b9d-117">对于在管道中的多个阶段（例如在和块中）运行的 cmdlet 和高级函数，在 `process` `end` `this.WriteError()` 任何点调用或分别调用或 `$PSCmdlet.WriteError()` 分别将设置 `$?` 为 **False** ，就像 `this.ThrowTerminatingError()` 和 `$PSCmdlet.ThrowTerminatingError()` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-117">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False** , as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="b9b9d-118">`Write-Error`Cmdlet 始终在 `$?` 执行后立即设置为 **false** ，但不会 `$?` 对调用它的函数设置为 **false** ：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-118">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="b9b9d-119">对于后一种用途， `$PSCmdlet.WriteError()` 应改为使用。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-119">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="b9b9d-120">对于 (可执行文件) 的本机命令， `$?` 当为0时，将设置为 **True** `$LASTEXITCODE` ，如果 **False** `$LASTEXITCODE` 为任何其他值，则设置为 False。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-120">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b9d-121">在 PowerShell 7 中，在括号内包含语句后 `(...)` ，子表达式语法 `$(...)` 或数组表达式 `@(...)` 始终重置 `$?` 为 **True** ，因此 `(Write-Error)` 显示 `$?` 为 **true** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-121">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True** , so that `(Write-Error)` shows `$?` as **True** .</span></span>
> <span data-ttu-id="b9b9d-122">此操作在 PowerShell 7 中已更改，因此 `$?` 将始终反映在这些表达式中运行的最后一个命令的实际成功。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-122">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="b9b9d-123">包含会话收到的最后一行中的第一个标记。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-123">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="b9b9d-124">$_</span><span class="sxs-lookup"><span data-stu-id="b9b9d-124">$_</span></span>

<span data-ttu-id="b9b9d-125">与 `$PSItem` 相同。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-125">Same as `$PSItem`.</span></span> <span data-ttu-id="b9b9d-126">包含管道对象中的当前对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-126">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="b9b9d-127">可以在对每个对象或管道中的选定对象执行操作的命令中使用此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-127">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="b9b9d-128">$args</span><span class="sxs-lookup"><span data-stu-id="b9b9d-128">$args</span></span>

<span data-ttu-id="b9b9d-129">包含传递给函数、脚本或脚本块的未声明参数的值数组。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-129">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="b9b9d-130">创建函数时，可以使用 `param` 关键字或在函数名称后的括号中添加以逗号分隔的参数列表，来声明参数。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-130">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="b9b9d-131">在事件操作中， `$Args` 变量包含表示正在处理的事件的事件参数的对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-131">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="b9b9d-132">仅在 `Action` 事件注册命令块内填充此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-132">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="b9b9d-133">此变量的值还可在返回的 **PSEventArgs** 对象的 **SourceArgs** 属性中找到 `Get-Event` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-133">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="b9b9d-134">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="b9b9d-134">$ConsoleFileName</span></span>

<span data-ttu-id="b9b9d-135">包含 `.psc1` 会话中最近使用的控制台文件 () 的路径。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-135">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="b9b9d-136">使用 **PSConsoleFile** 参数启动 PowerShell 或使用 `Export-Console` cmdlet 将管理单元名称导出到控制台文件时，将填充此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-136">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="b9b9d-137">使用 `Export-Console` 不带参数的 cmdlet 时，它会自动更新会话中最近使用的控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-137">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="b9b9d-138">您可以使用此自动变量来确定将更新哪个文件。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-138">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="b9b9d-139">$Error</span><span class="sxs-lookup"><span data-stu-id="b9b9d-139">$Error</span></span>

<span data-ttu-id="b9b9d-140">包含错误对象的数组，这些对象表示最近的错误。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-140">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="b9b9d-141">最近的错误是数组中第一个错误对象 `$Error[0]` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-141">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="b9b9d-142">若要防止将错误添加到 `$Error` 数组，请使用值为 **Ignore** 的 **ErrorAction** 通用参数。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-142">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore** .</span></span> <span data-ttu-id="b9b9d-143">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-143">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="b9b9d-144">$Event</span><span class="sxs-lookup"><span data-stu-id="b9b9d-144">$Event</span></span>

<span data-ttu-id="b9b9d-145">包含表示正在处理的事件的 **PSEventArgs** 对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-145">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="b9b9d-146">此变量仅在 `Action` 事件注册命令块中填充，例如 `Register-ObjectEvent` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-146">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="b9b9d-147">此变量的值与 cmdlet 返回的对象相同 `Get-Event` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-147">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="b9b9d-148">因此，可以 `Event` `$Event.TimeGenerated` 在脚本块中使用该变量的属性，例如 `Action` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-148">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="b9b9d-149">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="b9b9d-149">$EventArgs</span></span>

<span data-ttu-id="b9b9d-150">包含一个对象，该对象表示从正在处理的事件的 **EventArgs** 派生的第一个事件参数。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-150">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="b9b9d-151">仅在 `Action` 事件注册命令块内填充此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-151">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="b9b9d-152">此变量的值还可在返回的 **PSEventArgs** 对象的 **SourceEventArgs** 属性中找到 `Get-Event` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-152">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="b9b9d-153">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="b9b9d-153">$EventSubscriber</span></span>

<span data-ttu-id="b9b9d-154">包含一个 **PSEventSubscriber** 对象，该对象表示正在处理的事件的事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-154">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="b9b9d-155">仅在 `Action` 事件注册命令块内填充此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-155">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="b9b9d-156">此变量的值与 cmdlet 返回的对象相同 `Get-EventSubscriber` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-156">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="b9b9d-157">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="b9b9d-157">$ExecutionContext</span></span>

<span data-ttu-id="b9b9d-158">包含一个 **EngineIntrinsics** 对象，该对象表示 PowerShell 主机的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-158">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="b9b9d-159">您可以使用此变量来查找可用于 cmdlet 的执行对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-159">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="b9b9d-160">$false</span><span class="sxs-lookup"><span data-stu-id="b9b9d-160">$false</span></span>

<span data-ttu-id="b9b9d-161">包含 **False** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-161">Contains **False** .</span></span> <span data-ttu-id="b9b9d-162">可以在命令和脚本中使用此变量来表示 **False** ，而不是使用字符串 "False"。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-162">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="b9b9d-163">如果字符串被转换为非空字符串或非零整数，则可以将该字符串解释为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-163">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="b9b9d-164">$foreach</span><span class="sxs-lookup"><span data-stu-id="b9b9d-164">$foreach</span></span>

<span data-ttu-id="b9b9d-165">包含枚举器 (不是 [ForEach](about_ForEach.md) 循环) 的结果值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-165">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="b9b9d-166">此 `$ForEach` 变量仅在 `ForEach` 循环运行时存在; 在循环完成后将其删除。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-166">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="b9b9d-167">枚举器包含可用于检索循环值和更改当前循环迭代的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-167">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="b9b9d-168">有关详细信息，请参阅 [使用枚举](#using-enumerators)器。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-168">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="b9b9d-169">$HOME</span><span class="sxs-lookup"><span data-stu-id="b9b9d-169">$HOME</span></span>

<span data-ttu-id="b9b9d-170">包含用户的主目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-170">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="b9b9d-171">通常，此变量等效于 `"$env:homedrive$env:homepath"` Windows 环境变量 `C:\Users\<UserName>` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-171">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="b9b9d-172">$Host</span><span class="sxs-lookup"><span data-stu-id="b9b9d-172">$Host</span></span>

<span data-ttu-id="b9b9d-173">包含表示 PowerShell 的当前主机应用程序的对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-173">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="b9b9d-174">您可以使用此变量来表示命令中的当前宿主，或者显示或更改主机的属性，例如 `$Host.version` 或 `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-174">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="b9b9d-175">$input</span><span class="sxs-lookup"><span data-stu-id="b9b9d-175">$input</span></span>

<span data-ttu-id="b9b9d-176">包含枚举传递到函数的所有输入的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-176">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="b9b9d-177">此 `$input` 变量仅适用于) 为未命名函数 (函数和脚本块。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-177">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="b9b9d-178">在没有 `Begin` 、或块的函数中 `Process` `End` ， `$input` 变量枚举函数的所有输入的集合。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-178">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="b9b9d-179">在 `Begin` 块中， `$input` 变量不包含任何数据。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-179">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="b9b9d-180">在 `Process` 块中， `$input` 变量包含管道中当前的对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-180">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="b9b9d-181">在 `End` 块中， `$input` 变量枚举函数的所有输入的集合。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-181">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b9b9d-182">不能 `$input` 在同一函数或脚本块中的进程块和结束块中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-182">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="b9b9d-183">由于 `$input` 是一个枚举器，因此访问它的任何属性都将导致 `$input` 不再可用。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-183">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="b9b9d-184">可以 `$input` 在另一个变量中存储以重用 `$input` 属性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-184">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="b9b9d-185">枚举器包含可用于检索循环值和更改当前循环迭代的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-185">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="b9b9d-186">有关详细信息，请参阅 [使用枚举](#using-enumerators)器。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-186">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="iscoreclr"></a><span data-ttu-id="b9b9d-187">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="b9b9d-187">$IsCoreCLR</span></span>

<span data-ttu-id="b9b9d-188">包含 `$True` 当前会话是否在 .Net Core 运行时上运行 (CoreCLR) 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-188">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="b9b9d-189">否则包含 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-189">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="b9b9d-190">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="b9b9d-190">$IsLinux</span></span>

<span data-ttu-id="b9b9d-191">包含 `$True` 当前会话是否在 Linux 操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-191">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="b9b9d-192">否则包含 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-192">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="b9b9d-193">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="b9b9d-193">$IsMacOS</span></span>

<span data-ttu-id="b9b9d-194">包含 `$True` 当前会话是否在 MacOS 操作系统上运行的。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-194">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="b9b9d-195">否则包含 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-195">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="b9b9d-196">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="b9b9d-196">$IsWindows</span></span>

<span data-ttu-id="b9b9d-197">`$TRUE`如果当前会话正在 Windows 操作系统上运行，则包含。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-197">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="b9b9d-198">否则包含 `$FALSE` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-198">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="b9b9d-199">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="b9b9d-199">$LastExitCode</span></span>

<span data-ttu-id="b9b9d-200">包含上一次运行的基于 Windows 的程序的退出代码。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-200">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="b9b9d-201">$Matches</span><span class="sxs-lookup"><span data-stu-id="b9b9d-201">$Matches</span></span>

<span data-ttu-id="b9b9d-202">`Matches`变量与 `-match` and 运算符一起使用 `-notmatch` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-202">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="b9b9d-203">当你将标量输入提交给 `-match` or `-notmatch` 运算符，并且其中一个检测到匹配时，它们将返回一个布尔值，并 `$Matches` 使用匹配的任何字符串值的哈希表填充自动变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-203">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="b9b9d-204">在 `$Matches` 将正则表达式用于运算符时，还可以使用捕获来填充哈希表 `-match` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-204">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="b9b9d-205">有关运算符的详细信息 `-match` ，请参阅 [about_Comparison_Operators](about_comparison_operators.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-205">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="b9b9d-206">有关正则表达式的详细信息，请参阅 [about_Regular_Expressions](about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-206">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="b9b9d-207">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="b9b9d-207">$MyInvocation</span></span>

<span data-ttu-id="b9b9d-208">包含有关当前命令的信息，如名称、参数、参数值和有关如何启动、调用或调用命令的信息，例如调用当前命令的脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-208">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="b9b9d-209">`$MyInvocation` 仅填充脚本、函数和脚本块。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-209">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="b9b9d-210">您可以使用在当前脚本中返回的 **InvocationInfo** 对象中的信息 `$MyInvocation` ，例如脚本 () 的路径和文件名， `$MyInvocation.MyCommand.Path` 或函数的名称 (`$MyInvocation.MyCommand.Name`) 以标识当前命令。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-210">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="b9b9d-211">这对于查找当前脚本的名称特别有用。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-211">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="b9b9d-212">从 PowerShell 3.0 开始， `MyInvocation` 具有以下新属性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-212">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="b9b9d-213">属性</span><span class="sxs-lookup"><span data-stu-id="b9b9d-213">Property</span></span>      | <span data-ttu-id="b9b9d-214">说明</span><span class="sxs-lookup"><span data-stu-id="b9b9d-214">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="b9b9d-215">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-215">**PSScriptRoot**</span></span>  | <span data-ttu-id="b9b9d-216">包含调用的脚本的完整路径</span><span class="sxs-lookup"><span data-stu-id="b9b9d-216">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="b9b9d-217">当前命令。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-217">the current command.</span></span> <span data-ttu-id="b9b9d-218">此属性的值为</span><span class="sxs-lookup"><span data-stu-id="b9b9d-218">The value of this property is</span></span>  |
|               | <span data-ttu-id="b9b9d-219">仅当调用方为脚本时才填充。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-219">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="b9b9d-220">**PSCommandPath**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-220">**PSCommandPath**</span></span> | <span data-ttu-id="b9b9d-221">包含脚本的完整路径和文件名</span><span class="sxs-lookup"><span data-stu-id="b9b9d-221">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="b9b9d-222">调用当前命令的。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-222">that invoked the current command.</span></span> <span data-ttu-id="b9b9d-223">此的值</span><span class="sxs-lookup"><span data-stu-id="b9b9d-223">The value of this</span></span> |
|               | <span data-ttu-id="b9b9d-224">仅当调用方是</span><span class="sxs-lookup"><span data-stu-id="b9b9d-224">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="b9b9d-225">脚本。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-225">script.</span></span>                                             |

<span data-ttu-id="b9b9d-226">与自动变量不同 `$PSScriptRoot` `$PSCommandPath` ，自动变量的 **PSScriptRoot** 和 **PSCommandPath** 属性 `$MyInvocation` 包含有关调用程序或调用脚本的信息，而不是当前脚本。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-226">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="b9b9d-227">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="b9b9d-227">$NestedPromptLevel</span></span>

<span data-ttu-id="b9b9d-228">包含当前提示符级别。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-228">Contains the current prompt level.</span></span> <span data-ttu-id="b9b9d-229">值0表示原始提示级别。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-229">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="b9b9d-230">当您输入嵌套级别时，该值会递增，并且在您退出时将递增。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-230">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="b9b9d-231">例如，使用方法时，PowerShell 会显示嵌套的命令提示符 `$Host.EnterNestedPrompt` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-231">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="b9b9d-232">当你到达 PowerShell 调试器中的断点时，PowerShell 还会显示嵌套的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-232">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="b9b9d-233">输入嵌套提示符时，PowerShell 将暂停当前命令，保存执行上下文，并递增变量的值 `$NestedPromptLevel` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-233">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="b9b9d-234">若要创建其他嵌套的命令提示 (最多128级别) 或返回到原始命令提示符，请完成命令或键入 `exit` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-234">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="b9b9d-235">`$NestedPromptLevel`变量有助于跟踪提示级别。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-235">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="b9b9d-236">你可以创建一个包含此值的备用 PowerShell 命令提示符，以使其始终可见。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-236">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="b9b9d-237">$null</span><span class="sxs-lookup"><span data-stu-id="b9b9d-237">$null</span></span>

<span data-ttu-id="b9b9d-238">`$null` 是包含 **null** 值或空值的自动变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-238">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="b9b9d-239">您可以使用此变量来表示命令和脚本中缺少的值或未定义的值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-239">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="b9b9d-240">PowerShell 将视为 `$null` 具有值的对象（即，作为显式占位符），因此可以使用 `$null` 来表示一系列值中的空值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-240">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="b9b9d-241">例如，当 `$null` 包含在集合中时，会将其计为一个对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-241">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="b9b9d-242">如果通过管道将 `$null` 变量传递给 `ForEach-Object` cmdlet，它会为生成一个值 `$null` ，就像对其他对象执行此方法一样。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-242">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="b9b9d-243">因此，不能使用 `$null` 来表示 **没有参数值** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-243">As a result, you can't use `$null` to mean **no parameter value** .</span></span> <span data-ttu-id="b9b9d-244">参数值 `$null` 覆盖默认参数值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-244">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="b9b9d-245">但是，因为 PowerShell 将 `$null` 变量视为占位符，所以可以在脚本中使用它，如果忽略，这将不起作用 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-245">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

```powershell
$calendar = @($null, $null, "Meeting", $null, $null, "Team Lunch", $null)
$days = "Sunday","Monday","Tuesday","Wednesday","Thursday",
        "Friday","Saturday"
$currentDay = 0
foreach($day in $calendar)
{
    if($day -ne $null)
    {
        "Appointment on $($days[$currentDay]): $day"
    }

    $currentDay++
}
```

```Output
Appointment on Tuesday: Meeting
Appointment on Friday: Team lunch
```

### <a name="pid"></a><span data-ttu-id="b9b9d-246">$PID</span><span class="sxs-lookup"><span data-stu-id="b9b9d-246">$PID</span></span>

<span data-ttu-id="b9b9d-247">包含承载当前 PowerShell 会话的进程的进程标识符 (PID) 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-247">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="b9b9d-248">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="b9b9d-248">$PROFILE</span></span>

<span data-ttu-id="b9b9d-249">包含当前用户和当前主机应用程序的 PowerShell 配置文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-249">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="b9b9d-250">您可以使用此变量来表示命令中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-250">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="b9b9d-251">例如，你可以在命令中使用它来确定是否已创建配置文件：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-251">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="b9b9d-252">或者，你可以在命令中使用它来创建配置文件：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-252">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="b9b9d-253">可以在命令中使用它在 **notepad.exe** 中打开配置文件：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-253">You can use it in a command to open the profile in **notepad.exe** :</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="b9b9d-254">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="b9b9d-254">$PSBoundParameters</span></span>

<span data-ttu-id="b9b9d-255">包含传递给脚本或函数的参数的字典及其当前值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-255">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="b9b9d-256">此变量仅在声明参数的作用域（如脚本或函数）中具有值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-256">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="b9b9d-257">您可以使用它显示或更改参数的当前值，或者将参数值传递给其他脚本或函数。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-257">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="b9b9d-258">在此示例中， **Test2** 函数将传递 `$PSBoundParameters` 给 **Test1** 函数。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-258">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="b9b9d-259">`$PSBoundParameters`以 **键** 和 **值** 的格式显示。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-259">The `$PSBoundParameters` are displayed in the format of **Key** and **Value** .</span></span>

```powershell
function Test1 {
   param($a, $b)

   # Display the parameters in dictionary format.
   $PSBoundParameters
}

function Test2 {
   param($a, $b)

   # Run the Test1 function with $a and $b.
   Test1 @PSBoundParameters
}
```

```powershell
Test2 -a Power -b Shell
```

```Output
Key   Value
---   -----
a     Power
b     Shell
```

### <a name="pscmdlet"></a><span data-ttu-id="b9b9d-260">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="b9b9d-260">$PSCmdlet</span></span>

<span data-ttu-id="b9b9d-261">包含一个对象，该对象表示正在运行的 cmdlet 或高级函数。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-261">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="b9b9d-262">你可以使用 cmdlet 或函数代码中的对象的属性和方法来响应使用情况。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-262">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="b9b9d-263">例如， **ParameterSetName** 属性包含所使用的参数集的名称， **ShouldProcess** 方法会动态地将 **WhatIf** 和 **Confirm** 参数添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-263">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="b9b9d-264">有关自动变量的详细信息 `$PSCmdlet` ，请参阅 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) 和 [about_Functions_Advanced](about_Functions_Advanced.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-264">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="b9b9d-265">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="b9b9d-265">$PSCommandPath</span></span>

<span data-ttu-id="b9b9d-266">包含正在运行的脚本的完整路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-266">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="b9b9d-267">此变量在所有脚本中都有效。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-267">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="b9b9d-268">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="b9b9d-268">$PSCulture</span></span>

<span data-ttu-id="b9b9d-269">从 PowerShell 7 开始， `$PSCulture` 反映当前 PowerShell 运行空间的区域性 (会话) 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-269">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="b9b9d-270">如果在 PowerShell 运行空间中更改了区域性，则将 `$PSCulture` 更新该运行空间的值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-270">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="b9b9d-271">区域性确定项的显示格式（例如数字、货币和日期），并将其存储在 **system.exception 对象中。**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-271">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="b9b9d-272">用于 `Get-Culture` 显示计算机的区域性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-272">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="b9b9d-273">`$PSCulture` 包含 **名称** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-273">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="b9b9d-274">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="b9b9d-274">$PSDebugContext</span></span>

<span data-ttu-id="b9b9d-275">调试时，此变量包含有关调试环境的信息。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-275">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="b9b9d-276">否则，它将包含 **null** 值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-276">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="b9b9d-277">因此，你可以使用它来指示调试器是否具有控件。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-277">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="b9b9d-278">填充后，它将包含一个 **PsDebugContext** 对象，该对象具有 **断点** 和 **InvocationInfo** 属性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-278">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="b9b9d-279">**InvocationInfo** 属性具有多个有用的属性，包括 **Location** 属性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-279">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="b9b9d-280">**Location** 属性指示正在调试的脚本的路径。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-280">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="b9b9d-281">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="b9b9d-281">$PSHOME</span></span>

<span data-ttu-id="b9b9d-282">包含适用于 PowerShell 的安装目录的完整路径，通常是 `$env:windir\System32\PowerShell\v1.0` 在 Windows 系统中。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-282">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="b9b9d-283">可以在 PowerShell 文件的路径中使用此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-283">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="b9b9d-284">例如，下面的命令在概念帮助主题中搜索 word **变量** ：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-284">For example, the following command searches the conceptual Help topics for the word **variable** :</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="b9b9d-285">$PSItem</span><span class="sxs-lookup"><span data-stu-id="b9b9d-285">$PSItem</span></span>

<span data-ttu-id="b9b9d-286">与 `$_` 相同。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-286">Same as `$_`.</span></span> <span data-ttu-id="b9b9d-287">包含管道对象中的当前对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-287">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="b9b9d-288">可以在对每个对象或管道中的选定对象执行操作的命令中使用此变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-288">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="b9b9d-289">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="b9b9d-289">$PSScriptRoot</span></span>

<span data-ttu-id="b9b9d-290">包含正在从中运行脚本的目录。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-290">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="b9b9d-291">在 PowerShell 2.0 中，此变量仅在) 的脚本模块中有效 (`.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-291">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="b9b9d-292">从 PowerShell 3.0 开始，它在所有脚本中都有效。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-292">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="b9b9d-293">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="b9b9d-293">$PSSenderInfo</span></span>

<span data-ttu-id="b9b9d-294">包含有关启动 PSSession 的用户的信息，其中包括源计算机的用户标识和时区。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-294">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="b9b9d-295">此变量仅在 Pssession 中可用。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-295">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="b9b9d-296">此 `$PSSenderInfo` 变量包含一个用户可配置的属性 **ApplicationArguments** ，默认情况下，该属性仅包含 `$PSVersionTable` 来自原始会话的。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-296">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments** , that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="b9b9d-297">若要将数据添加到 **ApplicationArguments** 属性，请使用 Cmdlet 的 **ApplicationArguments** 参数 `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-297">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="b9b9d-298">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="b9b9d-298">$PSUICulture</span></span>

<span data-ttu-id="b9b9d-299">包含操作系统中当前正在使用的 (UI) 区域性的用户界面的名称。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-299">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="b9b9d-300">UI 区域性确定哪些文本字符串用于用户界面元素，例如菜单和消息。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-300">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="b9b9d-301">这是系统的 **System.Globalization.CultureInfo.CurrentUICulture.Name** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-301">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="b9b9d-302">若要获取 **系统的 system.servicemodel 对象，** 请使用 `Get-UICulture` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-302">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="b9b9d-303">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="b9b9d-303">$PSVersionTable</span></span>

<span data-ttu-id="b9b9d-304">包含一个只读的哈希表，该表显示有关当前会话中正在运行的 PowerShell 版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-304">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="b9b9d-305">该表包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="b9b9d-305">The table includes the following items:</span></span>

| <span data-ttu-id="b9b9d-306">属性</span><span class="sxs-lookup"><span data-stu-id="b9b9d-306">Property</span></span>                  | <span data-ttu-id="b9b9d-307">说明</span><span class="sxs-lookup"><span data-stu-id="b9b9d-307">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="b9b9d-308">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-308">**PSVersion**</span></span>             | <span data-ttu-id="b9b9d-309">PowerShell 版本号</span><span class="sxs-lookup"><span data-stu-id="b9b9d-309">The PowerShell version number</span></span>                 |
| <span data-ttu-id="b9b9d-310">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-310">**PSEdition**</span></span>             | <span data-ttu-id="b9b9d-311">此属性的值为 "Desktop"</span><span class="sxs-lookup"><span data-stu-id="b9b9d-311">This property has the value of 'Desktop' for</span></span>  |
|                           | <span data-ttu-id="b9b9d-312">PowerShell 4 及更低</span><span class="sxs-lookup"><span data-stu-id="b9b9d-312">PowerShell 4 and below as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="b9b9d-313">5.1 功能齐全的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-313">5.1 on full-featured Windows editions.</span></span>        |
|                           | <span data-ttu-id="b9b9d-314">此属性的值为 "Core"</span><span class="sxs-lookup"><span data-stu-id="b9b9d-314">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="b9b9d-315">PowerShell 6 及更高版本以及 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9b9d-315">PowerShell 6 and above as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="b9b9d-316">精简版的小型版本上的 PowerShell 5。1</span><span class="sxs-lookup"><span data-stu-id="b9b9d-316">PowerShell 5.1 on reduced-footprint editions</span></span>  |
|                           | <span data-ttu-id="b9b9d-317">类似于 Windows Nano Server 或 Windows IoT。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-317">like Windows Nano Server or Windows IoT.</span></span>      |
| <span data-ttu-id="b9b9d-318">**GitCommitId**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-318">**GitCommitId**</span></span>           | <span data-ttu-id="b9b9d-319">GitHub 中的源文件的提交 Id</span><span class="sxs-lookup"><span data-stu-id="b9b9d-319">The commit Id of the source files, in GitHub,</span></span> |
| <span data-ttu-id="b9b9d-320">**OS**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-320">**OS**</span></span>                    | <span data-ttu-id="b9b9d-321">操作系统的说明</span><span class="sxs-lookup"><span data-stu-id="b9b9d-321">Description of the operating system that</span></span>      |
|                           | <span data-ttu-id="b9b9d-322">PowerShell 正在上运行。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-322">PowerShell is running on.</span></span>                     |
| <span data-ttu-id="b9b9d-323">**平台**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-323">**Platform**</span></span>              | <span data-ttu-id="b9b9d-324">操作系统正在运行的平台</span><span class="sxs-lookup"><span data-stu-id="b9b9d-324">Platform that the operating system is running</span></span> |
|                           | <span data-ttu-id="b9b9d-325">如果</span><span class="sxs-lookup"><span data-stu-id="b9b9d-325">on.</span></span> <span data-ttu-id="b9b9d-326">Linux 和 macOS 上的值为 **Unix** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-326">The value on Linux and macOS is **Unix** .</span></span> |
|                           | <span data-ttu-id="b9b9d-327">请参见 `$IsMacOs` 和 `$IsLinux`。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-327">See `$IsMacOs` and `$IsLinux`.</span></span>                |
| <span data-ttu-id="b9b9d-328">**PSCompatibleVersions**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-328">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="b9b9d-329">兼容的 PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="b9b9d-329">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="b9b9d-330">与当前版本</span><span class="sxs-lookup"><span data-stu-id="b9b9d-330">with the current version</span></span>                      |
| <span data-ttu-id="b9b9d-331">**PSRemotingProtocolVersion**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-331">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="b9b9d-332">PowerShell 远程的版本</span><span class="sxs-lookup"><span data-stu-id="b9b9d-332">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="b9b9d-333">管理协议。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-333">management protocol.</span></span>                          |
| <span data-ttu-id="b9b9d-334">**SerializationVersion**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-334">**SerializationVersion**</span></span>  | <span data-ttu-id="b9b9d-335">序列化方法的版本</span><span class="sxs-lookup"><span data-stu-id="b9b9d-335">The version of the serialization method</span></span>       |
| <span data-ttu-id="b9b9d-336">**WSManStackVersion**</span><span class="sxs-lookup"><span data-stu-id="b9b9d-336">**WSManStackVersion**</span></span>     | <span data-ttu-id="b9b9d-337">WS-Management 堆栈的版本号</span><span class="sxs-lookup"><span data-stu-id="b9b9d-337">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="b9b9d-338">$PWD</span><span class="sxs-lookup"><span data-stu-id="b9b9d-338">$PWD</span></span>

<span data-ttu-id="b9b9d-339">包含表示当前目录的完整路径的路径对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-339">Contains a path object that represents the full path of the current directory.</span></span>

### <a name="sender"></a><span data-ttu-id="b9b9d-340">$Sender</span><span class="sxs-lookup"><span data-stu-id="b9b9d-340">$Sender</span></span>

<span data-ttu-id="b9b9d-341">包含生成此事件的对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-341">Contains the object that generated this event.</span></span> <span data-ttu-id="b9b9d-342">此变量仅在事件注册命令的操作块中进行填充。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-342">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="b9b9d-343">此变量的值还可在返回的 **PSEventArgs** 对象的发送方属性中找到 `Get-Event` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-343">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="b9b9d-344">$ShellId</span><span class="sxs-lookup"><span data-stu-id="b9b9d-344">$ShellId</span></span>

<span data-ttu-id="b9b9d-345">包含当前 shell 的标识符。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-345">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="b9b9d-346">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="b9b9d-346">$StackTrace</span></span>

<span data-ttu-id="b9b9d-347">包含最新错误的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-347">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="b9b9d-348">$switch</span><span class="sxs-lookup"><span data-stu-id="b9b9d-348">$switch</span></span>

<span data-ttu-id="b9b9d-349">包含枚举器，而不包含语句的结果值 `Switch` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-349">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="b9b9d-350">`$switch`仅当语句正在运行时，才存在该变量 `Switch` ; 当语句完成执行时，该变量会被删除 `switch` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-350">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="b9b9d-351">有关详细信息，请参阅 [about_Switch](about_Switch.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-351">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="b9b9d-352">枚举器包含可用于检索循环值和更改当前循环迭代的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-352">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="b9b9d-353">有关详细信息，请参阅 [使用枚举](#using-enumerators)器。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-353">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="b9b9d-354">$this</span><span class="sxs-lookup"><span data-stu-id="b9b9d-354">$this</span></span>

<span data-ttu-id="b9b9d-355">在定义脚本属性或脚本方法的脚本块中， `$this` 变量引用要扩展的对象。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-355">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="b9b9d-356">在自定义类中， `$this` 变量引用类对象本身，以允许访问类中定义的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-356">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="b9b9d-357">$true</span><span class="sxs-lookup"><span data-stu-id="b9b9d-357">$true</span></span>

<span data-ttu-id="b9b9d-358">包含 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-358">Contains **True** .</span></span> <span data-ttu-id="b9b9d-359">可以在命令和脚本中使用此变量来表示 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-359">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="b9b9d-360">使用枚举器</span><span class="sxs-lookup"><span data-stu-id="b9b9d-360">Using Enumerators</span></span>

<span data-ttu-id="b9b9d-361">`$input`、 `$foreach` 和 `$switch` 变量是所有枚举器，用于循环访问由其包含代码块处理的值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-361">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="b9b9d-362">枚举器包含可用于提前或重置迭代或检索迭代值的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-362">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="b9b9d-363">直接操作枚举器并不是最佳做法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-363">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="b9b9d-364">在循环中，应首选流控制关键字 " [中断](about_Break.md) 并 [继续](about_Continue.md) "。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-364">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="b9b9d-365">在接受管道输入的函数中，最佳做法是将参数与 **ValueFromPipeline** 或 **ValueFromPipelineByPropertyName** 属性结合使用。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-365">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="b9b9d-366">有关详细信息，请参阅 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-366">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="b9b9d-367">MoveNext</span><span class="sxs-lookup"><span data-stu-id="b9b9d-367">MoveNext</span></span>

<span data-ttu-id="b9b9d-368">[MoveNext](/dotnet/api/system.collections.ienumerator.movenext)方法将枚举器推进到集合的下一个元素。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-368">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="b9b9d-369">如果枚举器已成功进行高级，则 **MoveNext** 返回 **True** ; 如果枚举数已越过集合的末尾，则返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-369">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b9d-370">返回的 **布尔** 值会将我的 **MoveNext** 发送到输出流。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-370">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="b9b9d-371">可以通过将输出 typecasting 为 `[void]` 或将其传送到 [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null)来禁止输出。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-371">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="b9b9d-372">重置</span><span class="sxs-lookup"><span data-stu-id="b9b9d-372">Reset</span></span>

<span data-ttu-id="b9b9d-373">[Reset](/dotnet/api/system.collections.ienumerator.reset)方法将枚举器设置为其初始位置，该位置位于集合中第一个元素 **之前** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-373">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="b9b9d-374">当前</span><span class="sxs-lookup"><span data-stu-id="b9b9d-374">Current</span></span>

<span data-ttu-id="b9b9d-375">[当前](/dotnet/api/system.collections.ienumerator.current)属性获取集合中的元素或管道中的枚举器的当前位置。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-375">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="b9b9d-376">**当前** 属性将继续返回相同的属性，直到调用 **MoveNext** 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-376">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="b9b9d-377">示例</span><span class="sxs-lookup"><span data-stu-id="b9b9d-377">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="b9b9d-378">示例1：使用 $input 变量</span><span class="sxs-lookup"><span data-stu-id="b9b9d-378">Example 1: Using the $input variable</span></span>

<span data-ttu-id="b9b9d-379">在下面的示例中，访问 `$input` 变量将清除变量，直到下一次执行进程块。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-379">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="b9b9d-380">使用 **Reset** 方法会将变量重置 `$input` 为当前管道值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-380">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

```powershell
function Test
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tInput: $input"
        "`tAccess Again: $input"
        $input.Reset()
        "`tAfter Reset: $input"
    }
}

"one","two" | Test
```

```Output
Iteration: 0
    Input: one
    Access Again:
    After Reset: one
Iteration: 1
    Input: two
    Access Again:
    After Reset: two
```

<span data-ttu-id="b9b9d-381">即使不访问变量，进程块也会自动推进该 `$input` 变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-381">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

```powershell
$skip = $true
function Skip
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        if ($skip)
        {
            "`tSkipping"
            $skip = $false
        }
        else
        {
            "`tInput: $input"
        }
    }
}

"one","two" | Skip
```

```Output
Iteration: 0
    Skipping
Iteration: 1
    Input: two
```

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="b9b9d-382">示例2：在进程块外使用 $input</span><span class="sxs-lookup"><span data-stu-id="b9b9d-382">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="b9b9d-383">在进程块外，该 `$input` 变量表示通过管道传递到函数中的所有值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-383">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="b9b9d-384">访问 `$input` 变量将清除所有值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-384">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="b9b9d-385">**Reset** 方法重置整个集合。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-385">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="b9b9d-386">从未填充 **当前** 属性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-386">The **Current** property is never populated.</span></span>
- <span data-ttu-id="b9b9d-387">**MoveNext** 方法返回 false，因为集合不能为高级。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-387">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="b9b9d-388">调用 **MoveNext** 会清除该 `$input` 变量。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-388">Calling **MoveNext** clears out the `$input` variable.</span></span>

```powershell
Function All
{
    "All Values: $input"
    "Access Again: $input"
    $input.Reset()
    "After Reset: $input"
    $input.MoveNext() | Out-Null
    "After MoveNext: $input"
}

"one","two","three" | All
```

```Output
All Values: one two three
Access Again:
After Reset: one two three
After MoveNext:
```

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="b9b9d-389">示例3：使用 $input。当前属性</span><span class="sxs-lookup"><span data-stu-id="b9b9d-389">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="b9b9d-390">通过使用 **当前** 属性，可以多次访问当前管道值，而无需使用 **Reset** 方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-390">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="b9b9d-391">进程块不会自动调用 **MoveNext** 方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-391">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="b9b9d-392">除非显式调用 **MoveNext** ，否则不会填充 **当前** 属性。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-392">The **Current** property will never be populated unless you explicitly call **MoveNext** .</span></span> <span data-ttu-id="b9b9d-393">**当前** 属性可以在进程块内多次访问，而无需清除其值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-393">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

```powershell
function Current
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tBefore MoveNext: $($input.Current)"
        $input.MoveNext() | Out-Null
        "`tAfter MoveNext: $($input.Current)"
        "`tAccess Again: $($input.Current)"
    }
}

"one","two" | Current
```

```Output
Iteration: 0
    Before MoveNext:
    After MoveNext: one
    Access Again: one
Iteration: 1
    Before MoveNext:
    After MoveNext: two
    Access Again: two
```

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="b9b9d-394">示例4：使用 $foreach 变量</span><span class="sxs-lookup"><span data-stu-id="b9b9d-394">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="b9b9d-395">与 `$input` 变量不同，在 `$foreach` 直接访问时，变量始终表示集合中的所有项。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-395">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="b9b9d-396">使用 **current** 属性可以访问当前集合元素，使用 **Reset** 和 **MoveNext** 方法可以更改其值。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-396">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b9d-397">循环的每次迭代 `foreach` 都将自动调用 **MoveNext** 方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-397">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="b9b9d-398">以下循环只执行两次。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-398">The following loop only executes twice.</span></span> <span data-ttu-id="b9b9d-399">在第二次迭代中，在迭代完成之前，将集合移动到第三个元素。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-399">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="b9b9d-400">在第二次迭代后，现在没有更多值可供迭代，循环将终止。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-400">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="b9b9d-401">**MoveNext** 属性不影响所选择的用于循环访问集合的变量 (`$Num`) 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-401">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

```powershell
$i = 0
foreach ($num in ("one","two","three"))
{
    "Iteration: $i"
    $i++
    "`tNum: $num"
    "`tCurrent: $($foreach.Current)"

    if ($foreach.Current -eq "two")
    {
        "Before MoveNext (Current): $($foreach.Current)"
        $foreach.MoveNext() | Out-Null
        "After MoveNext (Current): $($foreach.Current)"
        "Num has not changed: $num"
    }
}
```

```Output
Iteration: 0
        Num: one
        Current: one
Iteration: 1
        Num: two
        Current: two
Before MoveNext (Current): two
After MoveNext (Current): three
Num has not changed: two
```

<span data-ttu-id="b9b9d-402">使用 **Reset** 方法重置集合中的当前元素。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-402">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="b9b9d-403">下面的示例循环遍历前两个元素 **两次** ，因为调用 **Reset** 方法。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-403">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="b9b9d-404">在前两个循环之后， `if` 语句将失败，并且循环会正常地循环访问所有三个元素。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-404">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9b9d-405">这可能会导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-405">This could result in an infinite loop.</span></span>

```powershell
$stopLoop = 0
foreach ($num in ("one","two", "three"))
{
    ("`t" * $stopLoop) + "Current: $($foreach.Current)"

    if ($num -eq "two" -and $stopLoop -lt 2)
    {
        $foreach.Reset() | Out-Null
        ("`t" * $stopLoop) + "Reset Loop: $stopLoop"
        $stopLoop++
    }
}
```

```Output
Current: one
Current: two
Reset Loop: 0
        Current: one
        Current: two
        Reset Loop: 1
                Current: one
                Current: two
                Current: three
```

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="b9b9d-406">示例5：使用 $switch 变量</span><span class="sxs-lookup"><span data-stu-id="b9b9d-406">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="b9b9d-407">`$switch`变量与变量具有完全相同的规则 `$foreach` 。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-407">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="b9b9d-408">下面的示例演示了所有枚举器概念。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-408">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b9d-409">请注意， **NotEvaluated** 即使在 `break` **MoveNext** 方法后面没有语句，也不会执行 NotEvaluated 事例。</span><span class="sxs-lookup"><span data-stu-id="b9b9d-409">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

```powershell
$values = "Start", "MoveNext", "NotEvaluated", "Reset", "End"
$stopInfinite = $false
switch ($values)
{
    "MoveNext" {
        "`tMoveNext"
        $switch.MoveNext() | Out-Null
        "`tAfter MoveNext: $($switch.Current)"
    }
    # This case is never evaluated.
    "NotEvaluated" {
        "`tAfterMoveNext: $($switch.Current)"
    }

    "Reset" {
        if (!$stopInfinite)
        {
            "`tReset"
            $switch.Reset()
            $stopInfinite = $true
        }
    }

    default {
        "Default (Current): $($switch.Current)"
    }
}
```

```Output
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
    Reset
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
Default (Current): End
```

## <a name="see-also"></a><span data-ttu-id="b9b9d-410">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9b9d-410">See also</span></span>

[<span data-ttu-id="b9b9d-411">about_Functions</span><span class="sxs-lookup"><span data-stu-id="b9b9d-411">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="b9b9d-412">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="b9b9d-412">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="b9b9d-413">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="b9b9d-413">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="b9b9d-414">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="b9b9d-414">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="b9b9d-415">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="b9b9d-415">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="b9b9d-416">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="b9b9d-416">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="b9b9d-417">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="b9b9d-417">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="b9b9d-418">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b9b9d-418">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="b9b9d-419">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="b9b9d-419">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="b9b9d-420">about_Variables</span><span class="sxs-lookup"><span data-stu-id="b9b9d-420">about_Variables</span></span>](about_Variables.md)
