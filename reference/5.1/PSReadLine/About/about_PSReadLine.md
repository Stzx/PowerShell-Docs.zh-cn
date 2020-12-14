---
description: PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于 PSReadLine
ms.openlocfilehash: 25fc3a9a814728057b1ebc7e721d3fba84ae72c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692303"
---
# <a name="psreadline"></a><span data-ttu-id="f9411-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f9411-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="f9411-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f9411-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="f9411-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="f9411-106">Short Description</span></span>

<span data-ttu-id="f9411-107">PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="f9411-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="f9411-108">详细说明</span><span class="sxs-lookup"><span data-stu-id="f9411-108">Long Description</span></span>

<span data-ttu-id="f9411-109">PSReadLine 2.0 为 PowerShell 控制台提供了强大的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="f9411-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="f9411-110">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="f9411-110">It provides:</span></span>

- <span data-ttu-id="f9411-111">命令行的语法着色</span><span class="sxs-lookup"><span data-stu-id="f9411-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="f9411-112">语法错误的直观指示</span><span class="sxs-lookup"><span data-stu-id="f9411-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="f9411-113"> (编辑和历史记录的更好的多行体验) </span><span class="sxs-lookup"><span data-stu-id="f9411-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="f9411-114">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="f9411-114">Customizable key bindings</span></span>
- <span data-ttu-id="f9411-115">Cmd 和 Emacs 模式</span><span class="sxs-lookup"><span data-stu-id="f9411-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="f9411-116">许多配置选项</span><span class="sxs-lookup"><span data-stu-id="f9411-116">Many configuration options</span></span>
- <span data-ttu-id="f9411-117">在 Cmd 模式下，Bash 样式完成 (可选，默认值为 Emacs 模式) </span><span class="sxs-lookup"><span data-stu-id="f9411-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="f9411-118">Emacs yank/kill 循环</span><span class="sxs-lookup"><span data-stu-id="f9411-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="f9411-119">基于 PowerShell 令牌的 "word" 移动和终止</span><span class="sxs-lookup"><span data-stu-id="f9411-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="f9411-120">PSReadLine 要求安装 PowerShell 3.0 或更高版本，以及控制台主机。</span><span class="sxs-lookup"><span data-stu-id="f9411-120">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="f9411-121">它在 PowerShell ISE 中不起作用。</span><span class="sxs-lookup"><span data-stu-id="f9411-121">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="f9411-122">它在 Visual Studio Code 的控制台中工作。</span><span class="sxs-lookup"><span data-stu-id="f9411-122">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="f9411-123">类 **[PSConsoleReadLine]** 中提供了以下函数。</span><span class="sxs-lookup"><span data-stu-id="f9411-123">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="f9411-124">基本编辑函数</span><span class="sxs-lookup"><span data-stu-id="f9411-124">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="f9411-125">中止</span><span class="sxs-lookup"><span data-stu-id="f9411-125">Abort</span></span>

<span data-ttu-id="f9411-126">中止当前操作，例如增量历史记录搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-126">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="f9411-127">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="f9411-127">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="f9411-128">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="f9411-128">AcceptAndGetNext</span></span>

<span data-ttu-id="f9411-129">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-129">Attempt to execute the current input.</span></span> <span data-ttu-id="f9411-130">如果可以 (如 AcceptLine) 执行，则在下一次调用 ReadLine 时，从历史记录中撤回下一项。</span><span class="sxs-lookup"><span data-stu-id="f9411-130">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="f9411-131">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="f9411-131">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="f9411-132">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="f9411-132">AcceptLine</span></span>

<span data-ttu-id="f9411-133">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-133">Attempt to execute the current input.</span></span> <span data-ttu-id="f9411-134">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-134">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f9411-135">Cmd：`<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-135">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="f9411-136">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-136">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="f9411-137">Vi 插入模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-137">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="f9411-138">AddLine</span><span class="sxs-lookup"><span data-stu-id="f9411-138">AddLine</span></span>

<span data-ttu-id="f9411-139">继续提示显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-139">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="f9411-140">这可用于将多行输入作为单个命令输入，即使单个行自动完成输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="f9411-140">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="f9411-141">Cmd：`<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-141">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f9411-142">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-142">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f9411-143">Vi 插入模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-143">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f9411-144">Vi 命令模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-144">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="f9411-145">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="f9411-145">BackwardDeleteChar</span></span>

<span data-ttu-id="f9411-146">删除光标前面的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-146">Delete the character before the cursor.</span></span>

- <span data-ttu-id="f9411-147">Cmd： `<Backspace>` ， `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f9411-147">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f9411-148">Emacs： `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f9411-148">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f9411-149">Vi 插入模式： `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f9411-149">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="f9411-150">Vi 命令模式： `<X>` ， `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="f9411-150">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="f9411-151">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="f9411-151">BackwardDeleteLine</span></span>

<span data-ttu-id="f9411-152">与 BackwardKillLine 一样，从点到行的开头删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-152">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f9411-153">Cmd：`<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-153">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f9411-154">Vi 插入模式： `<Ctrl+u>` ， `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-154">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f9411-155">Vi 命令模式： `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="f9411-155">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="f9411-156">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="f9411-156">BackwardDeleteWord</span></span>

<span data-ttu-id="f9411-157">删除上一个词。</span><span class="sxs-lookup"><span data-stu-id="f9411-157">Deletes the previous word.</span></span>

- <span data-ttu-id="f9411-158">Vi 命令模式： `<Ctrl+w>` ， `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="f9411-158">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="f9411-159">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="f9411-159">BackwardKillLine</span></span>

<span data-ttu-id="f9411-160">清除输入从输入开始到光标。</span><span class="sxs-lookup"><span data-stu-id="f9411-160">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="f9411-161">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-161">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f9411-162">Emacs： `<Ctrl+u>` ， `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f9411-162">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="f9411-163">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="f9411-163">BackwardKillWord</span></span>

<span data-ttu-id="f9411-164">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-164">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f9411-165">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-165">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f9411-166">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-166">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f9411-167">Cmd：`<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f9411-167">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="f9411-168">Emacs： `<Alt+Backspace>` ， `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f9411-168">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="f9411-169">Vi 插入模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f9411-169">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="f9411-170">Vi 命令模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f9411-170">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="f9411-171">CancelLine</span><span class="sxs-lookup"><span data-stu-id="f9411-171">CancelLine</span></span>

<span data-ttu-id="f9411-172">取消当前输入，将输入保留在屏幕上，但返回到主机以便再次计算提示。</span><span class="sxs-lookup"><span data-stu-id="f9411-172">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="f9411-173">Vi 插入模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f9411-173">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f9411-174">Vi 命令模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f9411-174">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="f9411-175">复制</span><span class="sxs-lookup"><span data-stu-id="f9411-175">Copy</span></span>

<span data-ttu-id="f9411-176">将所选区域复制到系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f9411-176">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="f9411-177">如果未选择区域，则复制整行。</span><span class="sxs-lookup"><span data-stu-id="f9411-177">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="f9411-178">Cmd：`<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="f9411-178">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="f9411-179">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="f9411-179">CopyOrCancelLine</span></span>

<span data-ttu-id="f9411-180">如果选择了文本，请将其复制到剪贴板，否则取消该行。</span><span class="sxs-lookup"><span data-stu-id="f9411-180">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="f9411-181">Cmd：`<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f9411-181">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f9411-182">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f9411-182">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="f9411-183">剪切</span><span class="sxs-lookup"><span data-stu-id="f9411-183">Cut</span></span>

<span data-ttu-id="f9411-184">删除所选区域将删除的文本放入系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f9411-184">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="f9411-185">Cmd：`<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f9411-185">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="f9411-186">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="f9411-186">DeleteChar</span></span>

<span data-ttu-id="f9411-187">删除光标下的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-187">Delete the character under the cursor.</span></span>

- <span data-ttu-id="f9411-188">Cmd：`<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f9411-188">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="f9411-189">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f9411-189">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="f9411-190">Vi 插入模式： `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f9411-190">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="f9411-191">Vi 命令模式： `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="f9411-191">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="f9411-192">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="f9411-192">DeleteCharOrExit</span></span>

<span data-ttu-id="f9411-193">删除光标下的字符; 如果行为空，则退出该过程。</span><span class="sxs-lookup"><span data-stu-id="f9411-193">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="f9411-194">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f9411-194">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="f9411-195">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="f9411-195">DeleteEndOfWord</span></span>

<span data-ttu-id="f9411-196">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-196">Delete to the end of the word.</span></span>

- <span data-ttu-id="f9411-197">Vi 命令模式： `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="f9411-197">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="f9411-198">Deleteline.invoke</span><span class="sxs-lookup"><span data-stu-id="f9411-198">DeleteLine</span></span>

<span data-ttu-id="f9411-199">删除当前行，启用 "撤消"。</span><span class="sxs-lookup"><span data-stu-id="f9411-199">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="f9411-200">Vi 命令模式： `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="f9411-200">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="f9411-201">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="f9411-201">DeleteLineToFirstChar</span></span>

<span data-ttu-id="f9411-202">删除从光标到行的第一个非空白字符的文本。</span><span class="sxs-lookup"><span data-stu-id="f9411-202">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="f9411-203">Vi 命令模式： `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="f9411-203">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="f9411-204">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="f9411-204">DeleteToEnd</span></span>

<span data-ttu-id="f9411-205">删除到行的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-205">Delete to the end of the line.</span></span>

- <span data-ttu-id="f9411-206">Vi 命令模式： `<D>` ， `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="f9411-206">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="f9411-207">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="f9411-207">DeleteWord</span></span>

<span data-ttu-id="f9411-208">删除下一个词。</span><span class="sxs-lookup"><span data-stu-id="f9411-208">Delete the next word.</span></span>

- <span data-ttu-id="f9411-209">Vi 命令模式： `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="f9411-209">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="f9411-210">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="f9411-210">ForwardDeleteLine</span></span>

<span data-ttu-id="f9411-211">与 ForwardKillLine 一样，从点到行尾删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-211">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f9411-212">Cmd：`<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-212">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f9411-213">Vi 插入模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-213">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f9411-214">Vi 命令模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-214">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="f9411-215">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="f9411-215">InsertLineAbove</span></span>

<span data-ttu-id="f9411-216">在当前行的上方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="f9411-216">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f9411-217">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-217">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f9411-218">Cmd：`<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-218">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="f9411-219">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="f9411-219">InsertLineBelow</span></span>

<span data-ttu-id="f9411-220">在当前行下方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="f9411-220">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f9411-221">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-221">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f9411-222">Cmd：`<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-222">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="f9411-223">InvertCase</span><span class="sxs-lookup"><span data-stu-id="f9411-223">InvertCase</span></span>

<span data-ttu-id="f9411-224">反转当前字符的大小写，并移到下一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-224">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="f9411-225">Vi 命令模式： `<~>`</span><span class="sxs-lookup"><span data-stu-id="f9411-225">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="f9411-226">KillLine</span><span class="sxs-lookup"><span data-stu-id="f9411-226">KillLine</span></span>

<span data-ttu-id="f9411-227">清除从光标到输入末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-227">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="f9411-228">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-228">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f9411-229">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="f9411-229">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="f9411-230">KillRegion</span><span class="sxs-lookup"><span data-stu-id="f9411-230">KillRegion</span></span>

<span data-ttu-id="f9411-231">终止光标和标记之间的文本。</span><span class="sxs-lookup"><span data-stu-id="f9411-231">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="f9411-232">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-232">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="f9411-233">KillWord</span><span class="sxs-lookup"><span data-stu-id="f9411-233">KillWord</span></span>

<span data-ttu-id="f9411-234">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-234">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f9411-235">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-235">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f9411-236">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-236">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f9411-237">Cmd：`<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f9411-237">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f9411-238">Emacs： `<Alt+d>` ， `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="f9411-238">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="f9411-239">Vi 插入模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f9411-239">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f9411-240">Vi 命令模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f9411-240">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="f9411-241">粘贴</span><span class="sxs-lookup"><span data-stu-id="f9411-241">Paste</span></span>

<span data-ttu-id="f9411-242">粘贴系统剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="f9411-242">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="f9411-243">Cmd： `<Ctrl+v>` ， `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="f9411-243">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="f9411-244">Vi 插入模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f9411-244">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="f9411-245">Vi 命令模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f9411-245">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9411-246">使用 **Paste** 函数时，剪贴板缓冲区的全部内容将粘贴到 PSReadLine 的输入缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="f9411-246">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="f9411-247">然后，将输入缓冲区传递到 PowerShell 分析器。</span><span class="sxs-lookup"><span data-stu-id="f9411-247">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="f9411-248">使用控制台应用程序的 **右键单击** 粘贴方法粘贴的输入会一次复制到输入缓冲区中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-248">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="f9411-249">复制换行符时，输入缓冲区会传递到分析器。</span><span class="sxs-lookup"><span data-stu-id="f9411-249">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="f9411-250">因此，每次对输入进行一次分析。</span><span class="sxs-lookup"><span data-stu-id="f9411-250">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="f9411-251">Paste 方法之间的区别导致了不同的执行行为。</span><span class="sxs-lookup"><span data-stu-id="f9411-251">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="f9411-252">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="f9411-252">PasteAfter</span></span>

<span data-ttu-id="f9411-253">在光标后面粘贴剪贴板，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-253">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f9411-254">Vi 命令模式： `<p>`</span><span class="sxs-lookup"><span data-stu-id="f9411-254">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="f9411-255">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="f9411-255">PasteBefore</span></span>

<span data-ttu-id="f9411-256">将剪贴板粘贴到光标之前，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-256">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f9411-257">Vi 命令模式： `<P>`</span><span class="sxs-lookup"><span data-stu-id="f9411-257">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="f9411-258">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="f9411-258">PrependAndAccept</span></span>

<span data-ttu-id="f9411-259">预置 "#" 并接受该行。</span><span class="sxs-lookup"><span data-stu-id="f9411-259">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="f9411-260">Vi 命令模式： `<#>`</span><span class="sxs-lookup"><span data-stu-id="f9411-260">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="f9411-261">重做</span><span class="sxs-lookup"><span data-stu-id="f9411-261">Redo</span></span>

<span data-ttu-id="f9411-262">撤消撤消。</span><span class="sxs-lookup"><span data-stu-id="f9411-262">Undo an undo.</span></span>

- <span data-ttu-id="f9411-263">Cmd：`<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-263">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f9411-264">Vi 插入模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-264">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f9411-265">Vi 命令模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-265">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="f9411-266">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="f9411-266">RepeatLastCommand</span></span>

<span data-ttu-id="f9411-267">重复最后一次文本修改。</span><span class="sxs-lookup"><span data-stu-id="f9411-267">Repeat the last text modification.</span></span>

- <span data-ttu-id="f9411-268">Vi 命令模式： `<.>`</span><span class="sxs-lookup"><span data-stu-id="f9411-268">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="f9411-269">RevertLine</span><span class="sxs-lookup"><span data-stu-id="f9411-269">RevertLine</span></span>

<span data-ttu-id="f9411-270">将所有输入还原为当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-270">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="f9411-271">Cmd：`<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f9411-271">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="f9411-272">Emacs： `<Alt+r>` ， `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="f9411-272">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="f9411-273">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="f9411-273">ShellBackwardKillWord</span></span>

<span data-ttu-id="f9411-274">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-274">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f9411-275">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-275">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f9411-276">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-276">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f9411-277">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-277">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="f9411-278">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="f9411-278">ShellKillWord</span></span>

<span data-ttu-id="f9411-279">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-279">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f9411-280">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-280">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f9411-281">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-281">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f9411-282">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-282">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="f9411-283">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="f9411-283">SwapCharacters</span></span>

<span data-ttu-id="f9411-284">交换当前字符和该字符之前的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-284">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="f9411-285">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f9411-285">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f9411-286">Vi 插入模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f9411-286">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f9411-287">Vi 命令模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f9411-287">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="f9411-288">撤消</span><span class="sxs-lookup"><span data-stu-id="f9411-288">Undo</span></span>

<span data-ttu-id="f9411-289">撤消上一个编辑。</span><span class="sxs-lookup"><span data-stu-id="f9411-289">Undo a previous edit.</span></span>

- <span data-ttu-id="f9411-290">Cmd：`<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f9411-290">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f9411-291">Emacs： `<Ctrl+_>` ， `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="f9411-291">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="f9411-292">Vi 插入模式： `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f9411-292">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f9411-293">Vi 命令模式： `<Ctrl+z>` ， `<u>`</span><span class="sxs-lookup"><span data-stu-id="f9411-293">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="f9411-294">UndoAll</span><span class="sxs-lookup"><span data-stu-id="f9411-294">UndoAll</span></span>

<span data-ttu-id="f9411-295">撤消对行的所有以前的编辑。</span><span class="sxs-lookup"><span data-stu-id="f9411-295">Undo all previous edits for line.</span></span>

- <span data-ttu-id="f9411-296">Vi 命令模式： `<U>`</span><span class="sxs-lookup"><span data-stu-id="f9411-296">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="f9411-297">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="f9411-297">UnixWordRubout</span></span>

<span data-ttu-id="f9411-298">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-298">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f9411-299">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-299">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f9411-300">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="f9411-300">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f9411-301">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="f9411-301">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="f9411-302">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="f9411-302">ValidateAndAcceptLine</span></span>

<span data-ttu-id="f9411-303">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-303">Attempt to execute the current input.</span></span> <span data-ttu-id="f9411-304">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-304">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f9411-305">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="f9411-305">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="f9411-306">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="f9411-306">ViAcceptLine</span></span>

<span data-ttu-id="f9411-307">接受行并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="f9411-307">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="f9411-308">Vi 命令模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f9411-308">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="f9411-309">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="f9411-309">ViAcceptLineOrExit</span></span>

<span data-ttu-id="f9411-310">与 Emacs 模式下的 DeleteCharOrExit 类似，但接受行而不是删除字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-310">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="f9411-311">Vi 插入模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f9411-311">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="f9411-312">Vi 命令模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f9411-312">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="f9411-313">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="f9411-313">ViAppendLine</span></span>

<span data-ttu-id="f9411-314">新行插入到当前行的下方。</span><span class="sxs-lookup"><span data-stu-id="f9411-314">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="f9411-315">Vi 命令模式： `<o>`</span><span class="sxs-lookup"><span data-stu-id="f9411-315">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="f9411-316">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-316">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="f9411-317">删除上一个词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="f9411-317">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="f9411-318">Vi 命令模式： `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="f9411-318">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="f9411-319">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-319">ViBackwardGlob</span></span>

<span data-ttu-id="f9411-320">将光标移回上一个词的开头，仅使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="f9411-320">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f9411-321">Vi 命令模式： `<B>`</span><span class="sxs-lookup"><span data-stu-id="f9411-321">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="f9411-322">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="f9411-322">ViDeleteBrace</span></span>

<span data-ttu-id="f9411-323">查找匹配的大括号、圆括号或方括号，并删除其中的所有内容，包括大括号。</span><span class="sxs-lookup"><span data-stu-id="f9411-323">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="f9411-324">Vi 命令模式： `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="f9411-324">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="f9411-325">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-325">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="f9411-326">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-326">Delete to the end of the word.</span></span>

- <span data-ttu-id="f9411-327">Vi 命令模式： `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="f9411-327">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="f9411-328">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-328">ViDeleteGlob</span></span>

<span data-ttu-id="f9411-329">删除下一个 glob (空格分隔的单词) 。</span><span class="sxs-lookup"><span data-stu-id="f9411-329">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="f9411-330">Vi 命令模式： `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="f9411-330">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="f9411-331">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="f9411-331">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="f9411-332">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-332">Deletes until given character.</span></span>

- <span data-ttu-id="f9411-333">Vi 命令模式： `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="f9411-333">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="f9411-334">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-334">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="f9411-335">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-335">Deletes until given character.</span></span>

- <span data-ttu-id="f9411-336">Vi 命令模式： `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="f9411-336">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="f9411-337">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="f9411-337">ViDeleteToChar</span></span>

<span data-ttu-id="f9411-338">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-338">Deletes until given character.</span></span>

- <span data-ttu-id="f9411-339">Vi 命令模式： `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="f9411-339">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="f9411-340">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-340">ViDeleteToCharBackward</span></span>

<span data-ttu-id="f9411-341">向后删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-341">Deletes backwards until given character.</span></span>

- <span data-ttu-id="f9411-342">Vi 命令模式： `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="f9411-342">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="f9411-343">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="f9411-343">ViInsertAtBegining</span></span>

<span data-ttu-id="f9411-344">切换到插入模式，并将光标置于行首。</span><span class="sxs-lookup"><span data-stu-id="f9411-344">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="f9411-345">Vi 命令模式： `<I>`</span><span class="sxs-lookup"><span data-stu-id="f9411-345">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="f9411-346">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="f9411-346">ViInsertAtEnd</span></span>

<span data-ttu-id="f9411-347">切换到插入模式，并将光标置于行的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-347">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="f9411-348">Vi 命令模式： `<A>`</span><span class="sxs-lookup"><span data-stu-id="f9411-348">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="f9411-349">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="f9411-349">ViInsertLine</span></span>

<span data-ttu-id="f9411-350">在当前行的上方插入新行。</span><span class="sxs-lookup"><span data-stu-id="f9411-350">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="f9411-351">Vi 命令模式： `<O>`</span><span class="sxs-lookup"><span data-stu-id="f9411-351">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="f9411-352">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="f9411-352">ViInsertWithAppend</span></span>

<span data-ttu-id="f9411-353">从当前行位置追加。</span><span class="sxs-lookup"><span data-stu-id="f9411-353">Append from the current line position.</span></span>

- <span data-ttu-id="f9411-354">Vi 命令模式： `<a>`</span><span class="sxs-lookup"><span data-stu-id="f9411-354">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="f9411-355">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="f9411-355">ViInsertWithDelete</span></span>

<span data-ttu-id="f9411-356">删除当前字符并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="f9411-356">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="f9411-357">Vi 命令模式： `<s>`</span><span class="sxs-lookup"><span data-stu-id="f9411-357">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="f9411-358">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="f9411-358">ViJoinLines</span></span>

<span data-ttu-id="f9411-359">联接当前行和下一行。</span><span class="sxs-lookup"><span data-stu-id="f9411-359">Joins the current line and the next line.</span></span>

- <span data-ttu-id="f9411-360">Vi 命令模式： `<J>`</span><span class="sxs-lookup"><span data-stu-id="f9411-360">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="f9411-361">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="f9411-361">ViReplaceLine</span></span>

<span data-ttu-id="f9411-362">擦除整个命令行。</span><span class="sxs-lookup"><span data-stu-id="f9411-362">Erase the entire command line.</span></span>

- <span data-ttu-id="f9411-363">Vi 命令模式： `<S>` ， `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="f9411-363">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="f9411-364">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="f9411-364">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="f9411-365">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-365">Replaces until given character.</span></span>

- <span data-ttu-id="f9411-366">Vi 命令模式： `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="f9411-366">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="f9411-367">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-367">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="f9411-368">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-368">Replaces until given character.</span></span>

- <span data-ttu-id="f9411-369">Vi 命令模式： `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="f9411-369">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="f9411-370">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="f9411-370">ViReplaceToChar</span></span>

<span data-ttu-id="f9411-371">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-371">Deletes until given character.</span></span>

- <span data-ttu-id="f9411-372">Vi 命令模式： `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="f9411-372">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="f9411-373">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-373">ViReplaceToCharBackward</span></span>

<span data-ttu-id="f9411-374">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-374">Replaces until given character.</span></span>

- <span data-ttu-id="f9411-375">Vi 命令模式： `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="f9411-375">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="f9411-376">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="f9411-376">ViYankBeginningOfLine</span></span>

<span data-ttu-id="f9411-377">从缓冲区的开头到游标的 Yank。</span><span class="sxs-lookup"><span data-stu-id="f9411-377">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="f9411-378">Vi 命令模式： `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="f9411-378">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="f9411-379">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-379">ViYankEndOfGlob</span></span>

<span data-ttu-id="f9411-380">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-380">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="f9411-381">Vi 命令模式： `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="f9411-381">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="f9411-382">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="f9411-382">ViYankEndOfWord</span></span>

<span data-ttu-id="f9411-383">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-383">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="f9411-384">Vi 命令模式： `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="f9411-384">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="f9411-385">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="f9411-385">ViYankLeft</span></span>

<span data-ttu-id="f9411-386">Yank 字符 (s) 光标左侧。</span><span class="sxs-lookup"><span data-stu-id="f9411-386">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="f9411-387">Vi 命令模式： `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="f9411-387">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="f9411-388">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="f9411-388">ViYankLine</span></span>

<span data-ttu-id="f9411-389">Yank 整个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f9411-389">Yank the entire buffer.</span></span>

- <span data-ttu-id="f9411-390">Vi 命令模式： `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-390">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="f9411-391">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-391">ViYankNextGlob</span></span>

<span data-ttu-id="f9411-392">Yank 从 cursor 到下一个单词 () 的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-392">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="f9411-393">Vi 命令模式： `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="f9411-393">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="f9411-394">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="f9411-394">ViYankNextWord</span></span>

<span data-ttu-id="f9411-395">Yank 在游标后) 的单词 (。</span><span class="sxs-lookup"><span data-stu-id="f9411-395">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="f9411-396">Vi 命令模式： `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="f9411-396">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="f9411-397">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="f9411-397">ViYankPercent</span></span>

<span data-ttu-id="f9411-398">Yank 匹配的大括号。</span><span class="sxs-lookup"><span data-stu-id="f9411-398">Yank to/from matching brace.</span></span>

- <span data-ttu-id="f9411-399">Vi 命令模式： `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="f9411-399">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="f9411-400">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-400">ViYankPreviousGlob</span></span>

<span data-ttu-id="f9411-401">从单词 (开始，) 到游标。</span><span class="sxs-lookup"><span data-stu-id="f9411-401">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="f9411-402">Vi 命令模式： `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="f9411-402">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="f9411-403">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="f9411-403">ViYankPreviousWord</span></span>

<span data-ttu-id="f9411-404">Yank 在游标前)  (s。</span><span class="sxs-lookup"><span data-stu-id="f9411-404">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="f9411-405">Vi 命令模式： `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="f9411-405">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="f9411-406">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="f9411-406">ViYankRight</span></span>

<span data-ttu-id="f9411-407">Yank 字符 (s) 光标右侧和右侧。</span><span class="sxs-lookup"><span data-stu-id="f9411-407">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="f9411-408">Vi 命令模式： `<y,l>` ， `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="f9411-408">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="f9411-409">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="f9411-409">ViYankToEndOfLine</span></span>

<span data-ttu-id="f9411-410">Yank 从游标到缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-410">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="f9411-411">Vi 命令模式： `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="f9411-411">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="f9411-412">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="f9411-412">ViYankToFirstChar</span></span>

<span data-ttu-id="f9411-413">从第一个非空白字符 Yank 到游标。</span><span class="sxs-lookup"><span data-stu-id="f9411-413">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="f9411-414">Vi 命令模式： `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="f9411-414">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="f9411-415">Yank</span><span class="sxs-lookup"><span data-stu-id="f9411-415">Yank</span></span>

<span data-ttu-id="f9411-416">将最近终止的文本添加到输入中。</span><span class="sxs-lookup"><span data-stu-id="f9411-416">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="f9411-417">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-417">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="f9411-418">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="f9411-418">YankLastArg</span></span>

<span data-ttu-id="f9411-419">Yank 上一个历史记录行中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="f9411-419">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="f9411-420">如果使用参数，则第一次调用时，其行为就像 YankNthArg。</span><span class="sxs-lookup"><span data-stu-id="f9411-420">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="f9411-421">如果多次调用，则会循环访问历史记录，而 arg 会将方向设置 (负反转方向。 ) </span><span class="sxs-lookup"><span data-stu-id="f9411-421">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="f9411-422">Cmd：`<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="f9411-422">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="f9411-423">Emacs： `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="f9411-423">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="f9411-424">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="f9411-424">YankNthArg</span></span>

<span data-ttu-id="f9411-425">Yank 从上一历史记录行) 命令后 (第一个参数。</span><span class="sxs-lookup"><span data-stu-id="f9411-425">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="f9411-426">对于参数，yank 从 0) 开始 (第 n 个参数，如果参数为负数，则从最后一个参数开始。</span><span class="sxs-lookup"><span data-stu-id="f9411-426">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="f9411-427">Emacs： `<Ctrl+Alt+y>` ， `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-427">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="f9411-428">YankPop</span><span class="sxs-lookup"><span data-stu-id="f9411-428">YankPop</span></span>

<span data-ttu-id="f9411-429">如果上一操作是 Yank 或 YankPop，则将以前的拔掉文本替换为下一个终止的文本。</span><span class="sxs-lookup"><span data-stu-id="f9411-429">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="f9411-430">Emacs： `<Alt+y>` ， `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="f9411-430">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="f9411-431">游标移动函数</span><span class="sxs-lookup"><span data-stu-id="f9411-431">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="f9411-432">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="f9411-432">BackwardChar</span></span>

<span data-ttu-id="f9411-433">将光标向左移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-433">Move the cursor one character to the left.</span></span> <span data-ttu-id="f9411-434">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="f9411-434">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="f9411-435">Cmd：`<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-435">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="f9411-436">Emacs： `<LeftArrow>` ， `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="f9411-436">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="f9411-437">Vi 插入模式： `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-437">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="f9411-438">Vi 命令模式： `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="f9411-438">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="f9411-439">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-439">BackwardWord</span></span>

<span data-ttu-id="f9411-440">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-440">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f9411-441">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-441">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f9411-442">Cmd：`<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-442">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f9411-443">Emacs： `<Alt+b>` ， `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="f9411-443">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="f9411-444">Vi 插入模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-444">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f9411-445">Vi 命令模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-445">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="f9411-446">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="f9411-446">BeginningOfLine</span></span>

<span data-ttu-id="f9411-447">如果输入具有多个行，则移动到当前行的开头，或者，如果已位于行首，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-447">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="f9411-448">如果输入具有单行，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-448">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="f9411-449">Cmd：`<Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-449">Cmd: `<Home>`</span></span>
- <span data-ttu-id="f9411-450">Emacs： `<Home>` ， `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f9411-450">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="f9411-451">Vi 插入模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-451">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="f9411-452">Vi 命令模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-452">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="f9411-453">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="f9411-453">EndOfLine</span></span>

<span data-ttu-id="f9411-454">如果输入包含多行，则移动到当前行的末尾，或者，如果已位于行尾，则转到输入的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-454">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="f9411-455">如果输入具有单行，则移动到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-455">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="f9411-456">Cmd：`<End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-456">Cmd: `<End>`</span></span>
- <span data-ttu-id="f9411-457">Emacs： `<End>` ， `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f9411-457">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="f9411-458">Vi 插入模式： `<End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-458">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="f9411-459">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="f9411-459">ForwardChar</span></span>

<span data-ttu-id="f9411-460">将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-460">Move the cursor one character to the right.</span></span> <span data-ttu-id="f9411-461">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-461">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="f9411-462">Cmd：`<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-462">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="f9411-463">Emacs： `<RightArrow>` ， `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="f9411-463">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="f9411-464">Vi 插入模式： `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-464">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="f9411-465">Vi 命令模式： `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="f9411-465">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="f9411-466">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-466">ForwardWord</span></span>

<span data-ttu-id="f9411-467">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-467">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f9411-468">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-468">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f9411-469">Emacs： `<Alt+f>` ， `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="f9411-469">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="f9411-470">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="f9411-470">GotoBrace</span></span>

<span data-ttu-id="f9411-471">中转到匹配的大括号、圆括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="f9411-471">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="f9411-472">Cmd：`<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f9411-472">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f9411-473">Vi 插入模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f9411-473">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f9411-474">Vi 命令模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f9411-474">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="f9411-475">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="f9411-475">GotoColumn</span></span>

<span data-ttu-id="f9411-476">转到 arg 指示的列。</span><span class="sxs-lookup"><span data-stu-id="f9411-476">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="f9411-477">Vi 命令模式： `<|>`</span><span class="sxs-lookup"><span data-stu-id="f9411-477">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="f9411-478">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="f9411-478">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="f9411-479">将光标移动到行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-479">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="f9411-480">Vi 命令模式： `<^>`</span><span class="sxs-lookup"><span data-stu-id="f9411-480">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="f9411-481">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="f9411-481">MoveToEndOfLine</span></span>

<span data-ttu-id="f9411-482">将光标移到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-482">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="f9411-483">Vi 命令模式： `<End>` ， `<$>`</span><span class="sxs-lookup"><span data-stu-id="f9411-483">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="f9411-484">NextLine</span><span class="sxs-lookup"><span data-stu-id="f9411-484">NextLine</span></span>

<span data-ttu-id="f9411-485">将光标移到下一行。</span><span class="sxs-lookup"><span data-stu-id="f9411-485">Move the cursor to the next line.</span></span>

- <span data-ttu-id="f9411-486">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-486">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="f9411-487">NextWord</span><span class="sxs-lookup"><span data-stu-id="f9411-487">NextWord</span></span>

<span data-ttu-id="f9411-488">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-488">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f9411-489">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-489">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f9411-490">Cmd：`<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-490">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f9411-491">Vi 插入模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-491">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f9411-492">Vi 命令模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-492">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="f9411-493">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="f9411-493">NextWordEnd</span></span>

<span data-ttu-id="f9411-494">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-494">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f9411-495">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-495">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f9411-496">Vi 命令模式： `<e>`</span><span class="sxs-lookup"><span data-stu-id="f9411-496">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="f9411-497">PreviousLine</span><span class="sxs-lookup"><span data-stu-id="f9411-497">PreviousLine</span></span>

<span data-ttu-id="f9411-498">将光标移到上一行。</span><span class="sxs-lookup"><span data-stu-id="f9411-498">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="f9411-499">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-499">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="f9411-500">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-500">ShellBackwardWord</span></span>

<span data-ttu-id="f9411-501">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-501">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f9411-502">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-502">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f9411-503">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-503">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="f9411-504">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-504">ShellForwardWord</span></span>

<span data-ttu-id="f9411-505">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-505">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f9411-506">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-506">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f9411-507">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-507">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="f9411-508">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="f9411-508">ShellNextWord</span></span>

<span data-ttu-id="f9411-509">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="f9411-509">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f9411-510">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-510">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f9411-511">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-511">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="f9411-512">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-512">ViBackwardWord</span></span>

<span data-ttu-id="f9411-513">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-513">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f9411-514">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-514">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f9411-515">Vi 命令模式： `<b>`</span><span class="sxs-lookup"><span data-stu-id="f9411-515">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="f9411-516">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-516">ViEndOfGlob</span></span>

<span data-ttu-id="f9411-517">将光标移到单词的末尾，只使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="f9411-517">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f9411-518">Vi 命令模式： `<E>`</span><span class="sxs-lookup"><span data-stu-id="f9411-518">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="f9411-519">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-519">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="f9411-520">移到上一个词的末尾，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="f9411-520">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f9411-521">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-521">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="f9411-522">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="f9411-522">ViGotoBrace</span></span>

<span data-ttu-id="f9411-523">类似于 GotoBrace，但基于字符，而不是基于标记。</span><span class="sxs-lookup"><span data-stu-id="f9411-523">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="f9411-524">Vi 命令模式： `<%>`</span><span class="sxs-lookup"><span data-stu-id="f9411-524">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="f9411-525">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="f9411-525">ViNextGlob</span></span>

<span data-ttu-id="f9411-526">移到下一个单词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="f9411-526">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f9411-527">Vi 命令模式： `<W>`</span><span class="sxs-lookup"><span data-stu-id="f9411-527">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="f9411-528">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="f9411-528">ViNextWord</span></span>

<span data-ttu-id="f9411-529">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-529">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f9411-530">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="f9411-530">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f9411-531">Vi 命令模式： `<w>`</span><span class="sxs-lookup"><span data-stu-id="f9411-531">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="f9411-532">历史记录函数</span><span class="sxs-lookup"><span data-stu-id="f9411-532">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="f9411-533">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-533">BeginningOfHistory</span></span>

<span data-ttu-id="f9411-534">移到历史记录中的第一项。</span><span class="sxs-lookup"><span data-stu-id="f9411-534">Move to the first item in the history.</span></span>

- <span data-ttu-id="f9411-535">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="f9411-535">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="f9411-536">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-536">ClearHistory</span></span>

<span data-ttu-id="f9411-537">清除 PSReadLine 中的历史记录。</span><span class="sxs-lookup"><span data-stu-id="f9411-537">Clears history in PSReadLine.</span></span> <span data-ttu-id="f9411-538">这不会影响 PowerShell 历史记录。</span><span class="sxs-lookup"><span data-stu-id="f9411-538">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="f9411-539">Cmd：`<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="f9411-539">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="f9411-540">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-540">EndOfHistory</span></span>

<span data-ttu-id="f9411-541">移到历史记录中 (当前输入) 的最后一项。</span><span class="sxs-lookup"><span data-stu-id="f9411-541">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="f9411-542">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="f9411-542">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="f9411-543">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-543">ForwardSearchHistory</span></span>

<span data-ttu-id="f9411-544">通过历史记录执行增量向前搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-544">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="f9411-545">Cmd：`<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f9411-545">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f9411-546">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f9411-546">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="f9411-547">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-547">HistorySearchBackward</span></span>

<span data-ttu-id="f9411-548">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项，该匹配项与开始与输入和光标之间的字符匹配。</span><span class="sxs-lookup"><span data-stu-id="f9411-548">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f9411-549">Cmd：`<F8>`</span><span class="sxs-lookup"><span data-stu-id="f9411-549">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="f9411-550">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="f9411-550">HistorySearchForward</span></span>

<span data-ttu-id="f9411-551">将当前输入替换为 PSReadLine 历史记录中与 start 与 input 和 cursor 之间的字符相匹配的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="f9411-551">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f9411-552">Cmd：`<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="f9411-552">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="f9411-553">NextHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-553">NextHistory</span></span>

<span data-ttu-id="f9411-554">将当前输入替换为 PSReadLine 历史记录中的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="f9411-554">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="f9411-555">Cmd：`<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-555">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="f9411-556">Emacs： `<DownArrow>` ， `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="f9411-556">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="f9411-557">Vi 插入模式： `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-557">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="f9411-558">Vi 命令模式： `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="f9411-558">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="f9411-559">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-559">PreviousHistory</span></span>

<span data-ttu-id="f9411-560">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项。</span><span class="sxs-lookup"><span data-stu-id="f9411-560">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="f9411-561">Cmd：`<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-561">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="f9411-562">Emacs： `<UpArrow>` ， `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="f9411-562">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="f9411-563">Vi 插入模式： `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-563">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="f9411-564">Vi 命令模式： `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="f9411-564">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="f9411-565">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="f9411-565">ReverseSearchHistory</span></span>

<span data-ttu-id="f9411-566">通过历史记录执行增量向后搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-566">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="f9411-567">Cmd：`<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f9411-567">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f9411-568">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f9411-568">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="f9411-569">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-569">ViSearchHistoryBackward</span></span>

<span data-ttu-id="f9411-570">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-570">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f9411-571">Vi 插入模式： `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f9411-571">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f9411-572">Vi 命令模式： `</>` ， `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f9411-572">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="f9411-573">完成函数</span><span class="sxs-lookup"><span data-stu-id="f9411-573">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="f9411-574">完成</span><span class="sxs-lookup"><span data-stu-id="f9411-574">Complete</span></span>

<span data-ttu-id="f9411-575">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="f9411-575">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f9411-576">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="f9411-576">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f9411-577">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="f9411-577">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f9411-578">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-578">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="f9411-579">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="f9411-579">MenuComplete</span></span>

<span data-ttu-id="f9411-580">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="f9411-580">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f9411-581">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="f9411-581">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f9411-582">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="f9411-582">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f9411-583">Cmd：`<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f9411-583">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="f9411-584">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f9411-584">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="f9411-585">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="f9411-585">PossibleCompletions</span></span>

<span data-ttu-id="f9411-586">显示可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="f9411-586">Display the list of possible completions.</span></span>

- <span data-ttu-id="f9411-587">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="f9411-587">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="f9411-588">Vi 插入模式： `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f9411-588">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="f9411-589">Vi 命令模式： `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f9411-589">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="f9411-590">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="f9411-590">TabCompleteNext</span></span>

<span data-ttu-id="f9411-591">尝试使用下一个可用完成来完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="f9411-591">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="f9411-592">Cmd：`<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-592">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="f9411-593">Vi 命令模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-593">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="f9411-594">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="f9411-594">TabCompletePrevious</span></span>

<span data-ttu-id="f9411-595">尝试使用以前的可用完成功能完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="f9411-595">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="f9411-596">Cmd：`<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-596">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="f9411-597">Vi 命令模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-597">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="f9411-598">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="f9411-598">ViTabCompleteNext</span></span>

<span data-ttu-id="f9411-599">结束当前编辑组（如果需要），并调用 TabCompleteNext。</span><span class="sxs-lookup"><span data-stu-id="f9411-599">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="f9411-600">Vi 插入模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-600">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="f9411-601">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="f9411-601">ViTabCompletePrevious</span></span>

<span data-ttu-id="f9411-602">结束当前编辑组（如果需要），并调用 TabCompletePrevious。</span><span class="sxs-lookup"><span data-stu-id="f9411-602">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="f9411-603">Vi 插入模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f9411-603">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="f9411-604">杂项函数</span><span class="sxs-lookup"><span data-stu-id="f9411-604">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="f9411-605">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="f9411-605">CaptureScreen</span></span>

<span data-ttu-id="f9411-606">启动交互屏幕捕获-向上/向下箭头选择 "线条"，将选定文本作为文本和 html 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f9411-606">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="f9411-607">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-607">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="f9411-608">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="f9411-608">ClearScreen</span></span>

<span data-ttu-id="f9411-609">清除屏幕并在屏幕的顶部绘制当前线条。</span><span class="sxs-lookup"><span data-stu-id="f9411-609">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="f9411-610">Cmd：`<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f9411-610">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f9411-611">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f9411-611">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f9411-612">Vi 插入模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f9411-612">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f9411-613">Vi 命令模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f9411-613">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="f9411-614">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="f9411-614">DigitArgument</span></span>

<span data-ttu-id="f9411-615">启动新的数字参数，使其传递到其他函数。</span><span class="sxs-lookup"><span data-stu-id="f9411-615">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="f9411-616">Cmd： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f9411-616">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f9411-617">Emacs： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f9411-617">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f9411-618">Vi 命令模式： `<0>` 、 `<1>` 、 `<2>` 、 `<3>` 、 `<4>` 、 `<5>` 、 `<6>` 、 `<7>` 、 `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="f9411-618">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="f9411-619">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="f9411-619">InvokePrompt</span></span>

<span data-ttu-id="f9411-620">清除当前提示符并调用 prompt 函数以重新显示提示符。</span><span class="sxs-lookup"><span data-stu-id="f9411-620">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="f9411-621">适用于更改状态的自定义密钥处理程序，例如更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="f9411-621">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="f9411-622">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-622">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="f9411-623">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="f9411-623">ScrollDisplayDown</span></span>

<span data-ttu-id="f9411-624">将显示向下滚动一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="f9411-624">Scroll the display down one screen.</span></span>

- <span data-ttu-id="f9411-625">Cmd：`<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f9411-625">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="f9411-626">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f9411-626">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="f9411-627">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="f9411-627">ScrollDisplayDownLine</span></span>

<span data-ttu-id="f9411-628">将显示向下滚动一行。</span><span class="sxs-lookup"><span data-stu-id="f9411-628">Scroll the display down one line.</span></span>

- <span data-ttu-id="f9411-629">Cmd：`<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f9411-629">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="f9411-630">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f9411-630">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="f9411-631">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="f9411-631">ScrollDisplayToCursor</span></span>

<span data-ttu-id="f9411-632">将显示滚动到光标处。</span><span class="sxs-lookup"><span data-stu-id="f9411-632">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="f9411-633">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-633">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="f9411-634">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="f9411-634">ScrollDisplayTop</span></span>

<span data-ttu-id="f9411-635">向顶部滚动显示。</span><span class="sxs-lookup"><span data-stu-id="f9411-635">Scroll the display to the top.</span></span>

- <span data-ttu-id="f9411-636">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-636">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="f9411-637">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="f9411-637">ScrollDisplayUp</span></span>

<span data-ttu-id="f9411-638">将显示向上滚动一屏。</span><span class="sxs-lookup"><span data-stu-id="f9411-638">Scroll the display up one screen.</span></span>

- <span data-ttu-id="f9411-639">Cmd：`<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f9411-639">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="f9411-640">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f9411-640">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="f9411-641">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="f9411-641">ScrollDisplayUpLine</span></span>

<span data-ttu-id="f9411-642">将显示向上滚动一行。</span><span class="sxs-lookup"><span data-stu-id="f9411-642">Scroll the display up one line.</span></span>

- <span data-ttu-id="f9411-643">Cmd：`<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f9411-643">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="f9411-644">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f9411-644">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="f9411-645">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="f9411-645">SelfInsert</span></span>

<span data-ttu-id="f9411-646">插入密钥。</span><span class="sxs-lookup"><span data-stu-id="f9411-646">Insert the key.</span></span>

- <span data-ttu-id="f9411-647">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-647">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="f9411-648">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="f9411-648">ShowKeyBindings</span></span>

<span data-ttu-id="f9411-649">显示所有绑定键。</span><span class="sxs-lookup"><span data-stu-id="f9411-649">Show all bound keys.</span></span>

- <span data-ttu-id="f9411-650">Cmd：`<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f9411-650">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f9411-651">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f9411-651">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f9411-652">Vi 插入模式： `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f9411-652">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="f9411-653">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="f9411-653">ViCommandMode</span></span>

<span data-ttu-id="f9411-654">将当前运行模式从 Vi-Insert 切换到 Vi-Command。</span><span class="sxs-lookup"><span data-stu-id="f9411-654">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="f9411-655">Vi 插入模式： `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f9411-655">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="f9411-656">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="f9411-656">ViDigitArgumentInChord</span></span>

<span data-ttu-id="f9411-657">启动新的数字参数，将其传递给其他函数，同时使用 vi 的鼠标左键之一。</span><span class="sxs-lookup"><span data-stu-id="f9411-657">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="f9411-658">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-658">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="f9411-659">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="f9411-659">ViEditVisually</span></span>

<span data-ttu-id="f9411-660">在 $env： EDITOR 或 $env：视觉对象指定的文本编辑器中编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="f9411-660">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="f9411-661">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f9411-661">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="f9411-662">Vi 命令模式： `<v>`</span><span class="sxs-lookup"><span data-stu-id="f9411-662">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="f9411-663">ViExit</span><span class="sxs-lookup"><span data-stu-id="f9411-663">ViExit</span></span>

<span data-ttu-id="f9411-664">退出 shell。</span><span class="sxs-lookup"><span data-stu-id="f9411-664">Exits the shell.</span></span>

- <span data-ttu-id="f9411-665">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-665">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="f9411-666">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="f9411-666">ViInsertMode</span></span>

<span data-ttu-id="f9411-667">切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="f9411-667">Switch to Insert mode.</span></span>

- <span data-ttu-id="f9411-668">Vi 命令模式： `<i>`</span><span class="sxs-lookup"><span data-stu-id="f9411-668">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="f9411-669">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="f9411-669">WhatIsKey</span></span>

<span data-ttu-id="f9411-670">阅读密钥，并告诉我密钥的绑定内容。</span><span class="sxs-lookup"><span data-stu-id="f9411-670">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="f9411-671">Cmd：`<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f9411-671">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="f9411-672">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f9411-672">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="f9411-673">选择函数</span><span class="sxs-lookup"><span data-stu-id="f9411-673">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="f9411-674">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="f9411-674">ExchangePointAndMark</span></span>

<span data-ttu-id="f9411-675">将光标置于标记的位置，并将标记移到光标所在的位置。</span><span class="sxs-lookup"><span data-stu-id="f9411-675">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="f9411-676">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f9411-676">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="f9411-677">SelectAll</span><span class="sxs-lookup"><span data-stu-id="f9411-677">SelectAll</span></span>

<span data-ttu-id="f9411-678">选择整行。</span><span class="sxs-lookup"><span data-stu-id="f9411-678">Select the entire line.</span></span>

- <span data-ttu-id="f9411-679">Cmd：`<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f9411-679">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="f9411-680">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="f9411-680">SelectBackwardChar</span></span>

<span data-ttu-id="f9411-681">调整当前选定内容以包括前一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-681">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="f9411-682">Cmd：`<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-682">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="f9411-683">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-683">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="f9411-684">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="f9411-684">SelectBackwardsLine</span></span>

<span data-ttu-id="f9411-685">调整当前所选内容，使其包括从光标到行的开头。</span><span class="sxs-lookup"><span data-stu-id="f9411-685">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="f9411-686">Cmd：`<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-686">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="f9411-687">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f9411-687">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="f9411-688">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-688">SelectBackwardWord</span></span>

<span data-ttu-id="f9411-689">调整当前所选内容以包含上一个词。</span><span class="sxs-lookup"><span data-stu-id="f9411-689">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="f9411-690">Cmd：`<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-690">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f9411-691">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="f9411-691">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="f9411-692">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="f9411-692">SelectForwardChar</span></span>

<span data-ttu-id="f9411-693">调整当前所选内容以包含下一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-693">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="f9411-694">Cmd：`<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-694">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="f9411-695">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-695">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="f9411-696">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-696">SelectForwardWord</span></span>

<span data-ttu-id="f9411-697">使用 ForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="f9411-697">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="f9411-698">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="f9411-698">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="f9411-699">SelectLine</span><span class="sxs-lookup"><span data-stu-id="f9411-699">SelectLine</span></span>

<span data-ttu-id="f9411-700">调整当前所选内容，使其包括从光标到行尾的内容。</span><span class="sxs-lookup"><span data-stu-id="f9411-700">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="f9411-701">Cmd：`<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-701">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="f9411-702">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f9411-702">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="f9411-703">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="f9411-703">SelectNextWord</span></span>

<span data-ttu-id="f9411-704">调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="f9411-704">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="f9411-705">Cmd：`<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f9411-705">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="f9411-706">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-706">SelectShellBackwardWord</span></span>

<span data-ttu-id="f9411-707">使用 ShellBackwardWord 调整当前所选内容，使其包含前一词。</span><span class="sxs-lookup"><span data-stu-id="f9411-707">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="f9411-708">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-708">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="f9411-709">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="f9411-709">SelectShellForwardWord</span></span>

<span data-ttu-id="f9411-710">使用 ShellForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="f9411-710">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="f9411-711">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-711">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="f9411-712">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="f9411-712">SelectShellNextWord</span></span>

<span data-ttu-id="f9411-713">使用 ShellNextWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="f9411-713">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="f9411-714">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-714">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="f9411-715">SetMark</span><span class="sxs-lookup"><span data-stu-id="f9411-715">SetMark</span></span>

<span data-ttu-id="f9411-716">标记光标的当前位置，以供后续编辑命令使用。</span><span class="sxs-lookup"><span data-stu-id="f9411-716">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="f9411-717">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="f9411-717">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="f9411-718">搜索函数</span><span class="sxs-lookup"><span data-stu-id="f9411-718">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="f9411-719">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="f9411-719">CharacterSearch</span></span>

<span data-ttu-id="f9411-720">读取字符并向前搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f9411-720">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="f9411-721">如果指定了参数，则向前搜索 (或向后) 对于第 n 个匹配项为负。</span><span class="sxs-lookup"><span data-stu-id="f9411-721">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f9411-722">Cmd：`<F3>`</span><span class="sxs-lookup"><span data-stu-id="f9411-722">Cmd: `<F3>`</span></span>
- <span data-ttu-id="f9411-723">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f9411-723">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f9411-724">Vi 插入模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f9411-724">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="f9411-725">Vi 命令模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f9411-725">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="f9411-726">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-726">CharacterSearchBackward</span></span>

<span data-ttu-id="f9411-727">读取字符并向后搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f9411-727">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="f9411-728">如果指定了参数，则在第 n 个匹配项) 反向搜索时 (或转发。</span><span class="sxs-lookup"><span data-stu-id="f9411-728">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f9411-729">Cmd：`<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f9411-729">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="f9411-730">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="f9411-730">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="f9411-731">Vi 插入模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f9411-731">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="f9411-732">Vi 命令模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f9411-732">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="f9411-733">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="f9411-733">RepeatLastCharSearch</span></span>

<span data-ttu-id="f9411-734">重复上次记录的字符搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-734">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="f9411-735">Vi 命令模式： `<;>`</span><span class="sxs-lookup"><span data-stu-id="f9411-735">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="f9411-736">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="f9411-736">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="f9411-737">重复上次记录的字符搜索，但采用相反方向。</span><span class="sxs-lookup"><span data-stu-id="f9411-737">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="f9411-738">Vi 命令模式： `<,>`</span><span class="sxs-lookup"><span data-stu-id="f9411-738">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="f9411-739">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="f9411-739">RepeatSearch</span></span>

<span data-ttu-id="f9411-740">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f9411-741">Vi 命令模式： `<n>`</span><span class="sxs-lookup"><span data-stu-id="f9411-741">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="f9411-742">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-742">RepeatSearchBackward</span></span>

<span data-ttu-id="f9411-743">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-743">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f9411-744">Vi 命令模式： `<N>`</span><span class="sxs-lookup"><span data-stu-id="f9411-744">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="f9411-745">SearchChar</span><span class="sxs-lookup"><span data-stu-id="f9411-745">SearchChar</span></span>

<span data-ttu-id="f9411-746">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-746">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f9411-747">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="f9411-747">This is for 't' functionality.</span></span>

- <span data-ttu-id="f9411-748">Vi 命令模式： `<f>`</span><span class="sxs-lookup"><span data-stu-id="f9411-748">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="f9411-749">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="f9411-749">SearchCharBackward</span></span>

<span data-ttu-id="f9411-750">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-750">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f9411-751">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="f9411-751">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f9411-752">Vi 命令模式： `<F>`</span><span class="sxs-lookup"><span data-stu-id="f9411-752">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="f9411-753">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="f9411-753">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="f9411-754">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-754">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f9411-755">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="f9411-755">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f9411-756">Vi 命令模式： `<T>`</span><span class="sxs-lookup"><span data-stu-id="f9411-756">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="f9411-757">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="f9411-757">SearchCharWithBackoff</span></span>

<span data-ttu-id="f9411-758">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-758">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f9411-759">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="f9411-759">This is for 't' functionality.</span></span>

- <span data-ttu-id="f9411-760">Vi 命令模式： `<t>`</span><span class="sxs-lookup"><span data-stu-id="f9411-760">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="f9411-761">SearchForward</span><span class="sxs-lookup"><span data-stu-id="f9411-761">SearchForward</span></span>

<span data-ttu-id="f9411-762">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="f9411-762">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f9411-763">Vi 插入模式： `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f9411-763">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f9411-764">Vi 命令模式： `<?>` ， `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f9411-764">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="f9411-765">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="f9411-765">Custom Key Bindings</span></span>

<span data-ttu-id="f9411-766">PSReadLine 支持使用 cmdlet 的自定义键绑定 `Set-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="f9411-766">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="f9411-767">大多数自定义键绑定调用上述函数之一，例如</span><span class="sxs-lookup"><span data-stu-id="f9411-767">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="f9411-768">可以将 ScriptBlock 绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="f9411-768">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="f9411-769">ScriptBlock 可以执行任何所需的操作。</span><span class="sxs-lookup"><span data-stu-id="f9411-769">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="f9411-770">一些有用的示例包括</span><span class="sxs-lookup"><span data-stu-id="f9411-770">Some useful examples include</span></span>

- <span data-ttu-id="f9411-771">编辑命令行</span><span class="sxs-lookup"><span data-stu-id="f9411-771">edit the command line</span></span>
- <span data-ttu-id="f9411-772">打开新窗口 (例如，帮助) </span><span class="sxs-lookup"><span data-stu-id="f9411-772">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="f9411-773">更改目录而不更改命令行</span><span class="sxs-lookup"><span data-stu-id="f9411-773">change directories without changing the command line</span></span>

<span data-ttu-id="f9411-774">ScriptBlock 接收两个参数：</span><span class="sxs-lookup"><span data-stu-id="f9411-774">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="f9411-775">`$key` -一个作为触发自定义绑定的密钥的 **[ConsoleKeyInfo]** 对象。</span><span class="sxs-lookup"><span data-stu-id="f9411-775">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="f9411-776">如果将相同的 ScriptBlock 绑定到多个键，并且需要根据关键字执行不同的操作，则可以选中 $key。</span><span class="sxs-lookup"><span data-stu-id="f9411-776">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="f9411-777">许多自定义绑定会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="f9411-777">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="f9411-778">`$arg` -任意参数。</span><span class="sxs-lookup"><span data-stu-id="f9411-778">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="f9411-779">大多数情况下，这将是用户从键绑定 DigitArgument 传递的整数参数。</span><span class="sxs-lookup"><span data-stu-id="f9411-779">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="f9411-780">如果绑定不接受参数，则忽略此参数是合理的。</span><span class="sxs-lookup"><span data-stu-id="f9411-780">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="f9411-781">我们来看一个示例，该示例将一个命令行添加到历史记录中，而不执行它。</span><span class="sxs-lookup"><span data-stu-id="f9411-781">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="f9411-782">如果您认为您忘记了某些事情，但又不想重新输入您已经输入的命令行，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="f9411-782">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="f9411-783">你可以在 PSReadLine 模块文件夹中安装的文件中查看更多示例 `SamplePSReadLineProfile.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="f9411-783">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="f9411-784">大多数键绑定使用一些 helper 函数来编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="f9411-784">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="f9411-785">下一节将介绍这些 Api。</span><span class="sxs-lookup"><span data-stu-id="f9411-785">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="f9411-786">自定义键绑定支持 Api</span><span class="sxs-lookup"><span data-stu-id="f9411-786">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="f9411-787">以下函数是 PSConsoleReadLine 中的公共函数，但不能直接绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="f9411-787">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="f9411-788">大多数在自定义键绑定中很有用。</span><span class="sxs-lookup"><span data-stu-id="f9411-788">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="f9411-789">向历史记录中添加一个命令行而不执行它。</span><span class="sxs-lookup"><span data-stu-id="f9411-789">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="f9411-790">清除终止环。</span><span class="sxs-lookup"><span data-stu-id="f9411-790">Clear the kill-ring.</span></span>  <span data-ttu-id="f9411-791">这主要用于测试。</span><span class="sxs-lookup"><span data-stu-id="f9411-791">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="f9411-792">从开始删除长度字符。</span><span class="sxs-lookup"><span data-stu-id="f9411-792">Delete length characters from start.</span></span>  <span data-ttu-id="f9411-793">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="f9411-793">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="f9411-794">根据用户首选项执行 Ding 操作。</span><span class="sxs-lookup"><span data-stu-id="f9411-794">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="f9411-795">这两个函数检索有关输入缓冲区的当前状态的有用信息。</span><span class="sxs-lookup"><span data-stu-id="f9411-795">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="f9411-796">第一种方案更常见用于简单情况。</span><span class="sxs-lookup"><span data-stu-id="f9411-796">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="f9411-797">如果绑定使用 Ast 执行更高级的操作，则会使用第二个。</span><span class="sxs-lookup"><span data-stu-id="f9411-797">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="f9411-798">此函数由 Get-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="f9411-798">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="f9411-799">此函数由 Get-PSReadLineOption 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="f9411-799">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="f9411-800">如果未在命令行上进行选择，则将在 "开始" 和 "长度" 中返回-1。</span><span class="sxs-lookup"><span data-stu-id="f9411-800">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="f9411-801">如果命令行上有选择，则返回选定内容的开始和长度。</span><span class="sxs-lookup"><span data-stu-id="f9411-801">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="f9411-802">在光标处插入字符或字符串。</span><span class="sxs-lookup"><span data-stu-id="f9411-802">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="f9411-803">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="f9411-803">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="f9411-804">这是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="f9411-804">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="f9411-805">它不支持递归，因此在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="f9411-805">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="f9411-806">此函数由 Remove-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="f9411-806">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="f9411-807">替换部分输入。</span><span class="sxs-lookup"><span data-stu-id="f9411-807">Replace some of the input.</span></span> <span data-ttu-id="f9411-808">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="f9411-808">This operation supports undo/redo.</span></span> <span data-ttu-id="f9411-809">这优先于删除后再执行 Insert，因为它被视为单个操作来撤消。</span><span class="sxs-lookup"><span data-stu-id="f9411-809">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="f9411-810">将光标移动到给定偏移量。</span><span class="sxs-lookup"><span data-stu-id="f9411-810">Move the cursor to the given offset.</span></span> <span data-ttu-id="f9411-811">不跟踪游标移动以便撤消。</span><span class="sxs-lookup"><span data-stu-id="f9411-811">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="f9411-812">此函数是 cmdlet PSReadLineOption 使用的帮助器方法，但可能对要临时更改设置的自定义密钥绑定很有用。</span><span class="sxs-lookup"><span data-stu-id="f9411-812">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="f9411-813">此帮助器方法用于接受 DigitArgument 的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="f9411-813">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="f9411-814">典型调用如下所示</span><span class="sxs-lookup"><span data-stu-id="f9411-814">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="f9411-815">备注</span><span class="sxs-lookup"><span data-stu-id="f9411-815">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="f9411-816">命令历史记录</span><span class="sxs-lookup"><span data-stu-id="f9411-816">Command History</span></span>

<span data-ttu-id="f9411-817">PSReadLine 维护一个历史记录文件，其中包含在命令行中输入的所有命令和数据。</span><span class="sxs-lookup"><span data-stu-id="f9411-817">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="f9411-818">这可能包含敏感数据（包括密码）。</span><span class="sxs-lookup"><span data-stu-id="f9411-818">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="f9411-819">例如，如果使用 cmdlet，则 `ConvertTo-SecureString` 密码将作为纯文本记录到历史记录文件中。</span><span class="sxs-lookup"><span data-stu-id="f9411-819">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="f9411-820">历史记录文件是一个名为的文件 `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="f9411-820">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="f9411-821">在 Windows 系统上，历史记录文件存储在中 `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="f9411-821">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="f9411-822">参与 PSReadLine 的反馈 &</span><span class="sxs-lookup"><span data-stu-id="f9411-822">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="f9411-823">GitHub 上的 PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f9411-823">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="f9411-824">可在 GitHub 页上随意提交拉取请求或提交反馈。</span><span class="sxs-lookup"><span data-stu-id="f9411-824">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9411-825">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9411-825">See Also</span></span>

<span data-ttu-id="f9411-826">PSReadLine 会受到 GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) 库的严重影响。</span><span class="sxs-lookup"><span data-stu-id="f9411-826">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
