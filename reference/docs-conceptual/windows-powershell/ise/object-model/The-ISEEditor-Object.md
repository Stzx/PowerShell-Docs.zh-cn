---
ms.date: 12/31/2019
title: ISEEditor 对象
description: ISEEditor 对象是 Microsoft.PowerShell.Host.ISE.ISEEditor 类的实例。 控制台窗格是 ISEEditor 对象。
ms.openlocfilehash: ffcb6e35e1160beab6efb29cc84847fa9ffd012b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92654055"
---
# <a name="the-iseeditor-object"></a><span data-ttu-id="7a7a4-104">ISEEditor 对象</span><span class="sxs-lookup"><span data-stu-id="7a7a4-104">The ISEEditor Object</span></span>

<span data-ttu-id="7a7a4-105">**ISEEditor** 对象是 Microsoft.PowerShell.Host.ISE.ISEEditor 类的实例。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-105">An **ISEEditor** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEEditor class.</span></span> <span data-ttu-id="7a7a4-106">控制台窗格是 **ISEEditor** 对象。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-106">The Console pane is an **ISEEditor** object.</span></span> <span data-ttu-id="7a7a4-107">每个 [ISEFile](The-ISEFile-Object.md) 对象都有一个关联的 **ISEEditor** 对象。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-107">Each [ISEFile](The-ISEFile-Object.md) object has an associated **ISEEditor** object.</span></span> <span data-ttu-id="7a7a4-108">以下各节列出了 **ISEEditor** 对象的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-108">The following sections list the methods and properties of an **ISEEditor** object.</span></span>

## <a name="methods"></a><span data-ttu-id="7a7a4-109">方法</span><span class="sxs-lookup"><span data-stu-id="7a7a4-109">Methods</span></span>

### <a name="clear"></a><span data-ttu-id="7a7a4-110">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-110">Clear\(\)</span></span>

<span data-ttu-id="7a7a4-111">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-112">清除编辑器中的文本。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-112">Clears the text in the editor.</span></span>

```powershell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a><span data-ttu-id="7a7a4-113">EnsureVisible\(int lineNumber\)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-113">EnsureVisible\(int lineNumber\)</span></span>

<span data-ttu-id="7a7a4-114">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-115">滚动编辑器以使对应于指定 **lineNumber** 参数值的行可见。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-115">Scrolls the editor so that the line that corresponds to the specified **lineNumber** parameter value is visible.</span></span> <span data-ttu-id="7a7a4-116">如果指定的行号超出范围 1，即用于定义有效行号的最后一个行号，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-116">It throws an exception if the specified line number is outside the range of 1,last line number, which defines the valid line numbers.</span></span>

<span data-ttu-id="7a7a4-117">**lineNumber** 要使其可见的行号。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-117">**lineNumber** The number of the line that is to be made visible.</span></span>

```powershell
# Scrolls the text in the Script pane so that the fifth line is in view.
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a><span data-ttu-id="7a7a4-118">Focus\(\)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-118">Focus\(\)</span></span>

<span data-ttu-id="7a7a4-119">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-120">将焦点设置到编辑器。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-120">Sets the focus to the editor.</span></span>

```powershell
# Sets focus to the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a><span data-ttu-id="7a7a4-121">GetLineLength\(int lineNumber \)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-121">GetLineLength\(int lineNumber \)</span></span>

<span data-ttu-id="7a7a4-122">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-123">获取按行号指定的行的长度（整数形式）。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-123">Gets the line length as an integer for the line that is specified by the line number.</span></span>

<span data-ttu-id="7a7a4-124">**lineNumber** 要获取长度的行号。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-124">**lineNumber** The number of the line of which to get the length.</span></span>

<span data-ttu-id="7a7a4-125">**Returns** 所指定行号的行的长度。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-125">**Returns** The line length for the line at the specified line number.</span></span>

```powershell
# Gets the length of the first line in the text of the Command pane.
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a><span data-ttu-id="7a7a4-126">GoToMatch\(\)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-126">GoToMatch\(\)</span></span>

<span data-ttu-id="7a7a4-127">在 Windows PowerShell ISE 3.0 和更高版本中受支持，但不存在于早期版本中。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-127">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="7a7a4-128">如果编辑器对象的 CanGoToMatch 属性是 `$true`，当脱字号直接位于左括号、中括号或大括号 - `(`、`[`、`{` 之前或直接位于右括号、中括号或大括号 - `)`、`]`、`}` 之后。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-128">Moves the caret to the matching character if the **CanGoToMatch** property of the editor object is `$true`, which occurs when the caret is immediately before an opening parenthesis, bracket, or brace - `(`,`[`,`{` - or immediately after a closing parenthesis, bracket, or brace - `)`,`]`,`}`.</span></span> <span data-ttu-id="7a7a4-129">脱字号位于开始字符之前或结束字符之后。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-129">The caret is placed before an opening character or after a closing character.</span></span> <span data-ttu-id="7a7a4-130">如果 CanGoToMatch 属性是 `$false`，则此方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-130">If the **CanGoToMatch** property is `$false`, then this method does nothing.</span></span>

```powershell
# Goes to the matching character if CanGoToMatch() is $true
$psISE.CurrentPowerShellTab.ConsolePane.GoToMatch()
```

### <a name="inserttext-text-"></a><span data-ttu-id="7a7a4-131">InsertText\( text \)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-131">InsertText\( text \)</span></span>

<span data-ttu-id="7a7a4-132">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-132">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-133">将所选内容替换为文本或在当前脱字号位置插入文本。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-133">Replaces the selection with text or inserts text at the current caret position.</span></span>

<span data-ttu-id="7a7a4-134">**text** - String 要插入的文本。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-134">**text** - String The text to insert.</span></span>

<span data-ttu-id="7a7a4-135">请参阅本主题稍后介绍的[脚本示例](#scripting-example)。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-135">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="select-startline-startcolumn-endline-endcolumn-"></a><span data-ttu-id="7a7a4-136">Select\( startLine, startColumn, endLine, endColumn \)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-136">Select\( startLine, startColumn, endLine, endColumn \)</span></span>

<span data-ttu-id="7a7a4-137">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-137">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-138">从 **startLine** 、 **startColumn** 、 **endLine** 和 **endColumn** 参数中选择文本。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-138">Selects the text from the **startLine** , **startColumn** , **endLine** , and **endColumn** parameters.</span></span>

<span data-ttu-id="7a7a4-139">**startLine** - Integer 所选内容的起始行。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-139">**startLine** - Integer The line where the selection starts.</span></span>

<span data-ttu-id="7a7a4-140">**startColumn** - Integer 所选内容的起始行中的列。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-140">**startColumn** - Integer The column within the start line where the selection starts.</span></span>

<span data-ttu-id="7a7a4-141">**endLine** - Integer 所选内容的结束行。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-141">**endLine** - Integer The line where the selection ends.</span></span>

<span data-ttu-id="7a7a4-142">**endColumn** - Integer 所选内容的结束行中的列。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-142">**endColumn** - Integer The column within the end line where the selection ends.</span></span>

<span data-ttu-id="7a7a4-143">请参阅本主题稍后介绍的[脚本示例](#scripting-example)。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-143">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="selectcaretline"></a><span data-ttu-id="7a7a4-144">SelectCaretLine\(\)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-144">SelectCaretLine\(\)</span></span>

<span data-ttu-id="7a7a4-145">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-145">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-146">选择当前包含脱字号的整个文本行。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-146">Selects the entire line of text that currently contains the caret.</span></span>

```powershell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a><span data-ttu-id="7a7a4-147">SetCaretPosition\( lineNumber, columnNumber \)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-147">SetCaretPosition\( lineNumber, columnNumber \)</span></span>

<span data-ttu-id="7a7a4-148">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-148">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-149">在行号和列号处设置脱字号位置。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-149">Sets the caret position at the line number and the column number.</span></span> <span data-ttu-id="7a7a4-150">如果脱字号行号或脱字号列号不在其各自的有效范围内，会引发异常。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-150">It throws an exception if either the caret line number or the caret column number are out of their respective valid ranges.</span></span>

<span data-ttu-id="7a7a4-151">**lineNumber** - Integer 脱字号行号。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-151">**lineNumber** - Integer The caret line number.</span></span>

<span data-ttu-id="7a7a4-152">**columnNumber** - Integer 脱字号列号。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-152">**columnNumber** - Integer The caret column number.</span></span>

```powershell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a><span data-ttu-id="7a7a4-153">ToggleOutliningExpansion\(\)</span><span class="sxs-lookup"><span data-stu-id="7a7a4-153">ToggleOutliningExpansion\(\)</span></span>

<span data-ttu-id="7a7a4-154">在 Windows PowerShell ISE 3.0 和更高版本中受支持，但不存在于早期版本中。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-154">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="7a7a4-155">使所有大纲部分展开或折叠。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-155">Causes all the outline sections to expand or collapse.</span></span>

```powershell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a><span data-ttu-id="7a7a4-156">属性</span><span class="sxs-lookup"><span data-stu-id="7a7a4-156">Properties</span></span>

### <a name="cangotomatch"></a><span data-ttu-id="7a7a4-157">CanGoToMatch</span><span class="sxs-lookup"><span data-stu-id="7a7a4-157">CanGoToMatch</span></span>

<span data-ttu-id="7a7a4-158">在 Windows PowerShell ISE 3.0 和更高版本中受支持，但不存在于早期版本中。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-158">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="7a7a4-159">只读布尔值属性，指示脱字号是否位于小括号、中括号或大括号（即 `()`、`[]`、`{}`）旁边。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-159">The read-only Boolean property to indicate whether the caret is next to a parenthesis, bracket, or brace - `()`, `[]`, `{}`.</span></span> <span data-ttu-id="7a7a4-160">如果脱字号直接位于开始字符之前或直接位于结束字符之后，则此属性值是 `$true`。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-160">If the caret is immediately before the opening character or immediately after the closing character of a pair, then this property value is `$true`.</span></span> <span data-ttu-id="7a7a4-161">否则为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-161">Otherwise, it is `$false`.</span></span>

```powershell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

### <a name="caretcolumn"></a><span data-ttu-id="7a7a4-162">CaretColumn</span><span class="sxs-lookup"><span data-stu-id="7a7a4-162">CaretColumn</span></span>

<span data-ttu-id="7a7a4-163">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-163">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-164">只读属性，可获取对应于脱字号位置的列号。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-164">The read-only property that gets the column number that corresponds to the position of the caret.</span></span>

```powershell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

### <a name="caretline"></a><span data-ttu-id="7a7a4-165">CaretLine</span><span class="sxs-lookup"><span data-stu-id="7a7a4-165">CaretLine</span></span>

<span data-ttu-id="7a7a4-166">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-166">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-167">只读属性，可获取包含脱字号的行号。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-167">The read-only property that gets the number of the line that contains the caret.</span></span>

```powershell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

### <a name="caretlinetext"></a><span data-ttu-id="7a7a4-168">CaretLineText</span><span class="sxs-lookup"><span data-stu-id="7a7a4-168">CaretLineText</span></span>

<span data-ttu-id="7a7a4-169">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-169">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-170">只读属性，可获取包含脱字号的完整文本行。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-170">The read-only property that gets the complete line of text that contains the caret.</span></span>

```powershell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

### <a name="linecount"></a><span data-ttu-id="7a7a4-171">LineCount</span><span class="sxs-lookup"><span data-stu-id="7a7a4-171">LineCount</span></span>

<span data-ttu-id="7a7a4-172">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-172">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-173">只读属性，可获取编辑器中的行计数。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-173">The read-only property that gets the line count from the editor.</span></span>

```powershell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

### <a name="selectedtext"></a><span data-ttu-id="7a7a4-174">SelectedText</span><span class="sxs-lookup"><span data-stu-id="7a7a4-174">SelectedText</span></span>

<span data-ttu-id="7a7a4-175">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-175">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-176">只读属性，可获取编辑器中的所选文本。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-176">The read-only property that gets the selected text from the editor.</span></span>

<span data-ttu-id="7a7a4-177">请参阅本主题稍后介绍的[脚本示例](#scripting-example)。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-177">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="text"></a><span data-ttu-id="7a7a4-178">文本</span><span class="sxs-lookup"><span data-stu-id="7a7a4-178">Text</span></span>

<span data-ttu-id="7a7a4-179">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-179">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7a7a4-180">读写属性，可获取或设置编辑器中的文本。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-180">The read/write property that gets or sets the text in the editor.</span></span>

<span data-ttu-id="7a7a4-181">请参阅本主题稍后介绍的[脚本示例](#scripting-example)。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-181">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

## <a name="scripting-example"></a><span data-ttu-id="7a7a4-182">脚本示例</span><span class="sxs-lookup"><span data-stu-id="7a7a4-182">Scripting Example</span></span>

```powershell
# This illustrates how you can use the length of a line to
# select the entire line and shows how you can make it lowercase.
# You must run this in the Console pane. It will not run in the Script pane.
# Begin by getting a variable that points to the editor.
$myEditor = $psISE.CurrentFile.Editor
# Clear the text in the current file editor.
$myEditor.Clear()

# Make sure the file has five lines of text.
$myEditor.InsertText("LINE1 `n")
$myEditor.InsertText("LINE2 `n")
$myEditor.InsertText("LINE3 `n")
$myEditor.InsertText("LINE4 `n")
$myEditor.InsertText("LINE5 `n")

# Use the GetLineLength method to get the length of the third line.
$endColumn = $myEditor.GetLineLength(3)
# Select the text in the first three lines.
$myEditor.Select(1, 1, 3, $endColumn + 1)
$selection = $myEditor.SelectedText
# Clear all the text in the editor.
$myEditor.Clear()
# Add the selected text back, but in lower case.
$myEditor.InsertText($selection.ToLower())
```

## <a name="see-also"></a><span data-ttu-id="7a7a4-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a7a4-183">See Also</span></span>

- [<span data-ttu-id="7a7a4-184">ISEFile 对象</span><span class="sxs-lookup"><span data-stu-id="7a7a4-184">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="7a7a4-185">PowerShellTab 对象</span><span class="sxs-lookup"><span data-stu-id="7a7a4-185">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="7a7a4-186">Windows PowerShell ISE 脚本对象模型的用途</span><span class="sxs-lookup"><span data-stu-id="7a7a4-186">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="7a7a4-187">ISE 对象模型层次结构</span><span class="sxs-lookup"><span data-stu-id="7a7a4-187">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
