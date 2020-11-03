---
description: 介绍如何在 PowerShell 中创建和使用函数。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: 25ef4d3f12752bfabc47d6519988d0da3d5ab0db
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199599"
---
# <a name="about-functions"></a><span data-ttu-id="5f752-104">关于 Functions</span><span class="sxs-lookup"><span data-stu-id="5f752-104">About Functions</span></span>

## <a name="short-description"></a><span data-ttu-id="5f752-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="5f752-105">Short description</span></span>

<span data-ttu-id="5f752-106">介绍如何在 PowerShell 中创建和使用函数。</span><span class="sxs-lookup"><span data-stu-id="5f752-106">Describes how to create and use functions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5f752-107">长说明</span><span class="sxs-lookup"><span data-stu-id="5f752-107">Long description</span></span>

<span data-ttu-id="5f752-108">函数是包含您分配的名称的 PowerShell 语句的列表。</span><span class="sxs-lookup"><span data-stu-id="5f752-108">A function is a list of PowerShell statements that has a name that you assign.</span></span> <span data-ttu-id="5f752-109">运行函数时，请键入函数名称。</span><span class="sxs-lookup"><span data-stu-id="5f752-109">When you run a function, you type the function name.</span></span> <span data-ttu-id="5f752-110">如果在命令提示符下键入语句，则列表中的语句将运行。</span><span class="sxs-lookup"><span data-stu-id="5f752-110">The statements in the list run as if you had typed them at the command prompt.</span></span>

<span data-ttu-id="5f752-111">函数可以非常简单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-111">Functions can be as simple as:</span></span>

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

<span data-ttu-id="5f752-112">函数也可以作为 cmdlet 或应用程序的复杂性。</span><span class="sxs-lookup"><span data-stu-id="5f752-112">A function can also be as complex as a cmdlet or an application program.</span></span>

<span data-ttu-id="5f752-113">与 cmdlet 一样，函数也可以具有参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-113">Like cmdlets, functions can have parameters.</span></span> <span data-ttu-id="5f752-114">参数可以是命名的、位置的、开关或动态参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-114">The parameters can be named, positional, switch, or dynamic parameters.</span></span> <span data-ttu-id="5f752-115">函数参数可以从命令行或从管道中读取。</span><span class="sxs-lookup"><span data-stu-id="5f752-115">Function parameters can be read from the command line or from the pipeline.</span></span>

<span data-ttu-id="5f752-116">函数可以返回可以显示、赋给变量或传递给其他函数或 cmdlet 的值。</span><span class="sxs-lookup"><span data-stu-id="5f752-116">Functions can return values that can be displayed, assigned to variables, or passed to other functions or cmdlets.</span></span> <span data-ttu-id="5f752-117">你还可以使用关键字指定返回值 `return` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-117">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="5f752-118">`return`关键字不会影响或禁止从函数返回的其他输出。</span><span class="sxs-lookup"><span data-stu-id="5f752-118">The `return` keyword does not affect or suppress other output returned from your function.</span></span> <span data-ttu-id="5f752-119">不过， `return` 关键字将退出该函数。</span><span class="sxs-lookup"><span data-stu-id="5f752-119">However, the `return` keyword exits the function at that line.</span></span> <span data-ttu-id="5f752-120">有关详细信息，请参阅 [about_Return](about_Return.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-120">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="5f752-121">函数的语句列表可以包含具有关键字、和的不同类型的语句 `Begin` 列表 `Process` `End` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-121">The function's statement list can contain different types of statement lists with the keywords `Begin`, `Process`, and `End`.</span></span> <span data-ttu-id="5f752-122">这些语句以不同方式列出管道中的处理输入。</span><span class="sxs-lookup"><span data-stu-id="5f752-122">These statement lists handle input from the pipeline differently.</span></span>

<span data-ttu-id="5f752-123">筛选器是一种使用关键字的特殊函数 `Filter` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-123">A filter is a special kind of function that uses the `Filter` keyword.</span></span>

<span data-ttu-id="5f752-124">函数也可以像 cmdlet 一样操作。</span><span class="sxs-lookup"><span data-stu-id="5f752-124">Functions can also act like cmdlets.</span></span> <span data-ttu-id="5f752-125">你可以创建一个函数，该函数的工作方式与 cmdlet 相同，无需使用 `C#` 编程。</span><span class="sxs-lookup"><span data-stu-id="5f752-125">You can create a function that works just like a cmdlet without using `C#` programming.</span></span> <span data-ttu-id="5f752-126">有关详细信息，请参阅 [about_Functions_Advanced](about_Functions_Advanced.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-126">For more information, see [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="5f752-127">语法</span><span class="sxs-lookup"><span data-stu-id="5f752-127">Syntax</span></span>

<span data-ttu-id="5f752-128">下面是函数的语法：</span><span class="sxs-lookup"><span data-stu-id="5f752-128">The following is the syntax for a function:</span></span>

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="5f752-129">函数包含以下项：</span><span class="sxs-lookup"><span data-stu-id="5f752-129">A function includes the following items:</span></span>

- <span data-ttu-id="5f752-130">`Function`关键字</span><span class="sxs-lookup"><span data-stu-id="5f752-130">A `Function` keyword</span></span>
- <span data-ttu-id="5f752-131">范围 (可选) </span><span class="sxs-lookup"><span data-stu-id="5f752-131">A scope (optional)</span></span>
- <span data-ttu-id="5f752-132">你选择的名称</span><span class="sxs-lookup"><span data-stu-id="5f752-132">A name that you select</span></span>
- <span data-ttu-id="5f752-133">任意数量的命名参数 (可选) </span><span class="sxs-lookup"><span data-stu-id="5f752-133">Any number of named parameters (optional)</span></span>
- <span data-ttu-id="5f752-134">括在大括号中的一个或多个 PowerShell 命令 `{}`</span><span class="sxs-lookup"><span data-stu-id="5f752-134">One or more PowerShell commands enclosed in braces `{}`</span></span>

<span data-ttu-id="5f752-135">有关 `Dynamicparam` 函数中关键字和动态参数的详细信息，请参阅 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-135">For more information about the `Dynamicparam` keyword and dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="simple-functions"></a><span data-ttu-id="5f752-136">简单函数</span><span class="sxs-lookup"><span data-stu-id="5f752-136">Simple Functions</span></span>

<span data-ttu-id="5f752-137">函数不必太复杂，很有用。</span><span class="sxs-lookup"><span data-stu-id="5f752-137">Functions do not have to be complicated to be useful.</span></span> <span data-ttu-id="5f752-138">最简单的函数具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="5f752-138">The simplest functions have the following format:</span></span>

```
function <function-name> {statements}
```

<span data-ttu-id="5f752-139">例如，以下函数通过 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5f752-139">For example, the following function starts PowerShell with the Run as Administrator option.</span></span>

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

<span data-ttu-id="5f752-140">若要使用函数，请键入： `Start-PSAdmin`</span><span class="sxs-lookup"><span data-stu-id="5f752-140">To use the function, type: `Start-PSAdmin`</span></span>

<span data-ttu-id="5f752-141">若要向函数添加语句，请在单独的行中键入每个语句，或使用分号 `;` 分隔这些语句。</span><span class="sxs-lookup"><span data-stu-id="5f752-141">To add statements to the function, type each statement on a separate line, or use a semi-colon `;` to separate the statements.</span></span>

<span data-ttu-id="5f752-142">例如，以下函数将查找在 `.jpg` 开始日期之后更改的当前用户目录中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="5f752-142">For example, the following function finds all `.jpg` files in the current user's directories that were changed after the start date.</span></span>

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

<span data-ttu-id="5f752-143">您可以创建有用的小型函数的工具箱。</span><span class="sxs-lookup"><span data-stu-id="5f752-143">You can create a toolbox of useful small functions.</span></span> <span data-ttu-id="5f752-144">将这些函数添加到 PowerShell 配置文件，如本主题 [about_Profiles](about_Profiles.md) 和后面所述。</span><span class="sxs-lookup"><span data-stu-id="5f752-144">Add these functions to your PowerShell profile, as described in [about_Profiles](about_Profiles.md) and later in this topic.</span></span>

## <a name="function-names"></a><span data-ttu-id="5f752-145">函数名称</span><span class="sxs-lookup"><span data-stu-id="5f752-145">Function Names</span></span>

<span data-ttu-id="5f752-146">可以为函数分配任何名称，但与其他人共享的函数应遵循为所有 PowerShell 命令建立的命名规则。</span><span class="sxs-lookup"><span data-stu-id="5f752-146">You can assign any name to a function, but functions that you share with others should follow the naming rules that have been established for all PowerShell commands.</span></span>

<span data-ttu-id="5f752-147">函数名称应包含动词-名词对，其中谓词标识函数执行的操作，名词标识该 cmdlet 执行其操作的项。</span><span class="sxs-lookup"><span data-stu-id="5f752-147">Functions names should consist of a verb-noun pair in which the verb identifies the action that the function performs and the noun identifies the item on which the cmdlet performs its action.</span></span>

<span data-ttu-id="5f752-148">函数应使用已为所有 PowerShell 命令批准的标准谓词。</span><span class="sxs-lookup"><span data-stu-id="5f752-148">Functions should use the standard verbs that have been approved for all PowerShell commands.</span></span> <span data-ttu-id="5f752-149">这些谓词可帮助我们使命令名称变得简单、一致和易于理解。</span><span class="sxs-lookup"><span data-stu-id="5f752-149">These verbs help us to keep our command names simple, consistent, and easy for users to understand.</span></span>

<span data-ttu-id="5f752-150">有关标准 PowerShell 谓词的详细信息，请参阅 Microsoft Docs 中的 [批准的动词](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) 。</span><span class="sxs-lookup"><span data-stu-id="5f752-150">For more information about the standard PowerShell verbs, see [Approved Verbs](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in the Microsoft Docs.</span></span>

## <a name="functions-with-parameters"></a><span data-ttu-id="5f752-151">带参数的函数</span><span class="sxs-lookup"><span data-stu-id="5f752-151">Functions with Parameters</span></span>

<span data-ttu-id="5f752-152">可以将参数用于函数，包括命名参数、位置参数、开关参数和动态参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-152">You can use parameters with functions, including named parameters, positional parameters, switch parameters, and dynamic parameters.</span></span> <span data-ttu-id="5f752-153">有关函数中的动态参数的详细信息，请参阅 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-153">For more information about dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="named-parameters"></a><span data-ttu-id="5f752-154">命名的参数</span><span class="sxs-lookup"><span data-stu-id="5f752-154">Named Parameters</span></span>

<span data-ttu-id="5f752-155">可以定义任意数量的命名参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-155">You can define any number of named parameters.</span></span> <span data-ttu-id="5f752-156">可以包含命名参数的默认值，如本主题后面所述。</span><span class="sxs-lookup"><span data-stu-id="5f752-156">You can include a default value for named parameters, as described later in this topic.</span></span>

<span data-ttu-id="5f752-157">可以使用关键字在大括号内定义参数 `Param` ，如下面的示例语法所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-157">You can define parameters inside the braces using the `Param` keyword, as shown in the following sample syntax:</span></span>

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

<span data-ttu-id="5f752-158">你还可以在不带关键字的大括号外定义参数 `Param` ，如下面的示例语法所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-158">You can also define parameters outside the braces without the `Param` keyword, as shown in the following sample syntax:</span></span>

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

<span data-ttu-id="5f752-159">下面是此替代语法的示例。</span><span class="sxs-lookup"><span data-stu-id="5f752-159">Below is an example of this alternative syntax.</span></span>

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

<span data-ttu-id="5f752-160">尽管第一种方法是首选方法，但这两种方法之间没有区别。</span><span class="sxs-lookup"><span data-stu-id="5f752-160">While the first method is preferred, there is no difference between these two methods.</span></span>

<span data-ttu-id="5f752-161">运行函数时，为参数提供的值将分配给包含参数名的变量。</span><span class="sxs-lookup"><span data-stu-id="5f752-161">When you run the function, the value you supply for a parameter is assigned to a variable that contains the parameter name.</span></span> <span data-ttu-id="5f752-162">可在函数中使用该变量的值。</span><span class="sxs-lookup"><span data-stu-id="5f752-162">The value of that variable can be used in the function.</span></span>

<span data-ttu-id="5f752-163">下面的示例是一个名为的函数 `Get-SmallFiles` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-163">The following example is a function called `Get-SmallFiles`.</span></span> <span data-ttu-id="5f752-164">此函数有一个 `$Size` 参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-164">This function has a `$Size` parameter.</span></span> <span data-ttu-id="5f752-165">函数显示小于参数值的所有文件 `$Size` ，并排除目录：</span><span class="sxs-lookup"><span data-stu-id="5f752-165">The function displays all the files that are smaller than the value of the `$Size` parameter, and it excludes directories:</span></span>

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="5f752-166">在函数中，可以使用 `$Size` 变量，该变量是为参数定义的名称。</span><span class="sxs-lookup"><span data-stu-id="5f752-166">In the function, you can use the `$Size` variable, which is the name defined for the parameter.</span></span>

<span data-ttu-id="5f752-167">若要使用此函数，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f752-167">To use this function, type the following command:</span></span>

```powershell
Get-SmallFiles -Size 50
```

<span data-ttu-id="5f752-168">你还可以在没有参数名称的情况下为命名参数输入值。</span><span class="sxs-lookup"><span data-stu-id="5f752-168">You can also enter a value for a named parameter without the parameter name.</span></span>
<span data-ttu-id="5f752-169">例如，以下命令提供的结果与为 **Size** 参数命名的命令相同：</span><span class="sxs-lookup"><span data-stu-id="5f752-169">For example, the following command gives the same result as a command that names the **Size** parameter:</span></span>

```powershell
Get-SmallFiles 50
```

<span data-ttu-id="5f752-170">若要定义参数的默认值，请在参数名称后面键入一个等号和值，如下面的示例中所示 `Get-SmallFiles` ：</span><span class="sxs-lookup"><span data-stu-id="5f752-170">To define a default value for a parameter, type an equal sign and the value after the parameter name, as shown in the following variation of the `Get-SmallFiles` example:</span></span>

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="5f752-171">如果键入的 `Get-SmallFiles` 值不包含任何值，则函数会将100赋给 `$size` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-171">If you type `Get-SmallFiles` without a value, the function assigns 100 to `$size`.</span></span> <span data-ttu-id="5f752-172">如果提供值，该函数将使用该值。</span><span class="sxs-lookup"><span data-stu-id="5f752-172">If you provide a value, the function uses that value.</span></span>

<span data-ttu-id="5f752-173">或者，您可以通过将 **PSDefaultValue** 特性添加到参数说明，并指定 **PSDefaultValue** 的 **help** 属性，来提供描述参数的默认值的简短帮助字符串。</span><span class="sxs-lookup"><span data-stu-id="5f752-173">Optionally, you can provide a brief help string that describes the default value of your parameter, by adding the **PSDefaultValue** attribute to the description of your parameter, and specifying the **Help** property of **PSDefaultValue** .</span></span> <span data-ttu-id="5f752-174">若要提供描述函数中 **Size** 参数 (100) 默认值的帮助字符串 `Get-SmallFiles` ，请添加 **PSDefaultValue** 属性，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5f752-174">To provide a help string that describes the default value (100) of the **Size** parameter in the `Get-SmallFiles` function, add the **PSDefaultValue** attribute as shown in the following example.</span></span>

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

<span data-ttu-id="5f752-175">有关 **PSDefaultValue** 特性类的详细信息，请参阅 [PSDefaultValue 特性成员](/dotnet/api/system.management.automation.psdefaultvalueattribute)。</span><span class="sxs-lookup"><span data-stu-id="5f752-175">For more information about the **PSDefaultValue** attribute class, see [PSDefaultValue Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span></span>

### <a name="positional-parameters"></a><span data-ttu-id="5f752-176">位置参数</span><span class="sxs-lookup"><span data-stu-id="5f752-176">Positional Parameters</span></span>

<span data-ttu-id="5f752-177">位置参数是没有参数名称的参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-177">A positional parameter is a parameter without a parameter name.</span></span> <span data-ttu-id="5f752-178">PowerShell 使用参数值顺序将每个参数值与函数中的参数相关联。</span><span class="sxs-lookup"><span data-stu-id="5f752-178">PowerShell uses the parameter value order to associate each parameter value with a parameter in the function.</span></span>

<span data-ttu-id="5f752-179">使用位置参数时，请在函数名称后面键入一个或多个值。</span><span class="sxs-lookup"><span data-stu-id="5f752-179">When you use positional parameters, type one or more values after the function name.</span></span> <span data-ttu-id="5f752-180">位置参数值将分配给 `$args` 数组变量。</span><span class="sxs-lookup"><span data-stu-id="5f752-180">Positional parameter values are assigned to the `$args` array variable.</span></span>
<span data-ttu-id="5f752-181">函数名称后面的值将分配给数组中的第一个位置 `$args` `$args[0]` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-181">The value that follows the function name is assigned to the first position in the `$args` array, `$args[0]`.</span></span>

<span data-ttu-id="5f752-182">以下 `Get-Extension` 函数将 `.txt` 文件扩展名添加到提供的文件名：</span><span class="sxs-lookup"><span data-stu-id="5f752-182">The following `Get-Extension` function adds the `.txt` file name extension to a file name that you supply:</span></span>

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a><span data-ttu-id="5f752-183">开关参数</span><span class="sxs-lookup"><span data-stu-id="5f752-183">Switch Parameters</span></span>

<span data-ttu-id="5f752-184">开关是不需要值的参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-184">A switch is a parameter that does not require a value.</span></span> <span data-ttu-id="5f752-185">而是键入函数名称，后跟开关参数的名称。</span><span class="sxs-lookup"><span data-stu-id="5f752-185">Instead, you type the function name followed by the name of the switch parameter.</span></span>

<span data-ttu-id="5f752-186">若要定义开关参数，请在 `[switch]` 参数名称前面指定类型，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-186">To define a switch parameter, specify the type `[switch]` before the parameter name, as shown in the following example:</span></span>

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

<span data-ttu-id="5f752-187">在 `On` 函数名后键入 switch 参数时，该函数将显示 "开关 on"。</span><span class="sxs-lookup"><span data-stu-id="5f752-187">When you type the `On` switch parameter after the function name, the function displays "Switch on".</span></span> <span data-ttu-id="5f752-188">如果没有开关参数，它将显示 "切换为关闭"。</span><span class="sxs-lookup"><span data-stu-id="5f752-188">Without the switch parameter, it displays "Switch off".</span></span>

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

<span data-ttu-id="5f752-189">你还可以在运行函数时向开关分配一个 **布尔** 值，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-189">You can also assign a **Boolean** value to a switch when you run the function, as shown in the following example:</span></span>

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a><span data-ttu-id="5f752-190">使用展开表示命令参数</span><span class="sxs-lookup"><span data-stu-id="5f752-190">Using Splatting to Represent Command Parameters</span></span>

<span data-ttu-id="5f752-191">可以使用展开来表示命令的参数。</span><span class="sxs-lookup"><span data-stu-id="5f752-191">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="5f752-192">此功能是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5f752-192">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="5f752-193">在调用会话中的命令的函数中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="5f752-193">Use this technique in functions that call commands in the session.</span></span> <span data-ttu-id="5f752-194">不需要声明或枚举命令参数，也不需要在命令参数更改时更改函数。</span><span class="sxs-lookup"><span data-stu-id="5f752-194">You do not need to declare or enumerate the command parameters, or change the function when command parameters change.</span></span>

<span data-ttu-id="5f752-195">下面的示例函数调用 `Get-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f752-195">The following sample function calls the `Get-Command` cmdlet.</span></span> <span data-ttu-id="5f752-196">命令使用 `@Args` 来表示的参数 `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-196">The command uses `@Args` to represent the parameters of `Get-Command`.</span></span>

```powershell
function Get-MyCommand { Get-Command @Args }
```

<span data-ttu-id="5f752-197">调用函数时，可以使用的所有参数 `Get-Command` `Get-MyCommand` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-197">You can use all of the parameters of `Get-Command` when you call the `Get-MyCommand` function.</span></span> <span data-ttu-id="5f752-198">参数和参数值使用传递到命令 `@Args` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-198">The parameters and parameter values are passed to the command using `@Args`.</span></span>

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

<span data-ttu-id="5f752-199">此 `@Args` 功能使用 `$Args` 自动参数，该参数表示未声明的 cmdlet 参数和来自剩余参数的值。</span><span class="sxs-lookup"><span data-stu-id="5f752-199">The `@Args` feature uses the `$Args` automatic parameter, which represents undeclared cmdlet parameters and values from remaining arguments.</span></span>

<span data-ttu-id="5f752-200">有关展开的详细信息，请参阅 [about_Splatting](about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-200">For more information about splatting, see [about_Splatting](about_Splatting.md).</span></span>

## <a name="piping-objects-to-functions"></a><span data-ttu-id="5f752-201">管道对象到函数</span><span class="sxs-lookup"><span data-stu-id="5f752-201">Piping Objects to Functions</span></span>

<span data-ttu-id="5f752-202">任何函数都可以从管道中获取输入。</span><span class="sxs-lookup"><span data-stu-id="5f752-202">Any function can take input from the pipeline.</span></span> <span data-ttu-id="5f752-203">您可以使用 `Begin` 、和关键字控制函数处理管道输入的方式 `Process` `End` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-203">You can control how a function processes input from the pipeline using `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="5f752-204">下面的语法示例显示了三个关键字：</span><span class="sxs-lookup"><span data-stu-id="5f752-204">The following sample syntax shows the three keywords:</span></span>

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="5f752-205">`Begin`语句列表仅在函数的开始处运行一次。</span><span class="sxs-lookup"><span data-stu-id="5f752-205">The `Begin` statement list runs one time only, at the beginning of the function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f752-206">如果函数定义了 `Begin` `Process` 或 `End` 块，则所有代码必须位于这些块内。</span><span class="sxs-lookup"><span data-stu-id="5f752-206">If your function defines a `Begin`, `Process` or `End` block, all of your code must reside inside those blocks.</span></span> <span data-ttu-id="5f752-207">如果定义了任何块，则不会在块之外识别 *任何* 代码。</span><span class="sxs-lookup"><span data-stu-id="5f752-207">No code will be recognized outside the blocks if *any* of the blocks are defined.</span></span>

<span data-ttu-id="5f752-208">`Process`语句列表对管道中的每个对象运行一次。</span><span class="sxs-lookup"><span data-stu-id="5f752-208">The `Process` statement list runs one time for each object in the pipeline.</span></span>
<span data-ttu-id="5f752-209">当 `Process` 块正在运行时，每个管道对象将分配给 `$_` 自动变量，一次分配一个管道对象。</span><span class="sxs-lookup"><span data-stu-id="5f752-209">While the `Process` block is running, each pipeline object is assigned to the `$_` automatic variable, one pipeline object at a time.</span></span>

<span data-ttu-id="5f752-210">函数收到管道中的所有对象后， `End` 语句列表将运行一次。</span><span class="sxs-lookup"><span data-stu-id="5f752-210">After the function receives all the objects in the pipeline, the `End` statement list runs one time.</span></span> <span data-ttu-id="5f752-211">如果未 `Begin` `Process` 使用、或 `End` 关键字，则将所有语句视为 `End` 语句列表。</span><span class="sxs-lookup"><span data-stu-id="5f752-211">If no `Begin`, `Process`, or `End` keywords are used, all the statements are treated like an `End` statement list.</span></span>

<span data-ttu-id="5f752-212">下面的函数使用 `Process` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5f752-212">The following function uses the `Process` keyword.</span></span> <span data-ttu-id="5f752-213">函数显示管道中的示例：</span><span class="sxs-lookup"><span data-stu-id="5f752-213">The function displays examples from the pipeline:</span></span>

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

<span data-ttu-id="5f752-214">若要演示此函数，请输入用逗号分隔的数字列表，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-214">To demonstrate this function, enter an list of numbers separated by commas, as shown in the following example:</span></span>

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

<span data-ttu-id="5f752-215">在管道中使用函数时，将向该函数传递的对象将分配给 `$input` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="5f752-215">When you use a function in a pipeline, the objects piped to the function are assigned to the `$input` automatic variable.</span></span> <span data-ttu-id="5f752-216">函数在任何对象来自管道之前，运行带有关键字的语句 `Begin` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-216">The function runs statements with the `Begin` keyword before any objects come from the pipeline.</span></span> <span data-ttu-id="5f752-217">函数在 `End` 从管道接收到所有对象之后，使用关键字运行语句。</span><span class="sxs-lookup"><span data-stu-id="5f752-217">The function runs statements with the `End` keyword after all the objects have been received from the pipeline.</span></span>

<span data-ttu-id="5f752-218">下面的示例演示 `$input` 带有 and 关键字的自动变量 `Begin` `End` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-218">The following example shows the `$input` automatic variable with `Begin` and `End` keywords.</span></span>

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

<span data-ttu-id="5f752-219">如果使用管道运行此函数，则将显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="5f752-219">If this function is run by using the pipeline, it displays the following results:</span></span>

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

<span data-ttu-id="5f752-220">当 `Begin` 语句运行时，该函数不具有管道的输入。</span><span class="sxs-lookup"><span data-stu-id="5f752-220">When the `Begin` statement runs, the function does not have the input from the pipeline.</span></span> <span data-ttu-id="5f752-221">`End`语句在函数具有值后运行。</span><span class="sxs-lookup"><span data-stu-id="5f752-221">The `End` statement runs after the function has the values.</span></span>

<span data-ttu-id="5f752-222">如果函数具有 `Process` 关键字，则中的每个对象 `$input` 都将从中移除 `$input` 并被分配给 `$_` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-222">If the function has a `Process` keyword, each object in `$input` is removed from `$input` and assigned to `$_`.</span></span> <span data-ttu-id="5f752-223">下面的示例包含一个 `Process` 语句列表：</span><span class="sxs-lookup"><span data-stu-id="5f752-223">The following example has a `Process` statement list:</span></span>

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

<span data-ttu-id="5f752-224">在此示例中，向函数发出管道的每个对象都发送到 `Process` 语句列表。</span><span class="sxs-lookup"><span data-stu-id="5f752-224">In this example, each object that is piped to the function is sent to the `Process` statement list.</span></span> <span data-ttu-id="5f752-225">`Process`语句在每个对象上运行（一次一个对象）。</span><span class="sxs-lookup"><span data-stu-id="5f752-225">The `Process` statements run on each object, one object at a time.</span></span> <span data-ttu-id="5f752-226">`$input`当函数到达关键字时，自动变量为空 `End` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-226">The `$input` automatic variable is empty when the function reaches the `End` keyword.</span></span>

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

<span data-ttu-id="5f752-227">有关详细信息，请参阅[使用枚举](about_Automatic_Variables.md#using-enumerators)器</span><span class="sxs-lookup"><span data-stu-id="5f752-227">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators)</span></span>

## <a name="filters"></a><span data-ttu-id="5f752-228">筛选器</span><span class="sxs-lookup"><span data-stu-id="5f752-228">Filters</span></span>

<span data-ttu-id="5f752-229">筛选器是在管道中的每个对象上运行的函数类型。</span><span class="sxs-lookup"><span data-stu-id="5f752-229">A filter is a type of function that runs on each object in the pipeline.</span></span> <span data-ttu-id="5f752-230">筛选器类似于函数，其中的所有语句都位于 `Process` 块中。</span><span class="sxs-lookup"><span data-stu-id="5f752-230">A filter resembles a function with all its statements in a `Process` block.</span></span>

<span data-ttu-id="5f752-231">筛选器的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f752-231">The syntax of a filter is as follows:</span></span>

```
filter [<scope:>]<name> {<statement list>}
```

<span data-ttu-id="5f752-232">以下筛选器从管道中获取日志条目，然后显示整个条目或仅显示条目的消息部分：</span><span class="sxs-lookup"><span data-stu-id="5f752-232">The following filter takes log entries from the pipeline and then displays either the whole entry or only the message portion of the entry:</span></span>

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a><span data-ttu-id="5f752-233">函数范围</span><span class="sxs-lookup"><span data-stu-id="5f752-233">Function Scope</span></span>

<span data-ttu-id="5f752-234">函数存在于创建它的作用域中。</span><span class="sxs-lookup"><span data-stu-id="5f752-234">A function exists in the scope in which it was created.</span></span>

<span data-ttu-id="5f752-235">如果函数是脚本的一部分，则该函数可用于该脚本中的语句。</span><span class="sxs-lookup"><span data-stu-id="5f752-235">If a function is part of a script, the function is available to statements within that script.</span></span> <span data-ttu-id="5f752-236">默认情况下，在命令提示符下不能使用脚本中的函数。</span><span class="sxs-lookup"><span data-stu-id="5f752-236">By default, a function in a script is not available at the command prompt.</span></span>

<span data-ttu-id="5f752-237">可以指定函数的作用域。</span><span class="sxs-lookup"><span data-stu-id="5f752-237">You can specify the scope of a function.</span></span> <span data-ttu-id="5f752-238">例如，在以下示例中，将函数添加到全局范围：</span><span class="sxs-lookup"><span data-stu-id="5f752-238">For example, the function is added to the global scope in the following example:</span></span>

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

<span data-ttu-id="5f752-239">当函数在全局范围中时，可以在脚本中、在函数中使用函数，并在命令行中使用函数。</span><span class="sxs-lookup"><span data-stu-id="5f752-239">When a function is in the global scope, you can use the function in scripts, in functions, and at the command line.</span></span>

<span data-ttu-id="5f752-240">函数通常会创建一个作用域。</span><span class="sxs-lookup"><span data-stu-id="5f752-240">Functions normally create a scope.</span></span> <span data-ttu-id="5f752-241">在函数中创建的项（如变量）仅存在于函数作用域中。</span><span class="sxs-lookup"><span data-stu-id="5f752-241">The items created in a function, such as variables, exist only in the function scope.</span></span>

<span data-ttu-id="5f752-242">有关 PowerShell 中的作用域的详细信息，请参阅 [about_Scopes](about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-242">For more information about scope in PowerShell, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="finding-and-managing-functions-using-the-function-drive"></a><span data-ttu-id="5f752-243">使用函数查找和管理函数：驱动器</span><span class="sxs-lookup"><span data-stu-id="5f752-243">Finding and Managing Functions Using the Function: Drive</span></span>

<span data-ttu-id="5f752-244">PowerShell 中的所有函数和筛选器都将自动存储在 `Function:` 驱动器中。</span><span class="sxs-lookup"><span data-stu-id="5f752-244">All the functions and filters in PowerShell are automatically stored in the `Function:` drive.</span></span> <span data-ttu-id="5f752-245">此驱动器由 PowerShell **函数** 提供程序公开。</span><span class="sxs-lookup"><span data-stu-id="5f752-245">This drive is exposed by the PowerShell **Function** provider.</span></span>

<span data-ttu-id="5f752-246">在引用驱动器时 `Function:` ，请在 **函数** 后面键入一个冒号，就像引用计算机的或驱动器时所做的那样 `C` `D` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-246">When referring to the `Function:` drive, type a colon after **Function** , just as you would do when referencing the `C` or `D` drive of a computer.</span></span>

<span data-ttu-id="5f752-247">以下命令显示 PowerShell 的当前会话中的所有函数：</span><span class="sxs-lookup"><span data-stu-id="5f752-247">The following command displays all the functions in the current session of PowerShell:</span></span>

```powershell
Get-ChildItem function:
```

<span data-ttu-id="5f752-248">函数中的命令以脚本块的形式存储在函数的定义属性中。</span><span class="sxs-lookup"><span data-stu-id="5f752-248">The commands in the function are stored as a script block in the definition property of the function.</span></span> <span data-ttu-id="5f752-249">例如，若要显示 PowerShell 附带的帮助函数中的命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="5f752-249">For example, to display the commands in the Help function that comes with PowerShell, type:</span></span>

```powershell
(Get-ChildItem function:help).Definition
```

<span data-ttu-id="5f752-250">你还可以使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="5f752-250">You can also use the following syntax.</span></span>

```powershell
$function:help
```

<span data-ttu-id="5f752-251">有关驱动器的详细信息 `Function:` ，请参阅 **函数** 提供程序的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5f752-251">For more information about the `Function:` drive, see the help topic for the **Function** provider.</span></span> <span data-ttu-id="5f752-252">键入 `Get-Help Function`。</span><span class="sxs-lookup"><span data-stu-id="5f752-252">Type `Get-Help Function`.</span></span>

## <a name="reusing-functions-in-new-sessions"></a><span data-ttu-id="5f752-253">在新会话中重用函数</span><span class="sxs-lookup"><span data-stu-id="5f752-253">Reusing Functions in New Sessions</span></span>

<span data-ttu-id="5f752-254">在 PowerShell 命令提示符下键入函数时，该函数将成为当前会话的一部分。</span><span class="sxs-lookup"><span data-stu-id="5f752-254">When you type a function at the PowerShell command prompt, the function becomes part of the current session.</span></span> <span data-ttu-id="5f752-255">直到会话结束时，此功能才可用。</span><span class="sxs-lookup"><span data-stu-id="5f752-255">It is available until the session ends.</span></span>

<span data-ttu-id="5f752-256">若要在所有 PowerShell 会话中使用函数，请将函数添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="5f752-256">To use your function in all PowerShell sessions, add the function to your PowerShell profile.</span></span> <span data-ttu-id="5f752-257">有关配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-257">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="5f752-258">你还可以将函数保存在 PowerShell 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="5f752-258">You can also save your function in a PowerShell script file.</span></span> <span data-ttu-id="5f752-259">在文本文件中键入函数，然后使用文件扩展名保存该文件 `.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="5f752-259">Type your function in a text file, and then save the file with the `.ps1` file name extension.</span></span>

## <a name="writing-help-for-functions"></a><span data-ttu-id="5f752-260">编写函数的帮助</span><span class="sxs-lookup"><span data-stu-id="5f752-260">Writing Help for Functions</span></span>

<span data-ttu-id="5f752-261">`Get-Help`Cmdlet 可获取有关函数以及 cmdlet、提供程序和脚本的帮助。</span><span class="sxs-lookup"><span data-stu-id="5f752-261">The `Get-Help` cmdlet gets help for functions, as well as for cmdlets, providers, and scripts.</span></span> <span data-ttu-id="5f752-262">若要获取有关函数的帮助，请键入 `Get-Help` 后跟函数名称。</span><span class="sxs-lookup"><span data-stu-id="5f752-262">To get help for a function, type `Get-Help` followed by the function name.</span></span>

<span data-ttu-id="5f752-263">例如，若要获取有关该函数的帮助 `Get-MyDisks` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="5f752-263">For example, to get help for the `Get-MyDisks` function, type:</span></span>

```powershell
Get-Help Get-MyDisks
```

<span data-ttu-id="5f752-264">您可以使用以下两种方法之一来编写函数的帮助：</span><span class="sxs-lookup"><span data-stu-id="5f752-264">You can write help for a function by using either of the two following methods:</span></span>

- <span data-ttu-id="5f752-265">函数 Comment-Based 帮助</span><span class="sxs-lookup"><span data-stu-id="5f752-265">Comment-Based Help for Functions</span></span>

  <span data-ttu-id="5f752-266">在注释中使用特殊关键字创建帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5f752-266">Create a help topic by using special keywords in the comments.</span></span> <span data-ttu-id="5f752-267">若要为函数创建基于注释的帮助，注释必须位于函数体的开头或末尾，或者位于 function 关键字之前的行中。</span><span class="sxs-lookup"><span data-stu-id="5f752-267">To create comment-based help for a function, the comments must be placed at the beginning or end of the function body or on the lines preceding the function keyword.</span></span> <span data-ttu-id="5f752-268">有关基于注释的帮助的详细信息，请参阅 [about_Comment_Based_Help](about_Comment_Based_Help.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-268">For more information about comment-based help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="5f752-269">函数 XML-Based 帮助</span><span class="sxs-lookup"><span data-stu-id="5f752-269">XML-Based Help for Functions</span></span>

  <span data-ttu-id="5f752-270">创建基于 XML 的帮助主题，如通常为 cmdlet 创建的类型。</span><span class="sxs-lookup"><span data-stu-id="5f752-270">Create an XML-based help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="5f752-271">如果要将帮助主题本地化为多种语言，则必须提供基于 XML 的帮助。</span><span class="sxs-lookup"><span data-stu-id="5f752-271">XML-based help is required if you are localizing help topics into multiple languages.</span></span>

  <span data-ttu-id="5f752-272">若要将函数与基于 XML 的帮助主题相关联，请使用 `.ExternalHelp` 基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="5f752-272">To associate the function with the XML-based help topic, use the `.ExternalHelp` comment-based help keyword.</span></span> <span data-ttu-id="5f752-273">如果没有此关键字，则找 `Get-Help` 不到函数帮助主题，并且对的调用将 `Get-Help` 仅返回自动生成的帮助。</span><span class="sxs-lookup"><span data-stu-id="5f752-273">Without this keyword, `Get-Help` cannot find the function help topic and calls to `Get-Help` for the function return only auto-generated help.</span></span>

  <span data-ttu-id="5f752-274">有关关键字的详细信息 `ExternalHelp` ，请参阅 [about_Comment_Based_Help](about_Comment_Based_Help.md)。</span><span class="sxs-lookup"><span data-stu-id="5f752-274">For more information about the `ExternalHelp` keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="5f752-275">有关基于 XML 的帮助的详细信息，请参阅 MSDN library 中的 how [To Write Cmdlet help （如何编写 Cmdlet 帮助](https://go.microsoft.com/fwlink/?LinkID=123415) ）。</span><span class="sxs-lookup"><span data-stu-id="5f752-275">For more information about XML-based help, see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f752-276">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f752-276">See also</span></span>

[<span data-ttu-id="5f752-277">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="5f752-277">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="5f752-278">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="5f752-278">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="5f752-279">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="5f752-279">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="5f752-280">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="5f752-280">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="5f752-281">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="5f752-281">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="5f752-282">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="5f752-282">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="5f752-283">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="5f752-283">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="5f752-284">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="5f752-284">about_Parameters</span></span>](about_Parameters.md)

[<span data-ttu-id="5f752-285">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="5f752-285">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="5f752-286">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="5f752-286">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="5f752-287">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="5f752-287">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="5f752-288">about_Function_provider</span><span class="sxs-lookup"><span data-stu-id="5f752-288">about_Function_provider</span></span>](about_Function_provider.md)
