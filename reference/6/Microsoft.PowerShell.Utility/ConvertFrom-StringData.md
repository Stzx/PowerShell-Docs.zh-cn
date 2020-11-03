---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: 8ffb7a33bb1b4b5409c48445b88a8eb58f9b93b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198638"
---
# <span data-ttu-id="61e34-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="61e34-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="61e34-104">摘要</span><span class="sxs-lookup"><span data-stu-id="61e34-104">SYNOPSIS</span></span>
<span data-ttu-id="61e34-105">将包含一个或多个键-值对的字符串转换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="61e34-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="61e34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61e34-106">SYNTAX</span></span>

### <span data-ttu-id="61e34-107">全部</span><span class="sxs-lookup"><span data-stu-id="61e34-107">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [<CommonParameters>]
```

## <span data-ttu-id="61e34-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61e34-108">DESCRIPTION</span></span>

<span data-ttu-id="61e34-109">`ConvertFrom-StringData`Cmdlet 将包含一个或多个键和值对的字符串转换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="61e34-109">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="61e34-110">由于每个键-值对都必须位于单独的行上，因此，通常使用字符串作为输入格式。</span><span class="sxs-lookup"><span data-stu-id="61e34-110">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="61e34-111">默认情况下，必须将该 **密钥** 与 **值** 之间用等号分隔 (`=`) 字符。</span><span class="sxs-lookup"><span data-stu-id="61e34-111">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="61e34-112">该 `ConvertFrom-StringData` cmdlet 被视为可在脚本或函数的部分中使用的安全 cmdlet `DATA` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-112">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="61e34-113">当在节中使用时 `DATA` ，字符串的内容必须符合数据部分的规则。</span><span class="sxs-lookup"><span data-stu-id="61e34-113">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="61e34-114">有关详细信息，请参阅 [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md)。</span><span class="sxs-lookup"><span data-stu-id="61e34-114">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="61e34-115">`ConvertFrom-StringData` 支持传统机器翻译工具允许的转义字符序列。</span><span class="sxs-lookup"><span data-stu-id="61e34-115">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="61e34-116">也就是说，该 cmdlet 可以 `\` 使用 [Unescape 方法](/dotnet/api/system.text.regularexpressions.regex.unescape)解释字符串数据中) 转义符 (反斜杠，而不是使用 PowerShell 反撇号字符 (\`) 通常会在脚本中发出行的结尾。</span><span class="sxs-lookup"><span data-stu-id="61e34-116">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="61e34-117">在 here-string 中，反撇号字符无效。</span><span class="sxs-lookup"><span data-stu-id="61e34-117">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="61e34-118">还可以通过使用前面的反斜杠对其进行转义，使结果保留在结果中，如下所示： `\\` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-118">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="61e34-119">未转义的反斜杠字符（例如那些通常用在文件路径中的反斜杠字符）可以在结果中呈现为非法的转义序列。</span><span class="sxs-lookup"><span data-stu-id="61e34-119">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

## <span data-ttu-id="61e34-120">示例</span><span class="sxs-lookup"><span data-stu-id="61e34-120">EXAMPLES</span></span>

### <span data-ttu-id="61e34-121">示例1：将此处的单引用字符串转换为哈希表</span><span class="sxs-lookup"><span data-stu-id="61e34-121">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="61e34-122">此示例将用户消息的单引用字符串转换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="61e34-122">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="61e34-123">在带单引号的字符串中，不能使用变量和无法计算的表达式来代替其值。</span><span class="sxs-lookup"><span data-stu-id="61e34-123">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="61e34-124">`ConvertFrom-StringData`Cmdlet 将变量中的值转换 `$Here` 为哈希表。</span><span class="sxs-lookup"><span data-stu-id="61e34-124">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### <span data-ttu-id="61e34-125">示例2：转换包含注释的字符串</span><span class="sxs-lookup"><span data-stu-id="61e34-125">Example 2: Convert a here-string containing a comment</span></span>

<span data-ttu-id="61e34-126">此示例将包含注释和多个键/值对的字符串转换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="61e34-126">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

<span data-ttu-id="61e34-127">**Convertfrom-stringdata** 参数的值是一个字符串，而不是包含此字符串的变量。</span><span class="sxs-lookup"><span data-stu-id="61e34-127">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="61e34-128">两种格式都有效。</span><span class="sxs-lookup"><span data-stu-id="61e34-128">Either format is valid.</span></span> <span data-ttu-id="61e34-129">here-string 包括有关某字符串的注释。</span><span class="sxs-lookup"><span data-stu-id="61e34-129">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="61e34-130">`ConvertFrom-StringData` 忽略单行注释，但该 `#` 字符必须是行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="61e34-130">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="61e34-131">忽略后行中的所有字符 `#` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-131">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="61e34-132">示例3：将字符串转换为哈希表</span><span class="sxs-lookup"><span data-stu-id="61e34-132">Example 3: Convert a string to a hash table</span></span>

<span data-ttu-id="61e34-133">下面的示例将一个用双引号括起来的规则)  (转换为哈希表，并将其保存在 `$A` 变量中。</span><span class="sxs-lookup"><span data-stu-id="61e34-133">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

<span data-ttu-id="61e34-134">为了满足每个键/值对必须位于一个单独的行上的条件，该字符串使用 PowerShell 换行符 (\` n) 来分隔配对。</span><span class="sxs-lookup"><span data-stu-id="61e34-134">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="61e34-135">示例4：使用脚本的 DATA 节中的 ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="61e34-135">Example 4: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="61e34-136">此示例演示 `ConvertFrom-StringData` 脚本的数据部分中使用的命令。</span><span class="sxs-lookup"><span data-stu-id="61e34-136">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="61e34-137">DATA 节下面的语句向用户显示该文本。</span><span class="sxs-lookup"><span data-stu-id="61e34-137">The statements below the DATA section display the text to the user.</span></span>

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

<span data-ttu-id="61e34-138">由于文本包括变量名称，所以必须用单引号将它括起来，以便按照字义解释变量，而不是展开它。</span><span class="sxs-lookup"><span data-stu-id="61e34-138">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="61e34-139">不允许在 **DATA** 节中使用变量。</span><span class="sxs-lookup"><span data-stu-id="61e34-139">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="61e34-140">示例5：使用管道运算符传递字符串</span><span class="sxs-lookup"><span data-stu-id="61e34-140">Example 5: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="61e34-141">此示例演示可以使用管道运算符 (`|`) 将字符串发送到 `ConvertFrom-StringData` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-141">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="61e34-142">变量的值将通过 `$Here` 管道传递给 `ConvertFrom-StringData` ，并将结果放入 `$Hash` 变量中。</span><span class="sxs-lookup"><span data-stu-id="61e34-142">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### <span data-ttu-id="61e34-143">示例6：使用转义字符添加新行和返回字符</span><span class="sxs-lookup"><span data-stu-id="61e34-143">Example 6: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="61e34-144">此示例演示如何使用转义字符创建新行并返回源数据中的字符。</span><span class="sxs-lookup"><span data-stu-id="61e34-144">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="61e34-145">转义序列 `\n` 用于在与生成的哈希表中的名称或项关联的文本块中创建新行。</span><span class="sxs-lookup"><span data-stu-id="61e34-145">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### <span data-ttu-id="61e34-146">示例7：使用反斜杠转义字符正确呈现文件路径</span><span class="sxs-lookup"><span data-stu-id="61e34-146">Example 7: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="61e34-147">此示例演示如何使用字符串数据中的反斜杠转义字符，以允许在生成的哈希表中正确呈现文件路径 `ConvertFrom-StringData` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-147">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="61e34-148">双反斜杠可确保文本反斜杠字符正确呈现在哈希表输出中。</span><span class="sxs-lookup"><span data-stu-id="61e34-148">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="61e34-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61e34-149">PARAMETERS</span></span>

### <span data-ttu-id="61e34-150">-StringData</span><span class="sxs-lookup"><span data-stu-id="61e34-150">-StringData</span></span>

<span data-ttu-id="61e34-151">指定要转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="61e34-151">Specifies the string to be converted.</span></span> <span data-ttu-id="61e34-152">可以使用此参数或通过管道将字符串传递给 `ConvertFrom-StringData` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-152">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="61e34-153">参数名为可选项。</span><span class="sxs-lookup"><span data-stu-id="61e34-153">The parameter name is optional.</span></span>

<span data-ttu-id="61e34-154">此参数的值必须是包含一个或多个键/值对的字符串。</span><span class="sxs-lookup"><span data-stu-id="61e34-154">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="61e34-155">每个键/值对必须位于单独的行上，或每个对必须由换行符分隔 (\` n) 。</span><span class="sxs-lookup"><span data-stu-id="61e34-155">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="61e34-156">您可以在字符串中包含注释，但是注释不能与键值对在同一行上。</span><span class="sxs-lookup"><span data-stu-id="61e34-156">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="61e34-157">`ConvertFrom-StringData` 忽略单行注释。</span><span class="sxs-lookup"><span data-stu-id="61e34-157">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="61e34-158">该 `#` 字符必须是行中的第一个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="61e34-158">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="61e34-159">忽略后行中的所有字符 `#` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-159">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="61e34-160">哈希表中不包括注释。</span><span class="sxs-lookup"><span data-stu-id="61e34-160">The comments are not included in the hash table.</span></span>

<span data-ttu-id="61e34-161">这是一个字符串，包含一行或多行。</span><span class="sxs-lookup"><span data-stu-id="61e34-161">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="61e34-162">在此处字符串中的引号将按原义解释为字符串数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="61e34-162">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="61e34-163">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="61e34-163">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="61e34-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="61e34-164">CommonParameters</span></span>

<span data-ttu-id="61e34-165">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="61e34-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61e34-166">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="61e34-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="61e34-167">输入</span><span class="sxs-lookup"><span data-stu-id="61e34-167">INPUTS</span></span>

### <span data-ttu-id="61e34-168">System.String</span><span class="sxs-lookup"><span data-stu-id="61e34-168">System.String</span></span>

<span data-ttu-id="61e34-169">可以通过管道将包含键/值对的字符串传递给 `ConvertFrom-StringData` 。</span><span class="sxs-lookup"><span data-stu-id="61e34-169">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="61e34-170">输出</span><span class="sxs-lookup"><span data-stu-id="61e34-170">OUTPUTS</span></span>

### <span data-ttu-id="61e34-171">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="61e34-171">System.Collections.Hashtable</span></span>

<span data-ttu-id="61e34-172">此 cmdlet 将返回一个哈希表，该哈希表是从键/值对创建的。</span><span class="sxs-lookup"><span data-stu-id="61e34-172">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="61e34-173">注释</span><span class="sxs-lookup"><span data-stu-id="61e34-173">NOTES</span></span>

<span data-ttu-id="61e34-174">here-string 是由一行或多行组成的字符串，在其中，按照字义解释引号。</span><span class="sxs-lookup"><span data-stu-id="61e34-174">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="61e34-175">此 cmdlet 可用于以多种语言显示用户消息的脚本。</span><span class="sxs-lookup"><span data-stu-id="61e34-175">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="61e34-176">可使用字典风格的哈希表来从代码中隔离文本字符串（如在资源文件中），并为文本字符串设置格式以便在转换工具中使用。</span><span class="sxs-lookup"><span data-stu-id="61e34-176">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="61e34-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="61e34-177">RELATED LINKS</span></span>
