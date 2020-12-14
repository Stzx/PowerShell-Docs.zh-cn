---
description: PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于 PSReadLine
ms.openlocfilehash: 6d52bb04118914a9ccca5d3442a9d1915c1c2818
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692269"
---
# <a name="psreadline"></a><span data-ttu-id="a7015-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a7015-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="a7015-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a7015-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="a7015-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="a7015-106">Short Description</span></span>

<span data-ttu-id="a7015-107">PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="a7015-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="a7015-108">详细说明</span><span class="sxs-lookup"><span data-stu-id="a7015-108">Long Description</span></span>

<span data-ttu-id="a7015-109">PSReadLine 2.1 为 PowerShell 控制台提供了强大的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="a7015-109">PSReadLine 2.1 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="a7015-110">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="a7015-110">It provides:</span></span>

- <span data-ttu-id="a7015-111">命令行的语法着色</span><span class="sxs-lookup"><span data-stu-id="a7015-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="a7015-112">语法错误的直观指示</span><span class="sxs-lookup"><span data-stu-id="a7015-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="a7015-113"> (编辑和历史记录的更好的多行体验) </span><span class="sxs-lookup"><span data-stu-id="a7015-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="a7015-114">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="a7015-114">Customizable key bindings</span></span>
- <span data-ttu-id="a7015-115">Cmd 和 Emacs 模式</span><span class="sxs-lookup"><span data-stu-id="a7015-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="a7015-116">许多配置选项</span><span class="sxs-lookup"><span data-stu-id="a7015-116">Many configuration options</span></span>
- <span data-ttu-id="a7015-117">在 Cmd 模式下，Bash 样式完成 (可选，默认值为 Emacs 模式) </span><span class="sxs-lookup"><span data-stu-id="a7015-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="a7015-118">Emacs yank/kill 循环</span><span class="sxs-lookup"><span data-stu-id="a7015-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="a7015-119">基于 PowerShell 令牌的 "word" 移动和终止</span><span class="sxs-lookup"><span data-stu-id="a7015-119">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="a7015-120">预测 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a7015-120">Predictive IntelliSense</span></span>

<span data-ttu-id="a7015-121">PSReadLine 要求安装 PowerShell 3.0 或更高版本，以及控制台主机。</span><span class="sxs-lookup"><span data-stu-id="a7015-121">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="a7015-122">它在 PowerShell ISE 中不起作用。</span><span class="sxs-lookup"><span data-stu-id="a7015-122">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="a7015-123">它在 Visual Studio Code 的控制台中工作。</span><span class="sxs-lookup"><span data-stu-id="a7015-123">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="a7015-124">PSReadLine 2.1.0 随 PowerShell 7.1 一起提供，并在所有支持的 PowerShell 版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="a7015-124">PSReadLine 2.1.0 ships with PowerShell 7.1 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="a7015-125">它可从 PowerShell 库安装。</span><span class="sxs-lookup"><span data-stu-id="a7015-125">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="a7015-126">若要在支持的 PowerShell 版本中安装 PSReadLine 2.1.0，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="a7015-126">To install PSReadLine 2.1.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -RequiredVersion 2.1.0
```

> [!NOTE]
> <span data-ttu-id="a7015-127">从 PowerShell 7.0 开始，如果检测到屏幕阅读器程序，PowerShell 会跳过在 Windows 上自动加载 PSReadLine。</span><span class="sxs-lookup"><span data-stu-id="a7015-127">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="a7015-128">目前，PSReadLine 不能与屏幕阅读器很好地配合使用。</span><span class="sxs-lookup"><span data-stu-id="a7015-128">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="a7015-129">Windows 上 PowerShell 7.0 的默认呈现和格式设置正常。</span><span class="sxs-lookup"><span data-stu-id="a7015-129">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="a7015-130">如有必要，可以手动加载模块。</span><span class="sxs-lookup"><span data-stu-id="a7015-130">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="a7015-131">预测 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a7015-131">Predictive IntelliSense</span></span>

<span data-ttu-id="a7015-132">预测 IntelliSense 是选项卡完成的补充，可帮助用户成功完成命令。</span><span class="sxs-lookup"><span data-stu-id="a7015-132">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="a7015-133">它使用户能够基于用户历史记录和其他域特定插件中的匹配预测来发现、编辑和执行完整命令。</span><span class="sxs-lookup"><span data-stu-id="a7015-133">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="a7015-134">启用预测 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a7015-134">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="a7015-135">默认情况下，禁用预测 IntelliSense。</span><span class="sxs-lookup"><span data-stu-id="a7015-135">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="a7015-136">若要启用预测，只需运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a7015-136">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="a7015-137">**PredictionSource** 参数还可以接受插件特定于域和自定义的要求。</span><span class="sxs-lookup"><span data-stu-id="a7015-137">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="a7015-138">若要禁用预测 IntelliSense，只需运行：</span><span class="sxs-lookup"><span data-stu-id="a7015-138">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="a7015-139">类 **[PSConsoleReadLine]** 中提供了以下函数。</span><span class="sxs-lookup"><span data-stu-id="a7015-139">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="a7015-140">基本编辑函数</span><span class="sxs-lookup"><span data-stu-id="a7015-140">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="a7015-141">中止</span><span class="sxs-lookup"><span data-stu-id="a7015-141">Abort</span></span>

<span data-ttu-id="a7015-142">中止当前操作，例如增量历史记录搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-142">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="a7015-143">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="a7015-143">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="a7015-144">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="a7015-144">AcceptAndGetNext</span></span>

<span data-ttu-id="a7015-145">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-145">Attempt to execute the current input.</span></span> <span data-ttu-id="a7015-146">如果可以 (如 AcceptLine) 执行，则在下一次调用 ReadLine 时，从历史记录中撤回下一项。</span><span class="sxs-lookup"><span data-stu-id="a7015-146">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="a7015-147">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="a7015-147">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="a7015-148">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="a7015-148">AcceptLine</span></span>

<span data-ttu-id="a7015-149">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-149">Attempt to execute the current input.</span></span> <span data-ttu-id="a7015-150">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-150">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="a7015-151">Cmd：`<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-151">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="a7015-152">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-152">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="a7015-153">Vi 插入模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-153">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="a7015-154">AddLine</span><span class="sxs-lookup"><span data-stu-id="a7015-154">AddLine</span></span>

<span data-ttu-id="a7015-155">继续提示显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-155">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="a7015-156">这可用于将多行输入作为单个命令输入，即使单个行自动完成输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="a7015-156">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="a7015-157">Cmd：`<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-157">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="a7015-158">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-158">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="a7015-159">Vi 插入模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-159">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="a7015-160">Vi 命令模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-160">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="a7015-161">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="a7015-161">BackwardDeleteChar</span></span>

<span data-ttu-id="a7015-162">删除光标前面的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-162">Delete the character before the cursor.</span></span>

- <span data-ttu-id="a7015-163">Cmd： `<Backspace>` ， `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="a7015-163">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="a7015-164">Emacs： `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="a7015-164">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="a7015-165">Vi 插入模式： `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a7015-165">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="a7015-166">Vi 命令模式： `<X>` ， `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="a7015-166">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="a7015-167">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="a7015-167">BackwardDeleteLine</span></span>

<span data-ttu-id="a7015-168">与 BackwardKillLine 一样，从点到行的开头删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-168">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="a7015-169">Cmd：`<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-169">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="a7015-170">Vi 插入模式： `<Ctrl+u>` ， `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-170">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="a7015-171">Vi 命令模式： `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="a7015-171">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="a7015-172">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="a7015-172">BackwardDeleteWord</span></span>

<span data-ttu-id="a7015-173">删除上一个词。</span><span class="sxs-lookup"><span data-stu-id="a7015-173">Deletes the previous word.</span></span>

- <span data-ttu-id="a7015-174">Vi 命令模式： `<Ctrl+w>` ， `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="a7015-174">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="a7015-175">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="a7015-175">BackwardKillLine</span></span>

<span data-ttu-id="a7015-176">清除输入从输入开始到光标。</span><span class="sxs-lookup"><span data-stu-id="a7015-176">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="a7015-177">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-177">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a7015-178">Emacs： `<Ctrl+u>` ， `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a7015-178">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="a7015-179">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="a7015-179">BackwardKillWord</span></span>

<span data-ttu-id="a7015-180">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-180">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="a7015-181">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-181">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="a7015-182">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a7015-183">Cmd： `<Ctrl+Backspace>` ， `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="a7015-183">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="a7015-184">Emacs： `<Alt+Backspace>` ， `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a7015-184">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="a7015-185">Vi 插入模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a7015-185">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="a7015-186">Vi 命令模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a7015-186">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="a7015-187">CancelLine</span><span class="sxs-lookup"><span data-stu-id="a7015-187">CancelLine</span></span>

<span data-ttu-id="a7015-188">取消当前输入，将输入保留在屏幕上，但返回到主机以便再次计算提示。</span><span class="sxs-lookup"><span data-stu-id="a7015-188">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="a7015-189">Vi 插入模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a7015-189">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="a7015-190">Vi 命令模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a7015-190">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="a7015-191">复制</span><span class="sxs-lookup"><span data-stu-id="a7015-191">Copy</span></span>

<span data-ttu-id="a7015-192">将所选区域复制到系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="a7015-192">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="a7015-193">如果未选择区域，则复制整行。</span><span class="sxs-lookup"><span data-stu-id="a7015-193">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="a7015-194">Cmd：`<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="a7015-194">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="a7015-195">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="a7015-195">CopyOrCancelLine</span></span>

<span data-ttu-id="a7015-196">如果选择了文本，请将其复制到剪贴板，否则取消该行。</span><span class="sxs-lookup"><span data-stu-id="a7015-196">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="a7015-197">Cmd：`<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a7015-197">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="a7015-198">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a7015-198">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="a7015-199">剪切</span><span class="sxs-lookup"><span data-stu-id="a7015-199">Cut</span></span>

<span data-ttu-id="a7015-200">删除所选区域将删除的文本放入系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="a7015-200">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="a7015-201">Cmd：`<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="a7015-201">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="a7015-202">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="a7015-202">DeleteChar</span></span>

<span data-ttu-id="a7015-203">删除光标下的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-203">Delete the character under the cursor.</span></span>

- <span data-ttu-id="a7015-204">Cmd：`<Delete>`</span><span class="sxs-lookup"><span data-stu-id="a7015-204">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="a7015-205">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="a7015-205">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="a7015-206">Vi 插入模式： `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="a7015-206">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="a7015-207">Vi 命令模式： `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a7015-207">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="a7015-208">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="a7015-208">DeleteCharOrExit</span></span>

<span data-ttu-id="a7015-209">删除光标下的字符; 如果行为空，则退出该过程。</span><span class="sxs-lookup"><span data-stu-id="a7015-209">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="a7015-210">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="a7015-210">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="a7015-211">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="a7015-211">DeleteEndOfBuffer</span></span>

<span data-ttu-id="a7015-212">删除到多行缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-212">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="a7015-213">Vi 命令模式： `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="a7015-213">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="a7015-214">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="a7015-214">DeleteEndOfWord</span></span>

<span data-ttu-id="a7015-215">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-215">Delete to the end of the word.</span></span>

- <span data-ttu-id="a7015-216">Vi 命令模式： `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="a7015-216">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="a7015-217">Deleteline.invoke</span><span class="sxs-lookup"><span data-stu-id="a7015-217">DeleteLine</span></span>

<span data-ttu-id="a7015-218">删除多行缓冲区的当前逻辑行，启用 "撤消"。</span><span class="sxs-lookup"><span data-stu-id="a7015-218">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="a7015-219">Vi 命令模式： `<d,d>` ， `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="a7015-219">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="a7015-220">DeletePreviousLines</span><span class="sxs-lookup"><span data-stu-id="a7015-220">DeletePreviousLines</span></span>

<span data-ttu-id="a7015-221">删除多行缓冲区中以前请求的逻辑行和当前逻辑行。</span><span class="sxs-lookup"><span data-stu-id="a7015-221">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="a7015-222">Vi 命令模式： `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="a7015-222">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="a7015-223">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="a7015-223">DeleteRelativeLines</span></span>

<span data-ttu-id="a7015-224">从缓冲区的开头删除到多行缓冲区中的当前逻辑行。</span><span class="sxs-lookup"><span data-stu-id="a7015-224">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="a7015-225">作为最多 Vi 命令，该 `<d,g,g>` 命令可以用一个指定绝对行号的数值参数预置，这一数字参数与当前行号一起构成了要删除的行范围。</span><span class="sxs-lookup"><span data-stu-id="a7015-225">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="a7015-226">如果未指定，则数值参数默认为1，这表示多行缓冲区中的第一个逻辑行。</span><span class="sxs-lookup"><span data-stu-id="a7015-226">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="a7015-227">要从多行删除的实际行数将计算为当前逻辑行号和指定数值参数之间的差值，这可能是负数。</span><span class="sxs-lookup"><span data-stu-id="a7015-227">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="a7015-228">因此，方法名称的 _相关_ 部分。</span><span class="sxs-lookup"><span data-stu-id="a7015-228">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="a7015-229">Vi 命令模式： `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="a7015-229">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="a7015-230">DeleteNextLines</span><span class="sxs-lookup"><span data-stu-id="a7015-230">DeleteNextLines</span></span>

<span data-ttu-id="a7015-231">删除多行缓冲区中的当前逻辑行和下一个请求的逻辑行。</span><span class="sxs-lookup"><span data-stu-id="a7015-231">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="a7015-232">Vi 命令模式： `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="a7015-232">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="a7015-233">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="a7015-233">DeleteLineToFirstChar</span></span>

<span data-ttu-id="a7015-234">删除从光标到行的第一个非空白字符的文本。</span><span class="sxs-lookup"><span data-stu-id="a7015-234">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="a7015-235">Vi 命令模式： `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="a7015-235">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="a7015-236">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="a7015-236">DeleteToEnd</span></span>

<span data-ttu-id="a7015-237">删除到行的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-237">Delete to the end of the line.</span></span>

- <span data-ttu-id="a7015-238">Vi 命令模式： `<D>` ， `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="a7015-238">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="a7015-239">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="a7015-239">DeleteWord</span></span>

<span data-ttu-id="a7015-240">删除下一个词。</span><span class="sxs-lookup"><span data-stu-id="a7015-240">Delete the next word.</span></span>

- <span data-ttu-id="a7015-241">Vi 命令模式： `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="a7015-241">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="a7015-242">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="a7015-242">ForwardDeleteLine</span></span>

<span data-ttu-id="a7015-243">与 ForwardKillLine 一样，从点到行尾删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-243">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="a7015-244">Cmd：`<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-244">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="a7015-245">Vi 插入模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-245">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="a7015-246">Vi 命令模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-246">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="a7015-247">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="a7015-247">InsertLineAbove</span></span>

<span data-ttu-id="a7015-248">在当前行的上方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="a7015-248">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="a7015-249">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-249">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="a7015-250">Cmd：`<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-250">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="a7015-251">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="a7015-251">InsertLineBelow</span></span>

<span data-ttu-id="a7015-252">在当前行下方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="a7015-252">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="a7015-253">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-253">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="a7015-254">Cmd：`<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-254">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="a7015-255">InvertCase</span><span class="sxs-lookup"><span data-stu-id="a7015-255">InvertCase</span></span>

<span data-ttu-id="a7015-256">反转当前字符的大小写，并移到下一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-256">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="a7015-257">Vi 命令模式： `<~>`</span><span class="sxs-lookup"><span data-stu-id="a7015-257">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="a7015-258">KillLine</span><span class="sxs-lookup"><span data-stu-id="a7015-258">KillLine</span></span>

<span data-ttu-id="a7015-259">清除从光标到输入末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-259">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="a7015-260">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-260">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a7015-261">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="a7015-261">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="a7015-262">KillRegion</span><span class="sxs-lookup"><span data-stu-id="a7015-262">KillRegion</span></span>

<span data-ttu-id="a7015-263">终止光标和标记之间的文本。</span><span class="sxs-lookup"><span data-stu-id="a7015-263">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="a7015-264">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-264">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="a7015-265">KillWord</span><span class="sxs-lookup"><span data-stu-id="a7015-265">KillWord</span></span>

<span data-ttu-id="a7015-266">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-266">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="a7015-267">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-267">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="a7015-268">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-268">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a7015-269">Cmd： `<Alt+d>` ， `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="a7015-269">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="a7015-270">Emacs： `<Alt+d>` ， `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="a7015-270">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="a7015-271">Vi 插入模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="a7015-271">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="a7015-272">Vi 命令模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="a7015-272">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="a7015-273">粘贴</span><span class="sxs-lookup"><span data-stu-id="a7015-273">Paste</span></span>

<span data-ttu-id="a7015-274">粘贴系统剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="a7015-274">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="a7015-275">Cmd： `<Ctrl+v>` ， `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="a7015-275">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="a7015-276">Vi 插入模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="a7015-276">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="a7015-277">Vi 命令模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="a7015-277">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7015-278">使用 **Paste** 函数时，剪贴板缓冲区的全部内容将粘贴到 PSReadLine 的输入缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="a7015-278">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="a7015-279">然后，将输入缓冲区传递到 PowerShell 分析器。</span><span class="sxs-lookup"><span data-stu-id="a7015-279">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="a7015-280">使用控制台应用程序的 **右键单击** 粘贴方法粘贴的输入会一次复制到输入缓冲区中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-280">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="a7015-281">复制换行符时，输入缓冲区会传递到分析器。</span><span class="sxs-lookup"><span data-stu-id="a7015-281">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="a7015-282">因此，每次对输入进行一次分析。</span><span class="sxs-lookup"><span data-stu-id="a7015-282">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="a7015-283">Paste 方法之间的区别导致了不同的执行行为。</span><span class="sxs-lookup"><span data-stu-id="a7015-283">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="a7015-284">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="a7015-284">PasteAfter</span></span>

<span data-ttu-id="a7015-285">在光标后面粘贴剪贴板，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-285">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="a7015-286">Vi 命令模式： `<p>`</span><span class="sxs-lookup"><span data-stu-id="a7015-286">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="a7015-287">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="a7015-287">PasteBefore</span></span>

<span data-ttu-id="a7015-288">将剪贴板粘贴到光标之前，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-288">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="a7015-289">Vi 命令模式： `<P>`</span><span class="sxs-lookup"><span data-stu-id="a7015-289">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="a7015-290">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="a7015-290">PrependAndAccept</span></span>

<span data-ttu-id="a7015-291">预置 "#" 并接受该行。</span><span class="sxs-lookup"><span data-stu-id="a7015-291">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="a7015-292">Vi 命令模式： `<#>`</span><span class="sxs-lookup"><span data-stu-id="a7015-292">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="a7015-293">重做</span><span class="sxs-lookup"><span data-stu-id="a7015-293">Redo</span></span>

<span data-ttu-id="a7015-294">撤消撤消。</span><span class="sxs-lookup"><span data-stu-id="a7015-294">Undo an undo.</span></span>

- <span data-ttu-id="a7015-295">Cmd：`<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-295">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="a7015-296">Vi 插入模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-296">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="a7015-297">Vi 命令模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-297">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="a7015-298">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="a7015-298">RepeatLastCommand</span></span>

<span data-ttu-id="a7015-299">重复最后一次文本修改。</span><span class="sxs-lookup"><span data-stu-id="a7015-299">Repeat the last text modification.</span></span>

- <span data-ttu-id="a7015-300">Vi 命令模式： `<.>`</span><span class="sxs-lookup"><span data-stu-id="a7015-300">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="a7015-301">RevertLine</span><span class="sxs-lookup"><span data-stu-id="a7015-301">RevertLine</span></span>

<span data-ttu-id="a7015-302">将所有输入还原为当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-302">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="a7015-303">Cmd：`<Escape>`</span><span class="sxs-lookup"><span data-stu-id="a7015-303">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="a7015-304">Emacs： `<Alt+r>` ， `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="a7015-304">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="a7015-305">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="a7015-305">ShellBackwardKillWord</span></span>

<span data-ttu-id="a7015-306">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-306">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="a7015-307">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-307">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="a7015-308">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-308">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="a7015-309">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-309">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="a7015-310">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="a7015-310">ShellKillWord</span></span>

<span data-ttu-id="a7015-311">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-311">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="a7015-312">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-312">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="a7015-313">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-313">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="a7015-314">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-314">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="a7015-315">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="a7015-315">SwapCharacters</span></span>

<span data-ttu-id="a7015-316">交换当前字符和该字符之前的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-316">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="a7015-317">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="a7015-317">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="a7015-318">Vi 插入模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="a7015-318">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="a7015-319">Vi 命令模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="a7015-319">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="a7015-320">撤消</span><span class="sxs-lookup"><span data-stu-id="a7015-320">Undo</span></span>

<span data-ttu-id="a7015-321">撤消上一个编辑。</span><span class="sxs-lookup"><span data-stu-id="a7015-321">Undo a previous edit.</span></span>

- <span data-ttu-id="a7015-322">Cmd：`<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="a7015-322">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="a7015-323">Emacs： `<Ctrl+_>` ， `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="a7015-323">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="a7015-324">Vi 插入模式： `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="a7015-324">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="a7015-325">Vi 命令模式： `<Ctrl+z>` ， `<u>`</span><span class="sxs-lookup"><span data-stu-id="a7015-325">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="a7015-326">UndoAll</span><span class="sxs-lookup"><span data-stu-id="a7015-326">UndoAll</span></span>

<span data-ttu-id="a7015-327">撤消对行的所有以前的编辑。</span><span class="sxs-lookup"><span data-stu-id="a7015-327">Undo all previous edits for line.</span></span>

- <span data-ttu-id="a7015-328">Vi 命令模式： `<U>`</span><span class="sxs-lookup"><span data-stu-id="a7015-328">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="a7015-329">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="a7015-329">UnixWordRubout</span></span>

<span data-ttu-id="a7015-330">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-330">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="a7015-331">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-331">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="a7015-332">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="a7015-332">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a7015-333">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="a7015-333">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="a7015-334">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="a7015-334">ValidateAndAcceptLine</span></span>

<span data-ttu-id="a7015-335">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-335">Attempt to execute the current input.</span></span> <span data-ttu-id="a7015-336">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-336">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="a7015-337">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="a7015-337">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="a7015-338">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="a7015-338">ViAcceptLine</span></span>

<span data-ttu-id="a7015-339">接受行并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="a7015-339">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="a7015-340">Vi 命令模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a7015-340">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="a7015-341">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="a7015-341">ViAcceptLineOrExit</span></span>

<span data-ttu-id="a7015-342">与 Emacs 模式下的 DeleteCharOrExit 类似，但接受行而不是删除字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-342">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="a7015-343">Vi 插入模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="a7015-343">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="a7015-344">Vi 命令模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="a7015-344">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="a7015-345">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="a7015-345">ViAppendLine</span></span>

<span data-ttu-id="a7015-346">新行插入到当前行的下方。</span><span class="sxs-lookup"><span data-stu-id="a7015-346">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="a7015-347">Vi 命令模式： `<o>`</span><span class="sxs-lookup"><span data-stu-id="a7015-347">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="a7015-348">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-348">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="a7015-349">删除上一个词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="a7015-349">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="a7015-350">Vi 命令模式： `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="a7015-350">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="a7015-351">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-351">ViBackwardGlob</span></span>

<span data-ttu-id="a7015-352">将光标移回上一个词的开头，仅使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="a7015-352">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="a7015-353">Vi 命令模式： `<B>`</span><span class="sxs-lookup"><span data-stu-id="a7015-353">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="a7015-354">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="a7015-354">ViDeleteBrace</span></span>

<span data-ttu-id="a7015-355">查找匹配的大括号、圆括号或方括号，并删除其中的所有内容，包括大括号。</span><span class="sxs-lookup"><span data-stu-id="a7015-355">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="a7015-356">Vi 命令模式： `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="a7015-356">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="a7015-357">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-357">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="a7015-358">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-358">Delete to the end of the word.</span></span>

- <span data-ttu-id="a7015-359">Vi 命令模式： `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="a7015-359">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="a7015-360">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-360">ViDeleteGlob</span></span>

<span data-ttu-id="a7015-361">删除下一个 glob (空格分隔的单词) 。</span><span class="sxs-lookup"><span data-stu-id="a7015-361">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="a7015-362">Vi 命令模式： `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="a7015-362">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="a7015-363">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="a7015-363">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="a7015-364">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-364">Deletes until given character.</span></span>

- <span data-ttu-id="a7015-365">Vi 命令模式： `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="a7015-365">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="a7015-366">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-366">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="a7015-367">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-367">Deletes until given character.</span></span>

- <span data-ttu-id="a7015-368">Vi 命令模式： `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="a7015-368">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="a7015-369">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="a7015-369">ViDeleteToChar</span></span>

<span data-ttu-id="a7015-370">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-370">Deletes until given character.</span></span>

- <span data-ttu-id="a7015-371">Vi 命令模式： `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="a7015-371">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="a7015-372">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-372">ViDeleteToCharBackward</span></span>

<span data-ttu-id="a7015-373">向后删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-373">Deletes backwards until given character.</span></span>

- <span data-ttu-id="a7015-374">Vi 命令模式： `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="a7015-374">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="a7015-375">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="a7015-375">ViInsertAtBegining</span></span>

<span data-ttu-id="a7015-376">切换到插入模式，并将光标置于行首。</span><span class="sxs-lookup"><span data-stu-id="a7015-376">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="a7015-377">Vi 命令模式： `<I>`</span><span class="sxs-lookup"><span data-stu-id="a7015-377">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="a7015-378">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="a7015-378">ViInsertAtEnd</span></span>

<span data-ttu-id="a7015-379">切换到插入模式，并将光标置于行的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-379">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="a7015-380">Vi 命令模式： `<A>`</span><span class="sxs-lookup"><span data-stu-id="a7015-380">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="a7015-381">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="a7015-381">ViInsertLine</span></span>

<span data-ttu-id="a7015-382">在当前行的上方插入新行。</span><span class="sxs-lookup"><span data-stu-id="a7015-382">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="a7015-383">Vi 命令模式： `<O>`</span><span class="sxs-lookup"><span data-stu-id="a7015-383">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="a7015-384">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="a7015-384">ViInsertWithAppend</span></span>

<span data-ttu-id="a7015-385">从当前行位置追加。</span><span class="sxs-lookup"><span data-stu-id="a7015-385">Append from the current line position.</span></span>

- <span data-ttu-id="a7015-386">Vi 命令模式： `<a>`</span><span class="sxs-lookup"><span data-stu-id="a7015-386">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="a7015-387">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="a7015-387">ViInsertWithDelete</span></span>

<span data-ttu-id="a7015-388">删除当前字符并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="a7015-388">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="a7015-389">Vi 命令模式： `<s>`</span><span class="sxs-lookup"><span data-stu-id="a7015-389">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="a7015-390">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="a7015-390">ViJoinLines</span></span>

<span data-ttu-id="a7015-391">联接当前行和下一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-391">Joins the current line and the next line.</span></span>

- <span data-ttu-id="a7015-392">Vi 命令模式： `<J>`</span><span class="sxs-lookup"><span data-stu-id="a7015-392">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="a7015-393">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="a7015-393">ViReplaceLine</span></span>

<span data-ttu-id="a7015-394">擦除整个命令行。</span><span class="sxs-lookup"><span data-stu-id="a7015-394">Erase the entire command line.</span></span>

- <span data-ttu-id="a7015-395">Vi 命令模式： `<S>` ， `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="a7015-395">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="a7015-396">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="a7015-396">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="a7015-397">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-397">Replaces until given character.</span></span>

- <span data-ttu-id="a7015-398">Vi 命令模式： `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="a7015-398">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="a7015-399">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-399">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="a7015-400">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-400">Replaces until given character.</span></span>

- <span data-ttu-id="a7015-401">Vi 命令模式： `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="a7015-401">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="a7015-402">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="a7015-402">ViReplaceToChar</span></span>

<span data-ttu-id="a7015-403">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-403">Deletes until given character.</span></span>

- <span data-ttu-id="a7015-404">Vi 命令模式： `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="a7015-404">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="a7015-405">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-405">ViReplaceToCharBackward</span></span>

<span data-ttu-id="a7015-406">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-406">Replaces until given character.</span></span>

- <span data-ttu-id="a7015-407">Vi 命令模式： `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="a7015-407">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="a7015-408">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="a7015-408">ViYankBeginningOfLine</span></span>

<span data-ttu-id="a7015-409">从缓冲区的开头到游标的 Yank。</span><span class="sxs-lookup"><span data-stu-id="a7015-409">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="a7015-410">Vi 命令模式： `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="a7015-410">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="a7015-411">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-411">ViYankEndOfGlob</span></span>

<span data-ttu-id="a7015-412">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-412">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="a7015-413">Vi 命令模式： `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="a7015-413">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="a7015-414">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="a7015-414">ViYankEndOfWord</span></span>

<span data-ttu-id="a7015-415">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-415">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="a7015-416">Vi 命令模式： `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="a7015-416">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="a7015-417">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="a7015-417">ViYankLeft</span></span>

<span data-ttu-id="a7015-418">Yank 字符 (s) 光标左侧。</span><span class="sxs-lookup"><span data-stu-id="a7015-418">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="a7015-419">Vi 命令模式： `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="a7015-419">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="a7015-420">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="a7015-420">ViYankLine</span></span>

<span data-ttu-id="a7015-421">Yank 整个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="a7015-421">Yank the entire buffer.</span></span>

- <span data-ttu-id="a7015-422">Vi 命令模式： `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-422">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="a7015-423">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-423">ViYankNextGlob</span></span>

<span data-ttu-id="a7015-424">Yank 从 cursor 到下一个单词 () 的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-424">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="a7015-425">Vi 命令模式： `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="a7015-425">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="a7015-426">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="a7015-426">ViYankNextWord</span></span>

<span data-ttu-id="a7015-427">Yank 在游标后) 的单词 (。</span><span class="sxs-lookup"><span data-stu-id="a7015-427">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="a7015-428">Vi 命令模式： `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="a7015-428">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="a7015-429">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="a7015-429">ViYankPercent</span></span>

<span data-ttu-id="a7015-430">Yank 匹配的大括号。</span><span class="sxs-lookup"><span data-stu-id="a7015-430">Yank to/from matching brace.</span></span>

- <span data-ttu-id="a7015-431">Vi 命令模式： `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="a7015-431">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="a7015-432">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-432">ViYankPreviousGlob</span></span>

<span data-ttu-id="a7015-433">从单词 (开始，) 到游标。</span><span class="sxs-lookup"><span data-stu-id="a7015-433">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="a7015-434">Vi 命令模式： `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="a7015-434">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="a7015-435">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="a7015-435">ViYankPreviousWord</span></span>

<span data-ttu-id="a7015-436">Yank 在游标前)  (s。</span><span class="sxs-lookup"><span data-stu-id="a7015-436">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="a7015-437">Vi 命令模式： `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="a7015-437">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="a7015-438">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="a7015-438">ViYankRight</span></span>

<span data-ttu-id="a7015-439">Yank 字符 (s) 光标右侧和右侧。</span><span class="sxs-lookup"><span data-stu-id="a7015-439">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="a7015-440">Vi 命令模式： `<y,l>` ， `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a7015-440">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="a7015-441">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="a7015-441">ViYankToEndOfLine</span></span>

<span data-ttu-id="a7015-442">Yank 从游标到缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-442">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="a7015-443">Vi 命令模式： `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="a7015-443">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="a7015-444">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="a7015-444">ViYankToFirstChar</span></span>

<span data-ttu-id="a7015-445">从第一个非空白字符 Yank 到游标。</span><span class="sxs-lookup"><span data-stu-id="a7015-445">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="a7015-446">Vi 命令模式： `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="a7015-446">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="a7015-447">Yank</span><span class="sxs-lookup"><span data-stu-id="a7015-447">Yank</span></span>

<span data-ttu-id="a7015-448">将最近终止的文本添加到输入中。</span><span class="sxs-lookup"><span data-stu-id="a7015-448">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="a7015-449">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-449">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="a7015-450">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="a7015-450">YankLastArg</span></span>

<span data-ttu-id="a7015-451">Yank 上一个历史记录行中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="a7015-451">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="a7015-452">如果使用参数，则第一次调用时，其行为就像 YankNthArg。</span><span class="sxs-lookup"><span data-stu-id="a7015-452">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="a7015-453">如果多次调用，则会循环访问历史记录，而 arg 会将方向设置 (负反转方向。 ) </span><span class="sxs-lookup"><span data-stu-id="a7015-453">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="a7015-454">Cmd：`<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="a7015-454">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="a7015-455">Emacs： `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="a7015-455">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="a7015-456">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="a7015-456">YankNthArg</span></span>

<span data-ttu-id="a7015-457">Yank 从上一历史记录行) 命令后 (第一个参数。</span><span class="sxs-lookup"><span data-stu-id="a7015-457">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="a7015-458">对于参数，yank 从 0) 开始 (第 n 个参数，如果参数为负数，则从最后一个参数开始。</span><span class="sxs-lookup"><span data-stu-id="a7015-458">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="a7015-459">Emacs： `<Ctrl+Alt+y>` ， `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-459">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="a7015-460">YankPop</span><span class="sxs-lookup"><span data-stu-id="a7015-460">YankPop</span></span>

<span data-ttu-id="a7015-461">如果上一操作是 Yank 或 YankPop，则将以前的拔掉文本替换为下一个终止的文本。</span><span class="sxs-lookup"><span data-stu-id="a7015-461">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="a7015-462">Emacs： `<Alt+y>` ， `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="a7015-462">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="a7015-463">游标移动函数</span><span class="sxs-lookup"><span data-stu-id="a7015-463">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="a7015-464">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="a7015-464">BackwardChar</span></span>

<span data-ttu-id="a7015-465">将光标向左移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-465">Move the cursor one character to the left.</span></span> <span data-ttu-id="a7015-466">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-466">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="a7015-467">Cmd：`<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-467">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="a7015-468">Emacs： `<LeftArrow>` ， `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="a7015-468">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="a7015-469">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-469">BackwardWord</span></span>

<span data-ttu-id="a7015-470">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-470">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="a7015-471">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-471">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a7015-472">Cmd：`<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-472">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="a7015-473">Emacs： `<Alt+b>` ， `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="a7015-473">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="a7015-474">Vi 插入模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-474">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="a7015-475">Vi 命令模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-475">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="a7015-476">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="a7015-476">BeginningOfLine</span></span>

<span data-ttu-id="a7015-477">如果输入具有多个行，则移动到当前行的开头，或者，如果已位于行首，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-477">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="a7015-478">如果输入具有单行，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-478">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="a7015-479">Cmd：`<Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-479">Cmd: `<Home>`</span></span>
- <span data-ttu-id="a7015-480">Emacs： `<Home>` ， `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="a7015-480">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="a7015-481">Vi 插入模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-481">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="a7015-482">Vi 命令模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-482">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="a7015-483">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="a7015-483">EndOfLine</span></span>

<span data-ttu-id="a7015-484">如果输入包含多行，则移动到当前行的末尾，或者，如果已位于行尾，则转到输入的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-484">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="a7015-485">如果输入具有单行，则移动到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-485">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="a7015-486">Cmd：`<End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-486">Cmd: `<End>`</span></span>
- <span data-ttu-id="a7015-487">Emacs： `<End>` ， `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="a7015-487">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="a7015-488">Vi 插入模式： `<End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-488">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="a7015-489">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="a7015-489">ForwardChar</span></span>

<span data-ttu-id="a7015-490">将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-490">Move the cursor one character to the right.</span></span> <span data-ttu-id="a7015-491">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-491">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="a7015-492">Cmd：`<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-492">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="a7015-493">Emacs： `<RightArrow>` ， `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="a7015-493">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="a7015-494">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-494">ForwardWord</span></span>

<span data-ttu-id="a7015-495">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="a7015-496">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a7015-497">Emacs： `<Alt+f>` ， `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="a7015-497">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="a7015-498">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="a7015-498">GotoBrace</span></span>

<span data-ttu-id="a7015-499">中转到匹配的大括号、圆括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="a7015-499">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="a7015-500">Cmd：`<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a7015-500">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="a7015-501">Vi 插入模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a7015-501">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="a7015-502">Vi 命令模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a7015-502">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="a7015-503">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="a7015-503">GotoColumn</span></span>

<span data-ttu-id="a7015-504">转到 arg 指示的列。</span><span class="sxs-lookup"><span data-stu-id="a7015-504">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="a7015-505">Vi 命令模式： `<|>`</span><span class="sxs-lookup"><span data-stu-id="a7015-505">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="a7015-506">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="a7015-506">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="a7015-507">将光标移动到行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-507">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="a7015-508">Vi 命令模式： `<^>` ， `<_>`</span><span class="sxs-lookup"><span data-stu-id="a7015-508">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="a7015-509">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="a7015-509">MoveToEndOfLine</span></span>

<span data-ttu-id="a7015-510">将光标移到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-510">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="a7015-511">Vi 命令模式： `<End>` ， `<$>`</span><span class="sxs-lookup"><span data-stu-id="a7015-511">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="a7015-512">NextLine</span><span class="sxs-lookup"><span data-stu-id="a7015-512">NextLine</span></span>

<span data-ttu-id="a7015-513">将光标移到下一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-513">Move the cursor to the next line.</span></span>

- <span data-ttu-id="a7015-514">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-514">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="a7015-515">NextWord</span><span class="sxs-lookup"><span data-stu-id="a7015-515">NextWord</span></span>

<span data-ttu-id="a7015-516">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-516">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="a7015-517">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-517">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a7015-518">Cmd：`<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-518">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="a7015-519">Vi 插入模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-519">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="a7015-520">Vi 命令模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-520">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="a7015-521">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="a7015-521">NextWordEnd</span></span>

<span data-ttu-id="a7015-522">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="a7015-523">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-523">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a7015-524">Vi 命令模式： `<e>`</span><span class="sxs-lookup"><span data-stu-id="a7015-524">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="a7015-525">PreviousLine</span><span class="sxs-lookup"><span data-stu-id="a7015-525">PreviousLine</span></span>

<span data-ttu-id="a7015-526">将光标移到上一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-526">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="a7015-527">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-527">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="a7015-528">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-528">ShellBackwardWord</span></span>

<span data-ttu-id="a7015-529">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-529">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="a7015-530">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-530">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="a7015-531">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-531">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="a7015-532">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-532">ShellForwardWord</span></span>

<span data-ttu-id="a7015-533">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-533">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="a7015-534">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-534">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="a7015-535">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-535">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="a7015-536">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="a7015-536">ShellNextWord</span></span>

<span data-ttu-id="a7015-537">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="a7015-537">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="a7015-538">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-538">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="a7015-539">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-539">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="a7015-540">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="a7015-540">ViBackwardChar</span></span>

<span data-ttu-id="a7015-541">在 Vi 编辑模式下将光标左移一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-541">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="a7015-542">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-542">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="a7015-543">Vi 插入模式： `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-543">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="a7015-544">Vi 命令模式： `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="a7015-544">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="a7015-545">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-545">ViBackwardWord</span></span>

<span data-ttu-id="a7015-546">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-546">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="a7015-547">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-547">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a7015-548">Vi 命令模式： `<b>`</span><span class="sxs-lookup"><span data-stu-id="a7015-548">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="a7015-549">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="a7015-549">ViForwardChar</span></span>

<span data-ttu-id="a7015-550">在 Vi 编辑模式下将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-550">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="a7015-551">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-551">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="a7015-552">Vi 插入模式： `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-552">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="a7015-553">Vi 命令模式： `<RightArrow>` 、 `<Spacebar>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="a7015-553">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="a7015-554">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-554">ViEndOfGlob</span></span>

<span data-ttu-id="a7015-555">将光标移到单词的末尾，只使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="a7015-555">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="a7015-556">Vi 命令模式： `<E>`</span><span class="sxs-lookup"><span data-stu-id="a7015-556">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="a7015-557">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-557">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="a7015-558">移到上一个词的末尾，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="a7015-558">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="a7015-559">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-559">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="a7015-560">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="a7015-560">ViGotoBrace</span></span>

<span data-ttu-id="a7015-561">类似于 GotoBrace，但基于字符，而不是基于标记。</span><span class="sxs-lookup"><span data-stu-id="a7015-561">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="a7015-562">Vi 命令模式： `<%>`</span><span class="sxs-lookup"><span data-stu-id="a7015-562">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="a7015-563">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="a7015-563">ViNextGlob</span></span>

<span data-ttu-id="a7015-564">移到下一个单词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="a7015-564">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="a7015-565">Vi 命令模式： `<W>`</span><span class="sxs-lookup"><span data-stu-id="a7015-565">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="a7015-566">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="a7015-566">ViNextWord</span></span>

<span data-ttu-id="a7015-567">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-567">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="a7015-568">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="a7015-568">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a7015-569">Vi 命令模式： `<w>`</span><span class="sxs-lookup"><span data-stu-id="a7015-569">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="a7015-570">历史记录函数</span><span class="sxs-lookup"><span data-stu-id="a7015-570">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="a7015-571">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-571">BeginningOfHistory</span></span>

<span data-ttu-id="a7015-572">移到历史记录中的第一项。</span><span class="sxs-lookup"><span data-stu-id="a7015-572">Move to the first item in the history.</span></span>

- <span data-ttu-id="a7015-573">Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="a7015-573">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="a7015-574">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-574">ClearHistory</span></span>

<span data-ttu-id="a7015-575">清除 PSReadLine 中的历史记录。</span><span class="sxs-lookup"><span data-stu-id="a7015-575">Clears history in PSReadLine.</span></span> <span data-ttu-id="a7015-576">这不会影响 PowerShell 历史记录。</span><span class="sxs-lookup"><span data-stu-id="a7015-576">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="a7015-577">Cmd：`<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="a7015-577">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="a7015-578">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-578">EndOfHistory</span></span>

<span data-ttu-id="a7015-579">移到历史记录中 (当前输入) 的最后一项。</span><span class="sxs-lookup"><span data-stu-id="a7015-579">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="a7015-580">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="a7015-580">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="a7015-581">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-581">ForwardSearchHistory</span></span>

<span data-ttu-id="a7015-582">通过历史记录执行增量向前搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-582">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="a7015-583">Cmd：`<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a7015-583">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="a7015-584">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a7015-584">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="a7015-585">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-585">HistorySearchBackward</span></span>

<span data-ttu-id="a7015-586">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项，该匹配项与开始与输入和光标之间的字符匹配。</span><span class="sxs-lookup"><span data-stu-id="a7015-586">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="a7015-587">Cmd：`<F8>`</span><span class="sxs-lookup"><span data-stu-id="a7015-587">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="a7015-588">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="a7015-588">HistorySearchForward</span></span>

<span data-ttu-id="a7015-589">将当前输入替换为 PSReadLine 历史记录中与 start 与 input 和 cursor 之间的字符相匹配的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="a7015-589">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="a7015-590">Cmd：`<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="a7015-590">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="a7015-591">NextHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-591">NextHistory</span></span>

<span data-ttu-id="a7015-592">将当前输入替换为 PSReadLine 历史记录中的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="a7015-592">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="a7015-593">Cmd：`<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-593">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="a7015-594">Emacs： `<DownArrow>` ， `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="a7015-594">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="a7015-595">Vi 插入模式： `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-595">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="a7015-596">Vi 命令模式： `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="a7015-596">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="a7015-597">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-597">PreviousHistory</span></span>

<span data-ttu-id="a7015-598">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项。</span><span class="sxs-lookup"><span data-stu-id="a7015-598">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="a7015-599">Cmd：`<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-599">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="a7015-600">Emacs： `<UpArrow>` ， `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="a7015-600">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="a7015-601">Vi 插入模式： `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-601">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="a7015-602">Vi 命令模式： `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="a7015-602">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="a7015-603">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="a7015-603">ReverseSearchHistory</span></span>

<span data-ttu-id="a7015-604">通过历史记录执行增量向后搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-604">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="a7015-605">Cmd：`<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a7015-605">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="a7015-606">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a7015-606">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="a7015-607">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-607">ViSearchHistoryBackward</span></span>

<span data-ttu-id="a7015-608">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-608">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="a7015-609">Vi 插入模式： `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a7015-609">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="a7015-610">Vi 命令模式： `</>` ， `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a7015-610">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="a7015-611">完成函数</span><span class="sxs-lookup"><span data-stu-id="a7015-611">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="a7015-612">完成</span><span class="sxs-lookup"><span data-stu-id="a7015-612">Complete</span></span>

<span data-ttu-id="a7015-613">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="a7015-613">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="a7015-614">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="a7015-614">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="a7015-615">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="a7015-615">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="a7015-616">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-616">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="a7015-617">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="a7015-617">MenuComplete</span></span>

<span data-ttu-id="a7015-618">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="a7015-618">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="a7015-619">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="a7015-619">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="a7015-620">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="a7015-620">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="a7015-621">Cmd： `<Ctrl+@>` ， `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a7015-621">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="a7015-622">Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a7015-622">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="a7015-623">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="a7015-623">PossibleCompletions</span></span>

<span data-ttu-id="a7015-624">显示可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="a7015-624">Display the list of possible completions.</span></span>

- <span data-ttu-id="a7015-625">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="a7015-625">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="a7015-626">Vi 插入模式： `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a7015-626">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="a7015-627">Vi 命令模式： `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a7015-627">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="a7015-628">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="a7015-628">TabCompleteNext</span></span>

<span data-ttu-id="a7015-629">尝试使用下一个可用完成来完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="a7015-629">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="a7015-630">Cmd：`<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-630">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="a7015-631">Vi 命令模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-631">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="a7015-632">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="a7015-632">TabCompletePrevious</span></span>

<span data-ttu-id="a7015-633">尝试使用以前的可用完成功能完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="a7015-633">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="a7015-634">Cmd：`<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-634">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="a7015-635">Vi 命令模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-635">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="a7015-636">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="a7015-636">ViTabCompleteNext</span></span>

<span data-ttu-id="a7015-637">结束当前编辑组（如果需要），并调用 TabCompleteNext。</span><span class="sxs-lookup"><span data-stu-id="a7015-637">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="a7015-638">Vi 插入模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-638">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="a7015-639">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="a7015-639">ViTabCompletePrevious</span></span>

<span data-ttu-id="a7015-640">结束当前编辑组（如果需要），并调用 TabCompletePrevious。</span><span class="sxs-lookup"><span data-stu-id="a7015-640">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="a7015-641">Vi 插入模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="a7015-641">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="a7015-642">杂项函数</span><span class="sxs-lookup"><span data-stu-id="a7015-642">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="a7015-643">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="a7015-643">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="a7015-644">接受内嵌或所选建议的下一个单词。</span><span class="sxs-lookup"><span data-stu-id="a7015-644">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="a7015-645">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-645">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="a7015-646">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="a7015-646">AcceptSuggestion</span></span>

<span data-ttu-id="a7015-647">接受当前内联或所选的建议。</span><span class="sxs-lookup"><span data-stu-id="a7015-647">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="a7015-648">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-648">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="a7015-649">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="a7015-649">CaptureScreen</span></span>

<span data-ttu-id="a7015-650">启动交互屏幕捕获-向上/向下箭头选择 "线条"，将选定文本作为文本和 html 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="a7015-650">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="a7015-651">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-651">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="a7015-652">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="a7015-652">ClearScreen</span></span>

<span data-ttu-id="a7015-653">清除屏幕并在屏幕的顶部绘制当前线条。</span><span class="sxs-lookup"><span data-stu-id="a7015-653">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="a7015-654">Cmd：`<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a7015-654">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="a7015-655">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a7015-655">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="a7015-656">Vi 插入模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a7015-656">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="a7015-657">Vi 命令模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a7015-657">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="a7015-658">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="a7015-658">DigitArgument</span></span>

<span data-ttu-id="a7015-659">启动新的数字参数，使其传递到其他函数。</span><span class="sxs-lookup"><span data-stu-id="a7015-659">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="a7015-660">Cmd： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="a7015-660">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="a7015-661">Emacs： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="a7015-661">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="a7015-662">Vi 命令模式： `<0>` 、 `<1>` 、 `<2>` 、 `<3>` 、 `<4>` 、 `<5>` 、 `<6>` 、 `<7>` 、 `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="a7015-662">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="a7015-663">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="a7015-663">InvokePrompt</span></span>

<span data-ttu-id="a7015-664">清除当前提示符并调用 prompt 函数以重新显示提示符。</span><span class="sxs-lookup"><span data-stu-id="a7015-664">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="a7015-665">适用于更改状态的自定义密钥处理程序，例如更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="a7015-665">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="a7015-666">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-666">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="a7015-667">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="a7015-667">ScrollDisplayDown</span></span>

<span data-ttu-id="a7015-668">将显示向下滚动一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="a7015-668">Scroll the display down one screen.</span></span>

- <span data-ttu-id="a7015-669">Cmd：`<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a7015-669">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="a7015-670">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a7015-670">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="a7015-671">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="a7015-671">ScrollDisplayDownLine</span></span>

<span data-ttu-id="a7015-672">将显示向下滚动一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-672">Scroll the display down one line.</span></span>

- <span data-ttu-id="a7015-673">Cmd：`<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a7015-673">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="a7015-674">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a7015-674">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="a7015-675">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="a7015-675">ScrollDisplayToCursor</span></span>

<span data-ttu-id="a7015-676">将显示滚动到光标处。</span><span class="sxs-lookup"><span data-stu-id="a7015-676">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="a7015-677">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-677">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="a7015-678">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="a7015-678">ScrollDisplayTop</span></span>

<span data-ttu-id="a7015-679">向顶部滚动显示。</span><span class="sxs-lookup"><span data-stu-id="a7015-679">Scroll the display to the top.</span></span>

- <span data-ttu-id="a7015-680">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-680">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="a7015-681">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="a7015-681">ScrollDisplayUp</span></span>

<span data-ttu-id="a7015-682">将显示向上滚动一屏。</span><span class="sxs-lookup"><span data-stu-id="a7015-682">Scroll the display up one screen.</span></span>

- <span data-ttu-id="a7015-683">Cmd：`<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a7015-683">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="a7015-684">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a7015-684">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="a7015-685">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="a7015-685">ScrollDisplayUpLine</span></span>

<span data-ttu-id="a7015-686">将显示向上滚动一行。</span><span class="sxs-lookup"><span data-stu-id="a7015-686">Scroll the display up one line.</span></span>

- <span data-ttu-id="a7015-687">Cmd：`<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a7015-687">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="a7015-688">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a7015-688">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="a7015-689">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="a7015-689">SelfInsert</span></span>

<span data-ttu-id="a7015-690">插入密钥。</span><span class="sxs-lookup"><span data-stu-id="a7015-690">Insert the key.</span></span>

- <span data-ttu-id="a7015-691">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-691">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="a7015-692">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="a7015-692">ShowKeyBindings</span></span>

<span data-ttu-id="a7015-693">显示所有绑定键。</span><span class="sxs-lookup"><span data-stu-id="a7015-693">Show all bound keys.</span></span>

- <span data-ttu-id="a7015-694">Cmd：`<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a7015-694">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="a7015-695">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a7015-695">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="a7015-696">Vi 插入模式： `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a7015-696">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="a7015-697">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="a7015-697">ViCommandMode</span></span>

<span data-ttu-id="a7015-698">将当前运行模式从 Vi-Insert 切换到 Vi-Command。</span><span class="sxs-lookup"><span data-stu-id="a7015-698">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="a7015-699">Vi 插入模式： `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="a7015-699">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="a7015-700">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="a7015-700">ViDigitArgumentInChord</span></span>

<span data-ttu-id="a7015-701">启动新的数字参数，将其传递给其他函数，同时使用 vi 的鼠标左键之一。</span><span class="sxs-lookup"><span data-stu-id="a7015-701">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="a7015-702">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-702">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="a7015-703">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="a7015-703">ViEditVisually</span></span>

<span data-ttu-id="a7015-704">在 $env： EDITOR 或 $env：视觉对象指定的文本编辑器中编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="a7015-704">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="a7015-705">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="a7015-705">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="a7015-706">Vi 命令模式： `<v>`</span><span class="sxs-lookup"><span data-stu-id="a7015-706">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="a7015-707">ViExit</span><span class="sxs-lookup"><span data-stu-id="a7015-707">ViExit</span></span>

<span data-ttu-id="a7015-708">退出 shell。</span><span class="sxs-lookup"><span data-stu-id="a7015-708">Exits the shell.</span></span>

- <span data-ttu-id="a7015-709">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-709">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="a7015-710">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="a7015-710">ViInsertMode</span></span>

<span data-ttu-id="a7015-711">切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="a7015-711">Switch to Insert mode.</span></span>

- <span data-ttu-id="a7015-712">Vi 命令模式： `<i>`</span><span class="sxs-lookup"><span data-stu-id="a7015-712">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="a7015-713">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="a7015-713">WhatIsKey</span></span>

<span data-ttu-id="a7015-714">阅读密钥，并告诉我密钥的绑定内容。</span><span class="sxs-lookup"><span data-stu-id="a7015-714">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="a7015-715">Cmd：`<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a7015-715">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="a7015-716">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a7015-716">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="a7015-717">选择函数</span><span class="sxs-lookup"><span data-stu-id="a7015-717">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="a7015-718">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="a7015-718">ExchangePointAndMark</span></span>

<span data-ttu-id="a7015-719">将光标置于标记的位置，并将标记移到光标所在的位置。</span><span class="sxs-lookup"><span data-stu-id="a7015-719">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="a7015-720">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="a7015-720">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="a7015-721">SelectAll</span><span class="sxs-lookup"><span data-stu-id="a7015-721">SelectAll</span></span>

<span data-ttu-id="a7015-722">选择整行。</span><span class="sxs-lookup"><span data-stu-id="a7015-722">Select the entire line.</span></span>

- <span data-ttu-id="a7015-723">Cmd：`<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="a7015-723">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="a7015-724">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="a7015-724">SelectBackwardChar</span></span>

<span data-ttu-id="a7015-725">调整当前选定内容以包括前一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-725">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="a7015-726">Cmd：`<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-726">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="a7015-727">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-727">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="a7015-728">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="a7015-728">SelectBackwardsLine</span></span>

<span data-ttu-id="a7015-729">调整当前所选内容，使其包括从光标到行的开头。</span><span class="sxs-lookup"><span data-stu-id="a7015-729">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="a7015-730">Cmd：`<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-730">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="a7015-731">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="a7015-731">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="a7015-732">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-732">SelectBackwardWord</span></span>

<span data-ttu-id="a7015-733">调整当前所选内容以包含上一个词。</span><span class="sxs-lookup"><span data-stu-id="a7015-733">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="a7015-734">Cmd：`<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-734">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="a7015-735">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="a7015-735">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="a7015-736">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="a7015-736">SelectForwardChar</span></span>

<span data-ttu-id="a7015-737">调整当前所选内容以包含下一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-737">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="a7015-738">Cmd：`<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-738">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="a7015-739">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-739">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="a7015-740">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-740">SelectForwardWord</span></span>

<span data-ttu-id="a7015-741">使用 ForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="a7015-741">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="a7015-742">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="a7015-742">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="a7015-743">SelectLine</span><span class="sxs-lookup"><span data-stu-id="a7015-743">SelectLine</span></span>

<span data-ttu-id="a7015-744">调整当前所选内容，使其包括从光标到行尾的内容。</span><span class="sxs-lookup"><span data-stu-id="a7015-744">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="a7015-745">Cmd：`<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-745">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="a7015-746">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="a7015-746">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="a7015-747">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="a7015-747">SelectNextWord</span></span>

<span data-ttu-id="a7015-748">调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="a7015-748">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="a7015-749">Cmd：`<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a7015-749">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="a7015-750">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-750">SelectShellBackwardWord</span></span>

<span data-ttu-id="a7015-751">使用 ShellBackwardWord 调整当前所选内容，使其包含前一词。</span><span class="sxs-lookup"><span data-stu-id="a7015-751">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="a7015-752">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-752">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="a7015-753">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="a7015-753">SelectShellForwardWord</span></span>

<span data-ttu-id="a7015-754">使用 ShellForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="a7015-754">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="a7015-755">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-755">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="a7015-756">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="a7015-756">SelectShellNextWord</span></span>

<span data-ttu-id="a7015-757">使用 ShellNextWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="a7015-757">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="a7015-758">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-758">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="a7015-759">SetMark</span><span class="sxs-lookup"><span data-stu-id="a7015-759">SetMark</span></span>

<span data-ttu-id="a7015-760">标记光标的当前位置，以供后续编辑命令使用。</span><span class="sxs-lookup"><span data-stu-id="a7015-760">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="a7015-761">Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="a7015-761">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="a7015-762">预测 IntelliSense 函数</span><span class="sxs-lookup"><span data-stu-id="a7015-762">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="a7015-763">需要启用预测 IntelliSense 才能使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="a7015-763">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="a7015-764">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="a7015-764">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="a7015-765">接受预测 IntelliSense 中的下一个内嵌建议词。</span><span class="sxs-lookup"><span data-stu-id="a7015-765">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="a7015-766">此函数可以<kbd></kbd> + 通过运行以下命令与 Ctrl<kbd>F</kbd>绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-766">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="a7015-767">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="a7015-767">AcceptSuggestion</span></span>

<span data-ttu-id="a7015-768">当光标位于当前行的末尾时，通过按 <kbd>右箭头</kbd> ，接受预测 IntelliSense 中的当前内联建议。</span><span class="sxs-lookup"><span data-stu-id="a7015-768">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="a7015-769">搜索函数</span><span class="sxs-lookup"><span data-stu-id="a7015-769">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="a7015-770">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="a7015-770">CharacterSearch</span></span>

<span data-ttu-id="a7015-771">读取字符并向前搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="a7015-771">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="a7015-772">如果指定了参数，则向前搜索 (或向后) 对于第 n 个匹配项为负。</span><span class="sxs-lookup"><span data-stu-id="a7015-772">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="a7015-773">Cmd：`<F3>`</span><span class="sxs-lookup"><span data-stu-id="a7015-773">Cmd: `<F3>`</span></span>
- <span data-ttu-id="a7015-774">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a7015-774">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="a7015-775">Vi 插入模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="a7015-775">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="a7015-776">Vi 命令模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="a7015-776">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="a7015-777">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-777">CharacterSearchBackward</span></span>

<span data-ttu-id="a7015-778">读取字符并向后搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="a7015-778">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="a7015-779">如果指定了参数，则在第 n 个匹配项) 反向搜索时 (或转发。</span><span class="sxs-lookup"><span data-stu-id="a7015-779">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="a7015-780">Cmd：`<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="a7015-780">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="a7015-781">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="a7015-781">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="a7015-782">Vi 插入模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="a7015-782">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="a7015-783">Vi 命令模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="a7015-783">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="a7015-784">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="a7015-784">RepeatLastCharSearch</span></span>

<span data-ttu-id="a7015-785">重复上次记录的字符搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-785">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="a7015-786">Vi 命令模式： `<;>`</span><span class="sxs-lookup"><span data-stu-id="a7015-786">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="a7015-787">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="a7015-787">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="a7015-788">重复上次记录的字符搜索，但采用相反方向。</span><span class="sxs-lookup"><span data-stu-id="a7015-788">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="a7015-789">Vi 命令模式： `<,>`</span><span class="sxs-lookup"><span data-stu-id="a7015-789">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="a7015-790">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="a7015-790">RepeatSearch</span></span>

<span data-ttu-id="a7015-791">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-791">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="a7015-792">Vi 命令模式： `<n>`</span><span class="sxs-lookup"><span data-stu-id="a7015-792">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="a7015-793">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-793">RepeatSearchBackward</span></span>

<span data-ttu-id="a7015-794">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-794">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="a7015-795">Vi 命令模式： `<N>`</span><span class="sxs-lookup"><span data-stu-id="a7015-795">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="a7015-796">SearchChar</span><span class="sxs-lookup"><span data-stu-id="a7015-796">SearchChar</span></span>

<span data-ttu-id="a7015-797">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-797">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="a7015-798">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="a7015-798">This is for 't' functionality.</span></span>

- <span data-ttu-id="a7015-799">Vi 命令模式： `<f>`</span><span class="sxs-lookup"><span data-stu-id="a7015-799">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="a7015-800">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="a7015-800">SearchCharBackward</span></span>

<span data-ttu-id="a7015-801">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-801">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="a7015-802">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="a7015-802">This is for 'T' functionality.</span></span>

- <span data-ttu-id="a7015-803">Vi 命令模式： `<F>`</span><span class="sxs-lookup"><span data-stu-id="a7015-803">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="a7015-804">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="a7015-804">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="a7015-805">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-805">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="a7015-806">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="a7015-806">This is for 'T' functionality.</span></span>

- <span data-ttu-id="a7015-807">Vi 命令模式： `<T>`</span><span class="sxs-lookup"><span data-stu-id="a7015-807">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="a7015-808">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="a7015-808">SearchCharWithBackoff</span></span>

<span data-ttu-id="a7015-809">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-809">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="a7015-810">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="a7015-810">This is for 't' functionality.</span></span>

- <span data-ttu-id="a7015-811">Vi 命令模式： `<t>`</span><span class="sxs-lookup"><span data-stu-id="a7015-811">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="a7015-812">SearchForward</span><span class="sxs-lookup"><span data-stu-id="a7015-812">SearchForward</span></span>

<span data-ttu-id="a7015-813">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="a7015-813">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="a7015-814">Vi 插入模式： `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a7015-814">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="a7015-815">Vi 命令模式： `<?>` ， `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a7015-815">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="a7015-816">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="a7015-816">Custom Key Bindings</span></span>

<span data-ttu-id="a7015-817">PSReadLine 支持使用 cmdlet 的自定义键绑定 `Set-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="a7015-817">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="a7015-818">大多数自定义键绑定调用上述函数之一，例如</span><span class="sxs-lookup"><span data-stu-id="a7015-818">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="a7015-819">可以将 ScriptBlock 绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="a7015-819">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="a7015-820">ScriptBlock 可以执行任何所需的操作。</span><span class="sxs-lookup"><span data-stu-id="a7015-820">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="a7015-821">一些有用的示例包括</span><span class="sxs-lookup"><span data-stu-id="a7015-821">Some useful examples include</span></span>

- <span data-ttu-id="a7015-822">编辑命令行</span><span class="sxs-lookup"><span data-stu-id="a7015-822">edit the command line</span></span>
- <span data-ttu-id="a7015-823">打开新窗口 (例如，帮助) </span><span class="sxs-lookup"><span data-stu-id="a7015-823">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="a7015-824">更改目录而不更改命令行</span><span class="sxs-lookup"><span data-stu-id="a7015-824">change directories without changing the command line</span></span>

<span data-ttu-id="a7015-825">ScriptBlock 接收两个参数：</span><span class="sxs-lookup"><span data-stu-id="a7015-825">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="a7015-826">`$key` -一个作为触发自定义绑定的密钥的 **[ConsoleKeyInfo]** 对象。</span><span class="sxs-lookup"><span data-stu-id="a7015-826">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="a7015-827">如果将相同的 ScriptBlock 绑定到多个键，并且需要根据关键字执行不同的操作，则可以选中 $key。</span><span class="sxs-lookup"><span data-stu-id="a7015-827">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="a7015-828">许多自定义绑定会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="a7015-828">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="a7015-829">`$arg` -任意参数。</span><span class="sxs-lookup"><span data-stu-id="a7015-829">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="a7015-830">大多数情况下，这将是用户从键绑定 DigitArgument 传递的整数参数。</span><span class="sxs-lookup"><span data-stu-id="a7015-830">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="a7015-831">如果绑定不接受参数，则忽略此参数是合理的。</span><span class="sxs-lookup"><span data-stu-id="a7015-831">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="a7015-832">我们来看一个示例，该示例将一个命令行添加到历史记录中，而不执行它。</span><span class="sxs-lookup"><span data-stu-id="a7015-832">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="a7015-833">如果您认为您忘记了某些事情，但又不想重新输入您已经输入的命令行，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="a7015-833">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

<span data-ttu-id="a7015-834">你可以在 PSReadLine 模块文件夹中安装的文件中查看更多示例 `SamplePSReadLineProfile.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="a7015-834">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="a7015-835">大多数键绑定使用一些 helper 函数来编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="a7015-835">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="a7015-836">下一节将介绍这些 Api。</span><span class="sxs-lookup"><span data-stu-id="a7015-836">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="a7015-837">自定义键绑定支持 Api</span><span class="sxs-lookup"><span data-stu-id="a7015-837">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="a7015-838">以下函数是 PSConsoleReadLine 中的公共函数，但不能直接绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="a7015-838">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="a7015-839">大多数在自定义键绑定中很有用。</span><span class="sxs-lookup"><span data-stu-id="a7015-839">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="a7015-840">向历史记录中添加一个命令行而不执行它。</span><span class="sxs-lookup"><span data-stu-id="a7015-840">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="a7015-841">清除终止环。</span><span class="sxs-lookup"><span data-stu-id="a7015-841">Clear the kill-ring.</span></span>  <span data-ttu-id="a7015-842">这主要用于测试。</span><span class="sxs-lookup"><span data-stu-id="a7015-842">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="a7015-843">从开始删除长度字符。</span><span class="sxs-lookup"><span data-stu-id="a7015-843">Delete length characters from start.</span></span>  <span data-ttu-id="a7015-844">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="a7015-844">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="a7015-845">根据用户首选项执行 Ding 操作。</span><span class="sxs-lookup"><span data-stu-id="a7015-845">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="a7015-846">这两个函数检索有关输入缓冲区的当前状态的有用信息。</span><span class="sxs-lookup"><span data-stu-id="a7015-846">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="a7015-847">第一种方案更常见用于简单情况。</span><span class="sxs-lookup"><span data-stu-id="a7015-847">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="a7015-848">如果绑定使用 Ast 执行更高级的操作，则会使用第二个。</span><span class="sxs-lookup"><span data-stu-id="a7015-848">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="a7015-849">这两个函数由使用 `Get-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="a7015-849">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="a7015-850">第一个用于获取所有键绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-850">The first is used to get all key bindings.</span></span> <span data-ttu-id="a7015-851">第二个用于获取特定的键绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-851">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="a7015-852">此函数由 Get-PSReadLineOption 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="a7015-852">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="a7015-853">如果未在命令行上进行选择，则将在 "开始" 和 "长度" 中返回-1。</span><span class="sxs-lookup"><span data-stu-id="a7015-853">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="a7015-854">如果命令行上有选择，则返回选定内容的开始和长度。</span><span class="sxs-lookup"><span data-stu-id="a7015-854">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="a7015-855">在光标处插入字符或字符串。</span><span class="sxs-lookup"><span data-stu-id="a7015-855">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="a7015-856">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="a7015-856">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="a7015-857">这是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="a7015-857">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="a7015-858">它不支持递归，因此在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="a7015-858">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="a7015-859">此函数由 Remove-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="a7015-859">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="a7015-860">替换部分输入。</span><span class="sxs-lookup"><span data-stu-id="a7015-860">Replace some of the input.</span></span> <span data-ttu-id="a7015-861">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="a7015-861">This operation supports undo/redo.</span></span> <span data-ttu-id="a7015-862">这优先于删除后再执行 Insert，因为它被视为单个操作来撤消。</span><span class="sxs-lookup"><span data-stu-id="a7015-862">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="a7015-863">将光标移动到给定偏移量。</span><span class="sxs-lookup"><span data-stu-id="a7015-863">Move the cursor to the given offset.</span></span> <span data-ttu-id="a7015-864">不跟踪游标移动以便撤消。</span><span class="sxs-lookup"><span data-stu-id="a7015-864">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="a7015-865">此函数是 cmdlet PSReadLineOption 使用的帮助器方法，但可能对要临时更改设置的自定义密钥绑定很有用。</span><span class="sxs-lookup"><span data-stu-id="a7015-865">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="a7015-866">此帮助器方法用于接受 DigitArgument 的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="a7015-866">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="a7015-867">典型调用如下所示</span><span class="sxs-lookup"><span data-stu-id="a7015-867">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="a7015-868">备注</span><span class="sxs-lookup"><span data-stu-id="a7015-868">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="a7015-869">命令历史记录</span><span class="sxs-lookup"><span data-stu-id="a7015-869">Command History</span></span>

<span data-ttu-id="a7015-870">PSReadLine 维护一个历史记录文件，其中包含在命令行中输入的所有命令和数据。</span><span class="sxs-lookup"><span data-stu-id="a7015-870">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="a7015-871">这可能包含敏感数据（包括密码）。</span><span class="sxs-lookup"><span data-stu-id="a7015-871">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="a7015-872">例如，如果使用 cmdlet，则 `ConvertTo-SecureString` 密码将作为纯文本记录到历史记录文件中。</span><span class="sxs-lookup"><span data-stu-id="a7015-872">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="a7015-873">历史记录文件是一个名为的文件 `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="a7015-873">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="a7015-874">在 Windows 系统上，历史记录文件存储在中 `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="a7015-874">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="a7015-875">在非 Windows 系统上，历史记录文件存储在 `$env:XDG_DATA_HOME/powershell/PSReadLine` 或上 `$env:HOME/.local/share/powershell/PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="a7015-875">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="a7015-876">参与 PSReadLine 的反馈 &</span><span class="sxs-lookup"><span data-stu-id="a7015-876">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="a7015-877">GitHub 上的 PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a7015-877">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="a7015-878">可在 GitHub 页上随意提交拉取请求或提交反馈。</span><span class="sxs-lookup"><span data-stu-id="a7015-878">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7015-879">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7015-879">See Also</span></span>

<span data-ttu-id="a7015-880">PSReadLine 会受到 GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) 库的严重影响。</span><span class="sxs-lookup"><span data-stu-id="a7015-880">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
