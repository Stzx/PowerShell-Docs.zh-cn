---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 6aac74b9b084996377b97997ab78972cb28b0959
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198276"
---
# <span data-ttu-id="db1f8-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-103">Invoke-Item</span></span>

## <span data-ttu-id="db1f8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="db1f8-104">SYNOPSIS</span></span>
<span data-ttu-id="db1f8-105">对指定项执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="db1f8-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="db1f8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db1f8-106">SYNTAX</span></span>

### <span data-ttu-id="db1f8-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="db1f8-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="db1f8-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="db1f8-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="db1f8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db1f8-109">DESCRIPTION</span></span>

<span data-ttu-id="db1f8-110">`Invoke-Item`Cmdlet 对指定项执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="db1f8-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="db1f8-111">例如，它运行可执行文件或在与某一文档文件类型关联的应用程序中打开该文档文件。</span><span class="sxs-lookup"><span data-stu-id="db1f8-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="db1f8-112">默认操作依赖于项的类型，由提供数据访问的 PowerShell 提供程序确定。</span><span class="sxs-lookup"><span data-stu-id="db1f8-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="db1f8-113">示例</span><span class="sxs-lookup"><span data-stu-id="db1f8-113">EXAMPLES</span></span>

### <span data-ttu-id="db1f8-114">示例 1：打开文件</span><span class="sxs-lookup"><span data-stu-id="db1f8-114">Example 1: Open a file</span></span>

<span data-ttu-id="db1f8-115">此命令在 Microsoft Office Word 中打开文件 "aliasApr04.doc"。</span><span class="sxs-lookup"><span data-stu-id="db1f8-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="db1f8-116">在这种情况下，在 Word 中打开是 ".doc" 文件的默认操作。</span><span class="sxs-lookup"><span data-stu-id="db1f8-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="db1f8-117">示例 2：打开特定类型的所有文件</span><span class="sxs-lookup"><span data-stu-id="db1f8-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="db1f8-118">此命令打开 "C:\documents and 和 Settings\Lister\My Documents" 文件夹中的所有 Microsoft Office Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="db1f8-118">This command opens all of the Microsoft Office Excel spreadsheets in the "C:\Documents and Settings\Lister\My Documents" folder.</span></span>
<span data-ttu-id="db1f8-119">每个电子表格均在 Excel 的新实例中打开。</span><span class="sxs-lookup"><span data-stu-id="db1f8-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="db1f8-120">在这种情况下，在 Excel 中打开是 ".xls" 文件的默认操作。</span><span class="sxs-lookup"><span data-stu-id="db1f8-120">In this case, opening in Excel is the default action for ".xls" files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="db1f8-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db1f8-121">PARAMETERS</span></span>

### <span data-ttu-id="db1f8-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="db1f8-122">-Credential</span></span>

<span data-ttu-id="db1f8-123">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="db1f8-123">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="db1f8-124">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="db1f8-124">The default is the current user.</span></span>

<span data-ttu-id="db1f8-125">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="db1f8-125">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="db1f8-126">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="db1f8-126">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="db1f8-127">随同 Windows PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="db1f8-127">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="db1f8-128">-Exclude</span><span class="sxs-lookup"><span data-stu-id="db1f8-128">-Exclude</span></span>

<span data-ttu-id="db1f8-129">指定此 cmdlet 将从操作中排除的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="db1f8-129">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="db1f8-130">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="db1f8-130">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="db1f8-131">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="db1f8-131">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="db1f8-132">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="db1f8-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="db1f8-133">-Filter</span><span class="sxs-lookup"><span data-stu-id="db1f8-133">-Filter</span></span>

<span data-ttu-id="db1f8-134">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="db1f8-134">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="db1f8-135">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="db1f8-135">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="db1f8-136">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="db1f8-136">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="db1f8-137">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="db1f8-137">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="db1f8-138">-Include</span><span class="sxs-lookup"><span data-stu-id="db1f8-138">-Include</span></span>

<span data-ttu-id="db1f8-139">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="db1f8-139">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="db1f8-140">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="db1f8-140">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="db1f8-141">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="db1f8-141">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="db1f8-142">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="db1f8-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="db1f8-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="db1f8-143">-LiteralPath</span></span>

<span data-ttu-id="db1f8-144">指定项的路径。</span><span class="sxs-lookup"><span data-stu-id="db1f8-144">Specifies a path to the item.</span></span>
<span data-ttu-id="db1f8-145">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="db1f8-145">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="db1f8-146">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="db1f8-146">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="db1f8-147">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="db1f8-147">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="db1f8-148">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="db1f8-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="db1f8-149">-Path</span><span class="sxs-lookup"><span data-stu-id="db1f8-149">-Path</span></span>

<span data-ttu-id="db1f8-150">指定所选项的路径。</span><span class="sxs-lookup"><span data-stu-id="db1f8-150">Specifies the path to the selected item.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="db1f8-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="db1f8-151">-UseTransaction</span></span>

<span data-ttu-id="db1f8-152">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="db1f8-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="db1f8-153">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="db1f8-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="db1f8-154">有关详细信息，请参阅 about_transactions。</span><span class="sxs-lookup"><span data-stu-id="db1f8-154">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="db1f8-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="db1f8-155">-Confirm</span></span>
<span data-ttu-id="db1f8-156">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="db1f8-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="db1f8-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="db1f8-157">-WhatIf</span></span>

<span data-ttu-id="db1f8-158">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="db1f8-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="db1f8-159">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="db1f8-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="db1f8-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db1f8-160">CommonParameters</span></span>

<span data-ttu-id="db1f8-161">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="db1f8-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="db1f8-162">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="db1f8-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="db1f8-163">输入</span><span class="sxs-lookup"><span data-stu-id="db1f8-163">INPUTS</span></span>

### <span data-ttu-id="db1f8-164">System.String</span><span class="sxs-lookup"><span data-stu-id="db1f8-164">System.String</span></span>

<span data-ttu-id="db1f8-165">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="db1f8-165">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="db1f8-166">输出</span><span class="sxs-lookup"><span data-stu-id="db1f8-166">OUTPUTS</span></span>

### <span data-ttu-id="db1f8-167">无</span><span class="sxs-lookup"><span data-stu-id="db1f8-167">None</span></span>

<span data-ttu-id="db1f8-168">此命令不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="db1f8-168">The command does not generate any output.</span></span>
<span data-ttu-id="db1f8-169">但它调用的项可能会产生输出。</span><span class="sxs-lookup"><span data-stu-id="db1f8-169">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="db1f8-170">注释</span><span class="sxs-lookup"><span data-stu-id="db1f8-170">NOTES</span></span>

<span data-ttu-id="db1f8-171">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="db1f8-171">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="db1f8-172">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="db1f8-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="db1f8-173">有关详细信息，请参阅 about_Providers。</span><span class="sxs-lookup"><span data-stu-id="db1f8-173">For more information, see about_Providers.</span></span>

## <span data-ttu-id="db1f8-174">相关链接</span><span class="sxs-lookup"><span data-stu-id="db1f8-174">RELATED LINKS</span></span>

[<span data-ttu-id="db1f8-175">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-175">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="db1f8-176">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-176">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="db1f8-177">Get-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-177">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="db1f8-178">Move-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-178">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="db1f8-179">New-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-179">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="db1f8-180">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-180">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="db1f8-181">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-181">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="db1f8-182">Set-Item</span><span class="sxs-lookup"><span data-stu-id="db1f8-182">Set-Item</span></span>](Set-Item.md)
