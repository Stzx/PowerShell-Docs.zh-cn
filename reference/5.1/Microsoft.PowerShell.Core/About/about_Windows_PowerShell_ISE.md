---
description: 介绍 (ISE) 的 Windows PowerShell 集成脚本环境的功能和系统要求。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_ise?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_ISE
ms.openlocfilehash: ff543024d7c62c70217eeaf3ded192a5a24c4757
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388835"
---
# <a name="about-windows-powershell-ise"></a>关于 Windows PowerShell ISE

## <a name="short-description"></a>简短说明

介绍 (ISE) 的 Windows PowerShell 集成脚本环境的功能和系统要求。

## <a name="long-description"></a>详细说明

Windows PowerShell ISE 是 Windows PowerShell 的图形主机应用程序。
在 Windows PowerShell ISE 中，你可以在单个基于 Windows 的图形用户界面中运行命令并编写、测试和调试脚本。 它的功能包括 Intellisense、多行编辑、tab 自动补全、自动保存、语法着色、选择性执行、上下文相关帮助、显示命令 (在窗口中撰写命令) 并支持双字节字符集和从右向左的语言。

对于初学者而言，Windows PowerShell ISE 是一个极佳的工具。 显示命令窗口和新的远程 PowerShell 选项卡引导你完成任务，以便在第一次尝试时可以成功完成。 在工作时，代码段和错误指示器有助于你了解 Windows PowerShell 语言。

高级用户可以利用复杂的调试功能、外接程序和 Windows PowerShell ISE 对象模型。

Windows PowerShell 4.0 中 Windows PowerShell ISE 的新增功能

Windows PowerShell ISE 在 Windows PowerShell 4.0 中引入了两项新功能。

- Windows PowerShell ISE 现在同时支持 Windows PowerShell 工作流调试和远程脚本调试。 有关详细信息，请参阅 about_Debuggers。

- 已为 Windows PowerShell Desired State Configuration 提供程序和配置添加 IntelliSense 支持。

## <a name="starting-windows-powershell-ise"></a>开始 Windows PowerShell ISE

Windows PowerShell ISE 已安装、已启用，并可在所有受支持的 Windows 版本中使用。

- 在 Windows 8.1、Windows 8、Windows Server 2012 R2 和 Windows Server 2012 的 "开始" 屏幕上，键入 "PowerShell_ISE"，然后单击 "PowerShell_ISE" 或 "Windows PowerShell ISE"。

- 在 Windows Server 2012 R2 和 Windows Server 2012 的服务器管理器中，单击 "工具" 菜单上的 "Windows PowerShell ISE"。

- 在早期版本的 Windows 中，单击 "开始"、"所有程序"、"附件"、"Windows PowerShell"，然后单击 "Windows PowerShell ISE"。

- 在 Windows PowerShell 控制台中，Cmd.exe 或 Windows 中的 "运行" 或 "搜索" 框中，键入 "PowerShell_ise.exe"。 你还可以使用命令行参数，包括 NoProfile 开关。 有关详细信息，请参阅 [PowerShell_ISE.exe 控制台帮助](about_powershell_ise_exe.md)。

## <a name="running-interactive-commands"></a>运行交互式命令

可以在 Windows PowerShell ISE 中运行任何 Windows PowerShell 表达式或命令。 你可以像在 Windows PowerShell 控制台中使用 cmdlet、提供程序、管理单元和模块一样使用它们。

可以在控制台窗格中键入或粘贴交互式命令。 若要运行这些命令，可以使用按钮、菜单项和键盘快捷方式。

您可以使用多行编辑功能一次将多行代码键入或粘贴到控制台窗格中。 当你按向上键来撤回上一个命令时，命令中的所有行都将被撤回。 键入命令时，按 SHIFT + ENTER 使新的空行出现在当前行下。

## <a name="viewing-output"></a>查看输出

命令和脚本的结果会显示在控制台窗格中。 您可以通过使用键盘快捷方式或工具栏上的 "复制" 按钮来移动或复制控制台窗格中的结果，还可以将结果粘贴到脚本窗格或控制台窗格或其他程序中。 若要清除控制台窗格，请单击 "清除输出窗格" 按钮或键入下列命令之一：

```
Clear-Host
cls
```

## <a name="writing-scripts-and-functions"></a>编写脚本和函数

在脚本窗格中，可以打开、撰写、编辑和运行脚本。 使用 "脚本" 窗格可以通过使用按钮和键盘快捷方式编辑脚本。 你还可以在脚本窗格和控制台窗格之间复制、剪切和粘贴文本。

您可以使用 "选择性运行" 功能来运行脚本的全部或部分。 若要运行部分脚本，请选择要运行的文本，然后单击 "运行选定内容" 按钮或按 F8。 默认情况下，F8 运行当前行。

高级编辑功能包括大括号匹配、展开/折叠、行号、错误指示器、块编辑和缩进、丰富副本和大小写转换。

## <a name="getting-help"></a>获取帮助

Windows PowerShell ISE 包括说明其用法的帮助主题。 此外，可以从脚本和命令窗格中访问所有已安装的帮助文件。

Windows PowerShell ISE 还支持区分上下文的帮助。 若要获取有关特定 cmdlet、提供程序或关键字的帮助，请将光标置于该项的名称中，然后按 F1。 若要搜索帮助主题，请按 F1 并键入搜索词。

若要更新计算机上的帮助主题，请使用 "帮助" 菜单中的 "更新 Windows PowerShell 帮助" 项。 此项将为当前 UI 区域性中的当前会话中的模块更新帮助。 它等效于运行没有参数的 Update-Help cmdlet。 若要为 Windows PowerShell 附带的 cmdlet 更新帮助，请以 "以管理员身份运行" 选项启动 Windows PowerShell ISE。

你还可以在 Windows PowerShell ISE 中使用 Get-help、Save-Help 和 Update-Help cmdlet，就像在 Windows PowerShell 控制台中使用一样。 但是，在 Windows PowerShell ISE 中，Help 函数显示整个帮助主题，而不是一次显示一个页面。

## <a name="debugging-scripts"></a>调试脚本

您可以使用 Windows PowerShell ISE 调试器来调试 Windows PowerShell 脚本或函数。 调试脚本时，可以使用菜单项和快捷键执行多个在 Windows PowerShell 控制台中执行的相同任务。 例如，若要在脚本中设置行断点，请右键单击代码行，然后单击 "切换断点"。

当你在调试过程中逐步执行脚本时，调试突出显示将精确显示命令正在运行的部分，并自动打开包含被调用函数和脚本的文件。

默认情况下，"切换断点" 菜单项在脚本的整行中设置断点，但您可以在变量或命令名称上设置断点。
还可以按行和列号对命令设置断点，以便更轻松地调试长管道命令。

通常，只需在 Windows PowerShell ISE 中打开脚本文件，即可在脚本中调试语法错误。 错误指示符标识语法错误，大纲功能使你可以折叠部分脚本来重点关注问题点。

你还可以在命令窗格中使用 Windows PowerShell 调试器 cmdlet，就像你在控制台中使用这些 cmdlet 一样。

## <a name="running-remote-commands"></a>运行远程命令

使用新的远程 PowerShell 选项卡功能，可以轻松地为本地计算机或远程计算机 ( "PSSession" ) 建立持久的用户管理的 Windows PowerShell 会话。 此命令会打开一个弹出窗口，提示你输入计算机名以及有权在远程计算机上运行命令的用户帐户。

## <a name="customizing-the-view"></a>自定义视图

您可以使用 Windows PowerShell ISE 功能来移动控制台窗格和脚本窗格，并调整其大小。 您可以显示和隐藏任一窗格，还可以在所有窗格中更改文本大小。

你还可以使用 "选项" 窗口自定义 Windows PowerShell ISE 的外观和操作。 此外，Windows PowerShell ISE 具有自定义主机变量 $psISE，可用于自定义 Windows PowerShell ISE，包括添加菜单和菜单项。

## <a name="windows-powershell-ise-profile"></a>Windows PowerShell ISE 配置文件

Windows PowerShell ISE 有自己的 Windows PowerShell 配置文件，Microsoft.PowerShellISE_profile.ps1。 在此配置文件中，可以存储在 Windows PowerShell ISE 中使用的函数、别名、变量和命令。

Windows PowerShell AllHosts 配置文件中的项 (CurrentUser \\ AllHosts 和 AllUsers \\ AllHosts) 在 Windows PowerShell ISE 中也可用，就像它们在任何 Windows PowerShell 主机程序中一样。 但是，Windows PowerShell 控制台配置文件中的项在 Windows PowerShell ISE 中不可用。

Windows PowerShell ISE 帮助和 about_Profiles 中提供了有关移动和重新配置配置文件的说明。

## <a name="notes"></a>注释

Windows PowerShell ISE 是一项可选的 Windows 功能，默认情况下在 Windows 的客户端和服务器版本上处于打开状态。 若要在 Windows 的客户端版本中启用和禁用 Windows PowerShell ISE，请使用 "控制面板" 中的 "打开或关闭 Windows 功能"。 若要在 Windows 的服务器版本中启用和禁用 Windows PowerShell ISE，请使用服务器管理器中的 "添加角色和功能向导"。

由于 Windows PowerShell ISE 需要用户界面，因此它在 Windows Server 的 Server Core 安装上不起作用。 但是，如果添加了 Windows PowerShell ISE 功能，则安装将自动使用 GUI 转换为服务器。

Windows PowerShell ISE 基于 Windows Presentation Foundation (WPF) 构建而成。
如果 Windows PowerShell ISE 的图形元素无法在您的系统上正确呈现，则可以通过在您的系统上添加或调整 "禁用 WPF 硬件加速" 图形呈现设置来解决此问题。 有关详细信息，请参阅[图形呈现注册表设置](/dotnet/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings)。

## <a name="see-also"></a>另请参阅

[about_Debuggers](about_Debuggers.md)

[about_Profiles](about_Profiles.md)

[about_Updatable_Help](about_Updatable_Help.md)

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Get-IseSnippet](xref:ISE.Get-IseSnippet)

[Import-IseSnippet](xref:ISE.Import-IseSnippet)

[New-IseSnippet](xref:ISE.New-IseSnippet)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

[Show-Command](xref:Microsoft.PowerShell.Utility.Show-Command)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)
