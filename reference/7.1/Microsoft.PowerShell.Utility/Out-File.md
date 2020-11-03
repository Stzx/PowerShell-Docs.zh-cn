---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: 3a3d431276074d7c2b66b442307071076fdfebd5
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "93199439"
---
# <span data-ttu-id="d1434-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="d1434-103">Out-File</span></span>

## <span data-ttu-id="d1434-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d1434-104">SYNOPSIS</span></span>
<span data-ttu-id="d1434-105">将输出发送到文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-105">Sends output to a file.</span></span>

## <span data-ttu-id="d1434-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1434-106">SYNTAX</span></span>

### <span data-ttu-id="d1434-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="d1434-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d1434-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="d1434-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d1434-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1434-109">DESCRIPTION</span></span>

<span data-ttu-id="d1434-110">`Out-File`Cmdlet 可将输出发送到文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="d1434-111">它会隐式使用 PowerShell 的格式化系统以写入文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="d1434-112">文件接收与终端相同的显示表示形式。</span><span class="sxs-lookup"><span data-stu-id="d1434-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="d1434-113">这意味着，如果所有输入对象都是字符串，则输出可能不适合进行编程处理。</span><span class="sxs-lookup"><span data-stu-id="d1434-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="d1434-114">需要为输出指定参数时，请使用 `Out-File` （而不是重定向运算符） (`>`) 。</span><span class="sxs-lookup"><span data-stu-id="d1434-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="d1434-115">有关重定向的详细信息，请参阅 [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="d1434-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="d1434-116">示例</span><span class="sxs-lookup"><span data-stu-id="d1434-116">EXAMPLES</span></span>

### <span data-ttu-id="d1434-117">示例1：发送输出并创建文件</span><span class="sxs-lookup"><span data-stu-id="d1434-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="d1434-118">此示例显示了如何将本地计算机的进程的列表发送给文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="d1434-119">如果文件不存在，则 `Out-File` 在指定的路径中创建文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

<span data-ttu-id="d1434-120">`Get-Process`Cmdlet 将获取在本地计算机上运行的进程的列表。</span><span class="sxs-lookup"><span data-stu-id="d1434-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="d1434-121">**进程** 对象将通过管道向下发送到 `Out-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1434-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="d1434-122">`Out-File` 使用 **FilePath** 参数，并在当前目录中创建一个名为 **Process.txt** 的文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="d1434-123">此 `Get-Content` 命令从文件中获取内容，并在 PowerShell 控制台中显示内容。</span><span class="sxs-lookup"><span data-stu-id="d1434-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="d1434-124">示例2：防止覆盖现有文件</span><span class="sxs-lookup"><span data-stu-id="d1434-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="d1434-125">此示例可防止覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="d1434-126">默认情况下，将 `Out-File` 覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="d1434-127">`Get-Process`Cmdlet 将获取在本地计算机上运行的进程的列表。</span><span class="sxs-lookup"><span data-stu-id="d1434-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="d1434-128">**进程** 对象将通过管道向下发送到 `Out-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1434-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="d1434-129">`Out-File` 使用 **FilePath** 参数，并尝试写入当前目录中名为 **Process.txt** 的文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="d1434-130">**NoClobber** 参数可防止文件被覆盖，并显示一条消息，指出该文件已存在。</span><span class="sxs-lookup"><span data-stu-id="d1434-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="d1434-131">示例3：将输出发送到 ASCII 格式的文件</span><span class="sxs-lookup"><span data-stu-id="d1434-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="d1434-132">此示例演示如何使用特定的编码类型对输出进行编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="d1434-133">`Get-Process`Cmdlet 将获取在本地计算机上运行的进程的列表。</span><span class="sxs-lookup"><span data-stu-id="d1434-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="d1434-134">**进程** 对象存储在变量中 `$Procs` 。</span><span class="sxs-lookup"><span data-stu-id="d1434-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="d1434-135">`Out-File` 使用 **FilePath** 参数，并在当前目录中创建一个名为 **Process.txt** 的文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="d1434-136">**InputObject** 参数将中的进程对象传递 `$Procs` 给 **Process.txt** 的文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt** .</span></span> <span data-ttu-id="d1434-137">**Encoding** 参数将输出转换为 **ASCII** 格式。</span><span class="sxs-lookup"><span data-stu-id="d1434-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="d1434-138">**Width** 参数将文件中的每一行限制为50个字符，因此某些数据可能会被截断。</span><span class="sxs-lookup"><span data-stu-id="d1434-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="d1434-139">示例4：使用提供程序并将输出发送到文件</span><span class="sxs-lookup"><span data-stu-id="d1434-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="d1434-140">此示例演示 `Out-File` 当你不在 **FileSystem** 提供程序驱动器中时如何使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1434-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="d1434-141">使用 `Get-PSProvider` cmdlet 查看本地计算机上的提供程序。</span><span class="sxs-lookup"><span data-stu-id="d1434-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="d1434-142">有关详细信息，请参阅 [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="d1434-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

<span data-ttu-id="d1434-143">该 `Set-Location` 命令使用 **Path** 参数将当前位置设置为注册表提供程序 `Alias:` 。</span><span class="sxs-lookup"><span data-stu-id="d1434-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="d1434-144">`Get-Location`Cmdlet 显示的完整路径 `Alias:` 。</span><span class="sxs-lookup"><span data-stu-id="d1434-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="d1434-145">`Get-ChildItem` 将对象向下发送到 `Out-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1434-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="d1434-146">`Out-File` 使用 **FilePath** 参数指定输出的完整路径和文件名， **C:\TestDir\AliasNames.txt** 。</span><span class="sxs-lookup"><span data-stu-id="d1434-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt** .</span></span> <span data-ttu-id="d1434-147">`Get-Content`Cmdlet 使用 **Path** 参数，并在 PowerShell 控制台中显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d1434-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="d1434-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1434-148">PARAMETERS</span></span>

### <span data-ttu-id="d1434-149">-Append</span><span class="sxs-lookup"><span data-stu-id="d1434-149">-Append</span></span>

<span data-ttu-id="d1434-150">将输出添加到现有文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="d1434-150">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="d1434-151">-Encoding</span><span class="sxs-lookup"><span data-stu-id="d1434-151">-Encoding</span></span>

<span data-ttu-id="d1434-152">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="d1434-152">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="d1434-153">默认值是 `utf8NoBOM`。</span><span class="sxs-lookup"><span data-stu-id="d1434-153">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="d1434-154">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1434-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="d1434-155">`ascii`：使用 ASCII (7 位) 字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="d1434-156">`bigendianunicode`：使用大字节序字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d1434-157">`bigendianutf32`：使用大字节序字节顺序编码为32格式。</span><span class="sxs-lookup"><span data-stu-id="d1434-157">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d1434-158">`oem`：使用 MS-DOS 和控制台程序的默认编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-158">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="d1434-159">`unicode`：使用小 endian 字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-159">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="d1434-160">`utf7`：以 UTF-7 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-160">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="d1434-161">`utf8`：以 UTF-8 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-161">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="d1434-162">`utf8BOM`：以 UTF-8 格式编码 (BOM) </span><span class="sxs-lookup"><span data-stu-id="d1434-162">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d1434-163">`utf8NoBOM`：以 UTF-8 格式编码，而不包含字节顺序标记 (BOM) </span><span class="sxs-lookup"><span data-stu-id="d1434-163">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d1434-164">`utf32`：以32格式编码。</span><span class="sxs-lookup"><span data-stu-id="d1434-164">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="d1434-165">从 PowerShell 6.2 开始， **Encoding** 参数还允许已注册代码页的数字 id (如 `-Encoding 1251` (如) 所注册代码页的) 或字符串名称 `-Encoding "windows-1251"` 。</span><span class="sxs-lookup"><span data-stu-id="d1434-165">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="d1434-166">有关详细信息，请参阅 .NET 文档中的[编码。](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)</span><span class="sxs-lookup"><span data-stu-id="d1434-166">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="d1434-167">不建议使用 **utf-7** \*。</span><span class="sxs-lookup"><span data-stu-id="d1434-167">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="d1434-168">在 PowerShell 7.1 中，如果 `utf7` 为 **编码** 参数指定，则会写入警告。</span><span class="sxs-lookup"><span data-stu-id="d1434-168">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1434-169">-FilePath</span><span class="sxs-lookup"><span data-stu-id="d1434-169">-FilePath</span></span>

<span data-ttu-id="d1434-170">指定输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d1434-170">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1434-171">-Force</span><span class="sxs-lookup"><span data-stu-id="d1434-171">-Force</span></span>

<span data-ttu-id="d1434-172">重写只读特性并覆盖现有的只读文件。</span><span class="sxs-lookup"><span data-stu-id="d1434-172">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="d1434-173">**Force** 参数不会覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="d1434-173">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="d1434-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d1434-174">-InputObject</span></span>

<span data-ttu-id="d1434-175">指定要写入文件的对象。</span><span class="sxs-lookup"><span data-stu-id="d1434-175">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="d1434-176">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="d1434-176">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d1434-177">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d1434-177">-LiteralPath</span></span>

<span data-ttu-id="d1434-178">指定输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d1434-178">Specifies the path to the output file.</span></span> <span data-ttu-id="d1434-179">**LiteralPath** 参数的使用方式与键入的完全相同。</span><span class="sxs-lookup"><span data-stu-id="d1434-179">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="d1434-180">不接受通配符。</span><span class="sxs-lookup"><span data-stu-id="d1434-180">Wildcard characters are not accepted.</span></span> <span data-ttu-id="d1434-181">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="d1434-181">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d1434-182">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="d1434-182">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="d1434-183">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d1434-183">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d1434-184">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="d1434-184">-NoClobber</span></span>

<span data-ttu-id="d1434-185">**NoClobber** 可防止覆盖现有文件，并显示一条消息，指出该文件已存在。</span><span class="sxs-lookup"><span data-stu-id="d1434-185">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="d1434-186">默认情况下，如果指定路径中存在文件，则 `Out-File` 将覆盖该文件而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="d1434-186">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1434-187">-NoNewline</span><span class="sxs-lookup"><span data-stu-id="d1434-187">-NoNewline</span></span>

<span data-ttu-id="d1434-188">指定写入文件的内容不以换行符结尾。</span><span class="sxs-lookup"><span data-stu-id="d1434-188">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="d1434-189">输入对象的字符串表示形式连接起来以形成输出。</span><span class="sxs-lookup"><span data-stu-id="d1434-189">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="d1434-190">不会在输出字符串之间插入空格或换行符。</span><span class="sxs-lookup"><span data-stu-id="d1434-190">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="d1434-191">在最后一个输出字符串之后不添加任何行。</span><span class="sxs-lookup"><span data-stu-id="d1434-191">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="d1434-192">-Width</span><span class="sxs-lookup"><span data-stu-id="d1434-192">-Width</span></span>

<span data-ttu-id="d1434-193">指定输出的每一行中的字符数。</span><span class="sxs-lookup"><span data-stu-id="d1434-193">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="d1434-194">将截断任何额外字符，不换行。</span><span class="sxs-lookup"><span data-stu-id="d1434-194">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="d1434-195">如果未使用此参数，则由主机的特征确定宽度。</span><span class="sxs-lookup"><span data-stu-id="d1434-195">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="d1434-196">PowerShell 控制台的默认值为80个字符。</span><span class="sxs-lookup"><span data-stu-id="d1434-196">The default for the PowerShell console is 80 characters.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1434-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d1434-197">-Confirm</span></span>

<span data-ttu-id="d1434-198">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="d1434-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d1434-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d1434-199">-WhatIf</span></span>

<span data-ttu-id="d1434-200">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d1434-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d1434-201">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="d1434-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d1434-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d1434-202">CommonParameters</span></span>

<span data-ttu-id="d1434-203">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d1434-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1434-204">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d1434-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1434-205">输入</span><span class="sxs-lookup"><span data-stu-id="d1434-205">INPUTS</span></span>

### <span data-ttu-id="d1434-206">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="d1434-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d1434-207">可以通过管道将任何对象传递给 `Out-File` 。</span><span class="sxs-lookup"><span data-stu-id="d1434-207">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="d1434-208">输出</span><span class="sxs-lookup"><span data-stu-id="d1434-208">OUTPUTS</span></span>

### <span data-ttu-id="d1434-209">无</span><span class="sxs-lookup"><span data-stu-id="d1434-209">None</span></span>

<span data-ttu-id="d1434-210">`Out-File` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="d1434-210">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="d1434-211">注释</span><span class="sxs-lookup"><span data-stu-id="d1434-211">NOTES</span></span>

<span data-ttu-id="d1434-212">输入对象将自动设置为在终端中的格式，但你可以使用 `Format-*` cmdlet 显式控制输出到文件的格式。</span><span class="sxs-lookup"><span data-stu-id="d1434-212">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="d1434-213">例如： `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="d1434-213">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="d1434-214">若要将 PowerShell 命令的输出发送到 `Out-File` cmdlet，请使用管道。</span><span class="sxs-lookup"><span data-stu-id="d1434-214">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="d1434-215">另外，还可以将数据存储在变量中，并使用 **InputObject** 参数将数据传递给 `Out-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1434-215">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="d1434-216">`Out-File` 将数据保存到文件，但不会向管道生成任何输出对象。</span><span class="sxs-lookup"><span data-stu-id="d1434-216">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="d1434-217">相关链接</span><span class="sxs-lookup"><span data-stu-id="d1434-217">RELATED LINKS</span></span>

[<span data-ttu-id="d1434-218">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d1434-218">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="d1434-219">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="d1434-219">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="d1434-220">Out-Default</span><span class="sxs-lookup"><span data-stu-id="d1434-220">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="d1434-221">Out-Host</span><span class="sxs-lookup"><span data-stu-id="d1434-221">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="d1434-222">Out-Null</span><span class="sxs-lookup"><span data-stu-id="d1434-222">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="d1434-223">Out-String</span><span class="sxs-lookup"><span data-stu-id="d1434-223">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="d1434-224">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="d1434-224">Tee-Object</span></span>](Tee-Object.md)

