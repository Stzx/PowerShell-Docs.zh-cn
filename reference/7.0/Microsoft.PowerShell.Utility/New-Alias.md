---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: c9e6f844b25abe5f2a94aa929eeeb457efab3d44
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197224"
---
# <span data-ttu-id="b6cc0-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="b6cc0-103">New-Alias</span></span>

## <span data-ttu-id="b6cc0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b6cc0-104">SYNOPSIS</span></span>
<span data-ttu-id="b6cc0-105">创建新别名。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-105">Creates a new alias.</span></span>

## <span data-ttu-id="b6cc0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6cc0-106">SYNTAX</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b6cc0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6cc0-107">DESCRIPTION</span></span>

<span data-ttu-id="b6cc0-108">**新别名** cmdlet 在当前 PowerShell 会话中创建新别名。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-108">The **New-Alias** cmdlet creates a new alias in the current PowerShell session.</span></span>
<span data-ttu-id="b6cc0-109">退出会话或关闭 PowerShell 后，不会保存使用 **新别名** 创建的别名。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-109">Aliases created by using **New-Alias** are not saved after you exit the session or close PowerShell.</span></span>
<span data-ttu-id="b6cc0-110">可以使用 Export-Alias cmdlet 来将你的别名信息保存到文件。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-110">You can use the Export-Alias cmdlet to save your alias information to a file.</span></span>
<span data-ttu-id="b6cc0-111">以后可以使用 **Import-Alias** 来检索已保存的别名信息。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-111">You can later use **Import-Alias** to retrieve that saved alias information.</span></span>

## <span data-ttu-id="b6cc0-112">示例</span><span class="sxs-lookup"><span data-stu-id="b6cc0-112">EXAMPLES</span></span>

### <span data-ttu-id="b6cc0-113">示例 1：创建 cmdlet 的别名</span><span class="sxs-lookup"><span data-stu-id="b6cc0-113">Example 1: Create an alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="b6cc0-114">此命令创建名为“List”的别名来表示 Get-ChildItem cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="b6cc0-115">示例 2：创建 cmdlet 的只读别名</span><span class="sxs-lookup"><span data-stu-id="b6cc0-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

<span data-ttu-id="b6cc0-116">此命令创建名为 W 的别名来表示 Get-WMIObject cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-116">This command creates an alias named W to represent the Get-WmiObject cmdlet.</span></span>
<span data-ttu-id="b6cc0-117">它为该别名创建了说明、快速 wmi 别名，并使其只读。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span>
<span data-ttu-id="b6cc0-118">该命令的最后一行使用 Get-Alias 来获取新别名，并通过管道将其传递给 Format-List 以显示有关它的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-118">The last line of the command uses Get-Alias to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="b6cc0-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6cc0-119">PARAMETERS</span></span>

### <span data-ttu-id="b6cc0-120">-Description</span><span class="sxs-lookup"><span data-stu-id="b6cc0-120">-Description</span></span>

<span data-ttu-id="b6cc0-121">指定对别名的描述。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-121">Specifies a description of the alias.</span></span>
<span data-ttu-id="b6cc0-122">你可以键入任意字符串。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-122">You can type any string.</span></span>
<span data-ttu-id="b6cc0-123">如果描述包含空格，则请将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-123">If the description includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="b6cc0-124">-Force</span><span class="sxs-lookup"><span data-stu-id="b6cc0-124">-Force</span></span>

<span data-ttu-id="b6cc0-125">如果命名的别名已存在，则指示该 cmdlet 用作 Set-Alias。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-125">Indicates that the cmdlet acts like Set-Alias if the alias named already exists.</span></span>

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

### <span data-ttu-id="b6cc0-126">-Name</span><span class="sxs-lookup"><span data-stu-id="b6cc0-126">-Name</span></span>

<span data-ttu-id="b6cc0-127">指定新的别名。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-127">Specifies the new alias.</span></span>
<span data-ttu-id="b6cc0-128">可以在别名中使用任何字母数字字符，但第一个字符不能为数字。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6cc0-129">-Option</span><span class="sxs-lookup"><span data-stu-id="b6cc0-129">-Option</span></span>

<span data-ttu-id="b6cc0-130">指定别名的 **Options** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="b6cc0-131">有效值是：</span><span class="sxs-lookup"><span data-stu-id="b6cc0-131">Valid values are:</span></span>

- <span data-ttu-id="b6cc0-132">无：别名没有 (默认值的约束) </span><span class="sxs-lookup"><span data-stu-id="b6cc0-132">None: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="b6cc0-133">ReadOnly：可以删除别名，但不能对其进行更改，除非使用 **Force** 参数</span><span class="sxs-lookup"><span data-stu-id="b6cc0-133">ReadOnly: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="b6cc0-134">常量：别名不能删除或更改</span><span class="sxs-lookup"><span data-stu-id="b6cc0-134">Constant: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="b6cc0-135">Private：别名仅在当前作用域内可用</span><span class="sxs-lookup"><span data-stu-id="b6cc0-135">Private: The alias is available only in the current scope</span></span>
- <span data-ttu-id="b6cc0-136">AllScope：将别名复制到任何创建的新作用域</span><span class="sxs-lookup"><span data-stu-id="b6cc0-136">AllScope: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="b6cc0-137">未指定：未指定选项</span><span class="sxs-lookup"><span data-stu-id="b6cc0-137">Unspecified: The option is not specified</span></span>

<span data-ttu-id="b6cc0-138">若要查看会话中所有别名的 **Options** 属性，请键入 `Get-Alias | Format-Table -Property Name, Options -AutoSize` 。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-138">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6cc0-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b6cc0-139">-PassThru</span></span>

<span data-ttu-id="b6cc0-140">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-140">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b6cc0-141">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b6cc0-142">-Scope</span><span class="sxs-lookup"><span data-stu-id="b6cc0-142">-Scope</span></span>

<span data-ttu-id="b6cc0-143">指定新别名的范围。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-143">Specifies the scope of the new alias.</span></span>
<span data-ttu-id="b6cc0-144">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="b6cc0-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b6cc0-145">全球</span><span class="sxs-lookup"><span data-stu-id="b6cc0-145">Global</span></span>
- <span data-ttu-id="b6cc0-146">Local</span><span class="sxs-lookup"><span data-stu-id="b6cc0-146">Local</span></span>
- <span data-ttu-id="b6cc0-147">脚本</span><span class="sxs-lookup"><span data-stu-id="b6cc0-147">Script</span></span>
- <span data-ttu-id="b6cc0-148">一个相对于当前作用域的数字（0 到作用域数，其中 0 是指当前作用域，1 是指其父作用域）。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-148">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="b6cc0-149">默认值为 Local。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-149">Local is the default.</span></span>
<span data-ttu-id="b6cc0-150">有关详细信息，请参阅 about_Scopes。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-150">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="b6cc0-151">-Value</span><span class="sxs-lookup"><span data-stu-id="b6cc0-151">-Value</span></span>

<span data-ttu-id="b6cc0-152">指定作为别名的 cmdlet 或命令元素的名称。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-152">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6cc0-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b6cc0-153">-Confirm</span></span>

<span data-ttu-id="b6cc0-154">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b6cc0-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b6cc0-155">-WhatIf</span></span>

<span data-ttu-id="b6cc0-156">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b6cc0-157">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b6cc0-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6cc0-158">CommonParameters</span></span>

<span data-ttu-id="b6cc0-159">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6cc0-160">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6cc0-161">输入</span><span class="sxs-lookup"><span data-stu-id="b6cc0-161">INPUTS</span></span>

### <span data-ttu-id="b6cc0-162">无</span><span class="sxs-lookup"><span data-stu-id="b6cc0-162">None</span></span>

<span data-ttu-id="b6cc0-163">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b6cc0-164">输出</span><span class="sxs-lookup"><span data-stu-id="b6cc0-164">OUTPUTS</span></span>

### <span data-ttu-id="b6cc0-165">无或 System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="b6cc0-165">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="b6cc0-166">使用 Passthru 参数时，**New-Alias** 将生成表示新别名的 **System.Management.Automation.AliasInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-166">When you use the *Passthru* parameter, **New-Alias** generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span>
<span data-ttu-id="b6cc0-167">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b6cc0-168">注释</span><span class="sxs-lookup"><span data-stu-id="b6cc0-168">NOTES</span></span>

* <span data-ttu-id="b6cc0-169">若要创建新别名，请使用 `Set-Alias` 或 `New-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-169">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="b6cc0-170">若要更改别名，请使用 `Set-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-170">To change an alias, use `Set-Alias`.</span></span> <span data-ttu-id="b6cc0-171">若要删除别名，请使用 `Remove-Item` 。</span><span class="sxs-lookup"><span data-stu-id="b6cc0-171">To delete an alias, use `Remove-Item`.</span></span>

## <span data-ttu-id="b6cc0-172">相关链接</span><span class="sxs-lookup"><span data-stu-id="b6cc0-172">RELATED LINKS</span></span>

[<span data-ttu-id="b6cc0-173">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="b6cc0-173">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="b6cc0-174">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="b6cc0-174">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="b6cc0-175">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="b6cc0-175">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="b6cc0-176">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="b6cc0-176">Set-Alias</span></span>](Set-Alias.md)
