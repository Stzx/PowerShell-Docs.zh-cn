---
title: 如何复制 Visual Studio Code 中的 ISE 体验
description: 如何复制 Visual Studio Code 中的 ISE 体验
ms.date: 08/06/2018
ms.openlocfilehash: 899e1c393fd49b0659631b88d610e80ec885e69e
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "81005595"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>如何复制 Visual Studio Code 中的 ISE 体验

虽然适用于 VS Code 的 PowerShell 扩展并不寻求与 PowerShell ISE 的完全功能奇偶一致性，但有些功能可以让 ISE 用户更自然地体验 VS Code。

本文档尝试列出可以在 VS Code 中配置的设置，使用户获得与 ISE 相比更熟悉的体验。

## <a name="ise-mode"></a>ISE 模式

> [!NOTE]
> 此功能自版本 2019.12.0 起在 PowerShell 预览版扩展中可用，自版本 2020.3.0 起在 PowerShell 扩展中可用。

在 Visual Studio Code 中复制 ISE 体验的最简单方法是打开“ISE 模式”。
为此，请打开命令托盘（<kbd>F1</kbd> 或 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>，在 macOS 上为 <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>），然后键入“ISE 模式”。 从列表中选择“PowerShell:启用 ISE 模式”。

此命令会自动应用下面所述的设置，结果如下所示：

![ISE 模式](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a>ISE 模式配置设置

ISE 模式对 VS Code 设置进行了以下更改。

- 键绑定

  |               函数                |         ISE 绑定          |              VS Code 绑定                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | 干扰并中断调试器          | <kbd>Ctrl</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
  | 执行当前行/突出显示的文本 | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
  | 列出可用代码片段               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

  > [!NOTE]
  > 也可以在 VS Code 中[配置自己的键绑定](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)。

- 简化的类似 ISE 的 UI

  如果希望简化 Visual Studio Code UI，以便看起来更接近 ISE 的 UI，请应用以下两个设置：

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  这些设置会隐藏下面的红色框内显示的“活动栏”和“调试侧边栏”部分：

  ![突出显示的部分包括“活动栏”和“调试侧边栏”](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  最终结果如下所示：

  ![简化的 VS Code 视图](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- Tab 自动补全

  若要启用更类似于 ISE 的 Tab 自动补全，请添加以下设置：

  ```json
  "editor.tabCompletion": "on",
  ```

- 执行时焦点无需置于控制台

  使用 <kbd>F8</kbd> 执行时，要在编辑器中保持焦点：

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  访问性目的默认为 `true`。

- 启动时不要启动集成控制台

  若要在启动时停止集成控制台，请设置：

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > 后台 PowerShell 进程仍将启动，以提供 IntelliSense、脚本分析、符号导航等，但控制台不会显示。

- 假设默认情况下文件是 PowerShell

  若要创建新/无标题文件，请默认注册为 PowerShell：

  ```json
  "files.defaultLanguage": "powershell",
  ```

- 配色方案

  有许多可供 VS Code 使用的 ISE 主题，它们使编辑器看起来更像 ISE。

  在[命令面板][]中，键入 `theme` 以获得 `Preferences: Color Theme`，并按 <kbd>Enter</kbd>。 从下拉列表中选择 `PowerShell ISE`。

  可以通过以下工具在设置中设置该主题：

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- PowerShell 命令资源管理器

  感谢 [@corbob](https://github.com/corbob) 的工作，PowerShell 扩展开始有其自己的命令资源管理器。

  在[命令面板][]中，键入 `PowerShell Command Explorer` 并按 <kbd>Enter</kbd>。

- 在 ISE 中打开

  如果仍要在 Windows PowerShell ISE 中打开文件，请打开[命令面板][]，搜索“在 ISE 中打开”，然后选择“PowerShell:  在 PowerShell ISE 中打开当前文件”。

## <a name="other-resources"></a>其他资源

- 4sysops 上有一篇有关如何将 VS Code 配置得更像 ISE 的[精彩文章][4sysops]。
- Mike F Robbins 撰写了一篇关于如何设置 VS Code 的[出色文章][mikefrobbins]。
- Learn PowerShell 上有一篇关于为 PowerShell 进行设置的[优秀文章][learnpwsh]。

## <a name="vs-code-tips"></a>VS Code 提示

- 命令面板

  命令面板是在 VS Code 中执行命令的一种便捷方式。 要打开命令面板，可以使用 <kbd>F1</kbd> 或 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>，在 macOS 上为 <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>。

  有关详细信息，请参阅 [VS Code 文档][vsc-docs]。

- 禁用“调试控制台”

  如果你只计划使用 VS Code 进行 PowerShell 脚本编写，则可以隐藏“调试控制台”  ，因为 PowerShell 扩展不会用到它。 为此，请右键单击“调试控制台”，  然后单击复选标记以将其隐藏。

## <a name="more-settings"></a>更多设置

如果你知道更多让 ISE 用户更熟悉 VS Code 的方法，请参与编写本文档。如果正在寻找兼容性配置，但找不到任何方法来启用它，则[提出问题][]，然后询问！

此外，我们始终乐于接受 PR 并欢迎投稿！

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[命令面板]: #vs-code-tips
[提出问题]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
