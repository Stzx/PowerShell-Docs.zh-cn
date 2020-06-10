---
title: 关于 ShouldProcess 的各项须知内容
description: ShouldProcess 是一项经常被忽略的重要功能。 借助 WhatIf 和 Confirm 参数，可以将其轻松添加到函数中。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 1d9110302a191b90bd11bdf742f77704a8c9d6f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149480"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a><span data-ttu-id="77e21-104">关于 ShouldProcess 的各项须知内容</span><span class="sxs-lookup"><span data-stu-id="77e21-104">Everything you wanted to know about ShouldProcess</span></span>

<span data-ttu-id="77e21-105">PowerShell 函数有几项功能可以显著改善用户与它们交互的方式。</span><span class="sxs-lookup"><span data-stu-id="77e21-105">PowerShell functions have several features that greatly improve the way users interact with them.</span></span>
<span data-ttu-id="77e21-106">经常被忽略的一项重要功能是 `-WhatIf` 和 `-Confirm` 支持，可以轻松地将它添加到函数中。</span><span class="sxs-lookup"><span data-stu-id="77e21-106">One important feature that is often overlooked is `-WhatIf` and `-Confirm` support and it's easy to add to your functions.</span></span> <span data-ttu-id="77e21-107">本文将深入介绍如何实现此功能。</span><span class="sxs-lookup"><span data-stu-id="77e21-107">In this article, we dive deep into how to implement this feature.</span></span>

> [!NOTE]
> <span data-ttu-id="77e21-108">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="77e21-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="77e21-109">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="77e21-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="77e21-110">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="77e21-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

<span data-ttu-id="77e21-111">这是一个可以在函数中启用的简单功能，可为需要的用户提供一个安全网络。</span><span class="sxs-lookup"><span data-stu-id="77e21-111">This is a simple feature you can enable in your functions to provide a safety net for the users that need it.</span></span> <span data-ttu-id="77e21-112">没有什么比第一次执行一个你知道会有危险的命令更让人胆战心惊的了。</span><span class="sxs-lookup"><span data-stu-id="77e21-112">There's nothing scarier than running a command that you know can be dangerous for the first time.</span></span> <span data-ttu-id="77e21-113">而选择使用 `-WhatIf` 运行命令将会大有不同。</span><span class="sxs-lookup"><span data-stu-id="77e21-113">The option to run it with `-WhatIf` can make a big difference.</span></span>

## <a name="commonparameters"></a><span data-ttu-id="77e21-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="77e21-114">CommonParameters</span></span>

<span data-ttu-id="77e21-115">在探究如何实现这些[通用参数][]之前，我想快速介绍一下它们的用法。</span><span class="sxs-lookup"><span data-stu-id="77e21-115">Before we look at implementing these [common parameters][], I want to take a quick look at how they're used.</span></span>

## <a name="using--whatif"></a><span data-ttu-id="77e21-116">使用 -WhatIf</span><span class="sxs-lookup"><span data-stu-id="77e21-116">Using -WhatIf</span></span>

<span data-ttu-id="77e21-117">当命令支持 `-WhatIf` 参数时，它允许你查看命令将执行的操作，而不是进行更改。</span><span class="sxs-lookup"><span data-stu-id="77e21-117">When a command supports the `-WhatIf` parameter, it allows you to see what the command would have done instead of making changes.</span></span> <span data-ttu-id="77e21-118">这是测试命令影响的好方法，特别是在执行某些破坏性操作前。</span><span class="sxs-lookup"><span data-stu-id="77e21-118">it's a good way to test out the impact of a command, especially before you do something destructive.</span></span>

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="77e21-119">如果命令可正确实现 `ShouldProcess`，它应显示它所做的所有更改。</span><span class="sxs-lookup"><span data-stu-id="77e21-119">If the command correctly implements `ShouldProcess`, it should show you all the changes that it would have made.</span></span> <span data-ttu-id="77e21-120">下面是使用通配符删除多个文件的示例。</span><span class="sxs-lookup"><span data-stu-id="77e21-120">Here is an example using a wildcard to delete multiple files.</span></span>

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a><span data-ttu-id="77e21-121">使用 -Confirm</span><span class="sxs-lookup"><span data-stu-id="77e21-121">Using -Confirm</span></span>

<span data-ttu-id="77e21-122">支持 `-WhatIf` 的命令也支持 `-Confirm`。</span><span class="sxs-lookup"><span data-stu-id="77e21-122">Commands that support `-WhatIf` also support `-Confirm`.</span></span> <span data-ttu-id="77e21-123">这提供了在执行操作前进行确认的机会。</span><span class="sxs-lookup"><span data-stu-id="77e21-123">This gives you a chance confirm an action before performing it.</span></span>

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="77e21-124">在这种情况下，可以使用多个选项来继续、跳过更改或停止脚本。</span><span class="sxs-lookup"><span data-stu-id="77e21-124">In this case, you have multiple options that allow you to continue, skip a change, or stop the script.</span></span> <span data-ttu-id="77e21-125">“帮助”提示会按如下所述对这些选项进行说明。</span><span class="sxs-lookup"><span data-stu-id="77e21-125">The help prompt describes each of those options like this.</span></span>

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a><span data-ttu-id="77e21-126">本地化</span><span class="sxs-lookup"><span data-stu-id="77e21-126">Localization</span></span>

<span data-ttu-id="77e21-127">此提示已在 PowerShell 中本地化，因此将根据操作系统的语言来更改语言。</span><span class="sxs-lookup"><span data-stu-id="77e21-127">This prompt is localized in PowerShell so the language changes based on the language of your operating system.</span></span> <span data-ttu-id="77e21-128">这是 PowerShell 为你管理的另一项内容。</span><span class="sxs-lookup"><span data-stu-id="77e21-128">This is one more thing that PowerShell manages for you.</span></span>

### <a name="switch-parameters"></a><span data-ttu-id="77e21-129">开关参数</span><span class="sxs-lookup"><span data-stu-id="77e21-129">Switch parameters</span></span>

<span data-ttu-id="77e21-130">让我们快速了解一下将值传递给开关参数的方式。</span><span class="sxs-lookup"><span data-stu-id="77e21-130">Let's take quick moment to look at ways to pass a value to a switch parameter.</span></span> <span data-ttu-id="77e21-131">提到这一点的主要原因是，经常需要将参数值传递给调用的函数。</span><span class="sxs-lookup"><span data-stu-id="77e21-131">The main reason I call this out is that you often want to pass parameter values to functions you call.</span></span>

<span data-ttu-id="77e21-132">第一种方法是一种特定的参数语法，该语法可用于所有参数，但通常会将其用于开关参数。</span><span class="sxs-lookup"><span data-stu-id="77e21-132">The first approach is a specific parameter syntax that can be used for all parameters but you mostly see it used for switch parameters.</span></span> <span data-ttu-id="77e21-133">指定一个冒号以向参数附加值。</span><span class="sxs-lookup"><span data-stu-id="77e21-133">You specify a colon to attach a value to the parameter.</span></span>

```powershell
Remove-Item -Path:* -WhatIf:$true
```

<span data-ttu-id="77e21-134">可以使用变量执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="77e21-134">You can do the same with a variable.</span></span>

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

<span data-ttu-id="77e21-135">第二种方法是使用哈希表来展开值。</span><span class="sxs-lookup"><span data-stu-id="77e21-135">The second approach is to use a hashtable to splat the value.</span></span>

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

<span data-ttu-id="77e21-136">如果你不熟悉哈希表或展开操作，请参阅我的另一篇文章[关于哈希表的各项须知内容][]。</span><span class="sxs-lookup"><span data-stu-id="77e21-136">If you're new to hashtables or splatting, I have another article on that covers [everything you wanted to know about hashtables][].</span></span>

## <a name="supportsshouldprocess"></a><span data-ttu-id="77e21-137">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="77e21-137">SupportsShouldProcess</span></span>

<span data-ttu-id="77e21-138">启用 `-WhatIf` 和 `-Confirm` 支持的第一步是，在函数的 `CmdletBinding` 中指定 `SupportsShouldProcess`。</span><span class="sxs-lookup"><span data-stu-id="77e21-138">The first step to enable `-WhatIf` and `-Confirm` support is to specify `SupportsShouldProcess` in the `CmdletBinding` of your function.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

<span data-ttu-id="77e21-139">以这种方式指定 `SupportsShouldProcess` 后，就可以使用 `-WhatIf`（或 `-Confirm`）来调用函数了。</span><span class="sxs-lookup"><span data-stu-id="77e21-139">By specifying `SupportsShouldProcess` in this way, we can now call our function with `-WhatIf` (or `-Confirm`).</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="77e21-140">请注意，我没有创建名为 `-WhatIf` 的参数。</span><span class="sxs-lookup"><span data-stu-id="77e21-140">Notice that I did not create a parameter called `-WhatIf`.</span></span> <span data-ttu-id="77e21-141">指定 `SupportsShouldProcess` 会自动为我们创建该参数。</span><span class="sxs-lookup"><span data-stu-id="77e21-141">Specifying `SupportsShouldProcess` automatically creates it for us.</span></span> <span data-ttu-id="77e21-142">当我们在 `Test-ShouldProcess` 上指定 `-WhatIf` 参数时，我们调用的某些项也会执行 `-WhatIf` 处理。</span><span class="sxs-lookup"><span data-stu-id="77e21-142">When we specify the `-WhatIf` parameter on `Test-ShouldProcess`, some things we call also perform `-WhatIf` processing.</span></span>

### <a name="trust-but-verify"></a><span data-ttu-id="77e21-143">信任但验证</span><span class="sxs-lookup"><span data-stu-id="77e21-143">Trust but verify</span></span>

<span data-ttu-id="77e21-144">在这里，相信调用的所有内容都可继承 `-WhatIf` 值是有些危险的。</span><span class="sxs-lookup"><span data-stu-id="77e21-144">There's some danger here trusting that everything you call inherits `-WhatIf` values.</span></span> <span data-ttu-id="77e21-145">对于其余的示例，我将假设它不起作用，并且在调用其他命令时非常明确。</span><span class="sxs-lookup"><span data-stu-id="77e21-145">For the rest of the examples, I'm going to assume that it doesn't work and be very explicit when making calls to other commands.</span></span> <span data-ttu-id="77e21-146">我建议你也这样做。</span><span class="sxs-lookup"><span data-stu-id="77e21-146">I recommend that you do the same.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIf
}
```

<span data-ttu-id="77e21-147">当你能够更好地了解所涉及的所有操作后，我会在后续部分再次讨论其中的细微差别。</span><span class="sxs-lookup"><span data-stu-id="77e21-147">I will revisit the nuances much later once you have a better understanding of all the pieces in play.</span></span>

## <a name="pscmdletshouldprocess"></a><span data-ttu-id="77e21-148">$PSCmdlet.ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="77e21-148">$PSCmdlet.ShouldProcess</span></span>

<span data-ttu-id="77e21-149">允许你实现 `SupportsShouldProcess` 的方法是 `$PSCmdlet.ShouldProcess`。</span><span class="sxs-lookup"><span data-stu-id="77e21-149">The method that allows you to implement `SupportsShouldProcess` is `$PSCmdlet.ShouldProcess`.</span></span> <span data-ttu-id="77e21-150">调用 `$PSCmdlet.ShouldProcess(...)` 来查看是否应该处理一些逻辑，而 PowerShell 会处理其余部分。</span><span class="sxs-lookup"><span data-stu-id="77e21-150">You call `$PSCmdlet.ShouldProcess(...)` to see if you should process some logic and PowerShell takes care of the rest.</span></span> <span data-ttu-id="77e21-151">我们从一个示例开始：</span><span class="sxs-lookup"><span data-stu-id="77e21-151">Let's start with an example:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        $file.Delete()
    }
}
```

<span data-ttu-id="77e21-152">调用 `$PSCmdlet.ShouldProcess($file.name)` 检查 `-WhatIf`（和 `-Confirm` 参数），然后对其进行相应处理。</span><span class="sxs-lookup"><span data-stu-id="77e21-152">The call to `$PSCmdlet.ShouldProcess($file.name)` checks for the `-WhatIf` (and `-Confirm` parameter) then handles it accordingly.</span></span> <span data-ttu-id="77e21-153">`-WhatIf` 会导致 `ShouldProcess` 输出更改说明并返回 `$false`：</span><span class="sxs-lookup"><span data-stu-id="77e21-153">The `-WhatIf` causes `ShouldProcess` to output a description of the change and return `$false`:</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

<span data-ttu-id="77e21-154">使用 `-Confirm` 的调用会使脚本暂停，并提示用户选择是否要继续。</span><span class="sxs-lookup"><span data-stu-id="77e21-154">A call using `-Confirm` pauses the script and prompts the user with the option to continue.</span></span> <span data-ttu-id="77e21-155">如果用户选择 `Y`，它将返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="77e21-155">It returns `$true` if the user selected `Y`.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="77e21-156">`$PSCmdlet.ShouldProcess` 的一项出色功能是，它可同时提供更为详细的输出结果。</span><span class="sxs-lookup"><span data-stu-id="77e21-156">An awesome feature of `$PSCmdlet.ShouldProcess` is that it doubles as verbose output.</span></span> <span data-ttu-id="77e21-157">在实现 `ShouldProcess`时，我经常依赖这一功能。</span><span class="sxs-lookup"><span data-stu-id="77e21-157">I depend on this often when implementing `ShouldProcess`.</span></span>

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a><span data-ttu-id="77e21-158">重载</span><span class="sxs-lookup"><span data-stu-id="77e21-158">Overloads</span></span>

<span data-ttu-id="77e21-159">`$PSCmdlet.ShouldProcess` 有几个不同的重载，可使用不同的参数来自定义消息传递。</span><span class="sxs-lookup"><span data-stu-id="77e21-159">There are a few different overloads for `$PSCmdlet.ShouldProcess` with different parameters for customizing the messaging.</span></span> <span data-ttu-id="77e21-160">在上面的示例中，我们已经看到了第一种重载。</span><span class="sxs-lookup"><span data-stu-id="77e21-160">We already saw the first one in the example above.</span></span> <span data-ttu-id="77e21-161">下面对其进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="77e21-161">Let's take a closer look at it.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

<span data-ttu-id="77e21-162">这会生成包含函数名称和目标（参数值）的输出。</span><span class="sxs-lookup"><span data-stu-id="77e21-162">This produces output that includes both the function name and the target (value of the parameter).</span></span>

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

<span data-ttu-id="77e21-163">指定第二个参数，因为操作使用操作值，而非消息中的函数名称。</span><span class="sxs-lookup"><span data-stu-id="77e21-163">Specifying a second parameter as the operation uses the operation value instead of the function name in the message.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

<span data-ttu-id="77e21-164">下一选项是指定三个参数来完全自定义消息。</span><span class="sxs-lookup"><span data-stu-id="77e21-164">The next option is to specify three parameters to fully customize the message.</span></span> <span data-ttu-id="77e21-165">使用三个参数时，第一个参数是整个消息。</span><span class="sxs-lookup"><span data-stu-id="77e21-165">When three parameters are used, the first one is the entire message.</span></span> <span data-ttu-id="77e21-166">后两个参数仍在 `-Confirm` 消息输出中使用。</span><span class="sxs-lookup"><span data-stu-id="77e21-166">The second two parameters are still used in the `-Confirm` message output.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a><span data-ttu-id="77e21-167">快速参数参考</span><span class="sxs-lookup"><span data-stu-id="77e21-167">Quick parameter reference</span></span>

<span data-ttu-id="77e21-168">如果你阅读本文只是想知道应使用哪些参数，我在这里提供了一个快速参考，介绍了参数在不同的 `-WhatIf` 场景中更改消息的方式。</span><span class="sxs-lookup"><span data-stu-id="77e21-168">Just in case you came here only to figure out what parameters you should use, here is a quick reference showing how the parameters change the message in the different `-WhatIf` scenarios.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

<span data-ttu-id="77e21-169">我倾向于使用有两个参数的选项。</span><span class="sxs-lookup"><span data-stu-id="77e21-169">I tend to use the one with two parameters.</span></span>

### <a name="shouldprocessreason"></a><span data-ttu-id="77e21-170">ShouldProcessReason</span><span class="sxs-lookup"><span data-stu-id="77e21-170">ShouldProcessReason</span></span>

<span data-ttu-id="77e21-171">第四个重载比其他重载的功能更强大。</span><span class="sxs-lookup"><span data-stu-id="77e21-171">We have a fourth overload that's more advanced than the others.</span></span> <span data-ttu-id="77e21-172">它可获取执行 `ShouldProcess` 的原因。</span><span class="sxs-lookup"><span data-stu-id="77e21-172">It allows you to get the reason `ShouldProcess` was executed.</span></span> <span data-ttu-id="77e21-173">我在这里添加此内容只是为了内容完整，因为我们也可以直接查看 `$WhatIf` 是否为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="77e21-173">I'm only adding this here for completeness because we can just check if `$WhatIf` is `$true` instead.</span></span>

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

<span data-ttu-id="77e21-174">必须通过 `[ref]` 将 `$reason` 变量作为引用变量传入第四个参数。</span><span class="sxs-lookup"><span data-stu-id="77e21-174">We have to pass the `$reason` variable into the fourth parameter as a reference variable with `[ref]`.</span></span> <span data-ttu-id="77e21-175">`ShouldProcess` 用 `None` 或 `WhatIf` 值填充 `$reason`。</span><span class="sxs-lookup"><span data-stu-id="77e21-175">`ShouldProcess` populates `$reason` with the value `None` or `WhatIf`.</span></span> <span data-ttu-id="77e21-176">我没有说这样做有用，也从来没有使用它的理由。</span><span class="sxs-lookup"><span data-stu-id="77e21-176">I didn't say this was useful and I have had no reason to ever use it.</span></span>

### <a name="where-to-place-it"></a><span data-ttu-id="77e21-177">放置位置</span><span class="sxs-lookup"><span data-stu-id="77e21-177">Where to place it</span></span>

<span data-ttu-id="77e21-178">可使用 `ShouldProcess` 让脚本更安全。</span><span class="sxs-lookup"><span data-stu-id="77e21-178">You use `ShouldProcess` to make your scripts safer.</span></span> <span data-ttu-id="77e21-179">因此，可以在脚本进行更改时使用它。</span><span class="sxs-lookup"><span data-stu-id="77e21-179">So you use it when your scripts are making changes.</span></span> <span data-ttu-id="77e21-180">我喜欢将 `$PSCmdlet.ShouldProcess` 调用放在尽可能接近更改的位置。</span><span class="sxs-lookup"><span data-stu-id="77e21-180">I like to place the `$PSCmdlet.ShouldProcess` call as close to the change as possible.</span></span>

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

<span data-ttu-id="77e21-181">如果我正在处理一个项集合，我会为每一项调用它。</span><span class="sxs-lookup"><span data-stu-id="77e21-181">If I'm processing a collection of items, I call it for each item.</span></span> <span data-ttu-id="77e21-182">因此调用会置于 Foreach 循环中。</span><span class="sxs-lookup"><span data-stu-id="77e21-182">So the call gets placed inside the foreach loop.</span></span>

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

<span data-ttu-id="77e21-183">我将 `ShouldProcess` 紧密地放在更改周围的原因是，我希望在指定 `-WhatIf` 时尽可能多地执行代码。</span><span class="sxs-lookup"><span data-stu-id="77e21-183">The reason why I place `ShouldProcess` tightly around the change, is that I want as much code to execute as possible when `-WhatIf` is specified.</span></span> <span data-ttu-id="77e21-184">如果可能，我希望运行设置和验证，以便用户可以看到这些错误。</span><span class="sxs-lookup"><span data-stu-id="77e21-184">I want the setup and validation to run if possible so the user gets to see those errors.</span></span>

<span data-ttu-id="77e21-185">我还喜欢在验证我的项目的 Pester 测试中使用它。</span><span class="sxs-lookup"><span data-stu-id="77e21-185">I also like to use this in my Pester tests that validate my projects.</span></span> <span data-ttu-id="77e21-186">如果我在 Pester 中有一段难以模拟的逻辑，我通常会将其包装在 `ShouldProcess` 中，并在测试中使用 `-WhatIf` 来调用它。</span><span class="sxs-lookup"><span data-stu-id="77e21-186">If I have a piece of logic that is hard to mock in pester, I can often wrap it in `ShouldProcess` and call it with `-WhatIf` in my tests.</span></span> <span data-ttu-id="77e21-187">测试一部分代码总比不测试任何代码好。</span><span class="sxs-lookup"><span data-stu-id="77e21-187">It's better to test some of your code than none of it.</span></span>

### <a name="whatifpreference"></a><span data-ttu-id="77e21-188">$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="77e21-188">$WhatIfPreference</span></span>

<span data-ttu-id="77e21-189">我们拥有的第一个首选项变量是 `$WhatIfPreference`。</span><span class="sxs-lookup"><span data-stu-id="77e21-189">The first preference variable we have is `$WhatIfPreference`.</span></span> <span data-ttu-id="77e21-190">默认为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="77e21-190">This is `$false` by default.</span></span> <span data-ttu-id="77e21-191">如果将其设置为 `$true`，则函数的执行方式与指定 `-WhatIf` 时相同。</span><span class="sxs-lookup"><span data-stu-id="77e21-191">If you set it to `$true` then your function executes as if you specified `-WhatIf`.</span></span> <span data-ttu-id="77e21-192">如果在会话中按此设置，所有命令都将执行 `-WhatIf` 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="77e21-192">If you set this in your session, all commands perform `-WhatIf` execution.</span></span>

<span data-ttu-id="77e21-193">使用 `-WhatIf` 调用函数时，`$WhatIfPreference` 的值将在函数的作用域内设置为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="77e21-193">When you call a function with `-WhatIf`, the value of `$WhatIfPreference` gets set to `$true` inside the scope of your function.</span></span>

## <a name="confirmimpact"></a><span data-ttu-id="77e21-194">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="77e21-194">ConfirmImpact</span></span>

<span data-ttu-id="77e21-195">虽然我的大多数示例都是针对 `-WhatIf` 的，但到目前为止，所有这些也可以通过 `-Confirm` 来提示用户。</span><span class="sxs-lookup"><span data-stu-id="77e21-195">Most of my examples are for `-WhatIf` but everything so far also works with `-Confirm` to prompt the user.</span></span> <span data-ttu-id="77e21-196">可以将函数的 `ConfirmImpact` 设置为“高”，它会对用户进行提示，就像用 `-Confirm` 对其调用一样。</span><span class="sxs-lookup"><span data-stu-id="77e21-196">You can set the `ConfirmImpact` of the function to high and it prompts the user as if it was called with `-Confirm`.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param()

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="77e21-197">由于 `High` 的影响，此 `Test-ShouldProcess` 调用将执行 `-Confirm` 操作。</span><span class="sxs-lookup"><span data-stu-id="77e21-197">This call to `Test-ShouldProcess` is performing the `-Confirm` action because of the `High` impact.</span></span>

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

<span data-ttu-id="77e21-198">最明显的问题是，如果不提示用户，它会更难以在其他脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="77e21-198">The obvious issue is that now it's harder to use in other scripts without prompting the user.</span></span> <span data-ttu-id="77e21-199">在这种情况下，我们可以将 `$false` 传递给 `-Confirm` 以取消提示。</span><span class="sxs-lookup"><span data-stu-id="77e21-199">In this case, we can pass a `$false` to `-Confirm` to suppress the prompt.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

<span data-ttu-id="77e21-200">我将在后面的部分介绍如何添加 `-Force` 支持。</span><span class="sxs-lookup"><span data-stu-id="77e21-200">I'll cover how to add `-Force` support in a later section.</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="77e21-201">$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="77e21-201">$ConfirmPreference</span></span>

<span data-ttu-id="77e21-202">`$ConfirmPreference` 是一个自动变量，可控制 `ConfirmImpact` 要求你确认执行的时间。</span><span class="sxs-lookup"><span data-stu-id="77e21-202">`$ConfirmPreference` is an automatic variable that controls when `ConfirmImpact` asks you to confirm execution.</span></span> <span data-ttu-id="77e21-203">下面是 `$ConfirmPreference` 和 `ConfirmImpact` 的可能值。</span><span class="sxs-lookup"><span data-stu-id="77e21-203">Here are the possible values for both `$ConfirmPreference` and `ConfirmImpact`.</span></span>

- `High`
- `Medium`
- `Low`
- `None`

<span data-ttu-id="77e21-204">利用这些值，可以为每个函数指定不同的影响级别。</span><span class="sxs-lookup"><span data-stu-id="77e21-204">With these values, you can specify different levels of impact for each function.</span></span> <span data-ttu-id="77e21-205">如果将 `$ConfirmPreference` 设置为高于 `ConfirmImpact` 的值，则不会提示你确认执行。</span><span class="sxs-lookup"><span data-stu-id="77e21-205">If you have `$ConfirmPreference` set to a value higher than `ConfirmImpact`, then you aren't prompted to confirm execution.</span></span>

<span data-ttu-id="77e21-206">默认情况下，`$ConfirmPreference` 设置为 `High`，`ConfirmImpact` 设置为 `Medium`。</span><span class="sxs-lookup"><span data-stu-id="77e21-206">By default, `$ConfirmPreference` is set to `High` and `ConfirmImpact` is `Medium`.</span></span> <span data-ttu-id="77e21-207">如果希望函数自动提示用户，请将 `ConfirmImpact` 设置为 `High`。</span><span class="sxs-lookup"><span data-stu-id="77e21-207">If you want your function to automatically prompt the user, set your `ConfirmImpact` to `High`.</span></span> <span data-ttu-id="77e21-208">否则，如果命令具有破坏性，则将其设置为`Medium`；如果命令在生产环境中始终安全运行，则设置为 `Low`。</span><span class="sxs-lookup"><span data-stu-id="77e21-208">Otherwise set it to `Medium` if its destructive and use `Low` if the command is always safe run in production.</span></span> <span data-ttu-id="77e21-209">如果将其设置为 `none`，即使指定了 `-Confirm`，它也不会出现提示（但仍提供 `-WhatIf` 支持）。</span><span class="sxs-lookup"><span data-stu-id="77e21-209">If you set it to `none`, it doesn't prompt even if `-Confirm` was specified (but it still gives you `-WhatIf` support).</span></span>

<span data-ttu-id="77e21-210">使用 `-Confirm` 调用函数时，`$ConfirmPreference` 的值将在函数的作用域内设置为 `Low`。</span><span class="sxs-lookup"><span data-stu-id="77e21-210">When calling a function with `-Confirm`, the value of `$ConfirmPreference` gets set to `Low` inside the scope of your function.</span></span>

### <a name="suppressing-nested-confirm-prompts"></a><span data-ttu-id="77e21-211">取消嵌套确认提示</span><span class="sxs-lookup"><span data-stu-id="77e21-211">Suppressing nested confirm prompts</span></span>

<span data-ttu-id="77e21-212">可以通过调用的函数选取 `$ConfirmPreference`。</span><span class="sxs-lookup"><span data-stu-id="77e21-212">The `$ConfirmPreference` can get picked up by functions that you call.</span></span> <span data-ttu-id="77e21-213">这可能会导致以下情况：你添加了确认提示，调用的函数也会提示用户。</span><span class="sxs-lookup"><span data-stu-id="77e21-213">This can create scenarios where you add a confirm prompt and the function you call also prompts the user.</span></span>

<span data-ttu-id="77e21-214">我想要做的是，在处理完提示后在调用的命令上指定 `-Confirm:$false`。</span><span class="sxs-lookup"><span data-stu-id="77e21-214">What I tend to do is specify `-Confirm:$false` on the commands that I call when I have already handled the prompting.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        Remove-Item -Path $file.FullName -Confirm:$false
    }
}
```

<span data-ttu-id="77e21-215">这就把我们带回到一个之前讨论的问题：在 `-WhatIf` 未传递给函数时和 `-Confirm` 传递给函数时存在一些细微差别。</span><span class="sxs-lookup"><span data-stu-id="77e21-215">This brings us back to an earlier warning: There are nuances as to when `-WhatIf` is not passed to a function and when `-Confirm` passes to a function.</span></span> <span data-ttu-id="77e21-216">我保证晚点会再来讲这一点。</span><span class="sxs-lookup"><span data-stu-id="77e21-216">I promise I'll get back to this later.</span></span>

## <a name="pscmdletshouldcontinue"></a><span data-ttu-id="77e21-217">$PSCmdlet.ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="77e21-217">$PSCmdlet.ShouldContinue</span></span>

<span data-ttu-id="77e21-218">如果需要获得更多的控制（与 `ShouldProcess` 提供的控制相比），可以直接用 `ShouldContinue` 来触发提示。</span><span class="sxs-lookup"><span data-stu-id="77e21-218">If you need more control than `ShouldProcess` provides, you can trigger the prompt directly with `ShouldContinue`.</span></span> <span data-ttu-id="77e21-219">`ShouldContinue` 会忽略 `$ConfirmPreference`、`ConfirmImpact`、`-Confirm`、`$WhatIfPreference`和 `-WhatIf`，因为它会在每次执行时进行提示。</span><span class="sxs-lookup"><span data-stu-id="77e21-219">`ShouldContinue` ignores `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference`, and `-WhatIf` because it prompts every time it's executed.</span></span>

<span data-ttu-id="77e21-220">乍一看，很容易将 `ShouldProcess` 和 `ShouldContinue` 混淆。</span><span class="sxs-lookup"><span data-stu-id="77e21-220">At a quick glance, it's easy to confuse `ShouldProcess` and `ShouldContinue`.</span></span> <span data-ttu-id="77e21-221">我通常会记得使用 `ShouldProcess`，因为该参数在 `CmdletBinding` 中称为 `SupportsShouldProcess`。</span><span class="sxs-lookup"><span data-stu-id="77e21-221">I tend to remember to use `ShouldProcess` because the parameter is called `SupportsShouldProcess` in the `CmdletBinding`.</span></span>
<span data-ttu-id="77e21-222">几乎应该在所有场景中都使用 `ShouldProcess`。</span><span class="sxs-lookup"><span data-stu-id="77e21-222">You should use `ShouldProcess` in almost every scenario.</span></span> <span data-ttu-id="77e21-223">这就是我首先介绍此方法的原因。</span><span class="sxs-lookup"><span data-stu-id="77e21-223">That is why I covered that method first.</span></span>

<span data-ttu-id="77e21-224">让我们来看看 `ShouldContinue` 的实际应用。</span><span class="sxs-lookup"><span data-stu-id="77e21-224">Let's take a look at `ShouldContinue` in action.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="77e21-225">它提供的提示更简单，选项更少。</span><span class="sxs-lookup"><span data-stu-id="77e21-225">This provides us a simpler prompt with fewer options.</span></span>

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="77e21-226">`ShouldContinue` 的最大问题是，它要求用户以交互方式运行它，因为它总是提示用户。</span><span class="sxs-lookup"><span data-stu-id="77e21-226">The biggest issue with `ShouldContinue` is that it requires the user to run it interactively because it always prompts the user.</span></span> <span data-ttu-id="77e21-227">应始终构建可由其他脚本使用的工具。</span><span class="sxs-lookup"><span data-stu-id="77e21-227">You should always be building tools that can be used by other scripts.</span></span> <span data-ttu-id="77e21-228">执行此操作的方法是实现 `-Force`。</span><span class="sxs-lookup"><span data-stu-id="77e21-228">The way you do this is by implementing `-Force`.</span></span> <span data-ttu-id="77e21-229">我稍后将再次讨论此内容。</span><span class="sxs-lookup"><span data-stu-id="77e21-229">I'll revisit this idea later.</span></span>

### <a name="yes-to-all"></a><span data-ttu-id="77e21-230">Yes to all</span><span class="sxs-lookup"><span data-stu-id="77e21-230">Yes to all</span></span>

<span data-ttu-id="77e21-231">这是用 `ShouldProcess` 自动处理的，但是我们必须为 `ShouldContinue` 再多执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="77e21-231">This is automatically handled with `ShouldProcess` but we have to do a little more work for `ShouldContinue`.</span></span> <span data-ttu-id="77e21-232">还有第二个方法重载，我们必须通过引用传入一些值来控制逻辑。</span><span class="sxs-lookup"><span data-stu-id="77e21-232">There's a second method overload where we have to pass in a few values by reference to control the logic.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    $collection = 1..5
    $yesToAll = $false
    $noToAll = $false

    foreach($target in $collection) {

        $continue = $PSCmdlet.ShouldContinue(
                "TARGET_$target",
                'OPERATION',
                [ref]$yesToAll,
                [ref]$noToAll
            )

        if ($continue){
            Write-Output "Some Action [$target]"
        }
    }
}
```

<span data-ttu-id="77e21-233">我添加了一个 `foreach` 循环和一个集合，以在实际操作中进行演示。</span><span class="sxs-lookup"><span data-stu-id="77e21-233">I added a `foreach` loop and a collection to show it in action.</span></span> <span data-ttu-id="77e21-234">我从 `if` 语句中提取了`ShouldContinue` 调用，使其更便于阅读。</span><span class="sxs-lookup"><span data-stu-id="77e21-234">I pulled the `ShouldContinue` call out of the `if` statement to make it easier to read.</span></span> <span data-ttu-id="77e21-235">调用具有四个参数的方法会比较复杂，我尽量让它简单易懂。</span><span class="sxs-lookup"><span data-stu-id="77e21-235">Calling a method with four parameters starts to get a little ugly, but I tried to make it look as clean as I could.</span></span>

## <a name="implementing--force"></a><span data-ttu-id="77e21-236">实现 -Force</span><span class="sxs-lookup"><span data-stu-id="77e21-236">Implementing -Force</span></span>

<span data-ttu-id="77e21-237">`ShouldProcess` 和 `ShouldContinue` 需要用不同的方式实现 `-Force`。</span><span class="sxs-lookup"><span data-stu-id="77e21-237">`ShouldProcess` and `ShouldContinue` need to implement `-Force` in different ways.</span></span> <span data-ttu-id="77e21-238">实现的诀窍是，应始终执行 `ShouldProcess`，但如果指定了 `-Force`，则不应执行 `ShouldContinue`。</span><span class="sxs-lookup"><span data-stu-id="77e21-238">The trick to these implementations is that `ShouldProcess` should always get executed, but `ShouldContinue` should not get executed if `-Force` is specified.</span></span>

### <a name="shouldprocess--force"></a><span data-ttu-id="77e21-239">ShouldProcess -Force</span><span class="sxs-lookup"><span data-stu-id="77e21-239">ShouldProcess -Force</span></span>

<span data-ttu-id="77e21-240">如果将 `ConfirmImpact` 设置为 `high`，用户首先要尝试的操作是用 `-Force` 取消它。</span><span class="sxs-lookup"><span data-stu-id="77e21-240">If you set your `ConfirmImpact` to `high`, the first thing your users are going to try is to suppress it with `-Force`.</span></span> <span data-ttu-id="77e21-241">无论如何，这是我会执行的第一步操作。</span><span class="sxs-lookup"><span data-stu-id="77e21-241">That's the first thing I do anyway.</span></span>

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

<span data-ttu-id="77e21-242">如果从 `ConfirmImpact` 部分撤回，它们实际上需要按以下方式调用它：</span><span class="sxs-lookup"><span data-stu-id="77e21-242">If you recall from the `ConfirmImpact` section, they actually need to call it like this:</span></span>

```powershell
Test-ShouldProcess -Confirm:$false
```

<span data-ttu-id="77e21-243">并非每个人都能意识到他们需要这么做，`-Confirm:$false` 不会取消 `ShouldContinue`。</span><span class="sxs-lookup"><span data-stu-id="77e21-243">Not everyone realizes they need to do that and `-Confirm:$false` doesn't suppress `ShouldContinue`.</span></span>
<span data-ttu-id="77e21-244">所以，我们应实现 `-Force` 以使用户易于理解。</span><span class="sxs-lookup"><span data-stu-id="77e21-244">So we should implement `-Force` for the sanity of our users.</span></span> <span data-ttu-id="77e21-245">请看下面的完整示例：</span><span class="sxs-lookup"><span data-stu-id="77e21-245">Take a look at this full example here:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force -and -not $Confirm){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="77e21-246">我们添加自己的 `-Force` 开关作为参数，并使用在 `CmdletBinding` 中添加 `SupportsShouldProcess` 时可用的 `$Confirm` 自动参数。</span><span class="sxs-lookup"><span data-stu-id="77e21-246">We add our own `-Force` switch as a parameter and use the `$Confirm` automatic parameter that is available when adding `SupportsShouldProcess` in the `CmdletBinding`.</span></span>

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

<span data-ttu-id="77e21-247">请注意这里的 `-Force` 逻辑：</span><span class="sxs-lookup"><span data-stu-id="77e21-247">Focusing in on the `-Force` logic here:</span></span>

```powershell
if ($Force -and -not $Confirm){
    $ConfirmPreference = 'None'
}
```

<span data-ttu-id="77e21-248">如果用户指定了 `-Force`，则需要取消确认提示，除非他们还指定了 `-Confirm`。</span><span class="sxs-lookup"><span data-stu-id="77e21-248">If the user specifies `-Force`, we want to suppress the confirm prompt unless they also specify `-Confirm`.</span></span> <span data-ttu-id="77e21-249">这允许用户强制进行更改，但仍会确认更改。</span><span class="sxs-lookup"><span data-stu-id="77e21-249">This allows a user to force a change but still confirm the change.</span></span> <span data-ttu-id="77e21-250">然后我们在本地作用域中设置 `$ConfirmPreference`，在这里我们调用 `ShouldProcess` 来发现它。</span><span class="sxs-lookup"><span data-stu-id="77e21-250">Then we set `$ConfirmPreference` in the local scope where our call to `ShouldProcess` discoverers it.</span></span>

```powershell
if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

<span data-ttu-id="77e21-251">如果有人同时指定了 `-Force` 和 `-WhatIf`，则需优先考虑 `-WhatIf`。</span><span class="sxs-lookup"><span data-stu-id="77e21-251">If someone specifies both `-Force` and `-WhatIf`, then `-WhatIf` needs to take priority.</span></span> <span data-ttu-id="77e21-252">此方法保留 `-WhatIf` 处理，因为会始终执行 `ShouldProcess`。</span><span class="sxs-lookup"><span data-stu-id="77e21-252">This approach preserves `-WhatIf` processing because `ShouldProcess` always gets executed.</span></span>

<span data-ttu-id="77e21-253">不要使用 `ShouldProcess` 在 if 语句中添加对 `$Force` 值的检查。</span><span class="sxs-lookup"><span data-stu-id="77e21-253">Do not add a check for the `$Force` value inside the if statement with the `ShouldProcess`.</span></span> <span data-ttu-id="77e21-254">这是此特定场景的反模式，尽管这是我在 `ShouldContinue` 的下一部分要讨论的内容。</span><span class="sxs-lookup"><span data-stu-id="77e21-254">That is an anti-pattern for this specific scenario even though that's what I show you in the next section for `ShouldContinue`.</span></span>

### <a name="shouldcontinue--force"></a><span data-ttu-id="77e21-255">ShouldContinue -Force</span><span class="sxs-lookup"><span data-stu-id="77e21-255">ShouldContinue -Force</span></span>

<span data-ttu-id="77e21-256">这是使用 `ShouldContinue` 实现 `-Force` 的正确方法。</span><span class="sxs-lookup"><span data-stu-id="77e21-256">This is the correct way to implement `-Force` with `ShouldContinue`.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param(
        [Switch]$Force
    )

    if($Force -or $PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="77e21-257">通过将 `$Force` 放置在 `-or` 运算符的左侧，可首先对其求值。</span><span class="sxs-lookup"><span data-stu-id="77e21-257">By placing the `$Force` to the left of the `-or` operator, it gets evaluated first.</span></span> <span data-ttu-id="77e21-258">这样编写可缩短 `if` 语句的执行时间。</span><span class="sxs-lookup"><span data-stu-id="77e21-258">Writing it this way short circuits the execution of the `if` statement.</span></span> <span data-ttu-id="77e21-259">如果 `$true` 为 `$force`，则不会执行 `ShouldContinue`。</span><span class="sxs-lookup"><span data-stu-id="77e21-259">If `$force` is `$true`, then the `ShouldContinue` is not executed.</span></span>

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

<span data-ttu-id="77e21-260">在这种情况下，我们不必担心 `-Confirm` 或 `-WhatIf`，因为 `ShouldContinue` 不支持它们。</span><span class="sxs-lookup"><span data-stu-id="77e21-260">We don't have to worry about `-Confirm` or `-WhatIf` in this scenario because they're not supported by `ShouldContinue`.</span></span> <span data-ttu-id="77e21-261">这就是需要以不同于 `ShouldProcess` 的方式处理它的原因。</span><span class="sxs-lookup"><span data-stu-id="77e21-261">This is why it needs to be handled differently than `ShouldProcess`.</span></span>

## <a name="scope-issues"></a><span data-ttu-id="77e21-262">作用域问题</span><span class="sxs-lookup"><span data-stu-id="77e21-262">Scope issues</span></span>

<span data-ttu-id="77e21-263">使用 `-WhatIf` 和 `-Confirm` 应该适用于函数内的所有内容及其调用的所有内容。</span><span class="sxs-lookup"><span data-stu-id="77e21-263">Using `-WhatIf` and `-Confirm` are supposed to apply to everything inside your functions and everything they call.</span></span> <span data-ttu-id="77e21-264">它们通过在函数的本地作用域中将 `$WhatIfPreference` 设置为 `$true` 或将 `$ConfirmPreference` 设置为`Low` 来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="77e21-264">They do this by setting `$WhatIfPreference` to `$true` or setting `$ConfirmPreference` to `Low` in the local scope of the function.</span></span> <span data-ttu-id="77e21-265">调用另一个函数时，调用 `ShouldProcess` 将使用这些值。</span><span class="sxs-lookup"><span data-stu-id="77e21-265">When you call another function, calls to `ShouldProcess` use those values.</span></span>

<span data-ttu-id="77e21-266">这在大多数情况下都可以正常运行。</span><span class="sxs-lookup"><span data-stu-id="77e21-266">This actually works correctly most of the time.</span></span> <span data-ttu-id="77e21-267">无论何时在同一作用域内调用内置 cmdlet 或函数，都可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="77e21-267">Anytime you call built-in cmdlet or a function in your same scope, it works.</span></span> <span data-ttu-id="77e21-268">它也适用于从控制台调用脚本模块中的脚本或函数的情况。</span><span class="sxs-lookup"><span data-stu-id="77e21-268">It also works when you call a script or a function in a script module from the console.</span></span>

<span data-ttu-id="77e21-269">唯一不能正常运行的情况是，当脚本或脚本模块调用另一脚本模块中的函数时。</span><span class="sxs-lookup"><span data-stu-id="77e21-269">The one specific place where it doesn't work is when a script or a script module calls a function in another script module.</span></span> <span data-ttu-id="77e21-270">这听起来可能不是什么大问题，但从 PSGallery 创建或提取的大多数模块都是脚本模块。</span><span class="sxs-lookup"><span data-stu-id="77e21-270">This may not sound like a big problem, but most of the modules you create or pull from the PSGallery are script modules.</span></span>

<span data-ttu-id="77e21-271">核心问题在于，当从其他脚本模块中的函数中调用时，脚本模板不会继承 `$WhatIfPreference` 或 `$ConfirmPreference`（以及许多其他参数）的值。</span><span class="sxs-lookup"><span data-stu-id="77e21-271">The core issue is that script modules do not inherit the values for `$WhatIfPreference` or `$ConfirmPreference` (and several others) when called from functions in other script modules.</span></span>

<span data-ttu-id="77e21-272">将其概括为一般规则的最佳方法是，对于二进制模块，可以使用此方法，但对于脚本模块，则不要依赖于此方法。</span><span class="sxs-lookup"><span data-stu-id="77e21-272">The best way to summarize this as a general rule is that this works correctly for binary modules and never trust it to work for script modules.</span></span> <span data-ttu-id="77e21-273">如果对此不确定，可对其进行测试或直接假定它不能正常使用。</span><span class="sxs-lookup"><span data-stu-id="77e21-273">If you aren't sure, either test it or just assume it doesn't work correctly.</span></span>

<span data-ttu-id="77e21-274">我个人认为这是非常危险的，因为可能会遇到以下情况：将 `-WhatIf` 支持添加到多个模块中时，这些模块在隔离状态下可正常工作，但在它们相互调用时无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="77e21-274">I personally feel this is very dangerous because it creates scenarios where you add `-WhatIf` support to multiple modules that work correctly in isolation, but fail to work correctly when they call each other.</span></span>

<span data-ttu-id="77e21-275">可以使用 GitHub RFC 来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="77e21-275">We do have a GitHub RFC working to get this issue fixed.</span></span> <span data-ttu-id="77e21-276">有关更多详细信息，请参阅[将执行首选项扩展到脚本模块范围之外][RFC]。</span><span class="sxs-lookup"><span data-stu-id="77e21-276">See [Propagate execution preferences beyond script module scope][RFC] for more details.</span></span>

## <a name="in-closing"></a><span data-ttu-id="77e21-277">结束语</span><span class="sxs-lookup"><span data-stu-id="77e21-277">In closing</span></span>

<span data-ttu-id="77e21-278">在每次需要使用 `ShouldProcess` 时，我都会去查阅它的用法。</span><span class="sxs-lookup"><span data-stu-id="77e21-278">I have to look up how to use `ShouldProcess` every time I need to use it.</span></span> <span data-ttu-id="77e21-279">我花了很长时间才把 `ShouldProcess` 和 `ShouldContinue` 区分开来。</span><span class="sxs-lookup"><span data-stu-id="77e21-279">It took me a long time to distinguish `ShouldProcess` from `ShouldContinue`.</span></span> <span data-ttu-id="77e21-280">我几乎总是需要查找要使用的参数。</span><span class="sxs-lookup"><span data-stu-id="77e21-280">I almost always need to look up what parameters to use.</span></span> <span data-ttu-id="77e21-281">所以，如果你仍不时感到困惑，无需担心。</span><span class="sxs-lookup"><span data-stu-id="77e21-281">So don't worry if you still get confused from time to time.</span></span> <span data-ttu-id="77e21-282">可以在需要时阅读本文。</span><span class="sxs-lookup"><span data-stu-id="77e21-282">This article will be here when you need it.</span></span> <span data-ttu-id="77e21-283">我自己肯定会经常参考。</span><span class="sxs-lookup"><span data-stu-id="77e21-283">I'm sure I will reference it often myself.</span></span>

<span data-ttu-id="77e21-284">如果你喜欢这篇文章，请使用下面的链接在 Twitter 上分享你的想法。</span><span class="sxs-lookup"><span data-stu-id="77e21-284">If you liked this post, please share your thoughts with me on Twitter using the link below.</span></span> <span data-ttu-id="77e21-285">我非常期待听到你们从我的文章获益的消息。</span><span class="sxs-lookup"><span data-stu-id="77e21-285">I always like hearing from people that get value from my content.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[original version]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[通用参数]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[common parameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[关于哈希表的各项须知内容]: everything-about-hashtable.md
[everything you wanted to know about hashtables]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839
