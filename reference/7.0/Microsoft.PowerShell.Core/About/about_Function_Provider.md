---
description: 函数
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Function 提供程序
ms.openlocfilehash: 1feb12709ea458196ce9fa26fcdfaa5cb39010c0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200352"
---
# <a name="function-provider"></a><span data-ttu-id="cec49-104">函数提供程序</span><span class="sxs-lookup"><span data-stu-id="cec49-104">Function provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="cec49-105">提供程序名称</span><span class="sxs-lookup"><span data-stu-id="cec49-105">Provider name</span></span>
<span data-ttu-id="cec49-106">函数</span><span class="sxs-lookup"><span data-stu-id="cec49-106">Function</span></span>

## <a name="drives"></a><span data-ttu-id="cec49-107">驱动器</span><span class="sxs-lookup"><span data-stu-id="cec49-107">Drives</span></span>

`Function:`

## <a name="capabilities"></a><span data-ttu-id="cec49-108">功能</span><span class="sxs-lookup"><span data-stu-id="cec49-108">Capabilities</span></span>

<span data-ttu-id="cec49-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="cec49-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="cec49-110">简短说明</span><span class="sxs-lookup"><span data-stu-id="cec49-110">Short description</span></span>

<span data-ttu-id="cec49-111">提供对在 PowerShell 中定义的函数的访问权限。</span><span class="sxs-lookup"><span data-stu-id="cec49-111">Provides access to the functions defined in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="cec49-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="cec49-112">Detailed description</span></span>

<span data-ttu-id="cec49-113">PowerShell **函数** 提供程序可让你获取、添加、更改、清除和删除 PowerShell 中的函数和筛选器。</span><span class="sxs-lookup"><span data-stu-id="cec49-113">The PowerShell **Function** provider lets you get, add, change, clear, and delete the functions and filters in PowerShell.</span></span>

<span data-ttu-id="cec49-114">函数是用于执行某项操作的命名的代码块。</span><span class="sxs-lookup"><span data-stu-id="cec49-114">A function is a named block of code that performs an action.</span></span> <span data-ttu-id="cec49-115">在键入函数名称后，将运行该函数中的代码。</span><span class="sxs-lookup"><span data-stu-id="cec49-115">When you type the function name, the code in the function runs.</span></span> <span data-ttu-id="cec49-116">筛选器是用于建立操作条件的命名的代码块。</span><span class="sxs-lookup"><span data-stu-id="cec49-116">A filter is a named block of code that establishes conditions for an action.</span></span> <span data-ttu-id="cec49-117">您可以键入筛选器的名称来代替条件，例如在 `Where-Object` 命令中。</span><span class="sxs-lookup"><span data-stu-id="cec49-117">You can type the name of the filter in place of the condition, such as in a `Where-Object` command.</span></span>

<span data-ttu-id="cec49-118">**函数** 驱动器是只包含函数和筛选器对象的平面命名空间。</span><span class="sxs-lookup"><span data-stu-id="cec49-118">The **Function** drive is a flat namespace that contains only the function and filter objects.</span></span> <span data-ttu-id="cec49-119">函数和筛选器都没有子项。</span><span class="sxs-lookup"><span data-stu-id="cec49-119">Neither functions nor filters have child items.</span></span>

<span data-ttu-id="cec49-120">**函数** 提供程序支持以下 cmdlet，这将在本文中介绍。</span><span class="sxs-lookup"><span data-stu-id="cec49-120">The **Function** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="cec49-121">Get-Location</span><span class="sxs-lookup"><span data-stu-id="cec49-121">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="cec49-122">Set-Location</span><span class="sxs-lookup"><span data-stu-id="cec49-122">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="cec49-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="cec49-123">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="cec49-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="cec49-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="cec49-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="cec49-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="cec49-126">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="cec49-126">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="cec49-127">此提供程序公开的类型</span><span class="sxs-lookup"><span data-stu-id="cec49-127">Types exposed by this provider</span></span>

<span data-ttu-id="cec49-128">每个函数都是 [FunctionInfo](/dotnet/api/system.management.automation.functioninfo) 类的实例。</span><span class="sxs-lookup"><span data-stu-id="cec49-128">Each function is an instance of the [System.Management.Automation.FunctionInfo](/dotnet/api/system.management.automation.functioninfo) class.</span></span> <span data-ttu-id="cec49-129">每个筛选器都是 [都是 system.management.automation.filterinfo](/dotnet/api/system.management.automation.filterinfo) 类的实例。</span><span class="sxs-lookup"><span data-stu-id="cec49-129">Each filter is an instance of the [System.Management.Automation.FilterInfo](/dotnet/api/system.management.automation.filterinfo) class.</span></span>

## <a name="navigating-the-function-drive"></a><span data-ttu-id="cec49-130">导航函数驱动器</span><span class="sxs-lookup"><span data-stu-id="cec49-130">Navigating the Function drive</span></span>

<span data-ttu-id="cec49-131">**函数** 提供程序在驱动器中公开其数据存储区 `Function:` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-131">The **Function** provider exposes its data store in the `Function:` drive.</span></span> <span data-ttu-id="cec49-132">若要使用函数，你可以将你的位置更改为 `Function:` 驱动器 (`Set-Location Function:`) 。</span><span class="sxs-lookup"><span data-stu-id="cec49-132">To work with functions, you can change your location to the `Function:` drive (`Set-Location Function:`).</span></span> <span data-ttu-id="cec49-133">或者，你可以从另一个 PowerShell 驱动器进行工作。</span><span class="sxs-lookup"><span data-stu-id="cec49-133">Or, you can work from another PowerShell drive.</span></span> <span data-ttu-id="cec49-134">若要从其他位置引用函数，请在路径中使用驱动器名称 (`Function:`) 。</span><span class="sxs-lookup"><span data-stu-id="cec49-134">To reference a function from another location, use the drive name (`Function:`) in the path.</span></span>

```powershell
Set-Location Function:
```

<span data-ttu-id="cec49-135">若要返回到文件系统驱动器，请键入驱动器名称。</span><span class="sxs-lookup"><span data-stu-id="cec49-135">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="cec49-136">例如，键入：</span><span class="sxs-lookup"><span data-stu-id="cec49-136">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="cec49-137">你还可以从任何其他 PowerShell 驱动器使用该 **函数** 提供程序。</span><span class="sxs-lookup"><span data-stu-id="cec49-137">You can also work with the **Function** provider from any other PowerShell drive.</span></span> <span data-ttu-id="cec49-138">若要从其他位置引用函数，请 `Function:` 在路径中使用驱动器名称。</span><span class="sxs-lookup"><span data-stu-id="cec49-138">To reference an function from another location, use the drive name `Function:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="cec49-139">PowerShell 使用别名以允许你熟悉的方法来处理提供程序路径。</span><span class="sxs-lookup"><span data-stu-id="cec49-139">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="cec49-140">命令（如 `dir` 和） `ls` 现在是 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)的别名， `cd` 是 [设置位置](xref:Microsoft.PowerShell.Management.Set-Location)的别名。</span><span class="sxs-lookup"><span data-stu-id="cec49-140">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="cec49-141">和 `pwd` 是 [获取位置](xref:Microsoft.PowerShell.Management.Get-Location)的别名。</span><span class="sxs-lookup"><span data-stu-id="cec49-141">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-functions"></a><span data-ttu-id="cec49-142">获取函数</span><span class="sxs-lookup"><span data-stu-id="cec49-142">Getting functions</span></span>

<span data-ttu-id="cec49-143">此命令将获取当前会话中所有函数的列表。</span><span class="sxs-lookup"><span data-stu-id="cec49-143">This command gets the list of all the functions in the current session.</span></span> <span data-ttu-id="cec49-144">可以在任何 PowerShell 驱动器中使用此命令。</span><span class="sxs-lookup"><span data-stu-id="cec49-144">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="cec49-145">函数提供程序没有容器，因此，当与一起使用时，上面的命令具有相同的效果 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-145">The Function provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="cec49-146">可以通过访问 **定义** 属性来检索函数的定义，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cec49-146">You can retrieve a function's definition by accessing the **Definition** property, as shown below.</span></span>

```powershell
(Get-Item -Path function:more).Definition
```

<span data-ttu-id="cec49-147">还可以使用以美元符号 () 前缀的提供程序路径来检索函数的定义 `$` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-147">You can also retrieve a function's definition using its provider path prefixed by the dollar sign (`$`).</span></span>

```powershell
$function:more
```

### <a name="getting-selected-functions"></a><span data-ttu-id="cec49-148">正在获取选定函数</span><span class="sxs-lookup"><span data-stu-id="cec49-148">Getting selected functions</span></span>

<span data-ttu-id="cec49-149">此命令获取 `man` 驱动器中的函数 `Function:` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-149">This command gets the `man` function from the `Function:` drive.</span></span> <span data-ttu-id="cec49-150">它使用 `Get-Item` cmdlet 来获取函数。</span><span class="sxs-lookup"><span data-stu-id="cec49-150">It uses the `Get-Item` cmdlet to get the function.</span></span> <span data-ttu-id="cec49-151">管道运算符 (`|` 将结果发送到) `Format-Table` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-151">The pipeline operator (`|`) sends the result to `Format-Table`.</span></span> <span data-ttu-id="cec49-152">`-Wrap`参数将不适合行的文本定向到下一行。</span><span class="sxs-lookup"><span data-stu-id="cec49-152">The `-Wrap` parameter directs text that does not fit on the line onto the next line.</span></span> <span data-ttu-id="cec49-153">`-Autosize`参数调整表列的大小以容纳文本。</span><span class="sxs-lookup"><span data-stu-id="cec49-153">The `-Autosize` parameter resizes the table columns to accommodate the text.</span></span>

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a><span data-ttu-id="cec49-154">使用函数提供程序路径</span><span class="sxs-lookup"><span data-stu-id="cec49-154">Working with Function provider paths</span></span>

<span data-ttu-id="cec49-155">这些命令均获取名为的函数 `c:` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-155">These commands both get the function named `c:`.</span></span> <span data-ttu-id="cec49-156">第一个命令可在任何驱动器中使用。</span><span class="sxs-lookup"><span data-stu-id="cec49-156">The first command can be used in any drive.</span></span> <span data-ttu-id="cec49-157">第二个命令在驱动器中使用 `Function:` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-157">The second command is used in the `Function:` drive.</span></span> <span data-ttu-id="cec49-158">由于名称以冒号结束（这是驱动器的语法），因此必须使用驱动器名称来限定路径。</span><span class="sxs-lookup"><span data-stu-id="cec49-158">Because the name ends in a colon, which is the syntax for a drive, you must qualify the path with the drive name.</span></span> <span data-ttu-id="cec49-159">在 `Function:` 驱动器中，可以使用任何一种格式。</span><span class="sxs-lookup"><span data-stu-id="cec49-159">Within the `Function:` drive, you can use either format.</span></span> <span data-ttu-id="cec49-160">在第二个命令中，点 (`.`) 表示当前位置。</span><span class="sxs-lookup"><span data-stu-id="cec49-160">In the second command, the dot (`.`) represents the current location.</span></span>

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a><span data-ttu-id="cec49-161">创建函数</span><span class="sxs-lookup"><span data-stu-id="cec49-161">Creating a function</span></span>

<span data-ttu-id="cec49-162">此命令使用 `New-Item` cmdlet 创建名为的函数 `Win32:` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-162">This command uses the `New-Item` cmdlet to create a function called `Win32:`.</span></span>
<span data-ttu-id="cec49-163">大括号中的表达式是以函数名称表示的脚本块。</span><span class="sxs-lookup"><span data-stu-id="cec49-163">The expression in braces is the script block that is represented by the function name.</span></span>

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

<span data-ttu-id="cec49-164">还可以通过在 PowerShell 命令行中键入函数来创建该函数。</span><span class="sxs-lookup"><span data-stu-id="cec49-164">You can also create a function by typing it at the PowerShell command line.</span></span> <span data-ttu-id="cec49-165">例如，tpe `Function:Win32: {Set-Location C:\Windows\System32}` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-165">For example, tpe `Function:Win32: {Set-Location C:\Windows\System32}`.</span></span> <span data-ttu-id="cec49-166">如果在 `Function:` 驱动器中，则可以省略驱动器名称。</span><span class="sxs-lookup"><span data-stu-id="cec49-166">If you are in the `Function:` drive, you can omit the drive name.</span></span>

## <a name="deleting-a-function"></a><span data-ttu-id="cec49-167">删除函数</span><span class="sxs-lookup"><span data-stu-id="cec49-167">Deleting a function</span></span>

<span data-ttu-id="cec49-168">此命令 `more:` 从当前会话中删除该函数。</span><span class="sxs-lookup"><span data-stu-id="cec49-168">This command deletes the `more:` function from the current session.</span></span>

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a><span data-ttu-id="cec49-169">更改函数</span><span class="sxs-lookup"><span data-stu-id="cec49-169">Changing a function</span></span>

<span data-ttu-id="cec49-170">此命令使用 `Set-Item` cmdlet 来更改函数， `prompt` 使其在路径之前显示时间。</span><span class="sxs-lookup"><span data-stu-id="cec49-170">This command uses the `Set-Item` cmdlet to change the `prompt` function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a><span data-ttu-id="cec49-171">重命名函数</span><span class="sxs-lookup"><span data-stu-id="cec49-171">Rename a function</span></span>

<span data-ttu-id="cec49-172">此命令使用 `Rename-Item` cmdlet 将函数的名称更改 `help` 为 `gh` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-172">This command uses the `Rename-Item` cmdlet to change the name of the `help` function to `gh`.</span></span>

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a><span data-ttu-id="cec49-173">复制函数</span><span class="sxs-lookup"><span data-stu-id="cec49-173">Copying a function</span></span>

<span data-ttu-id="cec49-174">此命令将 `prompt` 函数复制到 `oldPrompt` ，从而为与 prompt 函数相关联的脚本块有效地创建一个新名称。</span><span class="sxs-lookup"><span data-stu-id="cec49-174">This command copies the `prompt` function to `oldPrompt`, effectively creating a new name for the script block that is associated with the prompt function.</span></span>
<span data-ttu-id="cec49-175">如果计划更改原始 prompt 函数，你可以使用此命令来保存该函数。</span><span class="sxs-lookup"><span data-stu-id="cec49-175">You can use this to save the original prompt function if you plan to change it.</span></span>
<span data-ttu-id="cec49-176">新函数的 **Options** 属性的值为 `None` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-176">The **Options** property of the new function has a value of `None`.</span></span> <span data-ttu-id="cec49-177">若要更改 **Options** 属性的值，请使用 `Set-Item` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-177">To change the value of the **Options** property, use `Set-Item`.</span></span>

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a><span data-ttu-id="cec49-178">动态参数</span><span class="sxs-lookup"><span data-stu-id="cec49-178">Dynamic parameters</span></span>

<span data-ttu-id="cec49-179">动态参数是 PowerShell 提供程序添加的 cmdlet 参数，只有在启用了提供程序的驱动器中使用 cmdlet 时，这些参数才可用。</span><span class="sxs-lookup"><span data-stu-id="cec49-179">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="cec49-180">选项 < [ScopedItemOptions] ></span><span class="sxs-lookup"><span data-stu-id="cec49-180">Options <[System.Management.Automation.ScopedItemOptions]></span></span>

<span data-ttu-id="cec49-181">确定函数的 **Options** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="cec49-181">Determines the value of the **Options** property of a function.</span></span>

- <span data-ttu-id="cec49-182">`None`：无选项。</span><span class="sxs-lookup"><span data-stu-id="cec49-182">`None`: No options.</span></span> <span data-ttu-id="cec49-183">`None` 为默认值。</span><span class="sxs-lookup"><span data-stu-id="cec49-183">`None` is the default.</span></span>
- <span data-ttu-id="cec49-184">`Constant`：无法删除该函数，并且无法更改其属性。</span><span class="sxs-lookup"><span data-stu-id="cec49-184">`Constant`: The function cannot be deleted, and its properties cannot be changed.</span></span> <span data-ttu-id="cec49-185">`Constant` 仅在创建函数时才可用。</span><span class="sxs-lookup"><span data-stu-id="cec49-185">`Constant` is available only when you are creating a function.</span></span>
  <span data-ttu-id="cec49-186">不能将现有函数的选项更改为 `Constant` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-186">You cannot change the option of an existing function to `Constant`.</span></span>
- <span data-ttu-id="cec49-187">`Private`：该函数仅在当前范围内可见</span><span class="sxs-lookup"><span data-stu-id="cec49-187">`Private`: The function is visible only in the current scope</span></span>
- <span data-ttu-id="cec49-188"> (子范围) 。</span><span class="sxs-lookup"><span data-stu-id="cec49-188">(not in child scopes).</span></span>
- <span data-ttu-id="cec49-189">`ReadOnly`：除使用参数外，不能更改函数的属性 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="cec49-189">`ReadOnly`: The properties of the function cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="cec49-190">您可以使用 `Remove-Item` 删除函数。</span><span class="sxs-lookup"><span data-stu-id="cec49-190">You can use `Remove-Item` to delete the function.</span></span>
- <span data-ttu-id="cec49-191">`AllScope`：该函数将复制到任何创建的新作用域。</span><span class="sxs-lookup"><span data-stu-id="cec49-191">`AllScope`: The function is copied to any new scopes that are created.</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="cec49-192">支持的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cec49-192">Cmdlets supported</span></span>

- [<span data-ttu-id="cec49-193">New-Item</span><span class="sxs-lookup"><span data-stu-id="cec49-193">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

- [<span data-ttu-id="cec49-194">Set-Item</span><span class="sxs-lookup"><span data-stu-id="cec49-194">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="cec49-195">使用管道</span><span class="sxs-lookup"><span data-stu-id="cec49-195">Using the pipeline</span></span>

<span data-ttu-id="cec49-196">提供程序 cmdlet 接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="cec49-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="cec49-197">可以通过将提供程序数据从一个 cmdlet 发送到另一个提供程序 cmdlet 来使用管道来简化任务。</span><span class="sxs-lookup"><span data-stu-id="cec49-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="cec49-198">若要详细了解如何将管道与提供程序 cmdlet 配合使用，请参阅本文中提供的 cmdlet 参考。</span><span class="sxs-lookup"><span data-stu-id="cec49-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="cec49-199">获取帮助</span><span class="sxs-lookup"><span data-stu-id="cec49-199">Getting help</span></span>

<span data-ttu-id="cec49-200">从 Windows PowerShell 3.0 开始，你可以获取有关提供程序 cmdlet 的自定义帮助主题，它们介绍了这些 cmdlet 在文件系统驱动器中的行为方式。</span><span class="sxs-lookup"><span data-stu-id="cec49-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="cec49-201">若要获取针对文件系统驱动器进行自定义的帮助主题，请在文件系统驱动器中运行[get-help](xref:Microsoft.PowerShell.Core.Get-Help)命令，或使用 get-help 的 `-Path` 参数来[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)指定文件系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="cec49-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a><span data-ttu-id="cec49-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cec49-202">See also</span></span>

[<span data-ttu-id="cec49-203">about_Functions</span><span class="sxs-lookup"><span data-stu-id="cec49-203">about_Functions</span></span>](../About/about_Functions.md)

[<span data-ttu-id="cec49-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cec49-204">about_Providers</span></span>](../About/about_Providers.md)
