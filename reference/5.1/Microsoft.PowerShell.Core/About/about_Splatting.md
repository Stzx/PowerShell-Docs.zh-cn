---
description: 介绍如何使用展开在 PowerShell 中将参数传递给命令。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: 0cf9702adcc7d19a19d9aaa9673fb42e3af715fa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200240"
---
# <a name="about-splatting"></a><span data-ttu-id="7d8bd-104">关于展开</span><span class="sxs-lookup"><span data-stu-id="7d8bd-104">About Splatting</span></span>

## <a name="short-description"></a><span data-ttu-id="7d8bd-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="7d8bd-105">Short description</span></span>

<span data-ttu-id="7d8bd-106">介绍如何使用展开在 PowerShell 中将参数传递给命令。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-106">Describes how to use splatting to pass parameters to commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7d8bd-107">长说明</span><span class="sxs-lookup"><span data-stu-id="7d8bd-107">Long description</span></span>

<span data-ttu-id="7d8bd-108">展开是将参数值集合作为一个单元传递到命令的方法。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-108">Splatting is a method of passing a collection of parameter values to a command as a unit.</span></span> <span data-ttu-id="7d8bd-109">PowerShell 会将集合中的每个值与命令参数相关联。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-109">PowerShell associates each value in the collection with a command parameter.</span></span> <span data-ttu-id="7d8bd-110">Splatted 参数值存储在名为展开的变量中，它们看起来像标准变量，但以 in 符号开头 (`@`) ，而不是 () 美元符号 `$` 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-110">Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol (`@`) instead of a dollar sign (`$`).</span></span> <span data-ttu-id="7d8bd-111">At 符号通知 PowerShell 要传递值的集合，而不是传递单个值。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-111">The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.</span></span>

<span data-ttu-id="7d8bd-112">展开使你的命令更简单、更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-112">Splatting makes your commands shorter and easier to read.</span></span> <span data-ttu-id="7d8bd-113">可以在不同的命令调用中重复使用展开值，并使用展开将参数值从 `$PSBoundParameters` 自动变量传递到其他脚本和函数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-113">You can reuse the splatting values in different command calls and use splatting to pass parameter values from the `$PSBoundParameters` automatic variable to other scripts and functions.</span></span>

<span data-ttu-id="7d8bd-114">从 Windows PowerShell 3.0 开始，还可以使用展开来表示命令的所有参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-114">Beginning in Windows PowerShell 3.0, you can also use splatting to represent all parameters of a command.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d8bd-115">语法</span><span class="sxs-lookup"><span data-stu-id="7d8bd-115">Syntax</span></span>

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

<span data-ttu-id="7d8bd-116">若要为位置参数提供参数值（在不需要参数名称的情况下），请使用数组语法。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-116">To provide parameter values for positional parameters, in which parameter names are not required, use the array syntax.</span></span> <span data-ttu-id="7d8bd-117">若要提供参数名称和值对，请使用哈希表语法。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-117">To provide parameter name and value pairs, use the hash table syntax.</span></span> <span data-ttu-id="7d8bd-118">Splatted 值可以出现在参数列表中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-118">The splatted value can appear anywhere in the parameter list.</span></span>

<span data-ttu-id="7d8bd-119">当展开时，无需使用哈希表或数组传递所有参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-119">When splatting, you do not need to use a hash table or an array to pass all parameters.</span></span> <span data-ttu-id="7d8bd-120">可以通过使用展开传递某些参数，并通过位置或参数名称传递其他参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-120">You may pass some parameters by using splatting and pass others by position or by parameter name.</span></span> <span data-ttu-id="7d8bd-121">此外，你可以在单个命令中 splat 多个对象，因此不会为每个参数传递多个值。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-121">Also, you can splat multiple objects in a single command so you don't pass more than one value for each parameter.</span></span>

## <a name="splatting-with-hash-tables"></a><span data-ttu-id="7d8bd-122">具有哈希表的展开</span><span class="sxs-lookup"><span data-stu-id="7d8bd-122">Splatting with hash tables</span></span>

<span data-ttu-id="7d8bd-123">使用哈希表 splat 参数名称和值对。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-123">Use a hash table to splat parameter name and value pairs.</span></span> <span data-ttu-id="7d8bd-124">对于所有参数类型（包括位置参数和开关参数），都可以使用此格式。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-124">You can use this format for all parameter types, including positional and switch parameters.</span></span>
<span data-ttu-id="7d8bd-125">必须按名称指定位置参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-125">Positional parameters must be assigned by name.</span></span>

<span data-ttu-id="7d8bd-126">下面的示例比较两个 `Copy-Item` 命令，它们将 Test.txt 文件复制到相同目录中的 Test2.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-126">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="7d8bd-127">第一个示例使用传统格式，其中包含参数名称。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-127">The first example uses the traditional format in which parameter names are included.</span></span>

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

<span data-ttu-id="7d8bd-128">第二个示例使用哈希表展开。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-128">The second example uses hash table splatting.</span></span> <span data-ttu-id="7d8bd-129">第一个命令创建参数名称和参数值对的哈希表，并将其存储在 `$HashArguments` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-129">The first command creates a hash table of parameter-name and parameter-value pairs and stores it in the `$HashArguments` variable.</span></span> <span data-ttu-id="7d8bd-130">第二个命令使用 `$HashArguments` 展开中的变量。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-130">The second command uses the `$HashArguments` variable in a command with splatting.</span></span> <span data-ttu-id="7d8bd-131">位于符号 (`@HashArguments`) 替换命令中的美元符号 (`$HashArguments`) 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-131">The At symbol (`@HashArguments`) replaces the dollar sign (`$HashArguments`) in the command.</span></span>

<span data-ttu-id="7d8bd-132">若要为 **WhatIf** 开关参数提供一个值，请使用 `$True` 或 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-132">To provide a value for the **WhatIf** switch parameter, use `$True` or `$False`.</span></span>

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> <span data-ttu-id="7d8bd-133">在第一个命令中，At 符号 (`@`) 指示哈希表，而不是 splatted 值。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-133">In the first command, the At symbol (`@`) indicates a hash table, not a splatted value.</span></span> <span data-ttu-id="7d8bd-134">PowerShell 中的哈希表语法为： `@{<name>=<value>; <name>=<value>; ...}`</span><span class="sxs-lookup"><span data-stu-id="7d8bd-134">The syntax for hash tables in PowerShell is: `@{<name>=<value>; <name>=<value>; ...}`</span></span>

## <a name="splatting-with-arrays"></a><span data-ttu-id="7d8bd-135">具有数组的展开</span><span class="sxs-lookup"><span data-stu-id="7d8bd-135">Splatting with arrays</span></span>

<span data-ttu-id="7d8bd-136">使用数组 splat 位置参数的值，不需要参数名称。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-136">Use an array to splat values for positional parameters, which do not require parameter names.</span></span> <span data-ttu-id="7d8bd-137">值必须在数组中的位置号顺序内。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-137">The values must be in position-number order in the array.</span></span>

<span data-ttu-id="7d8bd-138">下面的示例比较两个 `Copy-Item` 命令，它们将 Test.txt 文件复制到相同目录中的 Test2.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-138">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="7d8bd-139">第一个示例使用省略了参数名称的传统格式。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-139">The first example uses the traditional format in which parameter names are omitted.</span></span> <span data-ttu-id="7d8bd-140">参数值按位置顺序出现在命令中。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-140">The parameter values appear in position order in the command.</span></span>

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

<span data-ttu-id="7d8bd-141">第二个示例使用数组展开。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-141">The second example uses array splatting.</span></span> <span data-ttu-id="7d8bd-142">第一个命令创建参数值的数组，并将其存储在 `$ArrayArguments` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-142">The first command creates an array of the parameter values and stores it in the `$ArrayArguments` variable.</span></span> <span data-ttu-id="7d8bd-143">值在数组中的位置顺序。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-143">The values are in position order in the array.</span></span> <span data-ttu-id="7d8bd-144">第二个命令在 `$ArrayArguments` 展开中的命令中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-144">The second command uses the `$ArrayArguments` variable in a command in splatting.</span></span> <span data-ttu-id="7d8bd-145">位于符号 (`@ArrayArguments`) 替换命令中的美元符号 (`$ArrayArguments`) 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-145">The At symbol (`@ArrayArguments`) replaces the dollar sign (`$ArrayArguments`) in the command.</span></span>

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a><span data-ttu-id="7d8bd-146">使用 ArgumentList 参数</span><span class="sxs-lookup"><span data-stu-id="7d8bd-146">Using the ArgumentList parameter</span></span>

<span data-ttu-id="7d8bd-147">多个 cmdlet 具有 **ArgumentList** 参数，该参数用于将参数值传递到 cmdlet 执行的脚本块。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-147">Several cmdlets have an **ArgumentList** parameter that is used to pass parameter values to a script block that is executed by the cmdlet.</span></span> <span data-ttu-id="7d8bd-148">**ArgumentList** 参数采用传递到脚本块的值数组。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-148">The **ArgumentList** parameter takes an array of values that is passed to the script block.</span></span> <span data-ttu-id="7d8bd-149">PowerShell 有效地使用数组展开将值绑定到脚本块的参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-149">PowerShell is effectively using array splatting to bind the values to the parameters of the script block.</span></span> <span data-ttu-id="7d8bd-150">当使用 **ArgumentList** 时，如果需要将一个数组作为绑定到单个参数的单个对象传递，则必须将该数组包装为另一个数组的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-150">When using **ArgumentList** , if you need to pass an array as a single object bound to a single parameter, you must wrap the array as the only element of another array.</span></span>

<span data-ttu-id="7d8bd-151">下面的示例具有一个脚本块，该脚本块采用一个字符串数组的参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-151">The following example has a script block that takes a single parameter that is an array of strings.</span></span>

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```

<span data-ttu-id="7d8bd-152">在此示例中，只将中的第一项 `$array` 传递到脚本块。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-152">In this example, only the first item in `$array` is passed to the script block.</span></span>
```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList (,$array)
```

<span data-ttu-id="7d8bd-153">在此示例中， `$array` 包装在数组中，以便将整个数组作为单个对象传递到脚本块。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-153">In this example, `$array` is wrapped in an array so that the entire array is passed to the script block as a single object.</span></span>

```Output
Hello World!
```

## <a name="examples"></a><span data-ttu-id="7d8bd-154">示例</span><span class="sxs-lookup"><span data-stu-id="7d8bd-154">Examples</span></span>

<span data-ttu-id="7d8bd-155">此示例演示如何在不同的命令中重复使用 splatted 值。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-155">This example shows how to reuse splatted values in different commands.</span></span> <span data-ttu-id="7d8bd-156">此示例中的命令使用 `Write-Host` cmdlet 将消息写入主机程序控制台。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-156">The commands in this example use the `Write-Host` cmdlet to write messages to the host program console.</span></span> <span data-ttu-id="7d8bd-157">它使用展开来指定前景色和背景色。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-157">It uses splatting to specify the foreground and background colors.</span></span>

<span data-ttu-id="7d8bd-158">若要更改所有命令的颜色，只需更改变量的值 `$Colors` 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-158">To change the colors of all commands, just change the value of the `$Colors` variable.</span></span>

<span data-ttu-id="7d8bd-159">第一个命令创建参数名称和值的哈希表，并将该哈希表存储在 `$Colors` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-159">The first command creates a hash table of parameter names and values and stores the hash table in the `$Colors` variable.</span></span>

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

<span data-ttu-id="7d8bd-160">第二个和第三个命令 `$Colors` 在命令中使用展开的变量 `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-160">The second and third commands use the `$Colors` variable for splatting in a `Write-Host` command.</span></span> <span data-ttu-id="7d8bd-161">若要使用 `$Colors variable` ，请将美元符号 (`$Colors`) 替换为符号 (`@Colors`) 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-161">To use the `$Colors variable`, replace the dollar sign (`$Colors`) with an At symbol (`@Colors`).</span></span>

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

<span data-ttu-id="7d8bd-162">此示例显示了如何使用展开和自动变量将其参数转发到其他命令 `$PSBoundParameters` 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-162">This example shows how to forward their parameters to other commands by using splatting and the `$PSBoundParameters` automatic variable.</span></span>

<span data-ttu-id="7d8bd-163">`$PSBoundParameters`自动变量是 () 的字典对象，其中包含运行脚本或函数时使用的所有参数名称和值。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-163">The `$PSBoundParameters` automatic variable is a dictionary object (System.Collections.Generic.Dictionary) that contains all the parameter names and values that are used when a script or function is run.</span></span>

<span data-ttu-id="7d8bd-164">在下面的示例中，我们使用 `$PSBoundParameters` 变量将传递给脚本或函数的参数值转发给 `Test2` `Test1` 函数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-164">In the following example, we use the `$PSBoundParameters` variable to forward the parameters values passed to a script or function from `Test2` function to the `Test1` function.</span></span> <span data-ttu-id="7d8bd-165">对函数的两个调用都 `Test1` `Test2` 使用展开。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-165">Both calls to the `Test1` function from `Test2` use splatting.</span></span>

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

## <a name="splatting-command-parameters"></a><span data-ttu-id="7d8bd-166">展开命令参数</span><span class="sxs-lookup"><span data-stu-id="7d8bd-166">Splatting command parameters</span></span>

<span data-ttu-id="7d8bd-167">可以使用展开来表示命令的参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-167">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="7d8bd-168">当你创建的是一个代理函数（即调用另一个命令的函数）时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-168">This technique is useful when you are creating a proxy function, that is, a function that calls another command.</span></span> <span data-ttu-id="7d8bd-169">此功能是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-169">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="7d8bd-170">若要 splat 命令的参数，请使用 `@Args` 表示命令参数。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-170">To splat the parameters of a command, use `@Args` to represent the command parameters.</span></span> <span data-ttu-id="7d8bd-171">此方法比枚举命令参数更简单，即使调用的命令的参数发生更改，它也无需进行修订。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-171">This technique is easier than enumerating command parameters and it works without revision even if the parameters of the called command change.</span></span>

<span data-ttu-id="7d8bd-172">此功能使用 `$Args` 自动变量，该变量包含所有未分配的参数值。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-172">The feature uses the `$Args` automatic variable, which contains all unassigned parameter values.</span></span>

<span data-ttu-id="7d8bd-173">例如，以下函数调用 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-173">For example, the following function calls the `Get-Process` cmdlet.</span></span> <span data-ttu-id="7d8bd-174">在此函数中， `@Args` 表示 cmdlet 的所有参数 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-174">In this function, `@Args` represents all the parameters of the `Get-Process` cmdlet.</span></span>

```powershell
function Get-MyProcess { Get-Process @Args }
```

<span data-ttu-id="7d8bd-175">使用 `Get-MyProcess` 函数时，所有未分配的参数和参数值将传递到 `@Args` ，如以下命令中所示。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-175">When you use the `Get-MyProcess` function, all unassigned parameters and parameter values are passed to `@Args`, as shown in the following commands.</span></span>

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

<span data-ttu-id="7d8bd-176">可以 `@Args` 在具有显式声明的参数的函数中使用。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-176">You can use `@Args` in a function that has explicitly declared parameters.</span></span> <span data-ttu-id="7d8bd-177">可以在函数中多次使用它，但输入的所有参数都将传递给的所有实例 `@Args` ，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-177">You can use it more than once in a function, but all parameters that you enter are passed to all instances of `@Args`, as shown in the following example.</span></span>

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a><span data-ttu-id="7d8bd-178">注释</span><span class="sxs-lookup"><span data-stu-id="7d8bd-178">Notes</span></span>

<span data-ttu-id="7d8bd-179">如果使用 **CmdletBinding** 或 **参数** 特性使函数进入高级函数，则该 `$args` 函数中的自动变量将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-179">If you make a function into an advanced function by using either the **CmdletBinding** or **Parameter** attributes, the `$args` automatic variable is no longer available in the function.</span></span> <span data-ttu-id="7d8bd-180">高级函数需要显式参数定义。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-180">Advanced functions require explicit parameter definition.</span></span>

<span data-ttu-id="7d8bd-181">PowerShell 所需状态配置 (DSC) 设计为不使用展开。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-181">PowerShell Desired State Configuration (DSC) was not designed to use splatting.</span></span>
<span data-ttu-id="7d8bd-182">不能使用展开将值传递给 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-182">You cannot use splatting to pass values into a DSC resource.</span></span> <span data-ttu-id="7d8bd-183">有关详细信息，请参阅 Gael Colas 文章 [展开 DSC 资源](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/)。</span><span class="sxs-lookup"><span data-stu-id="7d8bd-183">For more information, see Gael Colas' article [Pseudo-Splatting DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d8bd-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d8bd-184">See also</span></span>

[<span data-ttu-id="7d8bd-185">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="7d8bd-185">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="7d8bd-186">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="7d8bd-186">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="7d8bd-187">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="7d8bd-187">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="7d8bd-188">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="7d8bd-188">about_Parameters</span></span>](about_Parameters.md)