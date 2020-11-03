---
description: 自定义 PowerShell 行为的变量。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 6f23e016131901ed78b223a4d23dfa12416d970b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199773"
---
# <a name="about-preference-variables"></a><span data-ttu-id="ec87d-104">关于首选项变量</span><span class="sxs-lookup"><span data-stu-id="ec87d-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="ec87d-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ec87d-105">Short description</span></span>

<span data-ttu-id="ec87d-106">自定义 PowerShell 行为的变量。</span><span class="sxs-lookup"><span data-stu-id="ec87d-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ec87d-107">长说明</span><span class="sxs-lookup"><span data-stu-id="ec87d-107">Long description</span></span>

<span data-ttu-id="ec87d-108">PowerShell 包含一组变量，使你能够自定义其行为。</span><span class="sxs-lookup"><span data-stu-id="ec87d-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="ec87d-109">这些首选项变量的工作方式类似于基于 GUI 的系统中的选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="ec87d-110">首选项变量将影响 PowerShell 操作环境以及在环境中运行的所有命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="ec87d-111">在许多情况下，cmdlet 具有可用于覆盖特定命令的首选项行为的参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="ec87d-112">下表列出了首选项变量及其默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="ec87d-113">变量</span><span class="sxs-lookup"><span data-stu-id="ec87d-113">Variable</span></span>             |       <span data-ttu-id="ec87d-114">默认值</span><span class="sxs-lookup"><span data-stu-id="ec87d-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="ec87d-115">高</span><span class="sxs-lookup"><span data-stu-id="ec87d-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="ec87d-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="ec87d-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="ec87d-117">继续</span><span class="sxs-lookup"><span data-stu-id="ec87d-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="ec87d-118">NormalView</span><span class="sxs-lookup"><span data-stu-id="ec87d-118">NormalView</span></span>                |
| `$FormatEnumerationLimit`        | <span data-ttu-id="ec87d-119">4</span><span class="sxs-lookup"><span data-stu-id="ec87d-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="ec87d-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="ec87d-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="ec87d-121">错误 (未记录) </span><span class="sxs-lookup"><span data-stu-id="ec87d-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="ec87d-122">错误 (未记录) </span><span class="sxs-lookup"><span data-stu-id="ec87d-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="ec87d-123"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="ec87d-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="ec87d-124"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="ec87d-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="ec87d-125"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="ec87d-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="ec87d-126"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="ec87d-126">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="ec87d-127">4096</span><span class="sxs-lookup"><span data-stu-id="ec87d-127">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="ec87d-128"> (空格字符 (`" "`) # A3</span><span class="sxs-lookup"><span data-stu-id="ec87d-128">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="ec87d-129">**UTF8Encoding** 对象</span><span class="sxs-lookup"><span data-stu-id="ec87d-129">**UTF8Encoding** object</span></span>   |
| `$ProgressPreference`            | <span data-ttu-id="ec87d-130">继续</span><span class="sxs-lookup"><span data-stu-id="ec87d-130">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="ec87d-131"> (无-) 哈希表</span><span class="sxs-lookup"><span data-stu-id="ec87d-131">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="ec87d-132">（无）</span><span class="sxs-lookup"><span data-stu-id="ec87d-132">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="ec87d-133">全部</span><span class="sxs-lookup"><span data-stu-id="ec87d-133">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="ec87d-134">wsman</span><span class="sxs-lookup"><span data-stu-id="ec87d-134">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="ec87d-135">请参阅 [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="ec87d-135">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="ec87d-136">（无）</span><span class="sxs-lookup"><span data-stu-id="ec87d-136">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="ec87d-137">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="ec87d-137">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="ec87d-138">继续</span><span class="sxs-lookup"><span data-stu-id="ec87d-138">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="ec87d-139">False</span><span class="sxs-lookup"><span data-stu-id="ec87d-139">False</span></span>                     |

<span data-ttu-id="ec87d-140">PowerShell 包括存储用户首选项的以下环境变量。</span><span class="sxs-lookup"><span data-stu-id="ec87d-140">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="ec87d-141">有关这些环境变量的详细信息，请参阅 [about_Environment_Variables](about_Environment_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-141">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="ec87d-142">首选项变量的更改仅对脚本和函数有效，前提是这些脚本或函数是在使用首选项的作用域中定义的。</span><span class="sxs-lookup"><span data-stu-id="ec87d-142">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="ec87d-143">有关详细信息，请参阅 [about_Scopes](about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-143">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="ec87d-144">使用首选项变量</span><span class="sxs-lookup"><span data-stu-id="ec87d-144">Working with preference variables</span></span>

<span data-ttu-id="ec87d-145">本文档介绍每个首选项变量。</span><span class="sxs-lookup"><span data-stu-id="ec87d-145">This document describes each of the preference variables.</span></span>

<span data-ttu-id="ec87d-146">若要显示特定首选项变量的当前值，请键入该变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ec87d-146">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="ec87d-147">例如，下面的命令显示 `$ConfirmPreference` 变量的值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-147">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="ec87d-148">若要更改变量的值，请使用赋值语句。</span><span class="sxs-lookup"><span data-stu-id="ec87d-148">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="ec87d-149">例如，下面的语句将 `$ConfirmPreference` 参数的值更改为 " **中** "。</span><span class="sxs-lookup"><span data-stu-id="ec87d-149">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium** .</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="ec87d-150">您设置的值特定于当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="ec87d-150">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="ec87d-151">若要使变量在所有 PowerShell 会话中生效，请将它们添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ec87d-151">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="ec87d-152">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-152">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="ec87d-153">远程工作</span><span class="sxs-lookup"><span data-stu-id="ec87d-153">Working remotely</span></span>

<span data-ttu-id="ec87d-154">在远程计算机上运行命令时，远程命令仅服从远程计算机的 PowerShell 客户端中的首选项设置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-154">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="ec87d-155">例如，当你运行远程命令时，远程计算机的变量的值将 `$DebugPreference` 决定 PowerShell 对调试消息的响应方式。</span><span class="sxs-lookup"><span data-stu-id="ec87d-155">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="ec87d-156">有关远程命令的详细信息，请参阅 [about_Remote](about_Remote.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-156">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="ec87d-157">\$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-157">\$ConfirmPreference</span></span>

<span data-ttu-id="ec87d-158">确定在运行 cmdlet 或函数之前 PowerShell 是否自动提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-158">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="ec87d-159">`$ConfirmPreference`变量的有效值为 " **高** "、" **中** " 或 " **低** "。</span><span class="sxs-lookup"><span data-stu-id="ec87d-159">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low** .</span></span> <span data-ttu-id="ec87d-160">为 cmdlet 和函数分配了 **高** 、 **中** 或 **低** 的风险。</span><span class="sxs-lookup"><span data-stu-id="ec87d-160">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low** .</span></span> <span data-ttu-id="ec87d-161">当变量的值 `$ConfirmPreference` 小于或等于分配给 cmdlet 或函数的风险时，PowerShell 会在运行 cmdlet 或函数之前自动提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-161">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="ec87d-162">如果该变量的值 `$ConfirmPreference` 为 " **无** "，则在运行 cmdlet 或函数之前，PowerShell 从不会自动提示您。</span><span class="sxs-lookup"><span data-stu-id="ec87d-162">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="ec87d-163">若要更改会话中所有 cmdlet 和函数的确认行为，请更改 `$ConfirmPreference` 变量的值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-163">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="ec87d-164">若要为 `$ConfirmPreference` 单个命令重写，请使用 cmdlet 或函数的 **Confirm** 参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-164">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="ec87d-165">若要请求确认，请使用 `-Confirm` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-165">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="ec87d-166">若要取消确认，请使用 `-Confirm:$false` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-166">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="ec87d-167">有效值为 `$ConfirmPreference` ：</span><span class="sxs-lookup"><span data-stu-id="ec87d-167">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="ec87d-168">**无** ：不自动提示 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ec87d-168">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="ec87d-169">若要请求确认特定命令，请使用 cmdlet 或函数的 **Confirm** 参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-169">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="ec87d-170">**低** ：在运行具有低、中或高风险的 cmdlet 或函数之前，PowerShell 会提示进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-170">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="ec87d-171">**中** ： PowerShell 在运行 cmdlet 之前提示进行确认，或使用中等或高风险运行这些功能。</span><span class="sxs-lookup"><span data-stu-id="ec87d-171">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="ec87d-172">**高** ： PowerShell 在运行 cmdlet 或具有高风险的功能之前提示确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-172">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="ec87d-173">详细说明</span><span class="sxs-lookup"><span data-stu-id="ec87d-173">Detailed explanation</span></span>

<span data-ttu-id="ec87d-174">PowerShell 可以在执行操作之前自动提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-174">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="ec87d-175">例如，当 cmdlet 或函数严重影响系统以删除数据或使用大量系统资源时。</span><span class="sxs-lookup"><span data-stu-id="ec87d-175">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="ec87d-176">风险的估计值是指作为其 **ConfirmImpact** 的 cmdlet 或函数的属性。</span><span class="sxs-lookup"><span data-stu-id="ec87d-176">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact** .</span></span> <span data-ttu-id="ec87d-177">用户无法更改它。</span><span class="sxs-lookup"><span data-stu-id="ec87d-177">Users can't change it.</span></span>

<span data-ttu-id="ec87d-178">可能会给系统带来风险的 cmdlet 和函数具有 **Confirm** 参数，可用于请求或取消对单个命令的确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-178">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="ec87d-179">由于大多数 cmdlet 和函数使用 **默认的风险** 值 **ConfirmImpact** ，而默认值为 "高"，因此 `$ConfirmPreference` 很 **High** 少发生自动确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-179">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="ec87d-180">但是，可以通过将的值更改为 "中" `$ConfirmPreference` 或 **Medium** " **低** " 来激活自动确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-180">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low** .</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-181">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-181">Examples</span></span>

<span data-ttu-id="ec87d-182">此示例显示 `$ConfirmPreference` 变量的默认值（ **高** ）的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-182">This example shows the effect of the `$ConfirmPreference` variable's default value, **High** .</span></span> <span data-ttu-id="ec87d-183">**高** 值仅用于确认高风险 cmdlet 和函数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-183">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="ec87d-184">由于大多数 cmdlet 和函数都是中等风险，因此它们不会自动确认并 `Remove-Item` 删除文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-184">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="ec87d-185">添加 `-Confirm` 到命令会提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-185">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="ec87d-186">使用 `-Confirm` 请求确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-186">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

<span data-ttu-id="ec87d-187">下面的示例演示了将的值更改为 " `$ConfirmPreference` **中** " 的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-187">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium** .</span></span> <span data-ttu-id="ec87d-188">由于大多数 cmdlet 和函数都是中等风险，因此它们会自动得到确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-188">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="ec87d-189">若要禁止显示单个命令的确认提示，请使用值为的 **Confirm** 参数 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-189">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="ec87d-190">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-190">\$DebugPreference</span></span>

<span data-ttu-id="ec87d-191">确定 PowerShell 如何响应脚本、cmdlet 或提供程序所生成的消息，或 `Write-Debug` 命令行中的命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-191">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="ec87d-192">某些 cmdlet 显示调试消息，这些消息通常是为程序员和技术支持专业人员设计的技术消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-192">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="ec87d-193">默认情况下，调试消息不会显示，但你可以通过更改的值来显示调试消息 `$DebugPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-193">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="ec87d-194">可以使用 cmdlet 的 **Debug** 通用参数来显示或隐藏特定命令的调试消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-194">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="ec87d-195">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-195">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="ec87d-196">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-196">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-197">**停止** ：显示调试消息，并停止执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-197">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="ec87d-198">向控制台写入错误。</span><span class="sxs-lookup"><span data-stu-id="ec87d-198">Writes an error to the console.</span></span>
- <span data-ttu-id="ec87d-199">**Inquire** ：显示调试消息，并询问您是否要继续。</span><span class="sxs-lookup"><span data-stu-id="ec87d-199">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="ec87d-200">将 **Debug** common 参数添加到命令时，在将该命令配置为生成调试消息时，将更改该变量的值 `$DebugPreference` 以进行 **查询** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-200">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire** .</span></span>
- <span data-ttu-id="ec87d-201">**继续** ：显示调试消息，并继续执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-201">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="ec87d-202">**SilentlyContinue** ： (默认值) 不起作用。</span><span class="sxs-lookup"><span data-stu-id="ec87d-202">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="ec87d-203">调试消息不会显示，执行将继续进行而不中断。</span><span class="sxs-lookup"><span data-stu-id="ec87d-203">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-204">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-204">Examples</span></span>

<span data-ttu-id="ec87d-205">下面的示例演示在 `$DebugPreference` 命令行中输入命令时更改值的影响 `Write-Debug` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-205">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="ec87d-206">更改会影响所有调试消息，包括 cmdlet 和脚本生成的消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-206">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="ec87d-207">示例显示了 **Debug** 参数，该参数显示或隐藏与单个命令相关的调试消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-207">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="ec87d-208">此示例显示 `$DebugPreference` 变量的默认值 **SilentlyContinue** 的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-208">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue** .</span></span> <span data-ttu-id="ec87d-209">默认情况下， `Write-Debug` cmdlet 的调试消息不会显示并且处理将继续进行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-209">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="ec87d-210">使用 **Debug** 参数时，它将覆盖单个命令的首选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-210">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="ec87d-211">将显示调试消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-211">The debug message is displayed.</span></span>

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="ec87d-212">此示例显示了 `$DebugPreference` 具有 **Continue** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-212">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="ec87d-213">调试消息随即显示，命令继续处理。</span><span class="sxs-lookup"><span data-stu-id="ec87d-213">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="ec87d-214">此示例使用 **Debug** 参数，其中的值 `$false` 为，以禁止将消息用于单个命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-214">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="ec87d-215">不显示调试消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-215">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="ec87d-216">此示例显示 `$DebugPreference` 设置为 " **停止** " 值的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-216">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="ec87d-217">将显示调试消息，并停止该命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-217">The debug message is displayed and the command is stopped.</span></span>

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

<span data-ttu-id="ec87d-218">此示例使用 **Debug** 参数，其中的值 `$false` 为，以禁止将消息用于单个命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-218">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="ec87d-219">调试消息不会显示并且不会停止处理。</span><span class="sxs-lookup"><span data-stu-id="ec87d-219">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="ec87d-220">此示例显示了 `$DebugPreference` 设置为 **查询** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-220">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="ec87d-221">将显示调试消息，并提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-221">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="ec87d-222">此示例使用 **Debug** 参数，其中的值 `$false` 为，以禁止将消息用于单个命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-222">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="ec87d-223">调试消息不会显示并继续处理。</span><span class="sxs-lookup"><span data-stu-id="ec87d-223">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="ec87d-224">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-224">\$ErrorActionPreference</span></span>

<span data-ttu-id="ec87d-225">确定 PowerShell 如何响应非终止错误，该错误不会停止 cmdlet 处理。</span><span class="sxs-lookup"><span data-stu-id="ec87d-225">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="ec87d-226">例如，在命令行或脚本、cmdlet 或提供程序中，如 cmdlet 生成的错误 `Write-Error` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-226">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="ec87d-227">可以使用 cmdlet 的 **ErrorAction** 通用参数来覆盖特定命令的首选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-227">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="ec87d-228">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-228">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-229">**继续** ： (默认值) 显示错误消息并继续执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-229">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="ec87d-230">**Ignore** ：禁止显示错误消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-230">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="ec87d-231">**Ignore** 值专用于按命令使用，而不是用作保存的首选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-231">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="ec87d-232">**Ignore** 不是变量的有效值 `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-232">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="ec87d-233">**Inquire** ：显示错误消息，并询问您是否要继续。</span><span class="sxs-lookup"><span data-stu-id="ec87d-233">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="ec87d-234">**SilentlyContinue** ：不起作用。</span><span class="sxs-lookup"><span data-stu-id="ec87d-234">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="ec87d-235">错误消息不会显示，执行将继续进行而不中断。</span><span class="sxs-lookup"><span data-stu-id="ec87d-235">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="ec87d-236">**停止** ：显示错误消息并停止执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-236">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="ec87d-237">除生成的错误外， **停止** 值还会将 ActionPreferenceStopException 对象生成到错误流。</span><span class="sxs-lookup"><span data-stu-id="ec87d-237">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="ec87d-238">流 (stream)</span><span class="sxs-lookup"><span data-stu-id="ec87d-238">stream</span></span>
- <span data-ttu-id="ec87d-239">**挂起** ：自动挂起工作流作业以便进一步进行调查。</span><span class="sxs-lookup"><span data-stu-id="ec87d-239">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="ec87d-240">调查后，工作流可以恢复。</span><span class="sxs-lookup"><span data-stu-id="ec87d-240">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="ec87d-241">" **挂起** " 值适用于按命令使用，而不是用作保存的首选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-241">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="ec87d-242">**挂起** 不是变量的有效值 `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-242">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="ec87d-243">`$ErrorActionPreference`**ErrorAction** 参数不会影响 PowerShell 响应终止处理停止 cmdlet 的错误的方式。</span><span class="sxs-lookup"><span data-stu-id="ec87d-243">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="ec87d-244">有关 **ErrorAction** 通用参数的详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-244">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-245">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-245">Examples</span></span>

<span data-ttu-id="ec87d-246">这些示例显示变量的不同值的影响 `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-246">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="ec87d-247">**ErrorAction** 参数用于重写 `$ErrorActionPreference` 值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-247">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="ec87d-248">此示例显示 `$ErrorActionPreference` 默认值 " **Continue** "。</span><span class="sxs-lookup"><span data-stu-id="ec87d-248">This example shows the `$ErrorActionPreference` default value, **Continue** .</span></span> <span data-ttu-id="ec87d-249">生成非终止错误。</span><span class="sxs-lookup"><span data-stu-id="ec87d-249">A non-terminating error is generated.</span></span> <span data-ttu-id="ec87d-250">消息随即显示并且处理继续。</span><span class="sxs-lookup"><span data-stu-id="ec87d-250">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error -Message  'Test Error' ; Write-Host 'Hello World' : Test Error
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

Hello World
```

<span data-ttu-id="ec87d-251">此示例显示 `$ErrorActionPreference` 默认值 **Inquire** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-251">This example shows the `$ErrorActionPreference` default value, **Inquire** .</span></span> <span data-ttu-id="ec87d-252">将生成一个错误，并显示一个操作提示。</span><span class="sxs-lookup"><span data-stu-id="ec87d-252">An error is generated and a prompt for action is shown.</span></span>

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="ec87d-253">此示例显示 `$ErrorActionPreference` 设置为 **SilentlyContinue** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-253">This example shows the `$ErrorActionPreference` set to **SilentlyContinue** .</span></span>
<span data-ttu-id="ec87d-254">错误消息将被取消。</span><span class="sxs-lookup"><span data-stu-id="ec87d-254">The error message is suppressed.</span></span>

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

<span data-ttu-id="ec87d-255">此示例显示 `$ErrorActionPreference` 设置为 " **停止** "。</span><span class="sxs-lookup"><span data-stu-id="ec87d-255">This example shows the `$ErrorActionPreference` set to **Stop** .</span></span> <span data-ttu-id="ec87d-256">它还显示生成到变量的额外对象 `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-256">It also shows the extra object generated to the `$Error` variable.</span></span>

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

The running command stopped because the preference variable "ErrorActionPreference"
or common parameter is set to Stop: Test Error

Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

### <a name="errorview"></a><span data-ttu-id="ec87d-257">\$ErrorView</span><span class="sxs-lookup"><span data-stu-id="ec87d-257">\$ErrorView</span></span>

<span data-ttu-id="ec87d-258">确定 PowerShell 中错误消息的显示格式。</span><span class="sxs-lookup"><span data-stu-id="ec87d-258">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="ec87d-259">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-259">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-260">**NormalView** ： (默认) 为大多数用户设计的详细视图。</span><span class="sxs-lookup"><span data-stu-id="ec87d-260">**NormalView** : (Default) A detailed view designed for most users.</span></span> <span data-ttu-id="ec87d-261">包含错误说明和错误中涉及的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="ec87d-261">Consists of a description of the error and the name of the object involved in the error.</span></span>
- <span data-ttu-id="ec87d-262">**CategoryView** ：一种简洁的结构化视图，适用于生产环境。</span><span class="sxs-lookup"><span data-stu-id="ec87d-262">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="ec87d-263">其格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="ec87d-263">The format is as follows:</span></span>

  <span data-ttu-id="ec87d-264">{Category}： ( {TargetName}： {TargetType} ) ： [{Activity}]，{Reason}</span><span class="sxs-lookup"><span data-stu-id="ec87d-264">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="ec87d-265">有关 **CategoryView** 中的字段的详细信息，请参阅 [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) 类。</span><span class="sxs-lookup"><span data-stu-id="ec87d-265">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-266">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-266">Examples</span></span>

<span data-ttu-id="ec87d-267">此示例演示当的值 `$ErrorView` 为默认值 **NormalView** 时，如何显示错误。</span><span class="sxs-lookup"><span data-stu-id="ec87d-267">This example shows how an error appears when the value of `$ErrorView` is the default, **NormalView** .</span></span> <span data-ttu-id="ec87d-268">`Get-ChildItem` 用于查找不存在的文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-268">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="ec87d-269">此示例演示当的值 `$ErrorView` 更改为 **CategoryView** 时出现的相同错误。</span><span class="sxs-lookup"><span data-stu-id="ec87d-269">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView** .</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="ec87d-270">此示例演示的值 `$ErrorView` 仅影响错误显示。</span><span class="sxs-lookup"><span data-stu-id="ec87d-270">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="ec87d-271">它不会更改自动变量中存储的错误对象的结构 `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-271">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="ec87d-272">有关 `$Error` 自动变量的信息，请参阅 [about_automatic_variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-272">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="ec87d-273">下面的命令使用与错误数组中的最新错误（ **元素 0** ）关联的 **ErrorRecord** 对象，并在列表中设置所有错误对象属性的格式。</span><span class="sxs-lookup"><span data-stu-id="ec87d-273">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a><span data-ttu-id="ec87d-274">\$FormatEnumerationLimit</span><span class="sxs-lookup"><span data-stu-id="ec87d-274">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="ec87d-275">确定显示中包含多少个枚举项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-275">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="ec87d-276">此变量不影响基础对象，仅影响显示。</span><span class="sxs-lookup"><span data-stu-id="ec87d-276">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="ec87d-277">如果的值 `$FormatEnumerationLimit` 小于枚举项的数目，则 PowerShell 会添加一个省略号 (`...`) 以指示未显示的项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-277">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="ec87d-278">**有效值** ：整数 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="ec87d-278">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="ec87d-279">**默认值** ：4</span><span class="sxs-lookup"><span data-stu-id="ec87d-279">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-280">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-280">Examples</span></span>

<span data-ttu-id="ec87d-281">此示例演示如何使用 `$FormatEnumerationLimit` 变量来改善枚举项的显示。</span><span class="sxs-lookup"><span data-stu-id="ec87d-281">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="ec87d-282">此示例中的命令将生成一个表，该表列出了在计算机上运行的所有服务，一个用于 **运行** 服务，另一个用于 **已停止** 的服务。</span><span class="sxs-lookup"><span data-stu-id="ec87d-282">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="ec87d-283">它使用 `Get-Service` 命令获取所有服务，然后将结果通过管道发送到 `Group-Object` cmdlet，后者按服务状态对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="ec87d-283">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="ec87d-284">结果是一个表，其中列出了 " **名称** " 列中的状态和 " **组** " 列中的进程。</span><span class="sxs-lookup"><span data-stu-id="ec87d-284">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="ec87d-285">若要更改列标签，请使用哈希表，请参阅 [about_Hash_Tables](about_Hash_Tables.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-285">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="ec87d-286">有关详细信息，请参阅 [格式表](xref:Microsoft.PowerShell.Utility.Format-Table)中的示例。</span><span class="sxs-lookup"><span data-stu-id="ec87d-286">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="ec87d-287">查找的当前值 `$FormatEnumerationLimit` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-287">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="ec87d-288">列出按 **状态** 分组的所有服务。</span><span class="sxs-lookup"><span data-stu-id="ec87d-288">List all services grouped by **Status** .</span></span> <span data-ttu-id="ec87d-289">每个状态的 " **组** " 列中最多列出了四个服务，因为 `$FormatEnumerationLimit` 值为 **4** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-289">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4** .</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="ec87d-290">若要增加列出的项数，请将的值增加 `$FormatEnumerationLimit` 到 **1000** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-290">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000** .</span></span> <span data-ttu-id="ec87d-291">使用 `Get-Service` 和 `Group-Object` 显示服务。</span><span class="sxs-lookup"><span data-stu-id="ec87d-291">Use `Get-Service` and `Group-Object` to display the services.</span></span>

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

<span data-ttu-id="ec87d-292">`Format-Table`与 **Wrap** 参数一起使用以显示服务列表。</span><span class="sxs-lookup"><span data-stu-id="ec87d-292">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a><span data-ttu-id="ec87d-293">\$InformationPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-293">\$InformationPreference</span></span>

<span data-ttu-id="ec87d-294">`$InformationPreference`利用变量，可以设置要向用户显示的信息流首选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-294">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="ec87d-295">具体而言，是通过添加 [写入信息](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet 添加到命令或脚本的信息性消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-295">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="ec87d-296">如果使用 **InformationAction** 参数，则其值将覆盖变量的值 `$InformationPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-296">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="ec87d-297">`Write-Information` 是在 PowerShell 5.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ec87d-297">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="ec87d-298">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-298">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-299">**Stop** ：在命令出现时停止命令或脚本 `Write-Information` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-299">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="ec87d-300">**Inquire** ：显示你在命令中指定的信息性消息 `Write-Information` ，然后询问你是否要继续。</span><span class="sxs-lookup"><span data-stu-id="ec87d-300">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="ec87d-301">**继续** ：显示信息性消息，并继续运行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-301">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="ec87d-302">" **挂起** " 仅适用于 PowerShell 6 和更高版本中不支持的工作流。</span><span class="sxs-lookup"><span data-stu-id="ec87d-302">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="ec87d-303">**SilentlyContinue** ： (默认值) 不起作用。</span><span class="sxs-lookup"><span data-stu-id="ec87d-303">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="ec87d-304">不显示信息性消息，该脚本将继续进行而不中断。</span><span class="sxs-lookup"><span data-stu-id="ec87d-304">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="ec87d-305">\$Log \* 事件</span><span class="sxs-lookup"><span data-stu-id="ec87d-305">\$Log\*Event</span></span>

<span data-ttu-id="ec87d-306">**日志 \* 事件** 首选项变量确定哪些类型的事件将写入事件查看器中的 PowerShell 事件日志。</span><span class="sxs-lookup"><span data-stu-id="ec87d-306">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="ec87d-307">默认情况下，只记录引擎和提供程序事件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-307">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="ec87d-308">但你可以使用 **log \* 事件** 首选项变量来自定义日志，如记录有关命令的事件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-308">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="ec87d-309">**日志 \* 事件** 首选项变量如下所示：</span><span class="sxs-lookup"><span data-stu-id="ec87d-309">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="ec87d-310">`$LogCommandHealthEvent`：记录命令初始化和处理中的错误和异常。</span><span class="sxs-lookup"><span data-stu-id="ec87d-310">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="ec87d-311">默认值为 `$false` (未记录) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-311">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="ec87d-312">`$LogCommandLifecycleEvent`：记录命令和命令管道的启动和停止，以及命令发现中的安全异常。</span><span class="sxs-lookup"><span data-stu-id="ec87d-312">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="ec87d-313">默认值为 `$false` (未记录) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-313">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="ec87d-314">`$LogEngineHealthEvent`：记录会话的错误和失败。</span><span class="sxs-lookup"><span data-stu-id="ec87d-314">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="ec87d-315">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-315">The default is `$true` (logged).</span></span>
- <span data-ttu-id="ec87d-316">`$LogEngineLifecycleEvent`：记录会话的开始和结束。</span><span class="sxs-lookup"><span data-stu-id="ec87d-316">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="ec87d-317">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-317">The default is `$true` (logged).</span></span>
- <span data-ttu-id="ec87d-318">`$LogProviderHealthEvent`：记录提供程序错误，如读取和写入错误、查找错误以及调用错误。</span><span class="sxs-lookup"><span data-stu-id="ec87d-318">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="ec87d-319">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-319">The default is `$true` (logged).</span></span>
- <span data-ttu-id="ec87d-320">`$LogProviderLifecycleEvent`：日志添加和删除 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="ec87d-320">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="ec87d-321">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-321">The default is `$true` (logged).</span></span> <span data-ttu-id="ec87d-322">有关 PowerShell 提供程序的信息，请参阅 [about_Providers](about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-322">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="ec87d-323">若要启用 **Log \* 事件** ，请键入变量，其值 `$true` 为，例如：</span><span class="sxs-lookup"><span data-stu-id="ec87d-323">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="ec87d-324">若要禁用事件类型，请使用值键入变量 `$false` ，例如：</span><span class="sxs-lookup"><span data-stu-id="ec87d-324">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="ec87d-325">启用的事件仅对当前 PowerShell 控制台有效。</span><span class="sxs-lookup"><span data-stu-id="ec87d-325">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="ec87d-326">若要将配置应用到所有控制台，请将变量设置保存到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ec87d-326">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="ec87d-327">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-327">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="ec87d-328">\$MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="ec87d-328">\$MaximumHistoryCount</span></span>

<span data-ttu-id="ec87d-329">确定在当前会话的命令历史记录中保存的命令数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-329">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="ec87d-330">**有效值** ： 1-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="ec87d-330">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="ec87d-331">**默认值** ：4096</span><span class="sxs-lookup"><span data-stu-id="ec87d-331">**Default** : 4096</span></span>

<span data-ttu-id="ec87d-332">若要确定命令历史记录中当前保存的命令数，请键入：</span><span class="sxs-lookup"><span data-stu-id="ec87d-332">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="ec87d-333">若要查看已保存在会话历史记录中的命令，请使用 `Get-History` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec87d-333">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="ec87d-334">有关详细信息，请参阅 [about_History](about_History.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-334">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="ec87d-335">\$.OFS</span><span class="sxs-lookup"><span data-stu-id="ec87d-335">\$OFS</span></span>

<span data-ttu-id="ec87d-336"> (.OFS 的输出字段分隔符) 指定将转换为字符串的数组元素分隔的字符。</span><span class="sxs-lookup"><span data-stu-id="ec87d-336">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="ec87d-337">**有效值** ：任何字符串。</span><span class="sxs-lookup"><span data-stu-id="ec87d-337">**Valid values** : Any string.</span></span>

<span data-ttu-id="ec87d-338">**默认值** ： Space</span><span class="sxs-lookup"><span data-stu-id="ec87d-338">**Default** : Space</span></span>

<span data-ttu-id="ec87d-339">默认情况下，该 `$OFS` 变量不存在，并且输出文件分隔符为空格，但您可以添加此变量并将其设置为任何字符串。</span><span class="sxs-lookup"><span data-stu-id="ec87d-339">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="ec87d-340">可以 `$OFS` 通过键入在会话中更改的值 `$OFS="<value>"` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-340">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="ec87d-341">如果需要在 `" "` 脚本、模块或配置输出中 () 的空间的默认值，请小心，不要在 `$OFS` 代码中的其他位置更改默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-341">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-342">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-342">Examples</span></span>

<span data-ttu-id="ec87d-343">此示例显示当数组转换为字符串时，将使用空格来分隔值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-343">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="ec87d-344">在这种情况下，整数数组存储在一个变量中，然后将该变量强制转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="ec87d-344">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="ec87d-345">若要更改分隔符，请 `$OFS` 通过为变量赋值来添加变量。</span><span class="sxs-lookup"><span data-stu-id="ec87d-345">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="ec87d-346">变量必须命名为 `$OFS` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-346">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="ec87d-347">若要还原默认行为，可以 () 分配一个空格， `" "` `$OFS` 或删除该变量。</span><span class="sxs-lookup"><span data-stu-id="ec87d-347">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="ec87d-348">以下命令将删除该变量，然后验证该分隔符是否为空格。</span><span class="sxs-lookup"><span data-stu-id="ec87d-348">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="ec87d-349">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="ec87d-349">\$OutputEncoding</span></span>

<span data-ttu-id="ec87d-350">确定 PowerShell 在向其他应用程序发送文本时所使用的字符编码方法。</span><span class="sxs-lookup"><span data-stu-id="ec87d-350">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="ec87d-351">例如，如果应用程序将 Unicode 字符串返回到 PowerShell，你可能需要将值更改为 **UnicodeEncoding** ，以便正确发送字符。</span><span class="sxs-lookup"><span data-stu-id="ec87d-351">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="ec87d-352">有效值如下：派生自编码类的对象，例如 **ASCIIEncoding** 、 **SBCSCodePageEncoding** 、 **UTF7Encoding** 、 **UTF8Encoding** 、 **UTF32Encoding** 和 **UnicodeEncoding** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-352">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding** .</span></span>

<span data-ttu-id="ec87d-353">**默认值** ： UTF8Encoding 对象 (UTF8Encoding) </span><span class="sxs-lookup"><span data-stu-id="ec87d-353">**Default** : UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-354">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-354">Examples</span></span>

<span data-ttu-id="ec87d-355">此示例演示如何在使用 Unicode 字符（如中文）为语言本地化的计算机上，使 Windows **findstr.exe** 命令在 PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-355">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="ec87d-356">第一个命令查找值 `$OutputEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-356">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="ec87d-357">由于值是编码对象，因此只显示其 **encoding.encodingname** 属性。</span><span class="sxs-lookup"><span data-stu-id="ec87d-357">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="ec87d-358">在此示例中， **findstr.exe** 命令用于搜索文件中存在的两个中文字符 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-358">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="ec87d-359">在 Windows 命令提示符下运行此 **findstr.exe** 命令时 ( **cmd.exe** ) ， **findstr.exe** 将查找文本文件中的字符。</span><span class="sxs-lookup"><span data-stu-id="ec87d-359">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="ec87d-360">但是，当你在 PowerShell 中运行相同的 **findstr.exe** 命令时，将找不到这些字符，因为 PowerShell 会将它们发送到 ASCII 文本中的 **findstr.exe** 而不是 Unicode 文本。</span><span class="sxs-lookup"><span data-stu-id="ec87d-360">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="ec87d-361">若要在 PowerShell 中运行命令，请将的值设置 `$OutputEncoding` 为控制台的 **OutputEncoding** 属性的值，该属性基于为 Windows 选择的区域设置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-361">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="ec87d-362">由于 **OutputEncoding** 是控制台的静态属性，因此请在命令中使用双冒号 (`::`) 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-362">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="ec87d-363">编码更改后， **findstr.exe** 命令将查找 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="ec87d-363">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="ec87d-364">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-364">\$ProgressPreference</span></span>

<span data-ttu-id="ec87d-365">确定 PowerShell 如何响应脚本、cmdlet 或提供程序生成的进度更新，如 [写入-进度](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet 生成的进度栏。</span><span class="sxs-lookup"><span data-stu-id="ec87d-365">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="ec87d-366">`Write-Progress`Cmdlet 可创建显示命令状态的进度栏。</span><span class="sxs-lookup"><span data-stu-id="ec87d-366">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="ec87d-367">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-367">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-368">**停止** ：不显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="ec87d-368">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="ec87d-369">相反，它将显示一条错误消息并停止执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-369">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="ec87d-370">**Inquire** ：不显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="ec87d-370">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="ec87d-371">提示继续操作。</span><span class="sxs-lookup"><span data-stu-id="ec87d-371">Prompts for permission to continue.</span></span> <span data-ttu-id="ec87d-372">如果你通过 `Y` 或 `A` 进行回复，它会显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="ec87d-372">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="ec87d-373">**继续** ： (默认值) 显示进度栏，并继续执行操作。</span><span class="sxs-lookup"><span data-stu-id="ec87d-373">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="ec87d-374">**SilentlyContinue** ：执行命令，但不显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="ec87d-374">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="ec87d-375">\$PSEmailServer</span><span class="sxs-lookup"><span data-stu-id="ec87d-375">\$PSEmailServer</span></span>

<span data-ttu-id="ec87d-376">指定用于发送电子邮件的默认电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="ec87d-376">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="ec87d-377">发送电子邮件的 cmdlet （如 [send-mailmessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet）使用此首选项变量。</span><span class="sxs-lookup"><span data-stu-id="ec87d-377">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="ec87d-378">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="ec87d-378">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="ec87d-379">为 cmdlet 和高级函数的参数指定默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-379">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="ec87d-380">的值 `$PSDefaultParameterValues` 是一个哈希表，其中的键由 cmdlet 名称和参数名称组成，该名称由冒号 (`:`) 分隔。</span><span class="sxs-lookup"><span data-stu-id="ec87d-380">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="ec87d-381">值是指定的自定义默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-381">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="ec87d-382">`$PSDefaultParameterValues` 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ec87d-382">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="ec87d-383">有关此首选项变量的详细信息，请参阅 [about_Parameters_Default_Values](about_Parameters_Default_Values.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-383">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="ec87d-384">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-384">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="ec87d-385">启用和禁用会话中模块的自动导入。</span><span class="sxs-lookup"><span data-stu-id="ec87d-385">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="ec87d-386">**All** 为默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-386">**All** is the default.</span></span> <span data-ttu-id="ec87d-387">无论变量的值是什么，都可以使用 [import-module](xref:Microsoft.PowerShell.Core.Import-Module) 导入模块。</span><span class="sxs-lookup"><span data-stu-id="ec87d-387">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="ec87d-388">有效值是：</span><span class="sxs-lookup"><span data-stu-id="ec87d-388">Valid values are:</span></span>

- <span data-ttu-id="ec87d-389">**所有** ：首次使用时自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="ec87d-389">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="ec87d-390">若要导入模块，请获取或使用模块中的任何命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-390">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="ec87d-391">例如，使用 `Get-Command`。</span><span class="sxs-lookup"><span data-stu-id="ec87d-391">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="ec87d-392">**ModuleQualified** ：仅当用户使用模块中的模块限定名称时，才会自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="ec87d-392">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="ec87d-393">例如，如果用户键入，则 `MyModule\MyCommand` PowerShell 将导入 **MyModule** 模块。</span><span class="sxs-lookup"><span data-stu-id="ec87d-393">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="ec87d-394">**None** ：在会话中禁用自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="ec87d-394">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="ec87d-395">若要导入模块，请使用 `Import-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec87d-395">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="ec87d-396">有关自动导入模块的详细信息，请参阅 [about_Modules](about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-396">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="ec87d-397">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="ec87d-397">\$PSSessionApplicationName</span></span>

<span data-ttu-id="ec87d-398">指定远程命令的默认应用程序名称，该命令使用 (WS-MANAGEMENT) 技术管理的 "Web 服务"。</span><span class="sxs-lookup"><span data-stu-id="ec87d-398">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="ec87d-399">有关详细信息，请参阅 [关于 Windows 远程管理](/windows/win32/winrm/about-windows-remote-management)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-399">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="ec87d-400">系统默认应用程序名称为 `WSMAN` ，但你可以使用此首选项变量更改默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-400">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="ec87d-401">应用程序名称是连接 URI 中的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="ec87d-401">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="ec87d-402">例如，下面的示例 URI 中的应用程序名称为 `WSMAN` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-402">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="ec87d-403">如果远程命令未指定连接 URI 或应用程序名称，则使用默认应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="ec87d-403">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="ec87d-404">**WinRM** 服务使用应用程序名称来选择用于处理连接请求的侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec87d-404">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="ec87d-405">参数的值应与远程计算机上的侦听器的 **URLPrefix** 属性值相匹配。</span><span class="sxs-lookup"><span data-stu-id="ec87d-405">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="ec87d-406">若要覆盖系统默认值和此变量的值，并为特定会话选择不同的应用程序名称，请使用 [新的 PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)、 [Enter-Pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession)或 [调用命令](xref:Microsoft.PowerShell.Core.Invoke-Command)cmdlet 的 **ConnectionURI** 或 **ApplicationName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-406">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="ec87d-407">`$PSSessionApplicationName`首选项变量是在本地计算机上设置的，但它指定了远程计算机上的侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec87d-407">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="ec87d-408">如果你指定的应用程序名称在远程计算机上不存在，则用于建立会话的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ec87d-408">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="ec87d-409">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="ec87d-409">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="ec87d-410">指定用于在当前会话中创建的 **pssession** 的默认会话配置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-410">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="ec87d-411">此首选项变量是在本地计算机上设置的，但它指定了位于远程计算机上的会话配置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-411">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="ec87d-412">变量的值 `$PSSessionConfigurationName` 是完全限定的资源 URI。</span><span class="sxs-lookup"><span data-stu-id="ec87d-412">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="ec87d-413">默认值 `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` 表示远程计算机上的 **Microsoft PowerShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-413">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="ec87d-414">如果只指定配置名称，则会预置以下架构 URI：</span><span class="sxs-lookup"><span data-stu-id="ec87d-414">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="ec87d-415">你可以使用 **ConfigurationName** `New-PSSession` 、 `Enter-PSSession` 或 cmdlet 的 ConfigurationName 参数覆盖默认值，并为特定会话选择不同的会话配置 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-415">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="ec87d-416">您可以随时更改此变量的值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-416">You can change the value of this variable at any time.</span></span> <span data-ttu-id="ec87d-417">当你执行此操作时，请记住，你选择的会话配置必须在远程计算机上存在。</span><span class="sxs-lookup"><span data-stu-id="ec87d-417">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="ec87d-418">否则，创建使用会话配置的会话的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ec87d-418">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="ec87d-419">当远程用户创建连接到此计算机的会话时，此首选项变量不会确定使用的本地会话配置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-419">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="ec87d-420">但是，你可以使用本地会话配置的权限来确定哪些用户可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="ec87d-420">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="ec87d-421">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="ec87d-421">\$PSSessionOption</span></span>

<span data-ttu-id="ec87d-422">建立远程会话中高级用户选项的默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-422">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="ec87d-423">这些选项首选项会替代会话选项的系统默认值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-423">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="ec87d-424">`$PSSessionOption`变量包含 **PSSessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="ec87d-424">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="ec87d-425">有关详细信息，请参阅 [PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-425">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="ec87d-426">对象的每个属性都表示一个会话选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-426">Each property of the object represents a session option.</span></span> <span data-ttu-id="ec87d-427">例如， **NoCompression** 属性将在会话期间启用数据压缩。</span><span class="sxs-lookup"><span data-stu-id="ec87d-427">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="ec87d-428">默认情况下，该 `$PSSessionOption` 变量包含一个 **PSSessionOption** 对象，该对象具有所有选项的默认值，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ec87d-428">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

<span data-ttu-id="ec87d-429">有关这些选项的说明和详细信息，请参阅 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-429">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="ec87d-430">有关远程命令和会话的详细信息，请参阅 [about_Remote](about_Remote.md) 和 [about_PSSessions](about_PSSessions.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-430">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="ec87d-431">若要更改首选项变量的值 `$PSSessionOption` ，请使用 `New-PSSessionOption` cmdlet 创建一个 **PSSessionOption** 对象，该对象具有你喜欢的选项值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-431">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="ec87d-432">将输出保存在一个名为的变量中 `$PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-432">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="ec87d-433">若要 `$PSSessionOption` 在每个 powershell 会话中使用首选项变量，请将 `New-PSSessionOption` 创建该变量的命令添加 `$PSSessionOption` 到 powershell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ec87d-433">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="ec87d-434">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-434">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="ec87d-435">您可以为特定的远程会话设置自定义选项。</span><span class="sxs-lookup"><span data-stu-id="ec87d-435">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="ec87d-436">您设置的选项优先于系统默认值和 `$PSSessionOption` 首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-436">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="ec87d-437">若要设置自定义会话选项，请使用 `New-PSSessionOption` cmdlet 创建 **PSSessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="ec87d-437">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="ec87d-438">然后，在创建会话的 cmdlet （例如、和）中，使用 **PSSessionOption** 对象作为 **SessionOption** 参数的值 `New-PSSession` `Enter-PSSession` `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-438">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="ec87d-439">$Transcript</span><span class="sxs-lookup"><span data-stu-id="ec87d-439">$Transcript</span></span>

<span data-ttu-id="ec87d-440">用于 `Start-Transcript` 指定脚本文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="ec87d-440">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="ec87d-441">如果未指定 **path** 参数的值，则将 `Start-Transcript` 使用全局变量的值中的路径 `$Transcript` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-441">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="ec87d-442">如果尚未创建此变量，请将这些 `Start-Transcript` 脚本 `$Home\My Documents` 作为文件存储在目录中 `\PowerShell_transcript.<time-stamp>.txt` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-442">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="ec87d-443">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-443">\$VerbosePreference</span></span>

<span data-ttu-id="ec87d-444">确定 PowerShell 如何响应脚本、cmdlet 或提供程序生成的详细消息，如 [写入-详细](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet 生成的消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-444">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="ec87d-445">详细消息描述执行命令所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ec87d-445">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="ec87d-446">默认情况下，不显示详细消息，但是您可以通过更改的值来更改此行为 `$VerbosePreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-446">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="ec87d-447">可以使用 cmdlet 的 **verbose** 通用参数来显示或隐藏特定命令的详细消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-447">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="ec87d-448">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-448">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="ec87d-449">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-449">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-450">**停止** ：显示详细消息和错误消息，然后停止执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-450">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="ec87d-451">**Inquire** ：显示详细消息，然后显示一条提示，询问您是否要继续。</span><span class="sxs-lookup"><span data-stu-id="ec87d-451">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="ec87d-452">**继续** ：显示详细消息，然后继续执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-452">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="ec87d-453">**SilentlyContinue** ： (默认) 不显示详细消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-453">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="ec87d-454">继续执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-454">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-455">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-455">Examples</span></span>

<span data-ttu-id="ec87d-456">这些示例显示了不同的值的效果 `$VerbosePreference` ，并显示了 **Verbose** 参数重写首选项值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-456">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="ec87d-457">此示例显示 **SilentlyContinue** 值（这是默认值）的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-457">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="ec87d-458">此命令使用 **message** 参数，但不会将消息写入 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="ec87d-458">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="ec87d-459">使用 **详细** 参数时，将写入消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-459">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="ec87d-460">此示例显示了 **Continue** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-460">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="ec87d-461">`$VerbosePreference`变量设置为 **Continue** ，并显示消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-461">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="ec87d-462">此示例使用 **Verbose** 参数，该参数的值为 `$false` ，它将重写 **Continue** 值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-462">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="ec87d-463">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-463">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="ec87d-464">此示例显示了 **停止** 值的影响。</span><span class="sxs-lookup"><span data-stu-id="ec87d-464">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="ec87d-465">`$VerbosePreference`变量设置为 " **停止** "，并显示消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-465">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="ec87d-466">命令已停止。</span><span class="sxs-lookup"><span data-stu-id="ec87d-466">The command is stopped.</span></span>

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="ec87d-467">此示例使用 **Verbose** 参数，该参数的值为 `$false` ，它将替代 **停止** 值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-467">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="ec87d-468">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-468">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="ec87d-469">此示例显示了 **Inquire** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-469">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="ec87d-470">`$VerbosePreference`变量设置为 **Inquire** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-470">The `$VerbosePreference` variable is set to **Inquire** .</span></span> <span data-ttu-id="ec87d-471">消息随即显示，并提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-471">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="ec87d-472">此示例使用带有 **Verbose** `$false` 替代 **Inquire** 值的值的详细参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-472">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="ec87d-473">系统不会提示用户并且不显示消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-473">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="ec87d-474">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-474">\$WarningPreference</span></span>

<span data-ttu-id="ec87d-475">确定 PowerShell 如何响应脚本、cmdlet 或提供程序生成的警告消息，如 [写入警告](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet 生成的消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-475">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="ec87d-476">默认情况下，会显示警告消息并继续执行，但你可以通过更改的值来更改此行为 `$WarningPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-476">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="ec87d-477">可以使用 cmdlet 的 **WarningAction** common 参数确定 PowerShell 如何响应特定命令中的警告。</span><span class="sxs-lookup"><span data-stu-id="ec87d-477">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="ec87d-478">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec87d-478">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="ec87d-479">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-479">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-480">**停止** ：显示警告消息和错误消息，然后停止执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-480">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="ec87d-481">**Inquire** ：显示警告消息，然后提示继续操作。</span><span class="sxs-lookup"><span data-stu-id="ec87d-481">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="ec87d-482">**继续** ： (默认值) 显示警告消息，然后继续执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-482">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="ec87d-483">**SilentlyContinue** ：不显示警告消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-483">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="ec87d-484">继续执行。</span><span class="sxs-lookup"><span data-stu-id="ec87d-484">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-485">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-485">Examples</span></span>

<span data-ttu-id="ec87d-486">这些示例显示了不同的值的效果 `$WarningPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-486">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="ec87d-487">**WarningAction** 参数将覆盖首选项值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-487">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="ec87d-488">此示例显示默认值的效果，然后 **继续** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-488">This example shows the effect of the default value, **Continue** .</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="ec87d-489">此示例使用值为 **SilentlyContinue** 的 **WarningAction** 参数来禁止显示警告。</span><span class="sxs-lookup"><span data-stu-id="ec87d-489">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="ec87d-490">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-490">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="ec87d-491">此示例将 `$WarningPreference` 变量更改为 **SilentlyContinue** 值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-491">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="ec87d-492">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-492">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="ec87d-493">此示例在生成警告时使用 **WarningAction** 参数停止。</span><span class="sxs-lookup"><span data-stu-id="ec87d-493">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

<span data-ttu-id="ec87d-494">此示例将 `$WarningPreference` 变量更改为 **Inquire** 值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-494">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="ec87d-495">系统将提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="ec87d-495">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="ec87d-496">此示例使用值为 **SilentlyContinue** 的 **WarningAction** 参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-496">This example uses the **WarningAction** parameter with the value **SilentlyContinue** .</span></span> <span data-ttu-id="ec87d-497">命令将继续执行，并且不会显示任何消息。</span><span class="sxs-lookup"><span data-stu-id="ec87d-497">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="ec87d-498">此示例将 `$WarningPreference` 值更改为 " **Stop** "。</span><span class="sxs-lookup"><span data-stu-id="ec87d-498">This example changes the `$WarningPreference` value to **Stop** .</span></span>

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

<span data-ttu-id="ec87d-499">此示例将 **WarningAction** 与 **Inquire** 值一起使用。</span><span class="sxs-lookup"><span data-stu-id="ec87d-499">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="ec87d-500">出现警告时，系统将提示用户。</span><span class="sxs-lookup"><span data-stu-id="ec87d-500">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="ec87d-501">\$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="ec87d-501">\$WhatIfPreference</span></span>

<span data-ttu-id="ec87d-502">确定是否自动为支持它的每个命令启用 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-502">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="ec87d-503">启用 **WhatIf** 后，该 cmdlet 会报告命令的预期效果，但不会执行命令。</span><span class="sxs-lookup"><span data-stu-id="ec87d-503">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="ec87d-504">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="ec87d-504">The valid values are as follows:</span></span>

- <span data-ttu-id="ec87d-505">**False** ( **0** ，未启用) ： (默认) **WhatIf** 不自动启用。</span><span class="sxs-lookup"><span data-stu-id="ec87d-505">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="ec87d-506">若要手动启用此参数，请使用 cmdlet 的 **WhatIf** 参数。</span><span class="sxs-lookup"><span data-stu-id="ec87d-506">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="ec87d-507">**True** ( **1** ，已启用) ：自动对支持该功能的任何命令启用 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-507">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="ec87d-508">用户可以使用值为 **False** 的 **WhatIf** 参数手动禁用它，如 `-WhatIf:$false` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-508">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="ec87d-509">示例</span><span class="sxs-lookup"><span data-stu-id="ec87d-509">Examples</span></span>

<span data-ttu-id="ec87d-510">这些示例显示了不同的值的效果 `$WhatIfPreference` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-510">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="ec87d-511">它们演示如何使用 **WhatIf** 参数覆盖特定命令的首选项值。</span><span class="sxs-lookup"><span data-stu-id="ec87d-511">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="ec87d-512">此示例显示 `$WhatIfPreference` 变量设置为默认值 **False** 的影响。</span><span class="sxs-lookup"><span data-stu-id="ec87d-512">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False** .</span></span> <span data-ttu-id="ec87d-513">使用 `Get-ChildItem` 验证该文件是否存在。</span><span class="sxs-lookup"><span data-stu-id="ec87d-513">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="ec87d-514">`Remove-Item` 删除文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-514">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="ec87d-515">删除文件后，可以通过验证删除 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-515">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

<span data-ttu-id="ec87d-516">此示例演示在的值为 False 时使用 **WhatIf** 参数的效果 `$WhatIfPreference` 。 **False**</span><span class="sxs-lookup"><span data-stu-id="ec87d-516">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False** .</span></span>

<span data-ttu-id="ec87d-517">请确保该文件已存在。</span><span class="sxs-lookup"><span data-stu-id="ec87d-517">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="ec87d-518">使用 **WhatIf** 参数确定尝试删除文件的结果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-518">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="ec87d-519">验证文件是否未被删除。</span><span class="sxs-lookup"><span data-stu-id="ec87d-519">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="ec87d-520">此示例显示 `$WhatIfPreference` 变量设置为值 **True** 后的效果。</span><span class="sxs-lookup"><span data-stu-id="ec87d-520">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True** .</span></span> <span data-ttu-id="ec87d-521">使用 `Remove-Item` 删除文件时，会显示文件的路径，但不会删除文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-521">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="ec87d-522">尝试删除文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-522">Attempt to delete a file.</span></span> <span data-ttu-id="ec87d-523">将显示一条消息，其中显示在运行时将会发生什么情况 `Remove-Item` ，但不会删除该文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-523">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="ec87d-524">使用 `Get-ChildItem` 验证文件是否未被删除。</span><span class="sxs-lookup"><span data-stu-id="ec87d-524">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="ec87d-525">此示例演示如何在的值为 True 时删除文件 `$WhatIfPreference` 。 **True**</span><span class="sxs-lookup"><span data-stu-id="ec87d-525">This example shows how to delete a file when the value of `$WhatIfPreference` is **True** .</span></span> <span data-ttu-id="ec87d-526">它使用值为的 **WhatIf** 参数 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-526">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="ec87d-527">使用 `Get-ChildItem` 验证是否已删除该文件。</span><span class="sxs-lookup"><span data-stu-id="ec87d-527">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="ec87d-528">下面是不 `Get-Process` 支持 **whatif** 并且 `Stop-Process` 支持 **whatif** 的 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="ec87d-528">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf** .</span></span> <span data-ttu-id="ec87d-529">`$WhatIfPreference`变量的值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-529">The `$WhatIfPreference` variable's value is **True** .</span></span>

<span data-ttu-id="ec87d-530">`Get-Process` 不支持 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-530">`Get-Process` doesn't support **WhatIf** .</span></span> <span data-ttu-id="ec87d-531">执行命令时，它将显示 **Winword** 进程。</span><span class="sxs-lookup"><span data-stu-id="ec87d-531">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="ec87d-532">`Stop-Process` 支持 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-532">`Stop-Process` does support **WhatIf** .</span></span> <span data-ttu-id="ec87d-533">**Winword** 进程未停止。</span><span class="sxs-lookup"><span data-stu-id="ec87d-533">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="ec87d-534">您可以 `Stop-Process` 通过使用值为的 **whatif** 参数来重写 **whatif** 行为 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-534">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="ec87d-535">**Winword** 进程已停止。</span><span class="sxs-lookup"><span data-stu-id="ec87d-535">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="ec87d-536">若要验证 **Winword** 进程是否已停止，请使用 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="ec87d-536">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="ec87d-537">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec87d-537">See also</span></span>

[<span data-ttu-id="ec87d-538">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="ec87d-538">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="ec87d-539">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec87d-539">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="ec87d-540">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="ec87d-540">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="ec87d-541">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="ec87d-541">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="ec87d-542">about_Remote</span><span class="sxs-lookup"><span data-stu-id="ec87d-542">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="ec87d-543">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="ec87d-543">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="ec87d-544">about_Variables</span><span class="sxs-lookup"><span data-stu-id="ec87d-544">about_Variables</span></span>](about_Variables.md)
