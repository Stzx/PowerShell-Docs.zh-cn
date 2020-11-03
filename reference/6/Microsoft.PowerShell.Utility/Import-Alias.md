---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 438f089c1cd6e647ae5ee858234a3919bdc0328d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198448"
---
# <span data-ttu-id="43af4-103">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="43af4-103">Import-Alias</span></span>

## <span data-ttu-id="43af4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="43af4-104">SYNOPSIS</span></span>
<span data-ttu-id="43af4-105">从文件导入别名列表。</span><span class="sxs-lookup"><span data-stu-id="43af4-105">Imports an alias list from a file.</span></span>

## <span data-ttu-id="43af4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43af4-106">SYNTAX</span></span>

### <span data-ttu-id="43af4-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="43af4-107">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="43af4-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="43af4-108">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="43af4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43af4-109">DESCRIPTION</span></span>

<span data-ttu-id="43af4-110">`Import-Alias`Cmdlet 可从文件导入别名列表。</span><span class="sxs-lookup"><span data-stu-id="43af4-110">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="43af4-111">从 Windows PowerShell 3.0 开始，作为一项安全功能， `Import-Alias` 默认情况下不会覆盖现有别名。</span><span class="sxs-lookup"><span data-stu-id="43af4-111">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="43af4-112">若要覆盖现有别名，应在使用 **Force** 参数之前先确保该别名文件的内容是安全的。</span><span class="sxs-lookup"><span data-stu-id="43af4-112">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="43af4-113">示例</span><span class="sxs-lookup"><span data-stu-id="43af4-113">EXAMPLES</span></span>

### <span data-ttu-id="43af4-114">示例 1：从文件导入别名</span><span class="sxs-lookup"><span data-stu-id="43af4-114">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="43af4-115">此命令从名为 test.txt 的文件中导入别名信息。</span><span class="sxs-lookup"><span data-stu-id="43af4-115">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="43af4-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43af4-116">PARAMETERS</span></span>

### <span data-ttu-id="43af4-117">-Force</span><span class="sxs-lookup"><span data-stu-id="43af4-117">-Force</span></span>

<span data-ttu-id="43af4-118">允许该 cmdlet 导入已定义的或只读形式的别名。</span><span class="sxs-lookup"><span data-stu-id="43af4-118">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="43af4-119">可以使用以下命令显示有关当前定义的别名的信息：</span><span class="sxs-lookup"><span data-stu-id="43af4-119">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="43af4-120">如果对应的别名是只读的，则将它显示在 **Options** 属性的值中。</span><span class="sxs-lookup"><span data-stu-id="43af4-120">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="43af4-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="43af4-121">-LiteralPath</span></span>

<span data-ttu-id="43af4-122">指定包含导出的别名信息的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="43af4-122">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="43af4-123">与 **Path** 参数不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="43af4-123">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="43af4-124">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="43af4-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="43af4-125">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="43af4-125">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="43af4-126">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="43af4-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43af4-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="43af4-127">-PassThru</span></span>

<span data-ttu-id="43af4-128">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="43af4-128">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="43af4-129">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="43af4-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="43af4-130">-Path</span><span class="sxs-lookup"><span data-stu-id="43af4-130">-Path</span></span>

<span data-ttu-id="43af4-131">指定包含导出的别名信息的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="43af4-131">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="43af4-132">允许使用通配符，但它们必须解析为单个名称。</span><span class="sxs-lookup"><span data-stu-id="43af4-132">Wildcards are allowed but they must resolve to a single name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="43af4-133">-Scope</span><span class="sxs-lookup"><span data-stu-id="43af4-133">-Scope</span></span>

<span data-ttu-id="43af4-134">指定别名要导入的作用域。</span><span class="sxs-lookup"><span data-stu-id="43af4-134">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="43af4-135">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="43af4-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="43af4-136">全球</span><span class="sxs-lookup"><span data-stu-id="43af4-136">Global</span></span>
- <span data-ttu-id="43af4-137">Local</span><span class="sxs-lookup"><span data-stu-id="43af4-137">Local</span></span>
- <span data-ttu-id="43af4-138">脚本</span><span class="sxs-lookup"><span data-stu-id="43af4-138">Script</span></span>
- <span data-ttu-id="43af4-139">一个相对于当前作用域的数字（0 到作用域数，其中 0 是指当前作用域，1 是指其父作用域）</span><span class="sxs-lookup"><span data-stu-id="43af4-139">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="43af4-140">默认值为 Local。</span><span class="sxs-lookup"><span data-stu-id="43af4-140">The default is Local.</span></span>
<span data-ttu-id="43af4-141">有关详细信息，请参阅 about_Scopes。</span><span class="sxs-lookup"><span data-stu-id="43af4-141">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="43af4-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="43af4-142">-Confirm</span></span>

<span data-ttu-id="43af4-143">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="43af4-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="43af4-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="43af4-144">-WhatIf</span></span>

<span data-ttu-id="43af4-145">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="43af4-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="43af4-146">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="43af4-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="43af4-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43af4-147">CommonParameters</span></span>

<span data-ttu-id="43af4-148">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="43af4-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43af4-149">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="43af4-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43af4-150">输入</span><span class="sxs-lookup"><span data-stu-id="43af4-150">INPUTS</span></span>

### <span data-ttu-id="43af4-151">System.String</span><span class="sxs-lookup"><span data-stu-id="43af4-151">System.String</span></span>

<span data-ttu-id="43af4-152">可以通过管道将包含路径的字符串传递给 `Import-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="43af4-152">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="43af4-153">输出</span><span class="sxs-lookup"><span data-stu-id="43af4-153">OUTPUTS</span></span>

### <span data-ttu-id="43af4-154">无或 System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="43af4-154">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="43af4-155">当使用 **Passthru** 参数时，将 `Import-Alias` 返回一个表示别名的 **system.management.automation.aliasinfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="43af4-155">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="43af4-156">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="43af4-156">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="43af4-157">注释</span><span class="sxs-lookup"><span data-stu-id="43af4-157">NOTES</span></span>

## <span data-ttu-id="43af4-158">相关链接</span><span class="sxs-lookup"><span data-stu-id="43af4-158">RELATED LINKS</span></span>

[<span data-ttu-id="43af4-159">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="43af4-159">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="43af4-160">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="43af4-160">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="43af4-161">New-Alias</span><span class="sxs-lookup"><span data-stu-id="43af4-161">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="43af4-162">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="43af4-162">Set-Alias</span></span>](Set-Alias.md)
