---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197946"
---
# <span data-ttu-id="4a48b-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="4a48b-103">Export-Clixml</span></span>

## <span data-ttu-id="4a48b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4a48b-104">SYNOPSIS</span></span>
<span data-ttu-id="4a48b-105">创建一个或多个对象的基于 XML 的表示形式，并将其存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="4a48b-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="4a48b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a48b-106">SYNTAX</span></span>

### <span data-ttu-id="4a48b-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="4a48b-107">ByPath (Default)</span></span>

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4a48b-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="4a48b-108">ByLiteralPath</span></span>

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4a48b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4a48b-109">DESCRIPTION</span></span>

<span data-ttu-id="4a48b-110">`Export-Clixml`Cmdlet (CLI) 基于 XML 的对象或对象的表示形式创建公共语言基础结构，并将其存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="4a48b-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="4a48b-111">然后，可以使用 `Import-Clixml` cmdlet 基于该文件的内容重新创建已保存的对象。</span><span class="sxs-lookup"><span data-stu-id="4a48b-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="4a48b-112">有关 CLI 的详细信息，请参阅 [语言独立性](/dotnet/standard/language-independence)。</span><span class="sxs-lookup"><span data-stu-id="4a48b-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="4a48b-113">此 cmdlet 类似于 `ConvertTo-Xml` ，不同之处在于将 `Export-Clixml` 生成的 XML 存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="4a48b-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="4a48b-114">`ConvertTo-XML` 返回 XML，因此你可以继续在 PowerShell 中处理它。</span><span class="sxs-lookup"><span data-stu-id="4a48b-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="4a48b-115">Windows 计算机上的一个有价值的用途 `Export-Clixml` 是将凭据和安全字符串作为 XML 安全地导出。</span><span class="sxs-lookup"><span data-stu-id="4a48b-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="4a48b-116">有关示例，请参阅示例3。</span><span class="sxs-lookup"><span data-stu-id="4a48b-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="4a48b-117">示例</span><span class="sxs-lookup"><span data-stu-id="4a48b-117">EXAMPLES</span></span>

### <span data-ttu-id="4a48b-118">示例1：将字符串导出到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="4a48b-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="4a48b-119">此示例将创建一个 XML 文件，该文件存储在当前目录中， **这是一个测试** 字符串的表示形式。</span><span class="sxs-lookup"><span data-stu-id="4a48b-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="4a48b-120">**这是一种测试** 的字符串。</span><span class="sxs-lookup"><span data-stu-id="4a48b-120">The string **This is a test** is sent down the pipeline.</span></span> <span data-ttu-id="4a48b-121">`Export-Clixml` 使用 **Path** 参数 `sample.xml` 在当前目录中创建一个名为的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="4a48b-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="4a48b-122">示例2：将对象导出到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="4a48b-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="4a48b-123">此示例演示如何将对象导出到 XML 文件，然后通过从该文件导入 XML 来创建对象。</span><span class="sxs-lookup"><span data-stu-id="4a48b-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="4a48b-124">`Get-Acl`Cmdlet 将获取该文件的安全描述符 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="4a48b-125">它将对象向下发送到管道，以将安全描述符传递给 `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="4a48b-126">对象的基于 XML 的表示形式存储在名为的文件中 `FileACL.xml` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="4a48b-127">`Import-Clixml`Cmdlet 可从该文件中的 XML 创建对象 `FileACL.xml` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="4a48b-128">然后，它将对象保存在 `$fileacl` 变量中。</span><span class="sxs-lookup"><span data-stu-id="4a48b-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="4a48b-129">示例3：加密导出的凭据对象</span><span class="sxs-lookup"><span data-stu-id="4a48b-129">Example 3: Encrypt an exported credential object</span></span>

<span data-ttu-id="4a48b-130">在此示例中，给定通过运行 cmdlet 存储在变量中的凭据 `$Credential` `Get-Credential` ，可以运行 `Export-Clixml` cmdlet 将凭据保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="4a48b-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a48b-131">`Export-Clixml` 仅导出 Windows 上的加密凭据。</span><span class="sxs-lookup"><span data-stu-id="4a48b-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="4a48b-132">在非 Windows 操作系统（如 macOS 和 Linux）上，凭据以纯文本格式导出。</span><span class="sxs-lookup"><span data-stu-id="4a48b-132">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="4a48b-133">`Export-Clixml`Cmdlet 使用 Windows[数据保护 API](/previous-versions/windows/apps/hh464970(v=win.10))加密凭据对象。</span><span class="sxs-lookup"><span data-stu-id="4a48b-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="4a48b-134">加密可确保只有该计算机上的用户帐户才能解密 credential 对象的内容。</span><span class="sxs-lookup"><span data-stu-id="4a48b-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span> <span data-ttu-id="4a48b-135">导出的 `CLIXML` 文件不能用于其他计算机或其他用户。</span><span class="sxs-lookup"><span data-stu-id="4a48b-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="4a48b-136">在此示例中，存储凭据的文件由表示 `TestScript.ps1.credential` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="4a48b-137">将 **TestScript** 替换为要在其中加载凭据的脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="4a48b-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="4a48b-138">将凭据对象向下发送到管道 `Export-Clixml` ，并将其保存到在 `$Credxmlpath` 第一个命令中指定的路径。</span><span class="sxs-lookup"><span data-stu-id="4a48b-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="4a48b-139">若要将凭据自动导入脚本，请运行最后两个命令。</span><span class="sxs-lookup"><span data-stu-id="4a48b-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="4a48b-140">运行 `Import-Clixml` 将受保护的凭据对象导入脚本。</span><span class="sxs-lookup"><span data-stu-id="4a48b-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="4a48b-141">此导入消除了在脚本中公开纯文本密码的风险。</span><span class="sxs-lookup"><span data-stu-id="4a48b-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="4a48b-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a48b-142">PARAMETERS</span></span>

### <span data-ttu-id="4a48b-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4a48b-143">-Confirm</span></span>

<span data-ttu-id="4a48b-144">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="4a48b-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4a48b-145">-Depth</span><span class="sxs-lookup"><span data-stu-id="4a48b-145">-Depth</span></span>

<span data-ttu-id="4a48b-146">指定 XML 表示形式中所包含的包含对象的级别数。</span><span class="sxs-lookup"><span data-stu-id="4a48b-146">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="4a48b-147">默认值是 `2`。</span><span class="sxs-lookup"><span data-stu-id="4a48b-147">The default value is `2`.</span></span>

<span data-ttu-id="4a48b-148">对于文件中的对象类型，可以重写默认值 `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-148">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="4a48b-149">有关详细信息，请参阅 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)。</span><span class="sxs-lookup"><span data-stu-id="4a48b-149">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

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

### <span data-ttu-id="4a48b-150">-Encoding</span><span class="sxs-lookup"><span data-stu-id="4a48b-150">-Encoding</span></span>

<span data-ttu-id="4a48b-151">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="4a48b-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="4a48b-152">默认值为 **Unicode** 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-152">The default value is **Unicode** .</span></span>

<span data-ttu-id="4a48b-153">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="4a48b-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4a48b-154">`ASCII` 使用 ASCII (7 位) 字符集。</span><span class="sxs-lookup"><span data-stu-id="4a48b-154">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="4a48b-155">`BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="4a48b-155">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="4a48b-156">`Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-156">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="4a48b-157">`OEM` 使用与系统的当前 OEM 代码页相对应的编码。</span><span class="sxs-lookup"><span data-stu-id="4a48b-157">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="4a48b-158">`Unicode` 使用带有小 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="4a48b-158">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="4a48b-159">`UTF7` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="4a48b-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="4a48b-160">`UTF8` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="4a48b-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="4a48b-161">`UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="4a48b-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a48b-162">-Force</span><span class="sxs-lookup"><span data-stu-id="4a48b-162">-Force</span></span>

<span data-ttu-id="4a48b-163">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="4a48b-163">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="4a48b-164">使该 cmdlet 清除输出文件的只读属性（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="4a48b-164">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="4a48b-165">该 cmdlet 将在命令完成时尝试重置只读属性。</span><span class="sxs-lookup"><span data-stu-id="4a48b-165">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="4a48b-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4a48b-166">-InputObject</span></span>

<span data-ttu-id="4a48b-167">指定要转换的对象。</span><span class="sxs-lookup"><span data-stu-id="4a48b-167">Specifies the object to be converted.</span></span> <span data-ttu-id="4a48b-168">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="4a48b-168">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="4a48b-169">还可以通过管道将对象传递给 `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-169">You can also pipe objects to `Export-Clixml`.</span></span>

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

### <span data-ttu-id="4a48b-170">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4a48b-170">-LiteralPath</span></span>

<span data-ttu-id="4a48b-171">指定指向将存储对象的 XML 表示形式的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4a48b-171">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="4a48b-172">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="4a48b-172">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="4a48b-173">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="4a48b-173">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4a48b-174">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="4a48b-174">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4a48b-175">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="4a48b-175">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a48b-176">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="4a48b-176">-NoClobber</span></span>

<span data-ttu-id="4a48b-177">指示该 cmdlet 不会覆盖现有文件的内容。</span><span class="sxs-lookup"><span data-stu-id="4a48b-177">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="4a48b-178">默认情况下，如果指定路径中存在文件，则 `Export-Clixml` 将覆盖该文件而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="4a48b-178">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="4a48b-179">-Path</span><span class="sxs-lookup"><span data-stu-id="4a48b-179">-Path</span></span>

<span data-ttu-id="4a48b-180">指定指向将存储对象的 XML 表示形式的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4a48b-180">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="4a48b-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4a48b-181">-WhatIf</span></span>

<span data-ttu-id="4a48b-182">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="4a48b-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4a48b-183">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="4a48b-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="4a48b-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4a48b-184">CommonParameters</span></span>

<span data-ttu-id="4a48b-185">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4a48b-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a48b-186">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4a48b-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a48b-187">输入</span><span class="sxs-lookup"><span data-stu-id="4a48b-187">INPUTS</span></span>

### <span data-ttu-id="4a48b-188">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="4a48b-188">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4a48b-189">可以将任何对象通过管道进行管道 `Export-Clixml` 。</span><span class="sxs-lookup"><span data-stu-id="4a48b-189">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="4a48b-190">输出</span><span class="sxs-lookup"><span data-stu-id="4a48b-190">OUTPUTS</span></span>

### <span data-ttu-id="4a48b-191">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="4a48b-191">System.IO.FileInfo</span></span>

<span data-ttu-id="4a48b-192">`Export-Clixml` 创建包含 XML 的文件。</span><span class="sxs-lookup"><span data-stu-id="4a48b-192">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="4a48b-193">注释</span><span class="sxs-lookup"><span data-stu-id="4a48b-193">NOTES</span></span>

## <span data-ttu-id="4a48b-194">相关链接</span><span class="sxs-lookup"><span data-stu-id="4a48b-194">RELATED LINKS</span></span>

[<span data-ttu-id="4a48b-195">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="4a48b-195">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="4a48b-196">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="4a48b-196">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="4a48b-197">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="4a48b-197">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="4a48b-198">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="4a48b-198">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="4a48b-199">Join-Path</span><span class="sxs-lookup"><span data-stu-id="4a48b-199">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

<span data-ttu-id="4a48b-200">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)（将凭据安全存储到磁盘）</span><span class="sxs-lookup"><span data-stu-id="4a48b-200">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)</span></span>

<span data-ttu-id="4a48b-201">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)（使用 PowerShell 将凭据传递到旧系统）</span><span class="sxs-lookup"><span data-stu-id="4a48b-201">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)</span></span>

[<span data-ttu-id="4a48b-202">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="4a48b-202">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
