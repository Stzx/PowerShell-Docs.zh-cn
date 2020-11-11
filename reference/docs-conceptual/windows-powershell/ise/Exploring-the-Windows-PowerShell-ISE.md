---
ms.date: 01/02/2020
title: 探究 Windows PowerShell ISE
description: 本文概述了 Windows PowerShell ISE 的功能
ms.topic: landing-page
ms.custom: ISE-F1-page
ms.openlocfilehash: 4ef3f471f11c2f1de818491a193fcf34201cb04a
ms.sourcegitcommit: 109ff625773389be56e98e994b7e56146f2b9d93
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "93296359"
---
# <a name="exploring-the-windows-powershell-ise"></a>探究 Windows PowerShell ISE

可以使用 Windows PowerShell 集成脚本环境 (ISE) 来创建、运行及调试命令和脚本。 Windows PowerShell ISE 包含菜单栏、Windows PowerShell 选项卡、工具栏、脚本选项卡、脚本窗格、控制台窗格、状态栏、文字大小滑块和区分上下文的帮助。

## <a name="menu-bar"></a>菜单栏

菜单栏包含“ **文件** ”、“ **编辑** ”、“ **视图** ”、“ **工具** ”、“ **调试** ”、“ **加载项** ”和“ **帮助** ”菜单。 菜单上的按钮允许执行与编写和运行脚本以及在 Windows PowerShell ISE 中运行命令相关的任务。 此外，可以运行使用 [ISE 对象模型层次结构](object-model/The-ISE-Object-Model-Hierarchy.md)的脚本，将[加载项工具](object-model/The-ISEAddOnTool-Object.md)置于菜单栏中。

## <a name="windows-powershell-tabs"></a>Windows PowerShell 选项卡

Windows PowerShell 选项卡是 Windows PowerShell 脚本可在其中运行的环境。 可以在 Windows PowerShell ISE 中打开新的 Windows PowerShell 选项卡以在本地计算机或远程计算机上创建单独的环境。 最多可同时打开八个 PowerShell 选项卡。

有关详细信息，请参阅[如何在 Windows PowerShell ISE 中创建 PowerShell 选项卡](How-to-Create-a-PowerShell-Tab-in-Windows-PowerShell-ISE.md)。

## <a name="toolbar"></a>工具栏

下面的按钮位于工具栏上。

|             按钮             |                                                                                     函数                                                                                     |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **新建**                        | 打开新脚本。                                                                                                                                                              |
| **打开**                       | 打开现有脚本或文件。                                                                                                                                                |
| **保存**                       | 保存脚本或文件。                                                                                                                                                          |
| **剪切**                        | 剪切所选文本并将其复制到剪贴板。                                                                                                                           |
| **Copy**                       | 将选择的文本复制到剪贴板。                                                                                                                                       |
| **粘贴**                      | 将剪贴板内容粘贴到光标所在位置。                                                                                                                     |
| **清除输出窗格**          | 清除输出窗格中的所有内容。                                                                                                                                           |
| **撤消**                       | 撤销刚才执行的操作。                                                                                                                                     |
| **重做**                       | 执行刚才撤销的操作。                                                                                                                                        |
| **运行脚本**                 | 运行脚本。                                                                                                                                                                   |
| **运行选定内容**              | 运行脚本的选定部分。                                                                                                                                             |
| **停止执行**             | 停止正在运行的脚本。                                                                                                                                                  |
| **新建远程 PowerShell 选项卡**  | 创建将在远程计算机上建立会话的新 PowerShell 选项卡。 将出现一个对话框，提示你输入建立远程连接所需的详细信息。 |
| **启动 PowerShell.exe**       | 打开 Windows PowerShell 控制台。                                                                                                                                                      |
| **顶部显示脚本窗格**       | 将脚本窗格移动到显示器顶部。                                                                                                                                 |
| **右侧显示脚本窗格**     | 将脚本窗格移动到显示器右侧。                                                                                                                               |
| **最大化显示脚本窗格** | 最大化脚本窗格。                                                                                                                                                       |

## <a name="script-tab"></a>脚本选项卡

显示正在编辑的脚本的名称。 可以单击脚本选项卡以选择你想编辑的脚本。

当指向脚本选项卡时，脚本文件的完整限定路径将显示在工具提示中。

## <a name="script-pane"></a>脚本窗格

允许创建和运行脚本。 可以在脚本窗格中打开、编辑和运行现有脚本。 有关详细信息，请参阅[如何在 Windows PowerShell ISE 中编写和运行脚本](How-to-Write-and-Run-Scripts-in-the-Windows-PowerShell-ISE.md)。

## <a name="console-pane"></a>控制台窗格

显示已运行的命令和脚本的结果。 可在控制台窗格中运行命令。 你也可以在控制台窗格中复制和清除内容。

有关详细信息，请参阅以下文章：

- [如何在 Windows PowerShell ISE 中使用控制台窗格](How-to-Use-the-Console-Pane-in-the-Windows-PowerShell-ISE.md)
- [如何在 Windows PowerShell ISE 中调试脚本](How-to-Debug-Scripts-in-Windows-PowerShell-ISE.md)
- [如何在脚本窗格和控制台窗格中使用 Tab 自动补全](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)

## <a name="status-bar"></a>状态栏

允许查看你运行的命令和脚本是否完成。 状态栏位于显示器最底部。 错误消息的已选部分将显示在状态栏中。

## <a name="text-size-slider"></a>文字大小滑块

增大或减小屏幕上的文字大小。

## <a name="help"></a>帮助

可在 Web 上的 TechNet 库中找到有关 Windows PowerShell ISE 的帮助。 可以通过单击“帮助”菜单上的“Windows PowerShell ISE 帮助”打开帮助，或通过在任意位置（光标在脚本窗格或控制台窗格中的 cmdlet 名称上时除外）按 <kbd>F1</kbd> 键打开帮助。 从“帮助”菜单还可以运行 `Update-Help` cmdlet 和显示命令窗口，该命令窗口可显示某个 cmdlet 的所有参数并允许你在易于使用的窗体中填写参数，从而帮助你构造命令。

## <a name="see-also"></a>另请参阅

- [Windows PowerShell ISE 简介](Introducing-the-Windows-PowerShell-ISE.md)
- [如何在 Windows PowerShell ISE 中使用配置文件](How-to-Use-Profiles-in-Windows-PowerShell-ISE.md)
- [Windows PowerShell ISE 中的辅助功能](Accessibility-in-Windows-PowerShell-ISE.md)
- [Windows PowerShell ISE 的键盘快捷方式](Keyboard-Shortcuts-for-the-Windows-PowerShell-ISE.md)
