---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198333"
---
# <span data-ttu-id="02c34-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="02c34-103">Add-Content</span></span>

## <span data-ttu-id="02c34-104">摘要</span><span class="sxs-lookup"><span data-stu-id="02c34-104">SYNOPSIS</span></span>
<span data-ttu-id="02c34-105">向指定的项中添加内容，如向文件中添加字词。</span><span class="sxs-lookup"><span data-stu-id="02c34-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="02c34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="02c34-106">SYNTAX</span></span>

### <span data-ttu-id="02c34-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="02c34-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="02c34-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="02c34-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="02c34-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="02c34-109">DESCRIPTION</span></span>

<span data-ttu-id="02c34-110">`Add-Content`Cmdlet 将内容追加到指定项或文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="02c34-111">可以通过在命令中键入内容或通过指定包含内容的对象来指定内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="02c34-112">如果需要为以下示例创建文件或目录，请参阅 " [新建项](New-Item.md)"。</span><span class="sxs-lookup"><span data-stu-id="02c34-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="02c34-113">示例</span><span class="sxs-lookup"><span data-stu-id="02c34-113">EXAMPLES</span></span>

### <span data-ttu-id="02c34-114">示例1：向所有文本文件添加字符串，但出现异常</span><span class="sxs-lookup"><span data-stu-id="02c34-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="02c34-115">此示例将一个值附加到当前目录中的文本文件，但基于文件的文件名排除文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="02c34-116">`Add-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的所有 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-116">The `Add-Content` cmdlet uses the **Path** parameter to specify all .txt files in the current directory.</span></span> <span data-ttu-id="02c34-117">**Exclude** 参数将忽略与指定模式匹配的文件名。</span><span class="sxs-lookup"><span data-stu-id="02c34-117">The **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="02c34-118">**值** 参数指定写入文件的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="02c34-118">The **Value** parameter specifies the text string that is written to the files.</span></span>

<span data-ttu-id="02c34-119">使用 " [获取内容](Get-Content.md) " 显示这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-119">Use [Get-Content](Get-Content.md) to display the contents of these files.</span></span>

### <span data-ttu-id="02c34-120">示例2：将日期添加到指定文件的末尾</span><span class="sxs-lookup"><span data-stu-id="02c34-120">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="02c34-121">此示例将日期附加到当前目录中的文件，并在 PowerShell 控制台中显示日期。</span><span class="sxs-lookup"><span data-stu-id="02c34-121">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

<span data-ttu-id="02c34-122">`Add-Content`Cmdlet 使用 **Path** 和 **Value** 参数在当前目录中创建两个新文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-122">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create two new files in the current directory.</span></span> <span data-ttu-id="02c34-123">**值** 参数指定 `Get-Date` 用于获取日期并将日期传递到的 cmdlet `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-123">The **Value** parameter specifies the `Get-Date` cmdlet to get the date and passes the date to `Add-Content`.</span></span> <span data-ttu-id="02c34-124">`Add-Content`Cmdlet 将日期写入每个文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-124">The `Add-Content` cmdlet writes the date to each file.</span></span> <span data-ttu-id="02c34-125">**PassThru** 参数传递表示 date 对象的对象。</span><span class="sxs-lookup"><span data-stu-id="02c34-125">The **PassThru** parameter passes an object that represents the date object.</span></span> <span data-ttu-id="02c34-126">由于没有其他 cmdlet 接收传递的对象，因此它显示在 PowerShell 控制台中。</span><span class="sxs-lookup"><span data-stu-id="02c34-126">Because there is no other cmdlet to receive the passed object, it is displayed in the PowerShell console.</span></span> <span data-ttu-id="02c34-127">`Get-Content`Cmdlet 将显示更新的文件 DateTimeFile1。</span><span class="sxs-lookup"><span data-stu-id="02c34-127">The `Get-Content` cmdlet displays the updated file, DateTimeFile1.log.</span></span>

### <span data-ttu-id="02c34-128">示例3：将指定文件的内容添加到另一个文件</span><span class="sxs-lookup"><span data-stu-id="02c34-128">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="02c34-129">此示例从文件中获取内容，并将该内容附加到另一个文件中。</span><span class="sxs-lookup"><span data-stu-id="02c34-129">This example gets the content from a file and appends that content into another file.</span></span>

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="02c34-130">`Add-Content`Cmdlet 使用 **Path** 参数指定当前目录中的新文件，CopyToFile.txt。</span><span class="sxs-lookup"><span data-stu-id="02c34-130">The `Add-Content` cmdlet uses the **Path** parameter to specify the new file in the current directory, CopyToFile.txt.</span></span> <span data-ttu-id="02c34-131">**Value** 参数使用 `Get-Content` cmdlet 来获取文件的内容，CopyFromFile.txt。</span><span class="sxs-lookup"><span data-stu-id="02c34-131">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of the file, CopyFromFile.txt.</span></span> <span data-ttu-id="02c34-132">Cmdlet 两边的括号 `Get-Content` 可确保命令在命令开始前完成 `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-132">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="02c34-133">**值** 参数传递给 `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-133">The **Value** parameter is passed to `Add-Content`.</span></span> <span data-ttu-id="02c34-134">`Add-Content`Cmdlet 将数据追加到 CopyToFile.txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="02c34-134">The `Add-Content` cmdlet appends the data to the CopyToFile.txt file.</span></span> <span data-ttu-id="02c34-135">`Get-Content`Cmdlet 将显示更新后的文件 CopyToFile.txt。</span><span class="sxs-lookup"><span data-stu-id="02c34-135">The `Get-Content` cmdlet displays the updated file, CopyToFile.txt.</span></span>

### <span data-ttu-id="02c34-136">示例4：使用变量将指定文件的内容添加到另一个文件</span><span class="sxs-lookup"><span data-stu-id="02c34-136">Example 4: Use a variable to add the contents of a specified file to another file</span></span>

<span data-ttu-id="02c34-137">此示例从文件中获取内容，并将内容存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="02c34-137">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="02c34-138">变量用于将内容追加到另一个文件中。</span><span class="sxs-lookup"><span data-stu-id="02c34-138">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="02c34-139">`Get-Content`Cmdlet 将获取 CopyFromFile.txt 的内容，并将内容存储在 `$From` 变量中。</span><span class="sxs-lookup"><span data-stu-id="02c34-139">The `Get-Content` cmdlet gets the contents of CopyFromFile.txt and stores the contents in the `$From` variable.</span></span> <span data-ttu-id="02c34-140">`Add-Content`Cmdlet 使用 **Path** 参数来指定当前目录中的 CopyToFile.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-140">The `Add-Content` cmdlet uses the **Path** parameter to specify the CopyToFile.txt file in the current directory.</span></span> <span data-ttu-id="02c34-141">**值** 参数使用 `$From` 变量，并将内容传递给 `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-141">The **Value** parameter uses the `$From` variable and passes the content to `Add-Content`.</span></span> <span data-ttu-id="02c34-142">`Add-Content`Cmdlet 将更新 CopyToFile.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-142">The `Add-Content` cmdlet updates the CopyToFile.txt file.</span></span> <span data-ttu-id="02c34-143">`Get-Content`Cmdlet 将显示 CopyToFile.txt。</span><span class="sxs-lookup"><span data-stu-id="02c34-143">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="02c34-144">示例5：创建新文件并复制内容</span><span class="sxs-lookup"><span data-stu-id="02c34-144">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="02c34-145">此示例将创建一个新文件，并将现有文件的内容复制到新文件中。</span><span class="sxs-lookup"><span data-stu-id="02c34-145">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

<span data-ttu-id="02c34-146">`Add-Content`Cmdlet 使用 **Path** 和 **Value** 参数在当前目录中创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-146">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span> <span data-ttu-id="02c34-147">**Value** 参数使用 `Get-Content` cmdlet 获取现有文件的内容，CopyFromFile.txt。</span><span class="sxs-lookup"><span data-stu-id="02c34-147">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of an existing file, CopyFromFile.txt.</span></span> <span data-ttu-id="02c34-148">Cmdlet 两边的括号 `Get-Content` 可确保命令在命令开始前完成 `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-148">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="02c34-149">**Value** 参数传递 `Add-Content` 更新 NewFile.txt 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-149">The **Value** parameter passes the content to `Add-Content` which updates the NewFile.txt file.</span></span> <span data-ttu-id="02c34-150">`Get-Content`Cmdlet 将显示新文件的内容，NewFile.txt。</span><span class="sxs-lookup"><span data-stu-id="02c34-150">The `Get-Content` cmdlet displays the contents of the new file, NewFile.txt.</span></span>

### <span data-ttu-id="02c34-151">示例6：向只读文件中添加内容</span><span class="sxs-lookup"><span data-stu-id="02c34-151">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="02c34-152">即使 **IsReadOnly** 文件属性设置为 True，此命令也会将该值添加到文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-152">This command adds the value to the file even if the **IsReadOnly** file attribute is set to True.</span></span>
<span data-ttu-id="02c34-153">示例中包含创建只读文件的步骤。</span><span class="sxs-lookup"><span data-stu-id="02c34-153">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

<span data-ttu-id="02c34-154">`New-Item`Cmdlet 使用 **Path** 和 **ItemType** 参数在当前目录中创建 IsReadOnlyTextFile.txt 的文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-154">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file IsReadOnlyTextFile.txt in the current directory.</span></span> <span data-ttu-id="02c34-155">`Set-ItemProperty`Cmdlet 使用 **Name** 和 **Value** 参数将文件的 **IsReadOnly** 属性更改为 True。</span><span class="sxs-lookup"><span data-stu-id="02c34-155">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span> <span data-ttu-id="02c34-156">该 `Get-ChildItem` cmdlet 显示文件为空 (0) 并且 () 具有只读属性 `r` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-156">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span> <span data-ttu-id="02c34-157">`Add-Content`Cmdlet 使用 **Path** 参数指定文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-157">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="02c34-158">**Value** 参数包含要追加到文件中的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="02c34-158">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="02c34-159">**Force** 参数将文本写入只读文件。</span><span class="sxs-lookup"><span data-stu-id="02c34-159">The **Force** parameter writes the text to the read-only file.</span></span> <span data-ttu-id="02c34-160">`Get-Content`Cmdlet 使用 **Path** 参数显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-160">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="02c34-161">若要删除只读属性，请使用命令， `Set-ItemProperty` 并将 **Value** 参数设置为 `False` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-161">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

## <span data-ttu-id="02c34-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="02c34-162">PARAMETERS</span></span>

### <span data-ttu-id="02c34-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="02c34-163">-Confirm</span></span>

<span data-ttu-id="02c34-164">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="02c34-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="02c34-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="02c34-165">-Credential</span></span>

<span data-ttu-id="02c34-166">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="02c34-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="02c34-167">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="02c34-167">The default is the current user.</span></span>

<span data-ttu-id="02c34-168">键入用户名（如 **User01** 或 **Domain01\User01** ）或输入 PSCredential 对象，例如由 Cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-168">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="02c34-169">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="02c34-169">If you type a user name, you will be prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="02c34-170">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="02c34-170">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="02c34-171">-Encoding</span><span class="sxs-lookup"><span data-stu-id="02c34-171">-Encoding</span></span>

<span data-ttu-id="02c34-172">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="02c34-172">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="02c34-173">默认值是 `Default`。</span><span class="sxs-lookup"><span data-stu-id="02c34-173">The default value is `Default`.</span></span>

<span data-ttu-id="02c34-174">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="02c34-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="02c34-175">`Ascii` 使用 ASCII (7 位) 字符集。</span><span class="sxs-lookup"><span data-stu-id="02c34-175">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="02c34-176">`BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="02c34-176">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="02c34-177">`BigEndianUTF32` 使用带有大字节序字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="02c34-177">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="02c34-178">`Byte` 将一组字符编码为一个字节序列。</span><span class="sxs-lookup"><span data-stu-id="02c34-178">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="02c34-179">`Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。</span><span class="sxs-lookup"><span data-stu-id="02c34-179">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="02c34-180">`Oem` 使用与系统的当前 OEM 代码页相对应的编码。</span><span class="sxs-lookup"><span data-stu-id="02c34-180">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="02c34-181">`String` 与 **Unicode** 相同。</span><span class="sxs-lookup"><span data-stu-id="02c34-181">`String` Same as **Unicode** .</span></span>
- <span data-ttu-id="02c34-182">`Unicode` 使用带有小 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="02c34-182">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="02c34-183">`Unknown` 与 **Unicode** 相同。</span><span class="sxs-lookup"><span data-stu-id="02c34-183">`Unknown` Same as **Unicode** .</span></span>
- <span data-ttu-id="02c34-184">`UTF7` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="02c34-184">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="02c34-185">`UTF8` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="02c34-185">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="02c34-186">`UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="02c34-186">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="02c34-187">Encoding 是 FileSystem 提供程序添加到 cmdlet 的动态参数 `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-187">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="02c34-188">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="02c34-188">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="02c34-189">-Exclude</span><span class="sxs-lookup"><span data-stu-id="02c34-189">-Exclude</span></span>

<span data-ttu-id="02c34-190">忽略指定项。</span><span class="sxs-lookup"><span data-stu-id="02c34-190">Omits the specified items.</span></span> <span data-ttu-id="02c34-191">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="02c34-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="02c34-192">输入路径元素或模式，例如 **\* .txt** 。</span><span class="sxs-lookup"><span data-stu-id="02c34-192">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="02c34-193">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="02c34-193">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="02c34-194">-Filter</span><span class="sxs-lookup"><span data-stu-id="02c34-194">-Filter</span></span>

<span data-ttu-id="02c34-195">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="02c34-195">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="02c34-196">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="02c34-196">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="02c34-197">筛选器的语法（包括通配符的使用）取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="02c34-197">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="02c34-198">**筛选器** 比其他参数更有效，因为提供程序在检索对象时应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="02c34-198">**Filters** are more efficient than other parameters because the provider applies filters when objects are retrieved.</span></span> <span data-ttu-id="02c34-199">否则，PowerShell 将在检索对象后处理筛选器。</span><span class="sxs-lookup"><span data-stu-id="02c34-199">Otherwise, PowerShell processes filters after the objects are retrieved.</span></span>

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

### <span data-ttu-id="02c34-200">-Force</span><span class="sxs-lookup"><span data-stu-id="02c34-200">-Force</span></span>

<span data-ttu-id="02c34-201">覆盖只读属性，从而允许你向只读文件中添加内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-201">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="02c34-202">例如， **Force** 将覆盖只读属性或创建目录来完成文件路径，但它不会尝试更改文件权限。</span><span class="sxs-lookup"><span data-stu-id="02c34-202">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="02c34-203">-Include</span><span class="sxs-lookup"><span data-stu-id="02c34-203">-Include</span></span>

<span data-ttu-id="02c34-204">只添加指定项。</span><span class="sxs-lookup"><span data-stu-id="02c34-204">Adds only the specified items.</span></span> <span data-ttu-id="02c34-205">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="02c34-205">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="02c34-206">输入路径元素或模式，例如 **\* .txt** 。</span><span class="sxs-lookup"><span data-stu-id="02c34-206">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="02c34-207">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="02c34-207">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="02c34-208">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="02c34-208">-LiteralPath</span></span>

<span data-ttu-id="02c34-209">指定用于接收其他内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="02c34-209">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="02c34-210">不同于 **Path** ， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="02c34-210">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="02c34-211">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="02c34-211">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="02c34-212">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="02c34-212">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="02c34-213">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="02c34-213">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="02c34-214">-NoNewline</span><span class="sxs-lookup"><span data-stu-id="02c34-214">-NoNewline</span></span>

<span data-ttu-id="02c34-215">指示此 cmdlet 不会将新的行或回车添加到内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-215">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="02c34-216">输入对象的字符串表示形式连接起来以形成输出。</span><span class="sxs-lookup"><span data-stu-id="02c34-216">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="02c34-217">不会在输出字符串之间插入空格或换行符。</span><span class="sxs-lookup"><span data-stu-id="02c34-217">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="02c34-218">在最后一个输出字符串之后不添加任何行。</span><span class="sxs-lookup"><span data-stu-id="02c34-218">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="02c34-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="02c34-219">-PassThru</span></span>

<span data-ttu-id="02c34-220">返回一个表示所添加内容的对象。</span><span class="sxs-lookup"><span data-stu-id="02c34-220">Returns an object representing the added content.</span></span> <span data-ttu-id="02c34-221">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="02c34-221">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="02c34-222">-Path</span><span class="sxs-lookup"><span data-stu-id="02c34-222">-Path</span></span>

<span data-ttu-id="02c34-223">指定用于接收其他内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="02c34-223">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="02c34-224">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="02c34-224">Wildcards are permitted.</span></span> <span data-ttu-id="02c34-225">如果指定多个路径，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="02c34-225">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="02c34-226">-Stream</span><span class="sxs-lookup"><span data-stu-id="02c34-226">-Stream</span></span>

<span data-ttu-id="02c34-227">指定内容的备用数据流。</span><span class="sxs-lookup"><span data-stu-id="02c34-227">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="02c34-228">如果该流不存在，则此 cmdlet 将创建它。</span><span class="sxs-lookup"><span data-stu-id="02c34-228">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="02c34-229">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="02c34-229">Wildcard characters are not supported.</span></span>

<span data-ttu-id="02c34-230">**Stream** 是 FileSystem 提供程序添加到的动态参数 `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-230">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="02c34-231">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="02c34-231">This parameter works only in file system drives.</span></span>

<span data-ttu-id="02c34-232">可以使用 `Add-Content` cmdlet 更改区域的内容 **。标识符** 备用数据流。</span><span class="sxs-lookup"><span data-stu-id="02c34-232">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="02c34-233">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="02c34-233">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="02c34-234">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02c34-234">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="02c34-235">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="02c34-235">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="02c34-236">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="02c34-236">-UseTransaction</span></span>

<span data-ttu-id="02c34-237">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="02c34-237">Includes the command in the active transaction.</span></span> <span data-ttu-id="02c34-238">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="02c34-238">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="02c34-239">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="02c34-239">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="02c34-240">-Value</span><span class="sxs-lookup"><span data-stu-id="02c34-240">-Value</span></span>

<span data-ttu-id="02c34-241">指定要添加的内容。</span><span class="sxs-lookup"><span data-stu-id="02c34-241">Specifies the content to be added.</span></span> <span data-ttu-id="02c34-242">键入带引号的字符串，如 **此数据仅供内部使用** ，或指定包含内容的对象，例如生成的 **DateTime** 对象 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-242">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="02c34-243">不能通过键入文件路径来指定文件内容，因为路径只是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="02c34-243">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="02c34-244">您可以使用 `Get-Content` 命令获取内容并将其传递给 **Value** 参数。</span><span class="sxs-lookup"><span data-stu-id="02c34-244">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

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

### <span data-ttu-id="02c34-245">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="02c34-245">-WhatIf</span></span>

<span data-ttu-id="02c34-246">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="02c34-246">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="02c34-247">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="02c34-247">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="02c34-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="02c34-248">CommonParameters</span></span>

<span data-ttu-id="02c34-249">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-249">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="02c34-250">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="02c34-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="02c34-251">输入</span><span class="sxs-lookup"><span data-stu-id="02c34-251">INPUTS</span></span>

### <span data-ttu-id="02c34-252">System.web、System.web 和 System.object</span><span class="sxs-lookup"><span data-stu-id="02c34-252">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="02c34-253">可以通过管道将值、路径或凭据传递给 `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-253">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="02c34-254">输出</span><span class="sxs-lookup"><span data-stu-id="02c34-254">OUTPUTS</span></span>

### <span data-ttu-id="02c34-255">None 或 System.String</span><span class="sxs-lookup"><span data-stu-id="02c34-255">None or System.String</span></span>

<span data-ttu-id="02c34-256">当使用 **PassThru** 参数时，将 `Add-Content` 生成表示内容的 **system.string** 对象。</span><span class="sxs-lookup"><span data-stu-id="02c34-256">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="02c34-257">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="02c34-257">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="02c34-258">注释</span><span class="sxs-lookup"><span data-stu-id="02c34-258">NOTES</span></span>

<span data-ttu-id="02c34-259">将对象通过管道传递给时 `Add-Content` ，对象会在添加到项之前转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="02c34-259">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="02c34-260">对象类型决定字符串格式，但该格式可能不同于该对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="02c34-260">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="02c34-261">若要控制字符串格式，请使用发送 cmdlet 的格式设置参数。</span><span class="sxs-lookup"><span data-stu-id="02c34-261">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>

<span data-ttu-id="02c34-262">还可以 `Add-Content` 通过其内置别名来引用 `ac` 。</span><span class="sxs-lookup"><span data-stu-id="02c34-262">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="02c34-263">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="02c34-263">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="02c34-264">`Add-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="02c34-264">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="02c34-265">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="02c34-265">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="02c34-266">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="02c34-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="02c34-267">相关链接</span><span class="sxs-lookup"><span data-stu-id="02c34-267">RELATED LINKS</span></span>

[<span data-ttu-id="02c34-268">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="02c34-268">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="02c34-269">about_Providers</span><span class="sxs-lookup"><span data-stu-id="02c34-269">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="02c34-270">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="02c34-270">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="02c34-271">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="02c34-271">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="02c34-272">Get-Content</span><span class="sxs-lookup"><span data-stu-id="02c34-272">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="02c34-273">Get-Item</span><span class="sxs-lookup"><span data-stu-id="02c34-273">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="02c34-274">New-Item</span><span class="sxs-lookup"><span data-stu-id="02c34-274">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="02c34-275">Set-Content</span><span class="sxs-lookup"><span data-stu-id="02c34-275">Set-Content</span></span>](Set-Content.md)
