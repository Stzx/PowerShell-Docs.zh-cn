---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: 9fd99e346d97b9a39298170371164753cf04dad8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197907"
---
# <span data-ttu-id="cc4f0-103">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="cc4f0-103">Get-Variable</span></span>

## <span data-ttu-id="cc4f0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cc4f0-104">SYNOPSIS</span></span>
<span data-ttu-id="cc4f0-105">获取当前控制台中的变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-105">Gets the variables in the current console.</span></span>

## <span data-ttu-id="cc4f0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cc4f0-106">SYNTAX</span></span>

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="cc4f0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cc4f0-107">DESCRIPTION</span></span>

<span data-ttu-id="cc4f0-108">`Get-Variable`Cmdlet 将获取当前控制台中的 PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-108">The `Get-Variable` cmdlet gets the PowerShell variables in the current console.</span></span>
<span data-ttu-id="cc4f0-109">通过指定 **ValueOnly** 参数可以只检索这些变量的值，还可以按名称筛选返回的变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-109">You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.</span></span>

## <span data-ttu-id="cc4f0-110">示例</span><span class="sxs-lookup"><span data-stu-id="cc4f0-110">EXAMPLES</span></span>

### <span data-ttu-id="cc4f0-111">示例 1：按字母获取变量</span><span class="sxs-lookup"><span data-stu-id="cc4f0-111">Example 1: Get variables by letter</span></span>

<span data-ttu-id="cc4f0-112">此命令将获取名称以字母 m 开头的变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-112">This command gets variables with names that begin with the letter m.</span></span>
<span data-ttu-id="cc4f0-113">该命令还将获取这些变量的值。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-113">The command also gets the value of the variables.</span></span>

```powershell
Get-Variable m*
```

### <span data-ttu-id="cc4f0-114">示例 2：按字母获取变量值</span><span class="sxs-lookup"><span data-stu-id="cc4f0-114">Example 2: Get variable values by letter</span></span>

<span data-ttu-id="cc4f0-115">此命令仅获取名称以 m 开头的变量的值。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-115">This command gets only the values of the variables that have names that begin with m.</span></span>

```powershell
Get-Variable m* -ValueOnly
```

### <span data-ttu-id="cc4f0-116">示例 3：按两个字母获取变量</span><span class="sxs-lookup"><span data-stu-id="cc4f0-116">Example 3: Get variables by two letters</span></span>

<span data-ttu-id="cc4f0-117">此命令将获取有关以字母 M 或字母 P 开头的变量的信息。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-117">This command gets information about the variables that begin with either the letter M or the letter P.</span></span>

```powershell
Get-Variable -Include M*,P*
```

### <span data-ttu-id="cc4f0-118">示例 4：按作用域获取变量</span><span class="sxs-lookup"><span data-stu-id="cc4f0-118">Example 4: Get variables by scope</span></span>

<span data-ttu-id="cc4f0-119">第一个命令仅获取在本地作用域中定义的变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-119">The first command gets only the variables that are defined in the local scope.</span></span>
<span data-ttu-id="cc4f0-120">它等效于 `Get-Variable -Scope Local`，可以缩写为 `gv -s 0`。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-120">It is equivalent to `Get-Variable -Scope Local` and can be abbreviated as `gv -s 0`.</span></span>

<span data-ttu-id="cc4f0-121">第二个命令使用 `Compare-Object` cmdlet 来查找在父作用域中定义的变量 (作用域 1) ，但仅在本地作用域 (范围 0) 中可见。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-121">The second command uses the `Compare-Object` cmdlet to find the variables that are defined in the parent scope (Scope 1) but are visible only in the local scope (Scope 0).</span></span>

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## <span data-ttu-id="cc4f0-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cc4f0-122">PARAMETERS</span></span>

### <span data-ttu-id="cc4f0-123">-Exclude</span><span class="sxs-lookup"><span data-stu-id="cc4f0-123">-Exclude</span></span>

<span data-ttu-id="cc4f0-124">指定此 cmdlet 将从操作中排除的项数组。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-124">Specifies an array of items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="cc4f0-125">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="cc4f0-126">-Include</span><span class="sxs-lookup"><span data-stu-id="cc4f0-126">-Include</span></span>

<span data-ttu-id="cc4f0-127">指定此 cmdlet 会对其执行操作的项的数组（排除所有其他项）。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-127">Specifies an array of items upon which the cmdlet will act, excluding all others.</span></span>
<span data-ttu-id="cc4f0-128">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="cc4f0-129">-Name</span><span class="sxs-lookup"><span data-stu-id="cc4f0-129">-Name</span></span>

<span data-ttu-id="cc4f0-130">指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-130">Specifies the name of the variable.</span></span>
<span data-ttu-id="cc4f0-131">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-131">Wildcards are permitted.</span></span>
<span data-ttu-id="cc4f0-132">还可以通过管道将变量名传递给 `Get-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-132">You can also pipe a variable name to `Get-Variable`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="cc4f0-133">-Scope</span><span class="sxs-lookup"><span data-stu-id="cc4f0-133">-Scope</span></span>

<span data-ttu-id="cc4f0-134">指定作用域中的变量。此参数可接受的值包括：</span><span class="sxs-lookup"><span data-stu-id="cc4f0-134">Specifies the variables in the scope.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cc4f0-135">**全球**</span><span class="sxs-lookup"><span data-stu-id="cc4f0-135">**Global**</span></span>
- <span data-ttu-id="cc4f0-136">本地</span><span class="sxs-lookup"><span data-stu-id="cc4f0-136">**Local**</span></span>
- <span data-ttu-id="cc4f0-137">**脚本**</span><span class="sxs-lookup"><span data-stu-id="cc4f0-137">**Script**</span></span>
- <span data-ttu-id="cc4f0-138">一个相对于当前作用域的数字（0 到作用域数，其中 0 是指当前作用域，1 是指其父作用域）</span><span class="sxs-lookup"><span data-stu-id="cc4f0-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="cc4f0-139">默认值为 **Local** 。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-139">**Local** is the default.</span></span>
<span data-ttu-id="cc4f0-140">有关详细信息，请参阅 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="cc4f0-141">-ValueOnly</span><span class="sxs-lookup"><span data-stu-id="cc4f0-141">-ValueOnly</span></span>

<span data-ttu-id="cc4f0-142">指示此 cmdlet 仅获取变量的值。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-142">Indicates that this cmdlet gets only the value of the variable.</span></span>

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

### <span data-ttu-id="cc4f0-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cc4f0-143">CommonParameters</span></span>

<span data-ttu-id="cc4f0-144">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cc4f0-145">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-145">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="cc4f0-146">输入</span><span class="sxs-lookup"><span data-stu-id="cc4f0-146">INPUTS</span></span>

### <span data-ttu-id="cc4f0-147">System.String</span><span class="sxs-lookup"><span data-stu-id="cc4f0-147">System.String</span></span>

<span data-ttu-id="cc4f0-148">可以通过管道将包含变量名称的字符串传递给 `Get-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-148">You can pipe a string that contains the variable name to `Get-Variable`.</span></span>

## <span data-ttu-id="cc4f0-149">输出</span><span class="sxs-lookup"><span data-stu-id="cc4f0-149">OUTPUTS</span></span>

### <span data-ttu-id="cc4f0-150">System.Management.Automation.PSVariable</span><span class="sxs-lookup"><span data-stu-id="cc4f0-150">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="cc4f0-151">此 cmdlet 为它所获取的每个变量返回一个 **System.Management.AutomationPSVariable** 对象。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-151">This cmdlet returns a **System.Management.AutomationPSVariable** object for each variable that it gets.</span></span> <span data-ttu-id="cc4f0-152">对象类型取决于变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-152">The object type depends on the variable.</span></span>

### <span data-ttu-id="cc4f0-153">System.object []</span><span class="sxs-lookup"><span data-stu-id="cc4f0-153">System.Object[]</span></span>

<span data-ttu-id="cc4f0-154">当指定 **ValueOnly** 参数时，如果指定变量的值为集合，则 `Get-Variable` 返回 `[System.Object[]]` 。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-154">When you specify the **ValueOnly** parameter, if the specified variable's value is a collection, `Get-Variable` returns a `[System.Object[]]`.</span></span> <span data-ttu-id="cc4f0-155">此行为可防止正常管道操作一次处理一个变量的值。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-155">This behavior prevents normal pipeline operation from processing the variable's values one at a time.</span></span> <span data-ttu-id="cc4f0-156">强制集合枚举的一种解决方法是将 `Get-Variable` 命令括在括号中。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-156">A workaround to force collection enumeration is to enclose the `Get-Variable` command in parenthesis.</span></span>

## <span data-ttu-id="cc4f0-157">注释</span><span class="sxs-lookup"><span data-stu-id="cc4f0-157">NOTES</span></span>

- <span data-ttu-id="cc4f0-158">此 cmdlet 不管理环境变量。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-158">This cmdlet does not manage environment variables.</span></span> <span data-ttu-id="cc4f0-159">若要管理环境变量，可以使用环境变量提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc4f0-159">To manage environment variables, you can use the environment variable provider.</span></span>

## <span data-ttu-id="cc4f0-160">相关链接</span><span class="sxs-lookup"><span data-stu-id="cc4f0-160">RELATED LINKS</span></span>

[<span data-ttu-id="cc4f0-161">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="cc4f0-161">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="cc4f0-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="cc4f0-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="cc4f0-163">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="cc4f0-163">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="cc4f0-164">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="cc4f0-164">Set-Variable</span></span>](Set-Variable.md)