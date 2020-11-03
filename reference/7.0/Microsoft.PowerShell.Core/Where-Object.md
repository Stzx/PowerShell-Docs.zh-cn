---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 0d9101c751e9ebc0b0c6fe80564bb76524de8bb6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196887"
---
# <span data-ttu-id="0f394-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-103">Where-Object</span></span>

## <span data-ttu-id="0f394-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0f394-104">SYNOPSIS</span></span>
<span data-ttu-id="0f394-105">根据属性值从集合中选择对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="0f394-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f394-106">SYNTAX</span></span>

### <span data-ttu-id="0f394-107">EqualSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="0f394-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-108">ScriptBlockSet</span><span class="sxs-lookup"><span data-stu-id="0f394-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="0f394-109">MatchSet</span><span class="sxs-lookup"><span data-stu-id="0f394-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-110">CaseSensitiveEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-111">NotEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-112">CaseSensitiveNotEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-113">GreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="0f394-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-114">CaseSensitiveGreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="0f394-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-115">LessThanSet</span><span class="sxs-lookup"><span data-stu-id="0f394-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-116">CaseSensitiveLessThanSet</span><span class="sxs-lookup"><span data-stu-id="0f394-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-117">GreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-118">CaseSensitiveGreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-119">LessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-120">CaseSensitiveLessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0f394-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-121">LikeSet</span><span class="sxs-lookup"><span data-stu-id="0f394-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-122">CaseSensitiveLikeSet</span><span class="sxs-lookup"><span data-stu-id="0f394-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-123">NotLikeSet</span><span class="sxs-lookup"><span data-stu-id="0f394-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-124">CaseSensitiveNotLikeSet</span><span class="sxs-lookup"><span data-stu-id="0f394-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-125">CaseSensitiveMatchSet</span><span class="sxs-lookup"><span data-stu-id="0f394-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-126">NotMatchSet</span><span class="sxs-lookup"><span data-stu-id="0f394-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-127">CaseSensitiveNotMatchSet</span><span class="sxs-lookup"><span data-stu-id="0f394-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-128">ContainsSet</span><span class="sxs-lookup"><span data-stu-id="0f394-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-129">CaseSensitiveContainsSet</span><span class="sxs-lookup"><span data-stu-id="0f394-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-130">NotContainsSet</span><span class="sxs-lookup"><span data-stu-id="0f394-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-131">CaseSensitiveNotContainsSet</span><span class="sxs-lookup"><span data-stu-id="0f394-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-132">嵌入</span><span class="sxs-lookup"><span data-stu-id="0f394-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-133">CaseSensitiveInSet</span><span class="sxs-lookup"><span data-stu-id="0f394-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-134">NotInSet</span><span class="sxs-lookup"><span data-stu-id="0f394-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-135">CaseSensitiveNotInSet</span><span class="sxs-lookup"><span data-stu-id="0f394-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-136">IsSet</span><span class="sxs-lookup"><span data-stu-id="0f394-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-137">IsNotSet</span><span class="sxs-lookup"><span data-stu-id="0f394-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="0f394-138">Not</span><span class="sxs-lookup"><span data-stu-id="0f394-138">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="0f394-139">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f394-139">DESCRIPTION</span></span>

<span data-ttu-id="0f394-140">`Where-Object`Cmdlet 从传递给它的对象集合中选择具有特定属性值的对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-140">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="0f394-141">例如，你可以使用 `Where-Object` cmdlet 来选择在特定日期之后创建的文件、具有特定 ID 的事件，或使用特定版本的 Windows 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0f394-141">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="0f394-142">从 Windows PowerShell 3.0 开始，可以使用两种不同的方法来构造 `Where-Object` 命令。</span><span class="sxs-lookup"><span data-stu-id="0f394-142">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="0f394-143">**脚本块** 。</span><span class="sxs-lookup"><span data-stu-id="0f394-143">**Script block** .</span></span> <span data-ttu-id="0f394-144">你可以使用脚本块指定属性名称、比较运算符和属性值。</span><span class="sxs-lookup"><span data-stu-id="0f394-144">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="0f394-145">`Where-Object` 返回脚本块语句为 true 的所有对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-145">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="0f394-146">例如，下面的命令获取一般优先级类中的进程，即 **PriorityClass** 属性的值等于 Normal 的进程。</span><span class="sxs-lookup"><span data-stu-id="0f394-146">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="0f394-147">所有 PowerShell 比较运算符在脚本块格式中都有效。</span><span class="sxs-lookup"><span data-stu-id="0f394-147">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="0f394-148">有关比较运算符的详细信息，请参阅 [about_Comparison_Operators](./About/about_Comparison_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="0f394-148">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="0f394-149">**比较语句** 。</span><span class="sxs-lookup"><span data-stu-id="0f394-149">**Comparison statement** .</span></span> <span data-ttu-id="0f394-150">你还可以编写比较语句，它更像自然语言。</span><span class="sxs-lookup"><span data-stu-id="0f394-150">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="0f394-151">Windows PowerShell 3.0 中引入了比较语句。</span><span class="sxs-lookup"><span data-stu-id="0f394-151">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="0f394-152">例如，以下命令还获取优先级为 Normal 的进程。</span><span class="sxs-lookup"><span data-stu-id="0f394-152">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="0f394-153">这些命令是等效的，因此可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="0f394-153">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="0f394-154">从 Windows PowerShell 3.0 开始， `Where-Object` 将比较运算符作为参数添加到 `Where-Object` 命令中。</span><span class="sxs-lookup"><span data-stu-id="0f394-154">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="0f394-155">除非另有指定，否则所有运算符都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-155">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="0f394-156">在 Windows PowerShell 3.0 之前，PowerShell 语言中的比较运算符仅可在脚本块中使用。</span><span class="sxs-lookup"><span data-stu-id="0f394-156">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="0f394-157">向提供单个 **属性** 时 `Where-Object` ，属性的值将被视为布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="0f394-157">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="0f394-158">当 **Length** 的值不为零时，表达式的计算结果为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="0f394-158">When the value of **Length** is not zero, the expression evaluates to **True** .</span></span> <span data-ttu-id="0f394-159">例如：`('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="0f394-159">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="0f394-160">上一示例在功能上等效于：</span><span class="sxs-lookup"><span data-stu-id="0f394-160">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="0f394-161">示例</span><span class="sxs-lookup"><span data-stu-id="0f394-161">EXAMPLES</span></span>

### <span data-ttu-id="0f394-162">示例1：获取已停止的服务</span><span class="sxs-lookup"><span data-stu-id="0f394-162">Example 1: Get stopped services</span></span>

<span data-ttu-id="0f394-163">这些命令将获取当前已停止的所有服务的列表。</span><span class="sxs-lookup"><span data-stu-id="0f394-163">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="0f394-164">`$_`自动变量表示传递到 cmdlet 的每个对象 `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0f394-164">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="0f394-165">第一个命令使用脚本块格式，第二个命令使用比较语句格式。</span><span class="sxs-lookup"><span data-stu-id="0f394-165">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="0f394-166">这两个命令是等效的，因此可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="0f394-166">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="0f394-167">示例2：基于工作集获取进程</span><span class="sxs-lookup"><span data-stu-id="0f394-167">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="0f394-168">这些命令列出了工作集大于 250 mb (KB) 的进程。</span><span class="sxs-lookup"><span data-stu-id="0f394-168">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="0f394-169">Scriptblock 和语句语法是等效的，可互换使用。</span><span class="sxs-lookup"><span data-stu-id="0f394-169">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="0f394-170">示例3：基于进程名称获取进程</span><span class="sxs-lookup"><span data-stu-id="0f394-170">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="0f394-171">这些命令将获取 **ProcessName** 属性值以字母开头的进程 `p` 。</span><span class="sxs-lookup"><span data-stu-id="0f394-171">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="0f394-172">**Match** 运算符使你可以使用正则表达式匹配。</span><span class="sxs-lookup"><span data-stu-id="0f394-172">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="0f394-173">Scriptblock 和语句语法是等效的，可互换使用。</span><span class="sxs-lookup"><span data-stu-id="0f394-173">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="0f394-174">示例4：使用比较语句格式</span><span class="sxs-lookup"><span data-stu-id="0f394-174">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="0f394-175">此示例演示如何使用 cmdlet 的新比较语句格式 `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0f394-175">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="0f394-176">第一个命令使用比较语句格式。</span><span class="sxs-lookup"><span data-stu-id="0f394-176">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="0f394-177">在此命令中，未使用别名，并且所有参数都包含参数名称。</span><span class="sxs-lookup"><span data-stu-id="0f394-177">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="0f394-178">第二个命令是比较命令格式的更自然的用法。</span><span class="sxs-lookup"><span data-stu-id="0f394-178">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="0f394-179">该 `where` 别名替换为 `Where-Object` cmdlet 名称，并且省略了所有可选参数名称。</span><span class="sxs-lookup"><span data-stu-id="0f394-179">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="0f394-180">示例5：获取基于属性的命令</span><span class="sxs-lookup"><span data-stu-id="0f394-180">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="0f394-181">此示例演示如何编写可返回项（true 或 false）的命令或具有指定属性的任意值的命令。</span><span class="sxs-lookup"><span data-stu-id="0f394-181">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="0f394-182">每个示例显示该命令的脚本块和比较语句格式。</span><span class="sxs-lookup"><span data-stu-id="0f394-182">Each example shows both the script block and comparison statement formats for the command.</span></span>

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### <span data-ttu-id="0f394-183">示例6：使用多个条件</span><span class="sxs-lookup"><span data-stu-id="0f394-183">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="0f394-184">此示例演示如何创建 `Where-Object` 具有多个条件的命令。</span><span class="sxs-lookup"><span data-stu-id="0f394-184">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="0f394-185">此命令可获取用于支持可更新帮助功能的非核心模块。</span><span class="sxs-lookup"><span data-stu-id="0f394-185">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="0f394-186">该命令使用 cmdlet 的 **ListAvailable** 参数 `Get-Module` 来获取计算机上的所有模块。</span><span class="sxs-lookup"><span data-stu-id="0f394-186">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="0f394-187">管道运算符 (`|`) 将模块发送到 `Where-Object` cmdlet，该 cmdlet 将获取名称不以 MICROSOFT 或 PS 开头的模块，并为 **HelpInfoURI** 属性提供一个值，该值指示 PowerShell 在何处找到该模块的更新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="0f394-187">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="0f394-188">比较语句由 **和** 逻辑运算符连接。</span><span class="sxs-lookup"><span data-stu-id="0f394-188">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="0f394-189">该示例使用脚本块命令格式。</span><span class="sxs-lookup"><span data-stu-id="0f394-189">The example uses the script block command format.</span></span> <span data-ttu-id="0f394-190">逻辑运算符（如 **and** 和 **Or** ）仅在脚本块中有效。</span><span class="sxs-lookup"><span data-stu-id="0f394-190">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="0f394-191">不能以命令的比较语句格式使用它们 `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0f394-191">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="0f394-192">有关 PowerShell 逻辑运算符的详细信息，请参阅 [about_Logical_Operators](./About/about_logical_operators.md)。</span><span class="sxs-lookup"><span data-stu-id="0f394-192">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="0f394-193">有关可更新帮助功能的详细信息，请参阅 [about_Updatable_Help](./About/about_Updatable_Help.md)。</span><span class="sxs-lookup"><span data-stu-id="0f394-193">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="0f394-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f394-194">PARAMETERS</span></span>

### <span data-ttu-id="0f394-195">-包含</span><span class="sxs-lookup"><span data-stu-id="0f394-195">-CContains</span></span>

<span data-ttu-id="0f394-196">指示如果对象的属性值与指定值完全匹配，此 cmdlet 将从集合中获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-196">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="0f394-197">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-197">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-198">例如：`Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="0f394-198">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="0f394-199">**包含** 引用值的集合，如果集合包含与指定值完全匹配的项，则为 true。</span><span class="sxs-lookup"><span data-stu-id="0f394-199">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="0f394-200">如果输入是单个对象，则 PowerShell 会将其转换为一个对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0f394-200">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0f394-201">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-202">-CEQ</span><span class="sxs-lookup"><span data-stu-id="0f394-202">-CEQ</span></span>

<span data-ttu-id="0f394-203">指示此 cmdlet 获取对象（如果属性值与指定的值相同）。</span><span class="sxs-lookup"><span data-stu-id="0f394-203">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="0f394-204">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-204">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-205">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-206">-CGE</span><span class="sxs-lookup"><span data-stu-id="0f394-206">-CGE</span></span>

<span data-ttu-id="0f394-207">指示此 cmdlet 获取对象（如果属性值大于或等于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-207">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="0f394-208">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-208">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-209">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-209">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-210">-CGT</span><span class="sxs-lookup"><span data-stu-id="0f394-210">-CGT</span></span>

<span data-ttu-id="0f394-211">指示此 cmdlet 获取对象（如果属性值大于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-211">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="0f394-212">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-212">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-213">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-213">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-214">-CIn</span><span class="sxs-lookup"><span data-stu-id="0f394-214">-CIn</span></span>

<span data-ttu-id="0f394-215">指示此 cmdlet 在属性值包含指定值时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-215">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="0f394-216">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-216">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-217">例如：`Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="0f394-217">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="0f394-218">**CIn** 类似于 **包含** ，只不过属性和值位置是相反的。</span><span class="sxs-lookup"><span data-stu-id="0f394-218">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="0f394-219">例如，以下语句都为 true。</span><span class="sxs-lookup"><span data-stu-id="0f394-219">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="0f394-220">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-221">-CLE</span><span class="sxs-lookup"><span data-stu-id="0f394-221">-CLE</span></span>

<span data-ttu-id="0f394-222">指示在属性值小于或等于指定值的情况下，此 cmdlet 将获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-222">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="0f394-223">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-223">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-224">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-225">-CLike</span><span class="sxs-lookup"><span data-stu-id="0f394-225">-CLike</span></span>

<span data-ttu-id="0f394-226">指示此 cmdlet 在属性值与包含通配符的值匹配时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-226">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="0f394-227">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-227">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-228">例如：`Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="0f394-228">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="0f394-229">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-230">-CLT</span><span class="sxs-lookup"><span data-stu-id="0f394-230">-CLT</span></span>

<span data-ttu-id="0f394-231">指示此 cmdlet 获取对象（如果属性值小于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-231">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="0f394-232">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-232">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-233">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-234">-CMatch</span><span class="sxs-lookup"><span data-stu-id="0f394-234">-CMatch</span></span>

<span data-ttu-id="0f394-235">指示此 cmdlet 在属性值与指定的正则表达式匹配时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-235">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="0f394-236">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-236">This operation is case-sensitive.</span></span> <span data-ttu-id="0f394-237">当输入是标量时，匹配的值将保存在 `$Matches` 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="0f394-237">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0f394-238">例如：`Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="0f394-238">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="0f394-239">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-240">-CNE</span><span class="sxs-lookup"><span data-stu-id="0f394-240">-CNE</span></span>

<span data-ttu-id="0f394-241">指示此 cmdlet 获取对象（如果属性值不同于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-241">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="0f394-242">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-242">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-243">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-244">-CNotContains</span><span class="sxs-lookup"><span data-stu-id="0f394-244">-CNotContains</span></span>

<span data-ttu-id="0f394-245">指示如果对象的属性值与指定的值不完全匹配，则此 cmdlet 将获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-245">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="0f394-246">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-246">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-247">例如：`Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="0f394-247">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="0f394-248">**NotContains** 和 **CNotContains** 引用值的集合，并且在集合不包含与指定值完全匹配的任何项时为 true。</span><span class="sxs-lookup"><span data-stu-id="0f394-248">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="0f394-249">如果输入是单个对象，则 PowerShell 会将其转换为一个对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0f394-249">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0f394-250">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-251">-CNotIn</span><span class="sxs-lookup"><span data-stu-id="0f394-251">-CNotIn</span></span>

<span data-ttu-id="0f394-252">指示此 cmdlet 获取对象（如果属性值不是指定值的完全匹配项）。</span><span class="sxs-lookup"><span data-stu-id="0f394-252">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="0f394-253">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-253">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-254">例如：`Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="0f394-254">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="0f394-255">**NotIn** 和 **CNotIn** 运算符类似于 **NotContains** 和 **CNotContains** ，只不过属性和值位置是相反的。</span><span class="sxs-lookup"><span data-stu-id="0f394-255">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="0f394-256">例如，以下语句为 true。</span><span class="sxs-lookup"><span data-stu-id="0f394-256">For example, the following statements are true.</span></span>

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-257">-CNotLike</span><span class="sxs-lookup"><span data-stu-id="0f394-257">-CNotLike</span></span>

<span data-ttu-id="0f394-258">指示如果属性值与包含通配符的值不匹配，则此 cmdlet 将获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-258">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="0f394-259">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-259">This operation is case-sensitive.</span></span>

<span data-ttu-id="0f394-260">例如：`Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="0f394-260">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="0f394-261">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-262">-CNotMatch</span><span class="sxs-lookup"><span data-stu-id="0f394-262">-CNotMatch</span></span>

<span data-ttu-id="0f394-263">指示此 cmdlet 在属性值与指定的正则表达式不匹配时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-263">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="0f394-264">此操作区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f394-264">This operation is case-sensitive.</span></span> <span data-ttu-id="0f394-265">当输入是标量时，匹配的值将保存在 `$Matches` 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="0f394-265">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0f394-266">例如：`Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="0f394-266">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="0f394-267">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-268">-Contains</span><span class="sxs-lookup"><span data-stu-id="0f394-268">-Contains</span></span>

<span data-ttu-id="0f394-269">指示如果对象的属性值中的任何项与指定值完全匹配，则此 cmdlet 将获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-269">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="0f394-270">例如：`Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="0f394-270">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="0f394-271">如果属性值包含单个对象，则 PowerShell 会将其转换为一个对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0f394-271">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0f394-272">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-273">-EQ</span><span class="sxs-lookup"><span data-stu-id="0f394-273">-EQ</span></span>

<span data-ttu-id="0f394-274">指示此 cmdlet 获取对象（如果属性值与指定的值相同）。</span><span class="sxs-lookup"><span data-stu-id="0f394-274">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="0f394-275">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-276">-FilterScript</span><span class="sxs-lookup"><span data-stu-id="0f394-276">-FilterScript</span></span>

<span data-ttu-id="0f394-277">指定用于筛选对象的脚本块。</span><span class="sxs-lookup"><span data-stu-id="0f394-277">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="0f394-278">将脚本块括在大括号中， (`{}`) 。</span><span class="sxs-lookup"><span data-stu-id="0f394-278">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="0f394-279">参数 name （ **FilterScript** ）是可选的。</span><span class="sxs-lookup"><span data-stu-id="0f394-279">The parameter name, **FilterScript** , is optional.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-280">-GE</span><span class="sxs-lookup"><span data-stu-id="0f394-280">-GE</span></span>

<span data-ttu-id="0f394-281">指示此 cmdlet 获取对象（如果属性值大于或等于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-281">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="0f394-282">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-283">-GT</span><span class="sxs-lookup"><span data-stu-id="0f394-283">-GT</span></span>

<span data-ttu-id="0f394-284">指示此 cmdlet 获取对象（如果属性值大于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-284">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="0f394-285">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-286">-在中</span><span class="sxs-lookup"><span data-stu-id="0f394-286">-In</span></span>

<span data-ttu-id="0f394-287">指示此 cmdlet 获取对象（如果属性值与任何指定值匹配）。</span><span class="sxs-lookup"><span data-stu-id="0f394-287">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="0f394-288">例如：</span><span class="sxs-lookup"><span data-stu-id="0f394-288">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="0f394-289">如果 **value** 参数的值是单个对象，则 PowerShell 会将其转换为一个对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0f394-289">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0f394-290">如果对象的属性值是一个数组，则 PowerShell 将使用引用相等性来确定匹配项。</span><span class="sxs-lookup"><span data-stu-id="0f394-290">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="0f394-291">`Where-Object` 仅当 **Property** 参数的值和 **value** 的任何值都是对象的相同实例时才返回对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-291">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="0f394-292">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-293">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0f394-293">-InputObject</span></span>

<span data-ttu-id="0f394-294">指定要筛选的对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-294">Specifies the objects to be filtered.</span></span> <span data-ttu-id="0f394-295">还可以通过管道将对象传递给 `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0f394-295">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="0f394-296">当你将 **inputobject** 参数与一起使用时 `Where-Object` ， `Where-Object` **inputobject** 值将被视为单个对象，而不是管道将命令结果传递给。</span><span class="sxs-lookup"><span data-stu-id="0f394-296">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="0f394-297">即使该值是作为命令结果的集合（如），也是如此 `-InputObject (Get-Process)` 。</span><span class="sxs-lookup"><span data-stu-id="0f394-297">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="0f394-298">由于 **InputObject** 无法从数组或对象的集合返回各个属性，因此，如果您使用 `Where-Object` 筛选在定义的属性中具有特定值的那些对象的对象集合，则建议在管道中使用 `Where-Object` ，如本主题的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0f394-298">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-299">-为</span><span class="sxs-lookup"><span data-stu-id="0f394-299">-Is</span></span>

<span data-ttu-id="0f394-300">指示此 cmdlet 获取对象（如果属性值为指定 .NET 类型的实例）。</span><span class="sxs-lookup"><span data-stu-id="0f394-300">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="0f394-301">将类型名称括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="0f394-301">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="0f394-302">例如： `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="0f394-302">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="0f394-303">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-303">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-304">-IsNot</span><span class="sxs-lookup"><span data-stu-id="0f394-304">-IsNot</span></span>

<span data-ttu-id="0f394-305">指示此 cmdlet 获取对象（如果属性值不是指定 .NET 类型的实例）。</span><span class="sxs-lookup"><span data-stu-id="0f394-305">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="0f394-306">例如： `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="0f394-306">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="0f394-307">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-307">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-308">-LE</span><span class="sxs-lookup"><span data-stu-id="0f394-308">-LE</span></span>

<span data-ttu-id="0f394-309">指示此 cmdlet 在属性值小于或等于指定值时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-309">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="0f394-310">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-311">-Like</span><span class="sxs-lookup"><span data-stu-id="0f394-311">-Like</span></span>

<span data-ttu-id="0f394-312">指示此 cmdlet 在属性值与包含通配符的值匹配时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-312">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="0f394-313">例如：`Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="0f394-313">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="0f394-314">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-314">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-315">-LT</span><span class="sxs-lookup"><span data-stu-id="0f394-315">-LT</span></span>

<span data-ttu-id="0f394-316">指示此 cmdlet 获取对象（如果属性值小于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-316">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="0f394-317">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-317">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-318">-Match</span><span class="sxs-lookup"><span data-stu-id="0f394-318">-Match</span></span>

<span data-ttu-id="0f394-319">指示此 cmdlet 在属性值与指定的正则表达式匹配时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-319">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="0f394-320">当输入是标量时，匹配的值将保存在 `$Matches` 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="0f394-320">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0f394-321">例如：`Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="0f394-321">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="0f394-322">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-323">-NE</span><span class="sxs-lookup"><span data-stu-id="0f394-323">-NE</span></span>

<span data-ttu-id="0f394-324">指示此 cmdlet 获取对象（如果属性值不同于指定值）。</span><span class="sxs-lookup"><span data-stu-id="0f394-324">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="0f394-325">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-325">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-326">-Not</span><span class="sxs-lookup"><span data-stu-id="0f394-326">-Not</span></span>

<span data-ttu-id="0f394-327">指示此 cmdlet 获取对象（如果属性不存在）或值为 null 或 false。</span><span class="sxs-lookup"><span data-stu-id="0f394-327">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="0f394-328">例如：`Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="0f394-328">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="0f394-329">此参数是在 Windows PowerShell 6.1 中引入的。</span><span class="sxs-lookup"><span data-stu-id="0f394-329">This parameter was introduced in Windows PowerShell 6.1.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-330">-NotContains</span><span class="sxs-lookup"><span data-stu-id="0f394-330">-NotContains</span></span>

<span data-ttu-id="0f394-331">指示如果属性值中的任何项都不是指定值的完全匹配项，则此 cmdlet 将获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-331">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="0f394-332">例如：`Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="0f394-332">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="0f394-333">**NotContains** 引用值的集合，如果该集合不包含任何与指定值完全匹配的项，则为 true。</span><span class="sxs-lookup"><span data-stu-id="0f394-333">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="0f394-334">如果输入是单个对象，则 PowerShell 会将其转换为一个对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0f394-334">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0f394-335">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-335">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-336">-NotIn</span><span class="sxs-lookup"><span data-stu-id="0f394-336">-NotIn</span></span>

<span data-ttu-id="0f394-337">指示此 cmdlet 获取对象（如果属性值不与任何指定值完全匹配）。</span><span class="sxs-lookup"><span data-stu-id="0f394-337">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="0f394-338">例如：`Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="0f394-338">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="0f394-339">如果 **value** 的值是单个对象，则 PowerShell 会将其转换为一个对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0f394-339">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0f394-340">如果对象的属性值是一个数组，则 PowerShell 将使用引用相等性来确定匹配项。</span><span class="sxs-lookup"><span data-stu-id="0f394-340">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="0f394-341">`Where-Object` 仅当 **属性** 的值和 **值** 的任何值都不是对象的相同实例时才返回对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-341">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="0f394-342">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-342">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-343">-NotLike</span><span class="sxs-lookup"><span data-stu-id="0f394-343">-NotLike</span></span>

<span data-ttu-id="0f394-344">指示如果属性值与包含通配符的值不匹配，则此 cmdlet 将获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-344">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="0f394-345">例如：`Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="0f394-345">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="0f394-346">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-347">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="0f394-347">-NotMatch</span></span>

<span data-ttu-id="0f394-348">指示此 cmdlet 在属性值与指定的正则表达式不匹配时获取对象。</span><span class="sxs-lookup"><span data-stu-id="0f394-348">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="0f394-349">当输入是标量时，匹配的值将保存在 `$Matches` 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="0f394-349">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0f394-350">例如：`Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="0f394-350">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="0f394-351">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-351">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-352">-Property</span><span class="sxs-lookup"><span data-stu-id="0f394-352">-Property</span></span>

<span data-ttu-id="0f394-353">指定对象属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0f394-353">Specifies the name of an object property.</span></span> <span data-ttu-id="0f394-354">参数名称、 **属性** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="0f394-354">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="0f394-355">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-355">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, CaseSensitiveNotLikeSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f394-356">-Value</span><span class="sxs-lookup"><span data-stu-id="0f394-356">-Value</span></span>

<span data-ttu-id="0f394-357">指定属性值。</span><span class="sxs-lookup"><span data-stu-id="0f394-357">Specifies a property value.</span></span> <span data-ttu-id="0f394-358">参数名称， **值** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="0f394-358">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="0f394-359">与以下比较参数一起使用时，此参数可接受通配符：</span><span class="sxs-lookup"><span data-stu-id="0f394-359">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="0f394-360">**CLike**</span><span class="sxs-lookup"><span data-stu-id="0f394-360">**CLike**</span></span>
- <span data-ttu-id="0f394-361">**CNotLike**</span><span class="sxs-lookup"><span data-stu-id="0f394-361">**CNotLike**</span></span>
- <span data-ttu-id="0f394-362">**外观**</span><span class="sxs-lookup"><span data-stu-id="0f394-362">**Like**</span></span>
- <span data-ttu-id="0f394-363">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="0f394-363">**NotLike**</span></span>

<span data-ttu-id="0f394-364">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f394-364">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Object
Parameter Sets: EqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0f394-365">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f394-365">CommonParameters</span></span>

<span data-ttu-id="0f394-366">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0f394-366">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f394-367">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0f394-367">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f394-368">输入</span><span class="sxs-lookup"><span data-stu-id="0f394-368">INPUTS</span></span>

### <span data-ttu-id="0f394-369">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0f394-369">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0f394-370">可以通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f394-370">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="0f394-371">输出</span><span class="sxs-lookup"><span data-stu-id="0f394-371">OUTPUTS</span></span>

### <span data-ttu-id="0f394-372">Object</span><span class="sxs-lookup"><span data-stu-id="0f394-372">Object</span></span>

<span data-ttu-id="0f394-373">此 cmdlet 将返回输入对象集中的选定项。</span><span class="sxs-lookup"><span data-stu-id="0f394-373">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="0f394-374">注释</span><span class="sxs-lookup"><span data-stu-id="0f394-374">NOTES</span></span>

<span data-ttu-id="0f394-375">从 Windows PowerShell 4.0 开始， `Where` `ForEach` 添加了方法以与集合一起使用。</span><span class="sxs-lookup"><span data-stu-id="0f394-375">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="0f394-376">可在此处阅读有关这些新方法的详细信息 [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="0f394-376">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="0f394-377">相关链接</span><span class="sxs-lookup"><span data-stu-id="0f394-377">RELATED LINKS</span></span>

[<span data-ttu-id="0f394-378">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-378">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="0f394-379">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-379">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="0f394-380">Group-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-380">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="0f394-381">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-381">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="0f394-382">New-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-382">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="0f394-383">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-383">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="0f394-384">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-384">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="0f394-385">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="0f394-385">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
