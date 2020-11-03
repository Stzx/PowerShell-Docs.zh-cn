---
description: PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于 PSReadLine
ms.openlocfilehash: 1188b8dc0b4099a7c1dcc472e3b02c2d4fa908bc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199632"
---
# <a name="psreadline"></a><span data-ttu-id="d6634-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d6634-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="d6634-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d6634-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="d6634-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="d6634-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="d6634-107">PSReadLine 在 PowerShell 控制台中提供改进的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="d6634-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="d6634-108">详细说明</span><span class="sxs-lookup"><span data-stu-id="d6634-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="d6634-109">PSReadLine 2.0 为 PowerShell 控制台提供了强大的命令行编辑体验。</span><span class="sxs-lookup"><span data-stu-id="d6634-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="d6634-110">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="d6634-110">It provides:</span></span>

- <span data-ttu-id="d6634-111">命令行的语法着色</span><span class="sxs-lookup"><span data-stu-id="d6634-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="d6634-112">语法错误的直观指示</span><span class="sxs-lookup"><span data-stu-id="d6634-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="d6634-113"> (编辑和历史记录的更好的多行体验) </span><span class="sxs-lookup"><span data-stu-id="d6634-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="d6634-114">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="d6634-114">Customizable key bindings</span></span>
- <span data-ttu-id="d6634-115">Cmd 和 Emacs 模式</span><span class="sxs-lookup"><span data-stu-id="d6634-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="d6634-116">许多配置选项</span><span class="sxs-lookup"><span data-stu-id="d6634-116">Many configuration options</span></span>
- <span data-ttu-id="d6634-117">在 Cmd 模式下，Bash 样式完成 (可选，默认值为 Emacs 模式) </span><span class="sxs-lookup"><span data-stu-id="d6634-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="d6634-118">Emacs yank/kill 循环</span><span class="sxs-lookup"><span data-stu-id="d6634-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="d6634-119">基于 PowerShell 令牌的 "word" 移动和终止</span><span class="sxs-lookup"><span data-stu-id="d6634-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="d6634-120">类 **[PSConsoleReadLine]** 中提供了以下函数。</span><span class="sxs-lookup"><span data-stu-id="d6634-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

> [!NOTE]
> <span data-ttu-id="d6634-121">从 PowerShell 7.0 开始，如果检测到屏幕阅读器程序，PowerShell 会跳过在 Windows 上自动加载 PSReadLine。</span><span class="sxs-lookup"><span data-stu-id="d6634-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="d6634-122">目前，PSReadLine 不能与屏幕阅读器很好地配合使用。</span><span class="sxs-lookup"><span data-stu-id="d6634-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="d6634-123">Windows 上 PowerShell 7.0 的默认呈现和格式设置正常。</span><span class="sxs-lookup"><span data-stu-id="d6634-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="d6634-124">如有必要，可以手动加载模块。</span><span class="sxs-lookup"><span data-stu-id="d6634-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="d6634-125">基本编辑函数</span><span class="sxs-lookup"><span data-stu-id="d6634-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="d6634-126">中止</span><span class="sxs-lookup"><span data-stu-id="d6634-126">Abort</span></span>

<span data-ttu-id="d6634-127">中止当前操作，例如增量历史记录搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="d6634-128">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="d6634-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="d6634-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="d6634-129">AcceptAndGetNext</span></span>

<span data-ttu-id="d6634-130">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-130">Attempt to execute the current input.</span></span> <span data-ttu-id="d6634-131">如果可以 (如 AcceptLine) 执行，则在下一次调用 ReadLine 时，从历史记录中撤回下一项。</span><span class="sxs-lookup"><span data-stu-id="d6634-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="d6634-132">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="d6634-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="d6634-133">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="d6634-133">AcceptLine</span></span>

<span data-ttu-id="d6634-134">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-134">Attempt to execute the current input.</span></span> <span data-ttu-id="d6634-135">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="d6634-136">Cmd：`<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="d6634-137">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="d6634-138">Vi 插入模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="d6634-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="d6634-139">AddLine</span></span>

<span data-ttu-id="d6634-140">继续提示显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="d6634-141">这可用于将多行输入作为单个命令输入，即使单个行自动完成输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="d6634-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="d6634-142">Cmd：`<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d6634-143">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d6634-144">Vi 插入模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d6634-145">Vi 命令模式： `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="d6634-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="d6634-146">BackwardDeleteChar</span></span>

<span data-ttu-id="d6634-147">删除光标前面的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="d6634-148">Cmd： `<Backspace>` ， `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="d6634-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="d6634-149">Emacs： `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="d6634-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="d6634-150">Vi 插入模式： `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6634-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="d6634-151">Vi 命令模式： `<X>` ， `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="d6634-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="d6634-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="d6634-152">BackwardDeleteLine</span></span>

<span data-ttu-id="d6634-153">与 BackwardKillLine 一样，从点到行的开头删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="d6634-154">Cmd：`<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="d6634-155">Vi 插入模式： `<Ctrl+u>` ， `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="d6634-156">Vi 命令模式： `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="d6634-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="d6634-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="d6634-157">BackwardDeleteWord</span></span>

<span data-ttu-id="d6634-158">删除上一个词。</span><span class="sxs-lookup"><span data-stu-id="d6634-158">Deletes the previous word.</span></span>

- <span data-ttu-id="d6634-159">Vi 命令模式： `<Ctrl+w>` ， `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="d6634-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="d6634-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="d6634-160">BackwardKillLine</span></span>

<span data-ttu-id="d6634-161">清除输入从输入开始到光标。</span><span class="sxs-lookup"><span data-stu-id="d6634-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="d6634-162">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6634-163">Emacs： `<Ctrl+u>` ， `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6634-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="d6634-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="d6634-164">BackwardKillWord</span></span>

<span data-ttu-id="d6634-165">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d6634-166">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d6634-167">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6634-168">Cmd： `<Ctrl+Backspace>` ， `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="d6634-168">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="d6634-169">Emacs： `<Alt+Backspace>` ， `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6634-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="d6634-170">Vi 插入模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6634-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="d6634-171">Vi 命令模式： `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6634-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="d6634-172">CancelLine</span><span class="sxs-lookup"><span data-stu-id="d6634-172">CancelLine</span></span>

<span data-ttu-id="d6634-173">取消当前输入，将输入保留在屏幕上，但返回到主机以便再次计算提示。</span><span class="sxs-lookup"><span data-stu-id="d6634-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="d6634-174">Vi 插入模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6634-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="d6634-175">Vi 命令模式： `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6634-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="d6634-176">复制</span><span class="sxs-lookup"><span data-stu-id="d6634-176">Copy</span></span>

<span data-ttu-id="d6634-177">将所选区域复制到系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="d6634-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="d6634-178">如果未选择区域，则复制整行。</span><span class="sxs-lookup"><span data-stu-id="d6634-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="d6634-179">Cmd：`<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="d6634-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="d6634-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="d6634-180">CopyOrCancelLine</span></span>

<span data-ttu-id="d6634-181">如果选择了文本，请将其复制到剪贴板，否则取消该行。</span><span class="sxs-lookup"><span data-stu-id="d6634-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="d6634-182">Cmd：`<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6634-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="d6634-183">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6634-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="d6634-184">剪切</span><span class="sxs-lookup"><span data-stu-id="d6634-184">Cut</span></span>

<span data-ttu-id="d6634-185">删除所选区域将删除的文本放入系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="d6634-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="d6634-186">Cmd：`<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="d6634-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="d6634-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="d6634-187">DeleteChar</span></span>

<span data-ttu-id="d6634-188">删除光标下的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="d6634-189">Cmd：`<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6634-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="d6634-190">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6634-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="d6634-191">Vi 插入模式： `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6634-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="d6634-192">Vi 命令模式： `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6634-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="d6634-193">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="d6634-193">DeleteCharOrExit</span></span>

<span data-ttu-id="d6634-194">删除光标下的字符; 如果行为空，则退出该过程。</span><span class="sxs-lookup"><span data-stu-id="d6634-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="d6634-195">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d6634-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="d6634-196">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="d6634-196">DeleteEndOfBuffer</span></span>

<span data-ttu-id="d6634-197">删除到多行缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-197">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="d6634-198">Vi 命令模式： `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="d6634-198">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="d6634-199">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="d6634-199">DeleteEndOfWord</span></span>

<span data-ttu-id="d6634-200">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-200">Delete to the end of the word.</span></span>

- <span data-ttu-id="d6634-201">Vi 命令模式： `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="d6634-201">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="d6634-202">Deleteline.invoke</span><span class="sxs-lookup"><span data-stu-id="d6634-202">DeleteLine</span></span>

<span data-ttu-id="d6634-203">删除多行缓冲区的当前逻辑行，启用 "撤消"。</span><span class="sxs-lookup"><span data-stu-id="d6634-203">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="d6634-204">Vi 命令模式： `<d,d>` ， `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="d6634-204">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="d6634-205">DeletePreviousLines</span><span class="sxs-lookup"><span data-stu-id="d6634-205">DeletePreviousLines</span></span>

<span data-ttu-id="d6634-206">删除多行缓冲区中以前请求的逻辑行和当前逻辑行。</span><span class="sxs-lookup"><span data-stu-id="d6634-206">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="d6634-207">Vi 命令模式： `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="d6634-207">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="d6634-208">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="d6634-208">DeleteRelativeLines</span></span>

<span data-ttu-id="d6634-209">从缓冲区的开头删除到多行缓冲区中的当前逻辑行。</span><span class="sxs-lookup"><span data-stu-id="d6634-209">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="d6634-210">作为最多 Vi 命令，该 `<d,g,g>` 命令可以用一个指定绝对行号的数值参数预置，这一数字参数与当前行号一起构成了要删除的行范围。</span><span class="sxs-lookup"><span data-stu-id="d6634-210">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="d6634-211">如果未指定，则数值参数默认为1，这表示多行缓冲区中的第一个逻辑行。</span><span class="sxs-lookup"><span data-stu-id="d6634-211">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="d6634-212">要从多行删除的实际行数将计算为当前逻辑行号和指定数值参数之间的差值，这可能是负数。</span><span class="sxs-lookup"><span data-stu-id="d6634-212">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="d6634-213">因此，方法名称的 _相关_ 部分。</span><span class="sxs-lookup"><span data-stu-id="d6634-213">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="d6634-214">Vi 命令模式： `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="d6634-214">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="d6634-215">DeleteNextLines</span><span class="sxs-lookup"><span data-stu-id="d6634-215">DeleteNextLines</span></span>

<span data-ttu-id="d6634-216">删除多行缓冲区中的当前逻辑行和下一个请求的逻辑行。</span><span class="sxs-lookup"><span data-stu-id="d6634-216">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="d6634-217">Vi 命令模式： `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="d6634-217">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="d6634-218">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="d6634-218">DeleteLineToFirstChar</span></span>

<span data-ttu-id="d6634-219">删除从光标到行的第一个非空白字符的文本。</span><span class="sxs-lookup"><span data-stu-id="d6634-219">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="d6634-220">Vi 命令模式： `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="d6634-220">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="d6634-221">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="d6634-221">DeleteToEnd</span></span>

<span data-ttu-id="d6634-222">删除到行的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-222">Delete to the end of the line.</span></span>

- <span data-ttu-id="d6634-223">Vi 命令模式： `<D>` ， `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="d6634-223">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="d6634-224">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="d6634-224">DeleteWord</span></span>

<span data-ttu-id="d6634-225">删除下一个词。</span><span class="sxs-lookup"><span data-stu-id="d6634-225">Delete the next word.</span></span>

- <span data-ttu-id="d6634-226">Vi 命令模式： `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="d6634-226">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="d6634-227">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="d6634-227">ForwardDeleteLine</span></span>

<span data-ttu-id="d6634-228">与 ForwardKillLine 一样，从点到行尾删除文本，但不会将删除的文本放入 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-228">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="d6634-229">Cmd：`<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-229">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="d6634-230">Vi 插入模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-230">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="d6634-231">Vi 命令模式： `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-231">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="d6634-232">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="d6634-232">InsertLineAbove</span></span>

<span data-ttu-id="d6634-233">在当前行的上方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="d6634-233">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="d6634-234">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-234">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="d6634-235">Cmd：`<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-235">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="d6634-236">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="d6634-236">InsertLineBelow</span></span>

<span data-ttu-id="d6634-237">在当前行下方创建新的空行，而不考虑光标在当前行上的位置。</span><span class="sxs-lookup"><span data-stu-id="d6634-237">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="d6634-238">光标移动到新行的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-238">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="d6634-239">Cmd：`<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-239">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="d6634-240">InvertCase</span><span class="sxs-lookup"><span data-stu-id="d6634-240">InvertCase</span></span>

<span data-ttu-id="d6634-241">反转当前字符的大小写，并移到下一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-241">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="d6634-242">Vi 命令模式： `<~>`</span><span class="sxs-lookup"><span data-stu-id="d6634-242">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="d6634-243">KillLine</span><span class="sxs-lookup"><span data-stu-id="d6634-243">KillLine</span></span>

<span data-ttu-id="d6634-244">清除从光标到输入末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-244">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="d6634-245">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-245">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6634-246">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="d6634-246">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="d6634-247">KillRegion</span><span class="sxs-lookup"><span data-stu-id="d6634-247">KillRegion</span></span>

<span data-ttu-id="d6634-248">终止光标和标记之间的文本。</span><span class="sxs-lookup"><span data-stu-id="d6634-248">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="d6634-249">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-249">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="d6634-250">KillWord</span><span class="sxs-lookup"><span data-stu-id="d6634-250">KillWord</span></span>

<span data-ttu-id="d6634-251">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-251">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="d6634-252">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-252">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="d6634-253">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-253">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6634-254">Cmd： `<Alt+d>` ， `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6634-254">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="d6634-255">Emacs： `<Alt+d>` ， `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="d6634-255">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="d6634-256">Vi 插入模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6634-256">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="d6634-257">Vi 命令模式： `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6634-257">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="d6634-258">粘贴</span><span class="sxs-lookup"><span data-stu-id="d6634-258">Paste</span></span>

<span data-ttu-id="d6634-259">粘贴系统剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="d6634-259">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="d6634-260">Cmd： `<Ctrl+v>` ， `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="d6634-260">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="d6634-261">Vi 插入模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="d6634-261">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="d6634-262">Vi 命令模式： `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="d6634-262">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6634-263">使用 **Paste** 函数时，剪贴板缓冲区的全部内容将粘贴到 PSReadLine 的输入缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="d6634-263">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="d6634-264">然后，将输入缓冲区传递到 PowerShell 分析器。</span><span class="sxs-lookup"><span data-stu-id="d6634-264">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="d6634-265">使用控制台应用程序的 **右键单击** 粘贴方法粘贴的输入会一次复制到输入缓冲区中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-265">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="d6634-266">复制换行符时，输入缓冲区会传递到分析器。</span><span class="sxs-lookup"><span data-stu-id="d6634-266">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="d6634-267">因此，每次对输入进行一次分析。</span><span class="sxs-lookup"><span data-stu-id="d6634-267">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="d6634-268">Paste 方法之间的区别导致了不同的执行行为。</span><span class="sxs-lookup"><span data-stu-id="d6634-268">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="d6634-269">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="d6634-269">PasteAfter</span></span>

<span data-ttu-id="d6634-270">在光标后面粘贴剪贴板，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-270">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="d6634-271">Vi 命令模式： `<p>`</span><span class="sxs-lookup"><span data-stu-id="d6634-271">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="d6634-272">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="d6634-272">PasteBefore</span></span>

<span data-ttu-id="d6634-273">将剪贴板粘贴到光标之前，并将光标移动到粘贴文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-273">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="d6634-274">Vi 命令模式： `<P>`</span><span class="sxs-lookup"><span data-stu-id="d6634-274">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="d6634-275">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="d6634-275">PrependAndAccept</span></span>

<span data-ttu-id="d6634-276">预置 "#" 并接受该行。</span><span class="sxs-lookup"><span data-stu-id="d6634-276">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="d6634-277">Vi 命令模式： `<#>`</span><span class="sxs-lookup"><span data-stu-id="d6634-277">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="d6634-278">重做</span><span class="sxs-lookup"><span data-stu-id="d6634-278">Redo</span></span>

<span data-ttu-id="d6634-279">撤消撤消。</span><span class="sxs-lookup"><span data-stu-id="d6634-279">Undo an undo.</span></span>

- <span data-ttu-id="d6634-280">Cmd：`<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-280">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="d6634-281">Vi 插入模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-281">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="d6634-282">Vi 命令模式： `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-282">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="d6634-283">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="d6634-283">RepeatLastCommand</span></span>

<span data-ttu-id="d6634-284">重复最后一次文本修改。</span><span class="sxs-lookup"><span data-stu-id="d6634-284">Repeat the last text modification.</span></span>

- <span data-ttu-id="d6634-285">Vi 命令模式： `<.>`</span><span class="sxs-lookup"><span data-stu-id="d6634-285">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="d6634-286">RevertLine</span><span class="sxs-lookup"><span data-stu-id="d6634-286">RevertLine</span></span>

<span data-ttu-id="d6634-287">将所有输入还原为当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-287">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="d6634-288">Cmd：`<Escape>`</span><span class="sxs-lookup"><span data-stu-id="d6634-288">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="d6634-289">Emacs： `<Alt+r>` ， `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="d6634-289">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="d6634-290">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="d6634-290">ShellBackwardKillWord</span></span>

<span data-ttu-id="d6634-291">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-291">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d6634-292">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-292">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d6634-293">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-293">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="d6634-294">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-294">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="d6634-295">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="d6634-295">ShellKillWord</span></span>

<span data-ttu-id="d6634-296">清除从光标到当前单词末尾的输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-296">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="d6634-297">如果光标位于单词之间，则会将输入从光标处清除到下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-297">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="d6634-298">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-298">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="d6634-299">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-299">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="d6634-300">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="d6634-300">SwapCharacters</span></span>

<span data-ttu-id="d6634-301">交换当前字符和该字符之前的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-301">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="d6634-302">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d6634-302">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="d6634-303">Vi 插入模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d6634-303">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="d6634-304">Vi 命令模式： `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d6634-304">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="d6634-305">撤消</span><span class="sxs-lookup"><span data-stu-id="d6634-305">Undo</span></span>

<span data-ttu-id="d6634-306">撤消上一个编辑。</span><span class="sxs-lookup"><span data-stu-id="d6634-306">Undo a previous edit.</span></span>

- <span data-ttu-id="d6634-307">Cmd：`<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="d6634-307">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="d6634-308">Emacs： `<Ctrl+_>` ， `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="d6634-308">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="d6634-309">Vi 插入模式： `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="d6634-309">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="d6634-310">Vi 命令模式： `<Ctrl+z>` ， `<u>`</span><span class="sxs-lookup"><span data-stu-id="d6634-310">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="d6634-311">UndoAll</span><span class="sxs-lookup"><span data-stu-id="d6634-311">UndoAll</span></span>

<span data-ttu-id="d6634-312">撤消对行的所有以前的编辑。</span><span class="sxs-lookup"><span data-stu-id="d6634-312">Undo all previous edits for line.</span></span>

- <span data-ttu-id="d6634-313">Vi 命令模式： `<U>`</span><span class="sxs-lookup"><span data-stu-id="d6634-313">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="d6634-314">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="d6634-314">UnixWordRubout</span></span>

<span data-ttu-id="d6634-315">清除从当前单词开头到光标的输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-315">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d6634-316">如果光标位于单词之间，则会从上一个字的开头到光标清除输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-316">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d6634-317">清除的文本会置于 kill 循环中。</span><span class="sxs-lookup"><span data-stu-id="d6634-317">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6634-318">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="d6634-318">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="d6634-319">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="d6634-319">ValidateAndAcceptLine</span></span>

<span data-ttu-id="d6634-320">尝试执行当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-320">Attempt to execute the current input.</span></span> <span data-ttu-id="d6634-321">如果当前输入不完整 (例如，缺少右括号、方括号或引号，则继续提示符将显示在下一行，PSReadLine 将等待键编辑当前输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-321">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="d6634-322">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="d6634-322">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="d6634-323">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="d6634-323">ViAcceptLine</span></span>

<span data-ttu-id="d6634-324">接受行并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="d6634-324">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="d6634-325">Vi 命令模式： `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6634-325">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="d6634-326">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="d6634-326">ViAcceptLineOrExit</span></span>

<span data-ttu-id="d6634-327">与 Emacs 模式下的 DeleteCharOrExit 类似，但接受行而不是删除字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-327">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="d6634-328">Vi 插入模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d6634-328">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="d6634-329">Vi 命令模式： `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d6634-329">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="d6634-330">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="d6634-330">ViAppendLine</span></span>

<span data-ttu-id="d6634-331">新行插入到当前行的下方。</span><span class="sxs-lookup"><span data-stu-id="d6634-331">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="d6634-332">Vi 命令模式： `<o>`</span><span class="sxs-lookup"><span data-stu-id="d6634-332">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="d6634-333">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-333">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="d6634-334">删除上一个词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6634-334">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="d6634-335">Vi 命令模式： `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="d6634-335">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="d6634-336">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-336">ViBackwardGlob</span></span>

<span data-ttu-id="d6634-337">将光标移回上一个词的开头，仅使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6634-337">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="d6634-338">Vi 命令模式： `<B>`</span><span class="sxs-lookup"><span data-stu-id="d6634-338">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="d6634-339">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="d6634-339">ViDeleteBrace</span></span>

<span data-ttu-id="d6634-340">查找匹配的大括号、圆括号或方括号，并删除其中的所有内容，包括大括号。</span><span class="sxs-lookup"><span data-stu-id="d6634-340">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="d6634-341">Vi 命令模式： `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="d6634-341">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="d6634-342">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-342">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="d6634-343">删除到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-343">Delete to the end of the word.</span></span>

- <span data-ttu-id="d6634-344">Vi 命令模式： `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="d6634-344">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="d6634-345">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-345">ViDeleteGlob</span></span>

<span data-ttu-id="d6634-346">删除下一个 glob (空格分隔的单词) 。</span><span class="sxs-lookup"><span data-stu-id="d6634-346">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="d6634-347">Vi 命令模式： `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="d6634-347">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="d6634-348">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="d6634-348">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="d6634-349">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-349">Deletes until given character.</span></span>

- <span data-ttu-id="d6634-350">Vi 命令模式： `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="d6634-350">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="d6634-351">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-351">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="d6634-352">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-352">Deletes until given character.</span></span>

- <span data-ttu-id="d6634-353">Vi 命令模式： `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="d6634-353">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="d6634-354">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="d6634-354">ViDeleteToChar</span></span>

<span data-ttu-id="d6634-355">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-355">Deletes until given character.</span></span>

- <span data-ttu-id="d6634-356">Vi 命令模式： `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="d6634-356">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="d6634-357">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-357">ViDeleteToCharBackward</span></span>

<span data-ttu-id="d6634-358">向后删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-358">Deletes backwards until given character.</span></span>

- <span data-ttu-id="d6634-359">Vi 命令模式： `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="d6634-359">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="d6634-360">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="d6634-360">ViInsertAtBegining</span></span>

<span data-ttu-id="d6634-361">切换到插入模式，并将光标置于行首。</span><span class="sxs-lookup"><span data-stu-id="d6634-361">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="d6634-362">Vi 命令模式： `<I>`</span><span class="sxs-lookup"><span data-stu-id="d6634-362">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="d6634-363">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="d6634-363">ViInsertAtEnd</span></span>

<span data-ttu-id="d6634-364">切换到插入模式，并将光标置于行的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-364">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="d6634-365">Vi 命令模式： `<A>`</span><span class="sxs-lookup"><span data-stu-id="d6634-365">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="d6634-366">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="d6634-366">ViInsertLine</span></span>

<span data-ttu-id="d6634-367">在当前行的上方插入新行。</span><span class="sxs-lookup"><span data-stu-id="d6634-367">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="d6634-368">Vi 命令模式： `<O>`</span><span class="sxs-lookup"><span data-stu-id="d6634-368">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="d6634-369">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="d6634-369">ViInsertWithAppend</span></span>

<span data-ttu-id="d6634-370">从当前行位置追加。</span><span class="sxs-lookup"><span data-stu-id="d6634-370">Append from the current line position.</span></span>

- <span data-ttu-id="d6634-371">Vi 命令模式： `<a>`</span><span class="sxs-lookup"><span data-stu-id="d6634-371">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="d6634-372">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="d6634-372">ViInsertWithDelete</span></span>

<span data-ttu-id="d6634-373">删除当前字符并切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="d6634-373">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="d6634-374">Vi 命令模式： `<s>`</span><span class="sxs-lookup"><span data-stu-id="d6634-374">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="d6634-375">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="d6634-375">ViJoinLines</span></span>

<span data-ttu-id="d6634-376">联接当前行和下一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-376">Joins the current line and the next line.</span></span>

- <span data-ttu-id="d6634-377">Vi 命令模式： `<J>`</span><span class="sxs-lookup"><span data-stu-id="d6634-377">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="d6634-378">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="d6634-378">ViReplaceLine</span></span>

<span data-ttu-id="d6634-379">擦除整个命令行。</span><span class="sxs-lookup"><span data-stu-id="d6634-379">Erase the entire command line.</span></span>

- <span data-ttu-id="d6634-380">Vi 命令模式： `<S>` ， `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="d6634-380">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="d6634-381">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="d6634-381">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="d6634-382">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-382">Replaces until given character.</span></span>

- <span data-ttu-id="d6634-383">Vi 命令模式： `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="d6634-383">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="d6634-384">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-384">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="d6634-385">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-385">Replaces until given character.</span></span>

- <span data-ttu-id="d6634-386">Vi 命令模式： `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="d6634-386">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="d6634-387">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="d6634-387">ViReplaceToChar</span></span>

<span data-ttu-id="d6634-388">删除到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-388">Deletes until given character.</span></span>

- <span data-ttu-id="d6634-389">Vi 命令模式： `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="d6634-389">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="d6634-390">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-390">ViReplaceToCharBackward</span></span>

<span data-ttu-id="d6634-391">替换到给定的字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-391">Replaces until given character.</span></span>

- <span data-ttu-id="d6634-392">Vi 命令模式： `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="d6634-392">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="d6634-393">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="d6634-393">ViYankBeginningOfLine</span></span>

<span data-ttu-id="d6634-394">从缓冲区的开头到游标的 Yank。</span><span class="sxs-lookup"><span data-stu-id="d6634-394">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="d6634-395">Vi 命令模式： `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="d6634-395">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="d6634-396">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-396">ViYankEndOfGlob</span></span>

<span data-ttu-id="d6634-397">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-397">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="d6634-398">Vi 命令模式： `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="d6634-398">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="d6634-399">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="d6634-399">ViYankEndOfWord</span></span>

<span data-ttu-id="d6634-400">从光标 Yank 到单词 (s) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-400">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="d6634-401">Vi 命令模式： `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="d6634-401">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="d6634-402">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="d6634-402">ViYankLeft</span></span>

<span data-ttu-id="d6634-403">Yank 字符 (s) 光标左侧。</span><span class="sxs-lookup"><span data-stu-id="d6634-403">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="d6634-404">Vi 命令模式： `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="d6634-404">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="d6634-405">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="d6634-405">ViYankLine</span></span>

<span data-ttu-id="d6634-406">Yank 整个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d6634-406">Yank the entire buffer.</span></span>

- <span data-ttu-id="d6634-407">Vi 命令模式： `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-407">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="d6634-408">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-408">ViYankNextGlob</span></span>

<span data-ttu-id="d6634-409">Yank 从 cursor 到下一个单词 () 的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-409">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="d6634-410">Vi 命令模式： `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="d6634-410">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="d6634-411">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="d6634-411">ViYankNextWord</span></span>

<span data-ttu-id="d6634-412">Yank 在游标后) 的单词 (。</span><span class="sxs-lookup"><span data-stu-id="d6634-412">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="d6634-413">Vi 命令模式： `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="d6634-413">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="d6634-414">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="d6634-414">ViYankPercent</span></span>

<span data-ttu-id="d6634-415">Yank 匹配的大括号。</span><span class="sxs-lookup"><span data-stu-id="d6634-415">Yank to/from matching brace.</span></span>

- <span data-ttu-id="d6634-416">Vi 命令模式： `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="d6634-416">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="d6634-417">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-417">ViYankPreviousGlob</span></span>

<span data-ttu-id="d6634-418">从单词 (开始，) 到游标。</span><span class="sxs-lookup"><span data-stu-id="d6634-418">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="d6634-419">Vi 命令模式： `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="d6634-419">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="d6634-420">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="d6634-420">ViYankPreviousWord</span></span>

<span data-ttu-id="d6634-421">Yank 在游标前)  (s。</span><span class="sxs-lookup"><span data-stu-id="d6634-421">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="d6634-422">Vi 命令模式： `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="d6634-422">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="d6634-423">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="d6634-423">ViYankRight</span></span>

<span data-ttu-id="d6634-424">Yank 字符 (s) 光标右侧和右侧。</span><span class="sxs-lookup"><span data-stu-id="d6634-424">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="d6634-425">Vi 命令模式： `<y,l>` ， `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6634-425">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="d6634-426">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="d6634-426">ViYankToEndOfLine</span></span>

<span data-ttu-id="d6634-427">Yank 从游标到缓冲区的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-427">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="d6634-428">Vi 命令模式： `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="d6634-428">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="d6634-429">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="d6634-429">ViYankToFirstChar</span></span>

<span data-ttu-id="d6634-430">从第一个非空白字符 Yank 到游标。</span><span class="sxs-lookup"><span data-stu-id="d6634-430">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="d6634-431">Vi 命令模式： `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="d6634-431">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="d6634-432">Yank</span><span class="sxs-lookup"><span data-stu-id="d6634-432">Yank</span></span>

<span data-ttu-id="d6634-433">将最近终止的文本添加到输入中。</span><span class="sxs-lookup"><span data-stu-id="d6634-433">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="d6634-434">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-434">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="d6634-435">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="d6634-435">YankLastArg</span></span>

<span data-ttu-id="d6634-436">Yank 上一个历史记录行中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="d6634-436">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="d6634-437">如果使用参数，则第一次调用时，其行为就像 YankNthArg。</span><span class="sxs-lookup"><span data-stu-id="d6634-437">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="d6634-438">如果多次调用，则会循环访问历史记录，而 arg 会将方向设置 (负反转方向。 ) </span><span class="sxs-lookup"><span data-stu-id="d6634-438">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="d6634-439">Cmd：`<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="d6634-439">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="d6634-440">Emacs： `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="d6634-440">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="d6634-441">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="d6634-441">YankNthArg</span></span>

<span data-ttu-id="d6634-442">Yank 从上一历史记录行) 命令后 (第一个参数。</span><span class="sxs-lookup"><span data-stu-id="d6634-442">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="d6634-443">对于参数，yank 从 0) 开始 (第 n 个参数，如果参数为负数，则从最后一个参数开始。</span><span class="sxs-lookup"><span data-stu-id="d6634-443">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="d6634-444">Emacs： `<Ctrl+Alt+y>` ， `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-444">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="d6634-445">YankPop</span><span class="sxs-lookup"><span data-stu-id="d6634-445">YankPop</span></span>

<span data-ttu-id="d6634-446">如果上一操作是 Yank 或 YankPop，则将以前的拔掉文本替换为下一个终止的文本。</span><span class="sxs-lookup"><span data-stu-id="d6634-446">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="d6634-447">Emacs： `<Alt+y>` ， `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="d6634-447">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="d6634-448">游标移动函数</span><span class="sxs-lookup"><span data-stu-id="d6634-448">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="d6634-449">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="d6634-449">BackwardChar</span></span>

<span data-ttu-id="d6634-450">将光标向左移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-450">Move the cursor one character to the left.</span></span> <span data-ttu-id="d6634-451">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-451">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="d6634-452">Cmd：`<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-452">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="d6634-453">Emacs： `<LeftArrow>` ， `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="d6634-453">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="d6634-454">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-454">BackwardWord</span></span>

<span data-ttu-id="d6634-455">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-455">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d6634-456">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-456">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6634-457">Cmd：`<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-457">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d6634-458">Emacs： `<Alt+b>` ， `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="d6634-458">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="d6634-459">Vi 插入模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-459">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d6634-460">Vi 命令模式： `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-460">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="d6634-461">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="d6634-461">BeginningOfLine</span></span>

<span data-ttu-id="d6634-462">如果输入具有多个行，则移动到当前行的开头，或者，如果已位于行首，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-462">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="d6634-463">如果输入具有单行，则移动到输入的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-463">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="d6634-464">Cmd：`<Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-464">Cmd: `<Home>`</span></span>
- <span data-ttu-id="d6634-465">Emacs： `<Home>` ， `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="d6634-465">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="d6634-466">Vi 插入模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-466">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="d6634-467">Vi 命令模式： `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-467">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="d6634-468">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="d6634-468">EndOfLine</span></span>

<span data-ttu-id="d6634-469">如果输入包含多行，则移动到当前行的末尾，或者，如果已位于行尾，则转到输入的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-469">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="d6634-470">如果输入具有单行，则移动到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-470">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="d6634-471">Cmd：`<End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-471">Cmd: `<End>`</span></span>
- <span data-ttu-id="d6634-472">Emacs： `<End>` ， `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="d6634-472">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="d6634-473">Vi 插入模式： `<End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-473">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="d6634-474">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="d6634-474">ForwardChar</span></span>

<span data-ttu-id="d6634-475">将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-475">Move the cursor one character to the right.</span></span> <span data-ttu-id="d6634-476">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-476">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="d6634-477">Cmd：`<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-477">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="d6634-478">Emacs： `<RightArrow>` ， `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="d6634-478">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="d6634-479">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-479">ForwardWord</span></span>

<span data-ttu-id="d6634-480">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-480">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d6634-481">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-481">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6634-482">Emacs： `<Alt+f>` ， `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="d6634-482">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="d6634-483">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="d6634-483">GotoBrace</span></span>

<span data-ttu-id="d6634-484">中转到匹配的大括号、圆括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="d6634-484">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="d6634-485">Cmd：`<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6634-485">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d6634-486">Vi 插入模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6634-486">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d6634-487">Vi 命令模式： `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6634-487">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="d6634-488">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="d6634-488">GotoColumn</span></span>

<span data-ttu-id="d6634-489">转到 arg 指示的列。</span><span class="sxs-lookup"><span data-stu-id="d6634-489">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="d6634-490">Vi 命令模式： `<|>`</span><span class="sxs-lookup"><span data-stu-id="d6634-490">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="d6634-491">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="d6634-491">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="d6634-492">将光标移动到行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-492">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="d6634-493">Vi 命令模式： `<^>` ， `<_>`</span><span class="sxs-lookup"><span data-stu-id="d6634-493">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="d6634-494">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="d6634-494">MoveToEndOfLine</span></span>

<span data-ttu-id="d6634-495">将光标移到输入的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-495">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="d6634-496">Vi 命令模式： `<End>` ， `<$>`</span><span class="sxs-lookup"><span data-stu-id="d6634-496">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="d6634-497">NextLine</span><span class="sxs-lookup"><span data-stu-id="d6634-497">NextLine</span></span>

<span data-ttu-id="d6634-498">将光标移到下一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-498">Move the cursor to the next line.</span></span>

- <span data-ttu-id="d6634-499">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-499">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="d6634-500">NextWord</span><span class="sxs-lookup"><span data-stu-id="d6634-500">NextWord</span></span>

<span data-ttu-id="d6634-501">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-501">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d6634-502">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-502">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6634-503">Cmd：`<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-503">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="d6634-504">Vi 插入模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-504">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="d6634-505">Vi 命令模式： `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-505">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="d6634-506">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="d6634-506">NextWordEnd</span></span>

<span data-ttu-id="d6634-507">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d6634-508">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6634-509">Vi 命令模式： `<e>`</span><span class="sxs-lookup"><span data-stu-id="d6634-509">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="d6634-510">PreviousLine</span><span class="sxs-lookup"><span data-stu-id="d6634-510">PreviousLine</span></span>

<span data-ttu-id="d6634-511">将光标移到上一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-511">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="d6634-512">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-512">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="d6634-513">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-513">ShellBackwardWord</span></span>

<span data-ttu-id="d6634-514">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d6634-515">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-515">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d6634-516">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-516">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="d6634-517">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-517">ShellForwardWord</span></span>

<span data-ttu-id="d6634-518">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d6634-519">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-519">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d6634-520">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-520">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="d6634-521">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="d6634-521">ShellNextWord</span></span>

<span data-ttu-id="d6634-522">将光标向前移动到当前单词的末尾，或者在单词之间向前移动，直到成为下一个单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="d6634-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d6634-523">Word 边界由 PowerShell 令牌定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-523">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d6634-524">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-524">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="d6634-525">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="d6634-525">ViBackwardChar</span></span>

<span data-ttu-id="d6634-526">在 Vi 编辑模式下将光标左移一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-526">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="d6634-527">这可以将光标移到多行输入的上一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-527">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="d6634-528">Vi 插入模式： `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-528">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="d6634-529">Vi 命令模式： `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="d6634-529">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="d6634-530">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-530">ViBackwardWord</span></span>

<span data-ttu-id="d6634-531">将光标移回到当前单词的开头，或者在单词之间移动，如果为，则将光标移到上一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d6634-532">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-532">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6634-533">Vi 命令模式： `<b>`</span><span class="sxs-lookup"><span data-stu-id="d6634-533">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="d6634-534">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="d6634-534">ViForwardChar</span></span>

<span data-ttu-id="d6634-535">在 Vi 编辑模式下将光标向右移动一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-535">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="d6634-536">这可能会将光标移到下一行的多行输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-536">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="d6634-537">Vi 插入模式： `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-537">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="d6634-538">Vi 命令模式： `<RightArrow>` 、 `<Spacebar>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="d6634-538">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="d6634-539">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-539">ViEndOfGlob</span></span>

<span data-ttu-id="d6634-540">将光标移到单词的末尾，只使用空格作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6634-540">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="d6634-541">Vi 命令模式： `<E>`</span><span class="sxs-lookup"><span data-stu-id="d6634-541">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="d6634-542">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-542">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="d6634-543">移到上一个词的末尾，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6634-543">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="d6634-544">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-544">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="d6634-545">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="d6634-545">ViGotoBrace</span></span>

<span data-ttu-id="d6634-546">类似于 GotoBrace，但基于字符，而不是基于标记。</span><span class="sxs-lookup"><span data-stu-id="d6634-546">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="d6634-547">Vi 命令模式： `<%>`</span><span class="sxs-lookup"><span data-stu-id="d6634-547">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="d6634-548">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="d6634-548">ViNextGlob</span></span>

<span data-ttu-id="d6634-549">移到下一个单词，只使用空格作为单词分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6634-549">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="d6634-550">Vi 命令模式： `<W>`</span><span class="sxs-lookup"><span data-stu-id="d6634-550">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="d6634-551">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="d6634-551">ViNextWord</span></span>

<span data-ttu-id="d6634-552">将光标向前移动到下一个单词的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-552">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d6634-553">字边界由一组可配置的字符集定义。</span><span class="sxs-lookup"><span data-stu-id="d6634-553">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6634-554">Vi 命令模式： `<w>`</span><span class="sxs-lookup"><span data-stu-id="d6634-554">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="d6634-555">历史记录函数</span><span class="sxs-lookup"><span data-stu-id="d6634-555">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="d6634-556">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-556">BeginningOfHistory</span></span>

<span data-ttu-id="d6634-557">移到历史记录中的第一项。</span><span class="sxs-lookup"><span data-stu-id="d6634-557">Move to the first item in the history.</span></span>

- <span data-ttu-id="d6634-558">Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="d6634-558">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="d6634-559">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-559">ClearHistory</span></span>

<span data-ttu-id="d6634-560">清除 PSReadLine 中的历史记录。</span><span class="sxs-lookup"><span data-stu-id="d6634-560">Clears history in PSReadLine.</span></span> <span data-ttu-id="d6634-561">这不会影响 PowerShell 历史记录。</span><span class="sxs-lookup"><span data-stu-id="d6634-561">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="d6634-562">Cmd：`<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="d6634-562">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="d6634-563">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-563">EndOfHistory</span></span>

<span data-ttu-id="d6634-564">移到历史记录中 (当前输入) 的最后一项。</span><span class="sxs-lookup"><span data-stu-id="d6634-564">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="d6634-565">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="d6634-565">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="d6634-566">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-566">ForwardSearchHistory</span></span>

<span data-ttu-id="d6634-567">通过历史记录执行增量向前搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-567">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="d6634-568">Cmd：`<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6634-568">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="d6634-569">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6634-569">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="d6634-570">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-570">HistorySearchBackward</span></span>

<span data-ttu-id="d6634-571">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项，该匹配项与开始与输入和光标之间的字符匹配。</span><span class="sxs-lookup"><span data-stu-id="d6634-571">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="d6634-572">Cmd：`<F8>`</span><span class="sxs-lookup"><span data-stu-id="d6634-572">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="d6634-573">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="d6634-573">HistorySearchForward</span></span>

<span data-ttu-id="d6634-574">将当前输入替换为 PSReadLine 历史记录中与 start 与 input 和 cursor 之间的字符相匹配的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="d6634-574">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="d6634-575">Cmd：`<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="d6634-575">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="d6634-576">NextHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-576">NextHistory</span></span>

<span data-ttu-id="d6634-577">将当前输入替换为 PSReadLine 历史记录中的 "next" 项。</span><span class="sxs-lookup"><span data-stu-id="d6634-577">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="d6634-578">Cmd：`<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-578">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="d6634-579">Emacs： `<DownArrow>` ， `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="d6634-579">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="d6634-580">Vi 插入模式： `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-580">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="d6634-581">Vi 命令模式： `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="d6634-581">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="d6634-582">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-582">PreviousHistory</span></span>

<span data-ttu-id="d6634-583">将当前输入替换为 PSReadLine 历史记录中的 "previous" 项。</span><span class="sxs-lookup"><span data-stu-id="d6634-583">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="d6634-584">Cmd：`<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-584">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="d6634-585">Emacs： `<UpArrow>` ， `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="d6634-585">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="d6634-586">Vi 插入模式： `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-586">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="d6634-587">Vi 命令模式： `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="d6634-587">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="d6634-588">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="d6634-588">ReverseSearchHistory</span></span>

<span data-ttu-id="d6634-589">通过历史记录执行增量向后搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-589">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="d6634-590">Cmd：`<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6634-590">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="d6634-591">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6634-591">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="d6634-592">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-592">ViSearchHistoryBackward</span></span>

<span data-ttu-id="d6634-593">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-593">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="d6634-594">Vi 插入模式： `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6634-594">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="d6634-595">Vi 命令模式： `</>` ， `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6634-595">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="d6634-596">完成函数</span><span class="sxs-lookup"><span data-stu-id="d6634-596">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="d6634-597">完成</span><span class="sxs-lookup"><span data-stu-id="d6634-597">Complete</span></span>

<span data-ttu-id="d6634-598">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="d6634-598">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="d6634-599">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="d6634-599">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="d6634-600">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="d6634-600">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="d6634-601">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-601">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="d6634-602">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="d6634-602">MenuComplete</span></span>

<span data-ttu-id="d6634-603">尝试对光标周围的文本执行完成。</span><span class="sxs-lookup"><span data-stu-id="d6634-603">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="d6634-604">如果有多个可能的完成，则使用最长的明确前缀完成。</span><span class="sxs-lookup"><span data-stu-id="d6634-604">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="d6634-605">如果尝试完成最长的明确完成，则会显示一个可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="d6634-605">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="d6634-606">Cmd： `<Ctrl+@>` ， `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6634-606">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="d6634-607">Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6634-607">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="d6634-608">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="d6634-608">PossibleCompletions</span></span>

<span data-ttu-id="d6634-609">显示可能的完成列表。</span><span class="sxs-lookup"><span data-stu-id="d6634-609">Display the list of possible completions.</span></span>

- <span data-ttu-id="d6634-610">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="d6634-610">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="d6634-611">Vi 插入模式： `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6634-611">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="d6634-612">Vi 命令模式： `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6634-612">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="d6634-613">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="d6634-613">TabCompleteNext</span></span>

<span data-ttu-id="d6634-614">尝试使用下一个可用完成来完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="d6634-614">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="d6634-615">Cmd：`<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-615">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="d6634-616">Vi 命令模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-616">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="d6634-617">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="d6634-617">TabCompletePrevious</span></span>

<span data-ttu-id="d6634-618">尝试使用以前的可用完成功能完成光标周围的文本。</span><span class="sxs-lookup"><span data-stu-id="d6634-618">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="d6634-619">Cmd：`<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-619">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="d6634-620">Vi 命令模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-620">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="d6634-621">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="d6634-621">ViTabCompleteNext</span></span>

<span data-ttu-id="d6634-622">结束当前编辑组（如果需要），并调用 TabCompleteNext。</span><span class="sxs-lookup"><span data-stu-id="d6634-622">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="d6634-623">Vi 插入模式： `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-623">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="d6634-624">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="d6634-624">ViTabCompletePrevious</span></span>

<span data-ttu-id="d6634-625">结束当前编辑组（如果需要），并调用 TabCompletePrevious。</span><span class="sxs-lookup"><span data-stu-id="d6634-625">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="d6634-626">Vi 插入模式： `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6634-626">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="d6634-627">杂项函数</span><span class="sxs-lookup"><span data-stu-id="d6634-627">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="d6634-628">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="d6634-628">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="d6634-629">接受内嵌或所选建议的下一个单词。</span><span class="sxs-lookup"><span data-stu-id="d6634-629">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="d6634-630">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-630">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="d6634-631">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="d6634-631">AcceptSuggestion</span></span>

<span data-ttu-id="d6634-632">接受当前内联或所选的建议。</span><span class="sxs-lookup"><span data-stu-id="d6634-632">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="d6634-633">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-633">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="d6634-634">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="d6634-634">CaptureScreen</span></span>

<span data-ttu-id="d6634-635">启动交互屏幕捕获-向上/向下箭头选择 "线条"，将选定文本作为文本和 html 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="d6634-635">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="d6634-636">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-636">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="d6634-637">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="d6634-637">ClearScreen</span></span>

<span data-ttu-id="d6634-638">清除屏幕并在屏幕的顶部绘制当前线条。</span><span class="sxs-lookup"><span data-stu-id="d6634-638">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="d6634-639">Cmd：`<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6634-639">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d6634-640">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6634-640">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d6634-641">Vi 插入模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6634-641">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d6634-642">Vi 命令模式： `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6634-642">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="d6634-643">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="d6634-643">DigitArgument</span></span>

<span data-ttu-id="d6634-644">启动新的数字参数，使其传递到其他函数。</span><span class="sxs-lookup"><span data-stu-id="d6634-644">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="d6634-645">Cmd： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="d6634-645">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="d6634-646">Emacs： `<Alt+0>` 、 `<Alt+1>` 、 `<Alt+2>` 、 `<Alt+3>` 、 `<Alt+4>` 、 `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、、、、、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="d6634-646">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="d6634-647">Vi 命令模式： `<0>` 、 `<1>` 、 `<2>` 、 `<3>` 、 `<4>` 、 `<5>` 、 `<6>` 、 `<7>` 、 `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="d6634-647">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="d6634-648">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="d6634-648">InvokePrompt</span></span>

<span data-ttu-id="d6634-649">清除当前提示符并调用 prompt 函数以重新显示提示符。</span><span class="sxs-lookup"><span data-stu-id="d6634-649">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="d6634-650">适用于更改状态的自定义密钥处理程序，例如更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="d6634-650">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="d6634-651">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-651">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="d6634-652">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="d6634-652">ScrollDisplayDown</span></span>

<span data-ttu-id="d6634-653">将显示向下滚动一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="d6634-653">Scroll the display down one screen.</span></span>

- <span data-ttu-id="d6634-654">Cmd：`<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6634-654">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="d6634-655">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6634-655">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="d6634-656">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="d6634-656">ScrollDisplayDownLine</span></span>

<span data-ttu-id="d6634-657">将显示向下滚动一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-657">Scroll the display down one line.</span></span>

- <span data-ttu-id="d6634-658">Cmd：`<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6634-658">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="d6634-659">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6634-659">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="d6634-660">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="d6634-660">ScrollDisplayToCursor</span></span>

<span data-ttu-id="d6634-661">将显示滚动到光标处。</span><span class="sxs-lookup"><span data-stu-id="d6634-661">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="d6634-662">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-662">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="d6634-663">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="d6634-663">ScrollDisplayTop</span></span>

<span data-ttu-id="d6634-664">向顶部滚动显示。</span><span class="sxs-lookup"><span data-stu-id="d6634-664">Scroll the display to the top.</span></span>

- <span data-ttu-id="d6634-665">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-665">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="d6634-666">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="d6634-666">ScrollDisplayUp</span></span>

<span data-ttu-id="d6634-667">将显示向上滚动一屏。</span><span class="sxs-lookup"><span data-stu-id="d6634-667">Scroll the display up one screen.</span></span>

- <span data-ttu-id="d6634-668">Cmd：`<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6634-668">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="d6634-669">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6634-669">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="d6634-670">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="d6634-670">ScrollDisplayUpLine</span></span>

<span data-ttu-id="d6634-671">将显示向上滚动一行。</span><span class="sxs-lookup"><span data-stu-id="d6634-671">Scroll the display up one line.</span></span>

- <span data-ttu-id="d6634-672">Cmd：`<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6634-672">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="d6634-673">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6634-673">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="d6634-674">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="d6634-674">SelfInsert</span></span>

<span data-ttu-id="d6634-675">插入密钥。</span><span class="sxs-lookup"><span data-stu-id="d6634-675">Insert the key.</span></span>

- <span data-ttu-id="d6634-676">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-676">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="d6634-677">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="d6634-677">ShowKeyBindings</span></span>

<span data-ttu-id="d6634-678">显示所有绑定键。</span><span class="sxs-lookup"><span data-stu-id="d6634-678">Show all bound keys.</span></span>

- <span data-ttu-id="d6634-679">Cmd：`<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6634-679">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="d6634-680">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6634-680">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="d6634-681">Vi 插入模式： `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6634-681">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="d6634-682">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="d6634-682">ViCommandMode</span></span>

<span data-ttu-id="d6634-683">将当前运行模式从 Vi-Insert 切换到 Vi-Command。</span><span class="sxs-lookup"><span data-stu-id="d6634-683">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="d6634-684">Vi 插入模式： `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="d6634-684">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="d6634-685">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="d6634-685">ViDigitArgumentInChord</span></span>

<span data-ttu-id="d6634-686">启动新的数字参数，将其传递给其他函数，同时使用 vi 的鼠标左键之一。</span><span class="sxs-lookup"><span data-stu-id="d6634-686">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="d6634-687">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-687">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="d6634-688">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="d6634-688">ViEditVisually</span></span>

<span data-ttu-id="d6634-689">在 $env： EDITOR 或 $env：视觉对象指定的文本编辑器中编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="d6634-689">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="d6634-690">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="d6634-690">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="d6634-691">Vi 命令模式： `<v>`</span><span class="sxs-lookup"><span data-stu-id="d6634-691">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="d6634-692">ViExit</span><span class="sxs-lookup"><span data-stu-id="d6634-692">ViExit</span></span>

<span data-ttu-id="d6634-693">退出 shell。</span><span class="sxs-lookup"><span data-stu-id="d6634-693">Exits the shell.</span></span>

- <span data-ttu-id="d6634-694">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-694">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="d6634-695">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="d6634-695">ViInsertMode</span></span>

<span data-ttu-id="d6634-696">切换到插入模式。</span><span class="sxs-lookup"><span data-stu-id="d6634-696">Switch to Insert mode.</span></span>

- <span data-ttu-id="d6634-697">Vi 命令模式： `<i>`</span><span class="sxs-lookup"><span data-stu-id="d6634-697">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="d6634-698">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="d6634-698">WhatIsKey</span></span>

<span data-ttu-id="d6634-699">阅读密钥，并告诉我密钥的绑定内容。</span><span class="sxs-lookup"><span data-stu-id="d6634-699">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="d6634-700">Cmd：`<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6634-700">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="d6634-701">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6634-701">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="d6634-702">选择函数</span><span class="sxs-lookup"><span data-stu-id="d6634-702">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="d6634-703">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="d6634-703">ExchangePointAndMark</span></span>

<span data-ttu-id="d6634-704">将光标置于标记的位置，并将标记移到光标所在的位置。</span><span class="sxs-lookup"><span data-stu-id="d6634-704">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="d6634-705">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="d6634-705">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="d6634-706">SelectAll</span><span class="sxs-lookup"><span data-stu-id="d6634-706">SelectAll</span></span>

<span data-ttu-id="d6634-707">选择整行。</span><span class="sxs-lookup"><span data-stu-id="d6634-707">Select the entire line.</span></span>

- <span data-ttu-id="d6634-708">Cmd：`<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="d6634-708">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="d6634-709">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="d6634-709">SelectBackwardChar</span></span>

<span data-ttu-id="d6634-710">调整当前选定内容以包括前一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-710">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="d6634-711">Cmd：`<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-711">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="d6634-712">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-712">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="d6634-713">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="d6634-713">SelectBackwardsLine</span></span>

<span data-ttu-id="d6634-714">调整当前所选内容，使其包括从光标到行的开头。</span><span class="sxs-lookup"><span data-stu-id="d6634-714">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="d6634-715">Cmd：`<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-715">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="d6634-716">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6634-716">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="d6634-717">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-717">SelectBackwardWord</span></span>

<span data-ttu-id="d6634-718">调整当前所选内容以包含上一个词。</span><span class="sxs-lookup"><span data-stu-id="d6634-718">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="d6634-719">Cmd：`<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-719">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d6634-720">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="d6634-720">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="d6634-721">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="d6634-721">SelectForwardChar</span></span>

<span data-ttu-id="d6634-722">调整当前所选内容以包含下一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-722">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="d6634-723">Cmd：`<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-723">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="d6634-724">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-724">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="d6634-725">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-725">SelectForwardWord</span></span>

<span data-ttu-id="d6634-726">使用 ForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="d6634-726">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="d6634-727">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="d6634-727">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="d6634-728">SelectLine</span><span class="sxs-lookup"><span data-stu-id="d6634-728">SelectLine</span></span>

<span data-ttu-id="d6634-729">调整当前所选内容，使其包括从光标到行尾的内容。</span><span class="sxs-lookup"><span data-stu-id="d6634-729">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="d6634-730">Cmd：`<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-730">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="d6634-731">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="d6634-731">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="d6634-732">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="d6634-732">SelectNextWord</span></span>

<span data-ttu-id="d6634-733">调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="d6634-733">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="d6634-734">Cmd：`<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6634-734">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="d6634-735">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-735">SelectShellBackwardWord</span></span>

<span data-ttu-id="d6634-736">使用 ShellBackwardWord 调整当前所选内容，使其包含前一词。</span><span class="sxs-lookup"><span data-stu-id="d6634-736">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="d6634-737">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-737">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="d6634-738">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6634-738">SelectShellForwardWord</span></span>

<span data-ttu-id="d6634-739">使用 ShellForwardWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="d6634-739">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="d6634-740">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-740">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="d6634-741">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="d6634-741">SelectShellNextWord</span></span>

<span data-ttu-id="d6634-742">使用 ShellNextWord 调整当前所选内容以包含下一个单词。</span><span class="sxs-lookup"><span data-stu-id="d6634-742">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="d6634-743">函数未绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-743">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="d6634-744">SetMark</span><span class="sxs-lookup"><span data-stu-id="d6634-744">SetMark</span></span>

<span data-ttu-id="d6634-745">标记光标的当前位置，以供后续编辑命令使用。</span><span class="sxs-lookup"><span data-stu-id="d6634-745">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="d6634-746">Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="d6634-746">Emacs: `<Ctrl+@>`</span></span>

## <a name="search-functions"></a><span data-ttu-id="d6634-747">搜索函数</span><span class="sxs-lookup"><span data-stu-id="d6634-747">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="d6634-748">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="d6634-748">CharacterSearch</span></span>

<span data-ttu-id="d6634-749">读取字符并向前搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="d6634-749">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="d6634-750">如果指定了参数，则向前搜索 (或向后) 对于第 n 个匹配项为负。</span><span class="sxs-lookup"><span data-stu-id="d6634-750">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="d6634-751">Cmd：`<F3>`</span><span class="sxs-lookup"><span data-stu-id="d6634-751">Cmd: `<F3>`</span></span>
- <span data-ttu-id="d6634-752">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6634-752">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d6634-753">Vi 插入模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d6634-753">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="d6634-754">Vi 命令模式： `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d6634-754">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="d6634-755">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-755">CharacterSearchBackward</span></span>

<span data-ttu-id="d6634-756">读取字符并向后搜索该字符的下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="d6634-756">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="d6634-757">如果指定了参数，则在第 n 个匹配项) 反向搜索时 (或转发。</span><span class="sxs-lookup"><span data-stu-id="d6634-757">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="d6634-758">Cmd：`<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d6634-758">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="d6634-759">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="d6634-759">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="d6634-760">Vi 插入模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d6634-760">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="d6634-761">Vi 命令模式： `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d6634-761">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="d6634-762">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="d6634-762">RepeatLastCharSearch</span></span>

<span data-ttu-id="d6634-763">重复上次记录的字符搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-763">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="d6634-764">Vi 命令模式： `<;>`</span><span class="sxs-lookup"><span data-stu-id="d6634-764">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="d6634-765">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="d6634-765">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="d6634-766">重复上次记录的字符搜索，但采用相反方向。</span><span class="sxs-lookup"><span data-stu-id="d6634-766">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="d6634-767">Vi 命令模式： `<,>`</span><span class="sxs-lookup"><span data-stu-id="d6634-767">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="d6634-768">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="d6634-768">RepeatSearch</span></span>

<span data-ttu-id="d6634-769">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-769">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="d6634-770">Vi 命令模式： `<n>`</span><span class="sxs-lookup"><span data-stu-id="d6634-770">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="d6634-771">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-771">RepeatSearchBackward</span></span>

<span data-ttu-id="d6634-772">像以前一样，重复最后一个搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-772">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="d6634-773">Vi 命令模式： `<N>`</span><span class="sxs-lookup"><span data-stu-id="d6634-773">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="d6634-774">SearchChar</span><span class="sxs-lookup"><span data-stu-id="d6634-774">SearchChar</span></span>

<span data-ttu-id="d6634-775">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-775">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="d6634-776">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="d6634-776">This is for 't' functionality.</span></span>

- <span data-ttu-id="d6634-777">Vi 命令模式： `<f>`</span><span class="sxs-lookup"><span data-stu-id="d6634-777">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="d6634-778">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6634-778">SearchCharBackward</span></span>

<span data-ttu-id="d6634-779">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-779">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="d6634-780">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="d6634-780">This is for 'T' functionality.</span></span>

- <span data-ttu-id="d6634-781">Vi 命令模式： `<F>`</span><span class="sxs-lookup"><span data-stu-id="d6634-781">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="d6634-782">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="d6634-782">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="d6634-783">读取下一个字符，然后查找它，向后移动，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-783">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="d6634-784">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="d6634-784">This is for 'T' functionality.</span></span>

- <span data-ttu-id="d6634-785">Vi 命令模式： `<T>`</span><span class="sxs-lookup"><span data-stu-id="d6634-785">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="d6634-786">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="d6634-786">SearchCharWithBackoff</span></span>

<span data-ttu-id="d6634-787">阅读下一个字符，然后查找、前进，然后再返回一个字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-787">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="d6634-788">这适用于 "t" 功能。</span><span class="sxs-lookup"><span data-stu-id="d6634-788">This is for 't' functionality.</span></span>

- <span data-ttu-id="d6634-789">Vi 命令模式： `<t>`</span><span class="sxs-lookup"><span data-stu-id="d6634-789">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="d6634-790">SearchForward</span><span class="sxs-lookup"><span data-stu-id="d6634-790">SearchForward</span></span>

<span data-ttu-id="d6634-791">提示输入搜索字符串并在 AcceptLine 上开始搜索。</span><span class="sxs-lookup"><span data-stu-id="d6634-791">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="d6634-792">Vi 插入模式： `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6634-792">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="d6634-793">Vi 命令模式： `<?>` ， `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6634-793">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="d6634-794">自定义键绑定</span><span class="sxs-lookup"><span data-stu-id="d6634-794">Custom Key Bindings</span></span>

<span data-ttu-id="d6634-795">PSReadLine 支持使用 cmdlet 的自定义键绑定 `Set-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="d6634-795">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="d6634-796">大多数自定义键绑定调用上述函数之一，例如</span><span class="sxs-lookup"><span data-stu-id="d6634-796">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="d6634-797">可以将 ScriptBlock 绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="d6634-797">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="d6634-798">ScriptBlock 可以执行任何所需的操作。</span><span class="sxs-lookup"><span data-stu-id="d6634-798">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="d6634-799">一些有用的示例包括</span><span class="sxs-lookup"><span data-stu-id="d6634-799">Some useful examples include</span></span>

- <span data-ttu-id="d6634-800">编辑命令行</span><span class="sxs-lookup"><span data-stu-id="d6634-800">edit the command line</span></span>
- <span data-ttu-id="d6634-801">打开新窗口 (例如，帮助) </span><span class="sxs-lookup"><span data-stu-id="d6634-801">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="d6634-802">更改目录而不更改命令行</span><span class="sxs-lookup"><span data-stu-id="d6634-802">change directories without changing the command line</span></span>

<span data-ttu-id="d6634-803">ScriptBlock 接收两个参数：</span><span class="sxs-lookup"><span data-stu-id="d6634-803">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="d6634-804">`$key` -一个作为触发自定义绑定的密钥的 **[ConsoleKeyInfo]** 对象。</span><span class="sxs-lookup"><span data-stu-id="d6634-804">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="d6634-805">如果将相同的 ScriptBlock 绑定到多个键，并且需要根据关键字执行不同的操作，则可以选中 $key。</span><span class="sxs-lookup"><span data-stu-id="d6634-805">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="d6634-806">许多自定义绑定会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="d6634-806">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="d6634-807">`$arg` -任意参数。</span><span class="sxs-lookup"><span data-stu-id="d6634-807">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="d6634-808">大多数情况下，这将是用户从键绑定 DigitArgument 传递的整数参数。</span><span class="sxs-lookup"><span data-stu-id="d6634-808">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="d6634-809">如果绑定不接受参数，则忽略此参数是合理的。</span><span class="sxs-lookup"><span data-stu-id="d6634-809">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="d6634-810">我们来看一个示例，该示例将一个命令行添加到历史记录中，而不执行它。</span><span class="sxs-lookup"><span data-stu-id="d6634-810">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="d6634-811">如果您认为您忘记了某些事情，但又不想重新输入您已经输入的命令行，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="d6634-811">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="d6634-812">你可以在 PSReadLine 模块文件夹中安装的文件中查看更多示例 `SamplePSReadLineProfile.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="d6634-812">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="d6634-813">大多数键绑定使用一些 helper 函数来编辑命令行。</span><span class="sxs-lookup"><span data-stu-id="d6634-813">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="d6634-814">下一节将介绍这些 Api。</span><span class="sxs-lookup"><span data-stu-id="d6634-814">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="d6634-815">自定义键绑定支持 Api</span><span class="sxs-lookup"><span data-stu-id="d6634-815">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="d6634-816">以下函数是 PSConsoleReadLine 中的公共函数，但不能直接绑定到密钥。</span><span class="sxs-lookup"><span data-stu-id="d6634-816">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="d6634-817">大多数在自定义键绑定中很有用。</span><span class="sxs-lookup"><span data-stu-id="d6634-817">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="d6634-818">向历史记录中添加一个命令行而不执行它。</span><span class="sxs-lookup"><span data-stu-id="d6634-818">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="d6634-819">清除终止环。</span><span class="sxs-lookup"><span data-stu-id="d6634-819">Clear the kill-ring.</span></span>  <span data-ttu-id="d6634-820">这主要用于测试。</span><span class="sxs-lookup"><span data-stu-id="d6634-820">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="d6634-821">从开始删除长度字符。</span><span class="sxs-lookup"><span data-stu-id="d6634-821">Delete length characters from start.</span></span>  <span data-ttu-id="d6634-822">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="d6634-822">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="d6634-823">根据用户首选项执行 Ding 操作。</span><span class="sxs-lookup"><span data-stu-id="d6634-823">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="d6634-824">这两个函数检索有关输入缓冲区的当前状态的有用信息。</span><span class="sxs-lookup"><span data-stu-id="d6634-824">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="d6634-825">第一种方案更常见用于简单情况。</span><span class="sxs-lookup"><span data-stu-id="d6634-825">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="d6634-826">如果绑定使用 Ast 执行更高级的操作，则会使用第二个。</span><span class="sxs-lookup"><span data-stu-id="d6634-826">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="d6634-827">这两个函数由使用 `Get-PSReadLineKeyHandler` 。</span><span class="sxs-lookup"><span data-stu-id="d6634-827">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="d6634-828">第一个用于获取所有键绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-828">The first is used to get all key bindings.</span></span> <span data-ttu-id="d6634-829">第二个用于获取特定的键绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-829">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="d6634-830">此函数由 Get-PSReadLineOption 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="d6634-830">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="d6634-831">如果未在命令行上进行选择，则将在 "开始" 和 "长度" 中返回-1。</span><span class="sxs-lookup"><span data-stu-id="d6634-831">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="d6634-832">如果命令行上有选择，则返回选定内容的开始和长度。</span><span class="sxs-lookup"><span data-stu-id="d6634-832">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="d6634-833">在光标处插入字符或字符串。</span><span class="sxs-lookup"><span data-stu-id="d6634-833">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="d6634-834">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="d6634-834">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="d6634-835">这是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="d6634-835">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="d6634-836">它不支持递归，因此在自定义键绑定中不起作用。</span><span class="sxs-lookup"><span data-stu-id="d6634-836">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="d6634-837">此函数由 Remove-PSReadLineKeyHandler 使用，并可能在自定义键绑定中不太有用。</span><span class="sxs-lookup"><span data-stu-id="d6634-837">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="d6634-838">替换部分输入。</span><span class="sxs-lookup"><span data-stu-id="d6634-838">Replace some of the input.</span></span> <span data-ttu-id="d6634-839">此操作支持撤消/重做。</span><span class="sxs-lookup"><span data-stu-id="d6634-839">This operation supports undo/redo.</span></span> <span data-ttu-id="d6634-840">这优先于删除后再执行 Insert，因为它被视为单个操作来撤消。</span><span class="sxs-lookup"><span data-stu-id="d6634-840">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="d6634-841">将光标移动到给定偏移量。</span><span class="sxs-lookup"><span data-stu-id="d6634-841">Move the cursor to the given offset.</span></span> <span data-ttu-id="d6634-842">不跟踪游标移动以便撤消。</span><span class="sxs-lookup"><span data-stu-id="d6634-842">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="d6634-843">此函数是 cmdlet PSReadLineOption 使用的帮助器方法，但可能对要临时更改设置的自定义密钥绑定很有用。</span><span class="sxs-lookup"><span data-stu-id="d6634-843">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="d6634-844">此帮助器方法用于接受 DigitArgument 的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d6634-844">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="d6634-845">典型调用如下所示</span><span class="sxs-lookup"><span data-stu-id="d6634-845">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="d6634-846">注意</span><span class="sxs-lookup"><span data-stu-id="d6634-846">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="d6634-847">POWERSHELL 兼容性</span><span class="sxs-lookup"><span data-stu-id="d6634-847">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="d6634-848">PSReadLine 要求安装 PowerShell 3.0 或更高版本，以及控制台主机。</span><span class="sxs-lookup"><span data-stu-id="d6634-848">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="d6634-849">它在 PowerShell ISE 中不起作用。</span><span class="sxs-lookup"><span data-stu-id="d6634-849">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="d6634-850">它在 Visual Studio Code 的控制台中工作。</span><span class="sxs-lookup"><span data-stu-id="d6634-850">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="d6634-851">命令历史记录</span><span class="sxs-lookup"><span data-stu-id="d6634-851">COMMAND HISTORY</span></span>

<span data-ttu-id="d6634-852">PSReadLine 维护一个历史记录文件，其中包含在命令行中输入的所有命令和数据。</span><span class="sxs-lookup"><span data-stu-id="d6634-852">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="d6634-853">这可能包含敏感数据（包括密码）。</span><span class="sxs-lookup"><span data-stu-id="d6634-853">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="d6634-854">例如，如果使用 cmdlet，则 `ConvertTo-SecureString` 密码将作为纯文本记录到历史记录文件中。</span><span class="sxs-lookup"><span data-stu-id="d6634-854">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="d6634-855">历史记录文件是一个名为的文件 `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="d6634-855">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="d6634-856">在 Windows 系统上，历史记录文件存储在中 `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="d6634-856">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="d6634-857">在非 Windows 系统上，历史记录文件存储在 `$env:XDG_DATA_HOME/powershell/PSReadLine` 或上 `$env:HOME/.local/share/powershell/PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="d6634-857">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="d6634-858">参与 PSReadLine 的反馈 &</span><span class="sxs-lookup"><span data-stu-id="d6634-858">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="d6634-859">GitHub 上的 PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d6634-859">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="d6634-860">可在 GitHub 页上随意提交拉取请求或提交反馈。</span><span class="sxs-lookup"><span data-stu-id="d6634-860">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6634-861">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6634-861">SEE ALSO</span></span>

<span data-ttu-id="d6634-862">PSReadLine 会受到 GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) 库的严重影响。</span><span class="sxs-lookup"><span data-stu-id="d6634-862">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>

