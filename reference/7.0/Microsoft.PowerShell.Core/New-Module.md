---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: a0d0e31e9010c5ee119b4fbe5f6a877ebc4dc1d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197246"
---
# <span data-ttu-id="c6445-103">New-Module</span><span class="sxs-lookup"><span data-stu-id="c6445-103">New-Module</span></span>

## <span data-ttu-id="c6445-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c6445-104">SYNOPSIS</span></span>
<span data-ttu-id="c6445-105">创建一个仅存在于内存中的新动态模块。</span><span class="sxs-lookup"><span data-stu-id="c6445-105">Creates a new dynamic module that exists only in memory.</span></span>

## <span data-ttu-id="c6445-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6445-106">SYNTAX</span></span>

### <span data-ttu-id="c6445-107">ScriptBlock（默认值）</span><span class="sxs-lookup"><span data-stu-id="c6445-107">ScriptBlock (Default)</span></span>

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="c6445-108">名称</span><span class="sxs-lookup"><span data-stu-id="c6445-108">Name</span></span>

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="c6445-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c6445-109">DESCRIPTION</span></span>

<span data-ttu-id="c6445-110">`New-Module`Cmdlet 从脚本块创建动态模块。</span><span class="sxs-lookup"><span data-stu-id="c6445-110">The `New-Module` cmdlet creates a dynamic module from a script block.</span></span> <span data-ttu-id="c6445-111">动态模块的成员（如函数和变量）在会话中立即可用并保持可用状态，直到关闭此会话。</span><span class="sxs-lookup"><span data-stu-id="c6445-111">The members of the dynamic module, such as functions and variables, are immediately available in the session and remain available until you close the session.</span></span>

<span data-ttu-id="c6445-112">类似于静态模块，默认情况下，将导出动态模块中的 cmdlet 和函数，而不导出变量和别名。</span><span class="sxs-lookup"><span data-stu-id="c6445-112">Like static modules, by default, the cmdlets and functions in a dynamic module are exported and the variables and aliases are not.</span></span> <span data-ttu-id="c6445-113">但是，可以使用 Export-ModuleMember cmdlet 和的参数 `New-Module` 来覆盖默认值。</span><span class="sxs-lookup"><span data-stu-id="c6445-113">However, you can use the Export-ModuleMember cmdlet and the parameters of `New-Module` to override the defaults.</span></span>

<span data-ttu-id="c6445-114">你还可以使用的 **AsCustomObject** 参数 `New-Module` ，以自定义对象的形式返回动态模块。</span><span class="sxs-lookup"><span data-stu-id="c6445-114">You can also use the **AsCustomObject** parameter of `New-Module` to return the dynamic module as a custom object.</span></span> <span data-ttu-id="c6445-115">将模块的成员（例如函数）实现为自定义对象的脚本方法，而不是将其导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="c6445-115">The members of the modules, such as functions, are implemented as script methods of the custom object instead of being imported into the session.</span></span>

<span data-ttu-id="c6445-116">动态模块只存在于内存中，而不存在于磁盘上。</span><span class="sxs-lookup"><span data-stu-id="c6445-116">Dynamic modules exist only in memory, not on disk.</span></span> <span data-ttu-id="c6445-117">类似于所有模块，动态模块的成员在专用模块作用域中运行，此作用域是全局作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="c6445-117">Like all modules, the members of dynamic modules run in a private module scope that is a child of the global scope.</span></span> <span data-ttu-id="c6445-118">Get-Module 无法获取动态模块，但 Get-Command 可以获取导出的成员。</span><span class="sxs-lookup"><span data-stu-id="c6445-118">Get-Module cannot get a dynamic module, but Get-Command can get the exported members.</span></span>

<span data-ttu-id="c6445-119">若要使动态模块可供使用 `Get-Module` ，请通过管道将 `New-Module` 命令传递给 import-module，或将返回的模块对象传递给 `New-Module` `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-119">To make a dynamic module available to `Get-Module`, pipe a `New-Module` command to Import-Module, or pipe the module object that `New-Module` returns to `Import-Module`.</span></span> <span data-ttu-id="c6445-120">此操作将动态模块添加到 `Get-Module` 列表中，但它不会将模块保存到磁盘或使其保持不变。</span><span class="sxs-lookup"><span data-stu-id="c6445-120">This action adds the dynamic module to the `Get-Module` list, but it does not save the module to disk or make it persistent.</span></span>

## <span data-ttu-id="c6445-121">示例</span><span class="sxs-lookup"><span data-stu-id="c6445-121">EXAMPLES</span></span>

### <span data-ttu-id="c6445-122">示例1：创建动态模块</span><span class="sxs-lookup"><span data-stu-id="c6445-122">Example 1: Create a dynamic module</span></span>

<span data-ttu-id="c6445-123">此示例使用名为的函数创建新的动态模块 `Hello` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-123">This example creates a new dynamic module with a function called `Hello`.</span></span> <span data-ttu-id="c6445-124">此命令返回表示新的动态模块的模块对象。</span><span class="sxs-lookup"><span data-stu-id="c6445-124">The command returns a module object that represents the new dynamic module.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### <span data-ttu-id="c6445-125">示例2：使用动态模块、Get-Module 和 Get-Command</span><span class="sxs-lookup"><span data-stu-id="c6445-125">Example 2: Working with dynamic modules and Get-Module and Get-Command</span></span>

<span data-ttu-id="c6445-126">此示例演示 cmdlet 不返回动态模块 `Get-Module` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-126">This example demonstrates that dynamic modules are not returned by the `Get-Module` cmdlet.</span></span> <span data-ttu-id="c6445-127">Cmdlet 将返回它们导出的成员 `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-127">The members that they export are returned by the `Get-Command` cmdlet.</span></span>

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### <span data-ttu-id="c6445-128">示例3：将变量导出到当前会话中</span><span class="sxs-lookup"><span data-stu-id="c6445-128">Example 3: Export a variable into the current session</span></span>

<span data-ttu-id="c6445-129">此示例使用 `Export-ModuleMember` cmdlet 将变量导出到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="c6445-129">This example uses the `Export-ModuleMember` cmdlet to export a variable into the current session.</span></span>
<span data-ttu-id="c6445-130">如果没有 `Export-ModuleMember` 命令，则只会导出函数。</span><span class="sxs-lookup"><span data-stu-id="c6445-130">Without the `Export-ModuleMember` command, only the function is exported.</span></span>

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

<span data-ttu-id="c6445-131">输出显示已将变量和函数导出到会话中。</span><span class="sxs-lookup"><span data-stu-id="c6445-131">The output shows that both the variable and the function were exported into the session.</span></span>

### <span data-ttu-id="c6445-132">示例4：使动态模块可用于 Get-Module</span><span class="sxs-lookup"><span data-stu-id="c6445-132">Example 4: Make a dynamic module available to Get-Module</span></span>

<span data-ttu-id="c6445-133">此示例演示如何通过管道将动态模块传递给，使动态模块可供使用 `Get-Module` `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-133">This example demonstrates that you can make a dynamic module available to `Get-Module` by piping the dynamic module to `Import-Module`.</span></span>

<span data-ttu-id="c6445-134">`New-Module` 创建通过管道传递给 cmdlet 的模块对象 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-134">`New-Module` creates a module object that is piped to the `Import-Module` cmdlet.</span></span> <span data-ttu-id="c6445-135">的 **name** 参数将为 `New-Module` 模块分配一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="c6445-135">The **Name** parameter of `New-Module` assigns a friendly name to the module.</span></span> <span data-ttu-id="c6445-136">由于 `Import-Module` 默认情况下不返回任何对象，因此没有来自此命令的输出。</span><span class="sxs-lookup"><span data-stu-id="c6445-136">Because `Import-Module` does not return any objects by default, there is no output from this command.</span></span> <span data-ttu-id="c6445-137">`Get-Module`**GreetingModule** 已导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="c6445-137">`Get-Module` that the **GreetingModule** has been imported into the current session.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

<span data-ttu-id="c6445-138">`Get-Command`Cmdlet 显示 `Hello` 动态模块导出的函数。</span><span class="sxs-lookup"><span data-stu-id="c6445-138">The `Get-Command` cmdlet shows the `Hello` function that the dynamic module exports.</span></span>

### <span data-ttu-id="c6445-139">示例5：生成具有导出函数的自定义对象</span><span class="sxs-lookup"><span data-stu-id="c6445-139">Example 5: Generate a custom object that has exported functions</span></span>

<span data-ttu-id="c6445-140">此示例演示如何使用的 **AsCustomObject** 参数 `New-Module` 生成一个自定义对象，该对象具有表示导出的函数的脚本方法。</span><span class="sxs-lookup"><span data-stu-id="c6445-140">This example shows how to use the **AsCustomObject** parameter of `New-Module` to generate a custom object that has script methods that represent the exported functions.</span></span>

<span data-ttu-id="c6445-141">`New-Module`Cmdlet 将创建包含两个函数和的动态 `Hello` 模块 `Goodbye` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-141">The `New-Module` cmdlet creates a dynamic module with two functions, `Hello` and `Goodbye`.</span></span> <span data-ttu-id="c6445-142">**AsCustomObject** 参数创建自定义对象，而不是默认生成的 **PSModuleInfo** 对象 `New-Module` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-142">The **AsCustomObject** parameter creates a custom object instead of the **PSModuleInfo** object that `New-Module` generates by default.</span></span> <span data-ttu-id="c6445-143">此自定义对象保存在 `$m` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c6445-143">This custom object is saved in the `$m` variable.</span></span>
<span data-ttu-id="c6445-144">`$m`变量似乎没有分配值。</span><span class="sxs-lookup"><span data-stu-id="c6445-144">The `$m` variable appears to have no assigned value.</span></span>

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

<span data-ttu-id="c6445-145">管道传递 `$m` 到 `Get-Member` cmdlet 显示自定义对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="c6445-145">Piping `$m` to the `Get-Member` cmdlet displays the properties and methods of the custom object.</span></span> <span data-ttu-id="c6445-146">输出显示对象具有表示和函数的脚本方法 `Hello` `Goodbye` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-146">The output shows that the object has script methods that represent the `Hello` and `Goodbye` functions.</span></span>
<span data-ttu-id="c6445-147">最后，我们调用这些脚本方法并显示结果。</span><span class="sxs-lookup"><span data-stu-id="c6445-147">Finally, we call these script methods and display the results.</span></span>

### <span data-ttu-id="c6445-148">示例6：获取脚本块的结果</span><span class="sxs-lookup"><span data-stu-id="c6445-148">Example 6: Get the results of the script block</span></span>

<span data-ttu-id="c6445-149">此示例使用 **ReturnResult** 参数来请求运行脚本块的结果，而不是请求模块对象。</span><span class="sxs-lookup"><span data-stu-id="c6445-149">This example uses the **ReturnResult** parameter to request the results of running the script block instead of requesting a module object.</span></span> <span data-ttu-id="c6445-150">新模块中的脚本块定义 `SayHello` 函数，然后调用函数。</span><span class="sxs-lookup"><span data-stu-id="c6445-150">The script block in the new module defines the `SayHello` function and then calls the function.</span></span>

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## <span data-ttu-id="c6445-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6445-151">PARAMETERS</span></span>

### <span data-ttu-id="c6445-152">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="c6445-152">-ArgumentList</span></span>

<span data-ttu-id="c6445-153">指定参数数组，这些参数是传递到脚本块的参数值。</span><span class="sxs-lookup"><span data-stu-id="c6445-153">Specifies an array of arguments which are parameter values that are passed to the script block.</span></span> <span data-ttu-id="c6445-154">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="c6445-154">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c6445-155">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="c6445-155">-AsCustomObject</span></span>

<span data-ttu-id="c6445-156">指示此 cmdlet 返回表示动态模块的自定义对象。</span><span class="sxs-lookup"><span data-stu-id="c6445-156">Indicates that this cmdlet returns a custom object that represents the dynamic module.</span></span> <span data-ttu-id="c6445-157">将模块成员实现为自定义对象的脚本方法，但是不将它们导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="c6445-157">The module members are implemented as script methods of the custom object, but they are not imported into the session.</span></span> <span data-ttu-id="c6445-158">可以在变量中保存自定义对象，并使用点表示法来调用成员。</span><span class="sxs-lookup"><span data-stu-id="c6445-158">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

<span data-ttu-id="c6445-159">如果模块有多个具有相同名称的成员，如函数和名为的变量，则只能从自定义对象访问一个具有每个名称的成员。</span><span class="sxs-lookup"><span data-stu-id="c6445-159">If the module has multiple members with the same name, such as a function and a variable that are both named A, only one member with each name can be accessed from the custom object.</span></span>

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

### <span data-ttu-id="c6445-160">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c6445-160">-Cmdlet</span></span>

<span data-ttu-id="c6445-161">指定此 cmdlet 从模块导出到当前会话中的 cmdlet 的数组。</span><span class="sxs-lookup"><span data-stu-id="c6445-161">Specifies an array of cmdlets that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="c6445-162">输入以逗号分隔的 cmdlet 列表。</span><span class="sxs-lookup"><span data-stu-id="c6445-162">Enter a comma-separated list of cmdlets.</span></span> <span data-ttu-id="c6445-163">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c6445-163">Wildcard characters are permitted.</span></span> <span data-ttu-id="c6445-164">默认情况下，导出模块中的所有 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c6445-164">By default, all cmdlets in the module are exported.</span></span>

<span data-ttu-id="c6445-165">你无法在脚本块中定义 cmdlet，但如果从二进制模块导入 cmdlet，则动态模块可以包含 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c6445-165">You cannot define cmdlets in a script block, but a dynamic module can include cmdlets if it imports the cmdlets from a binary module.</span></span>

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

### <span data-ttu-id="c6445-166">-Function</span><span class="sxs-lookup"><span data-stu-id="c6445-166">-Function</span></span>

<span data-ttu-id="c6445-167">指定此 cmdlet 从模块导出到当前会话的函数数组。</span><span class="sxs-lookup"><span data-stu-id="c6445-167">Specifies an array of functions that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="c6445-168">输入以逗号分隔的函数列表。</span><span class="sxs-lookup"><span data-stu-id="c6445-168">Enter a comma-separated list of functions.</span></span> <span data-ttu-id="c6445-169">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c6445-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="c6445-170">默认情况下，导出模块中定义的所有函数。</span><span class="sxs-lookup"><span data-stu-id="c6445-170">By default, all functions defined in a module are exported.</span></span>

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

### <span data-ttu-id="c6445-171">-Name</span><span class="sxs-lookup"><span data-stu-id="c6445-171">-Name</span></span>

<span data-ttu-id="c6445-172">指定新模块的名称。</span><span class="sxs-lookup"><span data-stu-id="c6445-172">Specifies a name for the new module.</span></span> <span data-ttu-id="c6445-173">还可以通过管道将模块的名称传递给 New-Module。</span><span class="sxs-lookup"><span data-stu-id="c6445-173">You can also pipe a module name to New-Module.</span></span>

<span data-ttu-id="c6445-174">默认值是自动生成的名称，该名称以开头， `__DynamicModule_` 后跟一个 GUID，它指定动态模块的路径。</span><span class="sxs-lookup"><span data-stu-id="c6445-174">The default value is an autogenerated name that starts with `__DynamicModule_` and is followed by a GUID that specifies the path of the dynamic module.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c6445-175">-ReturnResult</span><span class="sxs-lookup"><span data-stu-id="c6445-175">-ReturnResult</span></span>

<span data-ttu-id="c6445-176">指示此 cmdlet 运行脚本块并返回脚本块结果，而不是返回模块对象。</span><span class="sxs-lookup"><span data-stu-id="c6445-176">Indicates that this cmdlet runs the script block and returns the script block results instead of returning a module object.</span></span>

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

### <span data-ttu-id="c6445-177">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="c6445-177">-ScriptBlock</span></span>

<span data-ttu-id="c6445-178">指定动态模块的内容。</span><span class="sxs-lookup"><span data-stu-id="c6445-178">Specifies the contents of the dynamic module.</span></span> <span data-ttu-id="c6445-179">将内容括在大括号中 (`{}`) 创建脚本块。</span><span class="sxs-lookup"><span data-stu-id="c6445-179">Enclose the contents in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="c6445-180">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="c6445-180">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c6445-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c6445-181">CommonParameters</span></span>

<span data-ttu-id="c6445-182">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c6445-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6445-183">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c6445-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6445-184">输入</span><span class="sxs-lookup"><span data-stu-id="c6445-184">INPUTS</span></span>

### <span data-ttu-id="c6445-185">System.String</span><span class="sxs-lookup"><span data-stu-id="c6445-185">System.String</span></span>

<span data-ttu-id="c6445-186">可以通过管道将模块名称传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c6445-186">You can pipe a module name to this cmdlet.</span></span>

## <span data-ttu-id="c6445-187">输出</span><span class="sxs-lookup"><span data-stu-id="c6445-187">OUTPUTS</span></span>

### <span data-ttu-id="c6445-188">System.Management.Automation.PSModuleInfo、System.Management.Automation.PSCustomObject 或无</span><span class="sxs-lookup"><span data-stu-id="c6445-188">System.Management.Automation.PSModuleInfo, System.Management.Automation.PSCustomObject, or None</span></span>

<span data-ttu-id="c6445-189">默认情况下，此 cmdlet 将生成 **PSModuleInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="c6445-189">This cmdlet generates a **PSModuleInfo** object, by default.</span></span> <span data-ttu-id="c6445-190">如果使用 **AsCustomObject** 参数，它将生成 **PSCustomObject** 对象。</span><span class="sxs-lookup"><span data-stu-id="c6445-190">If you use the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span> <span data-ttu-id="c6445-191">如果使用 **ReturnResult** 参数，则它会返回对动态模块中的脚本块求值所得的结果。</span><span class="sxs-lookup"><span data-stu-id="c6445-191">If you use the **ReturnResult** parameter, it returns the result of evaluating the script block in the dynamic module.</span></span>

## <span data-ttu-id="c6445-192">注释</span><span class="sxs-lookup"><span data-stu-id="c6445-192">NOTES</span></span>

<span data-ttu-id="c6445-193">还可以 `New-Module` 通过其别名来引用 `nmo` 。</span><span class="sxs-lookup"><span data-stu-id="c6445-193">You can also refer to `New-Module` by its alias, `nmo`.</span></span> <span data-ttu-id="c6445-194">有关详细信息，请参阅 [about_Aliases](About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="c6445-194">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="c6445-195">相关链接</span><span class="sxs-lookup"><span data-stu-id="c6445-195">RELATED LINKS</span></span>

[<span data-ttu-id="c6445-196">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="c6445-196">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="c6445-197">Get-Module</span><span class="sxs-lookup"><span data-stu-id="c6445-197">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="c6445-198">Import-Module</span><span class="sxs-lookup"><span data-stu-id="c6445-198">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="c6445-199">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="c6445-199">Remove-Module</span></span>](Remove-Module.md)
