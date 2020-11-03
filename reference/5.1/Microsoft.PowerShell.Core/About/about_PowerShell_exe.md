---
description: 说明如何使用 `powershell.exe` 命令行界面。 显示命令行参数并描述语法。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: ef03558a6b58868b98c9da488934b0bfbbce9fe7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200263"
---
# <a name="about-powershellexe"></a><span data-ttu-id="c560a-105">关于 PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="c560a-105">About PowerShell.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="c560a-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="c560a-106">Short Description</span></span>
<span data-ttu-id="c560a-107">说明如何使用 `powershell.exe` 命令行界面。</span><span class="sxs-lookup"><span data-stu-id="c560a-107">Explains how to use the `powershell.exe` command-line interface.</span></span> <span data-ttu-id="c560a-108">显示命令行参数并描述语法。</span><span class="sxs-lookup"><span data-stu-id="c560a-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="c560a-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="c560a-109">Long Description</span></span>

### <a name="syntax"></a><span data-ttu-id="c560a-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c560a-110">SYNTAX</span></span>

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a><span data-ttu-id="c560a-111">parameters</span><span class="sxs-lookup"><span data-stu-id="c560a-111">Parameters</span></span>

#### <a name="-psconsolefile-filepath"></a><span data-ttu-id="c560a-112">-PSConsoleFile \<FilePath\></span><span class="sxs-lookup"><span data-stu-id="c560a-112">-PSConsoleFile \<FilePath\></span></span>

<span data-ttu-id="c560a-113">加载指定的 PowerShell 控制台文件。</span><span class="sxs-lookup"><span data-stu-id="c560a-113">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="c560a-114">输入控制台文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="c560a-114">Enter the path and name of the console file.</span></span> <span data-ttu-id="c560a-115">若要创建控制台文件，请使用 PowerShell 中的 Export-console cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c560a-115">To create a console file, use the Export-Console cmdlet in PowerShell.</span></span>

#### <a name="-version-powershell-version"></a><span data-ttu-id="c560a-116">-Version \<PowerShell Version\></span><span class="sxs-lookup"><span data-stu-id="c560a-116">-Version \<PowerShell Version\></span></span>

<span data-ttu-id="c560a-117">启动 PowerShell 的指定版本。</span><span class="sxs-lookup"><span data-stu-id="c560a-117">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="c560a-118">有效值为 2.0 和 3.0。</span><span class="sxs-lookup"><span data-stu-id="c560a-118">Valid values are 2.0 and 3.0.</span></span> <span data-ttu-id="c560a-119">必须在系统上安装指定的版本。</span><span class="sxs-lookup"><span data-stu-id="c560a-119">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="c560a-120">如果计算机上安装了 Windows PowerShell 3.0，则默认版本为 "3.0"。</span><span class="sxs-lookup"><span data-stu-id="c560a-120">If Windows PowerShell 3.0 is installed on the computer, "3.0" is the default version.</span></span>
<span data-ttu-id="c560a-121">否则为默认版本 "2.0"。</span><span class="sxs-lookup"><span data-stu-id="c560a-121">Otherwise, "2.0" is the default version.</span></span> <span data-ttu-id="c560a-122">有关详细信息，请参阅 [安装 PowerShell](/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c560a-122">For more information, see [Installing PowerShell](/powershell/scripting/install/installing-windows-powershell).</span></span>

#### <a name="-nologo"></a><span data-ttu-id="c560a-123">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="c560a-123">-NoLogo</span></span>

<span data-ttu-id="c560a-124">启动时隐藏版权横幅。</span><span class="sxs-lookup"><span data-stu-id="c560a-124">Hides the copyright banner at startup.</span></span>

#### <a name="-noexit"></a><span data-ttu-id="c560a-125">-NoExit</span><span class="sxs-lookup"><span data-stu-id="c560a-125">-NoExit</span></span>

<span data-ttu-id="c560a-126">运行启动命令后不退出。</span><span class="sxs-lookup"><span data-stu-id="c560a-126">Does not exit after running startup commands.</span></span>

#### <a name="-sta"></a><span data-ttu-id="c560a-127">-Sta</span><span class="sxs-lookup"><span data-stu-id="c560a-127">-Sta</span></span>

<span data-ttu-id="c560a-128">使用单线程单元启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c560a-128">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="c560a-129">在 Windows PowerShell 2.0 中，多线程单元 (MTA) 是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c560a-129">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="c560a-130">在 Windows PowerShell 3.0 中，单线程单元 (STA) 是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c560a-130">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-mta"></a><span data-ttu-id="c560a-131">-Mta</span><span class="sxs-lookup"><span data-stu-id="c560a-131">-Mta</span></span>

<span data-ttu-id="c560a-132">使用多线程单元启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c560a-132">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="c560a-133">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c560a-133">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="c560a-134">在 PowerShell 2.0 中，多线程单元 (MTA) 是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c560a-134">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="c560a-135">在 PowerShell 3.0 中，单线程单元 (STA) 是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c560a-135">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-noprofile"></a><span data-ttu-id="c560a-136">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="c560a-136">-NoProfile</span></span>

<span data-ttu-id="c560a-137">不加载 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="c560a-137">Does not load the PowerShell profile.</span></span>

#### <a name="-noninteractive"></a><span data-ttu-id="c560a-138">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="c560a-138">-NonInteractive</span></span>

<span data-ttu-id="c560a-139">不向用户显示交互式提示。</span><span class="sxs-lookup"><span data-stu-id="c560a-139">Does not present an interactive prompt to the user.</span></span>

#### <a name="-inputformat-text--xml"></a><span data-ttu-id="c560a-140">-InputFormat {文本 |XML}</span><span class="sxs-lookup"><span data-stu-id="c560a-140">-InputFormat {Text | XML}</span></span>

<span data-ttu-id="c560a-141">描述发送到 PowerShell 的数据格式。</span><span class="sxs-lookup"><span data-stu-id="c560a-141">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="c560a-142">有效值为“Text”（文本字符串）或“XML”（序列化 CLIXML 格式）。</span><span class="sxs-lookup"><span data-stu-id="c560a-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-outputformat-text--xml"></a><span data-ttu-id="c560a-143">-OutputFormat {文本 | XML}</span><span class="sxs-lookup"><span data-stu-id="c560a-143">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="c560a-144">确定 PowerShell 输出内容的格式。</span><span class="sxs-lookup"><span data-stu-id="c560a-144">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="c560a-145">有效值为“Text”（文本字符串）或“XML”（序列化 CLIXML 格式）。</span><span class="sxs-lookup"><span data-stu-id="c560a-145">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-windowstyle-window-style"></a><span data-ttu-id="c560a-146">-WindowStyle \<Window style\></span><span class="sxs-lookup"><span data-stu-id="c560a-146">-WindowStyle \<Window style\></span></span>

<span data-ttu-id="c560a-147">为会话设置窗口样式。</span><span class="sxs-lookup"><span data-stu-id="c560a-147">Sets the window style for the session.</span></span> <span data-ttu-id="c560a-148">有效值包括 Normal、Minimized、Maximized 和 Hidden。</span><span class="sxs-lookup"><span data-stu-id="c560a-148">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

#### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="c560a-149">-EncodedCommand \<Base64EncodedCommand\></span><span class="sxs-lookup"><span data-stu-id="c560a-149">-EncodedCommand \<Base64EncodedCommand\></span></span>

<span data-ttu-id="c560a-150">接受命令的 base-64 编码字符串版本。</span><span class="sxs-lookup"><span data-stu-id="c560a-150">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="c560a-151">使用此参数将命令提交到需要复杂的引号或大括号的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c560a-151">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span> <span data-ttu-id="c560a-152">必须使用 UTF-16LE 字符编码对字符串进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="c560a-152">The string must be formatted using UTF-16LE character encoding.</span></span>

#### <a name="-configurationname-string"></a><span data-ttu-id="c560a-153">-ConfigurationName \<string\></span><span class="sxs-lookup"><span data-stu-id="c560a-153">-ConfigurationName \<string\></span></span>

<span data-ttu-id="c560a-154">指定运行 PowerShell 的配置终结点。</span><span class="sxs-lookup"><span data-stu-id="c560a-154">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="c560a-155">这可以是在本地计算机上注册的任何终结点，包括默认 PowerShell 远程处理终结点或具有特定用户角色功能的自定义终结点。</span><span class="sxs-lookup"><span data-stu-id="c560a-155">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

#### <a name="-file----filepath-args"></a><span data-ttu-id="c560a-156">-File-|\<filePath\>\<args\></span><span class="sxs-lookup"><span data-stu-id="c560a-156">-File - | \<filePath\> \<args\></span></span>

<span data-ttu-id="c560a-157">如果 " **文件** " 的值为 "-"，则将从标准输入读取命令文本。</span><span class="sxs-lookup"><span data-stu-id="c560a-157">If the value of **File** is "-", the command text is read from standard input.</span></span>
<span data-ttu-id="c560a-158">运行时 `powershell -File -` 不使用重定向标准输入会启动常规会话。</span><span class="sxs-lookup"><span data-stu-id="c560a-158">Running `powershell -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="c560a-159">这与根本不指定 **文件** 参数相同。</span><span class="sxs-lookup"><span data-stu-id="c560a-159">This is the same as not specifying the **File** parameter at all.</span></span>

<span data-ttu-id="c560a-160">如果 " **文件** " 的值是文件路径，则脚本会在本地作用域中运行 ( "带 ) 点"，以便脚本创建的函数和变量在当前会话中可用。</span><span class="sxs-lookup"><span data-stu-id="c560a-160">If the value of **File** is a file path, the script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="c560a-161">输入脚本文件路径和任何参数。</span><span class="sxs-lookup"><span data-stu-id="c560a-161">Enter the script file path and any parameters.</span></span> <span data-ttu-id="c560a-162">“文件”  必须是命令中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="c560a-162">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="c560a-163">在 **File** 参数之后键入的所有值都被解释为脚本文件路径和传递到该脚本的参数。</span><span class="sxs-lookup"><span data-stu-id="c560a-163">All values typed after the **File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="c560a-164">传递给脚本的参数作为文字字符串（在当前 shell 的解释后）传递。</span><span class="sxs-lookup"><span data-stu-id="c560a-164">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="c560a-165">例如，如果你处于 **cmd.exe** 并且想要传递环境变量值，则应使用 **cmd.exe** 语法： `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="c560a-165">For example, if you are in **cmd.exe** and want to pass an environment variable value, you would use the **cmd.exe** syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="c560a-166">相反， `powershell.exe -File .\test.ps1 -TestParam $env:windir` 在 **cmd.exe** 中运行将导致接收文本字符串的脚本， `$env:windir` 因为它对当前 **cmd.exe** shell 没有特殊意义。</span><span class="sxs-lookup"><span data-stu-id="c560a-166">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in **cmd.exe** results in the script receiving the literal string `$env:windir` because it has no special meaning to the current **cmd.exe** shell.</span></span> <span data-ttu-id="c560a-167">`$env:windir`_可以_ 在 **命令** 参数中使用环境变量引用的样式，因为它将被解释为 PowerShell 代码。</span><span class="sxs-lookup"><span data-stu-id="c560a-167">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it will be interpreted as PowerShell code.</span></span>

<span data-ttu-id="c560a-168">同样，如果您想要从 **批处理脚本** 执行相同的命令，则可以使用 `%~dp0` 而不是 `.\` 或 `$PSScriptRoot` 来表示当前执行目录： `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` 。</span><span class="sxs-lookup"><span data-stu-id="c560a-168">Similarly, if you want to execute the same command from a **Batch script** , you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%`.</span></span>
<span data-ttu-id="c560a-169">如果你使用 `.\test.ps1` ，则 PowerShell 将引发错误，因为它无法找到文本路径 `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="c560a-169">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="c560a-170">如果 **file** 的值是文件路径，则 **file** _必须_ 是命令中的最后一个参数，因为在 **文件** 参数名称后键入的所有字符都会被解释为后跟脚本参数的脚本文件路径。</span><span class="sxs-lookup"><span data-stu-id="c560a-170">When the value of **File** is a file path, **File** _must_ be the last parameter in the command because any characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="c560a-171">可以在 **File** 参数的值中包含脚本参数和值。</span><span class="sxs-lookup"><span data-stu-id="c560a-171">You can include the script parameters and values in the value of the **File** parameter.</span></span> <span data-ttu-id="c560a-172">例如：`-File .\Get-Script.ps1 -Domain Central`</span><span class="sxs-lookup"><span data-stu-id="c560a-172">For example: `-File .\Get-Script.ps1 -Domain Central`</span></span>

<span data-ttu-id="c560a-173">通常，将包括或忽略脚本的开关参数。</span><span class="sxs-lookup"><span data-stu-id="c560a-173">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="c560a-174">例如，以下命令使用脚本文件的 **All** 参数 `Get-Script.ps1` ： `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="c560a-174">For example, the following command uses the **All** parameter of the `Get-Script.ps1` script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="c560a-175">在极少数情况下，可能需要为参数提供一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="c560a-175">In rare cases, you might need to provide a **Boolean** value for a parameter.</span></span>
<span data-ttu-id="c560a-176">以这种方式运行脚本时，不能为开关参数传递显式布尔值。</span><span class="sxs-lookup"><span data-stu-id="c560a-176">It is not possible to pass an explicit boolean value for a switch parameter when running a script in this way.</span></span> <span data-ttu-id="c560a-177">此限制已在 PowerShell 6 () 中删除 `pwsh.exe` 。</span><span class="sxs-lookup"><span data-stu-id="c560a-177">This limitation was removed in PowerShell 6 (`pwsh.exe`).</span></span>

#### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="c560a-178">-ExecutionPolicy \<ExecutionPolicy\></span><span class="sxs-lookup"><span data-stu-id="c560a-178">-ExecutionPolicy \<ExecutionPolicy\></span></span>

<span data-ttu-id="c560a-179">为当前会话设置默认执行策略，并将其保存在 `$env:PSExecutionPolicyPreference` 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="c560a-179">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="c560a-180">此参数不会更改在注册表中设置的 PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="c560a-180">This parameter does not change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="c560a-181">若要了解 PowerShell 执行策略（包括有效值列表），请参阅 [about_Execution_Policies](about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c560a-181">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

#### <a name="-command"></a><span data-ttu-id="c560a-182">-Command</span><span class="sxs-lookup"><span data-stu-id="c560a-182">-Command</span></span>

<span data-ttu-id="c560a-183">执行指定的命令 (和任何) 参数，如同在 PowerShell 命令提示符下键入一样，然后退出，除非 `NoExit` 指定了参数。</span><span class="sxs-lookup"><span data-stu-id="c560a-183">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="c560a-184">**Command** 的值可以是 `-` 、脚本块或字符串。</span><span class="sxs-lookup"><span data-stu-id="c560a-184">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="c560a-185">如果 **command** 的值为，则将 `-` 从标准输入读取命令文本。</span><span class="sxs-lookup"><span data-stu-id="c560a-185">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="c560a-186">仅当 **命令** 参数可以将传递给 **Command** 的值识别为 **ScriptBlock** 类型时，才接受脚本块执行。</span><span class="sxs-lookup"><span data-stu-id="c560a-186">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="c560a-187">_仅_ 当 `powershell.exe` 从另一个 PowerShell 主机运行时，才可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="c560a-187">This is _only_ possible when running `powershell.exe` from another PowerShell host.</span></span> <span data-ttu-id="c560a-188">**ScriptBlock** 类型可能包含在从表达式返回的现有变量中，或由 PowerShell 主机分析为括在大括号中的文本脚本块 (`{}`) ，然后再传递到 `powershell.exe` 。</span><span class="sxs-lookup"><span data-stu-id="c560a-188">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `powershell.exe`.</span></span>

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="c560a-189">在中 `cmd.exe` ，没有脚本块 (或 **ScriptBlock** 类型) ，因此传递给 **Command** 的值 _始终_ 为字符串。</span><span class="sxs-lookup"><span data-stu-id="c560a-189">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="c560a-190">可以在字符串中编写一个脚本块，但它不会被执行，该脚本块的行为与你在典型 PowerShell 提示符中键入它的行为完全相同，即将脚本块内容输出出来返还给你。</span><span class="sxs-lookup"><span data-stu-id="c560a-190">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="c560a-191">传递给 **命令** 的字符串仍作为 PowerShell 代码执行，因此，在从运行时，在第一位置通常不需要脚本块大括号 `cmd.exe` 。</span><span class="sxs-lookup"><span data-stu-id="c560a-191">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="c560a-192">要执行在字符串中定义的内联脚本块，可以使用[调用操作符](about_operators.md#special-operators) `&`：</span><span class="sxs-lookup"><span data-stu-id="c560a-192">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```cmd
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="c560a-193">如果 **command** 的值为字符串，则 **command** 必须是 pwsh 的最后一个参数，因为其后面的所有参数都将解释为要执行的命令的一部分。</span><span class="sxs-lookup"><span data-stu-id="c560a-193">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="c560a-194">从现有 PowerShell 会话内调用时，结果将作为反序列化 XML 对象（而非活动对象）返回到父外壳程序。</span><span class="sxs-lookup"><span data-stu-id="c560a-194">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="c560a-195">对于其他 shell，结果将作为字符串返回。</span><span class="sxs-lookup"><span data-stu-id="c560a-195">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="c560a-196">如果 **command** 的值为，则将 `-` 从标准输入读取命令文本。</span><span class="sxs-lookup"><span data-stu-id="c560a-196">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="c560a-197">使用带有标准输入的 **命令** 参数时，必须重定向标准输入。</span><span class="sxs-lookup"><span data-stu-id="c560a-197">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="c560a-198">例如：</span><span class="sxs-lookup"><span data-stu-id="c560a-198">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="c560a-199">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c560a-199">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="c560a-200">进程退出代码由脚本块内最后 (执行) 命令的状态确定。</span><span class="sxs-lookup"><span data-stu-id="c560a-200">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="c560a-201">退出代码为 `0` 时为 `$?` `$true` 或 `1` 何时为时 `$?` `$false` 。</span><span class="sxs-lookup"><span data-stu-id="c560a-201">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="c560a-202">如果最后一个命令是外部程序或 PowerShell 脚本，它显式设置除或之外的退出代码 `0` `1` ，则会将该退出代码转换为以 `1` 处理退出代码。</span><span class="sxs-lookup"><span data-stu-id="c560a-202">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="c560a-203">若要保留特定退出代码，请将添加 `exit $LASTEXITCODE` 到命令字符串或脚本块。</span><span class="sxs-lookup"><span data-stu-id="c560a-203">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="c560a-204">同样，当脚本终止 (运行空间终止) 错误（如或）时，将返回值1， `throw` `-ErrorAction Stop` 或在使用<kbd>Ctrl</kbd> - <kbd>C</kbd>中断执行时进行。</span><span class="sxs-lookup"><span data-stu-id="c560a-204">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

<span data-ttu-id="c560a-205">_仅_ 在从另一个 PowerShell 主机运行 **PowerShell.exe** 时可能。</span><span class="sxs-lookup"><span data-stu-id="c560a-205">_only_ possible when running **PowerShell.exe** from another PowerShell host.</span></span>
<span data-ttu-id="c560a-206">**ScriptBlock** 类型可能包含在从表达式返回的现有变量中，或由 PowerShell 主机在 `{}` 传递到 **PowerShell.exe** 之前，作为括在大括号中的文本脚本块进行分析。</span><span class="sxs-lookup"><span data-stu-id="c560a-206">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to **PowerShell.exe** .</span></span>

<span data-ttu-id="c560a-207">在 **cmd.exe** 中，脚本块 (或 **ScriptBlock** 类型) ，因此传递给 **Command** 的值将 _始终_ 为字符串。</span><span class="sxs-lookup"><span data-stu-id="c560a-207">In **cmd.exe** , there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="c560a-208">可以在字符串中编写一个脚本块，但它不会被执行，该脚本块的行为与你在典型 PowerShell 提示符中键入它的行为完全相同，即将脚本块内容输出出来返还给你。</span><span class="sxs-lookup"><span data-stu-id="c560a-208">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="c560a-209">传递给 **Command** 的字符串仍将作为 PowerShell 执行，因此，从 **cmd.exe** 运行时，在第一位置通常不需要脚本块大括号。</span><span class="sxs-lookup"><span data-stu-id="c560a-209">A string passed to **Command** will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from **cmd.exe** .</span></span> <span data-ttu-id="c560a-210">若要执行在字符串中定义的内联脚本块，可以使用[调用运算符](about_operators.md#special-operators) 
 `&` ：</span><span class="sxs-lookup"><span data-stu-id="c560a-210">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators)
`&` can be used:</span></span>

```console
"& {<command>}"
```

#### <a name="-help---"></a><span data-ttu-id="c560a-211">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="c560a-211">-Help, -?, /?</span></span>

<span data-ttu-id="c560a-212">显示 **PowerShell.exe** 的帮助。</span><span class="sxs-lookup"><span data-stu-id="c560a-212">Displays help for **PowerShell.exe** .</span></span> <span data-ttu-id="c560a-213">如果在 PowerShell 会话中键入 **PowerShell.exe** 命令，请在命令参数前面添加连字符 (-) ，而不是正斜杠 (/) 。</span><span class="sxs-lookup"><span data-stu-id="c560a-213">If you are typing a **PowerShell.exe** command in a PowerShell session, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="c560a-214">可以在 **cmd.exe** 中使用连字符或正斜杠。</span><span class="sxs-lookup"><span data-stu-id="c560a-214">You can use either a hyphen or forward slash in **cmd.exe** .</span></span>

### <a name="remarks"></a><span data-ttu-id="c560a-215">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c560a-215">REMARKS</span></span>

<span data-ttu-id="c560a-216">疑难解答说明：在 PowerShell 2.0 中，从 PowerShell 控制台启动某些程序失败，并出现 **LastExitCode** 的0xc0000142。</span><span class="sxs-lookup"><span data-stu-id="c560a-216">Troubleshooting note: In PowerShell 2.0, starting some programs from the PowerShell console fails with a **LastExitCode** of 0xc0000142.</span></span>

### <a name="examples"></a><span data-ttu-id="c560a-217">示例</span><span class="sxs-lookup"><span data-stu-id="c560a-217">EXAMPLES</span></span>

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
