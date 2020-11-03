---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: bbd3ca9a3a4df8930a75ecc395765e70fc7ccf7b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196929"
---
# <span data-ttu-id="a8e71-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-103">Invoke-Item</span></span>

## <span data-ttu-id="a8e71-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a8e71-104">SYNOPSIS</span></span>
<span data-ttu-id="a8e71-105">对指定项执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="a8e71-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="a8e71-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a8e71-106">SYNTAX</span></span>

### <span data-ttu-id="a8e71-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="a8e71-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a8e71-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a8e71-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a8e71-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a8e71-109">DESCRIPTION</span></span>

<span data-ttu-id="a8e71-110">`Invoke-Item`Cmdlet 对指定项执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="a8e71-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="a8e71-111">例如，它运行可执行文件或在与某一文档文件类型关联的应用程序中打开该文档文件。</span><span class="sxs-lookup"><span data-stu-id="a8e71-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="a8e71-112">默认操作依赖于项的类型，由提供数据访问的 PowerShell 提供程序确定。</span><span class="sxs-lookup"><span data-stu-id="a8e71-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="a8e71-113">示例</span><span class="sxs-lookup"><span data-stu-id="a8e71-113">EXAMPLES</span></span>

### <span data-ttu-id="a8e71-114">示例 1：打开文件</span><span class="sxs-lookup"><span data-stu-id="a8e71-114">Example 1: Open a file</span></span>

<span data-ttu-id="a8e71-115">此命令在 Microsoft Office Word 中打开文件 "aliasApr04.doc"。</span><span class="sxs-lookup"><span data-stu-id="a8e71-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="a8e71-116">在这种情况下，在 Word 中打开是 ".doc" 文件的默认操作。</span><span class="sxs-lookup"><span data-stu-id="a8e71-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="a8e71-117">示例 2：打开特定类型的所有文件</span><span class="sxs-lookup"><span data-stu-id="a8e71-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="a8e71-118">此命令打开文件夹中的所有 Microsoft Office Excel 电子表格 `C:\Documents and
Settings\Lister\My Documents` 。</span><span class="sxs-lookup"><span data-stu-id="a8e71-118">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="a8e71-119">每个电子表格均在 Excel 的新实例中打开。</span><span class="sxs-lookup"><span data-stu-id="a8e71-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="a8e71-120">在这种情况下，在 Excel 中打开是文件的默认操作 `.xls` 。</span><span class="sxs-lookup"><span data-stu-id="a8e71-120">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="a8e71-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a8e71-121">PARAMETERS</span></span>

### <span data-ttu-id="a8e71-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="a8e71-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a8e71-123">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="a8e71-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a8e71-124">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e71-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a8e71-125">-Exclude</span><span class="sxs-lookup"><span data-stu-id="a8e71-125">-Exclude</span></span>

<span data-ttu-id="a8e71-126">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="a8e71-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a8e71-127">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="a8e71-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a8e71-128">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="a8e71-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a8e71-129">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a8e71-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="a8e71-130">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="a8e71-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a8e71-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="a8e71-131">-Filter</span></span>

<span data-ttu-id="a8e71-132">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a8e71-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a8e71-133">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a8e71-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="a8e71-134">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="a8e71-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="a8e71-135">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a8e71-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a8e71-136">-Include</span><span class="sxs-lookup"><span data-stu-id="a8e71-136">-Include</span></span>

<span data-ttu-id="a8e71-137">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="a8e71-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a8e71-138">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="a8e71-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a8e71-139">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="a8e71-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="a8e71-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a8e71-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="a8e71-141">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="a8e71-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a8e71-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a8e71-142">-LiteralPath</span></span>

<span data-ttu-id="a8e71-143">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="a8e71-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a8e71-144">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="a8e71-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a8e71-145">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="a8e71-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a8e71-146">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="a8e71-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a8e71-147">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="a8e71-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a8e71-148">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e71-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a8e71-149">-Path</span><span class="sxs-lookup"><span data-stu-id="a8e71-149">-Path</span></span>

<span data-ttu-id="a8e71-150">指定所选项的路径。</span><span class="sxs-lookup"><span data-stu-id="a8e71-150">Specifies the path to the selected item.</span></span>
<span data-ttu-id="a8e71-151">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a8e71-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a8e71-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a8e71-152">-Confirm</span></span>

<span data-ttu-id="a8e71-153">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="a8e71-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a8e71-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a8e71-154">-WhatIf</span></span>

<span data-ttu-id="a8e71-155">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a8e71-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a8e71-156">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="a8e71-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a8e71-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a8e71-157">CommonParameters</span></span>

<span data-ttu-id="a8e71-158">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="a8e71-158">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a8e71-159">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e71-159">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a8e71-160">输入</span><span class="sxs-lookup"><span data-stu-id="a8e71-160">INPUTS</span></span>

### <span data-ttu-id="a8e71-161">System.String</span><span class="sxs-lookup"><span data-stu-id="a8e71-161">System.String</span></span>

<span data-ttu-id="a8e71-162">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a8e71-162">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="a8e71-163">输出</span><span class="sxs-lookup"><span data-stu-id="a8e71-163">OUTPUTS</span></span>

### <span data-ttu-id="a8e71-164">无</span><span class="sxs-lookup"><span data-stu-id="a8e71-164">None</span></span>

<span data-ttu-id="a8e71-165">此命令不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="a8e71-165">The command does not generate any output.</span></span>
<span data-ttu-id="a8e71-166">但它调用的项可能会产生输出。</span><span class="sxs-lookup"><span data-stu-id="a8e71-166">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="a8e71-167">注释</span><span class="sxs-lookup"><span data-stu-id="a8e71-167">NOTES</span></span>

<span data-ttu-id="a8e71-168">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="a8e71-168">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a8e71-169">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="a8e71-169">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a8e71-170">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e71-170">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a8e71-171">相关链接</span><span class="sxs-lookup"><span data-stu-id="a8e71-171">RELATED LINKS</span></span>

[<span data-ttu-id="a8e71-172">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-172">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="a8e71-173">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-173">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="a8e71-174">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-174">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="a8e71-175">Move-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-175">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="a8e71-176">New-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-176">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="a8e71-177">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-177">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="a8e71-178">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-178">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="a8e71-179">Set-Item</span><span class="sxs-lookup"><span data-stu-id="a8e71-179">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="a8e71-180">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a8e71-180">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
