---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 5a732573a24da5de2a00bfd29abb3711218c64e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198619"
---
# <span data-ttu-id="db5af-103">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="db5af-103">Export-Alias</span></span>

## <span data-ttu-id="db5af-104">摘要</span><span class="sxs-lookup"><span data-stu-id="db5af-104">SYNOPSIS</span></span>
<span data-ttu-id="db5af-105">将有关当前定义的别名的信息导出到文件中。</span><span class="sxs-lookup"><span data-stu-id="db5af-105">Exports information about currently defined aliases to a file.</span></span>

## <span data-ttu-id="db5af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db5af-106">SYNTAX</span></span>

### <span data-ttu-id="db5af-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="db5af-107">ByPath (Default)</span></span>

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="db5af-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="db5af-108">ByLiteralPath</span></span>

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="db5af-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db5af-109">DESCRIPTION</span></span>

<span data-ttu-id="db5af-110">`Export-Alias`Cmdlet 将当前会话中的别名导出到文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-110">The `Export-Alias` cmdlet exports the aliases in the current session to a file.</span></span>
<span data-ttu-id="db5af-111">如果输出文件不存在，则该 cmdlet 将创建它。</span><span class="sxs-lookup"><span data-stu-id="db5af-111">If the output file does not exist, the cmdlet will create it.</span></span>

<span data-ttu-id="db5af-112">`Export-Alias` 可以导出特定作用域或所有作用域中的别名，它可以生成 CSV 格式的数据，或者作为一系列可添加到会话或 PowerShell 配置文件的 Set-Alias 命令生成数据。</span><span class="sxs-lookup"><span data-stu-id="db5af-112">`Export-Alias` can export the aliases in a particular scope or all scopes, it can generate the data in CSV format or as a series of Set-Alias commands that you can add to a session or to a PowerShell profile.</span></span>

## <span data-ttu-id="db5af-113">示例</span><span class="sxs-lookup"><span data-stu-id="db5af-113">EXAMPLES</span></span>

### <span data-ttu-id="db5af-114">示例1：导出别名</span><span class="sxs-lookup"><span data-stu-id="db5af-114">Example 1: Export an alias</span></span>

```powershell
Export-Alias -Path "alias.csv"
```

<span data-ttu-id="db5af-115">此命令将当前的别名信息导出到当前目录中名为 Alias.csv 的文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-115">This command exports current alias information to a file named Alias.csv in the current directory.</span></span>

### <span data-ttu-id="db5af-116">示例2：除非导出文件已存在，否则导出别名</span><span class="sxs-lookup"><span data-stu-id="db5af-116">Example 2: Export an alias unless the export file already exists</span></span>

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

<span data-ttu-id="db5af-117">此命令将当前会话中的别名导出到 Alias.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-117">This command exports the aliases in the current session to an Alias.csv file.</span></span>

<span data-ttu-id="db5af-118">由于指定了 **NoClobber** 参数，因此如果 Alias.csv 文件已存在于当前目录中，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="db5af-118">Because the **NoClobber** parameter is specified, the command will fail if an Alias.csv file already exists in the current directory.</span></span>

### <span data-ttu-id="db5af-119">示例3：将别名追加到文件</span><span class="sxs-lookup"><span data-stu-id="db5af-119">Example 3: Append aliases to a file</span></span>

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

<span data-ttu-id="db5af-120">此命令将当前会话中的别名附加到 Alias.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-120">This command appends the aliases in the current session to the Alias.csv file.</span></span>

<span data-ttu-id="db5af-121">此命令使用 **description** 参数将描述添加到文件顶部的注释。</span><span class="sxs-lookup"><span data-stu-id="db5af-121">The command uses the **Description** parameter to add a description to the comments at the top of the file.</span></span>

<span data-ttu-id="db5af-122">该命令还使用 **Force** 参数覆盖任何现有 Alias.csv 文件，即使它们具有只读属性也是如此。</span><span class="sxs-lookup"><span data-stu-id="db5af-122">The command also uses the **Force** parameter to overwrite any existing Alias.csv files, even if they have the read-only attribute.</span></span>

### <span data-ttu-id="db5af-123">示例4：将别名导出为脚本</span><span class="sxs-lookup"><span data-stu-id="db5af-123">Example 4: Export aliases as a script</span></span>

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

<span data-ttu-id="db5af-124">此示例演示如何使用生成的脚本文件格式 `Export-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="db5af-124">This example shows how to use the script file format that `Export-Alias` generates.</span></span>

<span data-ttu-id="db5af-125">第一个命令将会话中的别名导出到 Alias.ps1 文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-125">The first command exports the aliases in the session to the Alias.ps1 file.</span></span>
<span data-ttu-id="db5af-126">它将 **As** 参数与 Script 值一起使用，以生成包含每个别名的 Set-Alias 命令的文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-126">It uses the **As** parameter with a value of Script to generate a file that contains a Set-Alias command for each alias.</span></span>

<span data-ttu-id="db5af-127">第二个命令将 Alias.ps1 文件中的别名添加到 CurrentUser-CurrentHost 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="db5af-127">The second command adds the aliases in the Alias.ps1 file to the CurrentUser-CurrentHost profile.</span></span>
<span data-ttu-id="db5af-128">配置文件的路径保存在 `$Profile` 变量中。</span><span class="sxs-lookup"><span data-stu-id="db5af-128">The path to the profile is saved in the `$Profile` variable.</span></span>
<span data-ttu-id="db5af-129">该命令使用 `Get-Content` cmdlet 来获取 Alias.ps1 文件中的别名，并使用 `Add-Content` cmdlet 将它们添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="db5af-129">The command uses the `Get-Content` cmdlet to get the aliases from the Alias.ps1 file and the `Add-Content` cmdlet to add them to the profile.</span></span>
<span data-ttu-id="db5af-130">有关详细信息，请参阅 about_Profiles。</span><span class="sxs-lookup"><span data-stu-id="db5af-130">For more information, see about_Profiles.</span></span>

<span data-ttu-id="db5af-131">第三个和第四个命令将 Alias.ps1 文件中的别名添加到 Server01 计算机上的远程会话。</span><span class="sxs-lookup"><span data-stu-id="db5af-131">The third and fourth commands add the aliases in the Alias.ps1 file to a remote session on the Server01 computer.</span></span>
<span data-ttu-id="db5af-132">第三个命令使用 `New-PSSession` cmdlet 来创建会话。</span><span class="sxs-lookup"><span data-stu-id="db5af-132">The third command uses the `New-PSSession` cmdlet to create the session.</span></span>
<span data-ttu-id="db5af-133">第四个命令使用 cmdlet 的 **FilePath** 参数 `Invoke-Command` 在新会话中运行 Alias.ps1 文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-133">The fourth command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run the Alias.ps1 file in the new session.</span></span>

## <span data-ttu-id="db5af-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db5af-134">PARAMETERS</span></span>

### <span data-ttu-id="db5af-135">-Append</span><span class="sxs-lookup"><span data-stu-id="db5af-135">-Append</span></span>

<span data-ttu-id="db5af-136">指示此 cmdlet 将输出追加到指定的文件，而不是覆盖该文件的现有内容。</span><span class="sxs-lookup"><span data-stu-id="db5af-136">Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file.</span></span>

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

### <span data-ttu-id="db5af-137">-As</span><span class="sxs-lookup"><span data-stu-id="db5af-137">-As</span></span>

<span data-ttu-id="db5af-138">指定输出格式。</span><span class="sxs-lookup"><span data-stu-id="db5af-138">Specifies the output format.</span></span>
<span data-ttu-id="db5af-139">CSV 是默认值。</span><span class="sxs-lookup"><span data-stu-id="db5af-139">CSV is the default.</span></span>
<span data-ttu-id="db5af-140">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="db5af-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="db5af-141">CSV</span><span class="sxs-lookup"><span data-stu-id="db5af-141">CSV.</span></span>
<span data-ttu-id="db5af-142">以逗号分隔值 (CSV) 格式。</span><span class="sxs-lookup"><span data-stu-id="db5af-142">Comma-separated value (CSV) format.</span></span>
- <span data-ttu-id="db5af-143">脚本。</span><span class="sxs-lookup"><span data-stu-id="db5af-143">Script.</span></span>
<span data-ttu-id="db5af-144">`Set-Alias`为每个导出的别名创建一个命令。</span><span class="sxs-lookup"><span data-stu-id="db5af-144">Creates a `Set-Alias` command for each exported alias.</span></span>
<span data-ttu-id="db5af-145">如果你使用 .ps1 文件扩展命名输出文件，则可以将它作为脚本运行，以将别名添加到任何会话中。</span><span class="sxs-lookup"><span data-stu-id="db5af-145">If you name the output file with a .ps1 file name extension, you can run it as a script to add the aliases to any session.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="db5af-146">-Description</span><span class="sxs-lookup"><span data-stu-id="db5af-146">-Description</span></span>

<span data-ttu-id="db5af-147">指定导出文件的说明。</span><span class="sxs-lookup"><span data-stu-id="db5af-147">Specifies the description of the exported file.</span></span>
<span data-ttu-id="db5af-148">该描述显示为该文件顶部的注释，位于标头信息之后。</span><span class="sxs-lookup"><span data-stu-id="db5af-148">The description appears as a comment at the top of the file, following the header information.</span></span>

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

### <span data-ttu-id="db5af-149">-Force</span><span class="sxs-lookup"><span data-stu-id="db5af-149">-Force</span></span>

<span data-ttu-id="db5af-150">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="db5af-150">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="db5af-151">即使在文件上设置了只读属性，也将覆盖输出文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-151">Overwrites the output file, even if the read-only attribute is set on the file.</span></span>

<span data-ttu-id="db5af-152">默认情况下， `Export-Alias` 除非设置了只读或隐藏属性，或者命令中使用了 **NoClobber** 参数，否则，将在不发出警告的情况下覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-152">By default, `Export-Alias` overwrites files without warning, unless the read-only or hidden attribute is set or the **NoClobber** parameter is used in the command.</span></span>
<span data-ttu-id="db5af-153">当命令中同时使用 **NoClobber** 参数时，该参数优先于 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="db5af-153">The **NoClobber** parameter takes precedence over the **Force** parameter when both are used in a command.</span></span>

<span data-ttu-id="db5af-154">**Force** 参数不能强制 `Export-Alias` 覆盖具有隐藏特性的文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-154">The **Force** parameter cannot force `Export-Alias` to overwrite files with the hidden attribute.</span></span>

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

### <span data-ttu-id="db5af-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="db5af-155">-LiteralPath</span></span>

<span data-ttu-id="db5af-156">指定输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="db5af-156">Specifies the path to the output file.</span></span>
<span data-ttu-id="db5af-157">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="db5af-157">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="db5af-158">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="db5af-158">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="db5af-159">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="db5af-159">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="db5af-160">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="db5af-160">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="db5af-161">-Name</span><span class="sxs-lookup"><span data-stu-id="db5af-161">-Name</span></span>

<span data-ttu-id="db5af-162">将名称指定为要导出的别名的数组。</span><span class="sxs-lookup"><span data-stu-id="db5af-162">Specifies the names as an array of the aliases to export.</span></span>
<span data-ttu-id="db5af-163">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="db5af-163">Wildcards are permitted.</span></span>

<span data-ttu-id="db5af-164">默认情况下， `Export-Alias` 将导出会话或作用域中的所有别名。</span><span class="sxs-lookup"><span data-stu-id="db5af-164">By default, `Export-Alias` exports all aliases in the session or scope.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="db5af-165">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="db5af-165">-NoClobber</span></span>

<span data-ttu-id="db5af-166">指示此 cmdlet 防止 `Export-Alias` 覆盖任何文件，即使在该命令中使用了 **Force** 参数也是如此。</span><span class="sxs-lookup"><span data-stu-id="db5af-166">Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.</span></span>

<span data-ttu-id="db5af-167">如果省略 **NoClobber** 参数，则 `Export-Alias` 将覆盖现有文件而不发出警告，除非在该文件上设置了只读特性。</span><span class="sxs-lookup"><span data-stu-id="db5af-167">If the **NoClobber** parameter is omitted, `Export-Alias` will overwrite an existing file without warning, unless the read-only attribute is set on the file.</span></span>
<span data-ttu-id="db5af-168">*NoClobber* 优先于 **Force** 参数，这将允许 `Export-Alias` 使用只读属性覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-168">*NoClobber* takes precedence over the **Force** parameter, which permits `Export-Alias` to overwrite a file with the read-only attribute.</span></span>

<span data-ttu-id="db5af-169">*NoClobber* 不会阻止 **Append** 参数将内容添加到现有文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-169">*NoClobber* does not prevent the **Append** parameter from adding content to an existing file.</span></span>

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

### <span data-ttu-id="db5af-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="db5af-170">-PassThru</span></span>

<span data-ttu-id="db5af-171">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="db5af-171">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="db5af-172">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="db5af-172">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="db5af-173">-Path</span><span class="sxs-lookup"><span data-stu-id="db5af-173">-Path</span></span>

<span data-ttu-id="db5af-174">指定输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="db5af-174">Specifies the path to the output file.</span></span>
<span data-ttu-id="db5af-175">允许使用通配符，但所得到的路径值必须解析为单个文件名称。</span><span class="sxs-lookup"><span data-stu-id="db5af-175">Wildcards are permitted, but the resulting path value must resolve to a single file name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="db5af-176">-Scope</span><span class="sxs-lookup"><span data-stu-id="db5af-176">-Scope</span></span>

<span data-ttu-id="db5af-177">指定应从其导出别名的作用域。</span><span class="sxs-lookup"><span data-stu-id="db5af-177">Specifies the scope from which the aliases should be exported.</span></span>
<span data-ttu-id="db5af-178">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="db5af-178">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="db5af-179">全球</span><span class="sxs-lookup"><span data-stu-id="db5af-179">Global</span></span>
- <span data-ttu-id="db5af-180">Local</span><span class="sxs-lookup"><span data-stu-id="db5af-180">Local</span></span>
- <span data-ttu-id="db5af-181">脚本</span><span class="sxs-lookup"><span data-stu-id="db5af-181">Script</span></span>
- <span data-ttu-id="db5af-182">一个相对于当前作用域的数字 (0 到作用域数，其中0是当前作用域，1是其父级) </span><span class="sxs-lookup"><span data-stu-id="db5af-182">A number relative to the current scope (0 through the number of scopes where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="db5af-183">默认值为 Local。</span><span class="sxs-lookup"><span data-stu-id="db5af-183">The default value is Local.</span></span>
<span data-ttu-id="db5af-184">有关详细信息，请参阅 about_Scopes。</span><span class="sxs-lookup"><span data-stu-id="db5af-184">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="db5af-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="db5af-185">-Confirm</span></span>

<span data-ttu-id="db5af-186">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="db5af-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="db5af-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="db5af-187">-WhatIf</span></span>

<span data-ttu-id="db5af-188">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="db5af-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="db5af-189">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="db5af-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="db5af-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db5af-190">CommonParameters</span></span>

<span data-ttu-id="db5af-191">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="db5af-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="db5af-192">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="db5af-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="db5af-193">输入</span><span class="sxs-lookup"><span data-stu-id="db5af-193">INPUTS</span></span>

### <span data-ttu-id="db5af-194">无。</span><span class="sxs-lookup"><span data-stu-id="db5af-194">None.</span></span>

<span data-ttu-id="db5af-195">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="db5af-195">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="db5af-196">输出</span><span class="sxs-lookup"><span data-stu-id="db5af-196">OUTPUTS</span></span>

### <span data-ttu-id="db5af-197">无或 System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="db5af-197">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="db5af-198">当使用 **Passthru** 参数时，将 `Export-Alias` 返回一个表示别名的 **system.management.automation.aliasinfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="db5af-198">When you use the **Passthru** parameter, `Export-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="db5af-199">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="db5af-199">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="db5af-200">注释</span><span class="sxs-lookup"><span data-stu-id="db5af-200">NOTES</span></span>

* <span data-ttu-id="db5af-201">可以仅将别名导出到文件。</span><span class="sxs-lookup"><span data-stu-id="db5af-201">You can only Export-Aliases to a file.</span></span>

## <span data-ttu-id="db5af-202">相关链接</span><span class="sxs-lookup"><span data-stu-id="db5af-202">RELATED LINKS</span></span>

[<span data-ttu-id="db5af-203">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="db5af-203">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="db5af-204">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="db5af-204">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="db5af-205">New-Alias</span><span class="sxs-lookup"><span data-stu-id="db5af-205">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="db5af-206">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="db5af-206">Set-Alias</span></span>](Set-Alias.md)
