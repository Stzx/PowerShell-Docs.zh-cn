---
description: 描述如何在 PowerShell 命令提示符处编辑命令。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_line_editing?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Line_Editing
ms.openlocfilehash: 59516bf14ca273c495c3d126a40a76f31293735b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199810"
---
# <a name="about-line-editing"></a><span data-ttu-id="bbaff-104">关于行编辑</span><span class="sxs-lookup"><span data-stu-id="bbaff-104">About Line Editing</span></span>

## <a name="short-description"></a><span data-ttu-id="bbaff-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="bbaff-105">Short description</span></span>

<span data-ttu-id="bbaff-106">描述如何在 PowerShell 命令提示符处编辑命令。</span><span class="sxs-lookup"><span data-stu-id="bbaff-106">Describes how to edit commands at the PowerShell command prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="bbaff-107">长说明</span><span class="sxs-lookup"><span data-stu-id="bbaff-107">Long description</span></span>

<span data-ttu-id="bbaff-108">PowerShell 控制台提供了一些有用的键盘快捷方式，可帮助你在 PowerShell 命令提示符下编辑命令。</span><span class="sxs-lookup"><span data-stu-id="bbaff-108">The PowerShell console has some useful keyboard shortcuts to help you edit commands at the PowerShell command prompt.</span></span>

### <a name="add-a-line"></a><span data-ttu-id="bbaff-109">添加线条</span><span class="sxs-lookup"><span data-stu-id="bbaff-109">Add a line</span></span>

<span data-ttu-id="bbaff-110">若要添加行，请按<kbd>Shift</kbd> + <kbd>enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-110">To add a line, press <kbd>Shift</kbd>+<kbd>Enter</kbd>.</span></span>

<span data-ttu-id="bbaff-111">您可以添加多个行。</span><span class="sxs-lookup"><span data-stu-id="bbaff-111">You can add multiple lines.</span></span> <span data-ttu-id="bbaff-112">每增加一行都以开头 `>>` ，即继续提示。</span><span class="sxs-lookup"><span data-stu-id="bbaff-112">Each additional line begins with `>>`, the continuation prompt.</span></span> <span data-ttu-id="bbaff-113">按 <kbd>enter</kbd> 执行该命令。</span><span class="sxs-lookup"><span data-stu-id="bbaff-113">Press <kbd>Enter</kbd> to execute the command.</span></span>

### <a name="move-left-and-right"></a><span data-ttu-id="bbaff-114">向左和向右移动</span><span class="sxs-lookup"><span data-stu-id="bbaff-114">Move left and right</span></span>

<span data-ttu-id="bbaff-115">若要将光标左移一个字符，请按 <kbd>向左键</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-115">To move the cursor one character to the left, press the <kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="bbaff-116">若要将光标左移一个字，请按<kbd>Ctrl</kbd> + <kbd>向左键</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-116">To move the cursor one word to the left, press <kbd>Ctrl</kbd>+<kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="bbaff-117">若要将光标向右移动一个字符，请按 <kbd>向右箭头</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-117">To move the cursor one character to the right, press the <kbd>Right arrow</kbd>.</span></span>

<span data-ttu-id="bbaff-118">若要将光标向右移动一个单词，请按<kbd>Ctrl</kbd> + <kbd>向右箭头</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-118">To move the cursor one word to the right, press <kbd>Ctrl</kbd>+<kbd>Right arrow</kbd>.</span></span>

### <a name="move-to-a-lines-beginning-or-end"></a><span data-ttu-id="bbaff-119">移到行的开头或结尾</span><span class="sxs-lookup"><span data-stu-id="bbaff-119">Move to a line's beginning or end</span></span>

<span data-ttu-id="bbaff-120">若要移动到行首，请按 <kbd>Home</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-120">To move to the beginning of a line, press <kbd>Home</kbd>.</span></span>

<span data-ttu-id="bbaff-121">若要移动到行尾，请按 <kbd>end</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-121">To move to the end of a line, press <kbd>End</kbd>.</span></span>

<span data-ttu-id="bbaff-122">如果已添加行，请按 <kbd>Home</kbd> 或 <kbd>end</kbd> 两次，移动到行的开头或结尾。</span><span class="sxs-lookup"><span data-stu-id="bbaff-122">If lines were added, press <kbd>Home</kbd> or <kbd>End</kbd> twice to move to the beginning or end of the lines.</span></span>

### <a name="delete-characters"></a><span data-ttu-id="bbaff-123">删除字符</span><span class="sxs-lookup"><span data-stu-id="bbaff-123">Delete characters</span></span>

<span data-ttu-id="bbaff-124">若要删除光标位置后面的字符，请按 <kbd>Backspace</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-124">To delete the character behind the cursor's position, press <kbd>Backspace</kbd>.</span></span>

<span data-ttu-id="bbaff-125">若要删除光标位置的字符，请按 <kbd>delete</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-125">To delete the character at the cursor's position, press <kbd>Delete</kbd>.</span></span>

### <a name="delete-characters-from-a-line"></a><span data-ttu-id="bbaff-126">删除行中的字符</span><span class="sxs-lookup"><span data-stu-id="bbaff-126">Delete characters from a line</span></span>

<span data-ttu-id="bbaff-127">若要删除从光标位置到行尾的所有字符，请按<kbd>Ctrl</kbd> + <kbd>end</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-127">To delete all the characters from the cursor's position to the end of a line, press <kbd>Ctrl</kbd>+<kbd>End</kbd>.</span></span>

<span data-ttu-id="bbaff-128">若要删除从光标位置到行首的所有字符，请按<kbd>Ctrl</kbd> + <kbd>Home</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-128">To delete all the characters from the cursor's position to the beginning of a line, press <kbd>Ctrl</kbd>+<kbd>Home</kbd>.</span></span>

<span data-ttu-id="bbaff-129">如果已添加行，则从当前行和已添加的行中删除字符。</span><span class="sxs-lookup"><span data-stu-id="bbaff-129">If lines were added, characters are deleted from the current line and the lines that were added.</span></span>

### <a name="insert-and-overstrike-mode"></a><span data-ttu-id="bbaff-130">Insert 和替换模式</span><span class="sxs-lookup"><span data-stu-id="bbaff-130">Insert and overstrike mode</span></span>

<span data-ttu-id="bbaff-131">若要更改为覆盖模式，请按 <kbd>Insert</kbd>。</span><span class="sxs-lookup"><span data-stu-id="bbaff-131">To change to overwrite mode, press <kbd>Insert</kbd>.</span></span> <span data-ttu-id="bbaff-132">若要返回到插入模式，请再次按 <kbd>insert</kbd> 。</span><span class="sxs-lookup"><span data-stu-id="bbaff-132">To return to insert mode, press <kbd>Insert</kbd> again.</span></span>

### <a name="tab-completion"></a><span data-ttu-id="bbaff-133">Tab 自动补全</span><span class="sxs-lookup"><span data-stu-id="bbaff-133">Tab completion</span></span>

<span data-ttu-id="bbaff-134">若要完成 cmdlet 名称、参数或路径，请按 <kbd>tab</kbd> 键。</span><span class="sxs-lookup"><span data-stu-id="bbaff-134">To complete a cmdlet name, a parameter, or a path, press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="bbaff-135">若要在值列表中滚动，请再次按 <kbd>tab</kbd> 键。</span><span class="sxs-lookup"><span data-stu-id="bbaff-135">To scroll through a list of values, press the <kbd>Tab</kbd> key again.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbaff-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbaff-136">See also</span></span>

[<span data-ttu-id="bbaff-137">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="bbaff-137">about_Command_Syntax</span></span>](about_Command_Syntax.md)

[<span data-ttu-id="bbaff-138">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="bbaff-138">about_Path_Syntax</span></span>](about_Path_Syntax.md)

[<span data-ttu-id="bbaff-139">about_PSReadline</span><span class="sxs-lookup"><span data-stu-id="bbaff-139">about_PSReadline</span></span>](../../PSReadline/About/about_PSReadline.md)
