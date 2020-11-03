---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197937"
---
# <span data-ttu-id="14c85-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="14c85-103">Format-Hex</span></span>

## <span data-ttu-id="14c85-104">摘要</span><span class="sxs-lookup"><span data-stu-id="14c85-104">SYNOPSIS</span></span>

<span data-ttu-id="14c85-105">将文件或其他输入显示为十六进制。</span><span class="sxs-lookup"><span data-stu-id="14c85-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="14c85-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14c85-106">SYNTAX</span></span>

### <span data-ttu-id="14c85-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="14c85-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### <span data-ttu-id="14c85-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="14c85-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### <span data-ttu-id="14c85-109">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="14c85-109">ByInputObject</span></span>

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="14c85-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14c85-110">DESCRIPTION</span></span>

<span data-ttu-id="14c85-111">`Format-Hex`Cmdlet 将文件或其他输入显示为十六进制值。</span><span class="sxs-lookup"><span data-stu-id="14c85-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="14c85-112">若要确定输出中的字符的偏移量，请将行最左侧的数字与该字符所在列顶部的数字相加。</span><span class="sxs-lookup"><span data-stu-id="14c85-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="14c85-113">此 `Format-Hex` cmdlet 可帮助你确定损坏文件的文件类型或可能不具有文件扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="14c85-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="14c85-114">您可以运行此 cmdlet，然后读取十六进制输出以获取文件信息。</span><span class="sxs-lookup"><span data-stu-id="14c85-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="14c85-115">`Format-Hex`对文件使用时，该 cmdlet 将忽略换行符，并将保留了换行符的文件中的全部内容返回。</span><span class="sxs-lookup"><span data-stu-id="14c85-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="14c85-116">示例</span><span class="sxs-lookup"><span data-stu-id="14c85-116">EXAMPLES</span></span>

### <span data-ttu-id="14c85-117">示例 1：获取字符串的十六进制表示形式</span><span class="sxs-lookup"><span data-stu-id="14c85-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="14c85-118">此命令返回字符串的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="14c85-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="14c85-119">字符串 **Hello World** 会沿管道向下发送到 `Format-Hex` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="14c85-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="14c85-120">的十六进制输出 `Format-Hex` 显示字符串中每个字符的值。</span><span class="sxs-lookup"><span data-stu-id="14c85-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="14c85-121">示例2：从十六进制输出中查找文件类型</span><span class="sxs-lookup"><span data-stu-id="14c85-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="14c85-122">此示例使用十六进制输出来确定文件类型。</span><span class="sxs-lookup"><span data-stu-id="14c85-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="14c85-123">Cmdlet 显示文件的完整路径和十六进制值。</span><span class="sxs-lookup"><span data-stu-id="14c85-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="14c85-124">若要测试以下命令，请在本地计算机上创建现有 PDF 文件的副本，并将复制的文件重命名为 **t7f** 。</span><span class="sxs-lookup"><span data-stu-id="14c85-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to **File.t7f** .</span></span>

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

<span data-ttu-id="14c85-125">`Format-Hex`Cmdlet 使用 **Path** 参数来指定当前目录中的文件名 `File.t7f` 。</span><span class="sxs-lookup"><span data-stu-id="14c85-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="14c85-126">文件扩展名 `.t7f` 不常见，但十六进制输出 `%PDF` 显示它是 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="14c85-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span>

### <span data-ttu-id="14c85-127">示例3：显示原始十六进制输出</span><span class="sxs-lookup"><span data-stu-id="14c85-127">Example 3: Display raw hexadecimal output</span></span>

<span data-ttu-id="14c85-128">默认情况下， `Format-Hex` 对于数值数据类型，可以使用单字节和双字节序列。</span><span class="sxs-lookup"><span data-stu-id="14c85-128">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="14c85-129">**原始** 参数停用此行为。</span><span class="sxs-lookup"><span data-stu-id="14c85-129">The **Raw** parameter deactivates this behavior.</span></span>

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

<span data-ttu-id="14c85-130">请注意输出中的差异。</span><span class="sxs-lookup"><span data-stu-id="14c85-130">Notice the difference in output.</span></span> <span data-ttu-id="14c85-131">**Raw** 参数将数字显示为4字节值，将其值显示为 **Int32** 类型。</span><span class="sxs-lookup"><span data-stu-id="14c85-131">The **Raw** parameter displays the numbers as 4-byte values, true to their **Int32** types.</span></span>

## <span data-ttu-id="14c85-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14c85-132">PARAMETERS</span></span>

### <span data-ttu-id="14c85-133">-Encoding</span><span class="sxs-lookup"><span data-stu-id="14c85-133">-Encoding</span></span>

<span data-ttu-id="14c85-134">指定输出的编码。</span><span class="sxs-lookup"><span data-stu-id="14c85-134">Specifies the encoding of the output.</span></span> <span data-ttu-id="14c85-135">这仅适用于 `[string]` 输入。</span><span class="sxs-lookup"><span data-stu-id="14c85-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="14c85-136">参数对数值类型不起作用。</span><span class="sxs-lookup"><span data-stu-id="14c85-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="14c85-137">默认值是 `ASCII`。</span><span class="sxs-lookup"><span data-stu-id="14c85-137">The default value is `ASCII`.</span></span>

<span data-ttu-id="14c85-138">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="14c85-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="14c85-139">`Ascii` 使用 ASCII (7 位) 字符集。</span><span class="sxs-lookup"><span data-stu-id="14c85-139">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="14c85-140">`BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="14c85-140">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="14c85-141">`Unicode` 使用带有小 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="14c85-141">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="14c85-142">`UTF7` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="14c85-142">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="14c85-143">`UTF8` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="14c85-143">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="14c85-144">`UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="14c85-144">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="14c85-145">输入中的非 ASCII 字符输出为原义 `?` 字符，导致信息丢失。</span><span class="sxs-lookup"><span data-stu-id="14c85-145">Non-ASCII characters in the input are output as literal `?` characters resulting in a loss of information.</span></span>

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14c85-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="14c85-146">-InputObject</span></span>

<span data-ttu-id="14c85-147">用于管道输入。</span><span class="sxs-lookup"><span data-stu-id="14c85-147">Used for pipeline input.</span></span> <span data-ttu-id="14c85-148">管道输入仅支持特定于管道的标量类型和 `[system.io.fileinfo]` 实例 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="14c85-148">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="14c85-149">支持的标量类型为：</span><span class="sxs-lookup"><span data-stu-id="14c85-149">The supported scalar types are:</span></span>

- `[string]`
- `[byte]`
- <span data-ttu-id="14c85-150">`[int]`, `[int32]`</span><span class="sxs-lookup"><span data-stu-id="14c85-150">`[int]`, `[int32]`</span></span>
- <span data-ttu-id="14c85-151">`[long]`, `[int64]`</span><span class="sxs-lookup"><span data-stu-id="14c85-151">`[long]`, `[int64]`</span></span>

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="14c85-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="14c85-152">-LiteralPath</span></span>

<span data-ttu-id="14c85-153">指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="14c85-153">Specifies the complete path to a file.</span></span> <span data-ttu-id="14c85-154">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="14c85-154">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="14c85-155">此参数不接受通配符。</span><span class="sxs-lookup"><span data-stu-id="14c85-155">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="14c85-156">若要指定文件的多个路径，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="14c85-156">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="14c85-157">如果 **LiteralPath** 参数包含转义符，请将路径用单引号引起来。</span><span class="sxs-lookup"><span data-stu-id="14c85-157">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="14c85-158">PowerShell 不会将单个带引号的字符串中的任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="14c85-158">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="14c85-159">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="14c85-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14c85-160">-Path</span><span class="sxs-lookup"><span data-stu-id="14c85-160">-Path</span></span>

<span data-ttu-id="14c85-161">指定文件的路径。</span><span class="sxs-lookup"><span data-stu-id="14c85-161">Specifies the path to files.</span></span> <span data-ttu-id="14c85-162">使用点)  (`.` 指定当前位置。</span><span class="sxs-lookup"><span data-stu-id="14c85-162">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="14c85-163">通配符 (`*`) 是可接受的，并且可用于指定位置中的所有项。</span><span class="sxs-lookup"><span data-stu-id="14c85-163">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="14c85-164">如果 **path** 参数包含转义符，请将路径用单引号引起来。</span><span class="sxs-lookup"><span data-stu-id="14c85-164">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="14c85-165">若要指定文件的多个路径，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="14c85-165">To specify multiple paths to files, separate the paths with a comma.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="14c85-166">-Raw</span><span class="sxs-lookup"><span data-stu-id="14c85-166">-Raw</span></span>

<span data-ttu-id="14c85-167">默认情况下， `Format-Hex` 对于数值数据类型，可以使用单字节和双字节序列。</span><span class="sxs-lookup"><span data-stu-id="14c85-167">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="14c85-168">**原始** 参数停用此行为。</span><span class="sxs-lookup"><span data-stu-id="14c85-168">The **Raw** parameter deactivates this behavior.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14c85-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14c85-169">CommonParameters</span></span>

<span data-ttu-id="14c85-170">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="14c85-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14c85-171">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="14c85-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14c85-172">输入</span><span class="sxs-lookup"><span data-stu-id="14c85-172">INPUTS</span></span>

### <span data-ttu-id="14c85-173">System.String</span><span class="sxs-lookup"><span data-stu-id="14c85-173">System.String</span></span>

<span data-ttu-id="14c85-174">可以通过管道将字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="14c85-174">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="14c85-175">输出</span><span class="sxs-lookup"><span data-stu-id="14c85-175">OUTPUTS</span></span>

### <span data-ttu-id="14c85-176">Microsoft.PowerShell.Commands.ByteCollection</span><span class="sxs-lookup"><span data-stu-id="14c85-176">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="14c85-177">此 cmdlet 返回 **ByteCollection** 。</span><span class="sxs-lookup"><span data-stu-id="14c85-177">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="14c85-178">此对象表示字节的集合。</span><span class="sxs-lookup"><span data-stu-id="14c85-178">This object represents a collection of bytes.</span></span> <span data-ttu-id="14c85-179">它包含一些方法，这些方法可将字节的集合转换为格式类似于返回的每个输出行的字符串 `Format-Hex` 。</span><span class="sxs-lookup"><span data-stu-id="14c85-179">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="14c85-180">如果指定 Path  或 LiteralPath  参数，则该对象还包含其中含有每个字节的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="14c85-180">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="14c85-181">注释</span><span class="sxs-lookup"><span data-stu-id="14c85-181">NOTES</span></span>

<span data-ttu-id="14c85-182">输出的最右侧列尝试将字节呈现为字符：</span><span class="sxs-lookup"><span data-stu-id="14c85-182">The right-most column of output tries to render the bytes as characters:</span></span>

<span data-ttu-id="14c85-183">通常，每个字节都被解释为 Unicode 码位，这意味着：</span><span class="sxs-lookup"><span data-stu-id="14c85-183">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="14c85-184">可打印的 ASCII 字符始终正确呈现</span><span class="sxs-lookup"><span data-stu-id="14c85-184">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="14c85-185">多字节 UTF-8 字符永远无法正确呈现</span><span class="sxs-lookup"><span data-stu-id="14c85-185">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="14c85-186">只有在高序位字节发生的情况下，UTF-16 字符才会正确呈现 `NUL` 。</span><span class="sxs-lookup"><span data-stu-id="14c85-186">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="14c85-187">相关链接</span><span class="sxs-lookup"><span data-stu-id="14c85-187">RELATED LINKS</span></span>

[<span data-ttu-id="14c85-188">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="14c85-188">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="14c85-189">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="14c85-189">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="14c85-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="14c85-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="14c85-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="14c85-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="14c85-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="14c85-192">Format-Wide</span></span>](Format-Wide.md)
