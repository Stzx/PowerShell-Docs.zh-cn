---
description: 自定义 PowerShell 行为的变量。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 25677cf687349bf805b66a116d3b2f09d27037bd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200091"
---
# <a name="about-preference-variables"></a><span data-ttu-id="4070c-104">关于首选项变量</span><span class="sxs-lookup"><span data-stu-id="4070c-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="4070c-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="4070c-105">Short description</span></span>

<span data-ttu-id="4070c-106">自定义 PowerShell 行为的变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4070c-107">长说明</span><span class="sxs-lookup"><span data-stu-id="4070c-107">Long description</span></span>

<span data-ttu-id="4070c-108">PowerShell 包含一组变量，使你能够自定义其行为。</span><span class="sxs-lookup"><span data-stu-id="4070c-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="4070c-109">这些首选项变量的工作方式类似于基于 GUI 的系统中的选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="4070c-110">首选项变量将影响 PowerShell 操作环境以及在环境中运行的所有命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="4070c-111">在许多情况下，cmdlet 具有可用于覆盖特定命令的首选项行为的参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="4070c-112">下表列出了首选项变量及其默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="4070c-113">变量</span><span class="sxs-lookup"><span data-stu-id="4070c-113">Variable</span></span>             |       <span data-ttu-id="4070c-114">默认值</span><span class="sxs-lookup"><span data-stu-id="4070c-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="4070c-115">高</span><span class="sxs-lookup"><span data-stu-id="4070c-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="4070c-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="4070c-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="4070c-117">继续</span><span class="sxs-lookup"><span data-stu-id="4070c-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="4070c-118">NormalView</span><span class="sxs-lookup"><span data-stu-id="4070c-118">NormalView</span></span>                |
| `$FormatEnumerationLimit`        | <span data-ttu-id="4070c-119">4</span><span class="sxs-lookup"><span data-stu-id="4070c-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="4070c-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="4070c-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="4070c-121">错误 (未记录) </span><span class="sxs-lookup"><span data-stu-id="4070c-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="4070c-122">错误 (未记录) </span><span class="sxs-lookup"><span data-stu-id="4070c-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="4070c-123"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="4070c-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="4070c-124"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="4070c-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="4070c-125"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="4070c-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="4070c-126"> (记录为 True) </span><span class="sxs-lookup"><span data-stu-id="4070c-126">True (logged)</span></span>             |
| `$MaximumAliasCount`             | <span data-ttu-id="4070c-127">4096</span><span class="sxs-lookup"><span data-stu-id="4070c-127">4096</span></span>                      |
| `$MaximumDriveCount`             | <span data-ttu-id="4070c-128">4096</span><span class="sxs-lookup"><span data-stu-id="4070c-128">4096</span></span>                      |
| `$MaximumErrorCount`             | <span data-ttu-id="4070c-129">256</span><span class="sxs-lookup"><span data-stu-id="4070c-129">256</span></span>                       |
| `$MaximumFunctionCount`          | <span data-ttu-id="4070c-130">4096</span><span class="sxs-lookup"><span data-stu-id="4070c-130">4096</span></span>                      |
| `$MaximumHistoryCount`           | <span data-ttu-id="4070c-131">4096</span><span class="sxs-lookup"><span data-stu-id="4070c-131">4096</span></span>                      |
| `$MaximumVariableCount`          | <span data-ttu-id="4070c-132">4096</span><span class="sxs-lookup"><span data-stu-id="4070c-132">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="4070c-133"> (空格字符 (`" "`) # A3</span><span class="sxs-lookup"><span data-stu-id="4070c-133">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="4070c-134">**ASCIIEncoding** 对象</span><span class="sxs-lookup"><span data-stu-id="4070c-134">**ASCIIEncoding** object</span></span>  |
| `$ProgressPreference`            | <span data-ttu-id="4070c-135">继续</span><span class="sxs-lookup"><span data-stu-id="4070c-135">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="4070c-136"> (无-) 哈希表</span><span class="sxs-lookup"><span data-stu-id="4070c-136">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="4070c-137">（无）</span><span class="sxs-lookup"><span data-stu-id="4070c-137">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="4070c-138">全部</span><span class="sxs-lookup"><span data-stu-id="4070c-138">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="4070c-139">wsman</span><span class="sxs-lookup"><span data-stu-id="4070c-139">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="4070c-140">请参阅 [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="4070c-140">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="4070c-141">（无）</span><span class="sxs-lookup"><span data-stu-id="4070c-141">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="4070c-142">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="4070c-142">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="4070c-143">继续</span><span class="sxs-lookup"><span data-stu-id="4070c-143">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="4070c-144">False</span><span class="sxs-lookup"><span data-stu-id="4070c-144">False</span></span>                     |

<span data-ttu-id="4070c-145">PowerShell 包括存储用户首选项的以下环境变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-145">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="4070c-146">有关这些环境变量的详细信息，请参阅 [about_Environment_Variables](about_Environment_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-146">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="4070c-147">首选项变量的更改仅对脚本和函数有效，前提是这些脚本或函数是在使用首选项的作用域中定义的。</span><span class="sxs-lookup"><span data-stu-id="4070c-147">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="4070c-148">有关详细信息，请参阅 [about_Scopes](about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-148">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="4070c-149">使用首选项变量</span><span class="sxs-lookup"><span data-stu-id="4070c-149">Working with preference variables</span></span>

<span data-ttu-id="4070c-150">本文档介绍每个首选项变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-150">This document describes each of the preference variables.</span></span>

<span data-ttu-id="4070c-151">若要显示特定首选项变量的当前值，请键入该变量的名称。</span><span class="sxs-lookup"><span data-stu-id="4070c-151">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="4070c-152">例如，下面的命令显示 `$ConfirmPreference` 变量的值。</span><span class="sxs-lookup"><span data-stu-id="4070c-152">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="4070c-153">若要更改变量的值，请使用赋值语句。</span><span class="sxs-lookup"><span data-stu-id="4070c-153">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="4070c-154">例如，下面的语句将 `$ConfirmPreference` 参数的值更改为 " **中** "。</span><span class="sxs-lookup"><span data-stu-id="4070c-154">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium** .</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="4070c-155">您设置的值特定于当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="4070c-155">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="4070c-156">若要使变量在所有 PowerShell 会话中生效，请将它们添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="4070c-156">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="4070c-157">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-157">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="4070c-158">远程工作</span><span class="sxs-lookup"><span data-stu-id="4070c-158">Working remotely</span></span>

<span data-ttu-id="4070c-159">在远程计算机上运行命令时，远程命令仅服从远程计算机的 PowerShell 客户端中的首选项设置。</span><span class="sxs-lookup"><span data-stu-id="4070c-159">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="4070c-160">例如，当你运行远程命令时，远程计算机的变量的值将 `$DebugPreference` 决定 PowerShell 对调试消息的响应方式。</span><span class="sxs-lookup"><span data-stu-id="4070c-160">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="4070c-161">有关远程命令的详细信息，请参阅 [about_Remote](about_Remote.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-161">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="4070c-162">\$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-162">\$ConfirmPreference</span></span>

<span data-ttu-id="4070c-163">确定在运行 cmdlet 或函数之前 PowerShell 是否自动提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-163">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="4070c-164">`$ConfirmPreference`变量的有效值为 " **高** "、" **中** " 或 " **低** "。</span><span class="sxs-lookup"><span data-stu-id="4070c-164">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low** .</span></span> <span data-ttu-id="4070c-165">为 cmdlet 和函数分配了 **高** 、 **中** 或 **低** 的风险。</span><span class="sxs-lookup"><span data-stu-id="4070c-165">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low** .</span></span> <span data-ttu-id="4070c-166">当变量的值 `$ConfirmPreference` 小于或等于分配给 cmdlet 或函数的风险时，PowerShell 会在运行 cmdlet 或函数之前自动提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-166">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="4070c-167">如果该变量的值 `$ConfirmPreference` 为 " **无** "，则在运行 cmdlet 或函数之前，PowerShell 从不会自动提示您。</span><span class="sxs-lookup"><span data-stu-id="4070c-167">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="4070c-168">若要更改会话中所有 cmdlet 和函数的确认行为，请更改 `$ConfirmPreference` 变量的值。</span><span class="sxs-lookup"><span data-stu-id="4070c-168">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="4070c-169">若要为 `$ConfirmPreference` 单个命令重写，请使用 cmdlet 或函数的 **Confirm** 参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-169">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="4070c-170">若要请求确认，请使用 `-Confirm` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-170">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="4070c-171">若要取消确认，请使用 `-Confirm:$false` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-171">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="4070c-172">有效值为 `$ConfirmPreference` ：</span><span class="sxs-lookup"><span data-stu-id="4070c-172">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="4070c-173">**无** ：不自动提示 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4070c-173">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="4070c-174">若要请求确认特定命令，请使用 cmdlet 或函数的 **Confirm** 参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-174">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="4070c-175">**低** ：在运行具有低、中或高风险的 cmdlet 或函数之前，PowerShell 会提示进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-175">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="4070c-176">**中** ： PowerShell 在运行 cmdlet 之前提示进行确认，或使用中等或高风险运行这些功能。</span><span class="sxs-lookup"><span data-stu-id="4070c-176">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="4070c-177">**高** ： PowerShell 在运行 cmdlet 或具有高风险的功能之前提示确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-177">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="4070c-178">详细说明</span><span class="sxs-lookup"><span data-stu-id="4070c-178">Detailed explanation</span></span>

<span data-ttu-id="4070c-179">PowerShell 可以在执行操作之前自动提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-179">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="4070c-180">例如，当 cmdlet 或函数严重影响系统以删除数据或使用大量系统资源时。</span><span class="sxs-lookup"><span data-stu-id="4070c-180">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="4070c-181">风险的估计值是指作为其 **ConfirmImpact** 的 cmdlet 或函数的属性。</span><span class="sxs-lookup"><span data-stu-id="4070c-181">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact** .</span></span> <span data-ttu-id="4070c-182">用户无法更改它。</span><span class="sxs-lookup"><span data-stu-id="4070c-182">Users can't change it.</span></span>

<span data-ttu-id="4070c-183">可能会给系统带来风险的 cmdlet 和函数具有 **Confirm** 参数，可用于请求或取消对单个命令的确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-183">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="4070c-184">由于大多数 cmdlet 和函数使用 **默认的风险** 值 **ConfirmImpact** ，而默认值为 "高"，因此 `$ConfirmPreference` 很 **High** 少发生自动确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-184">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="4070c-185">但是，可以通过将的值更改为 "中" `$ConfirmPreference` 或 **Medium** " **低** " 来激活自动确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-185">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low** .</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-186">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-186">Examples</span></span>

<span data-ttu-id="4070c-187">此示例显示 `$ConfirmPreference` 变量的默认值（ **高** ）的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-187">This example shows the effect of the `$ConfirmPreference` variable's default value, **High** .</span></span> <span data-ttu-id="4070c-188">**高** 值仅用于确认高风险 cmdlet 和函数。</span><span class="sxs-lookup"><span data-stu-id="4070c-188">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="4070c-189">由于大多数 cmdlet 和函数都是中等风险，因此它们不会自动确认并 `Remove-Item` 删除文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-189">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="4070c-190">添加 `-Confirm` 到命令会提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-190">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="4070c-191">使用 `-Confirm` 请求确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-191">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="4070c-192">下面的示例演示了将的值更改为 " `$ConfirmPreference` **中** " 的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-192">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium** .</span></span> <span data-ttu-id="4070c-193">由于大多数 cmdlet 和函数都是中等风险，因此它们会自动得到确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-193">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="4070c-194">若要禁止显示单个命令的确认提示，请使用值为的 **Confirm** 参数 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-194">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="4070c-195">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-195">\$DebugPreference</span></span>

<span data-ttu-id="4070c-196">确定 PowerShell 如何响应脚本、cmdlet 或提供程序所生成的消息，或 `Write-Debug` 命令行中的命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-196">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="4070c-197">某些 cmdlet 显示调试消息，这些消息通常是为程序员和技术支持专业人员设计的技术消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-197">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="4070c-198">默认情况下，调试消息不会显示，但你可以通过更改的值来显示调试消息 `$DebugPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-198">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="4070c-199">可以使用 cmdlet 的 **Debug** 通用参数来显示或隐藏特定命令的调试消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-199">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="4070c-200">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-200">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="4070c-201">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-201">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-202">**停止** ：显示调试消息，并停止执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-202">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="4070c-203">向控制台写入错误。</span><span class="sxs-lookup"><span data-stu-id="4070c-203">Writes an error to the console.</span></span>
- <span data-ttu-id="4070c-204">**Inquire** ：显示调试消息，并询问您是否要继续。</span><span class="sxs-lookup"><span data-stu-id="4070c-204">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="4070c-205">将 **Debug** common 参数添加到命令时，在将该命令配置为生成调试消息时，将更改该变量的值 `$DebugPreference` 以进行 **查询** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-205">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire** .</span></span>
- <span data-ttu-id="4070c-206">**继续** ：显示调试消息，并继续执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-206">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="4070c-207">**SilentlyContinue** ： (默认值) 不起作用。</span><span class="sxs-lookup"><span data-stu-id="4070c-207">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="4070c-208">调试消息不会显示，执行将继续进行而不中断。</span><span class="sxs-lookup"><span data-stu-id="4070c-208">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-209">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-209">Examples</span></span>

<span data-ttu-id="4070c-210">下面的示例演示在 `$DebugPreference` 命令行中输入命令时更改值的影响 `Write-Debug` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-210">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="4070c-211">更改会影响所有调试消息，包括 cmdlet 和脚本生成的消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-211">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="4070c-212">示例显示了 **Debug** 参数，该参数显示或隐藏与单个命令相关的调试消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-212">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="4070c-213">此示例显示 `$DebugPreference` 变量的默认值 **SilentlyContinue** 的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-213">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue** .</span></span> <span data-ttu-id="4070c-214">默认情况下， `Write-Debug` cmdlet 的调试消息不会显示并且处理将继续进行。</span><span class="sxs-lookup"><span data-stu-id="4070c-214">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="4070c-215">使用 **Debug** 参数时，它将覆盖单个命令的首选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-215">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="4070c-216">系统将提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-216">The user is prompted for confirmation.</span></span>

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
Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="4070c-217">此示例显示了 `$DebugPreference` 具有 **Continue** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-217">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="4070c-218">调试消息随即显示，命令继续处理。</span><span class="sxs-lookup"><span data-stu-id="4070c-218">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="4070c-219">此示例使用 **Debug** 参数，其中的值 `$false` 为，以禁止将消息用于单个命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-219">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="4070c-220">不显示调试消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-220">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="4070c-221">此示例显示 `$DebugPreference` 设置为 " **停止** " 值的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-221">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="4070c-222">将显示调试消息，并停止该命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-222">The debug message is displayed and the command is stopped.</span></span>

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

<span data-ttu-id="4070c-223">此示例使用 **Debug** 参数，其中的值 `$false` 为，以禁止将消息用于单个命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-223">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="4070c-224">调试消息不会显示并且不会停止处理。</span><span class="sxs-lookup"><span data-stu-id="4070c-224">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="4070c-225">此示例显示了 `$DebugPreference` 设置为 **查询** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-225">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="4070c-226">将显示调试消息，并提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-226">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="4070c-227">此示例使用 **Debug** 参数，其中的值 `$false` 为，以禁止将消息用于单个命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-227">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="4070c-228">调试消息不会显示并继续处理。</span><span class="sxs-lookup"><span data-stu-id="4070c-228">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="4070c-229">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-229">\$ErrorActionPreference</span></span>

<span data-ttu-id="4070c-230">确定 PowerShell 如何响应非终止错误，该错误不会停止 cmdlet 处理。</span><span class="sxs-lookup"><span data-stu-id="4070c-230">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="4070c-231">例如，在命令行或脚本、cmdlet 或提供程序中，如 cmdlet 生成的错误 `Write-Error` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-231">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="4070c-232">可以使用 cmdlet 的 **ErrorAction** 通用参数来覆盖特定命令的首选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-232">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="4070c-233">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-233">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-234">**继续** ： (默认值) 显示错误消息并继续执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-234">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="4070c-235">**Ignore** ：禁止显示错误消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-235">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="4070c-236">**Ignore** 值专用于按命令使用，而不是用作保存的首选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-236">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="4070c-237">**Ignore** 不是变量的有效值 `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-237">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="4070c-238">**Inquire** ：显示错误消息，并询问您是否要继续。</span><span class="sxs-lookup"><span data-stu-id="4070c-238">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="4070c-239">**SilentlyContinue** ：不起作用。</span><span class="sxs-lookup"><span data-stu-id="4070c-239">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="4070c-240">错误消息不会显示，执行将继续进行而不中断。</span><span class="sxs-lookup"><span data-stu-id="4070c-240">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="4070c-241">**停止** ：显示错误消息并停止执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-241">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="4070c-242">除生成的错误外， **停止** 值还会将 ActionPreferenceStopException 对象生成到错误流。</span><span class="sxs-lookup"><span data-stu-id="4070c-242">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="4070c-243">流 (stream)</span><span class="sxs-lookup"><span data-stu-id="4070c-243">stream</span></span>
- <span data-ttu-id="4070c-244">**挂起** ：自动挂起工作流作业以便进一步进行调查。</span><span class="sxs-lookup"><span data-stu-id="4070c-244">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="4070c-245">调查后，工作流可以恢复。</span><span class="sxs-lookup"><span data-stu-id="4070c-245">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="4070c-246">" **挂起** " 值适用于按命令使用，而不是用作保存的首选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-246">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="4070c-247">**挂起** 不是变量的有效值 `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-247">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="4070c-248">`$ErrorActionPreference`**ErrorAction** 参数不会影响 PowerShell 响应终止处理停止 cmdlet 的错误的方式。</span><span class="sxs-lookup"><span data-stu-id="4070c-248">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="4070c-249">有关 **ErrorAction** 通用参数的详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-249">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-250">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-250">Examples</span></span>

<span data-ttu-id="4070c-251">这些示例显示变量的不同值的影响 `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-251">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="4070c-252">**ErrorAction** 参数用于重写 `$ErrorActionPreference` 值。</span><span class="sxs-lookup"><span data-stu-id="4070c-252">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="4070c-253">此示例显示 `$ErrorActionPreference` 默认值 " **Continue** "。</span><span class="sxs-lookup"><span data-stu-id="4070c-253">This example shows the `$ErrorActionPreference` default value, **Continue** .</span></span> <span data-ttu-id="4070c-254">生成非终止错误。</span><span class="sxs-lookup"><span data-stu-id="4070c-254">A non-terminating error is generated.</span></span> <span data-ttu-id="4070c-255">消息随即显示并且处理继续。</span><span class="sxs-lookup"><span data-stu-id="4070c-255">The message is displayed and processing continues.</span></span>

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

<span data-ttu-id="4070c-256">此示例显示 `$ErrorActionPreference` 默认值 **Inquire** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-256">This example shows the `$ErrorActionPreference` default value, **Inquire** .</span></span> <span data-ttu-id="4070c-257">将生成一个错误，并显示一个操作提示。</span><span class="sxs-lookup"><span data-stu-id="4070c-257">An error is generated and a prompt for action is shown.</span></span>

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

<span data-ttu-id="4070c-258">此示例显示 `$ErrorActionPreference` 设置为 **SilentlyContinue** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-258">This example shows the `$ErrorActionPreference` set to **SilentlyContinue** .</span></span>
<span data-ttu-id="4070c-259">错误消息将被取消。</span><span class="sxs-lookup"><span data-stu-id="4070c-259">The error message is suppressed.</span></span>

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

<span data-ttu-id="4070c-260">此示例显示 `$ErrorActionPreference` 设置为 " **停止** "。</span><span class="sxs-lookup"><span data-stu-id="4070c-260">This example shows the `$ErrorActionPreference` set to **Stop** .</span></span> <span data-ttu-id="4070c-261">它还显示生成到变量的额外对象 `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-261">It also shows the extra object generated to the `$Error` variable.</span></span>

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

### <a name="errorview"></a><span data-ttu-id="4070c-262">\$ErrorView</span><span class="sxs-lookup"><span data-stu-id="4070c-262">\$ErrorView</span></span>

<span data-ttu-id="4070c-263">确定 PowerShell 中错误消息的显示格式。</span><span class="sxs-lookup"><span data-stu-id="4070c-263">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="4070c-264">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-264">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-265">**NormalView** ： (默认) 为大多数用户设计的详细视图。</span><span class="sxs-lookup"><span data-stu-id="4070c-265">**NormalView** : (Default) A detailed view designed for most users.</span></span> <span data-ttu-id="4070c-266">包含错误说明和错误中涉及的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="4070c-266">Consists of a description of the error and the name of the object involved in the error.</span></span>
- <span data-ttu-id="4070c-267">**CategoryView** ：一种简洁的结构化视图，适用于生产环境。</span><span class="sxs-lookup"><span data-stu-id="4070c-267">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="4070c-268">其格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="4070c-268">The format is as follows:</span></span>

  <span data-ttu-id="4070c-269">{Category}： ( {TargetName}： {TargetType} ) ： [{Activity}]，{Reason}</span><span class="sxs-lookup"><span data-stu-id="4070c-269">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="4070c-270">有关 **CategoryView** 中的字段的详细信息，请参阅 [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) 类。</span><span class="sxs-lookup"><span data-stu-id="4070c-270">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-271">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-271">Examples</span></span>

<span data-ttu-id="4070c-272">此示例演示当的值 `$ErrorView` 为默认值 **NormalView** 时，如何显示错误。</span><span class="sxs-lookup"><span data-stu-id="4070c-272">This example shows how an error appears when the value of `$ErrorView` is the default, **NormalView** .</span></span> <span data-ttu-id="4070c-273">`Get-ChildItem` 用于查找不存在的文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-273">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="4070c-274">此示例演示当的值 `$ErrorView` 更改为 **CategoryView** 时出现的相同错误。</span><span class="sxs-lookup"><span data-stu-id="4070c-274">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView** .</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="4070c-275">此示例演示的值 `$ErrorView` 仅影响错误显示。</span><span class="sxs-lookup"><span data-stu-id="4070c-275">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="4070c-276">它不会更改自动变量中存储的错误对象的结构 `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-276">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="4070c-277">有关 `$Error` 自动变量的信息，请参阅 [about_automatic_variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-277">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="4070c-278">下面的命令使用与错误数组中的最新错误（ **元素 0** ）关联的 **ErrorRecord** 对象，并在列表中设置所有错误对象属性的格式。</span><span class="sxs-lookup"><span data-stu-id="4070c-278">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

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

### <a name="formatenumerationlimit"></a><span data-ttu-id="4070c-279">\$FormatEnumerationLimit</span><span class="sxs-lookup"><span data-stu-id="4070c-279">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="4070c-280">确定显示中包含多少个枚举项。</span><span class="sxs-lookup"><span data-stu-id="4070c-280">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="4070c-281">此变量不影响基础对象，仅影响显示。</span><span class="sxs-lookup"><span data-stu-id="4070c-281">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="4070c-282">如果的值 `$FormatEnumerationLimit` 小于枚举项的数目，则 PowerShell 会添加一个省略号 (`...`) 以指示未显示的项。</span><span class="sxs-lookup"><span data-stu-id="4070c-282">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="4070c-283">**有效值** ：整数 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-283">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="4070c-284">**默认值** ：4</span><span class="sxs-lookup"><span data-stu-id="4070c-284">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-285">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-285">Examples</span></span>

<span data-ttu-id="4070c-286">此示例演示如何使用 `$FormatEnumerationLimit` 变量来改善枚举项的显示。</span><span class="sxs-lookup"><span data-stu-id="4070c-286">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="4070c-287">此示例中的命令将生成一个表，该表列出了在计算机上运行的所有服务，一个用于 **运行** 服务，另一个用于 **已停止** 的服务。</span><span class="sxs-lookup"><span data-stu-id="4070c-287">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="4070c-288">它使用 `Get-Service` 命令获取所有服务，然后将结果通过管道发送到 `Group-Object` cmdlet，后者按服务状态对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="4070c-288">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="4070c-289">结果是一个表，其中列出了 " **名称** " 列中的状态和 " **组** " 列中的进程。</span><span class="sxs-lookup"><span data-stu-id="4070c-289">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="4070c-290">若要更改列标签，请使用哈希表，请参阅 [about_Hash_Tables](about_Hash_Tables.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-290">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="4070c-291">有关详细信息，请参阅 [格式表](xref:Microsoft.PowerShell.Utility.Format-Table)中的示例。</span><span class="sxs-lookup"><span data-stu-id="4070c-291">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="4070c-292">查找的当前值 `$FormatEnumerationLimit` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-292">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="4070c-293">列出按 **状态** 分组的所有服务。</span><span class="sxs-lookup"><span data-stu-id="4070c-293">List all services grouped by **Status** .</span></span> <span data-ttu-id="4070c-294">每个状态的 " **组** " 列中最多列出了四个服务，因为 `$FormatEnumerationLimit` 值为 **4** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-294">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4** .</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="4070c-295">若要增加列出的项数，请将的值增加 `$FormatEnumerationLimit` 到 **1000** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-295">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000** .</span></span> <span data-ttu-id="4070c-296">使用 `Get-Service` 和 `Group-Object` 显示服务。</span><span class="sxs-lookup"><span data-stu-id="4070c-296">Use `Get-Service` and `Group-Object` to display the services.</span></span>

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

<span data-ttu-id="4070c-297">`Format-Table`与 **Wrap** 参数一起使用以显示服务列表。</span><span class="sxs-lookup"><span data-stu-id="4070c-297">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

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

### <a name="informationpreference"></a><span data-ttu-id="4070c-298">\$InformationPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-298">\$InformationPreference</span></span>

<span data-ttu-id="4070c-299">`$InformationPreference`利用变量，可以设置要向用户显示的信息流首选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-299">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="4070c-300">具体而言，是通过添加 [写入信息](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet 添加到命令或脚本的信息性消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-300">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="4070c-301">如果使用 **InformationAction** 参数，则其值将覆盖变量的值 `$InformationPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-301">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="4070c-302">`Write-Information` 是在 PowerShell 5.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4070c-302">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="4070c-303">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-303">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-304">**Stop** ：在命令出现时停止命令或脚本 `Write-Information` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-304">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="4070c-305">**Inquire** ：显示你在命令中指定的信息性消息 `Write-Information` ，然后询问你是否要继续。</span><span class="sxs-lookup"><span data-stu-id="4070c-305">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="4070c-306">**继续** ：显示信息性消息，并继续运行。</span><span class="sxs-lookup"><span data-stu-id="4070c-306">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="4070c-307">**挂起** ：执行命令后，自动挂起工作流作业 `Write-Information` ，以允许用户在继续操作之前查看消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-307">**Suspend** : Automatically suspends a workflow job after a `Write-Information` command is carried out, to allow users to see the messages before continuing.</span></span> <span data-ttu-id="4070c-308">可以按用户的意愿恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="4070c-308">The workflow can be resumed at the user's discretion.</span></span>
- <span data-ttu-id="4070c-309">**SilentlyContinue** ： (默认值) 不起作用。</span><span class="sxs-lookup"><span data-stu-id="4070c-309">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="4070c-310">不显示信息性消息，该脚本将继续进行而不中断。</span><span class="sxs-lookup"><span data-stu-id="4070c-310">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="4070c-311">\$Log \* 事件</span><span class="sxs-lookup"><span data-stu-id="4070c-311">\$Log\*Event</span></span>

<span data-ttu-id="4070c-312">**日志 \* 事件** 首选项变量确定哪些类型的事件将写入事件查看器中的 PowerShell 事件日志。</span><span class="sxs-lookup"><span data-stu-id="4070c-312">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="4070c-313">默认情况下，只记录引擎和提供程序事件。</span><span class="sxs-lookup"><span data-stu-id="4070c-313">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="4070c-314">但你可以使用 **log \* 事件** 首选项变量来自定义日志，如记录有关命令的事件。</span><span class="sxs-lookup"><span data-stu-id="4070c-314">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="4070c-315">**日志 \* 事件** 首选项变量如下所示：</span><span class="sxs-lookup"><span data-stu-id="4070c-315">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="4070c-316">`$LogCommandHealthEvent`：记录命令初始化和处理中的错误和异常。</span><span class="sxs-lookup"><span data-stu-id="4070c-316">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="4070c-317">默认值为 `$false` (未记录) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-317">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="4070c-318">`$LogCommandLifecycleEvent`：记录命令和命令管道的启动和停止，以及命令发现中的安全异常。</span><span class="sxs-lookup"><span data-stu-id="4070c-318">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="4070c-319">默认值为 `$false` (未记录) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-319">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="4070c-320">`$LogEngineHealthEvent`：记录会话的错误和失败。</span><span class="sxs-lookup"><span data-stu-id="4070c-320">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="4070c-321">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-321">The default is `$true` (logged).</span></span>
- <span data-ttu-id="4070c-322">`$LogEngineLifecycleEvent`：记录会话的开始和结束。</span><span class="sxs-lookup"><span data-stu-id="4070c-322">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="4070c-323">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-323">The default is `$true` (logged).</span></span>
- <span data-ttu-id="4070c-324">`$LogProviderHealthEvent`：记录提供程序错误，如读取和写入错误、查找错误以及调用错误。</span><span class="sxs-lookup"><span data-stu-id="4070c-324">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="4070c-325">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-325">The default is `$true` (logged).</span></span>
- <span data-ttu-id="4070c-326">`$LogProviderLifecycleEvent`：日志添加和删除 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="4070c-326">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="4070c-327">默认值为 `$true` (记录) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-327">The default is `$true` (logged).</span></span> <span data-ttu-id="4070c-328">有关 PowerShell 提供程序的信息，请参阅 [about_Providers](about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-328">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="4070c-329">若要启用 **Log \* 事件** ，请键入变量，其值 `$true` 为，例如：</span><span class="sxs-lookup"><span data-stu-id="4070c-329">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="4070c-330">若要禁用事件类型，请使用值键入变量 `$false` ，例如：</span><span class="sxs-lookup"><span data-stu-id="4070c-330">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="4070c-331">启用的事件仅对当前 PowerShell 控制台有效。</span><span class="sxs-lookup"><span data-stu-id="4070c-331">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="4070c-332">若要将配置应用到所有控制台，请将变量设置保存到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="4070c-332">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="4070c-333">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-333">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumaliascount"></a><span data-ttu-id="4070c-334">\$MaximumAliasCount</span><span class="sxs-lookup"><span data-stu-id="4070c-334">\$MaximumAliasCount</span></span>

<span data-ttu-id="4070c-335">确定 PowerShell 会话中允许的别名数。</span><span class="sxs-lookup"><span data-stu-id="4070c-335">Determines how many aliases are permitted in a PowerShell session.</span></span> <span data-ttu-id="4070c-336">默认值为 **4096** ，应足以满足大多数使用的需要。</span><span class="sxs-lookup"><span data-stu-id="4070c-336">The default value is **4096** and that should be enough for most uses.</span></span> <span data-ttu-id="4070c-337">你可以调整 `$MaximumAliasCount` 以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="4070c-337">You can adjust `$MaximumAliasCount` to meet your needs.</span></span>

<span data-ttu-id="4070c-338">**有效值** ： 1024-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-338">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="4070c-339">**默认值** ：4096</span><span class="sxs-lookup"><span data-stu-id="4070c-339">**Default** : 4096</span></span>

<span data-ttu-id="4070c-340">若要统计系统中的别名，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-340">To count the aliases on your system, type:</span></span>

```powershell
(Get-Alias).count
```

### <a name="maximumdrivecount"></a><span data-ttu-id="4070c-341">\$MaximumDriveCount</span><span class="sxs-lookup"><span data-stu-id="4070c-341">\$MaximumDriveCount</span></span>

<span data-ttu-id="4070c-342">确定给定会话中允许的 PowerShell 驱动器数。</span><span class="sxs-lookup"><span data-stu-id="4070c-342">Determines how many PowerShell drives are permitted in a given session.</span></span> <span data-ttu-id="4070c-343">例如，文件系统驱动器和 PowerShell 提供程序公开的数据存储区，它们显示为驱动器，如 `Alias:` 和 `HKLM:` 驱动器。</span><span class="sxs-lookup"><span data-stu-id="4070c-343">For example, file system drives and data stores that are exposed by PowerShell providers and appear as drives, such as the `Alias:` and `HKLM:` drives.</span></span>

<span data-ttu-id="4070c-344">**有效值** ： 1024-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-344">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="4070c-345">**默认值** ：4096</span><span class="sxs-lookup"><span data-stu-id="4070c-345">**Default** : 4096</span></span>

<span data-ttu-id="4070c-346">若要统计系统中的别名，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-346">To count the aliases on your system, type:</span></span>

```powershell
(Get-PSDrive).count
```

### <a name="maximumerrorcount"></a><span data-ttu-id="4070c-347">\$MaximumErrorCount</span><span class="sxs-lookup"><span data-stu-id="4070c-347">\$MaximumErrorCount</span></span>

<span data-ttu-id="4070c-348">确定在会话的错误历史记录中保存的错误数。</span><span class="sxs-lookup"><span data-stu-id="4070c-348">Determines how many errors are saved in the error history for the session.</span></span>

<span data-ttu-id="4070c-349">**有效值** ： 256-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-349">**Valid values** : 256 - 32768 (`Int32`)</span></span>

<span data-ttu-id="4070c-350">**默认值** ：256</span><span class="sxs-lookup"><span data-stu-id="4070c-350">**Default** : 256</span></span>

<span data-ttu-id="4070c-351">表示每个保留错误的对象存储在 `$Error` 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="4070c-351">Objects that represent each retained error are stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="4070c-352">`$Error` 包含错误记录对象的数组。</span><span class="sxs-lookup"><span data-stu-id="4070c-352">`$Error` contains an array of error record objects.</span></span> <span data-ttu-id="4070c-353">最近的错误是数组中的第一个对象 `$Error[0]` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-353">The most recent error is the first object in the array, `$Error[0]`.</span></span>

<span data-ttu-id="4070c-354">若要对系统中的错误进行计数，请使用 `$Error` 数组的 **count** 属性。</span><span class="sxs-lookup"><span data-stu-id="4070c-354">To count the errors on your system, use the `$Error` array's **Count** property.</span></span>

```powershell
$Error.count
```

<span data-ttu-id="4070c-355">若要显示特定错误，请使用 `[0]` 数组表示法来查看最近的错误。</span><span class="sxs-lookup"><span data-stu-id="4070c-355">To display a specific error, use the `[0]` array notation to see the most recent error.</span></span>

```powershell
$Error[0]
```

<span data-ttu-id="4070c-356">若要显示最早的保留错误，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-356">To display the oldest retained error, type:</span></span>

```powershell
$Error[($Error.Count -1]
```

<span data-ttu-id="4070c-357">**Force** 参数重写 **ErrorRecord** 对象的特殊格式，并恢复为传统格式。</span><span class="sxs-lookup"><span data-stu-id="4070c-357">The **Force** parameter overrides the special formatting of **ErrorRecord** objects and reverts to the conventional format.</span></span> <span data-ttu-id="4070c-358">若要显示 **ErrorRecord** 对象的属性，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="4070c-358">To display the properties of the **ErrorRecord** object, type the following command:</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

<span data-ttu-id="4070c-359">在此示例中， `$Error.Count` 显示错误数。</span><span class="sxs-lookup"><span data-stu-id="4070c-359">In this example, `$Error.Count` displays the number of errors.</span></span> <span data-ttu-id="4070c-360">若要从错误历史记录中删除所有错误，请使用 `Clear` 错误数组的方法。</span><span class="sxs-lookup"><span data-stu-id="4070c-360">To delete all errors from the error history, use the `Clear` method of the error array.</span></span>

```powershell
$Error.Count
```

```Output
17
```

```powershell
$Error.Clear()
$Error.Count
```

```Output
0
```

<span data-ttu-id="4070c-361">若要查找错误数组的所有属性和方法，请使用 `Get-Member` 带有 **InputObject** 参数的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4070c-361">To find all properties and methods of an error array, use the `Get-Member` cmdlet with its **InputObject** parameter.</span></span> <span data-ttu-id="4070c-362">当使用 **InputObject** 参数时，将 `Get-Member` 显示集合的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="4070c-362">When you use the **InputObject** parameter, `Get-Member` displays the properties and methods of the collection.</span></span>

```powershell
Get-Member -InputObject $Error
```

<span data-ttu-id="4070c-363">将对象的集合传递给时 `Get-Member` ，会 `Get-Member` 显示集合中对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="4070c-363">When you pipe a collection of objects to `Get-Member`, `Get-Member` displays the properties and methods of the objects in the collection.</span></span>

```powershell
$Error | Get-Member
```

### <a name="maximumfunctioncount"></a><span data-ttu-id="4070c-364">\$MaximumFunctionCount</span><span class="sxs-lookup"><span data-stu-id="4070c-364">\$MaximumFunctionCount</span></span>

<span data-ttu-id="4070c-365">确定给定会话中允许的函数数。</span><span class="sxs-lookup"><span data-stu-id="4070c-365">Determines how many functions are permitted in a given session.</span></span>

<span data-ttu-id="4070c-366">**有效值** ： 1024-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-366">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="4070c-367">**默认值** ：4096</span><span class="sxs-lookup"><span data-stu-id="4070c-367">**Default** : 4096</span></span>

<span data-ttu-id="4070c-368">若要查看会话中的函数，请使用 `Function:` powershell 提供程序公开的 powershell 驱动器 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-368">To see the functions in your session, use the PowerShell `Function:` drive that is exposed by the PowerShell `Function` provider.</span></span> <span data-ttu-id="4070c-369">有关提供程序的详细信息 `Function` ，请 [about_Function_Provider](about_Function_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-369">For more information about the `Function` provider, [about_Function_Provider](about_Function_Provider.md).</span></span>

<span data-ttu-id="4070c-370">若要列出当前会话中的函数，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-370">To list the functions in the current session, type:</span></span>

```powershell
Get-ChildItem Function:
```

<span data-ttu-id="4070c-371">若要统计当前会话中的函数，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-371">To count the functions in the current session, type:</span></span>

```powershell
(Get-ChildItem Function:).Count
```

### <a name="maximumhistorycount"></a><span data-ttu-id="4070c-372">\$MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="4070c-372">\$MaximumHistoryCount</span></span>

<span data-ttu-id="4070c-373">确定在当前会话的命令历史记录中保存的命令数。</span><span class="sxs-lookup"><span data-stu-id="4070c-373">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="4070c-374">**有效值** ： 1-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-374">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="4070c-375">**默认值** ：4096</span><span class="sxs-lookup"><span data-stu-id="4070c-375">**Default** : 4096</span></span>

<span data-ttu-id="4070c-376">若要确定命令历史记录中当前保存的命令数，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-376">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="4070c-377">若要查看已保存在会话历史记录中的命令，请使用 `Get-History` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4070c-377">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="4070c-378">有关详细信息，请参阅 [about_History](about_History.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-378">For more information, see [about_History](about_History.md).</span></span>

### <a name="maximumvariablecount"></a><span data-ttu-id="4070c-379">\$MaximumVariableCount</span><span class="sxs-lookup"><span data-stu-id="4070c-379">\$MaximumVariableCount</span></span>

<span data-ttu-id="4070c-380">确定给定会话中允许的变量数，包括自动变量、首选项变量以及您在命令和脚本中创建的变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-380">Determines how many variables are permitted in a given session, including automatic variables, preference variables, and the variables that you create in commands and scripts.</span></span>

<span data-ttu-id="4070c-381">**有效值** ： 1024-32768 (`Int32`) </span><span class="sxs-lookup"><span data-stu-id="4070c-381">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="4070c-382">**默认值** ：4096</span><span class="sxs-lookup"><span data-stu-id="4070c-382">**Default** : 4096</span></span>

<span data-ttu-id="4070c-383">若要查看会话中的变量，请使用 `Get-Variable` cmdlet 以及 powershell `Variable:` 驱动器和 powershell `Variable` 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="4070c-383">To see the variables in your session, use the `Get-Variable` cmdlet and the features of the PowerShell `Variable:` drive and the PowerShell `Variable` provider.</span></span> <span data-ttu-id="4070c-384">有关信息，请参阅 [about_Variable_Provider](about_Variable_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-384">For information, see [about_Variable_Provider](about_Variable_Provider.md).</span></span>

<span data-ttu-id="4070c-385">若要查找系统上的当前变量数，请键入：</span><span class="sxs-lookup"><span data-stu-id="4070c-385">To find the current number of variables on the system, type:</span></span>

```powershell
(Get-Variable).Count
```

### <a name="ofs"></a><span data-ttu-id="4070c-386">\$.OFS</span><span class="sxs-lookup"><span data-stu-id="4070c-386">\$OFS</span></span>

<span data-ttu-id="4070c-387"> (.OFS 的输出字段分隔符) 指定将转换为字符串的数组元素分隔的字符。</span><span class="sxs-lookup"><span data-stu-id="4070c-387">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="4070c-388">**有效值** ：任何字符串。</span><span class="sxs-lookup"><span data-stu-id="4070c-388">**Valid values** : Any string.</span></span>

<span data-ttu-id="4070c-389">**默认值** ： Space</span><span class="sxs-lookup"><span data-stu-id="4070c-389">**Default** : Space</span></span>

<span data-ttu-id="4070c-390">默认情况下，该 `$OFS` 变量不存在，并且输出文件分隔符为空格，但您可以添加此变量并将其设置为任何字符串。</span><span class="sxs-lookup"><span data-stu-id="4070c-390">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="4070c-391">可以 `$OFS` 通过键入在会话中更改的值 `$OFS="<value>"` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-391">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="4070c-392">如果需要在 `" "` 脚本、模块或配置输出中 () 的空间的默认值，请小心，不要在 `$OFS` 代码中的其他位置更改默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-392">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-393">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-393">Examples</span></span>

<span data-ttu-id="4070c-394">此示例显示当数组转换为字符串时，将使用空格来分隔值。</span><span class="sxs-lookup"><span data-stu-id="4070c-394">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="4070c-395">在这种情况下，整数数组存储在一个变量中，然后将该变量强制转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="4070c-395">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="4070c-396">若要更改分隔符，请 `$OFS` 通过为变量赋值来添加变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-396">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="4070c-397">变量必须命名为 `$OFS` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-397">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="4070c-398">若要还原默认行为，可以 () 分配一个空格， `" "` `$OFS` 或删除该变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-398">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="4070c-399">以下命令将删除该变量，然后验证该分隔符是否为空格。</span><span class="sxs-lookup"><span data-stu-id="4070c-399">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="4070c-400">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="4070c-400">\$OutputEncoding</span></span>

<span data-ttu-id="4070c-401">确定 PowerShell 在向其他应用程序发送文本时所使用的字符编码方法。</span><span class="sxs-lookup"><span data-stu-id="4070c-401">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="4070c-402">例如，如果应用程序将 Unicode 字符串返回到 PowerShell，你可能需要将值更改为 **UnicodeEncoding** ，以便正确发送字符。</span><span class="sxs-lookup"><span data-stu-id="4070c-402">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="4070c-403">有效值如下：派生自编码类的对象，例如 **ASCIIEncoding** 、 **SBCSCodePageEncoding** 、 **UTF7Encoding** 、 **UTF8Encoding** 、 **UTF32Encoding** 和 **UnicodeEncoding** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-403">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding** .</span></span>

<span data-ttu-id="4070c-404">**默认值** ： ASCIIEncoding 对象 (ASCIIEncoding) </span><span class="sxs-lookup"><span data-stu-id="4070c-404">**Default** : ASCIIEncoding object (System.Text.ASCIIEncoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-405">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-405">Examples</span></span>

<span data-ttu-id="4070c-406">此示例演示如何在使用 Unicode 字符（如中文）为语言本地化的计算机上，使 Windows **findstr.exe** 命令在 PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="4070c-406">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="4070c-407">第一个命令查找值 `$OutputEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-407">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="4070c-408">由于值是编码对象，因此只显示其 **encoding.encodingname** 属性。</span><span class="sxs-lookup"><span data-stu-id="4070c-408">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="4070c-409">在此示例中， **findstr.exe** 命令用于搜索文件中存在的两个中文字符 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-409">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="4070c-410">在 Windows 命令提示符下运行此 **findstr.exe** 命令时 ( **cmd.exe** ) ， **findstr.exe** 将查找文本文件中的字符。</span><span class="sxs-lookup"><span data-stu-id="4070c-410">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="4070c-411">但是，当你在 PowerShell 中运行相同的 **findstr.exe** 命令时，将找不到这些字符，因为 PowerShell 会将它们发送到 ASCII 文本中的 **findstr.exe** 而不是 Unicode 文本。</span><span class="sxs-lookup"><span data-stu-id="4070c-411">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="4070c-412">若要在 PowerShell 中运行命令，请将的值设置 `$OutputEncoding` 为控制台的 **OutputEncoding** 属性的值，该属性基于为 Windows 选择的区域设置。</span><span class="sxs-lookup"><span data-stu-id="4070c-412">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="4070c-413">由于 **OutputEncoding** 是控制台的静态属性，因此请在命令中使用双冒号 (`::`) 。</span><span class="sxs-lookup"><span data-stu-id="4070c-413">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="4070c-414">编码更改后， **findstr.exe** 命令将查找 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="4070c-414">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="4070c-415">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-415">\$ProgressPreference</span></span>

<span data-ttu-id="4070c-416">确定 PowerShell 如何响应脚本、cmdlet 或提供程序生成的进度更新，如 [写入-进度](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet 生成的进度栏。</span><span class="sxs-lookup"><span data-stu-id="4070c-416">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="4070c-417">`Write-Progress`Cmdlet 可创建显示命令状态的进度栏。</span><span class="sxs-lookup"><span data-stu-id="4070c-417">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="4070c-418">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-418">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-419">**停止** ：不显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="4070c-419">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="4070c-420">相反，它将显示一条错误消息并停止执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-420">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="4070c-421">**Inquire** ：不显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="4070c-421">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="4070c-422">提示继续操作。</span><span class="sxs-lookup"><span data-stu-id="4070c-422">Prompts for permission to continue.</span></span> <span data-ttu-id="4070c-423">如果你通过 `Y` 或 `A` 进行回复，它会显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="4070c-423">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="4070c-424">**继续** ： (默认值) 显示进度栏，并继续执行操作。</span><span class="sxs-lookup"><span data-stu-id="4070c-424">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="4070c-425">**SilentlyContinue** ：执行命令，但不显示进度栏。</span><span class="sxs-lookup"><span data-stu-id="4070c-425">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="4070c-426">\$PSEmailServer</span><span class="sxs-lookup"><span data-stu-id="4070c-426">\$PSEmailServer</span></span>

<span data-ttu-id="4070c-427">指定用于发送电子邮件的默认电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="4070c-427">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="4070c-428">发送电子邮件的 cmdlet （如 [send-mailmessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet）使用此首选项变量。</span><span class="sxs-lookup"><span data-stu-id="4070c-428">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="4070c-429">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="4070c-429">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="4070c-430">为 cmdlet 和高级函数的参数指定默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-430">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="4070c-431">的值 `$PSDefaultParameterValues` 是一个哈希表，其中的键由 cmdlet 名称和参数名称组成，该名称由冒号 (`:`) 分隔。</span><span class="sxs-lookup"><span data-stu-id="4070c-431">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="4070c-432">值是指定的自定义默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-432">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="4070c-433">`$PSDefaultParameterValues` 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4070c-433">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="4070c-434">有关此首选项变量的详细信息，请参阅 [about_Parameters_Default_Values](about_Parameters_Default_Values.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-434">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="4070c-435">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-435">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="4070c-436">启用和禁用会话中模块的自动导入。</span><span class="sxs-lookup"><span data-stu-id="4070c-436">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="4070c-437">**All** 为默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-437">**All** is the default.</span></span> <span data-ttu-id="4070c-438">无论变量的值是什么，都可以使用 [import-module](xref:Microsoft.PowerShell.Core.Import-Module) 导入模块。</span><span class="sxs-lookup"><span data-stu-id="4070c-438">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="4070c-439">有效值是：</span><span class="sxs-lookup"><span data-stu-id="4070c-439">Valid values are:</span></span>

- <span data-ttu-id="4070c-440">**所有** ：首次使用时自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="4070c-440">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="4070c-441">若要导入模块，请获取或使用模块中的任何命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-441">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="4070c-442">例如，使用 `Get-Command`。</span><span class="sxs-lookup"><span data-stu-id="4070c-442">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="4070c-443">**ModuleQualified** ：仅当用户使用模块中的模块限定名称时，才会自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="4070c-443">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="4070c-444">例如，如果用户键入，则 `MyModule\MyCommand` PowerShell 将导入 **MyModule** 模块。</span><span class="sxs-lookup"><span data-stu-id="4070c-444">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="4070c-445">**None** ：在会话中禁用自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="4070c-445">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="4070c-446">若要导入模块，请使用 `Import-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4070c-446">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="4070c-447">有关自动导入模块的详细信息，请参阅 [about_Modules](about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-447">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="4070c-448">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="4070c-448">\$PSSessionApplicationName</span></span>

<span data-ttu-id="4070c-449">指定远程命令的默认应用程序名称，该命令使用 (WS-MANAGEMENT) 技术管理的 "Web 服务"。</span><span class="sxs-lookup"><span data-stu-id="4070c-449">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="4070c-450">有关详细信息，请参阅 [关于 Windows 远程管理](/windows/win32/winrm/about-windows-remote-management)。</span><span class="sxs-lookup"><span data-stu-id="4070c-450">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="4070c-451">系统默认应用程序名称为 `WSMAN` ，但你可以使用此首选项变量更改默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-451">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="4070c-452">应用程序名称是连接 URI 中的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="4070c-452">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="4070c-453">例如，下面的示例 URI 中的应用程序名称为 `WSMAN` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-453">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="4070c-454">如果远程命令未指定连接 URI 或应用程序名称，则使用默认应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="4070c-454">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="4070c-455">**WinRM** 服务使用应用程序名称来选择用于处理连接请求的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4070c-455">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="4070c-456">参数的值应与远程计算机上的侦听器的 **URLPrefix** 属性值相匹配。</span><span class="sxs-lookup"><span data-stu-id="4070c-456">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="4070c-457">若要覆盖系统默认值和此变量的值，并为特定会话选择不同的应用程序名称，请使用 [新的 PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)、 [Enter-Pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession)或 [调用命令](xref:Microsoft.PowerShell.Core.Invoke-Command)cmdlet 的 **ConnectionURI** 或 **ApplicationName** 参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-457">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="4070c-458">`$PSSessionApplicationName`首选项变量是在本地计算机上设置的，但它指定了远程计算机上的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4070c-458">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="4070c-459">如果你指定的应用程序名称在远程计算机上不存在，则用于建立会话的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="4070c-459">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="4070c-460">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="4070c-460">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="4070c-461">指定用于在当前会话中创建的 **pssession** 的默认会话配置。</span><span class="sxs-lookup"><span data-stu-id="4070c-461">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="4070c-462">此首选项变量是在本地计算机上设置的，但它指定了位于远程计算机上的会话配置。</span><span class="sxs-lookup"><span data-stu-id="4070c-462">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="4070c-463">变量的值 `$PSSessionConfigurationName` 是完全限定的资源 URI。</span><span class="sxs-lookup"><span data-stu-id="4070c-463">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="4070c-464">默认值 `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` 表示远程计算机上的 **Microsoft PowerShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="4070c-464">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="4070c-465">如果只指定配置名称，则会预置以下架构 URI：</span><span class="sxs-lookup"><span data-stu-id="4070c-465">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="4070c-466">你可以使用 **ConfigurationName** `New-PSSession` 、 `Enter-PSSession` 或 cmdlet 的 ConfigurationName 参数覆盖默认值，并为特定会话选择不同的会话配置 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-466">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="4070c-467">您可以随时更改此变量的值。</span><span class="sxs-lookup"><span data-stu-id="4070c-467">You can change the value of this variable at any time.</span></span> <span data-ttu-id="4070c-468">当你执行此操作时，请记住，你选择的会话配置必须在远程计算机上存在。</span><span class="sxs-lookup"><span data-stu-id="4070c-468">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="4070c-469">否则，创建使用会话配置的会话的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="4070c-469">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="4070c-470">当远程用户创建连接到此计算机的会话时，此首选项变量不会确定使用的本地会话配置。</span><span class="sxs-lookup"><span data-stu-id="4070c-470">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="4070c-471">但是，你可以使用本地会话配置的权限来确定哪些用户可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="4070c-471">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="4070c-472">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="4070c-472">\$PSSessionOption</span></span>

<span data-ttu-id="4070c-473">建立远程会话中高级用户选项的默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-473">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="4070c-474">这些选项首选项会替代会话选项的系统默认值。</span><span class="sxs-lookup"><span data-stu-id="4070c-474">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="4070c-475">`$PSSessionOption`变量包含 **PSSessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="4070c-475">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="4070c-476">有关详细信息，请参阅 [PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption)。</span><span class="sxs-lookup"><span data-stu-id="4070c-476">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="4070c-477">对象的每个属性都表示一个会话选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-477">Each property of the object represents a session option.</span></span> <span data-ttu-id="4070c-478">例如， **NoCompression** 属性将在会话期间启用数据压缩。</span><span class="sxs-lookup"><span data-stu-id="4070c-478">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="4070c-479">默认情况下，该 `$PSSessionOption` 变量包含一个 **PSSessionOption** 对象，该对象具有所有选项的默认值，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4070c-479">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

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

<span data-ttu-id="4070c-480">有关这些选项的说明和详细信息，请参阅 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。</span><span class="sxs-lookup"><span data-stu-id="4070c-480">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="4070c-481">有关远程命令和会话的详细信息，请参阅 [about_Remote](about_Remote.md) 和 [about_PSSessions](about_PSSessions.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-481">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="4070c-482">若要更改首选项变量的值 `$PSSessionOption` ，请使用 `New-PSSessionOption` cmdlet 创建一个 **PSSessionOption** 对象，该对象具有你喜欢的选项值。</span><span class="sxs-lookup"><span data-stu-id="4070c-482">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="4070c-483">将输出保存在一个名为的变量中 `$PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-483">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="4070c-484">若要 `$PSSessionOption` 在每个 powershell 会话中使用首选项变量，请将 `New-PSSessionOption` 创建该变量的命令添加 `$PSSessionOption` 到 powershell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="4070c-484">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="4070c-485">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-485">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="4070c-486">您可以为特定的远程会话设置自定义选项。</span><span class="sxs-lookup"><span data-stu-id="4070c-486">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="4070c-487">您设置的选项优先于系统默认值和 `$PSSessionOption` 首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="4070c-487">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="4070c-488">若要设置自定义会话选项，请使用 `New-PSSessionOption` cmdlet 创建 **PSSessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="4070c-488">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="4070c-489">然后，在创建会话的 cmdlet （例如、和）中，使用 **PSSessionOption** 对象作为 **SessionOption** 参数的值 `New-PSSession` `Enter-PSSession` `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-489">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="4070c-490">$Transcript</span><span class="sxs-lookup"><span data-stu-id="4070c-490">$Transcript</span></span>

<span data-ttu-id="4070c-491">用于 `Start-Transcript` 指定脚本文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="4070c-491">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="4070c-492">如果未指定 **path** 参数的值，则将 `Start-Transcript` 使用全局变量的值中的路径 `$Transcript` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-492">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="4070c-493">如果尚未创建此变量，请将这些 `Start-Transcript` 脚本 `$Home\My Documents` 作为文件存储在目录中 `\PowerShell_transcript.<time-stamp>.txt` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-493">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="4070c-494">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="4070c-494">\$VerbosePreference</span></span>

<span data-ttu-id="4070c-495">确定 PowerShell 如何响应脚本、cmdlet 或提供程序生成的详细消息，如 [写入-详细](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet 生成的消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-495">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="4070c-496">详细消息描述执行命令所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4070c-496">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="4070c-497">默认情况下，不显示详细消息，但是您可以通过更改的值来更改此行为 `$VerbosePreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-497">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="4070c-498">可以使用 cmdlet 的 **verbose** 通用参数来显示或隐藏特定命令的详细消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-498">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="4070c-499">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-499">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="4070c-500">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-500">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-501">**停止** ：显示详细消息和错误消息，然后停止执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-501">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="4070c-502">**Inquire** ：显示详细消息，然后显示一条提示，询问您是否要继续。</span><span class="sxs-lookup"><span data-stu-id="4070c-502">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="4070c-503">**继续** ：显示详细消息，然后继续执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-503">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="4070c-504">**SilentlyContinue** ： (默认) 不显示详细消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-504">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="4070c-505">继续执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-505">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-506">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-506">Examples</span></span>

<span data-ttu-id="4070c-507">这些示例显示了不同的值的效果 `$VerbosePreference` ，并显示了 **Verbose** 参数重写首选项值。</span><span class="sxs-lookup"><span data-stu-id="4070c-507">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="4070c-508">此示例显示 **SilentlyContinue** 值（这是默认值）的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-508">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="4070c-509">此命令使用 **message** 参数，但不会将消息写入 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="4070c-509">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="4070c-510">使用 **详细** 参数时，将写入消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-510">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="4070c-511">此示例显示了 **Continue** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-511">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="4070c-512">`$VerbosePreference`变量设置为 **Continue** ，并显示消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-512">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="4070c-513">此示例使用 **Verbose** 参数，该参数的值为 `$false` ，它将重写 **Continue** 值。</span><span class="sxs-lookup"><span data-stu-id="4070c-513">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="4070c-514">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-514">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="4070c-515">此示例显示了 **停止** 值的影响。</span><span class="sxs-lookup"><span data-stu-id="4070c-515">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="4070c-516">`$VerbosePreference`变量设置为 " **停止** "，并显示消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-516">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="4070c-517">命令已停止。</span><span class="sxs-lookup"><span data-stu-id="4070c-517">The command is stopped.</span></span>

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

<span data-ttu-id="4070c-518">此示例使用 **Verbose** 参数，该参数的值为 `$false` ，它将替代 **停止** 值。</span><span class="sxs-lookup"><span data-stu-id="4070c-518">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="4070c-519">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-519">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="4070c-520">此示例显示了 **Inquire** 值的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-520">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="4070c-521">`$VerbosePreference`变量设置为 **Inquire** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-521">The `$VerbosePreference` variable is set to **Inquire** .</span></span> <span data-ttu-id="4070c-522">消息随即显示，并提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-522">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="4070c-523">此示例使用带有 **Verbose** `$false` 替代 **Inquire** 值的值的详细参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-523">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="4070c-524">系统不会提示用户并且不显示消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-524">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="4070c-525">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-525">\$WarningPreference</span></span>

<span data-ttu-id="4070c-526">确定 PowerShell 如何响应脚本、cmdlet 或提供程序生成的警告消息，如 [写入警告](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet 生成的消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-526">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="4070c-527">默认情况下，会显示警告消息并继续执行，但你可以通过更改的值来更改此行为 `$WarningPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-527">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="4070c-528">可以使用 cmdlet 的 **WarningAction** common 参数确定 PowerShell 如何响应特定命令中的警告。</span><span class="sxs-lookup"><span data-stu-id="4070c-528">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="4070c-529">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4070c-529">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="4070c-530">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-530">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-531">**停止** ：显示警告消息和错误消息，然后停止执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-531">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="4070c-532">**Inquire** ：显示警告消息，然后提示继续操作。</span><span class="sxs-lookup"><span data-stu-id="4070c-532">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="4070c-533">**继续** ： (默认值) 显示警告消息，然后继续执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-533">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="4070c-534">**SilentlyContinue** ：不显示警告消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-534">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="4070c-535">继续执行。</span><span class="sxs-lookup"><span data-stu-id="4070c-535">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-536">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-536">Examples</span></span>

<span data-ttu-id="4070c-537">这些示例显示了不同的值的效果 `$WarningPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-537">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="4070c-538">**WarningAction** 参数将覆盖首选项值。</span><span class="sxs-lookup"><span data-stu-id="4070c-538">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="4070c-539">此示例显示默认值的效果，然后 **继续** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-539">This example shows the effect of the default value, **Continue** .</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="4070c-540">此示例使用值为 **SilentlyContinue** 的 **WarningAction** 参数来禁止显示警告。</span><span class="sxs-lookup"><span data-stu-id="4070c-540">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="4070c-541">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-541">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="4070c-542">此示例将 `$WarningPreference` 变量更改为 **SilentlyContinue** 值。</span><span class="sxs-lookup"><span data-stu-id="4070c-542">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="4070c-543">不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-543">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="4070c-544">此示例在生成警告时使用 **WarningAction** 参数停止。</span><span class="sxs-lookup"><span data-stu-id="4070c-544">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

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

<span data-ttu-id="4070c-545">此示例将 `$WarningPreference` 变量更改为 **Inquire** 值。</span><span class="sxs-lookup"><span data-stu-id="4070c-545">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="4070c-546">系统将提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="4070c-546">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="4070c-547">此示例使用值为 **SilentlyContinue** 的 **WarningAction** 参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-547">This example uses the **WarningAction** parameter with the value **SilentlyContinue** .</span></span> <span data-ttu-id="4070c-548">命令将继续执行，并且不会显示任何消息。</span><span class="sxs-lookup"><span data-stu-id="4070c-548">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="4070c-549">此示例将 `$WarningPreference` 值更改为 " **Stop** "。</span><span class="sxs-lookup"><span data-stu-id="4070c-549">This example changes the `$WarningPreference` value to **Stop** .</span></span>

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

<span data-ttu-id="4070c-550">此示例将 **WarningAction** 与 **Inquire** 值一起使用。</span><span class="sxs-lookup"><span data-stu-id="4070c-550">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="4070c-551">出现警告时，系统将提示用户。</span><span class="sxs-lookup"><span data-stu-id="4070c-551">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="4070c-552">\$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="4070c-552">\$WhatIfPreference</span></span>

<span data-ttu-id="4070c-553">确定是否自动为支持它的每个命令启用 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-553">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="4070c-554">启用 **WhatIf** 后，该 cmdlet 会报告命令的预期效果，但不会执行命令。</span><span class="sxs-lookup"><span data-stu-id="4070c-554">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="4070c-555">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="4070c-555">The valid values are as follows:</span></span>

- <span data-ttu-id="4070c-556">**False** ( **0** ，未启用) ： (默认) **WhatIf** 不自动启用。</span><span class="sxs-lookup"><span data-stu-id="4070c-556">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="4070c-557">若要手动启用此参数，请使用 cmdlet 的 **WhatIf** 参数。</span><span class="sxs-lookup"><span data-stu-id="4070c-557">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="4070c-558">**True** ( **1** ，已启用) ：自动对支持该功能的任何命令启用 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-558">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="4070c-559">用户可以使用值为 **False** 的 **WhatIf** 参数手动禁用它，如 `-WhatIf:$false` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-559">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="4070c-560">示例</span><span class="sxs-lookup"><span data-stu-id="4070c-560">Examples</span></span>

<span data-ttu-id="4070c-561">这些示例显示了不同的值的效果 `$WhatIfPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-561">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="4070c-562">它们演示如何使用 **WhatIf** 参数覆盖特定命令的首选项值。</span><span class="sxs-lookup"><span data-stu-id="4070c-562">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="4070c-563">此示例显示 `$WhatIfPreference` 变量设置为默认值 **False** 的影响。</span><span class="sxs-lookup"><span data-stu-id="4070c-563">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False** .</span></span> <span data-ttu-id="4070c-564">使用 `Get-ChildItem` 验证该文件是否存在。</span><span class="sxs-lookup"><span data-stu-id="4070c-564">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="4070c-565">`Remove-Item` 删除文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-565">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="4070c-566">删除文件后，可以通过验证删除 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-566">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

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

<span data-ttu-id="4070c-567">此示例演示在的值为 False 时使用 **WhatIf** 参数的效果 `$WhatIfPreference` 。 **False**</span><span class="sxs-lookup"><span data-stu-id="4070c-567">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False** .</span></span>

<span data-ttu-id="4070c-568">请确保该文件已存在。</span><span class="sxs-lookup"><span data-stu-id="4070c-568">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="4070c-569">使用 **WhatIf** 参数确定尝试删除文件的结果。</span><span class="sxs-lookup"><span data-stu-id="4070c-569">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="4070c-570">验证文件是否未被删除。</span><span class="sxs-lookup"><span data-stu-id="4070c-570">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="4070c-571">此示例显示 `$WhatIfPreference` 变量设置为值 **True** 后的效果。</span><span class="sxs-lookup"><span data-stu-id="4070c-571">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True** .</span></span> <span data-ttu-id="4070c-572">使用 `Remove-Item` 删除文件时，会显示文件的路径，但不会删除文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-572">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="4070c-573">尝试删除文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-573">Attempt to delete a file.</span></span> <span data-ttu-id="4070c-574">将显示一条消息，其中显示在运行时将会发生什么情况 `Remove-Item` ，但不会删除该文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-574">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="4070c-575">使用 `Get-ChildItem` 验证文件是否未被删除。</span><span class="sxs-lookup"><span data-stu-id="4070c-575">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="4070c-576">此示例演示如何在的值为 True 时删除文件 `$WhatIfPreference` 。 **True**</span><span class="sxs-lookup"><span data-stu-id="4070c-576">This example shows how to delete a file when the value of `$WhatIfPreference` is **True** .</span></span> <span data-ttu-id="4070c-577">它使用值为的 **WhatIf** 参数 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-577">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="4070c-578">使用 `Get-ChildItem` 验证是否已删除该文件。</span><span class="sxs-lookup"><span data-stu-id="4070c-578">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="4070c-579">下面是不 `Get-Process` 支持 **whatif** 并且 `Stop-Process` 支持 **whatif** 的 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="4070c-579">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf** .</span></span> <span data-ttu-id="4070c-580">`$WhatIfPreference`变量的值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-580">The `$WhatIfPreference` variable's value is **True** .</span></span>

<span data-ttu-id="4070c-581">`Get-Process` 不支持 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-581">`Get-Process` doesn't support **WhatIf** .</span></span> <span data-ttu-id="4070c-582">执行命令时，它将显示 **Winword** 进程。</span><span class="sxs-lookup"><span data-stu-id="4070c-582">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="4070c-583">`Stop-Process` 支持 **WhatIf** 。</span><span class="sxs-lookup"><span data-stu-id="4070c-583">`Stop-Process` does support **WhatIf** .</span></span> <span data-ttu-id="4070c-584">**Winword** 进程未停止。</span><span class="sxs-lookup"><span data-stu-id="4070c-584">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="4070c-585">您可以 `Stop-Process` 通过使用值为的 **whatif** 参数来重写 **whatif** 行为 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-585">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="4070c-586">**Winword** 进程已停止。</span><span class="sxs-lookup"><span data-stu-id="4070c-586">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="4070c-587">若要验证 **Winword** 进程是否已停止，请使用 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="4070c-587">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="4070c-588">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4070c-588">See also</span></span>

[<span data-ttu-id="4070c-589">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="4070c-589">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="4070c-590">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4070c-590">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="4070c-591">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="4070c-591">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="4070c-592">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="4070c-592">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="4070c-593">about_Remote</span><span class="sxs-lookup"><span data-stu-id="4070c-593">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="4070c-594">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="4070c-594">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="4070c-595">about_Variables</span><span class="sxs-lookup"><span data-stu-id="4070c-595">about_Variables</span></span>](about_Variables.md)
