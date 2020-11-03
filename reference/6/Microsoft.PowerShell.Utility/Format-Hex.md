---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 64275e72f8c21942179431b3aed4a17d328aa2e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198611"
---
# <span data-ttu-id="4e58c-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="4e58c-103">Format-Hex</span></span>

## <span data-ttu-id="4e58c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4e58c-104">SYNOPSIS</span></span>

<span data-ttu-id="4e58c-105">将文件或其他输入显示为十六进制。</span><span class="sxs-lookup"><span data-stu-id="4e58c-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="4e58c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e58c-106">SYNTAX</span></span>

### <span data-ttu-id="4e58c-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="4e58c-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="4e58c-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4e58c-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="4e58c-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="4e58c-109">InputObject</span></span>

```
Format-Hex -InputObject <psobject> [-Encoding <Encoding>] [-Count <long>] [-Offset <long>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="4e58c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4e58c-110">DESCRIPTION</span></span>

<span data-ttu-id="4e58c-111">`Format-Hex`Cmdlet 将文件或其他输入显示为十六进制值。</span><span class="sxs-lookup"><span data-stu-id="4e58c-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="4e58c-112">若要确定输出中的字符的偏移量，请将行最左侧的数字与该字符所在列顶部的数字相加。</span><span class="sxs-lookup"><span data-stu-id="4e58c-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="4e58c-113">此 `Format-Hex` cmdlet 可帮助你确定损坏文件的文件类型或可能不具有文件扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="4e58c-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="4e58c-114">您可以运行此 cmdlet，然后读取十六进制输出以获取文件信息。</span><span class="sxs-lookup"><span data-stu-id="4e58c-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="4e58c-115">`Format-Hex`对文件使用时，该 cmdlet 将忽略换行符，并将保留了换行符的文件中的全部内容返回。</span><span class="sxs-lookup"><span data-stu-id="4e58c-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="4e58c-116">示例</span><span class="sxs-lookup"><span data-stu-id="4e58c-116">EXAMPLES</span></span>

### <span data-ttu-id="4e58c-117">示例 1：获取字符串的十六进制表示形式</span><span class="sxs-lookup"><span data-stu-id="4e58c-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="4e58c-118">此命令返回字符串的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="4e58c-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="4e58c-119">字符串 **Hello World** 会沿管道向下发送到 `Format-Hex` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e58c-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="4e58c-120">的十六进制输出 `Format-Hex` 显示字符串中每个字符的值。</span><span class="sxs-lookup"><span data-stu-id="4e58c-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="4e58c-121">示例2：从十六进制输出中查找文件类型</span><span class="sxs-lookup"><span data-stu-id="4e58c-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="4e58c-122">此示例使用十六进制输出来确定文件类型。</span><span class="sxs-lookup"><span data-stu-id="4e58c-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="4e58c-123">Cmdlet 显示文件的完整路径和十六进制值。</span><span class="sxs-lookup"><span data-stu-id="4e58c-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="4e58c-124">若要测试以下命令，请在本地计算机上创建现有 PDF 文件的副本，并将复制的文件重命名为 `File.t7f` 。</span><span class="sxs-lookup"><span data-stu-id="4e58c-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

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

<span data-ttu-id="4e58c-125">`Format-Hex`Cmdlet 使用 **Path** 参数来指定当前目录 **t7f** 中的文件名。</span><span class="sxs-lookup"><span data-stu-id="4e58c-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, **File.t7f** .</span></span> <span data-ttu-id="4e58c-126">文件扩展名 **t7f** 不常见，但十六进制输出 **% PDF** 显示它是 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="4e58c-126">The file extension **.t7f** is uncommon, but the hexadecimal output **%PDF** shows that it is a PDF file.</span></span>

## <span data-ttu-id="4e58c-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e58c-127">PARAMETERS</span></span>

### <span data-ttu-id="4e58c-128">-Encoding</span><span class="sxs-lookup"><span data-stu-id="4e58c-128">-Encoding</span></span>

<span data-ttu-id="4e58c-129">指定输出的编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-129">Specifies the encoding of the output.</span></span> <span data-ttu-id="4e58c-130">这仅适用于 `[string]` 输入。</span><span class="sxs-lookup"><span data-stu-id="4e58c-130">This only applies to `[string]` input.</span></span> <span data-ttu-id="4e58c-131">参数对数值类型不起作用。</span><span class="sxs-lookup"><span data-stu-id="4e58c-131">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="4e58c-132">默认值是 `utf8NoBOM`。</span><span class="sxs-lookup"><span data-stu-id="4e58c-132">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="4e58c-133">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e58c-133">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4e58c-134">`ascii`：使用 ASCII (7 位) 字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-134">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="4e58c-135">`bigendianunicode`：使用大字节序字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-135">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="4e58c-136">`oem`：使用 MS-DOS 和控制台程序的默认编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-136">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="4e58c-137">`unicode`：使用小 endian 字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-137">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="4e58c-138">`utf7`：以 UTF-7 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-138">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="4e58c-139">`utf8`：以 UTF-8 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-139">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="4e58c-140">`utf8BOM`：以 UTF-8 格式编码 (BOM) </span><span class="sxs-lookup"><span data-stu-id="4e58c-140">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="4e58c-141">`utf8NoBOM`：以 UTF-8 格式编码，而不包含字节顺序标记 (BOM) </span><span class="sxs-lookup"><span data-stu-id="4e58c-141">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="4e58c-142">`utf32`：以32格式编码。</span><span class="sxs-lookup"><span data-stu-id="4e58c-142">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="4e58c-143">从 PowerShell 6.2 开始， **Encoding** 参数还允许已注册代码页的数字 id (如 `-Encoding 1251` (如) 所注册代码页的) 或字符串名称 `-Encoding "windows-1251"` 。</span><span class="sxs-lookup"><span data-stu-id="4e58c-143">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="4e58c-144">有关详细信息，请参阅 .NET 文档中的[编码。](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)</span><span class="sxs-lookup"><span data-stu-id="4e58c-144">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4e58c-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4e58c-145">-InputObject</span></span>

<span data-ttu-id="4e58c-146">用于管道输入。</span><span class="sxs-lookup"><span data-stu-id="4e58c-146">Used for pipeline input.</span></span> <span data-ttu-id="4e58c-147">管道输入仅支持特定于管道的标量类型和 `[system.io.fileinfo]` 实例 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="4e58c-147">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="4e58c-148">支持的标量类型为：</span><span class="sxs-lookup"><span data-stu-id="4e58c-148">The supported scalar types are:</span></span>

- <span data-ttu-id="4e58c-149">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="4e58c-149">`[string]`, `[char]`</span></span>
- <span data-ttu-id="4e58c-150">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="4e58c-150">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="4e58c-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="4e58c-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="4e58c-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="4e58c-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="4e58c-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="4e58c-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="4e58c-154">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="4e58c-154">`[single]`, `[float]`, `[double]`</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4e58c-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4e58c-155">-LiteralPath</span></span>

<span data-ttu-id="4e58c-156">指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="4e58c-156">Specifies the complete path to a file.</span></span> <span data-ttu-id="4e58c-157">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="4e58c-157">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="4e58c-158">此参数不接受通配符。</span><span class="sxs-lookup"><span data-stu-id="4e58c-158">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="4e58c-159">若要指定文件的多个路径，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="4e58c-159">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="4e58c-160">如果 **LiteralPath** 参数包含转义符，请将路径用单引号引起来。</span><span class="sxs-lookup"><span data-stu-id="4e58c-160">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="4e58c-161">PowerShell 不会将单个带引号的字符串中的任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="4e58c-161">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="4e58c-162">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4e58c-162">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4e58c-163">-Path</span><span class="sxs-lookup"><span data-stu-id="4e58c-163">-Path</span></span>

<span data-ttu-id="4e58c-164">指定文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4e58c-164">Specifies the path to files.</span></span> <span data-ttu-id="4e58c-165">使用点)  (`.` 指定当前位置。</span><span class="sxs-lookup"><span data-stu-id="4e58c-165">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="4e58c-166">通配符 (`*`) 是可接受的，并且可用于指定位置中的所有项。</span><span class="sxs-lookup"><span data-stu-id="4e58c-166">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="4e58c-167">如果 **path** 参数包含转义符，请将路径用单引号引起来。</span><span class="sxs-lookup"><span data-stu-id="4e58c-167">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="4e58c-168">若要指定文件的多个路径，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="4e58c-168">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="4e58c-169">-Raw</span><span class="sxs-lookup"><span data-stu-id="4e58c-169">-Raw</span></span>

<span data-ttu-id="4e58c-170">此参数不再执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4e58c-170">This parameter no longer does anything.</span></span> <span data-ttu-id="4e58c-171">它保留用于脚本兼容性。</span><span class="sxs-lookup"><span data-stu-id="4e58c-171">It is retained for script compatibility.</span></span>

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

### <span data-ttu-id="4e58c-172">-Offset</span><span class="sxs-lookup"><span data-stu-id="4e58c-172">-Offset</span></span>

<span data-ttu-id="4e58c-173">这表示要从十六进制输出中跳过的字节数。</span><span class="sxs-lookup"><span data-stu-id="4e58c-173">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="4e58c-174">此参数是在 PowerShell 6.2 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4e58c-174">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4e58c-175">-Count</span><span class="sxs-lookup"><span data-stu-id="4e58c-175">-Count</span></span>

<span data-ttu-id="4e58c-176">这表示要包含在十六进制输出中的字节数。</span><span class="sxs-lookup"><span data-stu-id="4e58c-176">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="4e58c-177">此参数是在 PowerShell 6.2 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4e58c-177">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4e58c-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4e58c-178">CommonParameters</span></span>

<span data-ttu-id="4e58c-179">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4e58c-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4e58c-180">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4e58c-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4e58c-181">输入</span><span class="sxs-lookup"><span data-stu-id="4e58c-181">INPUTS</span></span>

### <span data-ttu-id="4e58c-182">System.String</span><span class="sxs-lookup"><span data-stu-id="4e58c-182">System.String</span></span>

<span data-ttu-id="4e58c-183">可以通过管道将字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e58c-183">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="4e58c-184">输出</span><span class="sxs-lookup"><span data-stu-id="4e58c-184">OUTPUTS</span></span>

### <span data-ttu-id="4e58c-185">Microsoft.PowerShell.Commands.ByteCollection</span><span class="sxs-lookup"><span data-stu-id="4e58c-185">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="4e58c-186">此 cmdlet 返回 **ByteCollection** 。</span><span class="sxs-lookup"><span data-stu-id="4e58c-186">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="4e58c-187">此对象表示字节的集合。</span><span class="sxs-lookup"><span data-stu-id="4e58c-187">This object represents a collection of bytes.</span></span> <span data-ttu-id="4e58c-188">它包含一些方法，这些方法可将字节的集合转换为格式类似于返回的每个输出行的字符串 `Format-Hex` 。</span><span class="sxs-lookup"><span data-stu-id="4e58c-188">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="4e58c-189">如果指定 Path  或 LiteralPath  参数，则该对象还包含其中含有每个字节的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4e58c-189">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="4e58c-190">注释</span><span class="sxs-lookup"><span data-stu-id="4e58c-190">NOTES</span></span>

<span data-ttu-id="4e58c-191">输出的最右侧列尝试将字节呈现为 ASCII 字符：</span><span class="sxs-lookup"><span data-stu-id="4e58c-191">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="4e58c-192">通常，每个字节都被解释为 Unicode 码位，这意味着：</span><span class="sxs-lookup"><span data-stu-id="4e58c-192">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="4e58c-193">可打印的 ASCII 字符始终正确呈现</span><span class="sxs-lookup"><span data-stu-id="4e58c-193">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="4e58c-194">多字节 UTF-8 字符永远无法正确呈现</span><span class="sxs-lookup"><span data-stu-id="4e58c-194">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="4e58c-195">只有在高序位字节发生的情况下，UTF-16 字符才会正确呈现 `NUL` 。</span><span class="sxs-lookup"><span data-stu-id="4e58c-195">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="4e58c-196">相关链接</span><span class="sxs-lookup"><span data-stu-id="4e58c-196">RELATED LINKS</span></span>

[<span data-ttu-id="4e58c-197">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="4e58c-197">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="4e58c-198">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="4e58c-198">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="4e58c-199">Format-List</span><span class="sxs-lookup"><span data-stu-id="4e58c-199">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="4e58c-200">Format-Table</span><span class="sxs-lookup"><span data-stu-id="4e58c-200">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="4e58c-201">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="4e58c-201">Format-Wide</span></span>](Format-Wide.md)
