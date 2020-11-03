---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8e1557bca62ade784bd5b4ed5cb170bbf079b423
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "93199349"
---
# <span data-ttu-id="fd082-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="fd082-103">Export-Clixml</span></span>

## <span data-ttu-id="fd082-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fd082-104">SYNOPSIS</span></span>
<span data-ttu-id="fd082-105">创建一个或多个对象的基于 XML 的表示形式，并将其存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="fd082-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="fd082-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd082-106">SYNTAX</span></span>

### <span data-ttu-id="fd082-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="fd082-107">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fd082-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="fd082-108">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fd082-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd082-109">DESCRIPTION</span></span>

<span data-ttu-id="fd082-110">`Export-Clixml`Cmdlet (CLI) 基于 XML 的对象或对象的表示形式创建公共语言基础结构，并将其存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="fd082-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="fd082-111">然后，可以使用 `Import-Clixml` cmdlet 基于该文件的内容重新创建已保存的对象。</span><span class="sxs-lookup"><span data-stu-id="fd082-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="fd082-112">有关 CLI 的详细信息，请参阅 [语言独立性](/dotnet/standard/language-independence)。</span><span class="sxs-lookup"><span data-stu-id="fd082-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="fd082-113">此 cmdlet 类似于 `ConvertTo-Xml` ，不同之处在于将 `Export-Clixml` 生成的 XML 存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="fd082-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="fd082-114">`ConvertTo-XML` 返回 XML，因此你可以继续在 PowerShell 中处理它。</span><span class="sxs-lookup"><span data-stu-id="fd082-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="fd082-115">Windows 计算机上的一个有价值的用途 `Export-Clixml` 是将凭据和安全字符串作为 XML 安全地导出。</span><span class="sxs-lookup"><span data-stu-id="fd082-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="fd082-116">有关示例，请参阅示例3。</span><span class="sxs-lookup"><span data-stu-id="fd082-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="fd082-117">示例</span><span class="sxs-lookup"><span data-stu-id="fd082-117">EXAMPLES</span></span>

### <span data-ttu-id="fd082-118">示例1：将字符串导出到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="fd082-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="fd082-119">此示例将创建一个 XML 文件，该文件存储在当前目录中， **这是一个测试** 字符串的表示形式。</span><span class="sxs-lookup"><span data-stu-id="fd082-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="fd082-120">该字符串 `This is a test` 沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="fd082-120">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="fd082-121">`Export-Clixml` 使用 **Path** 参数 `sample.xml` 在当前目录中创建一个名为的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="fd082-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="fd082-122">示例2：将对象导出到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="fd082-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="fd082-123">此示例演示如何将对象导出到 XML 文件，然后通过从该文件导入 XML 来创建对象。</span><span class="sxs-lookup"><span data-stu-id="fd082-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="fd082-124">`Get-Acl`Cmdlet 将获取该文件的安全描述符 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="fd082-125">它将对象向下发送到管道，以将安全描述符传递给 `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="fd082-126">对象的基于 XML 的表示形式存储在名为的文件中 `FileACL.xml` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="fd082-127">`Import-Clixml`Cmdlet 可从该文件中的 XML 创建对象 `FileACL.xml` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="fd082-128">然后，它将对象保存在 `$fileacl` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd082-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="fd082-129">示例3：在 Windows 上加密已导出的凭据对象</span><span class="sxs-lookup"><span data-stu-id="fd082-129">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="fd082-130">在此示例中，给定通过运行 cmdlet 存储在变量中的凭据 `$Credential` `Get-Credential` ，可以运行 `Export-Clixml` cmdlet 将凭据保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="fd082-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd082-131">`Export-Clixml` 仅导出 Windows 上的加密凭据。</span><span class="sxs-lookup"><span data-stu-id="fd082-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="fd082-132">在非 Windows 操作系统（如 macOS 和 Linux）上，凭据将导出为作为 Unicode 字符数组存储的纯文本。</span><span class="sxs-lookup"><span data-stu-id="fd082-132">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="fd082-133">这会提供一些模糊处理，但不提供加密。</span><span class="sxs-lookup"><span data-stu-id="fd082-133">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="fd082-134">`Export-Clixml`Cmdlet 使用 Windows[数据保护 API](/previous-versions/windows/apps/hh464970(v=win.10))加密凭据对象。</span><span class="sxs-lookup"><span data-stu-id="fd082-134">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="fd082-135">加密可确保只有该计算机上的用户帐户才能解密 credential 对象的内容。</span><span class="sxs-lookup"><span data-stu-id="fd082-135">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="fd082-136">导出的 `CLIXML` 文件不能用于其他计算机或其他用户。</span><span class="sxs-lookup"><span data-stu-id="fd082-136">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="fd082-137">在此示例中，存储凭据的文件由表示 `TestScript.ps1.credential` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-137">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="fd082-138">将 **TestScript** 替换为要在其中加载凭据的脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="fd082-138">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="fd082-139">将凭据对象向下发送到管道 `Export-Clixml` ，并将其保存到在 `$Credxmlpath` 第一个命令中指定的路径。</span><span class="sxs-lookup"><span data-stu-id="fd082-139">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="fd082-140">若要将凭据自动导入脚本，请运行最后两个命令。</span><span class="sxs-lookup"><span data-stu-id="fd082-140">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="fd082-141">运行 `Import-Clixml` 将受保护的凭据对象导入脚本。</span><span class="sxs-lookup"><span data-stu-id="fd082-141">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="fd082-142">此导入消除了在脚本中公开纯文本密码的风险。</span><span class="sxs-lookup"><span data-stu-id="fd082-142">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="fd082-143">示例4：在 Linux 或 macOS 上导出 credential 对象</span><span class="sxs-lookup"><span data-stu-id="fd082-143">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="fd082-144">在此示例中，我们使用 cmdlet 在变量中创建 **PSCredential** `$Credential` `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-144">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="fd082-145">然后，使用将 `Export-Clixml` 凭据保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="fd082-145">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd082-146">`Export-Clixml` 仅导出 Windows 上的加密凭据。</span><span class="sxs-lookup"><span data-stu-id="fd082-146">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="fd082-147">在非 Windows 操作系统（如 macOS 和 Linux）上，凭据将导出为作为 Unicode 字符数组存储的纯文本。</span><span class="sxs-lookup"><span data-stu-id="fd082-147">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="fd082-148">这会提供一些模糊处理，但不提供加密。</span><span class="sxs-lookup"><span data-stu-id="fd082-148">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

<span data-ttu-id="fd082-149">`Get-Content`在此示例中，的输出已截断，以重点关注 XML 文件中的凭据信息。</span><span class="sxs-lookup"><span data-stu-id="fd082-149">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="fd082-150">请注意，密码的纯文本值作为 Unicode 字符数组存储在 XML 文件中，如经过验证 `Format-Hex` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-150">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="fd082-151">因此，对该值进行编码，但不对其进行加密。</span><span class="sxs-lookup"><span data-stu-id="fd082-151">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="fd082-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd082-152">PARAMETERS</span></span>

### <span data-ttu-id="fd082-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd082-153">-Confirm</span></span>

<span data-ttu-id="fd082-154">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="fd082-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd082-155">-Depth</span><span class="sxs-lookup"><span data-stu-id="fd082-155">-Depth</span></span>

<span data-ttu-id="fd082-156">指定 XML 表示形式中所包含的包含对象的级别数。</span><span class="sxs-lookup"><span data-stu-id="fd082-156">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="fd082-157">默认值是 `2`。</span><span class="sxs-lookup"><span data-stu-id="fd082-157">The default value is `2`.</span></span>

<span data-ttu-id="fd082-158">对于文件中的对象类型，可以重写默认值 `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-158">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="fd082-159">有关详细信息，请参阅 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)。</span><span class="sxs-lookup"><span data-stu-id="fd082-159">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd082-160">-Encoding</span><span class="sxs-lookup"><span data-stu-id="fd082-160">-Encoding</span></span>

<span data-ttu-id="fd082-161">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="fd082-161">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="fd082-162">默认值是 `utf8NoBOM`。</span><span class="sxs-lookup"><span data-stu-id="fd082-162">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="fd082-163">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="fd082-163">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="fd082-164">`ascii`：使用 ASCII (7 位) 字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-164">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="fd082-165">`bigendianunicode`：使用大字节序字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-165">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="fd082-166">`bigendianutf32`：使用大字节序字节顺序编码为32格式。</span><span class="sxs-lookup"><span data-stu-id="fd082-166">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="fd082-167">`oem`：使用 MS-DOS 和控制台程序的默认编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-167">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="fd082-168">`unicode`：使用小 endian 字节顺序对 UTF-16 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-168">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="fd082-169">`utf7`：以 UTF-7 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-169">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="fd082-170">`utf8`：以 UTF-8 格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-170">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="fd082-171">`utf8BOM`：以 UTF-8 格式编码 (BOM) </span><span class="sxs-lookup"><span data-stu-id="fd082-171">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fd082-172">`utf8NoBOM`：以 UTF-8 格式编码，而不包含字节顺序标记 (BOM) </span><span class="sxs-lookup"><span data-stu-id="fd082-172">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fd082-173">`utf32`：以32格式编码。</span><span class="sxs-lookup"><span data-stu-id="fd082-173">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="fd082-174">从 PowerShell 6.2 开始， **Encoding** 参数还允许已注册代码页的数字 id (如 `-Encoding 1251` (如) 所注册代码页的) 或字符串名称 `-Encoding "windows-1251"` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-174">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="fd082-175">有关详细信息，请参阅 .NET 文档中的[编码。](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)</span><span class="sxs-lookup"><span data-stu-id="fd082-175">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="fd082-176">不建议使用 **utf-7** \*。</span><span class="sxs-lookup"><span data-stu-id="fd082-176">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="fd082-177">在 PowerShell 7.1 中，如果 `utf7` 为 **编码** 参数指定，则会写入警告。</span><span class="sxs-lookup"><span data-stu-id="fd082-177">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

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

### <span data-ttu-id="fd082-178">-Force</span><span class="sxs-lookup"><span data-stu-id="fd082-178">-Force</span></span>

<span data-ttu-id="fd082-179">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="fd082-179">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="fd082-180">使该 cmdlet 清除输出文件的只读属性（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="fd082-180">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="fd082-181">该 cmdlet 将在命令完成时尝试重置只读属性。</span><span class="sxs-lookup"><span data-stu-id="fd082-181">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="fd082-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fd082-182">-InputObject</span></span>

<span data-ttu-id="fd082-183">指定要转换的对象。</span><span class="sxs-lookup"><span data-stu-id="fd082-183">Specifies the object to be converted.</span></span> <span data-ttu-id="fd082-184">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="fd082-184">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="fd082-185">还可以通过管道将对象传递给 `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-185">You can also pipe objects to `Export-Clixml`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd082-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fd082-186">-LiteralPath</span></span>

<span data-ttu-id="fd082-187">指定指向将存储对象的 XML 表示形式的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="fd082-187">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="fd082-188">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="fd082-188">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="fd082-189">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="fd082-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="fd082-190">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="fd082-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="fd082-191">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="fd082-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd082-192">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="fd082-192">-NoClobber</span></span>

<span data-ttu-id="fd082-193">指示该 cmdlet 不会覆盖现有文件的内容。</span><span class="sxs-lookup"><span data-stu-id="fd082-193">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="fd082-194">默认情况下，如果指定路径中存在文件，则 `Export-Clixml` 将覆盖该文件而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="fd082-194">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd082-195">-Path</span><span class="sxs-lookup"><span data-stu-id="fd082-195">-Path</span></span>

<span data-ttu-id="fd082-196">指定指向将存储对象的 XML 表示形式的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="fd082-196">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd082-197">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd082-197">-WhatIf</span></span>

<span data-ttu-id="fd082-198">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="fd082-198">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fd082-199">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="fd082-199">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="fd082-200">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd082-200">CommonParameters</span></span>

<span data-ttu-id="fd082-201">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fd082-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd082-202">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fd082-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd082-203">输入</span><span class="sxs-lookup"><span data-stu-id="fd082-203">INPUTS</span></span>

### <span data-ttu-id="fd082-204">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="fd082-204">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fd082-205">可以将任何对象通过管道进行管道 `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="fd082-205">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="fd082-206">输出</span><span class="sxs-lookup"><span data-stu-id="fd082-206">OUTPUTS</span></span>

### <span data-ttu-id="fd082-207">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="fd082-207">System.IO.FileInfo</span></span>

<span data-ttu-id="fd082-208">`Export-Clixml` 创建包含 XML 的文件。</span><span class="sxs-lookup"><span data-stu-id="fd082-208">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="fd082-209">注释</span><span class="sxs-lookup"><span data-stu-id="fd082-209">NOTES</span></span>

## <span data-ttu-id="fd082-210">相关链接</span><span class="sxs-lookup"><span data-stu-id="fd082-210">RELATED LINKS</span></span>

[<span data-ttu-id="fd082-211">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="fd082-211">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="fd082-212">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="fd082-212">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="fd082-213">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="fd082-213">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="fd082-214">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="fd082-214">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="fd082-215">Join-Path</span><span class="sxs-lookup"><span data-stu-id="fd082-215">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

<span data-ttu-id="fd082-216">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)（将凭据安全存储到磁盘）</span><span class="sxs-lookup"><span data-stu-id="fd082-216">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)</span></span>

<span data-ttu-id="fd082-217">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)（使用 PowerShell 将凭据传递到旧系统）</span><span class="sxs-lookup"><span data-stu-id="fd082-217">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)</span></span>

[<span data-ttu-id="fd082-218">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="fd082-218">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
