---
description: 描述在 PowerShell 中使用单引号和双引号的规则。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 3a858039a9128235d1b920223ca0fcc3d0b0f6c0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200085"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="ce760-104">关于报价规则</span><span class="sxs-lookup"><span data-stu-id="ce760-104">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="ce760-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ce760-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ce760-106">描述在 PowerShell 中使用单引号和双引号的规则。</span><span class="sxs-lookup"><span data-stu-id="ce760-106">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ce760-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="ce760-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ce760-108">引号用于指定文本字符串。</span><span class="sxs-lookup"><span data-stu-id="ce760-108">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="ce760-109">可以用单引号将字符串括起来 (`'`) 或双引号 (`"`) 。</span><span class="sxs-lookup"><span data-stu-id="ce760-109">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="ce760-110">引号还用于创建此处字符串。</span><span class="sxs-lookup"><span data-stu-id="ce760-110">Quotation marks are also used to create a here-string.</span></span> <span data-ttu-id="ce760-111">此处-字符串是用单引号或双引号括起来的字符串，其中的引号按原义解释。</span><span class="sxs-lookup"><span data-stu-id="ce760-111">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="ce760-112">此处的字符串可以跨多个行。</span><span class="sxs-lookup"><span data-stu-id="ce760-112">A here-string can span multiple lines.</span></span> <span data-ttu-id="ce760-113">此处字符串中的所有行都被解释为字符串，即使它们没有用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ce760-113">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="ce760-114">在远程计算机的命令中，引号定义在远程计算机上运行的命令的各个部分。</span><span class="sxs-lookup"><span data-stu-id="ce760-114">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="ce760-115">在远程会话中，引号还确定命令中的变量是在本地计算机上还是在远程计算机上首先解释。</span><span class="sxs-lookup"><span data-stu-id="ce760-115">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

### <a name="single-and-double-quoted-strings"></a><span data-ttu-id="ce760-116">单引号和双引号字符串</span><span class="sxs-lookup"><span data-stu-id="ce760-116">SINGLE AND DOUBLE-QUOTED STRINGS</span></span>

<span data-ttu-id="ce760-117">用双引号将字符串括起来时 (用双引号引起来) ，在将 `$` 字符串传递到命令进行处理之前，将用变量的值替换前面带有美元符号 () 的变量名称。</span><span class="sxs-lookup"><span data-stu-id="ce760-117">When you enclose a string in double quotation marks (a double-quoted string), variable names that are preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="ce760-118">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="ce760-119">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="ce760-120">此外，在带双引号的字符串中，将计算表达式，并将结果插入字符串中。</span><span class="sxs-lookup"><span data-stu-id="ce760-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="ce760-121">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="ce760-122">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="ce760-123">如果将字符串括在单引号中 (单引号的字符串) ，则该字符串将与你键入的内容完全相同。</span><span class="sxs-lookup"><span data-stu-id="ce760-123">When you enclose a string in single-quotation marks (a single-quoted string), the string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="ce760-124">不执行任何替换。</span><span class="sxs-lookup"><span data-stu-id="ce760-124">No substitution is performed.</span></span> <span data-ttu-id="ce760-125">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-125">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="ce760-126">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-126">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="ce760-127">同样，不计算用单引号字符串括起来的表达式。</span><span class="sxs-lookup"><span data-stu-id="ce760-127">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="ce760-128">它们被解释为文本。</span><span class="sxs-lookup"><span data-stu-id="ce760-128">They are interpreted as literals.</span></span> <span data-ttu-id="ce760-129">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-129">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="ce760-130">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-130">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="ce760-131">若要防止用双引号替换变量值，请使用反撇号字符 (`` ` ``) # B2 ASCII 96) ，这是 PowerShell 转义符。</span><span class="sxs-lookup"><span data-stu-id="ce760-131">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="ce760-132">在下面的示例中，第一个 $i 变量之前的反撇号字符会阻止 PowerShell 将变量名称替换为其值。</span><span class="sxs-lookup"><span data-stu-id="ce760-132">In the following example, the backtick character that precedes the first $i variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="ce760-133">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-133">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="ce760-134">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-134">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="ce760-135">若要使双引号出现在字符串中，请将整个字符串用单引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ce760-135">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="ce760-136">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-136">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="ce760-137">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-137">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="ce760-138">还可以在带引号的字符串中包含单引号字符串。</span><span class="sxs-lookup"><span data-stu-id="ce760-138">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="ce760-139">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-139">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="ce760-140">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-140">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="ce760-141">或者，用双引号将引号括起来。</span><span class="sxs-lookup"><span data-stu-id="ce760-141">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="ce760-142">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-142">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="ce760-143">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-143">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="ce760-144">若要在单引号字符串中包含单引号，请使用第二个连续的单引号。</span><span class="sxs-lookup"><span data-stu-id="ce760-144">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="ce760-145">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-145">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="ce760-146">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-146">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="ce760-147">若要强制 PowerShell 按字面解释双引号，请使用反撇号字符。</span><span class="sxs-lookup"><span data-stu-id="ce760-147">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="ce760-148">这会阻止 PowerShell 将引号解释为字符串分隔符。</span><span class="sxs-lookup"><span data-stu-id="ce760-148">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="ce760-149">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-149">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="ce760-150">由于单引号字符串的内容按原义解释，因此，反撇号字符被视为文本字符并显示在输出中。</span><span class="sxs-lookup"><span data-stu-id="ce760-150">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

### <a name="here-strings"></a><span data-ttu-id="ce760-151">此处-字符串</span><span class="sxs-lookup"><span data-stu-id="ce760-151">HERE-STRINGS</span></span>

<span data-ttu-id="ce760-152">此处的引号规则与字符串略有不同。</span><span class="sxs-lookup"><span data-stu-id="ce760-152">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="ce760-153">此处-字符串是用单引号或双引号括起来的字符串，其中的引号按原义解释。</span><span class="sxs-lookup"><span data-stu-id="ce760-153">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="ce760-154">此处的字符串可以跨多个行。</span><span class="sxs-lookup"><span data-stu-id="ce760-154">A here-string can span multiple lines.</span></span> <span data-ttu-id="ce760-155">此处字符串中的所有行都被解释为字符串，即使它们没有用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ce760-155">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="ce760-156">与规则字符串一样，变量在此处用双引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ce760-156">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="ce760-157">在此处使用单引号的字符串中，变量的值不会被替换。</span><span class="sxs-lookup"><span data-stu-id="ce760-157">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="ce760-158">对于任何文本，您可以使用此处的字符串，但对于以下类型的文本特别有用：</span><span class="sxs-lookup"><span data-stu-id="ce760-158">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="ce760-159">包含文本引号的文本</span><span class="sxs-lookup"><span data-stu-id="ce760-159">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="ce760-160">多行文本，如 HTML 或 XML 中的文本</span><span class="sxs-lookup"><span data-stu-id="ce760-160">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="ce760-161">脚本或函数文档的帮助文本</span><span class="sxs-lookup"><span data-stu-id="ce760-161">The Help text for a script or function document</span></span>

<span data-ttu-id="ce760-162">此处的字符串可以采用以下两种格式之一，其中 `<Enter>` 表示按下 <kbd>enter</kbd> 键时添加的换行符或换行符。</span><span class="sxs-lookup"><span data-stu-id="ce760-162">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="ce760-163">双引号：</span><span class="sxs-lookup"><span data-stu-id="ce760-163">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="ce760-164">单引号：</span><span class="sxs-lookup"><span data-stu-id="ce760-164">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="ce760-165">无论采用哪种格式，右引号都必须是行中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="ce760-165">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="ce760-166">此处-字符串包含两个隐藏字符之间的所有文本。</span><span class="sxs-lookup"><span data-stu-id="ce760-166">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="ce760-167">在此处字符串中，所有引号都按原义解释。</span><span class="sxs-lookup"><span data-stu-id="ce760-167">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="ce760-168">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-168">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="ce760-169">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-169">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="ce760-170">使用此处字符串可简化在命令中使用字符串的情况。</span><span class="sxs-lookup"><span data-stu-id="ce760-170">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="ce760-171">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-171">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="ce760-172">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-172">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="ce760-173">在此处用单引号括起来的字符串中，变量按原义解释和重现。</span><span class="sxs-lookup"><span data-stu-id="ce760-173">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="ce760-174">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-174">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="ce760-175">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-175">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="ce760-176">在后面加双引号的字符串中，变量被替换为其值。</span><span class="sxs-lookup"><span data-stu-id="ce760-176">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="ce760-177">例如：</span><span class="sxs-lookup"><span data-stu-id="ce760-177">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="ce760-178">此命令的输出为：</span><span class="sxs-lookup"><span data-stu-id="ce760-178">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="ce760-179">此处-通常使用字符串将多个行分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="ce760-179">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="ce760-180">例如，下面的字符串将一个 XML 页分配给 $page 变量。</span><span class="sxs-lookup"><span data-stu-id="ce760-180">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

<span data-ttu-id="ce760-181">此处-对于向 cmdlet 进行的输入，字符串也是一种方便的格式，这种格式会 `ConvertFrom-StringData` 将字符串转换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="ce760-181">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="ce760-182">有关详细信息，请参阅 `ConvertFrom-StringData`。</span><span class="sxs-lookup"><span data-stu-id="ce760-182">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce760-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce760-183">SEE ALSO</span></span>

[<span data-ttu-id="ce760-184">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="ce760-184">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="ce760-185">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="ce760-185">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)