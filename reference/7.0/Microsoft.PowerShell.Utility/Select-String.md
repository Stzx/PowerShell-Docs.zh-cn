---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 7c614314eb13ea484f5a0a5ade36aabdd6afdf58
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "93199339"
---
# <span data-ttu-id="f6949-103">Select-String</span><span class="sxs-lookup"><span data-stu-id="f6949-103">Select-String</span></span>

## <span data-ttu-id="f6949-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f6949-104">SYNOPSIS</span></span>
<span data-ttu-id="f6949-105">在字符串和文件中查找文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-105">Finds text in strings and files.</span></span>

## <span data-ttu-id="f6949-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f6949-106">SYNTAX</span></span>

### <span data-ttu-id="f6949-107">File（默认值）</span><span class="sxs-lookup"><span data-stu-id="f6949-107">File (Default)</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="f6949-108">ObjectRaw</span><span class="sxs-lookup"><span data-stu-id="f6949-108">ObjectRaw</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="f6949-109">Object</span><span class="sxs-lookup"><span data-stu-id="f6949-109">Object</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="f6949-110">FileRaw</span><span class="sxs-lookup"><span data-stu-id="f6949-110">FileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="f6949-111">LiteralFileRaw</span><span class="sxs-lookup"><span data-stu-id="f6949-111">LiteralFileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="f6949-112">LiteralFile</span><span class="sxs-lookup"><span data-stu-id="f6949-112">LiteralFile</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="f6949-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f6949-113">DESCRIPTION</span></span>

<span data-ttu-id="f6949-114">`Select-String`Cmdlet 将搜索输入字符串和文件中的文本模式和文本模式。</span><span class="sxs-lookup"><span data-stu-id="f6949-114">The `Select-String` cmdlet searches for text and text patterns in input strings and files.</span></span> <span data-ttu-id="f6949-115">你可以使用 `Select-String` 类似于 UNIX 中的 **Grep** 或 Windows 中的 **findstr.exe** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-115">You can use `Select-String` similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="f6949-116">`Select-String` 基于文本行。</span><span class="sxs-lookup"><span data-stu-id="f6949-116">`Select-String` is based on lines of text.</span></span> <span data-ttu-id="f6949-117">默认情况下， `Select-String` 会在每一行中查找第一个匹配项，对于每个匹配项，它将在包含匹配项的行中显示文件名、行号和所有文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-117">By default, `Select-String` finds the first match in each line and, for each match, it displays the file name, line number, and all text in the line containing the match.</span></span> <span data-ttu-id="f6949-118">您可以直接 `Select-String` 查找每行的多个匹配项，在匹配前后显示文本，或显示一个布尔值 (True 或 False) 指示是否找到了匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-118">You can direct `Select-String` to find multiple matches per line, display text before and after the match, or display a Boolean value (True or False) that indicates whether a match is found.</span></span>

<span data-ttu-id="f6949-119">`Select-String` 使用正则表达式匹配，但它还可以执行匹配，以便在输入中搜索指定的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-119">`Select-String` uses regular expression matching, but it can also perform a match that searches the input for the text that you specify.</span></span>

<span data-ttu-id="f6949-120">`Select-String` 可以在每个输入文件中的第一个匹配项之后显示所有文本匹配项或停止。</span><span class="sxs-lookup"><span data-stu-id="f6949-120">`Select-String` can display all the text matches or stop after the first match in each input file.</span></span>
<span data-ttu-id="f6949-121">`Select-String` 可用于显示与指定模式不匹配的所有文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-121">`Select-String` can be used to display all text that doesn't match the specified pattern.</span></span>

<span data-ttu-id="f6949-122">您还可以指定 `Select-String` 应使用特定字符编码，例如搜索 Unicode 文本的文件时。</span><span class="sxs-lookup"><span data-stu-id="f6949-122">You can also specify that `Select-String` should expect a particular character encoding, such as when you're searching files of Unicode text.</span></span> <span data-ttu-id="f6949-123">`Select-String` 使用字节顺序标记 (BOM) 来检测文件的编码格式。</span><span class="sxs-lookup"><span data-stu-id="f6949-123">`Select-String` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="f6949-124">如果文件没有 BOM，则假定编码为 UTF8。</span><span class="sxs-lookup"><span data-stu-id="f6949-124">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="f6949-125">示例</span><span class="sxs-lookup"><span data-stu-id="f6949-125">EXAMPLES</span></span>

### <span data-ttu-id="f6949-126">示例1：查找区分大小写的匹配</span><span class="sxs-lookup"><span data-stu-id="f6949-126">Example 1: Find a case-sensitive match</span></span>

<span data-ttu-id="f6949-127">此示例对已向下管道发送到 cmdlet 的文本执行区分大小写的匹配 `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-127">This example does a case-sensitive match of the text that was sent down the pipeline to the `Select-String` cmdlet.</span></span>

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

<span data-ttu-id="f6949-128">文本字符串 **hello** 和 **hello** 会将管道发送到 `Select-String` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f6949-128">The text strings **Hello** and **HELLO** are sent down the pipeline to the `Select-String` cmdlet.</span></span>
<span data-ttu-id="f6949-129">`Select-String` 使用 **Pattern** 参数指定 **HELLO** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-129">`Select-String` uses the **Pattern** parameter to specify **HELLO** .</span></span> <span data-ttu-id="f6949-130">**CaseSensitive** 参数指定该事例必须仅与大写模式匹配。</span><span class="sxs-lookup"><span data-stu-id="f6949-130">The **CaseSensitive** parameter specifies that the case must match only the upper-case pattern.</span></span> <span data-ttu-id="f6949-131">**SimpleMatch** 是一个可选参数，它指定模式中的字符串不会解释为正则表达式。</span><span class="sxs-lookup"><span data-stu-id="f6949-131">**SimpleMatch** is an optional parameter and specifies that the string in the pattern isn't interpreted as a regular expression.</span></span>
<span data-ttu-id="f6949-132">`Select-String` 在 PowerShell 控制台中显示 " **HELLO** "。</span><span class="sxs-lookup"><span data-stu-id="f6949-132">`Select-String` displays **HELLO** in the PowerShell console.</span></span>

### <span data-ttu-id="f6949-133">示例2：查找文本文件中的匹配项</span><span class="sxs-lookup"><span data-stu-id="f6949-133">Example 2: Find matches in text files</span></span>

<span data-ttu-id="f6949-134">此命令 `.txt` 在当前目录中搜索文件扩展名为的所有文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-134">This command searches all files with the `.txt` file name extension in the current directory.</span></span> <span data-ttu-id="f6949-135">输出显示这些文件中包含指定字符串的行。</span><span class="sxs-lookup"><span data-stu-id="f6949-135">The output displays the lines in those files that include the specified string.</span></span>

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

<span data-ttu-id="f6949-136">在此示例中， `Get-Alias` 和 `Get-Command` 与 cmdlet 一起使用， `Out-File` 以在当前目录中创建两个文本文件， **Alias.txt** 和 **Command.txt** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-136">In this example, `Get-Alias` and `Get-Command` are used with the `Out-File` cmdlet to create two text files in the current directory, **Alias.txt** and **Command.txt** .</span></span>

<span data-ttu-id="f6949-137">`Select-String` 使用带有星号的 **Path** 参数 (`*`) 通配符，搜索当前目录中文件扩展名为的所有文件 `.txt` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-137">`Select-String` uses the **Path** parameter with the asterisk (`*`) wildcard to search all files in the current directory with the file name extension `.txt`.</span></span> <span data-ttu-id="f6949-138">**Pattern** 参数指定 **要匹配的** 文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-138">The **Pattern** parameter specifies the text to match **Get-** .</span></span> <span data-ttu-id="f6949-139">`Select-String` 在 PowerShell 控制台中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f6949-139">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="f6949-140">文件名和行号位于包含 **Pattern** 参数匹配项的每个内容行之前。</span><span class="sxs-lookup"><span data-stu-id="f6949-140">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="f6949-141">示例3：查找模式匹配</span><span class="sxs-lookup"><span data-stu-id="f6949-141">Example 3: Find a pattern match</span></span>

<span data-ttu-id="f6949-142">在此示例中，搜索多个文件以查找指定模式的匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-142">In this example, multiple files are searched to find matches for the specified pattern.</span></span> <span data-ttu-id="f6949-143">此模式使用正则表达式限定符。</span><span class="sxs-lookup"><span data-stu-id="f6949-143">The pattern uses a regular expression quantifier.</span></span> <span data-ttu-id="f6949-144">有关详细信息，请参阅 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f6949-144">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span></span>

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

<span data-ttu-id="f6949-145">`Select-String`Cmdlet 使用两个参数： **路径** 和 **模式** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-145">The `Select-String` cmdlet uses two parameters, **Path** and **Pattern** .</span></span> <span data-ttu-id="f6949-146">**Path** 参数使用 `$PSHOME` 指定 PowerShell 目录的变量。</span><span class="sxs-lookup"><span data-stu-id="f6949-146">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="f6949-147">路径的其余部分包括子目录 **en-us** ，并指定 `*.txt` 该目录中的每个文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-147">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="f6949-148">**Pattern** 参数指定匹配 `?` 每个文件中的问号 () 。</span><span class="sxs-lookup"><span data-stu-id="f6949-148">The **Pattern** parameter specifies to match a question mark (`?`) in each file.</span></span> <span data-ttu-id="f6949-149">反斜杠 (`\`) 用作转义字符，这是必需的，因为问号 (`?`) 是正则表达式限定符。</span><span class="sxs-lookup"><span data-stu-id="f6949-149">A backslash (`\`) is used as an escape character and is necessary because the question mark (`?`) is a regular expression quantifier.</span></span> <span data-ttu-id="f6949-150">`Select-String` 在 PowerShell 控制台中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f6949-150">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="f6949-151">文件名和行号位于包含 **Pattern** 参数匹配项的每个内容行之前。</span><span class="sxs-lookup"><span data-stu-id="f6949-151">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="f6949-152">示例4：在函数中使用 Select-String</span><span class="sxs-lookup"><span data-stu-id="f6949-152">Example 4: Use Select-String in a function</span></span>

<span data-ttu-id="f6949-153">此示例创建一个函数，用于在 PowerShell 帮助文件中搜索模式。</span><span class="sxs-lookup"><span data-stu-id="f6949-153">This example creates a function to search for a pattern in the PowerShell help files.</span></span> <span data-ttu-id="f6949-154">在此示例中，该函数仅在 PowerShell 会话中存在。</span><span class="sxs-lookup"><span data-stu-id="f6949-154">For this example, the function only exists in the PowerShell session.</span></span> <span data-ttu-id="f6949-155">关闭 PowerShell 会话后，将删除该函数。</span><span class="sxs-lookup"><span data-stu-id="f6949-155">When the PowerShell session is closed, the function is deleted.</span></span> <span data-ttu-id="f6949-156">有关详细信息，请参阅 [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md)。</span><span class="sxs-lookup"><span data-stu-id="f6949-156">For more information, see [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span></span>

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

<span data-ttu-id="f6949-157">在 PowerShell 命令行上创建该函数。</span><span class="sxs-lookup"><span data-stu-id="f6949-157">The function is created on the PowerShell command line.</span></span> <span data-ttu-id="f6949-158">该 `Function` 命令使用名称 **搜索-Help** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-158">The `Function` command uses the name **Search-Help** .</span></span> <span data-ttu-id="f6949-159">按 **enter** 开始向函数添加语句。</span><span class="sxs-lookup"><span data-stu-id="f6949-159">Press **Enter** to begin adding statements to the function.</span></span> <span data-ttu-id="f6949-160">在 `>>` 提示符下，添加每个语句并按下 **enter** ，如示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f6949-160">From the `>>` prompt, add each statement and press **Enter** as shown in the example.</span></span> <span data-ttu-id="f6949-161">添加右括号后，会返回到 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="f6949-161">After the closing bracket is added, you're returned to a PowerShell prompt.</span></span>

<span data-ttu-id="f6949-162">函数包含两个命令。</span><span class="sxs-lookup"><span data-stu-id="f6949-162">The function contains two commands.</span></span> <span data-ttu-id="f6949-163">`$PSHelp`变量存储 PowerShell 帮助文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f6949-163">The `$PSHelp` variable stores the path to the PowerShell help files.</span></span> <span data-ttu-id="f6949-164">`$PSHOME` 是具有用于指定目录中的每个文件的子目录 **en-us** 的 PowerShell 安装目录 `*.txt` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-164">`$PSHOME` is the PowerShell installation directory with the subdirectory **en-US** that specifies each `*.txt` file in the directory.</span></span>

<span data-ttu-id="f6949-165">`Select-String`函数中的命令使用 **路径** 和 **模式** 参数。</span><span class="sxs-lookup"><span data-stu-id="f6949-165">The `Select-String` command in the function uses the **Path** and **Pattern** parameters.</span></span> <span data-ttu-id="f6949-166">**Path** 参数使用 `$PSHelp` 变量来获取路径。</span><span class="sxs-lookup"><span data-stu-id="f6949-166">The **Path** parameter uses the `$PSHelp` variable to get the path.</span></span> <span data-ttu-id="f6949-167">**Pattern** 参数使用字符串 **About_** 作为搜索条件。</span><span class="sxs-lookup"><span data-stu-id="f6949-167">The **Pattern** parameter uses the string **About_** as the search criteria.</span></span>

<span data-ttu-id="f6949-168">若要运行此函数，请键入 `Search-Help` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-168">To run the function, type `Search-Help`.</span></span> <span data-ttu-id="f6949-169">此函数的 `Select-String` 命令显示 PowerShell 控制台中的输出。</span><span class="sxs-lookup"><span data-stu-id="f6949-169">The function's `Select-String` command displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="f6949-170">示例5：在 Windows 事件日志中搜索字符串</span><span class="sxs-lookup"><span data-stu-id="f6949-170">Example 5: Search for a string in a Windows event log</span></span>

<span data-ttu-id="f6949-171">此示例在 Windows 事件日志中搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="f6949-171">This example searches for a string in a Windows event log.</span></span> <span data-ttu-id="f6949-172">变量 `$_` 表示管道中的当前对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-172">The variable `$_` represents the current object in the pipeline.</span></span> <span data-ttu-id="f6949-173">有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="f6949-173">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

<span data-ttu-id="f6949-174">`Get-WinEvent`Cmdlet 使用 **LogName** 参数来指定应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="f6949-174">The `Get-WinEvent` cmdlet uses the **LogName** parameter to specify the Application log.</span></span> <span data-ttu-id="f6949-175">**MaxEvents** 参数获取日志中的最新事件50。</span><span class="sxs-lookup"><span data-stu-id="f6949-175">The **MaxEvents** parameter gets the 50 most recent events from the log.</span></span> <span data-ttu-id="f6949-176">日志内容存储在名为的变量中 `$Events` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-176">The log content is stored in the variable named `$Events`.</span></span>

<span data-ttu-id="f6949-177">该 `$Events` 变量将通过管道向下发送到 `Select-String` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f6949-177">The `$Events` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="f6949-178">`Select-String` 使用 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="f6949-178">`Select-String` uses the **InputObject** parameter.</span></span> <span data-ttu-id="f6949-179">`$_`变量表示当前对象， `message` 是事件的属性。</span><span class="sxs-lookup"><span data-stu-id="f6949-179">The `$_` variable represents the current object and `message` is a property of the event.</span></span> <span data-ttu-id="f6949-180">物种字符串的 **Pattern** 参数 **失败** ，并在中搜索匹配项 `$_.message` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-180">The **Pattern** parameter species the string **Failed** and searches for matches in `$_.message`.</span></span> <span data-ttu-id="f6949-181">`Select-String` 在 PowerShell 控制台中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f6949-181">`Select-String` displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="f6949-182">示例6：在子目录中查找字符串</span><span class="sxs-lookup"><span data-stu-id="f6949-182">Example 6: Find a string in subdirectories</span></span>

<span data-ttu-id="f6949-183">此示例在目录及其所有子目录中搜索特定的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="f6949-183">This example searches a directory and all of its subdirectories for a specific text string.</span></span>

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

<span data-ttu-id="f6949-184">`Get-ChildItem` 使用 **Path** 参数指定 **C:\Windows\System32 \*** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-184">`Get-ChildItem` uses the **Path** parameter to specify **C:\Windows\System32\*.txt** .</span></span> <span data-ttu-id="f6949-185">**递归** 参数包括子目录。</span><span class="sxs-lookup"><span data-stu-id="f6949-185">The **Recurse** parameter includes the subdirectories.</span></span> <span data-ttu-id="f6949-186">对象将向下发送到 `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-186">The objects are sent down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="f6949-187">`Select-String` 使用 **Pattern** 参数，并指定 **Microsoft** 的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6949-187">`Select-String` uses the **Pattern** parameter and specifies the string **Microsoft** .</span></span> <span data-ttu-id="f6949-188">**CaseSensitive** 参数用于匹配字符串的准确大小写。</span><span class="sxs-lookup"><span data-stu-id="f6949-188">The **CaseSensitive** parameter is used to match the exact case of the string.</span></span> <span data-ttu-id="f6949-189">`Select-String` 在 PowerShell 控制台中显示输出。</span><span class="sxs-lookup"><span data-stu-id="f6949-189">`Select-String` displays the output in the PowerShell console.</span></span>

> [!NOTE]
> <span data-ttu-id="f6949-190">根据你的权限，你可能会在输出中看到 " **拒绝访问** " 消息。</span><span class="sxs-lookup"><span data-stu-id="f6949-190">Dependent upon your permissions, you might see **Access denied** messages in the output.</span></span>

### <span data-ttu-id="f6949-191">示例7：查找与模式不匹配的字符串</span><span class="sxs-lookup"><span data-stu-id="f6949-191">Example 7: Find strings that do not match a pattern</span></span>

<span data-ttu-id="f6949-192">此示例演示如何排除与模式不匹配的数据行。</span><span class="sxs-lookup"><span data-stu-id="f6949-192">This example shows how to exclude lines of data that don't match a pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

<span data-ttu-id="f6949-193">`Get-Command`Cmdlet 将对象向下发送到， `Out-File` 以在当前目录中创建 **Command.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-193">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="f6949-194">`Select-String` 使用 **Path** 参数指定 **Command.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-194">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="f6949-195">**Pattern** 参数指定 **Get** 和 **Set** 作为搜索模式。</span><span class="sxs-lookup"><span data-stu-id="f6949-195">The **Pattern** parameter specifies **Get** and **Set** as the search pattern.</span></span> <span data-ttu-id="f6949-196">**NotMatch** 参数从结果中排除 **Get** 和 **Set** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-196">The **NotMatch** parameter excludes **Get** and **Set** from the results.</span></span>
<span data-ttu-id="f6949-197">`Select-String` 在 PowerShell 控制台中显示不包括 **Get** 或 **Set** 的输出。</span><span class="sxs-lookup"><span data-stu-id="f6949-197">`Select-String` displays the output in the PowerShell console that doesn't include **Get** or **Set** .</span></span>

### <span data-ttu-id="f6949-198">示例8：查找匹配项前后的行</span><span class="sxs-lookup"><span data-stu-id="f6949-198">Example 8: Find lines before and after a match</span></span>

<span data-ttu-id="f6949-199">此示例演示如何获取匹配模式前后的行。</span><span class="sxs-lookup"><span data-stu-id="f6949-199">This example shows how to get the lines before and after the matched pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

<span data-ttu-id="f6949-200">`Get-Command`Cmdlet 将对象向下发送到， `Out-File` 以在当前目录中创建 **Command.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-200">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="f6949-201">`Select-String` 使用 **Path** 参数指定 **Command.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-201">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="f6949-202">**Pattern** 参数将 " **获取计算机** " 指定为搜索模式。</span><span class="sxs-lookup"><span data-stu-id="f6949-202">The **Pattern** parameter specifies **Get-Computer** as the search pattern.</span></span> <span data-ttu-id="f6949-203">**上下文** 参数使用两个值（之前和之后），并在输出中用尖括号标记模式匹配 (`>`) 。</span><span class="sxs-lookup"><span data-stu-id="f6949-203">The **Context** parameter uses two values, before and after, and marks pattern matches in the output with an angle bracket (`>`).</span></span> <span data-ttu-id="f6949-204">**上下文** 参数输出第一个模式匹配之前的两行以及最后一个模式匹配后的三行。</span><span class="sxs-lookup"><span data-stu-id="f6949-204">The **Context** parameter outputs the two lines before the first pattern match and three lines after the last pattern match.</span></span>

### <span data-ttu-id="f6949-205">示例9：查找所有模式匹配项</span><span class="sxs-lookup"><span data-stu-id="f6949-205">Example 9: Find all pattern matches</span></span>

<span data-ttu-id="f6949-206">此示例演示 **AllMatches** 参数如何查找文本行中的每个模式匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-206">This example shows how the **AllMatches** parameter finds each pattern match in a line of text.</span></span> <span data-ttu-id="f6949-207">默认情况下， `Select-String` 仅在文本行中查找模式的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-207">By default, `Select-String` only finds the first occurrence of a pattern in a line of text.</span></span> <span data-ttu-id="f6949-208">此示例使用通过 cmdlet 找到的对象属性 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-208">This example uses object properties that are found with the `Get-Member` cmdlet.</span></span>

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

<span data-ttu-id="f6949-209">`Get-ChildItem`Cmdlet 使用 **Path** 参数。</span><span class="sxs-lookup"><span data-stu-id="f6949-209">The `Get-ChildItem` cmdlet uses the **Path** parameter.</span></span> <span data-ttu-id="f6949-210">**Path** 参数使用 `$PSHOME` 指定 PowerShell 目录的变量。</span><span class="sxs-lookup"><span data-stu-id="f6949-210">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="f6949-211">路径的其余部分包括子目录 **en-us** ，并指定 `*.txt` 该目录中的每个文件。</span><span class="sxs-lookup"><span data-stu-id="f6949-211">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="f6949-212">这些 `Get-ChildItem` 对象存储在变量中 `$A` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-212">The `Get-ChildItem` objects are stored in the `$A` variable.</span></span> <span data-ttu-id="f6949-213">该 `$A` 变量将通过管道向下发送到 `Select-String` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f6949-213">The `$A` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="f6949-214">`Select-String` 使用 **Pattern** 参数在每个文件中搜索字符串 **PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-214">`Select-String` uses the **Pattern** parameter to search each file for the string **PowerShell** .</span></span>

<span data-ttu-id="f6949-215">在 PowerShell 命令行中 `$A` 显示变量内容。</span><span class="sxs-lookup"><span data-stu-id="f6949-215">From the PowerShell command line, the `$A` variable contents are displayed.</span></span> <span data-ttu-id="f6949-216">有一行包含字符串 **PowerShell** 的两个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-216">There's a line that contains two occurrences of the string **PowerShell** .</span></span>

<span data-ttu-id="f6949-217">`$A.Matches`属性在每一行上列出第一次出现的模式 **PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-217">The `$A.Matches` property lists the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="f6949-218">`$A.Matches.Length`属性对每个行的第一个匹配 **PowerShell** 项进行计数。</span><span class="sxs-lookup"><span data-stu-id="f6949-218">The `$A.Matches.Length` property counts the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="f6949-219">`$B`变量使用相同的 `Get-ChildItem` 和 `Select-String` cmdlet，但会添加 **AllMatches** 参数。</span><span class="sxs-lookup"><span data-stu-id="f6949-219">The `$B` variable uses the same `Get-ChildItem` and `Select-String` cmdlets, but adds the **AllMatches** parameter.</span></span> <span data-ttu-id="f6949-220">**AllMatches** 在每一行上查找模式 **PowerShell** 的每个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-220">**AllMatches** finds each occurrence of the pattern **PowerShell** on each line.</span></span> <span data-ttu-id="f6949-221">和变量中存储的 `$A` 对象 `$B` 是相同的。</span><span class="sxs-lookup"><span data-stu-id="f6949-221">The objects stored in the `$A` and `$B` variables are identical.</span></span>

<span data-ttu-id="f6949-222">`$B.Matches.Length`属性会增加，因为对于每一行，都会对模式 **PowerShell** 的每个匹配项进行计数。</span><span class="sxs-lookup"><span data-stu-id="f6949-222">The `$B.Matches.Length` property increases because for each line, every occurrence of the pattern **PowerShell** is counted.</span></span>

## <span data-ttu-id="f6949-223">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f6949-223">PARAMETERS</span></span>

### <span data-ttu-id="f6949-224">-AllMatches</span><span class="sxs-lookup"><span data-stu-id="f6949-224">-AllMatches</span></span>

<span data-ttu-id="f6949-225">指示该 cmdlet 在每个文本行中搜索多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-225">Indicates that the cmdlet searches for more than one match in each line of text.</span></span> <span data-ttu-id="f6949-226">如果没有此参数， `Select-String` 则仅查找每个文本行中的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-226">Without this parameter, `Select-String` finds only the first match in each line of text.</span></span>

<span data-ttu-id="f6949-227">当 `Select-String` 在一个文本行中找到多个匹配项时，它仍然只会为该行发出一个 **MatchInfo** 对象，但 **该** 对象的 match 属性包含所有匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-227">When `Select-String` finds more than one match in a line of text, it still emits only one **MatchInfo** object for the line, but the **Matches** property of the object contains all the matches.</span></span>

> [!NOTE]
> <span data-ttu-id="f6949-228">将此参数与 **SimpleMatch** 参数结合使用时，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="f6949-228">This parameter is ignored when used in combination with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="f6949-229">如果希望返回所有匹配项并且要搜索的模式包含正则表达式字符，则必须对这些字符进行转义，而不是使用 **SimpleMatch** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-229">If you wish to return all matches and the pattern that you are searching for contains regular expression characters, you must escape those characters rather than using **SimpleMatch** .</span></span> <span data-ttu-id="f6949-230">有关转义正则表达式的详细信息，请参阅 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) 。</span><span class="sxs-lookup"><span data-stu-id="f6949-230">See [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) for more information about escaping regular expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-231">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="f6949-231">-CaseSensitive</span></span>

<span data-ttu-id="f6949-232">指示 cmdlet 匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f6949-232">Indicates that the cmdlet matches are case-sensitive.</span></span> <span data-ttu-id="f6949-233">默认情况下，匹配不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f6949-233">By default, matches aren't case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-234">-Context</span><span class="sxs-lookup"><span data-stu-id="f6949-234">-Context</span></span>

<span data-ttu-id="f6949-235">捕获与模式匹配的行前后的指定行数。</span><span class="sxs-lookup"><span data-stu-id="f6949-235">Captures the specified number of lines before and after the line that matches the pattern.</span></span>

<span data-ttu-id="f6949-236">如果你输入一个数字作为此参数的值，则该数字将确定捕获的匹配项前后的行数。</span><span class="sxs-lookup"><span data-stu-id="f6949-236">If you enter one number as the value of this parameter, that number determines the number of lines captured before and after the match.</span></span> <span data-ttu-id="f6949-237">如果你输入两个数字作为此参数的值，则第一个数字将确定该匹配项前面的行数，第二个数字将确定该匹配项后面的行数。</span><span class="sxs-lookup"><span data-stu-id="f6949-237">If you enter two numbers as the value, the first number determines the number of lines before the match and the second number determines the number of lines after the match.</span></span> <span data-ttu-id="f6949-238">例如，`-Context 2,3`。</span><span class="sxs-lookup"><span data-stu-id="f6949-238">For example, `-Context 2,3`.</span></span>

<span data-ttu-id="f6949-239">在默认显示中，具有匹配项的行由右尖括号指示 (`>`) 显示的第一列中 (ASCII 62) 。</span><span class="sxs-lookup"><span data-stu-id="f6949-239">In the default display, lines with a match are indicated by a right angle bracket (`>`) (ASCII 62) in the first column of the display.</span></span> <span data-ttu-id="f6949-240">无标记行是上下文。</span><span class="sxs-lookup"><span data-stu-id="f6949-240">Unmarked lines are the context.</span></span>

<span data-ttu-id="f6949-241">**上下文** 参数不会更改所生成的对象的数目 `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-241">The **Context** parameter doesn't change the number of objects generated by `Select-String`.</span></span>
<span data-ttu-id="f6949-242">`Select-String` 为每个匹配项生成一个 [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-242">`Select-String` generates one [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) object for each match.</span></span> <span data-ttu-id="f6949-243">上下文在对象的 **context** 属性中存储为字符串数组。</span><span class="sxs-lookup"><span data-stu-id="f6949-243">The context is stored as an array of strings in the **Context** property of the object.</span></span>

<span data-ttu-id="f6949-244">将命令的输出 `Select-String` 发送到另一个 `Select-String` 命令时，接收命令只会搜索匹配行中的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-244">When the output of a `Select-String` command is sent down the pipeline to another `Select-String` command, the receiving command searches only the text in the matched line.</span></span> <span data-ttu-id="f6949-245">匹配的行是 **MatchInfo** 对象的 **line** 属性的值，而不是上下文行中的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-245">The matched line is the value of the **Line** property of the **MatchInfo** object, not the text in the context lines.</span></span> <span data-ttu-id="f6949-246">因此， **上下文** 参数对接收 `Select-String` 命令无效。</span><span class="sxs-lookup"><span data-stu-id="f6949-246">As a result, the **Context** parameter isn't valid on the receiving `Select-String` command.</span></span>

<span data-ttu-id="f6949-247">当上下文包含匹配项时，每个匹配项的 **MatchInfo** 对象都将包括所有的上下文行，但重叠的行仅在显示中出现一次。</span><span class="sxs-lookup"><span data-stu-id="f6949-247">When the context includes a match, the **MatchInfo** object for each match includes all the context lines, but the overlapping lines appear only once in the display.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-248">-Culture</span><span class="sxs-lookup"><span data-stu-id="f6949-248">-Culture</span></span>

<span data-ttu-id="f6949-249">指定与指定模式匹配的区域性名称。</span><span class="sxs-lookup"><span data-stu-id="f6949-249">Specifies a culture name to match the specified pattern.</span></span> <span data-ttu-id="f6949-250">**Culture** 参数必须与 **SimpleMatch** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="f6949-250">The **Culture** parameter must be used with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="f6949-251">默认行为使用当前 PowerShell 运行空间的区域性 (会话) 。</span><span class="sxs-lookup"><span data-stu-id="f6949-251">The default behavior uses the culture of the current PowerShell runspace (session).</span></span>

<span data-ttu-id="f6949-252">若要获取所有受支持的区域性的列表，请使用 `Get-Culture -ListAvailable` 命令。</span><span class="sxs-lookup"><span data-stu-id="f6949-252">To get a list of all supported cultures, use `Get-Culture -ListAvailable` command.</span></span>

<span data-ttu-id="f6949-253">此外，此参数还接受以下参数：</span><span class="sxs-lookup"><span data-stu-id="f6949-253">In addition, this parameter accepts the following arguments:</span></span>

- <span data-ttu-id="f6949-254">CurrentCulture，这是默认值;</span><span class="sxs-lookup"><span data-stu-id="f6949-254">CurrentCulture, that is default;</span></span>
- <span data-ttu-id="f6949-255">序数，是非语言二进制比较;</span><span class="sxs-lookup"><span data-stu-id="f6949-255">Ordinal, that is non-linguistic binary comparison;</span></span>
- <span data-ttu-id="f6949-256">固定，这是独立于区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="f6949-256">Invariant, that is culture independent comparison.</span></span>

<span data-ttu-id="f6949-257">通过 `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` 命令，可以获得最快的二进制比较。</span><span class="sxs-lookup"><span data-stu-id="f6949-257">With `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` command you gets fastest binary comparison.</span></span>

<span data-ttu-id="f6949-258">**Culture** 参数使用 tab 自动补全在指定可用区域性的参数列表中滚动。</span><span class="sxs-lookup"><span data-stu-id="f6949-258">The **Culture** parameter uses tab completion to scroll through the list of arguments that specify the available cultures.</span></span> <span data-ttu-id="f6949-259">若要列出所有可用参数，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="f6949-259">To list all available arguments, use the following command:</span></span>

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

<span data-ttu-id="f6949-260">有关 .NET CultureInfo.Name 属性的详细信息，请参阅 [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name)。</span><span class="sxs-lookup"><span data-stu-id="f6949-260">For more information about .NET CultureInfo.Name property, see [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span></span>

<span data-ttu-id="f6949-261">**Culture** 参数是在 PowerShell 7 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f6949-261">The **Culture** parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-262">-Encoding</span><span class="sxs-lookup"><span data-stu-id="f6949-262">-Encoding</span></span>

<span data-ttu-id="f6949-263">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="f6949-263">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="f6949-264">默认值是 `utf8NoBOM`。</span><span class="sxs-lookup"><span data-stu-id="f6949-264">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="f6949-265">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="f6949-265">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f6949-266">`ascii`：使用 ASCII (7 位) 字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-266">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="f6949-267">`bigendianunicode`：使用大字节序字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-267">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="f6949-268">`oem`：使用 MS-DOS 和控制台程序的默认编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-268">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="f6949-269">`unicode`：使用小 endian 字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-269">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="f6949-270">`utf7`：以 UTF-7 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-270">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="f6949-271">`utf8`：以 UTF-8 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-271">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="f6949-272">`utf8BOM`：以 UTF-8 格式编码 (BOM) </span><span class="sxs-lookup"><span data-stu-id="f6949-272">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="f6949-273">`utf8NoBOM`：以 UTF-8 格式编码，而不包含字节顺序标记 (BOM) </span><span class="sxs-lookup"><span data-stu-id="f6949-273">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="f6949-274">`utf32`：以32格式编码。</span><span class="sxs-lookup"><span data-stu-id="f6949-274">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="f6949-275">从 PowerShell 6.2 开始， **Encoding** 参数还允许已注册代码页的数字 id (如 `-Encoding 1251` (如) 所注册代码页的) 或字符串名称 `-Encoding "windows-1251"` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-275">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="f6949-276">有关详细信息，请参阅 .NET 文档中的[编码。](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)</span><span class="sxs-lookup"><span data-stu-id="f6949-276">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-277">-Exclude</span><span class="sxs-lookup"><span data-stu-id="f6949-277">-Exclude</span></span>

<span data-ttu-id="f6949-278">排除指定项。</span><span class="sxs-lookup"><span data-stu-id="f6949-278">Exclude the specified items.</span></span> <span data-ttu-id="f6949-279">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="f6949-279">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f6949-280">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="f6949-280">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f6949-281">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="f6949-281">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f6949-282">-Include</span><span class="sxs-lookup"><span data-stu-id="f6949-282">-Include</span></span>

<span data-ttu-id="f6949-283">包括指定项。</span><span class="sxs-lookup"><span data-stu-id="f6949-283">Includes the specified items.</span></span> <span data-ttu-id="f6949-284">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="f6949-284">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f6949-285">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="f6949-285">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f6949-286">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="f6949-286">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f6949-287">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f6949-287">-InputObject</span></span>

<span data-ttu-id="f6949-288">指定要搜索的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-288">Specifies the text to be searched.</span></span> <span data-ttu-id="f6949-289">输入一个包含该文本的变量，或键入可获取该文本的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="f6949-289">Enter a variable that contains the text, or type a command or expression that gets the text.</span></span>

<span data-ttu-id="f6949-290">使用 **InputObject** 参数不同于将字符串向下发送到 `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-290">Using the **InputObject** parameter isn't the same as sending strings down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="f6949-291">当你将多个字符串传递给 `Select-String` cmdlet 时，它会在每个字符串中搜索指定的文本，并返回包含搜索文本的每个字符串。</span><span class="sxs-lookup"><span data-stu-id="f6949-291">When you pipe more than one string to the `Select-String` cmdlet, it searches for the specified text in each string and returns each string that contains the search text.</span></span>

<span data-ttu-id="f6949-292">当使用 **InputObject** 参数提交字符串集合时，会将 `Select-String` 该集合视为单个组合字符串。</span><span class="sxs-lookup"><span data-stu-id="f6949-292">When you use the **InputObject** parameter to submit a collection of strings, `Select-String` treats the collection as a single combined string.</span></span> <span data-ttu-id="f6949-293">`Select-String` 如果在任何字符串中找到搜索文本，则将这些字符串作为单元返回。</span><span class="sxs-lookup"><span data-stu-id="f6949-293">`Select-String` returns the strings as a unit if it finds the search text in any string.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ObjectRaw, Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-294">-List</span><span class="sxs-lookup"><span data-stu-id="f6949-294">-List</span></span>

<span data-ttu-id="f6949-295">只从每个输入文件返回匹配文本的第一个实例。</span><span class="sxs-lookup"><span data-stu-id="f6949-295">Only the first instance of matching text is returned from each input file.</span></span> <span data-ttu-id="f6949-296">这是检索具有与正则表达式匹配的内容的文件列表的最有效方法。</span><span class="sxs-lookup"><span data-stu-id="f6949-296">This is the most efficient way to retrieve a list of files that have contents matching the regular expression.</span></span>

<span data-ttu-id="f6949-297">默认情况下，将 `Select-String` 为它找到的每个匹配项返回一个 **MatchInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-297">By default, `Select-String` returns a **MatchInfo** object for each match it finds.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-298">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f6949-298">-LiteralPath</span></span>

<span data-ttu-id="f6949-299">指定要搜索的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f6949-299">Specifies the path to the files to be searched.</span></span> <span data-ttu-id="f6949-300">**LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="f6949-300">The value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="f6949-301">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="f6949-301">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f6949-302">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="f6949-302">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f6949-303">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="f6949-303">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="f6949-304">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="f6949-304">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-305">-NoEmphasis</span><span class="sxs-lookup"><span data-stu-id="f6949-305">-NoEmphasis</span></span>

<span data-ttu-id="f6949-306">默认情况下， `Select-String` 将突出显示与你使用 **pattern** 参数搜索的模式匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6949-306">By default, `Select-String` highlights the string that matches the pattern you searched for with the **Pattern** parameter.</span></span> <span data-ttu-id="f6949-307">**NoEmphasis** 参数禁用突出显示。</span><span class="sxs-lookup"><span data-stu-id="f6949-307">The **NoEmphasis** parameter disables the highlighting.</span></span>

<span data-ttu-id="f6949-308">强调基于 PowerShell 背景和文本颜色使用负颜色。</span><span class="sxs-lookup"><span data-stu-id="f6949-308">The emphasis uses negative colors based on your PowerShell background and text colors.</span></span> <span data-ttu-id="f6949-309">例如，如果您的 PowerShell 颜色是带有白色文本的黑色背景。</span><span class="sxs-lookup"><span data-stu-id="f6949-309">For example, if your PowerShell colors are a black background with white text.</span></span> <span data-ttu-id="f6949-310">强调是带有黑色文本的白色背景。</span><span class="sxs-lookup"><span data-stu-id="f6949-310">The emphasis is a white background with black text.</span></span>

<span data-ttu-id="f6949-311">此参数是在 PowerShell 7 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f6949-311">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-312">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="f6949-312">-NotMatch</span></span>

<span data-ttu-id="f6949-313">**NotMatch** 参数查找与指定模式不匹配的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-313">The **NotMatch** parameter finds text that doesn't match the specified pattern.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-314">-Path</span><span class="sxs-lookup"><span data-stu-id="f6949-314">-Path</span></span>

<span data-ttu-id="f6949-315">指定要搜索的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f6949-315">Specifies the path to the files to search.</span></span> <span data-ttu-id="f6949-316">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="f6949-316">Wildcards are permitted.</span></span> <span data-ttu-id="f6949-317">默认位置为本地目录。</span><span class="sxs-lookup"><span data-stu-id="f6949-317">The default location is the local directory.</span></span>

<span data-ttu-id="f6949-318">指定目录中的文件，例如 `log1.txt` 、 `*.doc` 或 `*.*` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-318">Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`.</span></span> <span data-ttu-id="f6949-319">如果仅指定一个目录，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="f6949-319">If you specify only a directory, the command fails.</span></span>

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="f6949-320">-Pattern</span><span class="sxs-lookup"><span data-stu-id="f6949-320">-Pattern</span></span>

<span data-ttu-id="f6949-321">指定要在每一行上查找的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-321">Specifies the text to find on each line.</span></span> <span data-ttu-id="f6949-322">模式值被视为正则表达式。</span><span class="sxs-lookup"><span data-stu-id="f6949-322">The pattern value is treated as a regular expression.</span></span>

<span data-ttu-id="f6949-323">若要了解正则表达式，请参阅 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f6949-323">To learn about regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-324">-Quiet</span><span class="sxs-lookup"><span data-stu-id="f6949-324">-Quiet</span></span>

<span data-ttu-id="f6949-325">指示该 cmdlet 将返回一个布尔值， (True 或 False) 而不是 **MatchInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-325">Indicates that the cmdlet returns a Boolean value (True or False), instead of a **MatchInfo** object.</span></span> <span data-ttu-id="f6949-326">如果找到该模式，则该值为 True;否则，该值为 False。</span><span class="sxs-lookup"><span data-stu-id="f6949-326">The value is True if the pattern is found; otherwise the value is False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-327">-Raw</span><span class="sxs-lookup"><span data-stu-id="f6949-327">-Raw</span></span>

<span data-ttu-id="f6949-328">使 cmdlet 仅输出匹配的字符串，而不是 **MatchInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-328">Causes the cmdlet to output only the matching strings, rather than **MatchInfo** objects.</span></span> <span data-ttu-id="f6949-329">这是导致最类似于 Unix **grep** 或 Windows **findstr.exe** 命令的行为。</span><span class="sxs-lookup"><span data-stu-id="f6949-329">This is the results in behavior that's the most similar to the Unix **grep** or Windows **findstr.exe** commands.</span></span>

<span data-ttu-id="f6949-330">此参数是在 PowerShell 7 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f6949-330">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-331">-SimpleMatch</span><span class="sxs-lookup"><span data-stu-id="f6949-331">-SimpleMatch</span></span>

<span data-ttu-id="f6949-332">指示该 cmdlet 使用简单匹配，而不是正则表达式匹配。</span><span class="sxs-lookup"><span data-stu-id="f6949-332">Indicates that the cmdlet uses a simple match rather than a regular expression match.</span></span> <span data-ttu-id="f6949-333">在简单匹配中，在 `Select-String` 输入中搜索 **Pattern** 参数中的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-333">In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter.</span></span> <span data-ttu-id="f6949-334">它不会将 **Pattern** 参数的值解释为正则表达式语句。</span><span class="sxs-lookup"><span data-stu-id="f6949-334">It doesn't interpret the value of the **Pattern** parameter as a regular expression statement.</span></span>

<span data-ttu-id="f6949-335">此外，在使用 **SimpleMatch** 时，返回的 **MatchInfo** 对象的 " **匹配** " 属性为空。</span><span class="sxs-lookup"><span data-stu-id="f6949-335">Also, when **SimpleMatch** is used, the **Matches** property of the **MatchInfo** object returned is empty.</span></span>

> [!NOTE]
> <span data-ttu-id="f6949-336">将此参数与 **AllMatches** 参数一起使用时，将忽略 **AllMatches** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-336">When this parameter is used with the **AllMatches** parameter, the **AllMatches** is ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6949-337">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f6949-337">CommonParameters</span></span>

<span data-ttu-id="f6949-338">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f6949-338">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f6949-339">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f6949-339">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f6949-340">输入</span><span class="sxs-lookup"><span data-stu-id="f6949-340">INPUTS</span></span>

### <span data-ttu-id="f6949-341">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="f6949-341">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f6949-342">可以通过管道将具有 **ToString** 方法的任何对象传递给 `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-342">You can pipe any object that has a **ToString** method to `Select-String`.</span></span>

## <span data-ttu-id="f6949-343">输出</span><span class="sxs-lookup"><span data-stu-id="f6949-343">OUTPUTS</span></span>

### <span data-ttu-id="f6949-344">MatchInfo，System.string，System.string，系统字符串</span><span class="sxs-lookup"><span data-stu-id="f6949-344">Microsoft.PowerShell.Commands.MatchInfo, System.Boolean, System.String</span></span>

<span data-ttu-id="f6949-345">默认情况下，输出为一组 **MatchInfo** 对象，每个对象对应一个找到的匹配项。</span><span class="sxs-lookup"><span data-stu-id="f6949-345">By default, the output is a set of **MatchInfo** objects with one for each match found.</span></span> <span data-ttu-id="f6949-346">如果使用 **Quiet** 参数，则输出将是一个指示是否找到该模式的 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="f6949-346">If you use the **Quiet** parameter, the output is a **Boolean** value indicating whether the pattern was found.</span></span>
<span data-ttu-id="f6949-347">如果使用 **原始** 参数，则输出将是一组与模式匹配的 **字符串** 对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-347">If you use the **Raw** parameter, the output is a set of **String** objects that match the pattern.</span></span>

## <span data-ttu-id="f6949-348">注释</span><span class="sxs-lookup"><span data-stu-id="f6949-348">NOTES</span></span>

<span data-ttu-id="f6949-349">`Select-String` 类似于 UNIX 中的 **grep** 或 Windows 中的 **findstr.exe** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-349">`Select-String` is similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="f6949-350">Cmdlet 的 **sls** 别名 `Select-String` 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f6949-350">The **sls** alias for the `Select-String` cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="f6949-351">根据 [PowerShell 命令的批准的动词](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands)，cmdlet 的官方别名 `Select-*` 为，而 `sc` 不是 `sl` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-351">According to [Approved Verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), the official alias prefix for `Select-*` cmdlets is `sc`, not `sl`.</span></span> <span data-ttu-id="f6949-352">因此，的正确别名 `Select-String` 应为 `scs` ，而不是 `sls` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-352">Therefore, the proper alias for `Select-String` should be `scs`, not `sls`.</span></span> <span data-ttu-id="f6949-353">这是此规则的例外情况。</span><span class="sxs-lookup"><span data-stu-id="f6949-353">This is an exception to this rule.</span></span>

<span data-ttu-id="f6949-354">若要使用 `Select-String` ，请键入要查找为 **Pattern** 参数值的文本。</span><span class="sxs-lookup"><span data-stu-id="f6949-354">To use `Select-String`, type the text that you want to find as the value of the **Pattern** parameter.</span></span> <span data-ttu-id="f6949-355">若要指定要搜索的文本，请使用以下条件：</span><span class="sxs-lookup"><span data-stu-id="f6949-355">To specify the text to be searched, use the following criteria:</span></span>

- <span data-ttu-id="f6949-356">在带引号的字符串中键入文本，然后将其传递给 `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="f6949-356">Type the text in a quoted string, and then pipe it to `Select-String`.</span></span>
- <span data-ttu-id="f6949-357">将文本字符串存储在变量中，然后将该变量指定为 **InputObject** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="f6949-357">Store a text string in a variable, and then specify the variable as the value of the **InputObject** parameter.</span></span>
- <span data-ttu-id="f6949-358">如果文本存储在文件中，请使用 **path** 参数指定文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f6949-358">If the text is stored in files, use the **Path** parameter to specify the path to the files.</span></span>

<span data-ttu-id="f6949-359">默认情况下，会将 `Select-String` **Pattern** 参数的值解释为正则表达式。</span><span class="sxs-lookup"><span data-stu-id="f6949-359">By default, `Select-String` interprets the value of the **Pattern** parameter as a regular expression.</span></span> <span data-ttu-id="f6949-360">有关详细信息，请参阅 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f6949-360">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span> <span data-ttu-id="f6949-361">可以使用 **SimpleMatch** 参数重写正则表达式匹配。</span><span class="sxs-lookup"><span data-stu-id="f6949-361">You can use the **SimpleMatch** parameter to override the regular expression matching.</span></span> <span data-ttu-id="f6949-362">**SimpleMatch** 参数在输入中查找 **Pattern** 参数值的实例。</span><span class="sxs-lookup"><span data-stu-id="f6949-362">The **SimpleMatch** parameter finds instances of the value of the **Pattern** parameter in the input.</span></span>

<span data-ttu-id="f6949-363">的默认输出 `Select-String` 是一个 **MatchInfo** 对象，其中包括有关匹配项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6949-363">The default output of `Select-String` is a **MatchInfo** object, which includes detailed information about the matches.</span></span> <span data-ttu-id="f6949-364">当你在文件中搜索文本时，该对象中的信息非常有用，因为 **MatchInfo** 对象具有 **Filename** 和 **Line** 等属性。</span><span class="sxs-lookup"><span data-stu-id="f6949-364">The information in the object is useful when you're searching for text in files, because **MatchInfo** objects have properties such as **Filename** and **Line** .</span></span> <span data-ttu-id="f6949-365">如果输入不是来自文件，则这些参数的值为 **InputStream** 。</span><span class="sxs-lookup"><span data-stu-id="f6949-365">When the input isn't from the file, the value of these parameters is **InputStream** .</span></span>

<span data-ttu-id="f6949-366">如果不需要 **MatchInfo** 对象中的信息，请使用 **Quiet** 参数。</span><span class="sxs-lookup"><span data-stu-id="f6949-366">If you don't need the information in the **MatchInfo** object, use the **Quiet** parameter.</span></span> <span data-ttu-id="f6949-367">**Quiet** 参数将返回一个布尔值 (True 或 False) 以指示它是否找到匹配项，而不是 **MatchInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="f6949-367">The **Quiet** parameter returns a Boolean value (True or False) to indicate whether it found a match, instead of a **MatchInfo** object.</span></span>

<span data-ttu-id="f6949-368">匹配短语时，将 `Select-String` 使用为系统设置的当前区域性。</span><span class="sxs-lookup"><span data-stu-id="f6949-368">When matching phrases, `Select-String` uses the current culture that is set for the system.</span></span> <span data-ttu-id="f6949-369">若要查找当前区域性，请使用 `Get-Culture` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f6949-369">To find the current culture, use the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="f6949-370">若要查找 **MatchInfo** 对象的属性，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f6949-370">To find the properties of a **MatchInfo** object, type the following command:</span></span>

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## <span data-ttu-id="f6949-371">相关链接</span><span class="sxs-lookup"><span data-stu-id="f6949-371">RELATED LINKS</span></span>

[<span data-ttu-id="f6949-372">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="f6949-372">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="f6949-373">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="f6949-373">about_Comparison_Operators</span></span>](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[<span data-ttu-id="f6949-374">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f6949-374">about_Functions</span></span>](../Microsoft.PowerShell.Core/About/about_Functions.md)

[<span data-ttu-id="f6949-375">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="f6949-375">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="f6949-376">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="f6949-376">about_Regular_Expressions</span></span>](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[<span data-ttu-id="f6949-377">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="f6949-377">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="f6949-378">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="f6949-378">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="f6949-379">Get-Command</span><span class="sxs-lookup"><span data-stu-id="f6949-379">Get-Command</span></span>](../Microsoft.PowerShell.Core/Get-Command.md)

[<span data-ttu-id="f6949-380">Get-Member</span><span class="sxs-lookup"><span data-stu-id="f6949-380">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="f6949-381">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="f6949-381">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="f6949-382">Out-File</span><span class="sxs-lookup"><span data-stu-id="f6949-382">Out-File</span></span>](Out-File.md)
