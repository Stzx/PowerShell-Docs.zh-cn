---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: e6bbb1415a29b8dc3ef916ecc6c3e8bc6754583d
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199152"
---
# <span data-ttu-id="ea146-103">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="ea146-103">Remove-Variable</span></span>

## <span data-ttu-id="ea146-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ea146-104">SYNOPSIS</span></span>
<span data-ttu-id="ea146-105">删除变量及其值。</span><span class="sxs-lookup"><span data-stu-id="ea146-105">Deletes a variable and its value.</span></span>

## <span data-ttu-id="ea146-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea146-106">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ea146-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea146-107">DESCRIPTION</span></span>

<span data-ttu-id="ea146-108">`Remove-Variable`Cmdlet 从定义变量的作用域中删除变量及其值，如当前会话。</span><span class="sxs-lookup"><span data-stu-id="ea146-108">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="ea146-109">你不能使用此 cmdlet 删除设置为常量或由系统所拥有的变量。</span><span class="sxs-lookup"><span data-stu-id="ea146-109">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="ea146-110">示例</span><span class="sxs-lookup"><span data-stu-id="ea146-110">EXAMPLES</span></span>

### <span data-ttu-id="ea146-111">示例1：删除变量</span><span class="sxs-lookup"><span data-stu-id="ea146-111">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="ea146-112">此命令删除 `$Smp` 变量。</span><span class="sxs-lookup"><span data-stu-id="ea146-112">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="ea146-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea146-113">PARAMETERS</span></span>

### <span data-ttu-id="ea146-114">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ea146-114">-Exclude</span></span>

<span data-ttu-id="ea146-115">指定此 cmdlet 从操作中省略的项的数组。</span><span class="sxs-lookup"><span data-stu-id="ea146-115">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="ea146-116">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ea146-116">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ea146-117">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="ea146-117">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="ea146-118">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea146-118">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ea146-119">-Force</span><span class="sxs-lookup"><span data-stu-id="ea146-119">-Force</span></span>

<span data-ttu-id="ea146-120">指示该 cmdlet 删除变量，即使该变量是只读的。</span><span class="sxs-lookup"><span data-stu-id="ea146-120">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="ea146-121">即使使用 **Force** 参数，cmdlet 也无法删除常量。</span><span class="sxs-lookup"><span data-stu-id="ea146-121">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="ea146-122">-Include</span><span class="sxs-lookup"><span data-stu-id="ea146-122">-Include</span></span>

<span data-ttu-id="ea146-123">指定此 cmdlet 在操作中删除的项的数组。</span><span class="sxs-lookup"><span data-stu-id="ea146-123">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="ea146-124">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ea146-124">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ea146-125">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="ea146-125">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="ea146-126">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea146-126">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ea146-127">-Name</span><span class="sxs-lookup"><span data-stu-id="ea146-127">-Name</span></span>

<span data-ttu-id="ea146-128">指定要删除的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ea146-128">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="ea146-129"> ( **名称** ) 的参数名称是可选的。</span><span class="sxs-lookup"><span data-stu-id="ea146-129">The parameter name ( **Name** ) is optional.</span></span>
<span data-ttu-id="ea146-130">允许使用通配符</span><span class="sxs-lookup"><span data-stu-id="ea146-130">Wildcards are permitted</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ea146-131">-Scope</span><span class="sxs-lookup"><span data-stu-id="ea146-131">-Scope</span></span>

<span data-ttu-id="ea146-132">仅获取指定作用域中的变量。</span><span class="sxs-lookup"><span data-stu-id="ea146-132">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="ea146-133">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ea146-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ea146-134">全球</span><span class="sxs-lookup"><span data-stu-id="ea146-134">Global</span></span>
- <span data-ttu-id="ea146-135">Local</span><span class="sxs-lookup"><span data-stu-id="ea146-135">Local</span></span>
- <span data-ttu-id="ea146-136">脚本</span><span class="sxs-lookup"><span data-stu-id="ea146-136">Script</span></span>
- <span data-ttu-id="ea146-137">一个相对于当前作用域的数字（0 到作用域数，其中 0 是指当前作用域，1 是指其父作用域）</span><span class="sxs-lookup"><span data-stu-id="ea146-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="ea146-138">默认值为 Local。</span><span class="sxs-lookup"><span data-stu-id="ea146-138">Local is the default.</span></span> <span data-ttu-id="ea146-139">有关详细信息，请参阅 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="ea146-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="ea146-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ea146-140">-Confirm</span></span>

<span data-ttu-id="ea146-141">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="ea146-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ea146-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ea146-142">-WhatIf</span></span>

<span data-ttu-id="ea146-143">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ea146-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ea146-144">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ea146-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ea146-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ea146-145">CommonParameters</span></span>

<span data-ttu-id="ea146-146">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ea146-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea146-147">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ea146-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea146-148">输入</span><span class="sxs-lookup"><span data-stu-id="ea146-148">INPUTS</span></span>

### <span data-ttu-id="ea146-149">System.Management.Automation.PSVariable</span><span class="sxs-lookup"><span data-stu-id="ea146-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="ea146-150">可以通过管道将变量对象传递给 `Remove-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="ea146-150">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="ea146-151">输出</span><span class="sxs-lookup"><span data-stu-id="ea146-151">OUTPUTS</span></span>

### <span data-ttu-id="ea146-152">无</span><span class="sxs-lookup"><span data-stu-id="ea146-152">None</span></span>

<span data-ttu-id="ea146-153">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="ea146-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="ea146-154">注释</span><span class="sxs-lookup"><span data-stu-id="ea146-154">NOTES</span></span>

- <span data-ttu-id="ea146-155">更改仅影响当前作用域，例如会话。</span><span class="sxs-lookup"><span data-stu-id="ea146-155">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="ea146-156">若要从所有会话中删除某个变量，请将 `Remove-Variable` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea146-156">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="ea146-157">还可以 `Remove-Variable` 通过其内置别名来引用 `rv` 。</span><span class="sxs-lookup"><span data-stu-id="ea146-157">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="ea146-158">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="ea146-158">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="ea146-159">相关链接</span><span class="sxs-lookup"><span data-stu-id="ea146-159">RELATED LINKS</span></span>

[<span data-ttu-id="ea146-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="ea146-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="ea146-161">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="ea146-161">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="ea146-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="ea146-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="ea146-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="ea146-163">Set-Variable</span></span>](Set-Variable.md)
