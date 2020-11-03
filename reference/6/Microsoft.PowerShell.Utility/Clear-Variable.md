---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: 5eed9ef3f7aa2f2c8028c9b699487018e8dea153
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198641"
---
# <span data-ttu-id="ab31b-103">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="ab31b-103">Clear-Variable</span></span>

## <span data-ttu-id="ab31b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ab31b-104">SYNOPSIS</span></span>
<span data-ttu-id="ab31b-105">删除变量的值。</span><span class="sxs-lookup"><span data-stu-id="ab31b-105">Deletes the value of a variable.</span></span>

## <span data-ttu-id="ab31b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab31b-106">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ab31b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab31b-107">DESCRIPTION</span></span>

<span data-ttu-id="ab31b-108">**Clear variable** cmdlet 删除存储在变量中的数据，但不删除该变量。</span><span class="sxs-lookup"><span data-stu-id="ab31b-108">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="ab31b-109">因此，该变量的值为 NULL（空）。</span><span class="sxs-lookup"><span data-stu-id="ab31b-109">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="ab31b-110">如果该变量具有指定的数据或对象类型，则此 cmdlet 将保留存储在变量中的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ab31b-110">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="ab31b-111">示例</span><span class="sxs-lookup"><span data-stu-id="ab31b-111">EXAMPLES</span></span>

### <span data-ttu-id="ab31b-112">示例1：删除以搜索字符串开头的全局变量的值</span><span class="sxs-lookup"><span data-stu-id="ab31b-112">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="ab31b-113">此命令删除名称以 "my" 开头的全局变量的值。</span><span class="sxs-lookup"><span data-stu-id="ab31b-113">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="ab31b-114">示例2：清除子范围中的变量，而不是父作用域中的变量</span><span class="sxs-lookup"><span data-stu-id="ab31b-114">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="ab31b-115">这些命令演示了清除子作用域中的变量并不会清除父作用域中的值。</span><span class="sxs-lookup"><span data-stu-id="ab31b-115">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="ab31b-116">第一个命令将变量的值 $A 设置为3。</span><span class="sxs-lookup"><span data-stu-id="ab31b-116">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="ab31b-117">第二个命令使用调用运算符 ( # A0) 在新的作用域中运行 **明文** 。</span><span class="sxs-lookup"><span data-stu-id="ab31b-117">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="ab31b-118">在子作用域中清除该变量（尽管它不存在），但不会在本地作用域中清除它。</span><span class="sxs-lookup"><span data-stu-id="ab31b-118">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="ab31b-119">第三个命令（获取 $A 的值）显示值3不受影响。</span><span class="sxs-lookup"><span data-stu-id="ab31b-119">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="ab31b-120">示例3：删除指定变量的值</span><span class="sxs-lookup"><span data-stu-id="ab31b-120">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="ab31b-121">此命令删除名为进程的变量的值。</span><span class="sxs-lookup"><span data-stu-id="ab31b-121">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="ab31b-122">Cmdlet 完成操作后，名为 "进程" 的变量仍存在，但值为 null。</span><span class="sxs-lookup"><span data-stu-id="ab31b-122">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="ab31b-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab31b-123">PARAMETERS</span></span>

### <span data-ttu-id="ab31b-124">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ab31b-124">-Exclude</span></span>

<span data-ttu-id="ab31b-125">指定此 cmdlet 在操作中省略的项的数组。</span><span class="sxs-lookup"><span data-stu-id="ab31b-125">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="ab31b-126">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ab31b-126">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="ab31b-127">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="ab31b-127">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="ab31b-128">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ab31b-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ab31b-129">-Force</span><span class="sxs-lookup"><span data-stu-id="ab31b-129">-Force</span></span>

<span data-ttu-id="ab31b-130">允许 cmdlet 清除变量，即使该变量是只读的。</span><span class="sxs-lookup"><span data-stu-id="ab31b-130">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="ab31b-131">即使使用 Force 参数，该 cmdlet 也无法清除常量。</span><span class="sxs-lookup"><span data-stu-id="ab31b-131">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="ab31b-132">-Include</span><span class="sxs-lookup"><span data-stu-id="ab31b-132">-Include</span></span>

<span data-ttu-id="ab31b-133">指定此 cmdlet 将在操作中包含的项数组。</span><span class="sxs-lookup"><span data-stu-id="ab31b-133">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="ab31b-134">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ab31b-134">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="ab31b-135">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="ab31b-135">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="ab31b-136">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ab31b-136">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ab31b-137">-Name</span><span class="sxs-lookup"><span data-stu-id="ab31b-137">-Name</span></span>

<span data-ttu-id="ab31b-138">指定要清除的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ab31b-138">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="ab31b-139">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ab31b-139">Wildcards are permitted.</span></span>
<span data-ttu-id="ab31b-140">此参数为必需参数，但参数名（“名称”）为可选项。</span><span class="sxs-lookup"><span data-stu-id="ab31b-140">This parameter is required, but the parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="ab31b-141">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ab31b-141">-PassThru</span></span>

<span data-ttu-id="ab31b-142">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="ab31b-142">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="ab31b-143">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="ab31b-143">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ab31b-144">-Scope</span><span class="sxs-lookup"><span data-stu-id="ab31b-144">-Scope</span></span>

<span data-ttu-id="ab31b-145">指定此别名的有效作用域。</span><span class="sxs-lookup"><span data-stu-id="ab31b-145">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="ab31b-146">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ab31b-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ab31b-147">全球</span><span class="sxs-lookup"><span data-stu-id="ab31b-147">Global</span></span>
- <span data-ttu-id="ab31b-148">Local</span><span class="sxs-lookup"><span data-stu-id="ab31b-148">Local</span></span>
- <span data-ttu-id="ab31b-149">脚本</span><span class="sxs-lookup"><span data-stu-id="ab31b-149">Script</span></span>

<span data-ttu-id="ab31b-150">你还可以使用相对于当前作用域的数字 (0 到作用域数，其中0是当前作用域，1是其父) 。</span><span class="sxs-lookup"><span data-stu-id="ab31b-150">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="ab31b-151">默认值为 Local。</span><span class="sxs-lookup"><span data-stu-id="ab31b-151">Local is the default.</span></span>
<span data-ttu-id="ab31b-152">有关详细信息，请参阅 about_Scopes。</span><span class="sxs-lookup"><span data-stu-id="ab31b-152">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="ab31b-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ab31b-153">-Confirm</span></span>

<span data-ttu-id="ab31b-154">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="ab31b-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ab31b-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ab31b-155">-WhatIf</span></span>

<span data-ttu-id="ab31b-156">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ab31b-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ab31b-157">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ab31b-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ab31b-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab31b-158">CommonParameters</span></span>

<span data-ttu-id="ab31b-159">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ab31b-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab31b-160">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ab31b-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab31b-161">输入</span><span class="sxs-lookup"><span data-stu-id="ab31b-161">INPUTS</span></span>

### <span data-ttu-id="ab31b-162">无</span><span class="sxs-lookup"><span data-stu-id="ab31b-162">None</span></span>

<span data-ttu-id="ab31b-163">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ab31b-163">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ab31b-164">输出</span><span class="sxs-lookup"><span data-stu-id="ab31b-164">OUTPUTS</span></span>

### <span data-ttu-id="ab31b-165">无或 System.Management.Automation.PSVariable</span><span class="sxs-lookup"><span data-stu-id="ab31b-165">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="ab31b-166">当使用 *PassThru* 参数时，此 cmdlet 将生成表示已清除变量的 **system.management.automation.psvariable** 对象。</span><span class="sxs-lookup"><span data-stu-id="ab31b-166">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="ab31b-167">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ab31b-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ab31b-168">注释</span><span class="sxs-lookup"><span data-stu-id="ab31b-168">NOTES</span></span>

* <span data-ttu-id="ab31b-169">若要删除变量及其值，请使用删除 Remove-Variable 或 Remove-Item。</span><span class="sxs-lookup"><span data-stu-id="ab31b-169">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="ab31b-170">此 cmdlet 不会删除设置为常量或系统所拥有的变量的值，即使使用 *Force* 参数也是如此。</span><span class="sxs-lookup"><span data-stu-id="ab31b-170">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="ab31b-171">如果你清除的变量不存在，则此 cmdlet 无效。</span><span class="sxs-lookup"><span data-stu-id="ab31b-171">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="ab31b-172">它不会创建具有 null 值的变量。</span><span class="sxs-lookup"><span data-stu-id="ab31b-172">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="ab31b-173">还可以通过其内置别名 clv 来引用 **Clear 变量** 。</span><span class="sxs-lookup"><span data-stu-id="ab31b-173">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="ab31b-174">有关详细信息，请参阅 about_Aliases。</span><span class="sxs-lookup"><span data-stu-id="ab31b-174">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="ab31b-175">相关链接</span><span class="sxs-lookup"><span data-stu-id="ab31b-175">RELATED LINKS</span></span>

[<span data-ttu-id="ab31b-176">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="ab31b-176">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="ab31b-177">New-Variable</span><span class="sxs-lookup"><span data-stu-id="ab31b-177">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="ab31b-178">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="ab31b-178">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="ab31b-179">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="ab31b-179">Set-Variable</span></span>](Set-Variable.md)
