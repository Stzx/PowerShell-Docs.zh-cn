---
title: 关于 ShouldProcess 的各项须知内容
description: ShouldProcess 是一项经常被忽略的重要功能。 借助 WhatIf 和 Confirm 参数，可以将其轻松添加到函数中。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 4f11ad84f5c89423fe56cfe438ed3cb1587ce59e
ms.sourcegitcommit: be1df0bf757d734975a9aa021727608a396059ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "96616040"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a>关于 ShouldProcess 的各项须知内容

PowerShell 函数有几项功能可以显著改善用户与之交互的方式。
经常被忽略的一项重要功能是 `-WhatIf` 和 `-Confirm` 支持，可以轻松地将它添加到函数中。 本文将深入介绍如何实现此功能。

> [!NOTE]
> 本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。 PowerShell 团队感谢 Kevin 与我们分享这篇文章。 请前往 [PowerShellExplained.com][] 访问他的博客。

这是一个可以在函数中启用的简单功能，可为需要的用户提供一个安全网络。 没有什么比第一次执行一个明知会有危险的命令更让人胆战心惊的了。 而选择使用 `-WhatIf` 运行命令将会大有不同。

## <a name="commonparameters"></a>CommonParameters

在探究如何实现这些[通用参数][]之前，我想快速介绍一下它们的用法。

## <a name="using--whatif"></a>使用 -WhatIf

当命令支持 `-WhatIf` 参数时，它允许你查看命令将执行什么操作，而不是进行更改。 这是测试命令影响的好方法，特别是在执行某些破坏性操作前。

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

如果命令可正确实现 `ShouldProcess`，它应显示它所做的所有更改。 下面是使用通配符删除多个文件的示例。

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a>使用 -Confirm

支持 `-WhatIf` 的命令也支持 `-Confirm`。 这提供了在执行操作前进行确认的机会。

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

在本例中，可以使用多个选项来继续、跳过更改或停止脚本。 “帮助”提示会按如下所述对这些选项进行说明。

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a>本地化

此提示已在 PowerShell 中本地化，因此其语言因操作系统的语言而异。 这是 PowerShell 为你管理的又一项内容。

### <a name="switch-parameters"></a>开关参数

让我们快速了解一下将值传递给开关参数的方式。 提到这一点的主要原因是，经常需要将参数值传递给调用的函数。

第一种方法是使用一种特定的参数语法，该语法可用于所有参数，但主要用于开关参数。 指定一个冒号以向参数附加值。

```powershell
Remove-Item -Path:* -WhatIf:$true
```

可以使用变量执行相同的操作。

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

第二种方法是使用哈希表来展开值。

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

如果你不熟悉哈希表或展开操作，请参阅我的另一篇文章[关于哈希表的各项须知内容][]。

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

启用 `-WhatIf` 和 `-Confirm` 支持的第一步是，在函数的 `CmdletBinding` 中指定 `SupportsShouldProcess`。

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

以这种方式指定 `SupportsShouldProcess` 后，就可以使用 `-WhatIf`（或 `-Confirm`）来调用函数了。

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

请注意，我没有创建名为 `-WhatIf` 的参数。 指定 `SupportsShouldProcess` 即会自动为我们创建该参数。 当我们在 `Test-ShouldProcess` 上指定 `-WhatIf` 参数时，我们调用的某些项也会执行 `-WhatIf` 处理。

### <a name="trust-but-verify"></a>信任但验证

在这里，相信调用的所有内容都可继承 `-WhatIf` 值是有些危险的。 对于其余的示例，我将假设它不起作用，并且在调用其他命令时非常明确。 我建议你也这样做。

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIfPreference
}
```

当你能够更好地了解所涉及的所有操作后，我会在后续部分再次讨论其中的细微差别。

## <a name="pscmdletshouldprocess"></a>$PSCmdlet.ShouldProcess

允许你实现 `SupportsShouldProcess` 的方法是 `$PSCmdlet.ShouldProcess`。 调用 `$PSCmdlet.ShouldProcess(...)` 来查看是否应该处理一些逻辑，剩下的由 PowerShell 处理。 我们从一个示例开始：

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

调用 `$PSCmdlet.ShouldProcess($file.name)` 检查 `-WhatIf`（和 `-Confirm` 参数），然后对其进行相应处理。 `-WhatIf` 会导致 `ShouldProcess` 输出更改说明并返回 `$false`：

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

使用 `-Confirm` 的调用会使脚本暂停，并提示用户选择是否要继续。 如果用户选择 `Y`，它将返回 `$true`。

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

`$PSCmdlet.ShouldProcess` 的一项出色功能是，它可加倍提供更为详细的输出结果。 在实现 `ShouldProcess` 时，我经常依赖这一功能。

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a>重载

`$PSCmdlet.ShouldProcess` 有几个不同的重载，可使用不同的参数来自定义消息传递。 在上面的示例中，我们已经看到了第一种重载。 下面对其进行详细介绍。

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

这会生成包含函数名称和目标（参数值）的输出。

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

将第二个参数指定为操作将使用操作值而不是消息中的函数名称。

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

下一选项是指定三个参数来完全自定义消息。 使用三个参数时，第一个参数是整个消息。 后两个参数仍在 `-Confirm` 消息输出中使用。

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a>快速参数参考

如果你阅读本文只是想知道应使用哪些参数，我在这里提供了一个快速参考，介绍了参数在不同的 `-WhatIf` 场景中更改消息的方式。

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

我倾向于使用有两个参数的选项。

### <a name="shouldprocessreason"></a>ShouldProcessReason

第四个重载比其他重载的功能更强大。 它可获取执行 `ShouldProcess` 的原因。 我在这里添加此内容只是为了内容完整，因为我们也可以直接查看 `$WhatIfPreference` 是否为 `$true`。

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

必须通过 `[ref]` 将 `$reason` 变量作为引用变量传入第四个参数。 `ShouldProcess` 用 `None` 或 `WhatIf` 值填充 `$reason`。 我没说这样做有用，也从来没有使用它的理由。

### <a name="where-to-place-it"></a>放置位置

可使用 `ShouldProcess` 让脚本更安全。 因此，可以在脚本进行更改时使用它。 我喜欢将 `$PSCmdlet.ShouldProcess` 调用放在尽可能接近更改的位置。

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

如果我正在处理一个项集合，我会为每一项调用它。 因此调用会置于 Foreach 循环中。

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

我将 `ShouldProcess` 紧密地放在更改周围的原因是，我希望在指定 `-WhatIf` 时尽可能多地执行代码。 如果可能，我希望运行设置和验证，以便用户可以看到这些错误。

我还喜欢在验证我的项目的 Pester 测试中使用它。 如果我在 Pester 中有一段难以模拟的逻辑，我通常会将其包装在 `ShouldProcess` 中，并在测试中使用 `-WhatIf` 来调用它。 测试部分代码总比一点都不测试要好。

### <a name="whatifpreference"></a>$WhatIfPreference

我们拥有的第一个首选项变量是 `$WhatIfPreference`。 默认为 `$false`。 如果将其设置为 `$true`，则函数的执行方式与指定 `-WhatIf` 时相同。 如果在会话中按此设置，所有命令都将执行 `-WhatIf` 执行的操作。

使用 `-WhatIf` 调用函数时，`$WhatIfPreference` 的值将在函数的作用域内设置为 `$true`。

## <a name="confirmimpact"></a>ConfirmImpact

虽然我的大多数示例都是针对 `-WhatIf` 的，但到目前为止，所有这些都可以与 `-Confirm` 一起工作来提示用户。 可以将函数的 `ConfirmImpact` 设置为“高”，它会对用户进行提示，就像用 `-Confirm` 调用它一样。

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

由于 `High` 的影响，此 `Test-ShouldProcess` 调用将执行 `-Confirm` 操作。

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

一个明显的问题是，如果不提示用户，它会更难以在其他脚本中使用。 在这种情况下，我们可以将 `$false` 传递给 `-Confirm` 以取消提示。

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

我将在后面的部分介绍如何添加 `-Force` 支持。

### <a name="confirmpreference"></a>$ConfirmPreference

`$ConfirmPreference` 是一个自动变量，可以控制 `ConfirmImpact` 要求你确认执行的时间。 下面是 `$ConfirmPreference` 和 `ConfirmImpact` 的可能值。

- `High`
- `Medium`
- `Low`
- `None`

利用这些值，可以为每个函数指定不同的影响级别。 如果将 `$ConfirmPreference` 设置为高于 `ConfirmImpact` 的值，则不会提示你确认执行。

默认情况下，`$ConfirmPreference` 设置为 `High`，`ConfirmImpact` 设置为 `Medium`。 如果希望函数自动提示用户，请将 `ConfirmImpact` 设置为 `High`。 否则，如果命令具有破坏性，则将其设置为`Medium`；如果命令在生产环境中始终安全运行，则设置为 `Low`。 如果将其设置为 `none`，即使指定了 `-Confirm`，也不会出现提示（但仍提供 `-WhatIf` 支持）。

使用 `-Confirm` 调用函数时，`$ConfirmPreference` 的值将在函数的作用域内设置为 `Low`。

### <a name="suppressing-nested-confirm-prompts"></a>取消嵌套确认提示

`$ConfirmPreference` 可以被你调用的函数拾取。 这可能会导致以下情况：你添加了确认提示，你调用的函数也会提示用户。

我想要做的是，在处理完提示后在调用的命令上指定 `-Confirm:$false`。

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

这就把我们带回到一个之前提到的警告：何时 `-WhatIf` 不传递给函数和何时 `-Confirm` 传递给函数，这两者之间存在一些细微差别。 我保证晚点会再来讲这一点。

## <a name="pscmdletshouldcontinue"></a>$PSCmdlet.ShouldContinue

如果需要获得更多的控制（与 `ShouldProcess` 提供的控制相比），可以直接用 `ShouldContinue` 来触发提示。 `ShouldContinue` 会忽略 `$ConfirmPreference`、`ConfirmImpact`、`-Confirm`、`$WhatIfPreference`和 `-WhatIf`，因为它会在每次执行时进行提示。

乍一看，很容易将 `ShouldProcess` 和 `ShouldContinue` 混淆。 我倾向于记住使用 `ShouldProcess`，因为该参数在 `CmdletBinding` 中称为 `SupportsShouldProcess`。
几乎应该在所有场景中都使用 `ShouldProcess`。 这就是我首先介绍此方法的原因。

让我们来看看 `ShouldContinue` 的实际应用。

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

它提供的提示更简单，选项更少。

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

`ShouldContinue` 的最大问题是，它要求用户以交互方式运行，因为它总是提示用户。 应始终构建其他脚本可以使用的工具。 做到这一点的方法是实现 `-Force`。 我稍后将再次讨论这个观点。

### <a name="yes-to-all"></a>Yes to all

这是用 `ShouldProcess` 自动处理的，但是我们必须为 `ShouldContinue` 再多做一点工作。 还有第二个重载方法，我们必须通过引用来传入一些值以控制逻辑。

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

我添加了一个 `foreach` 循环和一个集合来显示它的作用。 我从 `if` 语句中提取了`ShouldContinue` 调用，使其更便于阅读。 调用具有四个参数的方法会有些麻烦，我尽量让它简单易懂。

## <a name="implementing--force"></a>实现 -Force

`ShouldProcess` 和 `ShouldContinue` 需要用不同的方式实现 `-Force`。 实现的诀窍是，应始终执行 `ShouldProcess`，但如果指定了 `-Force`，则不应执行 `ShouldContinue`。

### <a name="shouldprocess--force"></a>ShouldProcess -Force

如果将 `ConfirmImpact` 设置为 `high`，用户首先要尝试的操作是用 `-Force` 取消它。 无论如何，这是我会执行的第一步操作。

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

如果你回忆一下 `ConfirmImpact` 部分，他们实际上需要按以下方式调用它：

```powershell
Test-ShouldProcess -Confirm:$false
```

并非每个人都能意识到他们需要这么做，`-Force` 并不会取消 `ShouldContinue`。
所以，我们应实现 `-Force` 以使用户易于理解。 请看下面的完整示例：

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

我们添加自己的 `-Force` 开关作为一个参数。 在 `CmdletBinding` 中使用 `SupportsShouldProcess` 时，会自动添加 `-Confirm` 参数。

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

请关注这里的 `-Force` 逻辑：

```powershell
if ($Force){
    $ConfirmPreference = 'None'
}
```

如果用户指定了 `-Force`，我们希望取消确认提示，除非他们还指定了 `-Confirm`。 这允许用户强制进行更改，但仍会确认更改。 然后，在本地作用域中设置 `$ConfirmPreference`。 现在，使用 `-Force` 参数暂时将 `$ConfirmPreference` 设置为“none”，以禁用确认提示。

```powershell
if ($Force -or $PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

如果有人同时指定了 `-Force` 和 `-WhatIf`，则需优先考虑 `-WhatIf`。 此方法保留了 `-WhatIf` 处理，因为会始终执行 `ShouldProcess`。

请勿在含 `ShouldProcess` 的 `if` 语句中添加 `$Force` 值检查。 这是此特定场景的反模式，尽管这是我在 `ShouldContinue` 的下一部分要讨论的内容。

### <a name="shouldcontinue--force"></a>ShouldContinue -Force

以下是使用 `ShouldContinue` 实现 `-Force` 的正确方法。

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

通过将 `$Force` 放置在 `-or` 运算符的左侧，可首先对其求值。 这样编写可缩短 `if` 语句的执行时间。 如果 `$force` 为 `$true`，则不会执行 `ShouldContinue`。

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

在这种情况下，我们不必担心 `-Confirm` 或 `-WhatIf`，因为 `ShouldContinue` 不支持它们。 这就是需要以不同于 `ShouldProcess` 的方式处理它的原因。

## <a name="scope-issues"></a>作用域问题

使用 `-WhatIf` 和 `-Confirm` 应该适用于函数内的所有内容及其调用的所有内容。 通过在函数的本地作用域中将 `$WhatIfPreference` 设置为 `$true` 或将 `$ConfirmPreference` 设置为`Low` 来实现此目的。 当调用另一个函数时，对 `ShouldProcess` 的调用将使用这些值。

这实际上在大多数情况下都有效。 无论何时调用内置 cmdlet 或同一作用域内的函数时，它都会起作用。 它也适用于从控制台调用脚本模块中的脚本或函数的情况。

它不能起作用的一个特定情况是，当脚本或脚本模块调用另一脚本模块中的函数时。 这听起来可能不是什么大问题，但从 PSGallery 创建或提取的大多数模块都是脚本模块。

核心问题在于，当从其他脚本模块中的函数中调用时，脚本模块不会继承 `$WhatIfPreference` 或 `$ConfirmPreference`（以及几个其他参数）的值。

将其概括为一般规则的最佳方法是，对于二进制模块，可以使用此方法，但对于脚本模块，则不要依赖此方法。 如果对此不确定，可对其进行测试或直接假定它不能正常使用。

我个人认为这是非常危险的，因为可能会遇到以下情况：将 `-WhatIf` 支持添加到多个模块中时，这些模块可以独立正常工作，但在相互调用时无法正常工作。

可以使用 GitHub RFC 来解决此问题。 有关更多详细信息，请参阅[将执行首选项扩展到脚本模块范围之外][RFC]。

## <a name="in-closing"></a>结束语

在每次需要使用 `ShouldProcess` 时，我都会去查阅它的用法。 我花了很长时间才把 `ShouldProcess` 和 `ShouldContinue` 区分开来。 而且我几乎总是需要查找要使用的参数。 所以，如果你仍不时感到困惑，无需担心。 你可以在需要时阅读本文。 我自己肯定会经常参考。

如果你喜欢这篇文章，请使用下面的链接在 Twitter 上分享你的想法。 希望这篇文章对你有所帮助，期待听到你的声音。

<!-- link references -->
[原始版本]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[通用参数]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[关于哈希表的各项须知内容]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839
