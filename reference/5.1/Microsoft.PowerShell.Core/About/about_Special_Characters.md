---
description: 介绍用于控制 PowerShell 如何解释序列中的下一个字符的特殊字符序列。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 875a1c3c63e759151c3c64b5396312b030955cb7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200060"
---
# <a name="about-special-characters"></a><span data-ttu-id="1050a-104">关于特殊字符</span><span class="sxs-lookup"><span data-stu-id="1050a-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="1050a-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="1050a-105">Short description</span></span>

<span data-ttu-id="1050a-106">介绍用于控制 PowerShell 如何解释序列中的下一个字符的特殊字符序列。</span><span class="sxs-lookup"><span data-stu-id="1050a-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="1050a-107">长说明</span><span class="sxs-lookup"><span data-stu-id="1050a-107">Long description</span></span>

<span data-ttu-id="1050a-108">PowerShell 支持使用一组特殊字符序列来表示不属于标准字符集的字符。</span><span class="sxs-lookup"><span data-stu-id="1050a-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="1050a-109">序列通常称为 " _转义序列_ "。</span><span class="sxs-lookup"><span data-stu-id="1050a-109">The sequences are commonly known as _escape sequences_ .</span></span>

<span data-ttu-id="1050a-110">转义序列以反撇号字符开头，称为抑音符 (ASCII 96) ，区分大小写。</span><span class="sxs-lookup"><span data-stu-id="1050a-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="1050a-111">反撇号字符也可以称为 _转义字符_ 。</span><span class="sxs-lookup"><span data-stu-id="1050a-111">The backtick character can also be referred to as the _escape character_ .</span></span>

<span data-ttu-id="1050a-112">仅当转义序列包含在带双引号的 () 字符串中时，才会进行解释 `"` 。</span><span class="sxs-lookup"><span data-stu-id="1050a-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="1050a-113">PowerShell 可识别以下转义序列：</span><span class="sxs-lookup"><span data-stu-id="1050a-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="1050a-114">序列</span><span class="sxs-lookup"><span data-stu-id="1050a-114">Sequence</span></span>   |       <span data-ttu-id="1050a-115">说明</span><span class="sxs-lookup"><span data-stu-id="1050a-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="1050a-116">Null</span><span class="sxs-lookup"><span data-stu-id="1050a-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="1050a-117">警报</span><span class="sxs-lookup"><span data-stu-id="1050a-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="1050a-118">Backspace</span><span class="sxs-lookup"><span data-stu-id="1050a-118">Backspace</span></span>               |
| `` `f ``    | <span data-ttu-id="1050a-119">换页</span><span class="sxs-lookup"><span data-stu-id="1050a-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="1050a-120">换行</span><span class="sxs-lookup"><span data-stu-id="1050a-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="1050a-121">回车</span><span class="sxs-lookup"><span data-stu-id="1050a-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="1050a-122">水平制表符</span><span class="sxs-lookup"><span data-stu-id="1050a-122">Horizontal tab</span></span>          |
| `` `v ``    | <span data-ttu-id="1050a-123">垂直制表符</span><span class="sxs-lookup"><span data-stu-id="1050a-123">Vertical tab</span></span>            |

<span data-ttu-id="1050a-124">PowerShell 还具有一个特殊的标记，用于标记要停止分析的位置。</span><span class="sxs-lookup"><span data-stu-id="1050a-124">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="1050a-125">跟在此标记后面的所有字符都用作未解释的文本值。</span><span class="sxs-lookup"><span data-stu-id="1050a-125">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="1050a-126">特殊分析令牌：</span><span class="sxs-lookup"><span data-stu-id="1050a-126">Special parsing token:</span></span>

| <span data-ttu-id="1050a-127">序列</span><span class="sxs-lookup"><span data-stu-id="1050a-127">Sequence</span></span> |            <span data-ttu-id="1050a-128">说明</span><span class="sxs-lookup"><span data-stu-id="1050a-128">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="1050a-129">停止分析下面的任何内容</span><span class="sxs-lookup"><span data-stu-id="1050a-129">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="1050a-130">Null ("0) </span><span class="sxs-lookup"><span data-stu-id="1050a-130">Null (\`0)</span></span>

<span data-ttu-id="1050a-131">Null (`` `0 ``) 字符在 PowerShell 输出中显示为空白区域。</span><span class="sxs-lookup"><span data-stu-id="1050a-131">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="1050a-132">此功能允许你使用 PowerShell 读取和处理使用空字符的文本文件，如字符串终止或记录终止指示器。</span><span class="sxs-lookup"><span data-stu-id="1050a-132">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="1050a-133">Null 特殊字符不等效于 `$null` 存储 **null** 值的变量。</span><span class="sxs-lookup"><span data-stu-id="1050a-133">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="1050a-134">警报 ("a) </span><span class="sxs-lookup"><span data-stu-id="1050a-134">Alert (\`a)</span></span>

<span data-ttu-id="1050a-135">警报 (`` `a ``) 字符将嘟嘟声信号发送到计算机的扬声器。</span><span class="sxs-lookup"><span data-stu-id="1050a-135">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="1050a-136">您可以使用此字符警告用户即将执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1050a-136">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="1050a-137">下面的示例向本地计算机的扬声器发送两条嘟嘟声信号。</span><span class="sxs-lookup"><span data-stu-id="1050a-137">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="1050a-138">Backspace ("b) </span><span class="sxs-lookup"><span data-stu-id="1050a-138">Backspace (\`b)</span></span>

<span data-ttu-id="1050a-139">Backspace (`` `b ``) 字符将光标向后移动一个字符，但不会删除任何字符。</span><span class="sxs-lookup"><span data-stu-id="1050a-139">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="1050a-140">该示例将写入单词 **backup** ，然后将光标向后移动两次。</span><span class="sxs-lookup"><span data-stu-id="1050a-140">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="1050a-141">然后，在新位置写入一个空格，后跟单词 **out** 。</span><span class="sxs-lookup"><span data-stu-id="1050a-141">Then, at the new position, writes a space followed by the word **out** .</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="form-feed-f"></a><span data-ttu-id="1050a-142">换页符 ("f) </span><span class="sxs-lookup"><span data-stu-id="1050a-142">Form feed (\`f)</span></span>

<span data-ttu-id="1050a-143"> () 字符的窗体馈送 `` `f `` 是一种打印指令，用于弹出当前页面并继续在下一页上打印。</span><span class="sxs-lookup"><span data-stu-id="1050a-143">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="1050a-144">窗体馈送字符只影响打印文档。</span><span class="sxs-lookup"><span data-stu-id="1050a-144">The form feed character only affects printed documents.</span></span> <span data-ttu-id="1050a-145">它不会影响屏幕输出。</span><span class="sxs-lookup"><span data-stu-id="1050a-145">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="1050a-146">新行 (' n) </span><span class="sxs-lookup"><span data-stu-id="1050a-146">New line (\`n)</span></span>

<span data-ttu-id="1050a-147">新行 (`` `n ``) 字符直接在字符后面插入一个换行符。</span><span class="sxs-lookup"><span data-stu-id="1050a-147">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="1050a-148">此示例演示如何在命令中使用新行字符创建分行符 `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="1050a-148">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="1050a-149">回车 (r) </span><span class="sxs-lookup"><span data-stu-id="1050a-149">Carriage return (\`r)</span></span>

<span data-ttu-id="1050a-150">回车 (`` `r ``) 字符将输出光标移动到当前行的开头，并继续写入。</span><span class="sxs-lookup"><span data-stu-id="1050a-150">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="1050a-151">当前行上的任何字符都将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="1050a-151">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="1050a-152">在此示例中，将覆盖回车符前的文本。</span><span class="sxs-lookup"><span data-stu-id="1050a-152">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="1050a-153">请注意，不会删除字符之前的文本 `` `r `` ，它会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="1050a-153">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="1050a-154">水平选项卡 (不) </span><span class="sxs-lookup"><span data-stu-id="1050a-154">Horizontal tab (\`t)</span></span>

<span data-ttu-id="1050a-155">"水平" 选项卡 (`` `t ``) 字符前进到下一个制表位，并在该点继续写入。</span><span class="sxs-lookup"><span data-stu-id="1050a-155">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="1050a-156">默认情况下，PowerShell 控制台每隔8个空格都有一个制表位。</span><span class="sxs-lookup"><span data-stu-id="1050a-156">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="1050a-157">此示例在每个列之间插入两个制表符。</span><span class="sxs-lookup"><span data-stu-id="1050a-157">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="vertical-tab-v"></a><span data-ttu-id="1050a-158">垂直选项卡 ("v) </span><span class="sxs-lookup"><span data-stu-id="1050a-158">Vertical tab (\`v)</span></span>

<span data-ttu-id="1050a-159">"水平" 选项卡 (`` `v ``) 字符前进到下一个垂直制表位，并在该点写入剩余的输出。</span><span class="sxs-lookup"><span data-stu-id="1050a-159">The horizontal tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="1050a-160">这在默认的 Windows 控制台中不起作用。</span><span class="sxs-lookup"><span data-stu-id="1050a-160">This has no effect in the default Windows console.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="1050a-161">下面的示例显示了你将在打印机或其他控制台主机上获得的输出。</span><span class="sxs-lookup"><span data-stu-id="1050a-161">The following example shows the output you would get on a printer or in a different console host.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="1050a-162">停止分析标记 (--% ) </span><span class="sxs-lookup"><span data-stu-id="1050a-162">Stop-parsing token (--%)</span></span>

<span data-ttu-id="1050a-163">停止分析 (`--%`) 标记阻止 powershell 将字符串解释为 powershell 命令和表达式。</span><span class="sxs-lookup"><span data-stu-id="1050a-163">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="1050a-164">这允许将这些字符串传递到其他程序进行解释。</span><span class="sxs-lookup"><span data-stu-id="1050a-164">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="1050a-165">将停止解析标记放在程序名之后、可能导致错误的程序参数之前。</span><span class="sxs-lookup"><span data-stu-id="1050a-165">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="1050a-166">在此示例中，该 `Icacls` 命令使用了停止分析标记。</span><span class="sxs-lookup"><span data-stu-id="1050a-166">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="1050a-167">PowerShell 将以下字符串发送到 `Icacls` 。</span><span class="sxs-lookup"><span data-stu-id="1050a-167">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="1050a-168">以下是另一个示例。</span><span class="sxs-lookup"><span data-stu-id="1050a-168">Here is another example.</span></span> <span data-ttu-id="1050a-169">**ShowArgs** 函数输出传递给它的值。</span><span class="sxs-lookup"><span data-stu-id="1050a-169">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="1050a-170">在此示例中，我们将名为的变量传递 `$HOME` 到函数两次。</span><span class="sxs-lookup"><span data-stu-id="1050a-170">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

你可以在输出中看到，对于第一个参数，该变量 `$HOME` 由 PowerShell 进行解释，以便将该变量的值传递到函数。 <span data-ttu-id="1050a-172">的第二次使用 `$HOME` 出现在停止分析令牌之后，因此字符串 "$HOME" 将传递给函数，而不会被解释。</span><span class="sxs-lookup"><span data-stu-id="1050a-172">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="1050a-173">有关停止分析令牌的详细信息，请参阅 [about_Parsing](about_Parsing.md)。</span><span class="sxs-lookup"><span data-stu-id="1050a-173">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1050a-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1050a-174">See also</span></span>

[<span data-ttu-id="1050a-175">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1050a-175">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
