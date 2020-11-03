---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: bb9345470aa58dac7c14e1443c0fe4c12e7563a6
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "93199356"
---
# <span data-ttu-id="448b1-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="448b1-103">Set-Content</span></span>

## <span data-ttu-id="448b1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="448b1-104">SYNOPSIS</span></span>
<span data-ttu-id="448b1-105">写入新内容或替换文件中的现有内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="448b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="448b1-106">SYNTAX</span></span>

### <span data-ttu-id="448b1-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="448b1-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="448b1-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="448b1-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="448b1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="448b1-109">DESCRIPTION</span></span>

<span data-ttu-id="448b1-110">`Set-Content` 是一个字符串处理 cmdlet，用于写入新内容或替换文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="448b1-111">`Set-Content` 替换现有内容，不同于将 `Add-Content` 内容追加到文件的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448b1-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="448b1-112">若要将内容发送到 `Set-Content` ，可以在命令行上使用 **Value** 参数或通过管道发送内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="448b1-113">如果需要为以下示例创建文件或目录，请参阅 " [新建项](New-Item.md)"。</span><span class="sxs-lookup"><span data-stu-id="448b1-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="448b1-114">示例</span><span class="sxs-lookup"><span data-stu-id="448b1-114">EXAMPLES</span></span>

### <span data-ttu-id="448b1-115">示例1：替换目录中多个文件的内容</span><span class="sxs-lookup"><span data-stu-id="448b1-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="448b1-116">此示例替换当前目录中多个文件的内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-116">This example replaces the content for multiple files in the current directory.</span></span>

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

<span data-ttu-id="448b1-117">`Get-ChildItem`Cmdlet 使用 **Path** 参数列出以当前目录开头的 **.txt** 文件。 `Test*`</span><span class="sxs-lookup"><span data-stu-id="448b1-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="448b1-118">`Set-Content`Cmdlet 使用 **Path** 参数指定 `Test*.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="448b1-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="448b1-119">**Value** 参数提供替换每个文件中的现有内容的文本字符串 **Hello、World** 。</span><span class="sxs-lookup"><span data-stu-id="448b1-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="448b1-120">`Get-Content`Cmdlet 使用 **Path** 参数指定 `Test*.txt` 文件，并在 PowerShell 控制台中显示每个文件的内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="448b1-121">示例2：创建新文件并写入内容</span><span class="sxs-lookup"><span data-stu-id="448b1-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="448b1-122">此示例将创建一个新文件，并将当前日期和时间写入文件。</span><span class="sxs-lookup"><span data-stu-id="448b1-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="448b1-123">`Set-Content` 使用 **Path** 和 **Value** 参数在当前目录中创建一个名为 **DateTime.txt** 的新文件。</span><span class="sxs-lookup"><span data-stu-id="448b1-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="448b1-124">**值** 参数用于 `Get-Date` 获取当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="448b1-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="448b1-125">`Set-Content` 将 **DateTime** 对象作为字符串写入到文件中。</span><span class="sxs-lookup"><span data-stu-id="448b1-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="448b1-126">`Get-Content`Cmdlet 使用 **Path** 参数在 PowerShell 控制台中显示 **DateTime.txt** 的内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="448b1-127">示例 3：在文件中替换文本</span><span class="sxs-lookup"><span data-stu-id="448b1-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="448b1-128">此命令替换现有文件中的所有 word 实例。</span><span class="sxs-lookup"><span data-stu-id="448b1-128">This command replaces all instances of word within an existing file.</span></span>

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

<span data-ttu-id="448b1-129">`Get-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的 **Notice.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="448b1-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="448b1-130">`Get-Content`命令用括号括起来，以便命令在管道下发送前完成。</span><span class="sxs-lookup"><span data-stu-id="448b1-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="448b1-131">**Notice.txt** 文件的内容将通过管道向下发送到 `ForEach-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448b1-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="448b1-132">`ForEach-Object`使用自动变量 `$_` ，并将每次出现 **Warning** 的警告 **Caution** 替换为警告。</span><span class="sxs-lookup"><span data-stu-id="448b1-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="448b1-133">对象通过管道向下发送到 `Set-Content` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448b1-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="448b1-134">`Set-Content` 使用 **Path** 参数指定 **Notice.txt** 文件，并将更新的内容写入文件。</span><span class="sxs-lookup"><span data-stu-id="448b1-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="448b1-135">最后一个 `Get-Content` cmdlet 在 PowerShell 控制台中显示更新的文件内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="448b1-136">示例4：使用筛选器与 Set-Content</span><span class="sxs-lookup"><span data-stu-id="448b1-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="448b1-137">可以为 cmdlet 指定筛选器 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="448b1-138">使用筛选器限定 **路径** 参数时，需要包含一个尾随星号 (`*`) ，以指示路径的内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="448b1-139">以下命令将目录中的所有文件的内容设置 `*.txt` `C:\Temp` 为空 **值** 。</span><span class="sxs-lookup"><span data-stu-id="448b1-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="448b1-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="448b1-140">PARAMETERS</span></span>

### <span data-ttu-id="448b1-141">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="448b1-141">-AsByteStream</span></span>

<span data-ttu-id="448b1-142">指定应以字节流的形式读取内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-142">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="448b1-143">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="448b1-143">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="448b1-144">将 **AsByteStream** 参数与 **Encoding** 参数一起使用时，将出现警告。</span><span class="sxs-lookup"><span data-stu-id="448b1-144">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="448b1-145">**AsByteStream** 参数将忽略任何编码，并以字节流的形式返回输出。</span><span class="sxs-lookup"><span data-stu-id="448b1-145">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="448b1-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="448b1-147">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="448b1-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="448b1-148">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="448b1-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-149">-Encoding</span><span class="sxs-lookup"><span data-stu-id="448b1-149">-Encoding</span></span>

<span data-ttu-id="448b1-150">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="448b1-150">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="448b1-151">默认值是 `utf8NoBOM`。</span><span class="sxs-lookup"><span data-stu-id="448b1-151">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="448b1-152">Encoding 是 FileSystem 提供程序添加到的动态参数 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-152">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="448b1-153">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="448b1-153">This parameter works only in file system drives.</span></span>

<span data-ttu-id="448b1-154">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="448b1-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="448b1-155">`ascii`：使用 ASCII (7 位) 字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="448b1-156">`bigendianunicode`：使用大字节序字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="448b1-157">`bigendianutf32`：使用大字节序字节顺序编码为32格式。</span><span class="sxs-lookup"><span data-stu-id="448b1-157">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="448b1-158">`oem`：使用 MS-DOS 和控制台程序的默认编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-158">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="448b1-159">`unicode`：使用小 endian 字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-159">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="448b1-160">`utf7`：以 UTF-7 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-160">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="448b1-161">`utf8`：以 UTF-8 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-161">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="448b1-162">`utf8BOM`：以 UTF-8 格式编码 (BOM) </span><span class="sxs-lookup"><span data-stu-id="448b1-162">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="448b1-163">`utf8NoBOM`：以 UTF-8 格式编码，而不包含字节顺序标记 (BOM) </span><span class="sxs-lookup"><span data-stu-id="448b1-163">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="448b1-164">`utf32`：以32格式编码。</span><span class="sxs-lookup"><span data-stu-id="448b1-164">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="448b1-165">从 PowerShell 6.2 开始， **Encoding** 参数还允许已注册代码页的数字 id (如 `-Encoding 1251` (如) 所注册代码页的) 或字符串名称 `-Encoding "windows-1251"` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-165">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="448b1-166">有关详细信息，请参阅 .NET 文档中的[编码。](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)</span><span class="sxs-lookup"><span data-stu-id="448b1-166">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="448b1-167">不建议使用 **utf-7** \*。</span><span class="sxs-lookup"><span data-stu-id="448b1-167">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="448b1-168">在 PowerShell 7.1 中，如果 `utf7` 为 **编码** 参数指定，则会写入警告。</span><span class="sxs-lookup"><span data-stu-id="448b1-168">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-169">-Exclude</span><span class="sxs-lookup"><span data-stu-id="448b1-169">-Exclude</span></span>

<span data-ttu-id="448b1-170">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="448b1-170">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="448b1-171">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="448b1-171">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="448b1-172">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="448b1-172">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="448b1-173">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="448b1-173">Wildcard characters are permitted.</span></span> <span data-ttu-id="448b1-174">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-174">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="448b1-175">-Filter</span><span class="sxs-lookup"><span data-stu-id="448b1-175">-Filter</span></span>

<span data-ttu-id="448b1-176">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="448b1-176">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="448b1-177">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="448b1-177">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="448b1-178">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="448b1-178">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="448b1-179">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="448b1-179">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="448b1-180">-Force</span><span class="sxs-lookup"><span data-stu-id="448b1-180">-Force</span></span>

<span data-ttu-id="448b1-181">强制该 cmdlet 设置文件内容（即使该文件是只读的）。</span><span class="sxs-lookup"><span data-stu-id="448b1-181">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="448b1-182">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="448b1-182">Implementation varies from provider to provider.</span></span> <span data-ttu-id="448b1-183">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="448b1-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="448b1-184">**Force** 参数不会覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="448b1-184">The **Force** parameter does not override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-185">-Include</span><span class="sxs-lookup"><span data-stu-id="448b1-185">-Include</span></span>

<span data-ttu-id="448b1-186">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="448b1-186">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="448b1-187">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="448b1-187">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="448b1-188">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="448b1-188">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="448b1-189">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="448b1-189">Wildcard characters are permitted.</span></span> <span data-ttu-id="448b1-190">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-190">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="448b1-191">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="448b1-191">-LiteralPath</span></span>

<span data-ttu-id="448b1-192">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="448b1-192">Specifies a path to one or more locations.</span></span> <span data-ttu-id="448b1-193">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="448b1-193">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="448b1-194">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="448b1-194">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="448b1-195">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="448b1-195">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="448b1-196">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="448b1-196">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="448b1-197">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="448b1-197">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-198">-NoNewline</span><span class="sxs-lookup"><span data-stu-id="448b1-198">-NoNewline</span></span>

<span data-ttu-id="448b1-199">输入对象的字符串表示形式连接起来以形成输出。</span><span class="sxs-lookup"><span data-stu-id="448b1-199">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="448b1-200">不会在输出字符串之间插入空格或换行符。</span><span class="sxs-lookup"><span data-stu-id="448b1-200">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="448b1-201">在最后一个输出字符串之后不添加任何行。</span><span class="sxs-lookup"><span data-stu-id="448b1-201">No newline is added after the last output string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-202">-PassThru</span><span class="sxs-lookup"><span data-stu-id="448b1-202">-PassThru</span></span>

<span data-ttu-id="448b1-203">返回一个表示内容的对象。</span><span class="sxs-lookup"><span data-stu-id="448b1-203">Returns an object that represents the content.</span></span> <span data-ttu-id="448b1-204">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="448b1-204">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-205">-Path</span><span class="sxs-lookup"><span data-stu-id="448b1-205">-Path</span></span>

<span data-ttu-id="448b1-206">指定接受内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="448b1-206">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="448b1-207">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="448b1-207">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="448b1-208">-Stream</span><span class="sxs-lookup"><span data-stu-id="448b1-208">-Stream</span></span>

<span data-ttu-id="448b1-209">指定内容的备用数据流。</span><span class="sxs-lookup"><span data-stu-id="448b1-209">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="448b1-210">如果该流不存在，则此 cmdlet 将创建它。</span><span class="sxs-lookup"><span data-stu-id="448b1-210">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="448b1-211">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="448b1-211">Wildcard characters are not supported.</span></span>

<span data-ttu-id="448b1-212">**Stream** 是 **FileSystem** 提供程序添加到的动态参数 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-212">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="448b1-213">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="448b1-213">This parameter works only in file system drives.</span></span>

<span data-ttu-id="448b1-214">可以使用 `Set-Content` cmdlet 更改区域的内容 **。标识符** 备用数据流。</span><span class="sxs-lookup"><span data-stu-id="448b1-214">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="448b1-215">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="448b1-215">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="448b1-216">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="448b1-216">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="448b1-217">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="448b1-217">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-218">-Value</span><span class="sxs-lookup"><span data-stu-id="448b1-218">-Value</span></span>

<span data-ttu-id="448b1-219">为项指定新的内容。</span><span class="sxs-lookup"><span data-stu-id="448b1-219">Specifies the new content for the item.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-220">-Confirm</span><span class="sxs-lookup"><span data-stu-id="448b1-220">-Confirm</span></span>

<span data-ttu-id="448b1-221">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="448b1-221">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-222">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="448b1-222">-WhatIf</span></span>

<span data-ttu-id="448b1-223">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="448b1-223">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="448b1-224">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="448b1-224">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="448b1-225">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="448b1-225">CommonParameters</span></span>

<span data-ttu-id="448b1-226">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-226">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="448b1-227">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="448b1-227">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="448b1-228">输入</span><span class="sxs-lookup"><span data-stu-id="448b1-228">INPUTS</span></span>

### <span data-ttu-id="448b1-229">System.Object</span><span class="sxs-lookup"><span data-stu-id="448b1-229">System.Object</span></span>

<span data-ttu-id="448b1-230">可以通过管道将包含项的新值的对象传递给 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-230">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="448b1-231">输出</span><span class="sxs-lookup"><span data-stu-id="448b1-231">OUTPUTS</span></span>

### <span data-ttu-id="448b1-232">None 或 System.String</span><span class="sxs-lookup"><span data-stu-id="448b1-232">None or System.String</span></span>

<span data-ttu-id="448b1-233">当使用 **PassThru** 参数时，将 `Set-Content` 生成表示内容的 **system.string** 对象。</span><span class="sxs-lookup"><span data-stu-id="448b1-233">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="448b1-234">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="448b1-234">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="448b1-235">注释</span><span class="sxs-lookup"><span data-stu-id="448b1-235">NOTES</span></span>

- <span data-ttu-id="448b1-236">还可以 `Set-Content` 通过其内置别名来引用 `sc` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-236">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="448b1-237">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="448b1-237">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="448b1-238">`Set-Content` 用于字符串处理。</span><span class="sxs-lookup"><span data-stu-id="448b1-238">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="448b1-239">如果将非字符串对象通过管道传递给 `Set-Content` ，它会在写入之前将对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="448b1-239">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="448b1-240">若要将对象写入文件，请使用 `Out-File` 。</span><span class="sxs-lookup"><span data-stu-id="448b1-240">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="448b1-241">`Set-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="448b1-241">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="448b1-242">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="448b1-242">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="448b1-243">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="448b1-243">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="448b1-244">相关链接</span><span class="sxs-lookup"><span data-stu-id="448b1-244">RELATED LINKS</span></span>

[<span data-ttu-id="448b1-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="448b1-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="448b1-246">about_Automatic_Variables md</span><span class="sxs-lookup"><span data-stu-id="448b1-246">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="448b1-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="448b1-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="448b1-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="448b1-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="448b1-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="448b1-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="448b1-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="448b1-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="448b1-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="448b1-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="448b1-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="448b1-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="448b1-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="448b1-253">New-Item</span></span>](New-Item.md)

