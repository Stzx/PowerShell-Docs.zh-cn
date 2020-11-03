---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d89d80b296d8800d65c5acfae37434e9b3f3bce9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197191"
---
# <span data-ttu-id="13859-103">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="13859-103">Export-FormatData</span></span>

## <span data-ttu-id="13859-104">摘要</span><span class="sxs-lookup"><span data-stu-id="13859-104">SYNOPSIS</span></span>
<span data-ttu-id="13859-105">将当前会话中的格式设置数据保存在格式设置文件中。</span><span class="sxs-lookup"><span data-stu-id="13859-105">Saves formatting data from the current session in a formatting file.</span></span>

## <span data-ttu-id="13859-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="13859-106">SYNTAX</span></span>

### <span data-ttu-id="13859-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="13859-107">ByPath (Default)</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### <span data-ttu-id="13859-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="13859-108">ByLiteralPath</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## <span data-ttu-id="13859-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="13859-109">DESCRIPTION</span></span>

<span data-ttu-id="13859-110">`Export-FormatData`Cmdlet 从当前会话中的格式对象 ( # B0 xml) 创建 PowerShell 格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="13859-110">The `Export-FormatData` cmdlet creates PowerShell formatting files (format.ps1xml) from the formatting objects in the current session.</span></span> <span data-ttu-id="13859-111">它获取返回的 **ExtendedTypeDefinition** 对象 `Get-FormatData` ，并将其保存到 XML 格式的文件中。</span><span class="sxs-lookup"><span data-stu-id="13859-111">It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.</span></span>

<span data-ttu-id="13859-112">PowerShell 使用 ( # B0 xml) 格式设置文件中的数据来生成会话中 Microsoft .NET 框架对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="13859-112">PowerShell uses the data in formatting files (format.ps1xml) to generate the default display of Microsoft .NET Framework objects in the session.</span></span> <span data-ttu-id="13859-113">你可以查看和编辑这些格式设置文件，并使用 Update-FormatData cmdlet 将格式设置数据添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="13859-113">You can view and edit the formatting files and use the Update-FormatData cmdlet to add the formatting data to a session.</span></span>

<span data-ttu-id="13859-114">有关在 PowerShell 中格式化文件的详细信息，请参阅 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)。</span><span class="sxs-lookup"><span data-stu-id="13859-114">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="13859-115">示例</span><span class="sxs-lookup"><span data-stu-id="13859-115">EXAMPLES</span></span>

### <span data-ttu-id="13859-116">示例1：导出会话格式数据</span><span class="sxs-lookup"><span data-stu-id="13859-116">Example 1: Export session format data</span></span>

```powershell
Get-FormatData -TypeName "*" -PowerShellVersion 5.1 | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="13859-117">此命令将会话中的所有格式数据导出到 AllFormat.ps1xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="13859-117">This command exports all of the format data in the session to the AllFormat.ps1xml file.</span></span>

<span data-ttu-id="13859-118">该命令使用 `Get-FormatData` cmdlet 来获取会话中的格式数据。</span><span class="sxs-lookup"><span data-stu-id="13859-118">The command uses the `Get-FormatData` cmdlet to get the format data in the session.</span></span> <span data-ttu-id="13859-119">如果为 `*` **TypeName** 参数 (所有) ，则值为，指示该 cmdlet 获取会话中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="13859-119">A value of `*` (all) for the **TypeName** parameter directs the cmdlet to get all of the data in the session.</span></span>

<span data-ttu-id="13859-120">该命令使用管道运算符 (`|`) 将格式数据从 `Get-FormatData` 命令发送到 `Export-FormatData` cmdlet，后者将格式数据导出到 AllFormat.ps1 文件中。</span><span class="sxs-lookup"><span data-stu-id="13859-120">The command uses a pipeline operator (`|`) to send the format data from the `Get-FormatData` command to the `Export-FormatData` cmdlet, which exports the format data to the AllFormat.ps1 file.</span></span>

<span data-ttu-id="13859-121">该 `Export-FormatData` 命令使用 **IncludeScriptBlock** 参数将脚本块包含在文件中的格式数据。</span><span class="sxs-lookup"><span data-stu-id="13859-121">The `Export-FormatData` command uses the **IncludeScriptBlock** parameter to include script blocks in the format data in the file.</span></span>

### <span data-ttu-id="13859-122">示例2：导出类型的格式数据</span><span class="sxs-lookup"><span data-stu-id="13859-122">Example 2: Export format data for a type</span></span>

```powershell
$F = Get-FormatData -TypeName "helpinfoshort" -PowerShellVersion 5.1
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="13859-123">这些命令将 **HelpInfoShort** 类型的格式数据导出到 Help.format.ps1xml 文件。</span><span class="sxs-lookup"><span data-stu-id="13859-123">These commands export the format data for the **HelpInfoShort** type to the Help.format.ps1xml file.</span></span>

<span data-ttu-id="13859-124">第一个命令使用 `Get-FormatData` cmdlet 来获取 **HelpInfoShort** 类型的格式数据，并将其保存在 `$F` 变量中。</span><span class="sxs-lookup"><span data-stu-id="13859-124">The first command uses the `Get-FormatData` cmdlet to get the format data for the **HelpInfoShort** type, and it saves it in the `$F` variable.</span></span>

<span data-ttu-id="13859-125">第二个命令使用 cmdlet 的 **InputObject** 参数 `Export-FormatData` 来输入保存在变量中的格式数据 `$F` 。</span><span class="sxs-lookup"><span data-stu-id="13859-125">The second command uses the **InputObject** parameter of the `Export-FormatData` cmdlet to enter the format data saved in the `$F` variable.</span></span> <span data-ttu-id="13859-126">它还使用 **IncludeScriptBlock** 参数将脚本块包括在输出中。</span><span class="sxs-lookup"><span data-stu-id="13859-126">It also uses the **IncludeScriptBlock** parameter to include script blocks in the output.</span></span>

### <span data-ttu-id="13859-127">示例3：在不使用脚本块的情况下导出格式数据</span><span class="sxs-lookup"><span data-stu-id="13859-127">Example 3: Export format data without a script block</span></span>

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" -PowerShellVersion 5.1 | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

<span data-ttu-id="13859-128">此示例演示省略命令中的 **IncludeScriptBlock** 参数的效果 `Export-FormatData` 。</span><span class="sxs-lookup"><span data-stu-id="13859-128">This example shows the effect of omitting the **IncludeScriptBlock** parameter from an `Export-FormatData` command.</span></span>

<span data-ttu-id="13859-129">第一个命令使用 `Get-FormatData` cmdlet 来获取 Get-Process cmdlet 返回的 **system.object** 对象的格式数据。</span><span class="sxs-lookup"><span data-stu-id="13859-129">The first command uses the `Get-FormatData` cmdlet to get the format data for the **System.Diagnostics.Process** object that the Get-Process cmdlet returns.</span></span> <span data-ttu-id="13859-130">该命令使用管道运算符 (`|`) 将格式设置数据发送到 `Export-FormatData` cmdlet，该 cmdlet 将其导出到当前目录中的 Process.format.ps1xml 文件。</span><span class="sxs-lookup"><span data-stu-id="13859-130">The command uses a pipeline operator (`|`) to send the formatting data to the `Export-FormatData` cmdlet, which exports it to the Process.format.ps1xml file in the current directory.</span></span>

<span data-ttu-id="13859-131">在这种情况下，该 `Export-FormatData` 命令不使用 **IncludeScriptBlock** 参数。</span><span class="sxs-lookup"><span data-stu-id="13859-131">In this case, the `Export-FormatData` command does not use the **IncludeScriptBlock** parameter.</span></span>

<span data-ttu-id="13859-132">第二个命令使用 `Update-FormatData` cmdlet 将 Process.format.ps1xml 文件添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="13859-132">The second command uses the `Update-FormatData` cmdlet to add the Process.format.ps1xml file to the current session.</span></span> <span data-ttu-id="13859-133">该命令使用 **PrependPath** 参数来确保在进程对象的标准格式设置数据之前找到 Process.format.ps1xml 文件中的进程对象的格式设置数据。</span><span class="sxs-lookup"><span data-stu-id="13859-133">The command uses the **PrependPath** parameter to ensure that the formatting data for process objects in the Process.format.ps1xml file is found before the standard formatting data for process objects.</span></span>

<span data-ttu-id="13859-134">第三个命令显示此更改的效果。</span><span class="sxs-lookup"><span data-stu-id="13859-134">The third command shows the effects of this change.</span></span> <span data-ttu-id="13859-135">该命令使用 `Get-Process` cmdlet 来获取名称以 P 开头的进程。此输出显示，显示中缺少使用脚本块计算的属性值。</span><span class="sxs-lookup"><span data-stu-id="13859-135">The command uses the `Get-Process` cmdlet to get processes that have names that begin with P. The output shows that property values that are calculated by using script blocks are missing from the display.</span></span>

## <span data-ttu-id="13859-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="13859-136">PARAMETERS</span></span>

### <span data-ttu-id="13859-137">-Force</span><span class="sxs-lookup"><span data-stu-id="13859-137">-Force</span></span>

<span data-ttu-id="13859-138">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="13859-138">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="13859-139">-IncludeScriptBlock</span><span class="sxs-lookup"><span data-stu-id="13859-139">-IncludeScriptBlock</span></span>

<span data-ttu-id="13859-140">指示是否导出格式数据中的脚本块。</span><span class="sxs-lookup"><span data-stu-id="13859-140">Indicates whether script blocks in the format data are exported.</span></span>

<span data-ttu-id="13859-141">因为脚本块包含代码且可被恶意使用，所以在默认情况下不导出它们。</span><span class="sxs-lookup"><span data-stu-id="13859-141">Because script blocks contain code and can be used maliciously, they are not exported by default.</span></span>

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

### <span data-ttu-id="13859-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="13859-142">-InputObject</span></span>

<span data-ttu-id="13859-143">指定要导出的格式数据对象。</span><span class="sxs-lookup"><span data-stu-id="13859-143">Specifies the format data objects to be exported.</span></span> <span data-ttu-id="13859-144">输入包含对象的变量或获取对象的命令（如 `Get-FormatData` 命令）。</span><span class="sxs-lookup"><span data-stu-id="13859-144">Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command.</span></span> <span data-ttu-id="13859-145">还可以通过管道将对象传递 `Get-FormatData` 给 `Export-FormatData` 。</span><span class="sxs-lookup"><span data-stu-id="13859-145">You can also pipe the objects from `Get-FormatData` to `Export-FormatData`.</span></span>

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="13859-146">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="13859-146">-LiteralPath</span></span>

<span data-ttu-id="13859-147">指定输出文件的位置。</span><span class="sxs-lookup"><span data-stu-id="13859-147">Specifies a location for the output file.</span></span> <span data-ttu-id="13859-148">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="13859-148">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="13859-149">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="13859-149">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="13859-150">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="13859-150">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="13859-151">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="13859-151">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="13859-152">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="13859-152">-NoClobber</span></span>

<span data-ttu-id="13859-153">指示该 cmdlet 不会覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="13859-153">Indicates that the cmdlet does not overwrite existing files.</span></span> <span data-ttu-id="13859-154">默认情况下， `Export-FormatData` 除非文件具有只读属性，否则将覆盖文件而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="13859-154">By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="13859-155">若要指示 `Export-FormatData` 覆盖只读文件，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="13859-155">To direct `Export-FormatData` to overwrite read-only files, use the **Force** parameter.</span></span>

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

### <span data-ttu-id="13859-156">-Path</span><span class="sxs-lookup"><span data-stu-id="13859-156">-Path</span></span>

<span data-ttu-id="13859-157">指定输出文件的位置。</span><span class="sxs-lookup"><span data-stu-id="13859-157">Specifies a location for the output file.</span></span>
<span data-ttu-id="13859-158">输入路径（可选）和具有 format.ps1xml 文件扩展名的文件名。</span><span class="sxs-lookup"><span data-stu-id="13859-158">Enter a path (optional) and file name with a format.ps1xml file name extension.</span></span>
<span data-ttu-id="13859-159">如果省略路径，则将 `Export-FormatData` 在当前目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="13859-159">If you omit the path, `Export-FormatData` creates the file in the current directory.</span></span>

<span data-ttu-id="13859-160">如果使用 types.ps1xml 之外的文件扩展名，则该 `Update-FormatData` cmdlet 将不会识别该文件。</span><span class="sxs-lookup"><span data-stu-id="13859-160">If you use a file name extension other than .ps1xml, the `Update-FormatData` cmdlet will not recognize the file.</span></span>

<span data-ttu-id="13859-161">如果指定了现有文件，则将 `Export-FormatData` 覆盖该文件而不发出警告，除非该文件具有只读属性。</span><span class="sxs-lookup"><span data-stu-id="13859-161">If you specify an existing file, `Export-FormatData` overwrites the file without warning, unless the file has the read-only attribute.</span></span> <span data-ttu-id="13859-162">若要覆盖只读文件，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="13859-162">To overwrite a read-only file, use the **Force** parameter.</span></span> <span data-ttu-id="13859-163">若要防止文件被覆盖，请使用 **NoClobber** 参数。</span><span class="sxs-lookup"><span data-stu-id="13859-163">To prevent files from being overwritten, use the **NoClobber** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13859-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="13859-164">CommonParameters</span></span>

<span data-ttu-id="13859-165">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="13859-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="13859-166">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="13859-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="13859-167">输入</span><span class="sxs-lookup"><span data-stu-id="13859-167">INPUTS</span></span>

### <span data-ttu-id="13859-168">System.Management.Automation.ExtendedTypeDefinition</span><span class="sxs-lookup"><span data-stu-id="13859-168">System.Management.Automation.ExtendedTypeDefinition</span></span>

<span data-ttu-id="13859-169">可以通过管道将 **ExtendedTypeDefinition** 对象发送 `Get-FormatData` 到 `Export-FormatData` 。</span><span class="sxs-lookup"><span data-stu-id="13859-169">You can pipe **ExtendedTypeDefinition** objects from `Get-FormatData` to `Export-FormatData`.</span></span>

## <span data-ttu-id="13859-170">输出</span><span class="sxs-lookup"><span data-stu-id="13859-170">OUTPUTS</span></span>

### <span data-ttu-id="13859-171">无</span><span class="sxs-lookup"><span data-stu-id="13859-171">None</span></span>

<span data-ttu-id="13859-172">`Export-FormatData` 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="13859-172">`Export-FormatData` does not return any objects.</span></span>
<span data-ttu-id="13859-173">它将生成一个文件并将其保存在指定的路径中。</span><span class="sxs-lookup"><span data-stu-id="13859-173">It generates a file and saves it in the specified path.</span></span>

## <span data-ttu-id="13859-174">注释</span><span class="sxs-lookup"><span data-stu-id="13859-174">NOTES</span></span>

- <span data-ttu-id="13859-175">若要使用任何格式设置文件（包括已导出的格式设置文件），会话的执行策略必须允许运行脚本和配置文件。</span><span class="sxs-lookup"><span data-stu-id="13859-175">To use any formatting file, including an exported formatting file, the execution policy for the session must allow scripts and configuration files to run.</span></span> <span data-ttu-id="13859-176">有关详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="13859-176">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="13859-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="13859-177">RELATED LINKS</span></span>

[<span data-ttu-id="13859-178">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="13859-178">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="13859-179">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="13859-179">Update-FormatData</span></span>](Update-FormatData.md)
