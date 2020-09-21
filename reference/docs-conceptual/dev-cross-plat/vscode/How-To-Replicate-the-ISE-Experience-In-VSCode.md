---
title: 如何复制 Visual Studio Code 中的 ISE 体验
description: 如何复制 Visual Studio Code 中的 ISE 体验
ms.date: 08/06/2018
ms.openlocfilehash: 6b0b8ce054695d6cc0fc578290c554e2dc1472bc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784616"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="22cf3-103">如何复制 Visual Studio Code 中的 ISE 体验</span><span class="sxs-lookup"><span data-stu-id="22cf3-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="22cf3-104">虽然适用于 VS Code 的 PowerShell 扩展并不寻求与 PowerShell ISE 的完全功能奇偶一致性，但有些功能可以让 ISE 用户更自然地体验 VS Code。</span><span class="sxs-lookup"><span data-stu-id="22cf3-104">While the PowerShell extension for VS Code doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VS Code experience more natural for users of the ISE.</span></span>

<span data-ttu-id="22cf3-105">本文档尝试列出可以在 VS Code 中配置的设置，使用户获得与 ISE 相比更熟悉的体验。</span><span class="sxs-lookup"><span data-stu-id="22cf3-105">This document tries to list settings you can configure in VS Code to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="22cf3-106">ISE 模式</span><span class="sxs-lookup"><span data-stu-id="22cf3-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="22cf3-107">此功能自版本 2019.12.0 起在 PowerShell 预览版扩展中可用，自版本 2020.3.0 起在 PowerShell 扩展中可用。</span><span class="sxs-lookup"><span data-stu-id="22cf3-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="22cf3-108">在 Visual Studio Code 中复制 ISE 体验的最简单方法是打开“ISE 模式”。</span><span class="sxs-lookup"><span data-stu-id="22cf3-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="22cf3-109">为此，请打开命令托盘（<kbd>F1</kbd> 或 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>，在 macOS 上为 <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>），然后键入“ISE 模式”。</span><span class="sxs-lookup"><span data-stu-id="22cf3-109">To do this, open the command palette (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span> <span data-ttu-id="22cf3-110">从列表中选择“PowerShell:启用 ISE 模式”。</span><span class="sxs-lookup"><span data-stu-id="22cf3-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="22cf3-111">此命令会自动应用下面所述的设置，结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="22cf3-111">This command automatically applies the settings described below The result looks like this:</span></span>

![处于 ISE 模式的 Visual Studio Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a><span data-ttu-id="22cf3-113">ISE 模式配置设置</span><span class="sxs-lookup"><span data-stu-id="22cf3-113">ISE Mode configuration settings</span></span>

<span data-ttu-id="22cf3-114">ISE 模式对 VS Code 设置进行了以下更改。</span><span class="sxs-lookup"><span data-stu-id="22cf3-114">ISE Mode makes the following changes to VS Code settings.</span></span>

- <span data-ttu-id="22cf3-115">键绑定</span><span class="sxs-lookup"><span data-stu-id="22cf3-115">Key bindings</span></span>

  |               <span data-ttu-id="22cf3-116">函数</span><span class="sxs-lookup"><span data-stu-id="22cf3-116">Function</span></span>                |         <span data-ttu-id="22cf3-117">ISE 绑定</span><span class="sxs-lookup"><span data-stu-id="22cf3-117">ISE Binding</span></span>          |              <span data-ttu-id="22cf3-118">VS Code 绑定</span><span class="sxs-lookup"><span data-stu-id="22cf3-118">VS Code Binding</span></span>                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | <span data-ttu-id="22cf3-119">干扰并中断调试器</span><span class="sxs-lookup"><span data-stu-id="22cf3-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="22cf3-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="22cf3-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="22cf3-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="22cf3-121"><kbd>F6</kbd></span></span>                               |
  | <span data-ttu-id="22cf3-122">执行当前行/突出显示的文本</span><span class="sxs-lookup"><span data-stu-id="22cf3-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="22cf3-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="22cf3-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="22cf3-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="22cf3-124"><kbd>F8</kbd></span></span>                               |
  | <span data-ttu-id="22cf3-125">列出可用代码片段</span><span class="sxs-lookup"><span data-stu-id="22cf3-125">List available snippets</span></span>               | <span data-ttu-id="22cf3-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="22cf3-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="22cf3-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="22cf3-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

  > [!NOTE]
  > <span data-ttu-id="22cf3-128">也可以在 VS Code 中[配置自己的键绑定](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)。</span><span class="sxs-lookup"><span data-stu-id="22cf3-128">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VS Code as well.</span></span>

- <span data-ttu-id="22cf3-129">简化的类似 ISE 的 UI</span><span class="sxs-lookup"><span data-stu-id="22cf3-129">Simplified ISE-like UI</span></span>

  <span data-ttu-id="22cf3-130">如果希望简化 Visual Studio Code UI，以便看起来更接近 ISE 的 UI，请应用以下两个设置：</span><span class="sxs-lookup"><span data-stu-id="22cf3-130">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  <span data-ttu-id="22cf3-131">这些设置会隐藏下面的红色框内显示的“活动栏”和“调试侧边栏”部分：</span><span class="sxs-lookup"><span data-stu-id="22cf3-131">These settings hide the "Activity Bar" and the "Debug Side Bar" sections shown inside the red box below:</span></span>

  ![突出显示的部分包括“活动栏”和“调试侧边栏”](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  <span data-ttu-id="22cf3-133">最终结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="22cf3-133">The end result looks like this:</span></span>

  ![简化的 VS Code 视图](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- <span data-ttu-id="22cf3-135">Tab 自动补全</span><span class="sxs-lookup"><span data-stu-id="22cf3-135">Tab completion</span></span>

  <span data-ttu-id="22cf3-136">若要启用更类似于 ISE 的 Tab 自动补全，请添加以下设置：</span><span class="sxs-lookup"><span data-stu-id="22cf3-136">To enable more ISE-like tab completion, add this setting:</span></span>

  ```json
  "editor.tabCompletion": "on",
  ```

- <span data-ttu-id="22cf3-137">执行时焦点无需置于控制台</span><span class="sxs-lookup"><span data-stu-id="22cf3-137">No focus on console when executing</span></span>

  <span data-ttu-id="22cf3-138">使用 <kbd>F8</kbd> 执行时，要在编辑器中保持焦点：</span><span class="sxs-lookup"><span data-stu-id="22cf3-138">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  <span data-ttu-id="22cf3-139">访问性目的默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="22cf3-139">The default is `true` for accessibility purposes.</span></span>

- <span data-ttu-id="22cf3-140">启动时不要启动集成控制台</span><span class="sxs-lookup"><span data-stu-id="22cf3-140">Don't start integrated console on startup</span></span>

  <span data-ttu-id="22cf3-141">若要在启动时停止集成控制台，请设置：</span><span class="sxs-lookup"><span data-stu-id="22cf3-141">To stop the integrated console on startup, set:</span></span>

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > <span data-ttu-id="22cf3-142">后台 PowerShell 进程仍将启动，以提供 IntelliSense、脚本分析、符号导航等，但控制台不会显示。</span><span class="sxs-lookup"><span data-stu-id="22cf3-142">The background PowerShell process still starts to provide IntelliSense, script analysis, symbol navigation, etc., but the console won't be shown.</span></span>

- <span data-ttu-id="22cf3-143">假设默认情况下文件是 PowerShell</span><span class="sxs-lookup"><span data-stu-id="22cf3-143">Assume files are PowerShell by default</span></span>

  <span data-ttu-id="22cf3-144">若要创建新/无标题文件，请默认注册为 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="22cf3-144">To make new/untitled files, register as PowerShell by default:</span></span>

  ```json
  "files.defaultLanguage": "powershell",
  ```

- <span data-ttu-id="22cf3-145">配色方案</span><span class="sxs-lookup"><span data-stu-id="22cf3-145">Color scheme</span></span>

  <span data-ttu-id="22cf3-146">有许多可供 VS Code 使用的 ISE 主题，它们使编辑器看起来更像 ISE。</span><span class="sxs-lookup"><span data-stu-id="22cf3-146">There are a number of ISE themes available for VS Code to make the editor look much more like the ISE.</span></span>

  <span data-ttu-id="22cf3-147">在[命令面板][]中，键入 `theme` 以获得 `Preferences: Color Theme`，并按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="22cf3-147">In the [Command Palette][] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span> <span data-ttu-id="22cf3-148">从下拉列表中选择 `PowerShell ISE`。</span><span class="sxs-lookup"><span data-stu-id="22cf3-148">In the drop-down list, select `PowerShell ISE`.</span></span>

  <span data-ttu-id="22cf3-149">可以通过以下工具在设置中设置该主题：</span><span class="sxs-lookup"><span data-stu-id="22cf3-149">You can set this theme in the settings with:</span></span>

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- <span data-ttu-id="22cf3-150">PowerShell 命令资源管理器</span><span class="sxs-lookup"><span data-stu-id="22cf3-150">PowerShell Command Explorer</span></span>

  <span data-ttu-id="22cf3-151">感谢 [@corbob](https://github.com/corbob) 的工作，PowerShell 扩展开始有其自己的命令资源管理器。</span><span class="sxs-lookup"><span data-stu-id="22cf3-151">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

  <span data-ttu-id="22cf3-152">在[命令面板][]中，键入 `PowerShell Command Explorer` 并按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="22cf3-152">In the [Command Palette][], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

- <span data-ttu-id="22cf3-153">在 ISE 中打开</span><span class="sxs-lookup"><span data-stu-id="22cf3-153">Open in the ISE</span></span>

  <span data-ttu-id="22cf3-154">如果仍要在 Windows PowerShell ISE 中打开文件，请打开[命令面板][]，搜索“在 ISE 中打开”，然后选择“PowerShell:  在 PowerShell ISE 中打开当前文件”。</span><span class="sxs-lookup"><span data-stu-id="22cf3-154">If you want to open a file in the Windows PowerShell ISE anyway, open the [Command Palette][], search for "open in ise", then select **PowerShell: Open Current File in PowerShell ISE**.</span></span>

## <a name="other-resources"></a><span data-ttu-id="22cf3-155">其他资源</span><span class="sxs-lookup"><span data-stu-id="22cf3-155">Other resources</span></span>

- <span data-ttu-id="22cf3-156">4sysops 上有一篇有关如何将 VS Code 配置得更像 ISE 的[精彩文章][4sysops]。</span><span class="sxs-lookup"><span data-stu-id="22cf3-156">4sysops has [a great article][4sysops] on configuring VS Code to be more like the ISE.</span></span>
- <span data-ttu-id="22cf3-157">Mike F Robbins 撰写了一篇关于如何设置 VS Code 的[出色文章][mikefrobbins]。</span><span class="sxs-lookup"><span data-stu-id="22cf3-157">Mike F Robbins has [a great post][mikefrobbins] on setting up VS Code.</span></span>
<!-- - Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell. -->

## <a name="vs-code-tips"></a><span data-ttu-id="22cf3-158">VS Code 提示</span><span class="sxs-lookup"><span data-stu-id="22cf3-158">VS Code Tips</span></span>

- <span data-ttu-id="22cf3-159">命令面板</span><span class="sxs-lookup"><span data-stu-id="22cf3-159">Command Palette</span></span>

  <span data-ttu-id="22cf3-160">命令面板是在 VS Code 中执行命令的一种便捷方式。</span><span class="sxs-lookup"><span data-stu-id="22cf3-160">The Command Palette is handy way of executing commands in VS Code.</span></span> <span data-ttu-id="22cf3-161">要打开命令面板，可以使用 <kbd>F1</kbd> 或 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>，在 macOS 上为 <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>。</span><span class="sxs-lookup"><span data-stu-id="22cf3-161">Open the command palette using <kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS.</span></span>

  <span data-ttu-id="22cf3-162">有关详细信息，请参阅 [VS Code 文档][vsc-docs]。</span><span class="sxs-lookup"><span data-stu-id="22cf3-162">For more information, see [the VS Code documentation][vsc-docs].</span></span>

- <span data-ttu-id="22cf3-163">禁用“调试控制台”</span><span class="sxs-lookup"><span data-stu-id="22cf3-163">Disable the Debug Console</span></span>

  <span data-ttu-id="22cf3-164">如果你只计划使用 VS Code 进行 PowerShell 脚本编写，则可以隐藏“调试控制台”，因为 PowerShell 扩展不会用到它。</span><span class="sxs-lookup"><span data-stu-id="22cf3-164">If you only plan on using VS Code for PowerShell scripting, you can hide the **Debug Console** since it is not used by the PowerShell extension.</span></span> <span data-ttu-id="22cf3-165">为此，请右键单击“调试控制台”，然后单击复选标记以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="22cf3-165">To do so, right click on **Debug Console** then click on the check mark to hide it.</span></span>

## <a name="more-settings"></a><span data-ttu-id="22cf3-166">更多设置</span><span class="sxs-lookup"><span data-stu-id="22cf3-166">More settings</span></span>

<span data-ttu-id="22cf3-167">如果你知道更多让 ISE 用户更熟悉 VS Code 的方法，请参与编写本文档。如果正在寻找兼容性配置，但找不到任何方法来启用它，则[提出问题][]，然后询问！</span><span class="sxs-lookup"><span data-stu-id="22cf3-167">If you know of more ways to make VS Code feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue][] and ask away!</span></span>

<span data-ttu-id="22cf3-168">此外，我们始终乐于接受 PR 并欢迎投稿！</span><span class="sxs-lookup"><span data-stu-id="22cf3-168">We're always happy to accept PRs and contributions as well!</span></span>

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[命令面板]: #vs-code-tips
[Command Palette]: #vs-code-tips
[创建问题]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose
[open an issue]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
