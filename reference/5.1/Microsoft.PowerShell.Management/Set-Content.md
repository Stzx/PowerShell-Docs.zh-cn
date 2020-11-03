---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 897029cab790487f6834d021bfc447060fd39812
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198048"
---
# <span data-ttu-id="2ce69-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="2ce69-103">Set-Content</span></span>

## <span data-ttu-id="2ce69-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2ce69-104">SYNOPSIS</span></span>
<span data-ttu-id="2ce69-105">写入新内容或替换文件中的现有内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="2ce69-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ce69-106">SYNTAX</span></span>

### <span data-ttu-id="2ce69-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="2ce69-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="2ce69-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2ce69-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="2ce69-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ce69-109">DESCRIPTION</span></span>

<span data-ttu-id="2ce69-110">`Set-Content` 是一个字符串处理 cmdlet，用于写入新内容或替换文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="2ce69-111">`Set-Content` 替换现有内容，不同于将 `Add-Content` 内容追加到文件的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ce69-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="2ce69-112">若要将内容发送到 `Set-Content` ，可以在命令行上使用 **Value** 参数或通过管道发送内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="2ce69-113">如果需要为以下示例创建文件或目录，请参阅 " [新建项](New-Item.md)"。</span><span class="sxs-lookup"><span data-stu-id="2ce69-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="2ce69-114">示例</span><span class="sxs-lookup"><span data-stu-id="2ce69-114">EXAMPLES</span></span>

### <span data-ttu-id="2ce69-115">示例1：替换目录中多个文件的内容</span><span class="sxs-lookup"><span data-stu-id="2ce69-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="2ce69-116">此示例替换当前目录中多个文件的内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-116">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="2ce69-117">`Get-ChildItem`Cmdlet 使用 **Path** 参数列出以当前目录开头的 **.txt** 文件。 `Test*`</span><span class="sxs-lookup"><span data-stu-id="2ce69-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="2ce69-118">`Set-Content`Cmdlet 使用 **Path** 参数指定 `Test*.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="2ce69-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="2ce69-119">**Value** 参数提供替换每个文件中的现有内容的文本字符串 **Hello、World** 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="2ce69-120">`Get-Content`Cmdlet 使用 **Path** 参数指定 `Test*.txt` 文件，并在 PowerShell 控制台中显示每个文件的内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="2ce69-121">示例2：创建新文件并写入内容</span><span class="sxs-lookup"><span data-stu-id="2ce69-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="2ce69-122">此示例将创建一个新文件，并将当前日期和时间写入文件。</span><span class="sxs-lookup"><span data-stu-id="2ce69-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="2ce69-123">`Set-Content` 使用 **Path** 和 **Value** 参数在当前目录中创建一个名为 **DateTime.txt** 的新文件。</span><span class="sxs-lookup"><span data-stu-id="2ce69-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="2ce69-124">**值** 参数用于 `Get-Date` 获取当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2ce69-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="2ce69-125">`Set-Content` 将 **DateTime** 对象作为字符串写入到文件中。</span><span class="sxs-lookup"><span data-stu-id="2ce69-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="2ce69-126">`Get-Content`Cmdlet 使用 **Path** 参数在 PowerShell 控制台中显示 **DateTime.txt** 的内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="2ce69-127">示例 3：在文件中替换文本</span><span class="sxs-lookup"><span data-stu-id="2ce69-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="2ce69-128">此命令替换现有文件中的所有 word 实例。</span><span class="sxs-lookup"><span data-stu-id="2ce69-128">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="2ce69-129">`Get-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的 **Notice.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="2ce69-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="2ce69-130">`Get-Content`命令用括号括起来，以便命令在管道下发送前完成。</span><span class="sxs-lookup"><span data-stu-id="2ce69-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="2ce69-131">**Notice.txt** 文件的内容将通过管道向下发送到 `ForEach-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ce69-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="2ce69-132">`ForEach-Object`使用自动变量 `$_` ，并将每次出现 **Warning** 的警告 **Caution** 替换为警告。</span><span class="sxs-lookup"><span data-stu-id="2ce69-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="2ce69-133">对象通过管道向下发送到 `Set-Content` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ce69-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="2ce69-134">`Set-Content` 使用 **Path** 参数指定 **Notice.txt** 文件，并将更新的内容写入文件。</span><span class="sxs-lookup"><span data-stu-id="2ce69-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="2ce69-135">最后一个 `Get-Content` cmdlet 在 PowerShell 控制台中显示更新的文件内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="2ce69-136">示例4：使用筛选器与 Set-Content</span><span class="sxs-lookup"><span data-stu-id="2ce69-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="2ce69-137">可以为 cmdlet 指定筛选器 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="2ce69-138">使用筛选器限定 **路径** 参数时，需要包含一个尾随星号 (`*`) ，以指示路径的内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="2ce69-139">以下命令将目录中的所有文件的内容设置 `*.txt` `C:\Temp` 为空 **值** 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="2ce69-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ce69-140">PARAMETERS</span></span>

### <span data-ttu-id="2ce69-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="2ce69-141">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="2ce69-142">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="2ce69-142">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="2ce69-143">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-143">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="2ce69-144">-Encoding</span><span class="sxs-lookup"><span data-stu-id="2ce69-144">-Encoding</span></span>

<span data-ttu-id="2ce69-145">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="2ce69-145">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="2ce69-146">默认值是 `Default`。</span><span class="sxs-lookup"><span data-stu-id="2ce69-146">The default value is `Default`.</span></span>

<span data-ttu-id="2ce69-147">Encoding 是 FileSystem 提供程序添加到的动态参数 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-147">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="2ce69-148">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="2ce69-148">This parameter works only in file system drives.</span></span>

<span data-ttu-id="2ce69-149">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ce69-149">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2ce69-150">`Ascii` 使用 ASCII (7 位) 字符集。</span><span class="sxs-lookup"><span data-stu-id="2ce69-150">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="2ce69-151">`BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="2ce69-151">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="2ce69-152">`BigEndianUTF32` 使用带有大字节序字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="2ce69-152">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="2ce69-153">`Byte` 将一组字符编码为一个字节序列。</span><span class="sxs-lookup"><span data-stu-id="2ce69-153">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="2ce69-154">`Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-154">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="2ce69-155">`Oem` 使用与系统的当前 OEM 代码页相对应的编码。</span><span class="sxs-lookup"><span data-stu-id="2ce69-155">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="2ce69-156">`String` 与 `Unicode` 相同。</span><span class="sxs-lookup"><span data-stu-id="2ce69-156">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="2ce69-157">`Unicode` 使用带有小 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="2ce69-157">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="2ce69-158">`Unknown` 与 `Unicode` 相同。</span><span class="sxs-lookup"><span data-stu-id="2ce69-158">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="2ce69-159">`UTF7` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="2ce69-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="2ce69-160">`UTF8` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="2ce69-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="2ce69-161">`UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="2ce69-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="2ce69-162">Encoding 是 FileSystem 提供程序添加到的动态参数 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-162">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="2ce69-163">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="2ce69-163">This parameter works only in file system drives.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce69-164">-Exclude</span><span class="sxs-lookup"><span data-stu-id="2ce69-164">-Exclude</span></span>

<span data-ttu-id="2ce69-165">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="2ce69-165">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="2ce69-166">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="2ce69-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2ce69-167">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="2ce69-167">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="2ce69-168">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2ce69-168">Wildcard characters are permitted.</span></span> <span data-ttu-id="2ce69-169">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-169">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="2ce69-170">-Filter</span><span class="sxs-lookup"><span data-stu-id="2ce69-170">-Filter</span></span>

<span data-ttu-id="2ce69-171">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2ce69-171">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="2ce69-172">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ce69-172">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="2ce69-173">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="2ce69-173">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="2ce69-174">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="2ce69-174">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="2ce69-175">-Force</span><span class="sxs-lookup"><span data-stu-id="2ce69-175">-Force</span></span>

<span data-ttu-id="2ce69-176">强制该 cmdlet 设置文件内容（即使该文件是只读的）。</span><span class="sxs-lookup"><span data-stu-id="2ce69-176">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="2ce69-177">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="2ce69-177">Implementation varies from provider to provider.</span></span> <span data-ttu-id="2ce69-178">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="2ce69-179">**Force** 参数不会覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="2ce69-179">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="2ce69-180">-Include</span><span class="sxs-lookup"><span data-stu-id="2ce69-180">-Include</span></span>

<span data-ttu-id="2ce69-181">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="2ce69-181">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="2ce69-182">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="2ce69-182">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2ce69-183">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="2ce69-183">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="2ce69-184">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2ce69-184">Wildcard characters are permitted.</span></span> <span data-ttu-id="2ce69-185">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-185">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="2ce69-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2ce69-186">-LiteralPath</span></span>

<span data-ttu-id="2ce69-187">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="2ce69-187">Specifies a path to one or more locations.</span></span> <span data-ttu-id="2ce69-188">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="2ce69-188">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="2ce69-189">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="2ce69-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2ce69-190">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="2ce69-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2ce69-191">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="2ce69-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="2ce69-192">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-192">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ce69-193">-NoNewline</span><span class="sxs-lookup"><span data-stu-id="2ce69-193">-NoNewline</span></span>

<span data-ttu-id="2ce69-194">输入对象的字符串表示形式连接起来以形成输出。</span><span class="sxs-lookup"><span data-stu-id="2ce69-194">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="2ce69-195">不会在输出字符串之间插入空格或换行符。</span><span class="sxs-lookup"><span data-stu-id="2ce69-195">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="2ce69-196">在最后一个输出字符串之后不添加任何行。</span><span class="sxs-lookup"><span data-stu-id="2ce69-196">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="2ce69-197">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2ce69-197">-PassThru</span></span>

<span data-ttu-id="2ce69-198">返回一个表示内容的对象。</span><span class="sxs-lookup"><span data-stu-id="2ce69-198">Returns an object that represents the content.</span></span> <span data-ttu-id="2ce69-199">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="2ce69-199">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2ce69-200">-Path</span><span class="sxs-lookup"><span data-stu-id="2ce69-200">-Path</span></span>

<span data-ttu-id="2ce69-201">指定接受内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="2ce69-201">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="2ce69-202">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2ce69-202">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2ce69-203">-Stream</span><span class="sxs-lookup"><span data-stu-id="2ce69-203">-Stream</span></span>

<span data-ttu-id="2ce69-204">指定内容的备用数据流。</span><span class="sxs-lookup"><span data-stu-id="2ce69-204">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="2ce69-205">如果该流不存在，则此 cmdlet 将创建它。</span><span class="sxs-lookup"><span data-stu-id="2ce69-205">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="2ce69-206">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="2ce69-206">Wildcard characters are not supported.</span></span>

<span data-ttu-id="2ce69-207">**Stream** 是 **FileSystem** 提供程序添加到的动态参数 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-207">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="2ce69-208">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="2ce69-208">This parameter works only in file system drives.</span></span>

<span data-ttu-id="2ce69-209">可以使用 `Set-Content` cmdlet 更改区域的内容 **。标识符** 备用数据流。</span><span class="sxs-lookup"><span data-stu-id="2ce69-209">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="2ce69-210">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="2ce69-210">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="2ce69-211">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ce69-211">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="2ce69-212">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2ce69-212">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2ce69-213">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="2ce69-213">-UseTransaction</span></span>

<span data-ttu-id="2ce69-214">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="2ce69-214">Includes the command in the active transaction.</span></span> <span data-ttu-id="2ce69-215">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="2ce69-215">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="2ce69-216">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-216">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce69-217">-Value</span><span class="sxs-lookup"><span data-stu-id="2ce69-217">-Value</span></span>

<span data-ttu-id="2ce69-218">为项指定新的内容。</span><span class="sxs-lookup"><span data-stu-id="2ce69-218">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="2ce69-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2ce69-219">-Confirm</span></span>

<span data-ttu-id="2ce69-220">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="2ce69-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2ce69-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2ce69-221">-WhatIf</span></span>

<span data-ttu-id="2ce69-222">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="2ce69-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2ce69-223">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2ce69-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2ce69-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ce69-224">CommonParameters</span></span>

<span data-ttu-id="2ce69-225">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-225">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="2ce69-226">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-226">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2ce69-227">输入</span><span class="sxs-lookup"><span data-stu-id="2ce69-227">INPUTS</span></span>

### <span data-ttu-id="2ce69-228">System.Object</span><span class="sxs-lookup"><span data-stu-id="2ce69-228">System.Object</span></span>

<span data-ttu-id="2ce69-229">可以通过管道将包含项的新值的对象传递给 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-229">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="2ce69-230">输出</span><span class="sxs-lookup"><span data-stu-id="2ce69-230">OUTPUTS</span></span>

### <span data-ttu-id="2ce69-231">None 或 System.String</span><span class="sxs-lookup"><span data-stu-id="2ce69-231">None or System.String</span></span>

<span data-ttu-id="2ce69-232">当使用 **PassThru** 参数时，将 `Set-Content` 生成表示内容的 **system.string** 对象。</span><span class="sxs-lookup"><span data-stu-id="2ce69-232">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="2ce69-233">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="2ce69-233">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2ce69-234">注释</span><span class="sxs-lookup"><span data-stu-id="2ce69-234">NOTES</span></span>

- <span data-ttu-id="2ce69-235">还可以 `Set-Content` 通过其内置别名来引用 `sc` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-235">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="2ce69-236">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-236">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="2ce69-237">`Set-Content` 用于字符串处理。</span><span class="sxs-lookup"><span data-stu-id="2ce69-237">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="2ce69-238">如果将非字符串对象通过管道传递给 `Set-Content` ，它会在写入之前将对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="2ce69-238">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="2ce69-239">若要将对象写入文件，请使用 `Out-File` 。</span><span class="sxs-lookup"><span data-stu-id="2ce69-239">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="2ce69-240">`Set-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="2ce69-240">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="2ce69-241">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="2ce69-241">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="2ce69-242">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce69-242">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="2ce69-243">相关链接</span><span class="sxs-lookup"><span data-stu-id="2ce69-243">RELATED LINKS</span></span>

[<span data-ttu-id="2ce69-244">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="2ce69-244">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="2ce69-245">about_Automatic_Variables md</span><span class="sxs-lookup"><span data-stu-id="2ce69-245">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="2ce69-246">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2ce69-246">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="2ce69-247">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="2ce69-247">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="2ce69-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="2ce69-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="2ce69-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="2ce69-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="2ce69-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="2ce69-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="2ce69-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="2ce69-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="2ce69-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="2ce69-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="2ce69-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="2ce69-253">New-Item</span></span>](New-Item.md)
