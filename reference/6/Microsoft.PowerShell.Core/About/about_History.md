---
description: 介绍如何在命令历史记录中获取和运行命令。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: e009b6d1ecd739c321bdc45e5b043cbdea392db0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199821"
---
# <a name="about-history"></a><span data-ttu-id="234ca-104">关于历史记录</span><span class="sxs-lookup"><span data-stu-id="234ca-104">About History</span></span>

## <a name="short-description"></a><span data-ttu-id="234ca-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="234ca-105">Short Description</span></span>
<span data-ttu-id="234ca-106">介绍如何在命令历史记录中获取和运行命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-106">Describes how to get and run commands in the command history.</span></span>

## <a name="long-description"></a><span data-ttu-id="234ca-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="234ca-107">Long Description</span></span>

<span data-ttu-id="234ca-108">当你在命令提示符下输入命令时，PowerShell 会将命令保存在命令历史记录中。</span><span class="sxs-lookup"><span data-stu-id="234ca-108">When you enter a command at the command prompt, PowerShell saves the command in the command history.</span></span> <span data-ttu-id="234ca-109">你可以使用历史记录中的命令作为你的工作记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-109">You can use the commands in the history as a record of your work.</span></span> <span data-ttu-id="234ca-110">而且，您可以从命令历史记录中调用并运行命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-110">And, you can recall and run the commands from the command history.</span></span>

<span data-ttu-id="234ca-111">PowerShell 具有两个不同的历史记录提供程序：内置历史记录和 **PSReadLine** 模块管理的历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-111">PowerShell has two different history providers: the built-in history and the history managed by the **PSReadLine** module.</span></span> <span data-ttu-id="234ca-112">历史记录是分开管理的，但这两个历史记录均可用于加载 **PSReadLine** 的会话中。</span><span class="sxs-lookup"><span data-stu-id="234ca-112">The histories are managed separately, but both histories are available in sessions where **PSReadLine** is loaded.</span></span>

## <a name="using-the-psreadline-history"></a><span data-ttu-id="234ca-113">使用 PSReadLine 历史记录</span><span class="sxs-lookup"><span data-stu-id="234ca-113">Using the PSReadLine history</span></span>

<span data-ttu-id="234ca-114">PSReadLine 历史记录跟踪所有 PowerShell 会话中使用的命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-114">The PSReadLine history tracks the commands used in all PowerShell sessions.</span></span>
<span data-ttu-id="234ca-115">历史记录将写入每个主机的中心文件。</span><span class="sxs-lookup"><span data-stu-id="234ca-115">The history is written to a central file per host.</span></span> <span data-ttu-id="234ca-116">该历史记录文件可供所有会话使用，并包含所有过去的历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-116">That history file is available to all sessions and contains all past history.</span></span> <span data-ttu-id="234ca-117">会话结束时不会删除历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-117">The history is not deleted when the session ends.</span></span> <span data-ttu-id="234ca-118">此外，这些 cmdlet 无法管理该历史记录 `*-History` 。</span><span class="sxs-lookup"><span data-stu-id="234ca-118">Also, that history cannot be managed by the `*-History` cmdlets.</span></span> <span data-ttu-id="234ca-119">有关详细信息，请参阅 [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)。</span><span class="sxs-lookup"><span data-stu-id="234ca-119">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

## <a name="using-the-built-in-session-history"></a><span data-ttu-id="234ca-120">使用内置会话历史记录</span><span class="sxs-lookup"><span data-stu-id="234ca-120">Using the built-in session history</span></span>

<span data-ttu-id="234ca-121">内置历史记录只跟踪当前会话中使用的命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-121">The built-in history only tracks the commands used in the current session.</span></span> <span data-ttu-id="234ca-122">历史记录不能用于其他会话，在会话结束时将被删除。</span><span class="sxs-lookup"><span data-stu-id="234ca-122">The history is not available to other sessions and is deleted when the session ends.</span></span>

### <a name="history-cmdlets"></a><span data-ttu-id="234ca-123">历史记录 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="234ca-123">History Cmdlets</span></span>

<span data-ttu-id="234ca-124">PowerShell 包含一组用于管理命令历史记录的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="234ca-124">PowerShell has a set of cmdlets that manage the command history.</span></span>

| <span data-ttu-id="234ca-125">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="234ca-125">Cmdlet</span></span>           | <span data-ttu-id="234ca-126">Alias</span><span class="sxs-lookup"><span data-stu-id="234ca-126">Alias</span></span>  | <span data-ttu-id="234ca-127">说明</span><span class="sxs-lookup"><span data-stu-id="234ca-127">Description</span></span>                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | <span data-ttu-id="234ca-128">获取命令历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-128">Gets the command history.</span></span>                  |
| `Invoke-History` | `r`    | <span data-ttu-id="234ca-129">在命令历史记录中运行命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-129">Runs a command in the command history.</span></span>     |
| `Add-History`    |        | <span data-ttu-id="234ca-130">将命令添加到命令历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-130">Adds a command to the command history.</span></span>     |
| `Clear-History`  | `clhy` | <span data-ttu-id="234ca-131">从命令历史记录中删除命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-131">Deletes commands from the command history.</span></span> |

### <a name="keyboard-shortcuts-for-managing-history"></a><span data-ttu-id="234ca-132">用于管理历史记录的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="234ca-132">Keyboard Shortcuts for Managing History</span></span>

<span data-ttu-id="234ca-133">在 PowerShell 控制台中，可以使用以下快捷方式管理命令历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-133">In the PowerShell console, you can use the following shortcuts to manage the command history.</span></span>

- <span data-ttu-id="234ca-134"><kbd>向上键</kbd> -显示上一个命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-134"><kbd>UpArrow</kbd> - Displays the previous command.</span></span>
- <span data-ttu-id="234ca-135"><kbd>向下键</kbd> -显示下一个命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-135"><kbd>DownArrow</kbd> - Displays the next command.</span></span>
- <span data-ttu-id="234ca-136"><kbd>F7</kbd> -显示命令历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-136"><kbd>F7</kbd> - Displays the command history.</span></span>
- <span data-ttu-id="234ca-137"><kbd>ESC</kbd> -隐藏历史记录。</span><span class="sxs-lookup"><span data-stu-id="234ca-137"><kbd>ESC</kbd> - To hide the history.</span></span>
- <span data-ttu-id="234ca-138"><kbd>F8</kbd> -查找命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-138"><kbd>F8</kbd> - Finds a command.</span></span> <span data-ttu-id="234ca-139">键入一个或多个字符，然后按 <kbd>F8</kbd>。</span><span class="sxs-lookup"><span data-stu-id="234ca-139">Type one or more characters then press <kbd>F8</kbd>.</span></span> <span data-ttu-id="234ca-140">再次按 <kbd>F8</kbd> 。</span><span class="sxs-lookup"><span data-stu-id="234ca-140">Press <kbd>F8</kbd> again the next instance.</span></span>
- <span data-ttu-id="234ca-141"><kbd>F9</kbd> -按历史记录 ID 查找命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-141"><kbd>F9</kbd> - Find a command by history ID.</span></span> <span data-ttu-id="234ca-142">键入历史记录 ID，然后按 <kbd>F9</kbd>。</span><span class="sxs-lookup"><span data-stu-id="234ca-142">Type the history ID then press <kbd>F9</kbd>.</span></span> <span data-ttu-id="234ca-143">按 <kbd>F7</kbd> 查找 ID。</span><span class="sxs-lookup"><span data-stu-id="234ca-143">Press <kbd>F7</kbd> to find the ID.</span></span>
- <span data-ttu-id="234ca-144"><kbd>#</kbd>`<string>`</kbd><kbd>选项卡</kbd> -搜索历史记录 `*<string>*` ，并返回最近的匹配项。</span><span class="sxs-lookup"><span data-stu-id="234ca-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> - Search the history for `*<string>*` and returns the most recent match.</span></span> <span data-ttu-id="234ca-145">如果重复按 <kbd>tab</kbd> 键，则会循环遍历历史记录中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="234ca-145">If you press <kbd>Tab</kbd> repeatedly, it cycles through the matching items in your history.</span></span>

> [!NOTE]
> <span data-ttu-id="234ca-146">这些密钥绑定由控制台主机应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="234ca-146">These key bindings are implemented by the console host application.</span></span> <span data-ttu-id="234ca-147">其他应用程序（如 Visual Studio Code 或 Windows 终端）可以具有不同的键绑定。</span><span class="sxs-lookup"><span data-stu-id="234ca-147">Other applications, such as Visual Studio Code or Windows Terminal, can have different key bindings.</span></span> <span data-ttu-id="234ca-148">绑定可由 PSReadLine 模块重写。</span><span class="sxs-lookup"><span data-stu-id="234ca-148">The bindings can be overridden by the PSReadLine module.</span></span> <span data-ttu-id="234ca-149">启动 PowerShell 会话时，PSReadLine 会自动加载。</span><span class="sxs-lookup"><span data-stu-id="234ca-149">PSReadLine loads automatically when you start a PowerShell session.</span></span>
> <span data-ttu-id="234ca-150">在加载 PSReadLine 的情况下， <kbd>F7</kbd> 和 <kbd>F9</kbd> 未绑定到任何函数。</span><span class="sxs-lookup"><span data-stu-id="234ca-150">With PSReadLine loaded, <kbd>F7</kbd> and <kbd>F9</kbd> are not bound to any function.</span></span> <span data-ttu-id="234ca-151">PSReadLine 未提供等效功能。</span><span class="sxs-lookup"><span data-stu-id="234ca-151">PSReadLine does not provide equivalent functionality.</span></span> <span data-ttu-id="234ca-152">有关详细信息，请参阅 [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)。</span><span class="sxs-lookup"><span data-stu-id="234ca-152">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="234ca-153">MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="234ca-153">MaximumHistoryCount</span></span>

<span data-ttu-id="234ca-154">`$MaximumHistoryCount`首选项变量确定 PowerShell 在命令历史记录中保存的最大命令数。</span><span class="sxs-lookup"><span data-stu-id="234ca-154">The `$MaximumHistoryCount` preference variable determines the maximum number of commands that PowerShell saves in the command history.</span></span> <span data-ttu-id="234ca-155">默认值为</span><span class="sxs-lookup"><span data-stu-id="234ca-155">The default value is</span></span>
4096.

<span data-ttu-id="234ca-156">例如，以下命令将减少 `$MaximumHistoryCount` 到100命令：</span><span class="sxs-lookup"><span data-stu-id="234ca-156">For example, the following command lowers the `$MaximumHistoryCount` to 100 commands:</span></span>

```powershell
$MaximumHistoryCount = 100
```

<span data-ttu-id="234ca-157">若要应用设置，请重新启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="234ca-157">To apply the setting, restart PowerShell.</span></span>

<span data-ttu-id="234ca-158">若要为所有 PowerShell 会话保存新的变量值，请将赋值语句添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="234ca-158">To save the new variable value for all your PowerShell sessions, add the assignment statement to a PowerShell profile.</span></span> <span data-ttu-id="234ca-159">有关配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="234ca-159">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="234ca-160">有关 `$MaximumHistoryCount` 首选项变量的详细信息，请参阅 [about_Preference_Variables](about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="234ca-160">For more information about the `$MaximumHistoryCount` preference variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="order-of-commands-in-the-history"></a><span data-ttu-id="234ca-161">历史记录中的命令顺序</span><span class="sxs-lookup"><span data-stu-id="234ca-161">Order of Commands in the History</span></span>

<span data-ttu-id="234ca-162">命令完成执行时（而不是在输入命令时），会将命令添加到历史记录中。</span><span class="sxs-lookup"><span data-stu-id="234ca-162">Commands are added to the history when the command finishes executing, not when the command is entered.</span></span> <span data-ttu-id="234ca-163">如果命令需要一些时间才能完成，或命令在嵌套提示符下执行，则这些命令在历史记录中的显示顺序可能会不按顺序显示。</span><span class="sxs-lookup"><span data-stu-id="234ca-163">If commands take some time to be completed, or if the commands are executing in a nested prompt, the commands might appear to be out of order in the history.</span></span> <span data-ttu-id="234ca-164">仅当退出提示级别时，才会完成在嵌套提示中执行的命令。</span><span class="sxs-lookup"><span data-stu-id="234ca-164">Commands that are executing in a nested prompt are completed only when you exit the prompt level.</span></span>

## <a name="see-also"></a><span data-ttu-id="234ca-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="234ca-165">See Also</span></span>

- [<span data-ttu-id="234ca-166">about_Line_Editing</span><span class="sxs-lookup"><span data-stu-id="234ca-166">about_Line_Editing</span></span>](about_Line_Editing.md)
- [<span data-ttu-id="234ca-167">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="234ca-167">about_Preference_Variables</span></span>](about_Preference_Variables.md)
- [<span data-ttu-id="234ca-168">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="234ca-168">about_Profiles</span></span>](about_Profiles.md)
- [<span data-ttu-id="234ca-169">about_Variables</span><span class="sxs-lookup"><span data-stu-id="234ca-169">about_Variables</span></span>](about_Variables.md)
- [<span data-ttu-id="234ca-170">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="234ca-170">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)
