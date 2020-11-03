---
description: 说明 PowerShell 中的作用域的概念，并演示如何设置和更改元素的作用域。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 2149a1dec14e4de9c6ff1021e98689ca93307cb8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199584"
---
# <a name="about-scopes"></a><span data-ttu-id="12831-104">关于范围</span><span class="sxs-lookup"><span data-stu-id="12831-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="12831-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="12831-105">Short description</span></span>
<span data-ttu-id="12831-106">说明 PowerShell 中的作用域的概念，并演示如何设置和更改元素的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="12831-107">长说明</span><span class="sxs-lookup"><span data-stu-id="12831-107">Long description</span></span>

<span data-ttu-id="12831-108">PowerShell 通过限制可以读取和更改变量、别名、函数和 PowerShell 驱动器 (PSDrives) ，来保护这些驱动器的访问。</span><span class="sxs-lookup"><span data-stu-id="12831-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="12831-109">PowerShell 使用范围规则确保你不会无意中更改不应更改的项。</span><span class="sxs-lookup"><span data-stu-id="12831-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="12831-110">下面是范围的基本规则：</span><span class="sxs-lookup"><span data-stu-id="12831-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="12831-111">范围可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="12831-111">Scopes may nest.</span></span> <span data-ttu-id="12831-112">外部作用域称为父作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="12831-113">任何嵌套的作用域都是该父级的子作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="12831-114">项目在创建它的作用域和任何子作用域中可见，除非你显式将其设为私有。</span><span class="sxs-lookup"><span data-stu-id="12831-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="12831-115">可以在一个或多个作用域中放置变量、别名、函数或 PowerShell 驱动器。</span><span class="sxs-lookup"><span data-stu-id="12831-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="12831-116">在范围内创建的项只能在创建它的范围内更改，除非显式指定了不同的范围。</span><span class="sxs-lookup"><span data-stu-id="12831-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="12831-117">如果在作用域中创建一个项，并且该项与不同范围内的项共享其名称，则原始项可能会隐藏在新项下，但不会被覆盖或更改。</span><span class="sxs-lookup"><span data-stu-id="12831-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="12831-118">PowerShell 范围</span><span class="sxs-lookup"><span data-stu-id="12831-118">PowerShell Scopes</span></span>

<span data-ttu-id="12831-119">PowerShell 支持以下作用域：</span><span class="sxs-lookup"><span data-stu-id="12831-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="12831-120">全局： PowerShell 启动时生效的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-120">Global: The scope that is in effect when PowerShell starts.</span></span> <span data-ttu-id="12831-121">在全局作用域（例如自动变量和首选项变量）中创建了 PowerShell 启动时出现的变量和函数。</span><span class="sxs-lookup"><span data-stu-id="12831-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="12831-122">PowerShell 配置文件中的变量、别名和函数也是在全局范围内创建的。</span><span class="sxs-lookup"><span data-stu-id="12831-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span>

- <span data-ttu-id="12831-123">Local：当前范围。</span><span class="sxs-lookup"><span data-stu-id="12831-123">Local: The current scope.</span></span> <span data-ttu-id="12831-124">本地作用域可以是全局作用域或任何其他作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-124">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="12831-125">脚本：运行脚本文件时创建的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-125">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="12831-126">只有脚本中的命令在脚本作用域中运行。</span><span class="sxs-lookup"><span data-stu-id="12831-126">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="12831-127">对于脚本中的命令，脚本范围为本地范围。</span><span class="sxs-lookup"><span data-stu-id="12831-127">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="12831-128">**私有** 不是范围。</span><span class="sxs-lookup"><span data-stu-id="12831-128">**Private** is not a scope.</span></span> <span data-ttu-id="12831-129">它是一个 [选项](#private-option) ，它更改项的范围之外的项的可见性。</span><span class="sxs-lookup"><span data-stu-id="12831-129">It is an [option](#private-option) that changes the visibility of an item outside of the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="12831-130">父范围和子范围</span><span class="sxs-lookup"><span data-stu-id="12831-130">Parent and Child Scopes</span></span>

<span data-ttu-id="12831-131">可以通过运行脚本或函数、创建会话或启动 PowerShell 的新实例来创建新的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-131">You can create a new scope by running a script or function, by creating a session, or by starting a new instance of PowerShell.</span></span> <span data-ttu-id="12831-132">创建新作用域时，结果是 (原始作用域) 的父作用域和 () 的作用域中创建的子作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-132">When you create a new scope, the result is a parent scope (the original scope) and a child scope (the scope that you created).</span></span>

<span data-ttu-id="12831-133">在 PowerShell 中，所有作用域都是全局作用域的子作用域，但你可以创建多个作用域和多个递归作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-133">In PowerShell, all scopes are child scopes of the global scope, but you can create many scopes and many recursive scopes.</span></span>

<span data-ttu-id="12831-134">除非显式将项设置为私有，否则父范围中的项可用于子范围。</span><span class="sxs-lookup"><span data-stu-id="12831-134">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="12831-135">但是，在子范围内创建和更改的项不影响父范围，除非你在创建项时显式指定范围。</span><span class="sxs-lookup"><span data-stu-id="12831-135">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

## <a name="inheritance"></a><span data-ttu-id="12831-136">继承</span><span class="sxs-lookup"><span data-stu-id="12831-136">Inheritance</span></span>

<span data-ttu-id="12831-137">子作用域不从父作用域继承变量、别名和函数。</span><span class="sxs-lookup"><span data-stu-id="12831-137">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="12831-138">除非项是私有的，否则子范围可以查看父范围中的项。</span><span class="sxs-lookup"><span data-stu-id="12831-138">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="12831-139">并且，它可以通过显式指定父范围来更改项，但项不是子范围的一部分。</span><span class="sxs-lookup"><span data-stu-id="12831-139">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="12831-140">但是，使用一组项创建子范围。</span><span class="sxs-lookup"><span data-stu-id="12831-140">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="12831-141">通常，它包括具有 **AllScope** 选项的所有别名。</span><span class="sxs-lookup"><span data-stu-id="12831-141">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="12831-142">本文稍后将对此进行讨论。</span><span class="sxs-lookup"><span data-stu-id="12831-142">This option is discussed later in this article.</span></span> <span data-ttu-id="12831-143">它包括具有 **AllScope** 选项的所有变量，以及一些自动变量。</span><span class="sxs-lookup"><span data-stu-id="12831-143">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="12831-144">若要查找特定范围中的项，请使用或的作用域参数 `Get-Variable` `Get-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="12831-144">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="12831-145">例如，若要获取本地范围内的所有变量，请键入：</span><span class="sxs-lookup"><span data-stu-id="12831-145">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="12831-146">若要获取全局范围内的所有变量，请键入：</span><span class="sxs-lookup"><span data-stu-id="12831-146">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="12831-147">作用域修饰符</span><span class="sxs-lookup"><span data-stu-id="12831-147">Scope Modifiers</span></span>

<span data-ttu-id="12831-148">变量、别名或函数名可以包含以下任意一种可选的作用域修饰符：</span><span class="sxs-lookup"><span data-stu-id="12831-148">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="12831-149">`global:` -指定名称存在于 **全局** 范围内。</span><span class="sxs-lookup"><span data-stu-id="12831-149">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="12831-150">`local:` -指定名称存在于 **本地** 作用域中。</span><span class="sxs-lookup"><span data-stu-id="12831-150">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="12831-151">当前范围始终是 **本地** 范围。</span><span class="sxs-lookup"><span data-stu-id="12831-151">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="12831-152">`private:` -指定该名称是 **私有** 的，仅对当前作用域可见。</span><span class="sxs-lookup"><span data-stu-id="12831-152">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="12831-153">`script:` -指定名称存在于 **脚本** 作用域中。</span><span class="sxs-lookup"><span data-stu-id="12831-153">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="12831-154">如果没有最近的上级脚本文件，则 **脚本** 范围是最近的上级脚本文件的范围或 **全局** 。</span><span class="sxs-lookup"><span data-stu-id="12831-154">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="12831-155">`using:` -用于在通过 cmdlet （如和）运行脚本时访问在其他作用域中定义的变量 `Start-Job` `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="12831-155">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="12831-156">`workflow:` -指定名称存在于工作流中。</span><span class="sxs-lookup"><span data-stu-id="12831-156">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="12831-157">注意： PowerShell Core 不支持工作流。</span><span class="sxs-lookup"><span data-stu-id="12831-157">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="12831-158">`<variable-namespace>` -PowerShell New-psdrive 提供程序创建的修饰符。</span><span class="sxs-lookup"><span data-stu-id="12831-158">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="12831-159">例如：</span><span class="sxs-lookup"><span data-stu-id="12831-159">For example:</span></span>

  |  <span data-ttu-id="12831-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="12831-160">Namespace</span></span>  |                    <span data-ttu-id="12831-161">说明</span><span class="sxs-lookup"><span data-stu-id="12831-161">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="12831-162">当前作用域中定义的别名</span><span class="sxs-lookup"><span data-stu-id="12831-162">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="12831-163">在当前作用域中定义的环境变量</span><span class="sxs-lookup"><span data-stu-id="12831-163">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="12831-164">当前作用域中定义的函数</span><span class="sxs-lookup"><span data-stu-id="12831-164">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="12831-165">当前作用域中定义的变量</span><span class="sxs-lookup"><span data-stu-id="12831-165">Variables defined in the current scope</span></span>             |

<span data-ttu-id="12831-166">脚本的默认作用域为脚本范围。</span><span class="sxs-lookup"><span data-stu-id="12831-166">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="12831-167">函数和别名的默认作用域为本地作用域，即使它们是在脚本中定义的也是如此。</span><span class="sxs-lookup"><span data-stu-id="12831-167">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="12831-168">使用作用域修饰符</span><span class="sxs-lookup"><span data-stu-id="12831-168">Using scope modifiers</span></span>

<span data-ttu-id="12831-169">若要指定新变量、别名或函数的作用域，请使用作用域修饰符。</span><span class="sxs-lookup"><span data-stu-id="12831-169">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="12831-170">变量中的作用域修饰符的语法为：</span><span class="sxs-lookup"><span data-stu-id="12831-170">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="12831-171">函数中的作用域修饰符的语法为：</span><span class="sxs-lookup"><span data-stu-id="12831-171">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="12831-172">以下不使用范围修饰符的命令将在当前或 **本地** 范围内创建变量：</span><span class="sxs-lookup"><span data-stu-id="12831-172">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="12831-173">若要在 **全局** 作用域中创建相同的变量，请使用作用域 `global:` 修饰符：</span><span class="sxs-lookup"><span data-stu-id="12831-173">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="12831-174">若要在 **脚本** 作用域中创建相同的变量，请使用 `script:` 作用域修饰符：</span><span class="sxs-lookup"><span data-stu-id="12831-174">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="12831-175">还可以将作用域修饰符用于函数。</span><span class="sxs-lookup"><span data-stu-id="12831-175">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="12831-176">以下函数定义将在 **全局** 范围内创建函数：</span><span class="sxs-lookup"><span data-stu-id="12831-176">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="12831-177">你还可以使用作用域修饰符来引用不同范围中的变量。</span><span class="sxs-lookup"><span data-stu-id="12831-177">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="12831-178">以下命令 `$test` 首先引用本地作用域中的变量，然后在全局范围内引用：</span><span class="sxs-lookup"><span data-stu-id="12831-178">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="12831-179">`Using:`作用域修饰符</span><span class="sxs-lookup"><span data-stu-id="12831-179">The `Using:` scope modifier</span></span>

<span data-ttu-id="12831-180">使用是一个特殊的作用域修饰符，用来标识远程命令中的局部变量。</span><span class="sxs-lookup"><span data-stu-id="12831-180">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="12831-181">如果不使用修饰符，则 PowerShell 应在远程会话中定义远程命令中的变量。</span><span class="sxs-lookup"><span data-stu-id="12831-181">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="12831-182">`Using`PowerShell 3.0 中引入了作用域修饰符。</span><span class="sxs-lookup"><span data-stu-id="12831-182">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="12831-183">对于任何执行进程外的脚本或命令，都需要 `Using` 范围修饰符来嵌入调用会话范围内的变量值，以便使会话代码不能访问它们。</span><span class="sxs-lookup"><span data-stu-id="12831-183">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="12831-184">`Using`以下上下文支持作用域修饰符：</span><span class="sxs-lookup"><span data-stu-id="12831-184">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="12831-185">远程执行的命令，已开始 `Invoke-Command` 使用 **ComputerName** 、 **HostName** 、 **SSHConnection** 或 **Session** 参数 (远程会话) </span><span class="sxs-lookup"><span data-stu-id="12831-185">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="12831-186">后台作业， `Start-Job` (进程外会话开始) </span><span class="sxs-lookup"><span data-stu-id="12831-186">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="12831-187">通过 `Start-ThreadJob` 或 `ForEach-Object -Parallel` (单独的线程会话启动的线程作业) </span><span class="sxs-lookup"><span data-stu-id="12831-187">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="12831-188">根据上下文，嵌入变量值是调用方的作用域中的数据的独立副本或对其的引用。</span><span class="sxs-lookup"><span data-stu-id="12831-188">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="12831-189">在远程和进程外会话中，它们始终是独立的副本。</span><span class="sxs-lookup"><span data-stu-id="12831-189">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="12831-190">有关详细信息，请参阅 [about_Remote_Variables](about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="12831-190">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="12831-191">在线程会话中，它们是通过引用传递的。</span><span class="sxs-lookup"><span data-stu-id="12831-191">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="12831-192">这意味着可以在不同的线程中修改调用范围变量。</span><span class="sxs-lookup"><span data-stu-id="12831-192">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="12831-193">安全修改变量需要线程同步。</span><span class="sxs-lookup"><span data-stu-id="12831-193">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="12831-194">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="12831-194">For more information see:</span></span>

- [<span data-ttu-id="12831-195">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="12831-195">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)
- [<span data-ttu-id="12831-196">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="12831-196">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="12831-197">变量值的序列化</span><span class="sxs-lookup"><span data-stu-id="12831-197">Serialization of variable values</span></span>

<span data-ttu-id="12831-198">远程执行的命令和后台作业在进程外运行。</span><span class="sxs-lookup"><span data-stu-id="12831-198">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="12831-199">进程外会话使用基于 XML 的序列化和反序列化来使变量的值可在进程边界内使用。</span><span class="sxs-lookup"><span data-stu-id="12831-199">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="12831-200">序列化进程将对象转换为包含原始对象属性但不包含其方法的 **PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="12831-200">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="12831-201">对于有限类型的类型，请将解除冻结对象反序列化为原始类型。</span><span class="sxs-lookup"><span data-stu-id="12831-201">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="12831-202">解除冻结对象是原始对象实例的副本。</span><span class="sxs-lookup"><span data-stu-id="12831-202">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="12831-203">它具有类型属性和方法。</span><span class="sxs-lookup"><span data-stu-id="12831-203">It has the type properties and methods.</span></span> <span data-ttu-id="12831-204">对于简单的类型（如 **system.object** ），副本是精确的。</span><span class="sxs-lookup"><span data-stu-id="12831-204">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="12831-205">对于复杂类型，复制为完善。</span><span class="sxs-lookup"><span data-stu-id="12831-205">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="12831-206">例如，解除冻结证书对象不包含私钥。</span><span class="sxs-lookup"><span data-stu-id="12831-206">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="12831-207">所有其他类型的实例都是 **PSObject** 实例。</span><span class="sxs-lookup"><span data-stu-id="12831-207">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="12831-208">**PSTypeNames** 属性包含以 **反序列化** 的原始类型名称，例如 **Deserialized.System。Data DataTable**</span><span class="sxs-lookup"><span data-stu-id="12831-208">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="12831-209">AllScope 选项</span><span class="sxs-lookup"><span data-stu-id="12831-209">The AllScope Option</span></span>

<span data-ttu-id="12831-210">变量和别名有一个 **选项** 属性，该属性的值为 **AllScope** 。</span><span class="sxs-lookup"><span data-stu-id="12831-210">Variables and aliases have an **Option** property that can take a value of **AllScope** .</span></span> <span data-ttu-id="12831-211">具有 **AllScope** 属性的项将成为你创建的任何子范围的一部分，尽管它们不会被父范围继承。</span><span class="sxs-lookup"><span data-stu-id="12831-211">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="12831-212">具有 **AllScope** 属性的项在子范围中是可见的，它是该范围的一部分。</span><span class="sxs-lookup"><span data-stu-id="12831-212">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="12831-213">对任何范围内的项所做的更改都会影响定义该变量的所有范围。</span><span class="sxs-lookup"><span data-stu-id="12831-213">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="12831-214">管理作用域</span><span class="sxs-lookup"><span data-stu-id="12831-214">Managing Scope</span></span>

<span data-ttu-id="12831-215">多个 cmdlet 具有 **作用域** 参数，可让你获取或设置 (创建和更改特定作用域中) 项的功能。</span><span class="sxs-lookup"><span data-stu-id="12831-215">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="12831-216">使用以下命令查找会话中具有 **作用域** 参数的所有 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="12831-216">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="12831-217">若要查找在特定作用域中可见的变量，请使用的 `Scope` 参数 `Get-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="12831-217">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="12831-218">可见变量包括全局变量、父作用域中的变量以及当前作用域中的变量。</span><span class="sxs-lookup"><span data-stu-id="12831-218">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="12831-219">例如，以下命令将获取在本地作用域中可见的变量：</span><span class="sxs-lookup"><span data-stu-id="12831-219">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="12831-220">若要在特定范围内创建变量，请使用的作用域修饰符或 **作用域** 参数 `Set-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="12831-220">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="12831-221">以下命令在全局范围内创建变量：</span><span class="sxs-lookup"><span data-stu-id="12831-221">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="12831-222">你还可以使用、或 cmdlet 的作用域参数 `New-Alias` `Set-Alias` `Get-Alias` 来指定作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-222">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="12831-223">以下命令在全局范围内创建一个别名：</span><span class="sxs-lookup"><span data-stu-id="12831-223">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="12831-224">若要获取特定范围中的函数，请 `Get-Item` 在范围内使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12831-224">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="12831-225">`Get-Item`Cmdlet 没有 **Scope** 参数。</span><span class="sxs-lookup"><span data-stu-id="12831-225">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="12831-226">对于使用 **Scope** 参数的 cmdlet，还可以按编号引用范围。</span><span class="sxs-lookup"><span data-stu-id="12831-226">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="12831-227">该数字描述一个作用域相对于另一个作用域的相对位置。</span><span class="sxs-lookup"><span data-stu-id="12831-227">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="12831-228">范围0表示当前范围或本地范围。</span><span class="sxs-lookup"><span data-stu-id="12831-228">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="12831-229">作用域1指示直接父作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-229">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="12831-230">作用域2指示父作用域的父项，依此类推。</span><span class="sxs-lookup"><span data-stu-id="12831-230">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="12831-231">如果已创建多个递归作用域，编号范围很有用。</span><span class="sxs-lookup"><span data-stu-id="12831-231">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="12831-232">在作用域中使用点源表示法</span><span class="sxs-lookup"><span data-stu-id="12831-232">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="12831-233">脚本和函数遵循作用域的所有规则。</span><span class="sxs-lookup"><span data-stu-id="12831-233">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="12831-234">在特定的范围内创建它们，除非使用 cmdlet 参数或作用域修饰符来更改该作用域，否则它们只会影响该作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-234">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="12831-235">但是，您可以使用点源表示法将脚本或函数添加到当前作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-235">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="12831-236">然后，当脚本在当前作用域中运行时，该脚本创建的任何函数、别名和变量都在当前作用域中可用。</span><span class="sxs-lookup"><span data-stu-id="12831-236">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="12831-237">若要将函数添加到当前作用域，请在函数调用中键入一个句点 (. ) 和该函数的路径和名称之前的空格。</span><span class="sxs-lookup"><span data-stu-id="12831-237">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="12831-238">例如，若要在脚本范围中的 C：\Scripts 目录中运行 Sample.ps1 脚本 (脚本) 的默认值，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="12831-238">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="12831-239">若要在本地作用域中运行 Sample.ps1 脚本，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="12831-239">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="12831-240">使用 call 运算符 ( # A0) 运行函数或脚本时，不会将其添加到当前作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-240">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="12831-241">下面的示例使用调用运算符：</span><span class="sxs-lookup"><span data-stu-id="12831-241">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="12831-242">可以在 [about_operators](about_operators.md)中详细了解 call 运算符。</span><span class="sxs-lookup"><span data-stu-id="12831-242">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="12831-243">Sample.ps1 脚本创建的任何别名、函数或变量在当前作用域中都不可用。</span><span class="sxs-lookup"><span data-stu-id="12831-243">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="12831-244">不带作用域的限制</span><span class="sxs-lookup"><span data-stu-id="12831-244">Restricting Without Scope</span></span>

<span data-ttu-id="12831-245">一些 PowerShell 概念类似于作用域或与作用域交互。</span><span class="sxs-lookup"><span data-stu-id="12831-245">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="12831-246">这些概念可能会与范围或范围的行为混淆。</span><span class="sxs-lookup"><span data-stu-id="12831-246">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="12831-247">会话、模块和嵌套的提示是独立的环境，但是它们不是会话中全局作用域的子作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-247">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="12831-248">会话</span><span class="sxs-lookup"><span data-stu-id="12831-248">Sessions</span></span>

<span data-ttu-id="12831-249">会话是 PowerShell 运行的环境。</span><span class="sxs-lookup"><span data-stu-id="12831-249">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="12831-250">在远程计算机上创建会话时，PowerShell 会建立与远程计算机的持久连接。</span><span class="sxs-lookup"><span data-stu-id="12831-250">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="12831-251">使用持久性连接可以将会话用于多个相关命令。</span><span class="sxs-lookup"><span data-stu-id="12831-251">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="12831-252">由于会话是包含的环境，因此它具有其自己的作用域，但会话不是在其中创建它的会话的子作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-252">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="12831-253">该会话从其自己的全局作用域开始。</span><span class="sxs-lookup"><span data-stu-id="12831-253">The session starts with its own global scope.</span></span> <span data-ttu-id="12831-254">此作用域独立于会话的全局作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-254">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="12831-255">你可以在会话中创建子作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-255">You can create child scopes in the session.</span></span> <span data-ttu-id="12831-256">例如，你可以运行一个脚本以在会话中创建子作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-256">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="12831-257">模块</span><span class="sxs-lookup"><span data-stu-id="12831-257">Modules</span></span>

<span data-ttu-id="12831-258">你可以使用 PowerShell 模块来共享和传递 PowerShell 工具。</span><span class="sxs-lookup"><span data-stu-id="12831-258">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="12831-259">模块是一个可包含 cmdlet、脚本、函数、变量、别名和其他有用项的单位。</span><span class="sxs-lookup"><span data-stu-id="12831-259">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="12831-260">除非显式定义，否则模块中的项在模块外部不可访问。</span><span class="sxs-lookup"><span data-stu-id="12831-260">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="12831-261">因此，可以将该模块添加到会话中，并使用这些公共项，而不必担心其他项可能会覆盖会话中的 cmdlet、脚本、函数和其他项。</span><span class="sxs-lookup"><span data-stu-id="12831-261">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="12831-262">默认情况下，模块将加载到当前 _会话状态_ 的顶层，而不是当前 _作用域_ 。</span><span class="sxs-lookup"><span data-stu-id="12831-262">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_ .</span></span> <span data-ttu-id="12831-263">当前会话状态可以是模块会话状态或全局会话状态。</span><span class="sxs-lookup"><span data-stu-id="12831-263">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="12831-264">向会话添加模块不会更改范围。</span><span class="sxs-lookup"><span data-stu-id="12831-264">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="12831-265">如果在全局范围内，则将模块加载到全局会话状态。</span><span class="sxs-lookup"><span data-stu-id="12831-265">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="12831-266">所有导出都放置在全局表中。</span><span class="sxs-lookup"><span data-stu-id="12831-266">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="12831-267">如果从 module1 _中_ 加载 module2，则 module2 将加载到 module1 的会话状态，而不是全局会话状态。</span><span class="sxs-lookup"><span data-stu-id="12831-267">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="12831-268">Module2 中的任何导出都置于 module1 会话状态的顶部。</span><span class="sxs-lookup"><span data-stu-id="12831-268">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="12831-269">如果使用 `Import-Module -Scope local` ，则会将导出置于当前范围对象而不是顶级。</span><span class="sxs-lookup"><span data-stu-id="12831-269">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="12831-270">如果你 _在模块中_ ，并使用 `Import-Module -Scope global` (或 `Import-Module -Global`) 加载另一个模块，则该模块及其导出将加载到全局会话状态，而不是模块的本地会话状态。</span><span class="sxs-lookup"><span data-stu-id="12831-270">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="12831-271">此功能设计用于编写操作模块的模块。</span><span class="sxs-lookup"><span data-stu-id="12831-271">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="12831-272">**WindowsCompatibility** 模块执行此将代理模块导入全局会话状态。</span><span class="sxs-lookup"><span data-stu-id="12831-272">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="12831-273">在会话状态中，模块具有其自己的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-273">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="12831-274">请考虑以下模块 `C:\temp\mod1.psm1` ：</span><span class="sxs-lookup"><span data-stu-id="12831-274">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="12831-275">现在，我们创建一个全局变量 `$a` ，为其指定一个值，并调用函数 **foo** 。</span><span class="sxs-lookup"><span data-stu-id="12831-275">Now we create a global variable `$a`, give it a value and call the function **foo** .</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="12831-276">模块 `$a` 在模块范围内声明变量，而函数 **foo** 则在这两个作用域中输出该变量的值。</span><span class="sxs-lookup"><span data-stu-id="12831-276">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="12831-277">嵌套提示</span><span class="sxs-lookup"><span data-stu-id="12831-277">Nested Prompts</span></span>

<span data-ttu-id="12831-278">嵌套式提示不具有其自己的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-278">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="12831-279">当您输入嵌套提示符时，嵌套提示符将是环境的子集。</span><span class="sxs-lookup"><span data-stu-id="12831-279">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="12831-280">但仍在本地范围内。</span><span class="sxs-lookup"><span data-stu-id="12831-280">But, you remain within the local scope.</span></span>

<span data-ttu-id="12831-281">脚本具有自己的作用域。</span><span class="sxs-lookup"><span data-stu-id="12831-281">Scripts do have their own scope.</span></span> <span data-ttu-id="12831-282">如果要调试脚本，并在脚本中找到断点，则输入脚本范围。</span><span class="sxs-lookup"><span data-stu-id="12831-282">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="12831-283">Private 选项</span><span class="sxs-lookup"><span data-stu-id="12831-283">Private Option</span></span>

<span data-ttu-id="12831-284">别名和变量具有 **选项** 属性，该属性的值可以是 **Private** 。</span><span class="sxs-lookup"><span data-stu-id="12831-284">Aliases and variables have an **Option** property that can take a value of **Private** .</span></span> <span data-ttu-id="12831-285">具有 **Private** 选项的项可以在创建它们的范围内查看和更改，但无法在该范围外查看或更改它们。</span><span class="sxs-lookup"><span data-stu-id="12831-285">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="12831-286">例如，如果在全局作用域中创建一个具有 private 选项的变量，然后运行脚本，则 `Get-Variable` 该脚本中的命令不显示专用变量。</span><span class="sxs-lookup"><span data-stu-id="12831-286">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="12831-287">在此实例中使用全局作用域修饰符不显示私有变量。</span><span class="sxs-lookup"><span data-stu-id="12831-287">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="12831-288">可以使用 `New-Variable` 、、和 cmdlet 的选项参数 `Set-Variable` `New-Alias` `Set-Alias` 将选项属性的值设置为私有。</span><span class="sxs-lookup"><span data-stu-id="12831-288">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="12831-289">能见度</span><span class="sxs-lookup"><span data-stu-id="12831-289">Visibility</span></span>

<span data-ttu-id="12831-290">变量或别名的 " **可见性** " 属性决定了是否可以在创建容器的容器外查看项。</span><span class="sxs-lookup"><span data-stu-id="12831-290">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="12831-291">容器可以是模块、脚本或管理单元。</span><span class="sxs-lookup"><span data-stu-id="12831-291">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="12831-292">可见性适用于容器的设计方式与 **选项** 属性的 **私有** 值为作用域设计的方式相同。</span><span class="sxs-lookup"><span data-stu-id="12831-292">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="12831-293">**Visibility** 属性采用 **公共** 值和 **私有** 值。</span><span class="sxs-lookup"><span data-stu-id="12831-293">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="12831-294">只有在创建了私有可见性的项的容器中才能查看和更改这些项。</span><span class="sxs-lookup"><span data-stu-id="12831-294">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="12831-295">如果已添加或导入容器，则无法查看或更改具有私有可见性的项。</span><span class="sxs-lookup"><span data-stu-id="12831-295">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="12831-296">由于可见性是为容器设计的，因此它在作用域中的工作方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="12831-296">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="12831-297">如果创建的项在全局范围内具有私有可见性，则无法查看或更改任何范围中的项。</span><span class="sxs-lookup"><span data-stu-id="12831-297">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="12831-298">如果尝试查看或更改具有私有可见性的变量的值，则 PowerShell 将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="12831-298">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="12831-299">您可以使用 `New-Variable` 和 `Set-Variable` cmdlet 来创建具有私有可见性的变量。</span><span class="sxs-lookup"><span data-stu-id="12831-299">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="12831-300">示例</span><span class="sxs-lookup"><span data-stu-id="12831-300">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="12831-301">示例1：仅在脚本中更改变量值</span><span class="sxs-lookup"><span data-stu-id="12831-301">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="12831-302">以下命令更改 `$ConfirmPreference` 脚本中变量的值。</span><span class="sxs-lookup"><span data-stu-id="12831-302">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="12831-303">此更改不会影响全局范围。</span><span class="sxs-lookup"><span data-stu-id="12831-303">The change does not affect the global scope.</span></span>

<span data-ttu-id="12831-304">首先，若要 `$ConfirmPreference` 在本地范围中显示变量的值，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="12831-304">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="12831-305">创建包含以下命令的 Scope.ps1 脚本：</span><span class="sxs-lookup"><span data-stu-id="12831-305">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="12831-306">运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="12831-306">Run the script.</span></span> <span data-ttu-id="12831-307">此脚本将更改变量的值 `$ConfirmPreference` ，然后在脚本作用域中报告其值。</span><span class="sxs-lookup"><span data-stu-id="12831-307">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="12831-308">输出应类似于以下输出：</span><span class="sxs-lookup"><span data-stu-id="12831-308">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="12831-309">接下来，测试 `$ConfirmPreference` 当前作用域中的变量的当前值。</span><span class="sxs-lookup"><span data-stu-id="12831-309">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="12831-310">此示例说明对脚本作用域中变量的值所做的更改不会影响父作用域中的变量值。</span><span class="sxs-lookup"><span data-stu-id="12831-310">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="12831-311">示例2：查看不同范围中的变量值</span><span class="sxs-lookup"><span data-stu-id="12831-311">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="12831-312">您可以使用作用域修饰符来查看本地范围和父范围中的变量的值。</span><span class="sxs-lookup"><span data-stu-id="12831-312">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="12831-313">首先， `$test` 在全局范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="12831-313">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="12831-314">接下来，创建一个定义变量的 Sample.ps1 脚本 `$test` 。</span><span class="sxs-lookup"><span data-stu-id="12831-314">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="12831-315">在脚本中，使用范围修饰符来引用变量的全局或局部版本 `$test` 。</span><span class="sxs-lookup"><span data-stu-id="12831-315">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="12831-316">在 Sample.ps1 中：</span><span class="sxs-lookup"><span data-stu-id="12831-316">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="12831-317">运行 Sample.ps1 时，输出应类似于以下输出：</span><span class="sxs-lookup"><span data-stu-id="12831-317">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="12831-318">当脚本完成时，只有的全局值 `$test` 在会话中定义。</span><span class="sxs-lookup"><span data-stu-id="12831-318">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="12831-319">示例3：更改父作用域中的变量的值</span><span class="sxs-lookup"><span data-stu-id="12831-319">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="12831-320">除非使用 Private 选项或其他方法保护项，否则可以在父范围中查看和更改变量的值。</span><span class="sxs-lookup"><span data-stu-id="12831-320">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="12831-321">首先， `$test` 在全局范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="12831-321">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="12831-322">接下来，创建一个定义变量的 Sample.ps1 脚本 `$test` 。</span><span class="sxs-lookup"><span data-stu-id="12831-322">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="12831-323">在脚本中，使用范围修饰符来引用变量的全局或局部版本 `$test` 。</span><span class="sxs-lookup"><span data-stu-id="12831-323">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="12831-324">在 Sample.ps1 中：</span><span class="sxs-lookup"><span data-stu-id="12831-324">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="12831-325">脚本完成后，的全局值 `$test` 将更改。</span><span class="sxs-lookup"><span data-stu-id="12831-325">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="12831-326">示例4：创建私有变量</span><span class="sxs-lookup"><span data-stu-id="12831-326">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="12831-327">私有变量是具有值为 *private* 的 **选项** 属性的变量。</span><span class="sxs-lookup"><span data-stu-id="12831-327">A private variable is a variable that has an **Option** property that has a value of *Private* .</span></span> <span data-ttu-id="12831-328">*私有* 变量由子作用域继承，但只能在创建它们的作用域中查看或更改它们。</span><span class="sxs-lookup"><span data-stu-id="12831-328">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="12831-329">下面的命令创建一个 `$ptest` 在本地范围中调用的私有变量。</span><span class="sxs-lookup"><span data-stu-id="12831-329">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="12831-330">您可以 `$ptest` 在本地范围中显示和更改的值。</span><span class="sxs-lookup"><span data-stu-id="12831-330">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="12831-331">接下来，创建一个包含以下命令的 Sample.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="12831-331">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="12831-332">命令尝试显示并更改的值 `$ptest` 。</span><span class="sxs-lookup"><span data-stu-id="12831-332">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="12831-333">在 Sample.ps1 中：</span><span class="sxs-lookup"><span data-stu-id="12831-333">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="12831-334">`$ptest`变量在脚本作用域中不可见，输出为空。</span><span class="sxs-lookup"><span data-stu-id="12831-334">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="12831-335">示例5：使用远程命令中的局部变量</span><span class="sxs-lookup"><span data-stu-id="12831-335">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="12831-336">对于在本地会话中创建的远程命令中的变量，请使用 `Using` 作用域修饰符。</span><span class="sxs-lookup"><span data-stu-id="12831-336">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="12831-337">PowerShell 假设远程会话中创建了远程命令中的变量。</span><span class="sxs-lookup"><span data-stu-id="12831-337">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="12831-338">语法为：</span><span class="sxs-lookup"><span data-stu-id="12831-338">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="12831-339">例如，以下命令在 `$Cred` 本地会话中创建一个变量，然后 `$Cred` 在远程命令中使用该变量：</span><span class="sxs-lookup"><span data-stu-id="12831-339">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="12831-340">使用范围是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="12831-340">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="12831-341">在 PowerShell 2.0 中，若要指示在本地会话中创建了变量，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="12831-341">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="12831-342">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12831-342">See also</span></span>

[<span data-ttu-id="12831-343">about_Variables</span><span class="sxs-lookup"><span data-stu-id="12831-343">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="12831-344">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="12831-344">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="12831-345">about_Functions</span><span class="sxs-lookup"><span data-stu-id="12831-345">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="12831-346">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="12831-346">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="12831-347">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="12831-347">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)
