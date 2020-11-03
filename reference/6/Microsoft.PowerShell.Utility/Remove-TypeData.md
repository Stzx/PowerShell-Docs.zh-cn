---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 23a5241aa2f4b18fc02c3ea1c1a5bb8fb467b430
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198502"
---
# <span data-ttu-id="14666-103">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="14666-103">Remove-TypeData</span></span>

## <span data-ttu-id="14666-104">摘要</span><span class="sxs-lookup"><span data-stu-id="14666-104">Synopsis</span></span>
<span data-ttu-id="14666-105">从当前会话中删除扩展的类型。</span><span class="sxs-lookup"><span data-stu-id="14666-105">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="14666-106">语法</span><span class="sxs-lookup"><span data-stu-id="14666-106">Syntax</span></span>

### <span data-ttu-id="14666-107">RemoveTypeDataSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="14666-107">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="14666-108">RemoveTypeSet</span><span class="sxs-lookup"><span data-stu-id="14666-108">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="14666-109">RemoveFileSet</span><span class="sxs-lookup"><span data-stu-id="14666-109">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="14666-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14666-110">DESCRIPTION</span></span>

<span data-ttu-id="14666-111">`Remove-TypeData`Cmdlet 从当前会话中删除扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-111">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="14666-112">此 cmdlet 只影响当前会话和当前会话中创建的会话。</span><span class="sxs-lookup"><span data-stu-id="14666-112">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="14666-113">可以通过在命令和文件中定义来向 PowerShell 中的对象添加属性和方法 `Update-TypeData` `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="14666-113">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="14666-114">`Remove-TypeData` 从当前会话中删除这些扩展属性和方法。</span><span class="sxs-lookup"><span data-stu-id="14666-114">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="14666-115">`Remove-TypeData` 不会删除 `Types.ps1xml` 文件或从文件中删除任何扩展类型定义 `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="14666-115">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="14666-116">有关文件的详细信息 `Types.ps1xml` ，请参阅 [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md)。</span><span class="sxs-lookup"><span data-stu-id="14666-116">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="14666-117">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="14666-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="14666-118">示例</span><span class="sxs-lookup"><span data-stu-id="14666-118">Examples</span></span>

### <span data-ttu-id="14666-119">示例 1：删除指定类型的类型数据</span><span class="sxs-lookup"><span data-stu-id="14666-119">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="14666-120">此示例将从会话中删除 **system.object** 类型的所有类型数据，包括通过 `Types.ps1xml` 使用 cmdlet 添加到会话中的文件和动态类型数据添加的类型数据 `Update-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="14666-120">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="14666-121">示例 2：从会话中删除扩展数据类型</span><span class="sxs-lookup"><span data-stu-id="14666-121">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="14666-122">此示例演示了从会话中删除扩展类型数据的效果。</span><span class="sxs-lookup"><span data-stu-id="14666-122">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="14666-123">第一 `Get-TypeData` 种是为 system.string 类型获取 **System.DateTime** 扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-123">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="14666-124">输出显示已将 **datetime** 属性添加到 PowerShell 中的所有 **system.web** 对象。</span><span class="sxs-lookup"><span data-stu-id="14666-124">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="14666-125">`Get-Date`Cmdlet 将返回 **system.object** 对象。</span><span class="sxs-lookup"><span data-stu-id="14666-125">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="14666-126">该命令使用点表示法来获取返回的 **system.object** 对象的 **datetime** 属性的值 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="14666-126">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

<span data-ttu-id="14666-127">下一个 `Get-TypeData` cmdlet，用于获取 **system.web** 类型的所有扩展类型数据，并通过管道将其用于 `Remove-TypeData` 删除扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-127">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="14666-128">最后一个 `Get-Date` cmdlet 显示删除 **system.object** 类型的扩展类型数据的效果。</span><span class="sxs-lookup"><span data-stu-id="14666-128">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="14666-129">由于不存在 **system.web** 属性，因此用于获取其值的命令不会返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="14666-129">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="14666-130">示例 3：删除模块的扩展类型</span><span class="sxs-lookup"><span data-stu-id="14666-130">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="14666-131">此示例将删除模块对象的所有扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-131">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="14666-132">将对象通过管道传递给时 `Remove-TypeData` ，将 `Remove-TypeData` 获取该对象类型的名称，并删除该类型的所有对象的所有类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-132">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="14666-133">示例 4：删除指定模块中的扩展类型</span><span class="sxs-lookup"><span data-stu-id="14666-133">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="14666-134">此示例使用 cmdlet 的 **Path** 参数 `Remove-TypeData` 删除 `Types.ps1xml` **PSScheduledJob** 和 **PSWorkflow** 模块添加的文件中定义的扩展类型。</span><span class="sxs-lookup"><span data-stu-id="14666-134">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="14666-135">此命令不会影响使用 cmdlet 添加的动态类型数据 `Update-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="14666-135">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="14666-136">仅当已将模块导入当前会话时，此命令才能够成功执行。</span><span class="sxs-lookup"><span data-stu-id="14666-136">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="14666-137">有关模块的详细信息，请参阅 [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="14666-137">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="14666-138">示例 5：从远程会话中删除扩展类型</span><span class="sxs-lookup"><span data-stu-id="14666-138">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="14666-139">此示例将从远程会话中删除扩展类型。</span><span class="sxs-lookup"><span data-stu-id="14666-139">This example removes extended types from a remote session.</span></span> <span data-ttu-id="14666-140">该命令使用 `Invoke-Command` cmdlet 删除变量的会话中的所有 CIM 类型的扩展类型数据 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="14666-140">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="14666-141">parameters</span><span class="sxs-lookup"><span data-stu-id="14666-141">Parameters</span></span>

### <span data-ttu-id="14666-142">-Path</span><span class="sxs-lookup"><span data-stu-id="14666-142">-Path</span></span>

<span data-ttu-id="14666-143">指定此 cmdlet 将从会话扩展类型数据中删除的文件数组。</span><span class="sxs-lookup"><span data-stu-id="14666-143">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="14666-144">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="14666-144">This parameter is required.</span></span>

<span data-ttu-id="14666-145">输入一个或多个文件的路径和文件名 `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="14666-145">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="14666-146">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="14666-146">Wildcards are not supported.</span></span> <span data-ttu-id="14666-147">如果省略路径，则默认位置为当前目录。</span><span class="sxs-lookup"><span data-stu-id="14666-147">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14666-148">-TypeData</span><span class="sxs-lookup"><span data-stu-id="14666-148">-TypeData</span></span>

<span data-ttu-id="14666-149">指定此 cmdlet 将从会话中删除的类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-149">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="14666-150">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="14666-150">This parameter is required.</span></span> <span data-ttu-id="14666-151">输入包含 **update-typedata** 对象的变量， ( **update-typedata** ) 或获取 **update-typedata** 对象的命令（如命令）。 `Get-TypeData`</span><span class="sxs-lookup"><span data-stu-id="14666-151">Enter a variable that contains **TypeData** objects ( **System.Management.Automation.Runspaces.TypeData** ) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="14666-152">还可以通过管道将 **update-typedata** 对象传递给 `Remove-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="14666-152">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="14666-153">-TypeName</span><span class="sxs-lookup"><span data-stu-id="14666-153">-TypeName</span></span>

<span data-ttu-id="14666-154">指定此 cmdlet 将删除其所有扩展类型数据的类型。</span><span class="sxs-lookup"><span data-stu-id="14666-154">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="14666-155">对于 System 命名空间中的类型，请输入其短名称。</span><span class="sxs-lookup"><span data-stu-id="14666-155">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="14666-156">否则，必须输入完整类型名称。</span><span class="sxs-lookup"><span data-stu-id="14666-156">Otherwise, the full type name is required.</span></span> <span data-ttu-id="14666-157">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="14666-157">Wildcards are not supported.</span></span>

<span data-ttu-id="14666-158">可以通过管道将类型命名为 `Remove-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="14666-158">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="14666-159">将对象通过管道传递给时 `Remove-TypeData` ，将 `Remove-TypeData` 获取对象的类型名称，并移除该对象类型的所有类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-159">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="14666-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="14666-160">-Confirm</span></span>

<span data-ttu-id="14666-161">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="14666-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="14666-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="14666-162">-WhatIf</span></span>

<span data-ttu-id="14666-163">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="14666-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="14666-164">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="14666-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="14666-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14666-165">CommonParameters</span></span>

<span data-ttu-id="14666-166">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="14666-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14666-167">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="14666-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14666-168">输入</span><span class="sxs-lookup"><span data-stu-id="14666-168">Inputs</span></span>

### <span data-ttu-id="14666-169">System.Management.Automation.Runspaces.TypeData</span><span class="sxs-lookup"><span data-stu-id="14666-169">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="14666-170">可以通过管道将 **update-typedata** 对象（例如 cmdlet 返回的对象）传递 `Get-TypeData` 给 `Remove-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="14666-170">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="14666-171">System.String</span><span class="sxs-lookup"><span data-stu-id="14666-171">System.String</span></span>

<span data-ttu-id="14666-172">可以通过管道将类型名称传递给 `Remove-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="14666-172">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="14666-173">将对象通过管道传递给时 `Remove-TypeData` ，将 `Remove-TypeData` 获取对象的类型名称，并移除该对象类型的所有类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-173">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="14666-174">Outputs</span><span class="sxs-lookup"><span data-stu-id="14666-174">Outputs</span></span>

### <span data-ttu-id="14666-175">无</span><span class="sxs-lookup"><span data-stu-id="14666-175">None</span></span>

<span data-ttu-id="14666-176">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="14666-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="14666-177">注释</span><span class="sxs-lookup"><span data-stu-id="14666-177">Notes</span></span>

<span data-ttu-id="14666-178">`Remove-TypeData` 只能删除当前会话中的扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-178">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="14666-179">它无法删除位于计算机上的但未添加到当前会话的扩展类型数据，例如模块中定义的但未导入到当前会话中的扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="14666-179">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="14666-180">相关链接</span><span class="sxs-lookup"><span data-stu-id="14666-180">Related links</span></span>

[<span data-ttu-id="14666-181">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="14666-181">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="14666-182">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="14666-182">Update-TypeData</span></span>](Update-TypeData.md)
