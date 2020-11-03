---
description: PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于 PSReadLine
ms.openlocfilehash: ad6e85a30f866cb332c89a4c36f42231f511f5ae
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200660"
---
# <a name="psreadline"></a><span data-ttu-id="2a36b-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="2a36b-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="2a36b-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="2a36b-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="2a36b-107">PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="2a36b-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="2a36b-108">详细说明</span><span class="sxs-lookup"><span data-stu-id="2a36b-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="2a36b-109">PSReadLine 2.0 为 PowerShell 控制台提供了强大的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="2a36b-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="2a36b-110">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="2a36b-110">It provides:</span></span>

- <span data-ttu-id="2a36b-111">命令行的语法着色</span><span class="sxs-lookup"><span data-stu-id="2a36b-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="2a36b-112">语法错误的直观指示</span><span class="sxs-lookup"><span data-stu-id="2a36b-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="2a36b-113"> (编辑和历史记录的更好的多行体验) </span><span class="sxs-lookup"><span data-stu-id="2a36b-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="2a36b-114">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="2a36b-114">Customizable key bindings</span></span>
- <span data-ttu-id="2a36b-115">Cmd 和 Emacs 模式</span><span class="sxs-lookup"><span data-stu-id="2a36b-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="2a36b-116">许多配置选项</span><span class="sxs-lookup"><span data-stu-id="2a36b-116">Many configuration options</span></span>
- <span data-ttu-id="2a36b-117">在 Cmd 模式下，Bash 样式完成 (可选，默认值为 Emacs 模式) </span><span class="sxs-lookup"><span data-stu-id="2a36b-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="2a36b-118">Emacs yank/kill 循环</span><span class="sxs-lookup"><span data-stu-id="2a36b-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="2a36b-119">基于 PowerShell 令牌的 "word" 移动和终止</span><span class="sxs-lookup"><span data-stu-id="2a36b-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="2a36b-120">类 **[PSConsoleReadLine]** 中提供了以下函数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="2a36b-121">基本编辑函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-121">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="2a36b-122">中止</span><span class="sxs-lookup"><span data-stu-id="2a36b-122">Abort</span></span>

<span data-ttu-id="2a36b-123">中止当前操作，例如增量历史记录搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-123">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="2a36b-124">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-124">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="2a36b-125">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="2a36b-125">AcceptAndGetNext</span></span>

<span data-ttu-id="2a36b-126">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-126">Attempt to execute the current input.</span></span> <span data-ttu-id="2a36b-127">如果可以 (如 AcceptLine) 执行，则在下一次调用 ReadLine 时，从历史记录中撤回下一项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-127">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="2a36b-128">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-128">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="2a36b-129">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-129">AcceptLine</span></span>

<span data-ttu-id="2a36b-130">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-130">Attempt to execute the current input.</span></span> <span data-ttu-id="2a36b-131">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-131">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="2a36b-132">Cmd：`<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-132">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="2a36b-133">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-133">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="2a36b-134">Vi 插入模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-134">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="2a36b-135">AddLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-135">AddLine</span></span>

<span data-ttu-id="2a36b-136">继续提示显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-136">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="2a36b-137">这可用于将多行输入作为单个命令输入，即使单个行自动完成输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="2a36b-137">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="2a36b-138">Cmd：`<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-138">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="2a36b-139">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-139">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="2a36b-140">Vi 插入模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-140">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="2a36b-141">Vi 命令模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-141">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="2a36b-142">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-142">BackwardDeleteChar</span></span>

<span data-ttu-id="2a36b-143">删除光标前面的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-143">Delete the character before the cursor.</span></span>

- <span data-ttu-id="2a36b-144">Cmd： `<Backspace>` ， `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-144">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="2a36b-145">Emacs： `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-145">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="2a36b-146">Vi 插入模式： `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-146">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="2a36b-147">Vi 命令模式： `<X>` ， `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-147">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="2a36b-148">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-148">BackwardDeleteLine</span></span>

<span data-ttu-id="2a36b-149">与 BackwardKillLine 一样，从点到行的开头删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-149">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-150">Cmd：`<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-150">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="2a36b-151">Vi 插入模式： `<Ctrl+u>` ， `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-151">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="2a36b-152">Vi 命令模式： `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-152">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="2a36b-153">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-153">BackwardDeleteWord</span></span>

<span data-ttu-id="2a36b-154">删除上一个词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-154">Deletes the previous word.</span></span>

- <span data-ttu-id="2a36b-155">Vi 命令模式： `<Ctrl+w>` ， `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-155">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="2a36b-156">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-156">BackwardKillLine</span></span>

<span data-ttu-id="2a36b-157">清除输入从输入开始到光标。</span><span class="sxs-lookup"><span data-stu-id="2a36b-157">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="2a36b-158">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-158">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-159">Emacs： `<Ctrl+u>` ， `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-159">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="2a36b-160">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-160">BackwardKillWord</span></span>

<span data-ttu-id="2a36b-161">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-161">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="2a36b-162">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-162">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="2a36b-163">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-163">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-164">Cmd：`<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-164">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="2a36b-165">Emacs： `<Alt+Backspace>` ， `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-165">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="2a36b-166">Vi 插入模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-166">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="2a36b-167">Vi 命令模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-167">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="2a36b-168">CancelLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-168">CancelLine</span></span>

<span data-ttu-id="2a36b-169">取消当前输入，将输入保留在屏幕上，但返回到主机以便再次计算提示。</span><span class="sxs-lookup"><span data-stu-id="2a36b-169">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="2a36b-170">Vi 插入模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-170">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="2a36b-171">Vi 命令模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-171">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="2a36b-172">复制</span><span class="sxs-lookup"><span data-stu-id="2a36b-172">Copy</span></span>

<span data-ttu-id="2a36b-173">将所选区域复制到系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="2a36b-173">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="2a36b-174">如果未选择区域，则复制整行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-174">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="2a36b-175">Cmd：`<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-175">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="2a36b-176">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-176">CopyOrCancelLine</span></span>

<span data-ttu-id="2a36b-177">如果选择了文本，请将其复制到剪贴板，否则取消该行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-177">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="2a36b-178">Cmd：`<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-178">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="2a36b-179">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-179">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="2a36b-180">剪切</span><span class="sxs-lookup"><span data-stu-id="2a36b-180">Cut</span></span>

<span data-ttu-id="2a36b-181">删除所选区域将删除的文本放入系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="2a36b-181">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="2a36b-182">Cmd：`<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-182">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="2a36b-183">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-183">DeleteChar</span></span>

<span data-ttu-id="2a36b-184">删除光标下的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-184">Delete the character under the cursor.</span></span>

- <span data-ttu-id="2a36b-185">Cmd：`<Delete>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-185">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="2a36b-186">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-186">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="2a36b-187">Vi 插入模式： `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-187">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="2a36b-188">Vi 命令模式： `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-188">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="2a36b-189">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="2a36b-189">DeleteCharOrExit</span></span>

<span data-ttu-id="2a36b-190">删除光标下的字符; 如果行为空，则退出该过程。</span><span class="sxs-lookup"><span data-stu-id="2a36b-190">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="2a36b-191">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-191">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="2a36b-192">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-192">DeleteEndOfWord</span></span>

<span data-ttu-id="2a36b-193">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-193">Delete to the end of the word.</span></span>

- <span data-ttu-id="2a36b-194">Vi 命令模式： `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-194">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="2a36b-195">Deleteline.invoke</span><span class="sxs-lookup"><span data-stu-id="2a36b-195">DeleteLine</span></span>

<span data-ttu-id="2a36b-196">删除当前行，启用 "撤消"。</span><span class="sxs-lookup"><span data-stu-id="2a36b-196">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="2a36b-197">Vi 命令模式： `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-197">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="2a36b-198">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-198">DeleteLineToFirstChar</span></span>

<span data-ttu-id="2a36b-199">删除从光标到行的第一个非空白字符的文本。</span><span class="sxs-lookup"><span data-stu-id="2a36b-199">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="2a36b-200">Vi 命令模式： `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-200">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="2a36b-201">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="2a36b-201">DeleteToEnd</span></span>

<span data-ttu-id="2a36b-202">删除到行的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-202">Delete to the end of the line.</span></span>

- <span data-ttu-id="2a36b-203">Vi 命令模式： `<D>` ， `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-203">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="2a36b-204">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-204">DeleteWord</span></span>

<span data-ttu-id="2a36b-205">删除下一个词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-205">Delete the next word.</span></span>

- <span data-ttu-id="2a36b-206">Vi 命令模式： `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-206">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="2a36b-207">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-207">ForwardDeleteLine</span></span>

<span data-ttu-id="2a36b-208">与 ForwardKillLine 一样，从点到行尾删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-208">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-209">Cmd：`<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-209">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="2a36b-210">Vi 插入模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-210">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="2a36b-211">Vi 命令模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-211">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="2a36b-212">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="2a36b-212">InsertLineAbove</span></span>

<span data-ttu-id="2a36b-213">在当前行的上方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="2a36b-213">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="2a36b-214">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-214">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="2a36b-215">Cmd：`<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-215">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="2a36b-216">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="2a36b-216">InsertLineBelow</span></span>

<span data-ttu-id="2a36b-217">在当前行下方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="2a36b-217">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="2a36b-218">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="2a36b-219">Cmd：`<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-219">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="2a36b-220">InvertCase</span><span class="sxs-lookup"><span data-stu-id="2a36b-220">InvertCase</span></span>

<span data-ttu-id="2a36b-221">反转当前字符的大小写，并移到下一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-221">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="2a36b-222">Vi 命令模式： `<~>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-222">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="2a36b-223">KillLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-223">KillLine</span></span>

<span data-ttu-id="2a36b-224">清除从光标到输入末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-224">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="2a36b-225">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-225">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-226">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-226">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="2a36b-227">KillRegion</span><span class="sxs-lookup"><span data-stu-id="2a36b-227">KillRegion</span></span>

<span data-ttu-id="2a36b-228">终止光标和标记之间的文本。</span><span class="sxs-lookup"><span data-stu-id="2a36b-228">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="2a36b-229">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-229">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="2a36b-230">KillWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-230">KillWord</span></span>

<span data-ttu-id="2a36b-231">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-231">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="2a36b-232">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-232">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="2a36b-233">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-233">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-234">Cmd：`<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-234">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="2a36b-235">Emacs： `<Alt+d>` ， `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-235">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="2a36b-236">Vi 插入模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-236">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="2a36b-237">Vi 命令模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-237">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="2a36b-238">粘贴</span><span class="sxs-lookup"><span data-stu-id="2a36b-238">Paste</span></span>

<span data-ttu-id="2a36b-239">粘贴系统剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="2a36b-239">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="2a36b-240">Cmd： `<Ctrl+v>` ， `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-240">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="2a36b-241">Vi 插入模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-241">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="2a36b-242">Vi 命令模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-242">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a36b-243">使用 **Paste** 函数时，剪贴板缓冲区的全部内容将粘贴到 PSReadLine 的输入缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-243">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="2a36b-244">然后，将输入缓冲区传递到 PowerShell 分析器。</span><span class="sxs-lookup"><span data-stu-id="2a36b-244">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="2a36b-245">使用控制台应用程序的 **右键单击** 粘贴方法粘贴的输入会一次复制到输入缓冲区中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-245">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="2a36b-246">复制换行符时，输入缓冲区会传递到分析器。</span><span class="sxs-lookup"><span data-stu-id="2a36b-246">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="2a36b-247">因此，每次对输入进行一次分析。</span><span class="sxs-lookup"><span data-stu-id="2a36b-247">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="2a36b-248">Paste 方法之间的区别导致了不同的执行行为。</span><span class="sxs-lookup"><span data-stu-id="2a36b-248">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="2a36b-249">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="2a36b-249">PasteAfter</span></span>

<span data-ttu-id="2a36b-250">在光标后面粘贴剪贴板，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-250">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="2a36b-251">Vi 命令模式： `<p>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-251">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="2a36b-252">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="2a36b-252">PasteBefore</span></span>

<span data-ttu-id="2a36b-253">将剪贴板粘贴到光标之前，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-253">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="2a36b-254">Vi 命令模式： `<P>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-254">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="2a36b-255">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="2a36b-255">PrependAndAccept</span></span>

<span data-ttu-id="2a36b-256">预置 "#" 并接受该行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-256">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="2a36b-257">Vi 命令模式： `<#>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-257">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="2a36b-258">重做</span><span class="sxs-lookup"><span data-stu-id="2a36b-258">Redo</span></span>

<span data-ttu-id="2a36b-259">撤消撤消。</span><span class="sxs-lookup"><span data-stu-id="2a36b-259">Undo an undo.</span></span>

- <span data-ttu-id="2a36b-260">Cmd：`<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-260">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="2a36b-261">Vi 插入模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-261">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="2a36b-262">Vi 命令模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-262">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="2a36b-263">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="2a36b-263">RepeatLastCommand</span></span>

<span data-ttu-id="2a36b-264">重复最后一次文本修改。</span><span class="sxs-lookup"><span data-stu-id="2a36b-264">Repeat the last text modification.</span></span>

- <span data-ttu-id="2a36b-265">Vi 命令模式： `<.>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-265">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="2a36b-266">RevertLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-266">RevertLine</span></span>

<span data-ttu-id="2a36b-267">将所有输入还原为当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-267">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="2a36b-268">Cmd：`<Escape>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-268">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="2a36b-269">Emacs： `<Alt+r>` ， `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-269">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="2a36b-270">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-270">ShellBackwardKillWord</span></span>

<span data-ttu-id="2a36b-271">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-271">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="2a36b-272">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-272">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="2a36b-273">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-273">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="2a36b-274">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-274">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="2a36b-275">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-275">ShellKillWord</span></span>

<span data-ttu-id="2a36b-276">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-276">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="2a36b-277">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-277">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="2a36b-278">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-278">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="2a36b-279">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-279">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="2a36b-280">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="2a36b-280">SwapCharacters</span></span>

<span data-ttu-id="2a36b-281">交换当前字符和该字符之前的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-281">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="2a36b-282">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-282">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="2a36b-283">Vi 插入模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-283">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="2a36b-284">Vi 命令模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-284">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="2a36b-285">撤消</span><span class="sxs-lookup"><span data-stu-id="2a36b-285">Undo</span></span>

<span data-ttu-id="2a36b-286">撤消上一个编辑。</span><span class="sxs-lookup"><span data-stu-id="2a36b-286">Undo a previous edit.</span></span>

- <span data-ttu-id="2a36b-287">Cmd：`<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-287">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="2a36b-288">Emacs： `<Ctrl+_>` ， `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-288">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="2a36b-289">Vi 插入模式： `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-289">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="2a36b-290">Vi 命令模式： `<Ctrl+z>` ， `<u>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-290">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="2a36b-291">UndoAll</span><span class="sxs-lookup"><span data-stu-id="2a36b-291">UndoAll</span></span>

<span data-ttu-id="2a36b-292">撤消对行的所有以前的编辑。</span><span class="sxs-lookup"><span data-stu-id="2a36b-292">Undo all previous edits for line.</span></span>

- <span data-ttu-id="2a36b-293">Vi 命令模式： `<U>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-293">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="2a36b-294">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="2a36b-294">UnixWordRubout</span></span>

<span data-ttu-id="2a36b-295">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-295">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="2a36b-296">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-296">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="2a36b-297">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-297">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2a36b-298">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-298">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="2a36b-299">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-299">ValidateAndAcceptLine</span></span>

<span data-ttu-id="2a36b-300">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-300">Attempt to execute the current input.</span></span> <span data-ttu-id="2a36b-301">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-301">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="2a36b-302">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-302">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="2a36b-303">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-303">ViAcceptLine</span></span>

<span data-ttu-id="2a36b-304">接受行并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="2a36b-304">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="2a36b-305">Vi 命令模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-305">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="2a36b-306">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="2a36b-306">ViAcceptLineOrExit</span></span>

<span data-ttu-id="2a36b-307">与 Emacs 模式下的 DeleteCharOrExit 类似，但接受行而不是删除字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-307">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="2a36b-308">Vi 插入模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-308">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="2a36b-309">Vi 命令模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-309">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="2a36b-310">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-310">ViAppendLine</span></span>

<span data-ttu-id="2a36b-311">新行插入到当前行的下方。</span><span class="sxs-lookup"><span data-stu-id="2a36b-311">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="2a36b-312">Vi 命令模式： `<o>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-312">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="2a36b-313">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-313">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="2a36b-314">删除上一个词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-314">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="2a36b-315">Vi 命令模式： `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-315">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="2a36b-316">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-316">ViBackwardGlob</span></span>

<span data-ttu-id="2a36b-317">将光标移回上一个词的开头，仅使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-317">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="2a36b-318">Vi 命令模式： `<B>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-318">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="2a36b-319">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="2a36b-319">ViDeleteBrace</span></span>

<span data-ttu-id="2a36b-320">查找匹配的大括号、圆括号或方括号，并删除其中的所有内容，包括大括号。</span><span class="sxs-lookup"><span data-stu-id="2a36b-320">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="2a36b-321">Vi 命令模式： `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-321">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="2a36b-322">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-322">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="2a36b-323">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-323">Delete to the end of the word.</span></span>

- <span data-ttu-id="2a36b-324">Vi 命令模式： `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-324">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="2a36b-325">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-325">ViDeleteGlob</span></span>

<span data-ttu-id="2a36b-326">删除下一个 glob (空格分隔的单词) 。</span><span class="sxs-lookup"><span data-stu-id="2a36b-326">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="2a36b-327">Vi 命令模式： `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-327">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="2a36b-328">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-328">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="2a36b-329">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-329">Deletes until given character.</span></span>

- <span data-ttu-id="2a36b-330">Vi 命令模式： `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-330">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="2a36b-331">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-331">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="2a36b-332">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-332">Deletes until given character.</span></span>

- <span data-ttu-id="2a36b-333">Vi 命令模式： `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-333">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="2a36b-334">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-334">ViDeleteToChar</span></span>

<span data-ttu-id="2a36b-335">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-335">Deletes until given character.</span></span>

- <span data-ttu-id="2a36b-336">Vi 命令模式： `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-336">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="2a36b-337">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-337">ViDeleteToCharBackward</span></span>

<span data-ttu-id="2a36b-338">向后删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-338">Deletes backwards until given character.</span></span>

- <span data-ttu-id="2a36b-339">Vi 命令模式： `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-339">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="2a36b-340">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="2a36b-340">ViInsertAtBegining</span></span>

<span data-ttu-id="2a36b-341">切换到插入模式，并将光标置于行首。</span><span class="sxs-lookup"><span data-stu-id="2a36b-341">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="2a36b-342">Vi 命令模式： `<I>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-342">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="2a36b-343">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="2a36b-343">ViInsertAtEnd</span></span>

<span data-ttu-id="2a36b-344">切换到插入模式，并将光标置于行的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-344">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="2a36b-345">Vi 命令模式： `<A>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-345">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="2a36b-346">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-346">ViInsertLine</span></span>

<span data-ttu-id="2a36b-347">在当前行的上方插入新行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-347">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="2a36b-348">Vi 命令模式： `<O>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-348">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="2a36b-349">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="2a36b-349">ViInsertWithAppend</span></span>

<span data-ttu-id="2a36b-350">从当前行位置追加。</span><span class="sxs-lookup"><span data-stu-id="2a36b-350">Append from the current line position.</span></span>

- <span data-ttu-id="2a36b-351">Vi 命令模式： `<a>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-351">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="2a36b-352">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="2a36b-352">ViInsertWithDelete</span></span>

<span data-ttu-id="2a36b-353">删除当前字符并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="2a36b-353">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="2a36b-354">Vi 命令模式： `<s>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-354">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="2a36b-355">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="2a36b-355">ViJoinLines</span></span>

<span data-ttu-id="2a36b-356">联接当前行和下一行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-356">Joins the current line and the next line.</span></span>

- <span data-ttu-id="2a36b-357">Vi 命令模式： `<J>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-357">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="2a36b-358">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-358">ViReplaceLine</span></span>

<span data-ttu-id="2a36b-359">擦除整个命令行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-359">Erase the entire command line.</span></span>

- <span data-ttu-id="2a36b-360">Vi 命令模式： `<S>` ， `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-360">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="2a36b-361">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-361">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="2a36b-362">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-362">Replaces until given character.</span></span>

- <span data-ttu-id="2a36b-363">Vi 命令模式： `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-363">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="2a36b-364">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-364">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="2a36b-365">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-365">Replaces until given character.</span></span>

- <span data-ttu-id="2a36b-366">Vi 命令模式： `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-366">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="2a36b-367">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-367">ViReplaceToChar</span></span>

<span data-ttu-id="2a36b-368">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-368">Deletes until given character.</span></span>

- <span data-ttu-id="2a36b-369">Vi 命令模式： `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-369">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="2a36b-370">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-370">ViReplaceToCharBackward</span></span>

<span data-ttu-id="2a36b-371">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-371">Replaces until given character.</span></span>

- <span data-ttu-id="2a36b-372">Vi 命令模式： `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-372">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="2a36b-373">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-373">ViYankBeginningOfLine</span></span>

<span data-ttu-id="2a36b-374">从缓冲区的开头到游标的 Yank。</span><span class="sxs-lookup"><span data-stu-id="2a36b-374">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="2a36b-375">Vi 命令模式： `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-375">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="2a36b-376">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-376">ViYankEndOfGlob</span></span>

<span data-ttu-id="2a36b-377">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-377">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="2a36b-378">Vi 命令模式： `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-378">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="2a36b-379">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-379">ViYankEndOfWord</span></span>

<span data-ttu-id="2a36b-380">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-380">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="2a36b-381">Vi 命令模式： `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-381">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="2a36b-382">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="2a36b-382">ViYankLeft</span></span>

<span data-ttu-id="2a36b-383">Yank 字符 (s) 光标左侧。</span><span class="sxs-lookup"><span data-stu-id="2a36b-383">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="2a36b-384">Vi 命令模式： `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-384">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="2a36b-385">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-385">ViYankLine</span></span>

<span data-ttu-id="2a36b-386">Yank 整个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2a36b-386">Yank the entire buffer.</span></span>

- <span data-ttu-id="2a36b-387">Vi 命令模式： `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-387">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="2a36b-388">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-388">ViYankNextGlob</span></span>

<span data-ttu-id="2a36b-389">Yank 从 cursor 到下一个单词 () 的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-389">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="2a36b-390">Vi 命令模式： `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-390">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="2a36b-391">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-391">ViYankNextWord</span></span>

<span data-ttu-id="2a36b-392">Yank 在游标后) 的单词 (。</span><span class="sxs-lookup"><span data-stu-id="2a36b-392">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="2a36b-393">Vi 命令模式： `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-393">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="2a36b-394">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="2a36b-394">ViYankPercent</span></span>

<span data-ttu-id="2a36b-395">Yank 匹配的大括号。</span><span class="sxs-lookup"><span data-stu-id="2a36b-395">Yank to/from matching brace.</span></span>

- <span data-ttu-id="2a36b-396">Vi 命令模式： `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-396">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="2a36b-397">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-397">ViYankPreviousGlob</span></span>

<span data-ttu-id="2a36b-398">从单词 (开始，) 到游标。</span><span class="sxs-lookup"><span data-stu-id="2a36b-398">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="2a36b-399">Vi 命令模式： `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-399">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="2a36b-400">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-400">ViYankPreviousWord</span></span>

<span data-ttu-id="2a36b-401">Yank 在游标前)  (s。</span><span class="sxs-lookup"><span data-stu-id="2a36b-401">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="2a36b-402">Vi 命令模式： `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-402">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="2a36b-403">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="2a36b-403">ViYankRight</span></span>

<span data-ttu-id="2a36b-404">Yank 字符 (s) 光标右侧和右侧。</span><span class="sxs-lookup"><span data-stu-id="2a36b-404">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="2a36b-405">Vi 命令模式： `<y,l>` ， `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-405">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="2a36b-406">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-406">ViYankToEndOfLine</span></span>

<span data-ttu-id="2a36b-407">Yank 从游标到缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-407">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="2a36b-408">Vi 命令模式： `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-408">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="2a36b-409">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-409">ViYankToFirstChar</span></span>

<span data-ttu-id="2a36b-410">从第一个非空白字符 Yank 到游标。</span><span class="sxs-lookup"><span data-stu-id="2a36b-410">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="2a36b-411">Vi 命令模式： `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-411">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="2a36b-412">Yank</span><span class="sxs-lookup"><span data-stu-id="2a36b-412">Yank</span></span>

<span data-ttu-id="2a36b-413">将最近终止的文本添加到输入中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-413">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="2a36b-414">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-414">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="2a36b-415">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="2a36b-415">YankLastArg</span></span>

<span data-ttu-id="2a36b-416">Yank 上一个历史记录行中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-416">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="2a36b-417">如果使用参数，则第一次调用时，其行为就像 YankNthArg。</span><span class="sxs-lookup"><span data-stu-id="2a36b-417">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="2a36b-418">如果多次调用，则会循环访问历史记录，而 arg 会将方向设置 (负反转方向。 ) </span><span class="sxs-lookup"><span data-stu-id="2a36b-418">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="2a36b-419">Cmd：`<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-419">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="2a36b-420">Emacs： `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-420">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="2a36b-421">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="2a36b-421">YankNthArg</span></span>

<span data-ttu-id="2a36b-422">Yank 从上一历史记录行) 命令后 (第一个参数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-422">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="2a36b-423">对于参数，yank 从 0) 开始 (第 n 个参数，如果参数为负数，则从最后一个参数开始。</span><span class="sxs-lookup"><span data-stu-id="2a36b-423">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="2a36b-424">Emacs： `<Ctrl+Alt+y>` ， `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-424">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="2a36b-425">YankPop</span><span class="sxs-lookup"><span data-stu-id="2a36b-425">YankPop</span></span>

<span data-ttu-id="2a36b-426">如果上一操作是 Yank 或 YankPop，则将以前的拔掉文本替换为下一个终止的文本。</span><span class="sxs-lookup"><span data-stu-id="2a36b-426">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="2a36b-427">Emacs： `<Alt+y>` ， `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-427">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="2a36b-428">游标移动函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-428">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="2a36b-429">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-429">BackwardChar</span></span>

<span data-ttu-id="2a36b-430">将光标向左移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-430">Move the cursor one character to the left.</span></span> <span data-ttu-id="2a36b-431">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-431">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="2a36b-432">Cmd：`<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-432">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="2a36b-433">Emacs： `<LeftArrow>` ， `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-433">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="2a36b-434">Vi 插入模式： `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-434">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="2a36b-435">Vi 命令模式： `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-435">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="2a36b-436">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-436">BackwardWord</span></span>

<span data-ttu-id="2a36b-437">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-437">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="2a36b-438">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-438">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2a36b-439">Cmd：`<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-439">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="2a36b-440">Emacs： `<Alt+b>` ， `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-440">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="2a36b-441">Vi 插入模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-441">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="2a36b-442">Vi 命令模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-442">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="2a36b-443">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-443">BeginningOfLine</span></span>

<span data-ttu-id="2a36b-444">如果输入具有多个行，则移动到当前行的开头，或者，如果已位于行首，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-444">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="2a36b-445">如果输入具有单行，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-445">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="2a36b-446">Cmd：`<Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-446">Cmd: `<Home>`</span></span>
- <span data-ttu-id="2a36b-447">Emacs： `<Home>` ， `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-447">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="2a36b-448">Vi 插入模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-448">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="2a36b-449">Vi 命令模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-449">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="2a36b-450">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-450">EndOfLine</span></span>

<span data-ttu-id="2a36b-451">如果输入包含多行，则移动到当前行的末尾，或者，如果已位于行尾，则转到输入的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-451">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="2a36b-452">如果输入具有单行，则移动到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-452">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="2a36b-453">Cmd：`<End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-453">Cmd: `<End>`</span></span>
- <span data-ttu-id="2a36b-454">Emacs： `<End>` ， `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-454">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="2a36b-455">Vi 插入模式： `<End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-455">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="2a36b-456">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-456">ForwardChar</span></span>

<span data-ttu-id="2a36b-457">将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-457">Move the cursor one character to the right.</span></span> <span data-ttu-id="2a36b-458">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-458">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="2a36b-459">Cmd：`<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-459">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="2a36b-460">Emacs： `<RightArrow>` ， `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-460">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="2a36b-461">Vi 插入模式： `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-461">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="2a36b-462">Vi 命令模式： `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-462">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="2a36b-463">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-463">ForwardWord</span></span>

<span data-ttu-id="2a36b-464">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-464">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="2a36b-465">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-465">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2a36b-466">Emacs： `<Alt+f>` ， `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-466">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="2a36b-467">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="2a36b-467">GotoBrace</span></span>

<span data-ttu-id="2a36b-468">中转到匹配的大括号、圆括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="2a36b-468">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="2a36b-469">Cmd：`<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-469">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="2a36b-470">Vi 插入模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-470">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="2a36b-471">Vi 命令模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-471">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="2a36b-472">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="2a36b-472">GotoColumn</span></span>

<span data-ttu-id="2a36b-473">转到 arg 指示的列。</span><span class="sxs-lookup"><span data-stu-id="2a36b-473">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="2a36b-474">Vi 命令模式： `<|>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-474">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="2a36b-475">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-475">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="2a36b-476">将光标移动到行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-476">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="2a36b-477">Vi 命令模式： `<^>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-477">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="2a36b-478">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-478">MoveToEndOfLine</span></span>

<span data-ttu-id="2a36b-479">将光标移到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-479">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="2a36b-480">Vi 命令模式： `<End>` ， `<$>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-480">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="2a36b-481">NextLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-481">NextLine</span></span>

<span data-ttu-id="2a36b-482">将光标移到下一行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-482">Move the cursor to the next line.</span></span>

- <span data-ttu-id="2a36b-483">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-483">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="2a36b-484">NextWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-484">NextWord</span></span>

<span data-ttu-id="2a36b-485">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-485">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="2a36b-486">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-486">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2a36b-487">Cmd：`<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-487">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="2a36b-488">Vi 插入模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-488">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="2a36b-489">Vi 命令模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-489">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="2a36b-490">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="2a36b-490">NextWordEnd</span></span>

<span data-ttu-id="2a36b-491">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-491">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="2a36b-492">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-492">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2a36b-493">Vi 命令模式： `<e>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-493">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="2a36b-494">PreviousLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-494">PreviousLine</span></span>

<span data-ttu-id="2a36b-495">将光标移到上一行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-495">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="2a36b-496">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-496">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="2a36b-497">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-497">ShellBackwardWord</span></span>

<span data-ttu-id="2a36b-498">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-498">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="2a36b-499">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-499">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="2a36b-500">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-500">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="2a36b-501">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-501">ShellForwardWord</span></span>

<span data-ttu-id="2a36b-502">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-502">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="2a36b-503">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="2a36b-504">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-504">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="2a36b-505">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-505">ShellNextWord</span></span>

<span data-ttu-id="2a36b-506">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="2a36b-506">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="2a36b-507">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="2a36b-508">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-508">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="2a36b-509">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-509">ViBackwardWord</span></span>

<span data-ttu-id="2a36b-510">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-510">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="2a36b-511">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-511">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2a36b-512">Vi 命令模式： `<b>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-512">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="2a36b-513">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-513">ViEndOfGlob</span></span>

<span data-ttu-id="2a36b-514">将光标移到单词的末尾，只使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-514">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="2a36b-515">Vi 命令模式： `<E>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-515">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="2a36b-516">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-516">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="2a36b-517">移到上一个词的末尾，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-517">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="2a36b-518">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-518">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="2a36b-519">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="2a36b-519">ViGotoBrace</span></span>

<span data-ttu-id="2a36b-520">类似于 GotoBrace，但基于字符，而不是基于标记。</span><span class="sxs-lookup"><span data-stu-id="2a36b-520">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="2a36b-521">Vi 命令模式： `<%>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-521">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="2a36b-522">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="2a36b-522">ViNextGlob</span></span>

<span data-ttu-id="2a36b-523">移到下一个单词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-523">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="2a36b-524">Vi 命令模式： `<W>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-524">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="2a36b-525">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-525">ViNextWord</span></span>

<span data-ttu-id="2a36b-526">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-526">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="2a36b-527">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="2a36b-527">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2a36b-528">Vi 命令模式： `<w>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-528">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="2a36b-529">历史记录函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-529">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="2a36b-530">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-530">BeginningOfHistory</span></span>

<span data-ttu-id="2a36b-531">移到历史记录中的第一项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-531">Move to the first item in the history.</span></span>

- <span data-ttu-id="2a36b-532">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="2a36b-532">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="2a36b-533">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-533">ClearHistory</span></span>

<span data-ttu-id="2a36b-534">清除 PSReadLine 中的历史记录。</span><span class="sxs-lookup"><span data-stu-id="2a36b-534">Clears history in PSReadLine.</span></span> <span data-ttu-id="2a36b-535">这不会影响 PowerShell 历史记录。</span><span class="sxs-lookup"><span data-stu-id="2a36b-535">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="2a36b-536">Cmd：`<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-536">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="2a36b-537">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-537">EndOfHistory</span></span>

<span data-ttu-id="2a36b-538">移到历史记录中 (当前输入) 的最后一项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-538">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="2a36b-539">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-539">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="2a36b-540">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-540">ForwardSearchHistory</span></span>

<span data-ttu-id="2a36b-541">通过历史记录执行增量向前搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-541">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="2a36b-542">Cmd：`<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-542">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="2a36b-543">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-543">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="2a36b-544">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-544">HistorySearchBackward</span></span>

<span data-ttu-id="2a36b-545">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项，该匹配项与开始与输入和光标之间的字符匹配。</span><span class="sxs-lookup"><span data-stu-id="2a36b-545">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="2a36b-546">Cmd：`<F8>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-546">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="2a36b-547">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="2a36b-547">HistorySearchForward</span></span>

<span data-ttu-id="2a36b-548">将当前输入替换为 PSReadLine 历史记录中与 start 与 input 和 cursor 之间的字符相匹配的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-548">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="2a36b-549">Cmd：`<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-549">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="2a36b-550">NextHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-550">NextHistory</span></span>

<span data-ttu-id="2a36b-551">将当前输入替换为 PSReadLine 历史记录中的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-551">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="2a36b-552">Cmd：`<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-552">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="2a36b-553">Emacs： `<DownArrow>` ， `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-553">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="2a36b-554">Vi 插入模式： `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-554">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="2a36b-555">Vi 命令模式： `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-555">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="2a36b-556">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-556">PreviousHistory</span></span>

<span data-ttu-id="2a36b-557">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-557">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="2a36b-558">Cmd：`<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-558">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="2a36b-559">Emacs： `<UpArrow>` ， `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-559">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="2a36b-560">Vi 插入模式： `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-560">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="2a36b-561">Vi 命令模式： `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="2a36b-561">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="2a36b-562">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="2a36b-562">ReverseSearchHistory</span></span>

<span data-ttu-id="2a36b-563">通过历史记录执行增量向后搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-563">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="2a36b-564">Cmd：`<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-564">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="2a36b-565">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-565">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="2a36b-566">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-566">ViSearchHistoryBackward</span></span>

<span data-ttu-id="2a36b-567">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-567">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="2a36b-568">Vi 插入模式： `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-568">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="2a36b-569">Vi 命令模式： `</>` ， `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-569">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="2a36b-570">完成函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-570">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="2a36b-571">完成</span><span class="sxs-lookup"><span data-stu-id="2a36b-571">Complete</span></span>

<span data-ttu-id="2a36b-572">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="2a36b-572">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="2a36b-573">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="2a36b-573">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="2a36b-574">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="2a36b-574">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="2a36b-575">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-575">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="2a36b-576">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="2a36b-576">MenuComplete</span></span>

<span data-ttu-id="2a36b-577">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="2a36b-577">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="2a36b-578">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="2a36b-578">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="2a36b-579">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="2a36b-579">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="2a36b-580">Cmd：`<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-580">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="2a36b-581">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-581">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="2a36b-582">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="2a36b-582">PossibleCompletions</span></span>

<span data-ttu-id="2a36b-583">显示可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="2a36b-583">Display the list of possible completions.</span></span>

- <span data-ttu-id="2a36b-584">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-584">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="2a36b-585">Vi 插入模式： `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-585">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="2a36b-586">Vi 命令模式： `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-586">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="2a36b-587">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="2a36b-587">TabCompleteNext</span></span>

<span data-ttu-id="2a36b-588">尝试使用下一个可用完成来完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="2a36b-588">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="2a36b-589">Cmd：`<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-589">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="2a36b-590">Vi 命令模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-590">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="2a36b-591">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="2a36b-591">TabCompletePrevious</span></span>

<span data-ttu-id="2a36b-592">尝试使用以前的可用完成功能完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="2a36b-592">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="2a36b-593">Cmd：`<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-593">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="2a36b-594">Vi 命令模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-594">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="2a36b-595">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="2a36b-595">ViTabCompleteNext</span></span>

<span data-ttu-id="2a36b-596">结束当前编辑组（如果需要），并调用 TabCompleteNext。</span><span class="sxs-lookup"><span data-stu-id="2a36b-596">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="2a36b-597">Vi 插入模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-597">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="2a36b-598">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="2a36b-598">ViTabCompletePrevious</span></span>

<span data-ttu-id="2a36b-599">结束当前编辑组（如果需要），并调用 TabCompletePrevious。</span><span class="sxs-lookup"><span data-stu-id="2a36b-599">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="2a36b-600">Vi 插入模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-600">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="2a36b-601">杂项函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-601">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="2a36b-602">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="2a36b-602">CaptureScreen</span></span>

<span data-ttu-id="2a36b-603">启动交互屏幕捕获-向上/向下箭头选择 "线条"，将选定文本作为文本和 html 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="2a36b-603">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="2a36b-604">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-604">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="2a36b-605">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="2a36b-605">ClearScreen</span></span>

<span data-ttu-id="2a36b-606">清除屏幕并在屏幕的顶部绘制当前线条。</span><span class="sxs-lookup"><span data-stu-id="2a36b-606">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="2a36b-607">Cmd：`<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-607">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="2a36b-608">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-608">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="2a36b-609">Vi 插入模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-609">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="2a36b-610">Vi 命令模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-610">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="2a36b-611">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="2a36b-611">DigitArgument</span></span>

<span data-ttu-id="2a36b-612">启动新的数字参数，使其传递到其他函数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-612">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="2a36b-613">Cmd： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="2a36b-613">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="2a36b-614">Emacs： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="2a36b-614">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="2a36b-615">Vi 命令模式： `<0>` 、 `<1>` 、 `<2>` 、 `<3>` 、 `<4>` 、 `<5>` 、 `<6>` 、 `<7>` 、 `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-615">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="2a36b-616">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="2a36b-616">InvokePrompt</span></span>

<span data-ttu-id="2a36b-617">清除当前提示符并调用 prompt 函数以重新显示提示符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-617">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="2a36b-618">适用于更改状态的自定义密钥处理程序，例如更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="2a36b-618">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="2a36b-619">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-619">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="2a36b-620">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="2a36b-620">ScrollDisplayDown</span></span>

<span data-ttu-id="2a36b-621">将显示向下滚动一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="2a36b-621">Scroll the display down one screen.</span></span>

- <span data-ttu-id="2a36b-622">Cmd：`<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-622">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="2a36b-623">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-623">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="2a36b-624">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-624">ScrollDisplayDownLine</span></span>

<span data-ttu-id="2a36b-625">将显示向下滚动一行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-625">Scroll the display down one line.</span></span>

- <span data-ttu-id="2a36b-626">Cmd：`<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-626">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="2a36b-627">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-627">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="2a36b-628">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="2a36b-628">ScrollDisplayToCursor</span></span>

<span data-ttu-id="2a36b-629">将显示滚动到光标处。</span><span class="sxs-lookup"><span data-stu-id="2a36b-629">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="2a36b-630">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-630">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="2a36b-631">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="2a36b-631">ScrollDisplayTop</span></span>

<span data-ttu-id="2a36b-632">向顶部滚动显示。</span><span class="sxs-lookup"><span data-stu-id="2a36b-632">Scroll the display to the top.</span></span>

- <span data-ttu-id="2a36b-633">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-633">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="2a36b-634">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="2a36b-634">ScrollDisplayUp</span></span>

<span data-ttu-id="2a36b-635">将显示向上滚动一屏。</span><span class="sxs-lookup"><span data-stu-id="2a36b-635">Scroll the display up one screen.</span></span>

- <span data-ttu-id="2a36b-636">Cmd：`<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-636">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="2a36b-637">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-637">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="2a36b-638">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-638">ScrollDisplayUpLine</span></span>

<span data-ttu-id="2a36b-639">将显示向上滚动一行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-639">Scroll the display up one line.</span></span>

- <span data-ttu-id="2a36b-640">Cmd：`<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-640">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="2a36b-641">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-641">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="2a36b-642">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="2a36b-642">SelfInsert</span></span>

<span data-ttu-id="2a36b-643">插入密钥。</span><span class="sxs-lookup"><span data-stu-id="2a36b-643">Insert the key.</span></span>

- <span data-ttu-id="2a36b-644">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-644">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="2a36b-645">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="2a36b-645">ShowKeyBindings</span></span>

<span data-ttu-id="2a36b-646">显示所有绑定键。</span><span class="sxs-lookup"><span data-stu-id="2a36b-646">Show all bound keys.</span></span>

- <span data-ttu-id="2a36b-647">Cmd：`<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-647">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="2a36b-648">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-648">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="2a36b-649">Vi 插入模式： `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-649">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="2a36b-650">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="2a36b-650">ViCommandMode</span></span>

<span data-ttu-id="2a36b-651">将当前运行模式从 Vi-Insert 切换到 Vi-Command。</span><span class="sxs-lookup"><span data-stu-id="2a36b-651">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="2a36b-652">Vi 插入模式： `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-652">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="2a36b-653">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="2a36b-653">ViDigitArgumentInChord</span></span>

<span data-ttu-id="2a36b-654">启动新的数字参数，将其传递给其他函数，同时使用 vi 的鼠标左键之一。</span><span class="sxs-lookup"><span data-stu-id="2a36b-654">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="2a36b-655">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-655">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="2a36b-656">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="2a36b-656">ViEditVisually</span></span>

<span data-ttu-id="2a36b-657">在 $env： EDITOR 或 $env：视觉对象指定的文本编辑器中编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-657">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="2a36b-658">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-658">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="2a36b-659">Vi 命令模式： `<v>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-659">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="2a36b-660">ViExit</span><span class="sxs-lookup"><span data-stu-id="2a36b-660">ViExit</span></span>

<span data-ttu-id="2a36b-661">退出 shell。</span><span class="sxs-lookup"><span data-stu-id="2a36b-661">Exits the shell.</span></span>

- <span data-ttu-id="2a36b-662">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-662">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="2a36b-663">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="2a36b-663">ViInsertMode</span></span>

<span data-ttu-id="2a36b-664">切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="2a36b-664">Switch to Insert mode.</span></span>

- <span data-ttu-id="2a36b-665">Vi 命令模式： `<i>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-665">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="2a36b-666">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="2a36b-666">WhatIsKey</span></span>

<span data-ttu-id="2a36b-667">阅读密钥，并告诉我密钥的绑定内容。</span><span class="sxs-lookup"><span data-stu-id="2a36b-667">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="2a36b-668">Cmd：`<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-668">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="2a36b-669">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-669">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="2a36b-670">选择函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-670">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="2a36b-671">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="2a36b-671">ExchangePointAndMark</span></span>

<span data-ttu-id="2a36b-672">将光标置于标记的位置，并将标记移到光标所在的位置。</span><span class="sxs-lookup"><span data-stu-id="2a36b-672">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="2a36b-673">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-673">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="2a36b-674">SelectAll</span><span class="sxs-lookup"><span data-stu-id="2a36b-674">SelectAll</span></span>

<span data-ttu-id="2a36b-675">选择整行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-675">Select the entire line.</span></span>

- <span data-ttu-id="2a36b-676">Cmd：`<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-676">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="2a36b-677">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-677">SelectBackwardChar</span></span>

<span data-ttu-id="2a36b-678">调整当前选定内容以包括前一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-678">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="2a36b-679">Cmd：`<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-679">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="2a36b-680">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-680">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="2a36b-681">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-681">SelectBackwardsLine</span></span>

<span data-ttu-id="2a36b-682">调整当前所选内容，使其包括从光标到行的开头。</span><span class="sxs-lookup"><span data-stu-id="2a36b-682">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="2a36b-683">Cmd：`<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-683">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="2a36b-684">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-684">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="2a36b-685">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-685">SelectBackwardWord</span></span>

<span data-ttu-id="2a36b-686">调整当前所选内容以包含上一个词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-686">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="2a36b-687">Cmd：`<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-687">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="2a36b-688">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-688">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="2a36b-689">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-689">SelectForwardChar</span></span>

<span data-ttu-id="2a36b-690">调整当前所选内容以包含下一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-690">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="2a36b-691">Cmd：`<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-691">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="2a36b-692">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-692">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="2a36b-693">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-693">SelectForwardWord</span></span>

<span data-ttu-id="2a36b-694">使用 ForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-694">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="2a36b-695">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-695">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="2a36b-696">SelectLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-696">SelectLine</span></span>

<span data-ttu-id="2a36b-697">调整当前所选内容，使其包括从光标到行尾的内容。</span><span class="sxs-lookup"><span data-stu-id="2a36b-697">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="2a36b-698">Cmd：`<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-698">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="2a36b-699">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-699">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="2a36b-700">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-700">SelectNextWord</span></span>

<span data-ttu-id="2a36b-701">调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-701">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="2a36b-702">Cmd：`<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-702">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="2a36b-703">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-703">SelectShellBackwardWord</span></span>

<span data-ttu-id="2a36b-704">使用 ShellBackwardWord 调整当前所选内容，使其包含前一词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-704">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="2a36b-705">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-705">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="2a36b-706">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-706">SelectShellForwardWord</span></span>

<span data-ttu-id="2a36b-707">使用 ShellForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-707">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="2a36b-708">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-708">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="2a36b-709">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="2a36b-709">SelectShellNextWord</span></span>

<span data-ttu-id="2a36b-710">使用 ShellNextWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="2a36b-710">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="2a36b-711">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-711">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="2a36b-712">SetMark</span><span class="sxs-lookup"><span data-stu-id="2a36b-712">SetMark</span></span>

<span data-ttu-id="2a36b-713">标记光标的当前位置，以供后续编辑命令使用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-713">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="2a36b-714">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="2a36b-714">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="2a36b-715">搜索函数</span><span class="sxs-lookup"><span data-stu-id="2a36b-715">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="2a36b-716">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="2a36b-716">CharacterSearch</span></span>

<span data-ttu-id="2a36b-717">读取字符并向前搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-717">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="2a36b-718">如果指定了参数，则向前搜索 (或向后) 对于第 n 个匹配项为负。</span><span class="sxs-lookup"><span data-stu-id="2a36b-718">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="2a36b-719">Cmd：`<F3>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-719">Cmd: `<F3>`</span></span>
- <span data-ttu-id="2a36b-720">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-720">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="2a36b-721">Vi 插入模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-721">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="2a36b-722">Vi 命令模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-722">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="2a36b-723">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-723">CharacterSearchBackward</span></span>

<span data-ttu-id="2a36b-724">读取字符并向后搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2a36b-724">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="2a36b-725">如果指定了参数，则在第 n 个匹配项) 反向搜索时 (或转发。</span><span class="sxs-lookup"><span data-stu-id="2a36b-725">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="2a36b-726">Cmd：`<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-726">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="2a36b-727">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-727">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="2a36b-728">Vi 插入模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-728">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="2a36b-729">Vi 命令模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-729">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="2a36b-730">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="2a36b-730">RepeatLastCharSearch</span></span>

<span data-ttu-id="2a36b-731">重复上次记录的字符搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-731">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="2a36b-732">Vi 命令模式： `<;>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-732">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="2a36b-733">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="2a36b-733">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="2a36b-734">重复上次记录的字符搜索，但采用相反方向。</span><span class="sxs-lookup"><span data-stu-id="2a36b-734">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="2a36b-735">Vi 命令模式： `<,>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-735">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="2a36b-736">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="2a36b-736">RepeatSearch</span></span>

<span data-ttu-id="2a36b-737">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-737">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="2a36b-738">Vi 命令模式： `<n>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-738">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="2a36b-739">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-739">RepeatSearchBackward</span></span>

<span data-ttu-id="2a36b-740">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="2a36b-741">Vi 命令模式： `<N>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-741">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="2a36b-742">SearchChar</span><span class="sxs-lookup"><span data-stu-id="2a36b-742">SearchChar</span></span>

<span data-ttu-id="2a36b-743">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-743">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="2a36b-744">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="2a36b-744">This is for 't' functionality.</span></span>

- <span data-ttu-id="2a36b-745">Vi 命令模式： `<f>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-745">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="2a36b-746">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="2a36b-746">SearchCharBackward</span></span>

<span data-ttu-id="2a36b-747">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-747">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="2a36b-748">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="2a36b-748">This is for 'T' functionality.</span></span>

- <span data-ttu-id="2a36b-749">Vi 命令模式： `<F>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-749">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="2a36b-750">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="2a36b-750">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="2a36b-751">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="2a36b-752">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="2a36b-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="2a36b-753">Vi 命令模式： `<T>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-753">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="2a36b-754">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="2a36b-754">SearchCharWithBackoff</span></span>

<span data-ttu-id="2a36b-755">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-755">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="2a36b-756">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="2a36b-756">This is for 't' functionality.</span></span>

- <span data-ttu-id="2a36b-757">Vi 命令模式： `<t>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-757">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="2a36b-758">SearchForward</span><span class="sxs-lookup"><span data-stu-id="2a36b-758">SearchForward</span></span>

<span data-ttu-id="2a36b-759">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="2a36b-759">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="2a36b-760">Vi 插入模式： `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-760">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="2a36b-761">Vi 命令模式： `<?>` ， `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2a36b-761">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="2a36b-762">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="2a36b-762">Custom Key Bindings</span></span>

<span data-ttu-id="2a36b-763">PSReadLine 支持使用 cmdlet 的自定义键绑定 `Set-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="2a36b-763">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="2a36b-764">大多数自定义键绑定调用上述函数之一，例如</span><span class="sxs-lookup"><span data-stu-id="2a36b-764">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="2a36b-765">可以将 ScriptBlock 绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="2a36b-765">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="2a36b-766">ScriptBlock 可以执行任何所需的操作。</span><span class="sxs-lookup"><span data-stu-id="2a36b-766">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="2a36b-767">一些有用的示例包括</span><span class="sxs-lookup"><span data-stu-id="2a36b-767">Some useful examples include</span></span>

- <span data-ttu-id="2a36b-768">编辑命令行</span><span class="sxs-lookup"><span data-stu-id="2a36b-768">edit the command line</span></span>
- <span data-ttu-id="2a36b-769">打开新窗口 (例如，帮助) </span><span class="sxs-lookup"><span data-stu-id="2a36b-769">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="2a36b-770">更改目录而不更改命令行</span><span class="sxs-lookup"><span data-stu-id="2a36b-770">change directories without changing the command line</span></span>

<span data-ttu-id="2a36b-771">ScriptBlock 接收两个参数：</span><span class="sxs-lookup"><span data-stu-id="2a36b-771">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="2a36b-772">`$key` -一个作为触发自定义绑定的密钥的 **[ConsoleKeyInfo]** 对象。</span><span class="sxs-lookup"><span data-stu-id="2a36b-772">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="2a36b-773">如果将相同的 ScriptBlock 绑定到多个键，并且需要根据关键字执行不同的操作，则可以选中 $key。</span><span class="sxs-lookup"><span data-stu-id="2a36b-773">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="2a36b-774">许多自定义绑定会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-774">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="2a36b-775">`$arg` -任意参数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-775">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="2a36b-776">大多数情况下，这将是用户从键绑定 DigitArgument 传递的整数参数。</span><span class="sxs-lookup"><span data-stu-id="2a36b-776">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="2a36b-777">如果绑定不接受参数，则忽略此参数是合理的。</span><span class="sxs-lookup"><span data-stu-id="2a36b-777">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="2a36b-778">我们来看一个示例，该示例将一个命令行添加到历史记录中，而不执行它。</span><span class="sxs-lookup"><span data-stu-id="2a36b-778">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="2a36b-779">如果您认为您忘记了某些事情，但又不想重新输入您已经输入的命令行，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-779">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="2a36b-780">你可以在 PSReadLine 模块文件夹中安装的文件中查看更多示例 `SamplePSReadLineProfile.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="2a36b-780">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="2a36b-781">大多数键绑定使用一些 helper 函数来编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="2a36b-781">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="2a36b-782">下一节将介绍这些 Api。</span><span class="sxs-lookup"><span data-stu-id="2a36b-782">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="2a36b-783">自定义键绑定支持 Api</span><span class="sxs-lookup"><span data-stu-id="2a36b-783">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="2a36b-784">以下函数是 PSConsoleReadLine 中的公共函数，但不能直接绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="2a36b-784">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="2a36b-785">大多数在自定义键绑定中很有用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-785">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="2a36b-786">向历史记录中添加一个命令行而不执行它。</span><span class="sxs-lookup"><span data-stu-id="2a36b-786">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="2a36b-787">清除终止环。</span><span class="sxs-lookup"><span data-stu-id="2a36b-787">Clear the kill-ring.</span></span>  <span data-ttu-id="2a36b-788">这主要用于测试。</span><span class="sxs-lookup"><span data-stu-id="2a36b-788">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="2a36b-789">从开始删除长度字符。</span><span class="sxs-lookup"><span data-stu-id="2a36b-789">Delete length characters from start.</span></span>  <span data-ttu-id="2a36b-790">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="2a36b-790">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="2a36b-791">根据用户首选项执行 Ding 操作。</span><span class="sxs-lookup"><span data-stu-id="2a36b-791">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="2a36b-792">这两个函数检索有关输入缓冲区的当前状态的有用信息。</span><span class="sxs-lookup"><span data-stu-id="2a36b-792">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="2a36b-793">第一种方案更常见用于简单情况。</span><span class="sxs-lookup"><span data-stu-id="2a36b-793">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="2a36b-794">如果绑定使用 Ast 执行更高级的操作，则会使用第二个。</span><span class="sxs-lookup"><span data-stu-id="2a36b-794">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="2a36b-795">此函数由 Get-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-795">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="2a36b-796">此函数由 Get-PSReadLineOption 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-796">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="2a36b-797">如果未在命令行上进行选择，则将在 "开始" 和 "长度" 中返回-1。</span><span class="sxs-lookup"><span data-stu-id="2a36b-797">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="2a36b-798">如果命令行上有选择，则返回选定内容的开始和长度。</span><span class="sxs-lookup"><span data-stu-id="2a36b-798">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="2a36b-799">在光标处插入字符或字符串。</span><span class="sxs-lookup"><span data-stu-id="2a36b-799">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="2a36b-800">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="2a36b-800">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="2a36b-801">这是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="2a36b-801">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="2a36b-802">它不支持递归，因此在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-802">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="2a36b-803">此函数由 Remove-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-803">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="2a36b-804">替换部分输入。</span><span class="sxs-lookup"><span data-stu-id="2a36b-804">Replace some of the input.</span></span> <span data-ttu-id="2a36b-805">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="2a36b-805">This operation supports undo/redo.</span></span> <span data-ttu-id="2a36b-806">这优先于删除后再执行 Insert，因为它被视为单个操作来撤消。</span><span class="sxs-lookup"><span data-stu-id="2a36b-806">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="2a36b-807">将光标移动到给定偏移量。</span><span class="sxs-lookup"><span data-stu-id="2a36b-807">Move the cursor to the given offset.</span></span> <span data-ttu-id="2a36b-808">不跟踪游标移动以便撤消。</span><span class="sxs-lookup"><span data-stu-id="2a36b-808">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="2a36b-809">此函数是 cmdlet PSReadLineOption 使用的帮助器方法，但可能对要临时更改设置的自定义密钥绑定很有用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-809">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="2a36b-810">此帮助器方法用于接受 DigitArgument 的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="2a36b-810">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="2a36b-811">典型调用如下所示</span><span class="sxs-lookup"><span data-stu-id="2a36b-811">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="2a36b-812">注意</span><span class="sxs-lookup"><span data-stu-id="2a36b-812">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="2a36b-813">POWERSHELL 兼容性</span><span class="sxs-lookup"><span data-stu-id="2a36b-813">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="2a36b-814">PSReadLine 要求安装 PowerShell 3.0 或更高版本，以及控制台主机。</span><span class="sxs-lookup"><span data-stu-id="2a36b-814">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="2a36b-815">它在 PowerShell ISE 中不起作用。</span><span class="sxs-lookup"><span data-stu-id="2a36b-815">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="2a36b-816">它在 Visual Studio Code 的控制台中工作。</span><span class="sxs-lookup"><span data-stu-id="2a36b-816">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="2a36b-817">命令历史记录</span><span class="sxs-lookup"><span data-stu-id="2a36b-817">COMMAND HISTORY</span></span>

<span data-ttu-id="2a36b-818">PSReadLine 维护一个历史记录文件，其中包含在命令行中输入的所有命令和数据。</span><span class="sxs-lookup"><span data-stu-id="2a36b-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="2a36b-819">这可能包含敏感数据（包括密码）。</span><span class="sxs-lookup"><span data-stu-id="2a36b-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="2a36b-820">例如，如果使用 cmdlet，则 `ConvertTo-SecureString` 密码将作为纯文本记录到历史记录文件中。</span><span class="sxs-lookup"><span data-stu-id="2a36b-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="2a36b-821">历史记录文件是一个名为的文件 `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="2a36b-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="2a36b-822">在 Windows 系统上，历史记录文件存储在中 `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="2a36b-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="2a36b-823">参与 PSReadLine 的反馈 &</span><span class="sxs-lookup"><span data-stu-id="2a36b-823">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="2a36b-824">GitHub 上的 PSReadLine</span><span class="sxs-lookup"><span data-stu-id="2a36b-824">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="2a36b-825">可在 GitHub 页上随意提交拉取请求或提交反馈。</span><span class="sxs-lookup"><span data-stu-id="2a36b-825">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a36b-826">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a36b-826">SEE ALSO</span></span>

<span data-ttu-id="2a36b-827">PSReadLine 会受到 GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) 库的严重影响。</span><span class="sxs-lookup"><span data-stu-id="2a36b-827">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
