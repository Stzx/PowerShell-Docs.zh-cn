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
# <a name="about-powershellexe"></a>关于 PowerShell.exe

## <a name="short-description"></a>简短说明
说明如何使用 `powershell.exe` 命令行界面。 显示命令行参数并描述语法。

## <a name="long-description"></a>详细说明

### <a name="syntax"></a>SYNTAX

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

### <a name="parameters"></a>parameters

#### <a name="-psconsolefile-filepath"></a>-PSConsoleFile \<FilePath\>

加载指定的 PowerShell 控制台文件。 输入控制台文件的路径和名称。 若要创建控制台文件，请使用 PowerShell 中的 Export-console cmdlet。

#### <a name="-version-powershell-version"></a>-Version \<PowerShell Version\>

启动 PowerShell 的指定版本。 有效值为 2.0 和 3.0。 必须在系统上安装指定的版本。 如果计算机上安装了 Windows PowerShell 3.0，则默认版本为 "3.0"。
否则为默认版本 "2.0"。 有关详细信息，请参阅 [安装 PowerShell](/powershell/scripting/install/installing-windows-powershell)。

#### <a name="-nologo"></a>-NoLogo

启动时隐藏版权横幅。

#### <a name="-noexit"></a>-NoExit

运行启动命令后不退出。

#### <a name="-sta"></a>-Sta

使用单线程单元启动 PowerShell。 在 Windows PowerShell 2.0 中，多线程单元 (MTA) 是默认设置。 在 Windows PowerShell 3.0 中，单线程单元 (STA) 是默认设置。

#### <a name="-mta"></a>-Mta

使用多线程单元启动 PowerShell。 此参数是在 PowerShell 3.0 中引入的。 在 PowerShell 2.0 中，多线程单元 (MTA) 是默认设置。 在 PowerShell 3.0 中，单线程单元 (STA) 是默认设置。

#### <a name="-noprofile"></a>-NoProfile

不加载 PowerShell 配置文件。

#### <a name="-noninteractive"></a>-NonInteractive

不向用户显示交互式提示。

#### <a name="-inputformat-text--xml"></a>-InputFormat {文本 |XML}

描述发送到 PowerShell 的数据格式。 有效值为“Text”（文本字符串）或“XML”（序列化 CLIXML 格式）。

#### <a name="-outputformat-text--xml"></a>-OutputFormat {文本 | XML}

确定 PowerShell 输出内容的格式。 有效值为“Text”（文本字符串）或“XML”（序列化 CLIXML 格式）。

#### <a name="-windowstyle-window-style"></a>-WindowStyle \<Window style\>

为会话设置窗口样式。 有效值包括 Normal、Minimized、Maximized 和 Hidden。

#### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand \<Base64EncodedCommand\>

接受命令的 base-64 编码字符串版本。 使用此参数将命令提交到需要复杂的引号或大括号的 PowerShell。 必须使用 UTF-16LE 字符编码对字符串进行格式设置。

#### <a name="-configurationname-string"></a>-ConfigurationName \<string\>

指定运行 PowerShell 的配置终结点。 这可以是在本地计算机上注册的任何终结点，包括默认 PowerShell 远程处理终结点或具有特定用户角色功能的自定义终结点。

#### <a name="-file----filepath-args"></a>-File-|\<filePath\>\<args\>

如果 " **文件** " 的值为 "-"，则将从标准输入读取命令文本。
运行时 `powershell -File -` 不使用重定向标准输入会启动常规会话。 这与根本不指定 **文件** 参数相同。

如果 " **文件** " 的值是文件路径，则脚本会在本地作用域中运行 ( "带 ) 点"，以便脚本创建的函数和变量在当前会话中可用。 输入脚本文件路径和任何参数。 “文件”  必须是命令中的最后一个参数。 在 **File** 参数之后键入的所有值都被解释为脚本文件路径和传递到该脚本的参数。

传递给脚本的参数作为文字字符串（在当前 shell 的解释后）传递。 例如，如果你处于 **cmd.exe** 并且想要传递环境变量值，则应使用 **cmd.exe** 语法： `powershell.exe -File .\test.ps1 -TestParam %windir%`

相反， `powershell.exe -File .\test.ps1 -TestParam $env:windir` 在 **cmd.exe** 中运行将导致接收文本字符串的脚本， `$env:windir` 因为它对当前 **cmd.exe** shell 没有特殊意义。 `$env:windir`_可以_ 在 **命令** 参数中使用环境变量引用的样式，因为它将被解释为 PowerShell 代码。

同样，如果您想要从 **批处理脚本** 执行相同的命令，则可以使用 `%~dp0` 而不是 `.\` 或 `$PSScriptRoot` 来表示当前执行目录： `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` 。
如果你使用 `.\test.ps1` ，则 PowerShell 将引发错误，因为它无法找到文本路径 `.\test.ps1`

如果 **file** 的值是文件路径，则 **file** _必须_ 是命令中的最后一个参数，因为在 **文件** 参数名称后键入的所有字符都会被解释为后跟脚本参数的脚本文件路径。

可以在 **File** 参数的值中包含脚本参数和值。 例如：`-File .\Get-Script.ps1 -Domain Central`

通常，将包括或忽略脚本的开关参数。
例如，以下命令使用脚本文件的 **All** 参数 `Get-Script.ps1` ： `-File .\Get-Script.ps1 -All`

在极少数情况下，可能需要为参数提供一个 **布尔** 值。
以这种方式运行脚本时，不能为开关参数传递显式布尔值。 此限制已在 PowerShell 6 () 中删除 `pwsh.exe` 。

#### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy \<ExecutionPolicy\>

为当前会话设置默认执行策略，并将其保存在 `$env:PSExecutionPolicyPreference` 环境变量中。 此参数不会更改在注册表中设置的 PowerShell 执行策略。 若要了解 PowerShell 执行策略（包括有效值列表），请参阅 [about_Execution_Policies](about_Execution_Policies.md)。

#### <a name="-command"></a>-Command

执行指定的命令 (和任何) 参数，如同在 PowerShell 命令提示符下键入一样，然后退出，除非 `NoExit` 指定了参数。

**Command** 的值可以是 `-` 、脚本块或字符串。 如果 **command** 的值为，则将 `-` 从标准输入读取命令文本。

仅当 **命令** 参数可以将传递给 **Command** 的值识别为 **ScriptBlock** 类型时，才接受脚本块执行。 _仅_ 当 `powershell.exe` 从另一个 PowerShell 主机运行时，才可能出现这种情况。 **ScriptBlock** 类型可能包含在从表达式返回的现有变量中，或由 PowerShell 主机分析为括在大括号中的文本脚本块 (`{}`) ，然后再传递到 `powershell.exe` 。

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

在中 `cmd.exe` ，没有脚本块 (或 **ScriptBlock** 类型) ，因此传递给 **Command** 的值 _始终_ 为字符串。 可以在字符串中编写一个脚本块，但它不会被执行，该脚本块的行为与你在典型 PowerShell 提示符中键入它的行为完全相同，即将脚本块内容输出出来返还给你。

传递给 **命令** 的字符串仍作为 PowerShell 代码执行，因此，在从运行时，在第一位置通常不需要脚本块大括号 `cmd.exe` 。 要执行在字符串中定义的内联脚本块，可以使用[调用操作符](about_operators.md#special-operators) `&`：

```cmd
pwsh -Command "& {Get-WinEvent -LogName security}"
```

如果 **command** 的值为字符串，则 **command** 必须是 pwsh 的最后一个参数，因为其后面的所有参数都将解释为要执行的命令的一部分。

从现有 PowerShell 会话内调用时，结果将作为反序列化 XML 对象（而非活动对象）返回到父外壳程序。 对于其他 shell，结果将作为字符串返回。

如果 **command** 的值为，则将 `-` 从标准输入读取命令文本。 使用带有标准输入的 **命令** 参数时，必须重定向标准输入。 例如：

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

该示例产生下面的输出：

```Output
in
hi there
out
```

进程退出代码由脚本块内最后 (执行) 命令的状态确定。 退出代码为 `0` 时为 `$?` `$true` 或 `1` 何时为时 `$?` `$false` 。 如果最后一个命令是外部程序或 PowerShell 脚本，它显式设置除或之外的退出代码 `0` `1` ，则会将该退出代码转换为以 `1` 处理退出代码。 若要保留特定退出代码，请将添加 `exit $LASTEXITCODE` 到命令字符串或脚本块。

同样，当脚本终止 (运行空间终止) 错误（如或）时，将返回值1， `throw` `-ErrorAction Stop` 或在使用<kbd>Ctrl</kbd> - <kbd>C</kbd>中断执行时进行。

_仅_ 在从另一个 PowerShell 主机运行 **PowerShell.exe** 时可能。
**ScriptBlock** 类型可能包含在从表达式返回的现有变量中，或由 PowerShell 主机在 `{}` 传递到 **PowerShell.exe** 之前，作为括在大括号中的文本脚本块进行分析。

在 **cmd.exe** 中，脚本块 (或 **ScriptBlock** 类型) ，因此传递给 **Command** 的值将 _始终_ 为字符串。 可以在字符串中编写一个脚本块，但它不会被执行，该脚本块的行为与你在典型 PowerShell 提示符中键入它的行为完全相同，即将脚本块内容输出出来返还给你。

传递给 **Command** 的字符串仍将作为 PowerShell 执行，因此，从 **cmd.exe** 运行时，在第一位置通常不需要脚本块大括号。 若要执行在字符串中定义的内联脚本块，可以使用[调用运算符](about_operators.md#special-operators) 
 `&` ：

```console
"& {<command>}"
```

#### <a name="-help---"></a>-Help、-?、/?

显示 **PowerShell.exe** 的帮助。 如果在 PowerShell 会话中键入 **PowerShell.exe** 命令，请在命令参数前面添加连字符 (-) ，而不是正斜杠 (/) 。 可以在 **cmd.exe** 中使用连字符或正斜杠。

### <a name="remarks"></a>REMARKS

疑难解答说明：在 PowerShell 2.0 中，从 PowerShell 控制台启动某些程序失败，并出现 **LastExitCode** 的0xc0000142。

### <a name="examples"></a>示例

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
