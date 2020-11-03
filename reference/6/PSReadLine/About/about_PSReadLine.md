---
description: PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于 PSReadLine
ms.openlocfilehash: 5b59ffcdfb35c2aa10f8e0caf3a3b365c5bcf93e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200353"
---
# <a name="psreadline"></a><span data-ttu-id="0ef1e-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="0ef1e-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="0ef1e-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="0ef1e-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="0ef1e-107">PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="0ef1e-108">详细说明</span><span class="sxs-lookup"><span data-stu-id="0ef1e-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="0ef1e-109">PSReadLine 2.0 为 PowerShell 控制台提供了强大的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="0ef1e-110">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="0ef1e-110">It provides:</span></span>

- <span data-ttu-id="0ef1e-111">命令行的语法着色</span><span class="sxs-lookup"><span data-stu-id="0ef1e-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="0ef1e-112">语法错误的直观指示</span><span class="sxs-lookup"><span data-stu-id="0ef1e-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="0ef1e-113"> (编辑和历史记录的更好的多行体验) </span><span class="sxs-lookup"><span data-stu-id="0ef1e-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="0ef1e-114">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="0ef1e-114">Customizable key bindings</span></span>
- <span data-ttu-id="0ef1e-115">Cmd 和 Emacs 模式</span><span class="sxs-lookup"><span data-stu-id="0ef1e-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="0ef1e-116">许多配置选项</span><span class="sxs-lookup"><span data-stu-id="0ef1e-116">Many configuration options</span></span>
- <span data-ttu-id="0ef1e-117">在 Cmd 模式下，Bash 样式完成 (可选，默认值为 Emacs 模式) </span><span class="sxs-lookup"><span data-stu-id="0ef1e-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="0ef1e-118">Emacs yank/kill 循环</span><span class="sxs-lookup"><span data-stu-id="0ef1e-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="0ef1e-119">基于 PowerShell 令牌的 "word" 移动和终止</span><span class="sxs-lookup"><span data-stu-id="0ef1e-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="0ef1e-120">类 **[PSConsoleReadLine]** 中提供了以下函数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

> [!NOTE]
> <span data-ttu-id="0ef1e-121">从 PowerShell 7.0 开始，如果检测到屏幕阅读器程序，PowerShell 会跳过在 Windows 上自动加载 PSReadLine。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="0ef1e-122">目前，PSReadLine 不能与屏幕阅读器很好地配合使用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="0ef1e-123">Windows 上 PowerShell 7.0 的默认呈现和格式设置正常。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="0ef1e-124">如有必要，可以手动加载模块。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="0ef1e-125">基本编辑函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="0ef1e-126">中止</span><span class="sxs-lookup"><span data-stu-id="0ef1e-126">Abort</span></span>

<span data-ttu-id="0ef1e-127">中止当前操作，例如增量历史记录搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="0ef1e-128">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="0ef1e-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="0ef1e-129">AcceptAndGetNext</span></span>

<span data-ttu-id="0ef1e-130">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-130">Attempt to execute the current input.</span></span> <span data-ttu-id="0ef1e-131">如果可以 (如 AcceptLine) 执行，则在下一次调用 ReadLine 时，从历史记录中撤回下一项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="0ef1e-132">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="0ef1e-133">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-133">AcceptLine</span></span>

<span data-ttu-id="0ef1e-134">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-134">Attempt to execute the current input.</span></span> <span data-ttu-id="0ef1e-135">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="0ef1e-136">Cmd：`<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="0ef1e-137">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="0ef1e-138">Vi 插入模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="0ef1e-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-139">AddLine</span></span>

<span data-ttu-id="0ef1e-140">继续提示显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="0ef1e-141">这可用于将多行输入作为单个命令输入，即使单个行自动完成输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="0ef1e-142">Cmd：`<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="0ef1e-143">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="0ef1e-144">Vi 插入模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="0ef1e-145">Vi 命令模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="0ef1e-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-146">BackwardDeleteChar</span></span>

<span data-ttu-id="0ef1e-147">删除光标前面的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="0ef1e-148">Cmd： `<Backspace>` ， `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="0ef1e-149">Emacs： `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="0ef1e-150">Vi 插入模式： `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="0ef1e-151">Vi 命令模式： `<X>` ， `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="0ef1e-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-152">BackwardDeleteLine</span></span>

<span data-ttu-id="0ef1e-153">与 BackwardKillLine 一样，从点到行的开头删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-154">Cmd：`<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="0ef1e-155">Vi 插入模式： `<Ctrl+u>` ， `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="0ef1e-156">Vi 命令模式： `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="0ef1e-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-157">BackwardDeleteWord</span></span>

<span data-ttu-id="0ef1e-158">删除上一个词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-158">Deletes the previous word.</span></span>

- <span data-ttu-id="0ef1e-159">Vi 命令模式： `<Ctrl+w>` ， `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="0ef1e-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-160">BackwardKillLine</span></span>

<span data-ttu-id="0ef1e-161">清除输入从输入开始到光标。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="0ef1e-162">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-163">Emacs： `<Ctrl+u>` ， `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="0ef1e-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-164">BackwardKillWord</span></span>

<span data-ttu-id="0ef1e-165">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="0ef1e-166">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="0ef1e-167">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-168">Cmd：`<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="0ef1e-169">Emacs： `<Alt+Backspace>` ， `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="0ef1e-170">Vi 插入模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="0ef1e-171">Vi 命令模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="0ef1e-172">CancelLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-172">CancelLine</span></span>

<span data-ttu-id="0ef1e-173">取消当前输入，将输入保留在屏幕上，但返回到主机以便再次计算提示。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="0ef1e-174">Vi 插入模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="0ef1e-175">Vi 命令模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="0ef1e-176">复制</span><span class="sxs-lookup"><span data-stu-id="0ef1e-176">Copy</span></span>

<span data-ttu-id="0ef1e-177">将所选区域复制到系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="0ef1e-178">如果未选择区域，则复制整行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="0ef1e-179">Cmd：`<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="0ef1e-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-180">CopyOrCancelLine</span></span>

<span data-ttu-id="0ef1e-181">如果选择了文本，请将其复制到剪贴板，否则取消该行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="0ef1e-182">Cmd：`<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="0ef1e-183">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="0ef1e-184">剪切</span><span class="sxs-lookup"><span data-stu-id="0ef1e-184">Cut</span></span>

<span data-ttu-id="0ef1e-185">删除所选区域将删除的文本放入系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="0ef1e-186">Cmd：`<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="0ef1e-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-187">DeleteChar</span></span>

<span data-ttu-id="0ef1e-188">删除光标下的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="0ef1e-189">Cmd：`<Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="0ef1e-190">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="0ef1e-191">Vi 插入模式： `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="0ef1e-192">Vi 命令模式： `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="0ef1e-193">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="0ef1e-193">DeleteCharOrExit</span></span>

<span data-ttu-id="0ef1e-194">删除光标下的字符; 如果行为空，则退出该过程。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="0ef1e-195">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="0ef1e-196">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-196">DeleteEndOfWord</span></span>

<span data-ttu-id="0ef1e-197">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="0ef1e-198">Vi 命令模式： `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="0ef1e-199">Deleteline.invoke</span><span class="sxs-lookup"><span data-stu-id="0ef1e-199">DeleteLine</span></span>

<span data-ttu-id="0ef1e-200">删除当前行，启用 "撤消"。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="0ef1e-201">Vi 命令模式： `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="0ef1e-202">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="0ef1e-203">删除从光标到行的第一个非空白字符的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="0ef1e-204">Vi 命令模式： `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="0ef1e-205">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="0ef1e-205">DeleteToEnd</span></span>

<span data-ttu-id="0ef1e-206">删除到行的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="0ef1e-207">Vi 命令模式： `<D>` ， `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="0ef1e-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-208">DeleteWord</span></span>

<span data-ttu-id="0ef1e-209">删除下一个词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-209">Delete the next word.</span></span>

- <span data-ttu-id="0ef1e-210">Vi 命令模式： `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="0ef1e-211">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-211">ForwardDeleteLine</span></span>

<span data-ttu-id="0ef1e-212">与 ForwardKillLine 一样，从点到行尾删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-213">Cmd：`<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="0ef1e-214">Vi 插入模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="0ef1e-215">Vi 命令模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="0ef1e-216">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="0ef1e-216">InsertLineAbove</span></span>

<span data-ttu-id="0ef1e-217">在当前行的上方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="0ef1e-218">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="0ef1e-219">Cmd：`<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="0ef1e-220">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="0ef1e-220">InsertLineBelow</span></span>

<span data-ttu-id="0ef1e-221">在当前行下方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="0ef1e-222">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="0ef1e-223">Cmd：`<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="0ef1e-224">InvertCase</span><span class="sxs-lookup"><span data-stu-id="0ef1e-224">InvertCase</span></span>

<span data-ttu-id="0ef1e-225">反转当前字符的大小写，并移到下一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="0ef1e-226">Vi 命令模式： `<~>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="0ef1e-227">KillLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-227">KillLine</span></span>

<span data-ttu-id="0ef1e-228">清除从光标到输入末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="0ef1e-229">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-230">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="0ef1e-231">KillRegion</span><span class="sxs-lookup"><span data-stu-id="0ef1e-231">KillRegion</span></span>

<span data-ttu-id="0ef1e-232">终止光标和标记之间的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="0ef1e-233">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="0ef1e-234">KillWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-234">KillWord</span></span>

<span data-ttu-id="0ef1e-235">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="0ef1e-236">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="0ef1e-237">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-238">Cmd：`<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="0ef1e-239">Emacs： `<Alt+d>` ， `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="0ef1e-240">Vi 插入模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="0ef1e-241">Vi 命令模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="0ef1e-242">粘贴</span><span class="sxs-lookup"><span data-stu-id="0ef1e-242">Paste</span></span>

<span data-ttu-id="0ef1e-243">粘贴系统剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="0ef1e-244">Cmd： `<Ctrl+v>` ， `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="0ef1e-245">Vi 插入模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="0ef1e-246">Vi 命令模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ef1e-247">使用 **Paste** 函数时，剪贴板缓冲区的全部内容将粘贴到 PSReadLine 的输入缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="0ef1e-248">然后，将输入缓冲区传递到 PowerShell 分析器。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="0ef1e-249">使用控制台应用程序的 **右键单击** 粘贴方法粘贴的输入会一次复制到输入缓冲区中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="0ef1e-250">复制换行符时，输入缓冲区会传递到分析器。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="0ef1e-251">因此，每次对输入进行一次分析。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="0ef1e-252">Paste 方法之间的区别导致了不同的执行行为。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="0ef1e-253">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="0ef1e-253">PasteAfter</span></span>

<span data-ttu-id="0ef1e-254">在光标后面粘贴剪贴板，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="0ef1e-255">Vi 命令模式： `<p>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="0ef1e-256">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="0ef1e-256">PasteBefore</span></span>

<span data-ttu-id="0ef1e-257">将剪贴板粘贴到光标之前，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="0ef1e-258">Vi 命令模式： `<P>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="0ef1e-259">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="0ef1e-259">PrependAndAccept</span></span>

<span data-ttu-id="0ef1e-260">预置 "#" 并接受该行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="0ef1e-261">Vi 命令模式： `<#>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="0ef1e-262">重做</span><span class="sxs-lookup"><span data-stu-id="0ef1e-262">Redo</span></span>

<span data-ttu-id="0ef1e-263">撤消撤消。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-263">Undo an undo.</span></span>

- <span data-ttu-id="0ef1e-264">Cmd：`<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="0ef1e-265">Vi 插入模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="0ef1e-266">Vi 命令模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="0ef1e-267">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="0ef1e-267">RepeatLastCommand</span></span>

<span data-ttu-id="0ef1e-268">重复最后一次文本修改。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="0ef1e-269">Vi 命令模式： `<.>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="0ef1e-270">RevertLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-270">RevertLine</span></span>

<span data-ttu-id="0ef1e-271">将所有输入还原为当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="0ef1e-272">Cmd：`<Escape>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="0ef1e-273">Emacs： `<Alt+r>` ， `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="0ef1e-274">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="0ef1e-275">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="0ef1e-276">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="0ef1e-277">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="0ef1e-278">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="0ef1e-279">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-279">ShellKillWord</span></span>

<span data-ttu-id="0ef1e-280">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="0ef1e-281">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="0ef1e-282">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="0ef1e-283">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="0ef1e-284">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="0ef1e-284">SwapCharacters</span></span>

<span data-ttu-id="0ef1e-285">交换当前字符和该字符之前的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="0ef1e-286">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="0ef1e-287">Vi 插入模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="0ef1e-288">Vi 命令模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="0ef1e-289">撤消</span><span class="sxs-lookup"><span data-stu-id="0ef1e-289">Undo</span></span>

<span data-ttu-id="0ef1e-290">撤消上一个编辑。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-290">Undo a previous edit.</span></span>

- <span data-ttu-id="0ef1e-291">Cmd：`<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="0ef1e-292">Emacs： `<Ctrl+_>` ， `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="0ef1e-293">Vi 插入模式： `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="0ef1e-294">Vi 命令模式： `<Ctrl+z>` ， `<u>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="0ef1e-295">UndoAll</span><span class="sxs-lookup"><span data-stu-id="0ef1e-295">UndoAll</span></span>

<span data-ttu-id="0ef1e-296">撤消对行的所有以前的编辑。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="0ef1e-297">Vi 命令模式： `<U>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="0ef1e-298">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="0ef1e-298">UnixWordRubout</span></span>

<span data-ttu-id="0ef1e-299">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="0ef1e-300">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="0ef1e-301">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-302">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="0ef1e-303">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="0ef1e-304">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-304">Attempt to execute the current input.</span></span> <span data-ttu-id="0ef1e-305">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="0ef1e-306">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="0ef1e-307">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-307">ViAcceptLine</span></span>

<span data-ttu-id="0ef1e-308">接受行并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="0ef1e-309">Vi 命令模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="0ef1e-310">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="0ef1e-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="0ef1e-311">与 Emacs 模式下的 DeleteCharOrExit 类似，但接受行而不是删除字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="0ef1e-312">Vi 插入模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="0ef1e-313">Vi 命令模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="0ef1e-314">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-314">ViAppendLine</span></span>

<span data-ttu-id="0ef1e-315">新行插入到当前行的下方。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="0ef1e-316">Vi 命令模式： `<o>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="0ef1e-317">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="0ef1e-318">删除上一个词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="0ef1e-319">Vi 命令模式： `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="0ef1e-320">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-320">ViBackwardGlob</span></span>

<span data-ttu-id="0ef1e-321">将光标移回上一个词的开头，仅使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="0ef1e-322">Vi 命令模式： `<B>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="0ef1e-323">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="0ef1e-323">ViDeleteBrace</span></span>

<span data-ttu-id="0ef1e-324">查找匹配的大括号、圆括号或方括号，并删除其中的所有内容，包括大括号。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="0ef1e-325">Vi 命令模式： `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="0ef1e-326">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="0ef1e-327">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="0ef1e-328">Vi 命令模式： `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="0ef1e-329">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-329">ViDeleteGlob</span></span>

<span data-ttu-id="0ef1e-330">删除下一个 glob (空格分隔的单词) 。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="0ef1e-331">Vi 命令模式： `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="0ef1e-332">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="0ef1e-333">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-333">Deletes until given character.</span></span>

- <span data-ttu-id="0ef1e-334">Vi 命令模式： `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="0ef1e-335">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="0ef1e-336">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-336">Deletes until given character.</span></span>

- <span data-ttu-id="0ef1e-337">Vi 命令模式： `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="0ef1e-338">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-338">ViDeleteToChar</span></span>

<span data-ttu-id="0ef1e-339">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-339">Deletes until given character.</span></span>

- <span data-ttu-id="0ef1e-340">Vi 命令模式： `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="0ef1e-341">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="0ef1e-342">向后删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="0ef1e-343">Vi 命令模式： `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="0ef1e-344">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="0ef1e-344">ViInsertAtBegining</span></span>

<span data-ttu-id="0ef1e-345">切换到插入模式，并将光标置于行首。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="0ef1e-346">Vi 命令模式： `<I>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="0ef1e-347">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="0ef1e-347">ViInsertAtEnd</span></span>

<span data-ttu-id="0ef1e-348">切换到插入模式，并将光标置于行的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="0ef1e-349">Vi 命令模式： `<A>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="0ef1e-350">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-350">ViInsertLine</span></span>

<span data-ttu-id="0ef1e-351">在当前行的上方插入新行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="0ef1e-352">Vi 命令模式： `<O>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="0ef1e-353">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="0ef1e-353">ViInsertWithAppend</span></span>

<span data-ttu-id="0ef1e-354">从当前行位置追加。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-354">Append from the current line position.</span></span>

- <span data-ttu-id="0ef1e-355">Vi 命令模式： `<a>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="0ef1e-356">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="0ef1e-356">ViInsertWithDelete</span></span>

<span data-ttu-id="0ef1e-357">删除当前字符并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="0ef1e-358">Vi 命令模式： `<s>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="0ef1e-359">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="0ef1e-359">ViJoinLines</span></span>

<span data-ttu-id="0ef1e-360">联接当前行和下一行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="0ef1e-361">Vi 命令模式： `<J>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="0ef1e-362">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-362">ViReplaceLine</span></span>

<span data-ttu-id="0ef1e-363">擦除整个命令行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-363">Erase the entire command line.</span></span>

- <span data-ttu-id="0ef1e-364">Vi 命令模式： `<S>` ， `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="0ef1e-365">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="0ef1e-366">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-366">Replaces until given character.</span></span>

- <span data-ttu-id="0ef1e-367">Vi 命令模式： `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="0ef1e-368">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="0ef1e-369">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-369">Replaces until given character.</span></span>

- <span data-ttu-id="0ef1e-370">Vi 命令模式： `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="0ef1e-371">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-371">ViReplaceToChar</span></span>

<span data-ttu-id="0ef1e-372">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-372">Deletes until given character.</span></span>

- <span data-ttu-id="0ef1e-373">Vi 命令模式： `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="0ef1e-374">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="0ef1e-375">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-375">Replaces until given character.</span></span>

- <span data-ttu-id="0ef1e-376">Vi 命令模式： `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="0ef1e-377">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="0ef1e-378">从缓冲区的开头到游标的 Yank。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="0ef1e-379">Vi 命令模式： `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="0ef1e-380">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="0ef1e-381">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="0ef1e-382">Vi 命令模式： `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="0ef1e-383">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-383">ViYankEndOfWord</span></span>

<span data-ttu-id="0ef1e-384">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="0ef1e-385">Vi 命令模式： `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="0ef1e-386">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="0ef1e-386">ViYankLeft</span></span>

<span data-ttu-id="0ef1e-387">Yank 字符 (s) 光标左侧。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="0ef1e-388">Vi 命令模式： `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="0ef1e-389">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-389">ViYankLine</span></span>

<span data-ttu-id="0ef1e-390">Yank 整个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="0ef1e-391">Vi 命令模式： `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="0ef1e-392">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-392">ViYankNextGlob</span></span>

<span data-ttu-id="0ef1e-393">Yank 从 cursor 到下一个单词 () 的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="0ef1e-394">Vi 命令模式： `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="0ef1e-395">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-395">ViYankNextWord</span></span>

<span data-ttu-id="0ef1e-396">Yank 在游标后) 的单词 (。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="0ef1e-397">Vi 命令模式： `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="0ef1e-398">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="0ef1e-398">ViYankPercent</span></span>

<span data-ttu-id="0ef1e-399">Yank 匹配的大括号。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="0ef1e-400">Vi 命令模式： `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="0ef1e-401">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="0ef1e-402">从单词 (开始，) 到游标。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="0ef1e-403">Vi 命令模式： `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="0ef1e-404">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-404">ViYankPreviousWord</span></span>

<span data-ttu-id="0ef1e-405">Yank 在游标前)  (s。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="0ef1e-406">Vi 命令模式： `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="0ef1e-407">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="0ef1e-407">ViYankRight</span></span>

<span data-ttu-id="0ef1e-408">Yank 字符 (s) 光标右侧和右侧。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="0ef1e-409">Vi 命令模式： `<y,l>` ， `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="0ef1e-410">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="0ef1e-411">Yank 从游标到缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="0ef1e-412">Vi 命令模式： `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="0ef1e-413">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-413">ViYankToFirstChar</span></span>

<span data-ttu-id="0ef1e-414">从第一个非空白字符 Yank 到游标。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="0ef1e-415">Vi 命令模式： `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="0ef1e-416">Yank</span><span class="sxs-lookup"><span data-stu-id="0ef1e-416">Yank</span></span>

<span data-ttu-id="0ef1e-417">将最近终止的文本添加到输入中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="0ef1e-418">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="0ef1e-419">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="0ef1e-419">YankLastArg</span></span>

<span data-ttu-id="0ef1e-420">Yank 上一个历史记录行中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="0ef1e-421">如果使用参数，则第一次调用时，其行为就像 YankNthArg。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="0ef1e-422">如果多次调用，则会循环访问历史记录，而 arg 会将方向设置 (负反转方向。 ) </span><span class="sxs-lookup"><span data-stu-id="0ef1e-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="0ef1e-423">Cmd：`<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="0ef1e-424">Emacs： `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="0ef1e-425">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="0ef1e-425">YankNthArg</span></span>

<span data-ttu-id="0ef1e-426">Yank 从上一历史记录行) 命令后 (第一个参数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="0ef1e-427">对于参数，yank 从 0) 开始 (第 n 个参数，如果参数为负数，则从最后一个参数开始。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="0ef1e-428">Emacs： `<Ctrl+Alt+y>` ， `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="0ef1e-429">YankPop</span><span class="sxs-lookup"><span data-stu-id="0ef1e-429">YankPop</span></span>

<span data-ttu-id="0ef1e-430">如果上一操作是 Yank 或 YankPop，则将以前的拔掉文本替换为下一个终止的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="0ef1e-431">Emacs： `<Alt+y>` ， `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="0ef1e-432">游标移动函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="0ef1e-433">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-433">BackwardChar</span></span>

<span data-ttu-id="0ef1e-434">将光标向左移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="0ef1e-435">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="0ef1e-436">Cmd：`<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="0ef1e-437">Emacs： `<LeftArrow>` ， `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="0ef1e-438">Vi 插入模式： `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="0ef1e-439">Vi 命令模式： `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="0ef1e-440">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-440">BackwardWord</span></span>

<span data-ttu-id="0ef1e-441">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="0ef1e-442">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ef1e-443">Cmd：`<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="0ef1e-444">Emacs： `<Alt+b>` ， `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="0ef1e-445">Vi 插入模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="0ef1e-446">Vi 命令模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="0ef1e-447">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-447">BeginningOfLine</span></span>

<span data-ttu-id="0ef1e-448">如果输入具有多个行，则移动到当前行的开头，或者，如果已位于行首，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="0ef1e-449">如果输入具有单行，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="0ef1e-450">Cmd：`<Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="0ef1e-451">Emacs： `<Home>` ， `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="0ef1e-452">Vi 插入模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="0ef1e-453">Vi 命令模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="0ef1e-454">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-454">EndOfLine</span></span>

<span data-ttu-id="0ef1e-455">如果输入包含多行，则移动到当前行的末尾，或者，如果已位于行尾，则转到输入的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="0ef1e-456">如果输入具有单行，则移动到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="0ef1e-457">Cmd：`<End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="0ef1e-458">Emacs： `<End>` ， `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="0ef1e-459">Vi 插入模式： `<End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="0ef1e-460">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-460">ForwardChar</span></span>

<span data-ttu-id="0ef1e-461">将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="0ef1e-462">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="0ef1e-463">Cmd：`<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="0ef1e-464">Emacs： `<RightArrow>` ， `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="0ef1e-465">Vi 插入模式： `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="0ef1e-466">Vi 命令模式： `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="0ef1e-467">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-467">ForwardWord</span></span>

<span data-ttu-id="0ef1e-468">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="0ef1e-469">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ef1e-470">Emacs： `<Alt+f>` ， `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="0ef1e-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="0ef1e-471">GotoBrace</span></span>

<span data-ttu-id="0ef1e-472">中转到匹配的大括号、圆括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="0ef1e-473">Cmd：`<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="0ef1e-474">Vi 插入模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="0ef1e-475">Vi 命令模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="0ef1e-476">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="0ef1e-476">GotoColumn</span></span>

<span data-ttu-id="0ef1e-477">转到 arg 指示的列。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="0ef1e-478">Vi 命令模式： `<|>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="0ef1e-479">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="0ef1e-480">将光标移动到行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="0ef1e-481">Vi 命令模式： `<^>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="0ef1e-482">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-482">MoveToEndOfLine</span></span>

<span data-ttu-id="0ef1e-483">将光标移到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="0ef1e-484">Vi 命令模式： `<End>` ， `<$>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="0ef1e-485">NextLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-485">NextLine</span></span>

<span data-ttu-id="0ef1e-486">将光标移到下一行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="0ef1e-487">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="0ef1e-488">NextWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-488">NextWord</span></span>

<span data-ttu-id="0ef1e-489">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="0ef1e-490">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ef1e-491">Cmd：`<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="0ef1e-492">Vi 插入模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="0ef1e-493">Vi 命令模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="0ef1e-494">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="0ef1e-494">NextWordEnd</span></span>

<span data-ttu-id="0ef1e-495">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="0ef1e-496">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ef1e-497">Vi 命令模式： `<e>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="0ef1e-498">PreviousLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-498">PreviousLine</span></span>

<span data-ttu-id="0ef1e-499">将光标移到上一行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="0ef1e-500">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="0ef1e-501">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-501">ShellBackwardWord</span></span>

<span data-ttu-id="0ef1e-502">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="0ef1e-503">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="0ef1e-504">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="0ef1e-505">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-505">ShellForwardWord</span></span>

<span data-ttu-id="0ef1e-506">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="0ef1e-507">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="0ef1e-508">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="0ef1e-509">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-509">ShellNextWord</span></span>

<span data-ttu-id="0ef1e-510">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="0ef1e-511">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="0ef1e-512">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="0ef1e-513">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-513">ViBackwardWord</span></span>

<span data-ttu-id="0ef1e-514">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="0ef1e-515">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ef1e-516">Vi 命令模式： `<b>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="0ef1e-517">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-517">ViEndOfGlob</span></span>

<span data-ttu-id="0ef1e-518">将光标移到单词的末尾，只使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="0ef1e-519">Vi 命令模式： `<E>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="0ef1e-520">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="0ef1e-521">移到上一个词的末尾，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="0ef1e-522">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="0ef1e-523">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="0ef1e-523">ViGotoBrace</span></span>

<span data-ttu-id="0ef1e-524">类似于 GotoBrace，但基于字符，而不是基于标记。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="0ef1e-525">Vi 命令模式： `<%>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="0ef1e-526">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="0ef1e-526">ViNextGlob</span></span>

<span data-ttu-id="0ef1e-527">移到下一个单词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="0ef1e-528">Vi 命令模式： `<W>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="0ef1e-529">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-529">ViNextWord</span></span>

<span data-ttu-id="0ef1e-530">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="0ef1e-531">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ef1e-532">Vi 命令模式： `<w>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="0ef1e-533">历史记录函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="0ef1e-534">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-534">BeginningOfHistory</span></span>

<span data-ttu-id="0ef1e-535">移到历史记录中的第一项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="0ef1e-536">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="0ef1e-537">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-537">ClearHistory</span></span>

<span data-ttu-id="0ef1e-538">清除 PSReadLine 中的历史记录。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="0ef1e-539">这不会影响 PowerShell 历史记录。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="0ef1e-540">Cmd：`<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="0ef1e-541">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-541">EndOfHistory</span></span>

<span data-ttu-id="0ef1e-542">移到历史记录中 (当前输入) 的最后一项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="0ef1e-543">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="0ef1e-544">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-544">ForwardSearchHistory</span></span>

<span data-ttu-id="0ef1e-545">通过历史记录执行增量向前搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="0ef1e-546">Cmd：`<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="0ef1e-547">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="0ef1e-548">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-548">HistorySearchBackward</span></span>

<span data-ttu-id="0ef1e-549">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项，该匹配项与开始与输入和光标之间的字符匹配。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="0ef1e-550">Cmd：`<F8>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="0ef1e-551">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-551">HistorySearchForward</span></span>

<span data-ttu-id="0ef1e-552">将当前输入替换为 PSReadLine 历史记录中与 start 与 input 和 cursor 之间的字符相匹配的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="0ef1e-553">Cmd：`<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="0ef1e-554">NextHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-554">NextHistory</span></span>

<span data-ttu-id="0ef1e-555">将当前输入替换为 PSReadLine 历史记录中的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="0ef1e-556">Cmd：`<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="0ef1e-557">Emacs： `<DownArrow>` ， `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="0ef1e-558">Vi 插入模式： `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="0ef1e-559">Vi 命令模式： `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="0ef1e-560">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-560">PreviousHistory</span></span>

<span data-ttu-id="0ef1e-561">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="0ef1e-562">Cmd：`<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="0ef1e-563">Emacs： `<UpArrow>` ， `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="0ef1e-564">Vi 插入模式： `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="0ef1e-565">Vi 命令模式： `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="0ef1e-566">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="0ef1e-566">ReverseSearchHistory</span></span>

<span data-ttu-id="0ef1e-567">通过历史记录执行增量向后搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="0ef1e-568">Cmd：`<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="0ef1e-569">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="0ef1e-570">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="0ef1e-571">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="0ef1e-572">Vi 插入模式： `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="0ef1e-573">Vi 命令模式： `</>` ， `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="0ef1e-574">完成函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="0ef1e-575">完成</span><span class="sxs-lookup"><span data-stu-id="0ef1e-575">Complete</span></span>

<span data-ttu-id="0ef1e-576">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="0ef1e-577">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="0ef1e-578">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="0ef1e-579">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="0ef1e-580">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="0ef1e-580">MenuComplete</span></span>

<span data-ttu-id="0ef1e-581">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="0ef1e-582">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="0ef1e-583">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="0ef1e-584">Cmd：`<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="0ef1e-585">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="0ef1e-586">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="0ef1e-586">PossibleCompletions</span></span>

<span data-ttu-id="0ef1e-587">显示可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="0ef1e-588">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="0ef1e-589">Vi 插入模式： `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="0ef1e-590">Vi 命令模式： `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="0ef1e-591">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="0ef1e-591">TabCompleteNext</span></span>

<span data-ttu-id="0ef1e-592">尝试使用下一个可用完成来完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="0ef1e-593">Cmd：`<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="0ef1e-594">Vi 命令模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="0ef1e-595">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="0ef1e-595">TabCompletePrevious</span></span>

<span data-ttu-id="0ef1e-596">尝试使用以前的可用完成功能完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="0ef1e-597">Cmd：`<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="0ef1e-598">Vi 命令模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="0ef1e-599">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="0ef1e-599">ViTabCompleteNext</span></span>

<span data-ttu-id="0ef1e-600">结束当前编辑组（如果需要），并调用 TabCompleteNext。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="0ef1e-601">Vi 插入模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="0ef1e-602">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="0ef1e-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="0ef1e-603">结束当前编辑组（如果需要），并调用 TabCompletePrevious。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="0ef1e-604">Vi 插入模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="0ef1e-605">杂项函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="0ef1e-606">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="0ef1e-606">CaptureScreen</span></span>

<span data-ttu-id="0ef1e-607">启动交互屏幕捕获-向上/向下箭头选择 "线条"，将选定文本作为文本和 html 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="0ef1e-608">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="0ef1e-609">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="0ef1e-609">ClearScreen</span></span>

<span data-ttu-id="0ef1e-610">清除屏幕并在屏幕的顶部绘制当前线条。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="0ef1e-611">Cmd：`<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="0ef1e-612">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="0ef1e-613">Vi 插入模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="0ef1e-614">Vi 命令模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="0ef1e-615">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="0ef1e-615">DigitArgument</span></span>

<span data-ttu-id="0ef1e-616">启动新的数字参数，使其传递到其他函数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="0ef1e-617">Cmd： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="0ef1e-618">Emacs： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="0ef1e-619">Vi 命令模式： `<0>` 、 `<1>` 、 `<2>` 、 `<3>` 、 `<4>` 、 `<5>` 、 `<6>` 、 `<7>` 、 `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="0ef1e-620">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="0ef1e-620">InvokePrompt</span></span>

<span data-ttu-id="0ef1e-621">清除当前提示符并调用 prompt 函数以重新显示提示符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="0ef1e-622">适用于更改状态的自定义密钥处理程序，例如更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="0ef1e-623">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="0ef1e-624">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="0ef1e-624">ScrollDisplayDown</span></span>

<span data-ttu-id="0ef1e-625">将显示向下滚动一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="0ef1e-626">Cmd：`<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="0ef1e-627">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="0ef1e-628">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="0ef1e-629">将显示向下滚动一行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="0ef1e-630">Cmd：`<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="0ef1e-631">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="0ef1e-632">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="0ef1e-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="0ef1e-633">将显示滚动到光标处。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="0ef1e-634">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="0ef1e-635">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="0ef1e-635">ScrollDisplayTop</span></span>

<span data-ttu-id="0ef1e-636">向顶部滚动显示。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="0ef1e-637">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="0ef1e-638">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="0ef1e-638">ScrollDisplayUp</span></span>

<span data-ttu-id="0ef1e-639">将显示向上滚动一屏。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="0ef1e-640">Cmd：`<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="0ef1e-641">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="0ef1e-642">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="0ef1e-643">将显示向上滚动一行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="0ef1e-644">Cmd：`<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="0ef1e-645">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="0ef1e-646">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="0ef1e-646">SelfInsert</span></span>

<span data-ttu-id="0ef1e-647">插入密钥。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-647">Insert the key.</span></span>

- <span data-ttu-id="0ef1e-648">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="0ef1e-649">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="0ef1e-649">ShowKeyBindings</span></span>

<span data-ttu-id="0ef1e-650">显示所有绑定键。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-650">Show all bound keys.</span></span>

- <span data-ttu-id="0ef1e-651">Cmd：`<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="0ef1e-652">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="0ef1e-653">Vi 插入模式： `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="0ef1e-654">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="0ef1e-654">ViCommandMode</span></span>

<span data-ttu-id="0ef1e-655">将当前运行模式从 Vi-Insert 切换到 Vi-Command。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="0ef1e-656">Vi 插入模式： `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="0ef1e-657">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="0ef1e-658">启动新的数字参数，将其传递给其他函数，同时使用 vi 的鼠标左键之一。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="0ef1e-659">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="0ef1e-660">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="0ef1e-660">ViEditVisually</span></span>

<span data-ttu-id="0ef1e-661">在 $env： EDITOR 或 $env：视觉对象指定的文本编辑器中编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="0ef1e-662">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="0ef1e-663">Vi 命令模式： `<v>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="0ef1e-664">ViExit</span><span class="sxs-lookup"><span data-stu-id="0ef1e-664">ViExit</span></span>

<span data-ttu-id="0ef1e-665">退出 shell。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-665">Exits the shell.</span></span>

- <span data-ttu-id="0ef1e-666">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="0ef1e-667">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="0ef1e-667">ViInsertMode</span></span>

<span data-ttu-id="0ef1e-668">切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="0ef1e-669">Vi 命令模式： `<i>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="0ef1e-670">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="0ef1e-670">WhatIsKey</span></span>

<span data-ttu-id="0ef1e-671">阅读密钥，并告诉我密钥的绑定内容。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="0ef1e-672">Cmd：`<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="0ef1e-673">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="0ef1e-674">选择函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="0ef1e-675">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="0ef1e-675">ExchangePointAndMark</span></span>

<span data-ttu-id="0ef1e-676">将光标置于标记的位置，并将标记移到光标所在的位置。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="0ef1e-677">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="0ef1e-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="0ef1e-678">SelectAll</span></span>

<span data-ttu-id="0ef1e-679">选择整行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-679">Select the entire line.</span></span>

- <span data-ttu-id="0ef1e-680">Cmd：`<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="0ef1e-681">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-681">SelectBackwardChar</span></span>

<span data-ttu-id="0ef1e-682">调整当前选定内容以包括前一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="0ef1e-683">Cmd：`<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="0ef1e-684">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="0ef1e-685">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-685">SelectBackwardsLine</span></span>

<span data-ttu-id="0ef1e-686">调整当前所选内容，使其包括从光标到行的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="0ef1e-687">Cmd：`<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="0ef1e-688">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="0ef1e-689">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-689">SelectBackwardWord</span></span>

<span data-ttu-id="0ef1e-690">调整当前所选内容以包含上一个词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="0ef1e-691">Cmd：`<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="0ef1e-692">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="0ef1e-693">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-693">SelectForwardChar</span></span>

<span data-ttu-id="0ef1e-694">调整当前所选内容以包含下一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="0ef1e-695">Cmd：`<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="0ef1e-696">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="0ef1e-697">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-697">SelectForwardWord</span></span>

<span data-ttu-id="0ef1e-698">使用 ForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="0ef1e-699">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="0ef1e-700">SelectLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-700">SelectLine</span></span>

<span data-ttu-id="0ef1e-701">调整当前所选内容，使其包括从光标到行尾的内容。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="0ef1e-702">Cmd：`<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="0ef1e-703">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="0ef1e-704">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-704">SelectNextWord</span></span>

<span data-ttu-id="0ef1e-705">调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="0ef1e-706">Cmd：`<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="0ef1e-707">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="0ef1e-708">使用 ShellBackwardWord 调整当前所选内容，使其包含前一词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="0ef1e-709">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="0ef1e-710">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-710">SelectShellForwardWord</span></span>

<span data-ttu-id="0ef1e-711">使用 ShellForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="0ef1e-712">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="0ef1e-713">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="0ef1e-713">SelectShellNextWord</span></span>

<span data-ttu-id="0ef1e-714">使用 ShellNextWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="0ef1e-715">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="0ef1e-716">SetMark</span><span class="sxs-lookup"><span data-stu-id="0ef1e-716">SetMark</span></span>

<span data-ttu-id="0ef1e-717">标记光标的当前位置，以供后续编辑命令使用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="0ef1e-718">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="0ef1e-719">搜索函数</span><span class="sxs-lookup"><span data-stu-id="0ef1e-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="0ef1e-720">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="0ef1e-720">CharacterSearch</span></span>

<span data-ttu-id="0ef1e-721">读取字符并向前搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="0ef1e-722">如果指定了参数，则向前搜索 (或向后) 对于第 n 个匹配项为负。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="0ef1e-723">Cmd：`<F3>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="0ef1e-724">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="0ef1e-725">Vi 插入模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="0ef1e-726">Vi 命令模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="0ef1e-727">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-727">CharacterSearchBackward</span></span>

<span data-ttu-id="0ef1e-728">读取字符并向后搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="0ef1e-729">如果指定了参数，则在第 n 个匹配项) 反向搜索时 (或转发。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="0ef1e-730">Cmd：`<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="0ef1e-731">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="0ef1e-732">Vi 插入模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="0ef1e-733">Vi 命令模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="0ef1e-734">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="0ef1e-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="0ef1e-735">重复上次记录的字符搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="0ef1e-736">Vi 命令模式： `<;>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="0ef1e-737">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="0ef1e-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="0ef1e-738">重复上次记录的字符搜索，但采用相反方向。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="0ef1e-739">Vi 命令模式： `<,>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="0ef1e-740">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="0ef1e-740">RepeatSearch</span></span>

<span data-ttu-id="0ef1e-741">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="0ef1e-742">Vi 命令模式： `<n>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="0ef1e-743">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-743">RepeatSearchBackward</span></span>

<span data-ttu-id="0ef1e-744">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="0ef1e-745">Vi 命令模式： `<N>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="0ef1e-746">SearchChar</span><span class="sxs-lookup"><span data-stu-id="0ef1e-746">SearchChar</span></span>

<span data-ttu-id="0ef1e-747">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="0ef1e-748">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="0ef1e-749">Vi 命令模式： `<f>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="0ef1e-750">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-750">SearchCharBackward</span></span>

<span data-ttu-id="0ef1e-751">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="0ef1e-752">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="0ef1e-753">Vi 命令模式： `<F>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="0ef1e-754">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="0ef1e-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="0ef1e-755">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="0ef1e-756">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="0ef1e-757">Vi 命令模式： `<T>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="0ef1e-758">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="0ef1e-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="0ef1e-759">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="0ef1e-760">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="0ef1e-761">Vi 命令模式： `<t>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="0ef1e-762">SearchForward</span><span class="sxs-lookup"><span data-stu-id="0ef1e-762">SearchForward</span></span>

<span data-ttu-id="0ef1e-763">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="0ef1e-764">Vi 插入模式： `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="0ef1e-765">Vi 命令模式： `<?>` ， `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ef1e-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="0ef1e-766">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="0ef1e-766">Custom Key Bindings</span></span>

<span data-ttu-id="0ef1e-767">PSReadLine 支持使用 cmdlet 的自定义键绑定 `Set-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="0ef1e-768">大多数自定义键绑定调用上述函数之一，例如</span><span class="sxs-lookup"><span data-stu-id="0ef1e-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="0ef1e-769">可以将 ScriptBlock 绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="0ef1e-770">ScriptBlock 可以执行任何所需的操作。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="0ef1e-771">一些有用的示例包括</span><span class="sxs-lookup"><span data-stu-id="0ef1e-771">Some useful examples include</span></span>

- <span data-ttu-id="0ef1e-772">编辑命令行</span><span class="sxs-lookup"><span data-stu-id="0ef1e-772">edit the command line</span></span>
- <span data-ttu-id="0ef1e-773">打开新窗口 (例如，帮助) </span><span class="sxs-lookup"><span data-stu-id="0ef1e-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="0ef1e-774">更改目录而不更改命令行</span><span class="sxs-lookup"><span data-stu-id="0ef1e-774">change directories without changing the command line</span></span>

<span data-ttu-id="0ef1e-775">ScriptBlock 接收两个参数：</span><span class="sxs-lookup"><span data-stu-id="0ef1e-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="0ef1e-776">`$key` -一个作为触发自定义绑定的密钥的 **[ConsoleKeyInfo]** 对象。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="0ef1e-777">如果将相同的 ScriptBlock 绑定到多个键，并且需要根据关键字执行不同的操作，则可以选中 $key。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="0ef1e-778">许多自定义绑定会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="0ef1e-779">`$arg` -任意参数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="0ef1e-780">大多数情况下，这将是用户从键绑定 DigitArgument 传递的整数参数。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="0ef1e-781">如果绑定不接受参数，则忽略此参数是合理的。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="0ef1e-782">我们来看一个示例，该示例将一个命令行添加到历史记录中，而不执行它。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="0ef1e-783">如果您认为您忘记了某些事情，但又不想重新输入您已经输入的命令行，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="0ef1e-784">你可以在 PSReadLine 模块文件夹中安装的文件中查看更多示例 `SamplePSReadLineProfile.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="0ef1e-785">大多数键绑定使用一些 helper 函数来编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="0ef1e-786">下一节将介绍这些 Api。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="0ef1e-787">自定义键绑定支持 Api</span><span class="sxs-lookup"><span data-stu-id="0ef1e-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="0ef1e-788">以下函数是 PSConsoleReadLine 中的公共函数，但不能直接绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="0ef1e-789">大多数在自定义键绑定中很有用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="0ef1e-790">向历史记录中添加一个命令行而不执行它。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="0ef1e-791">清除终止环。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-791">Clear the kill-ring.</span></span>  <span data-ttu-id="0ef1e-792">这主要用于测试。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="0ef1e-793">从开始删除长度字符。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-793">Delete length characters from start.</span></span>  <span data-ttu-id="0ef1e-794">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="0ef1e-795">根据用户首选项执行 Ding 操作。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="0ef1e-796">这两个函数检索有关输入缓冲区的当前状态的有用信息。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="0ef1e-797">第一种方案更常见用于简单情况。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="0ef1e-798">如果绑定使用 Ast 执行更高级的操作，则会使用第二个。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="0ef1e-799">此函数由 Get-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="0ef1e-800">此函数由 Get-PSReadLineOption 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="0ef1e-801">如果未在命令行上进行选择，则将在 "开始" 和 "长度" 中返回-1。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="0ef1e-802">如果命令行上有选择，则返回选定内容的开始和长度。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="0ef1e-803">在光标处插入字符或字符串。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="0ef1e-804">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="0ef1e-805">这是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="0ef1e-806">它不支持递归，因此在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="0ef1e-807">此函数由 Remove-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="0ef1e-808">替换部分输入。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-808">Replace some of the input.</span></span> <span data-ttu-id="0ef1e-809">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-809">This operation supports undo/redo.</span></span> <span data-ttu-id="0ef1e-810">这优先于删除后再执行 Insert，因为它被视为单个操作来撤消。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="0ef1e-811">将光标移动到给定偏移量。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="0ef1e-812">不跟踪游标移动以便撤消。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="0ef1e-813">此函数是 cmdlet PSReadLineOption 使用的帮助器方法，但可能对要临时更改设置的自定义密钥绑定很有用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="0ef1e-814">此帮助器方法用于接受 DigitArgument 的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="0ef1e-815">典型调用如下所示</span><span class="sxs-lookup"><span data-stu-id="0ef1e-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="0ef1e-816">注意</span><span class="sxs-lookup"><span data-stu-id="0ef1e-816">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="0ef1e-817">POWERSHELL 兼容性</span><span class="sxs-lookup"><span data-stu-id="0ef1e-817">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="0ef1e-818">PSReadLine 要求安装 PowerShell 3.0 或更高版本，以及控制台主机。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-818">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="0ef1e-819">它在 PowerShell ISE 中不起作用。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-819">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="0ef1e-820">它在 Visual Studio Code 的控制台中工作。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-820">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="0ef1e-821">命令历史记录</span><span class="sxs-lookup"><span data-stu-id="0ef1e-821">COMMAND HISTORY</span></span>

<span data-ttu-id="0ef1e-822">PSReadLine 维护一个历史记录文件，其中包含在命令行中输入的所有命令和数据。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-822">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="0ef1e-823">这可能包含敏感数据（包括密码）。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-823">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="0ef1e-824">例如，如果使用 cmdlet，则 `ConvertTo-SecureString` 密码将作为纯文本记录到历史记录文件中。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-824">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="0ef1e-825">历史记录文件是一个名为的文件 `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-825">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="0ef1e-826">在 Windows 系统上，历史记录文件存储在中 `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-826">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="0ef1e-827">在非 Windows 系统上，历史记录文件存储在 `$env:XDG_DATA_HOME/powershell/PSReadLine` 或上 `$env:HOME/.local/share/powershell/PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-827">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="0ef1e-828">参与 PSReadLine 的反馈 &</span><span class="sxs-lookup"><span data-stu-id="0ef1e-828">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="0ef1e-829">GitHub 上的 PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ef1e-829">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="0ef1e-830">可在 GitHub 页上随意提交拉取请求或提交反馈。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-830">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ef1e-831">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ef1e-831">SEE ALSO</span></span>

<span data-ttu-id="0ef1e-832">PSReadLine 会受到 GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) 库的严重影响。</span><span class="sxs-lookup"><span data-stu-id="0ef1e-832">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
