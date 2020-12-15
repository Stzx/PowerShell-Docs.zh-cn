---
ms.date: 11/11/2020
title: 使用 PowerShell 中的实验性功能
description: 列出了目前可用的实验性功能及其用法。
ms.openlocfilehash: 4df3601cd38120fedecbbad8a3c63a95240c5f15
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625697"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="d9ee8-103">使用 PowerShell 中的实验性功能</span><span class="sxs-lookup"><span data-stu-id="d9ee8-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="d9ee8-104">PowerShell 中的实验性功能支持提供了一种机制，可便于实验性功能与 PowerShell 或 PowerShell 模块中的现有稳定功能共存。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="d9ee8-105">实验性功能是指设计尚未最终确定的功能。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="d9ee8-106">此类功能可供用户进行测试和提供反馈。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="d9ee8-107">一旦实验性功能最终确定下来，设计变更就变成了中断性变更。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="d9ee8-108">实验性功能不适合在生产环境中使用，因为允许变更成为中断性变更。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="d9ee8-109">实验性功能不受官方支持。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="d9ee8-110">不过，我们非常期望收到你的反馈和 Bug 报告。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="d9ee8-111">你可以在 [GitHub 源存储库](https://github.com/PowerShell/PowerShell/issues/new/choose)中提出问题。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="d9ee8-112">若要详细了解如何启用或禁用这些功能，请参阅 [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features)。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="d9ee8-113">可用功能</span><span class="sxs-lookup"><span data-stu-id="d9ee8-113">Available features</span></span>

<span data-ttu-id="d9ee8-114">本文介绍了可用的实验性功能及其用法。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="d9ee8-115">名称</span><span class="sxs-lookup"><span data-stu-id="d9ee8-115">Name</span></span>                            |   <span data-ttu-id="d9ee8-116">6.2</span><span class="sxs-lookup"><span data-stu-id="d9ee8-116">6.2</span></span>   |   <span data-ttu-id="d9ee8-117">7.0</span><span class="sxs-lookup"><span data-stu-id="d9ee8-117">7.0</span></span>   |   <span data-ttu-id="d9ee8-118">7.1</span><span class="sxs-lookup"><span data-stu-id="d9ee8-118">7.1</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: |
| <span data-ttu-id="d9ee8-119">PSTempDrive（PS 7.0 及更高版本中的主要支持）</span><span class="sxs-lookup"><span data-stu-id="d9ee8-119">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |
| <span data-ttu-id="d9ee8-120">PSUseAbbreviationExpansion（PS 7.0 及更高版本中的主要支持）</span><span class="sxs-lookup"><span data-stu-id="d9ee8-120">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |
| <span data-ttu-id="d9ee8-121">PSNullConditionalOperators（PS 7.1 及更高版本中的主要支持）</span><span class="sxs-lookup"><span data-stu-id="d9ee8-121">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |
| <span data-ttu-id="d9ee8-122">PSUnixFileStat（仅限非 Windows - PS 7.1 及更高版本中的主要支持）</span><span class="sxs-lookup"><span data-stu-id="d9ee8-122">PSUnixFileStat (non-Windows only - mainstream in PS 7.1+)</span></span>  |         | &check; |         |
| <span data-ttu-id="d9ee8-123">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="d9ee8-123">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; |
| <span data-ttu-id="d9ee8-124">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="d9ee8-124">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; |
| <span data-ttu-id="d9ee8-125">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="d9ee8-125">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; |
| <span data-ttu-id="d9ee8-126">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="d9ee8-126">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; |
| <span data-ttu-id="d9ee8-127">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="d9ee8-127">PSNativePSPathResolution</span></span>                                   |         |         | &check; |
| <span data-ttu-id="d9ee8-128">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="d9ee8-128">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; |
| <span data-ttu-id="d9ee8-129">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="d9ee8-129">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; |
| <span data-ttu-id="d9ee8-130">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="d9ee8-130">PSSubsystemPluginModel</span></span>                                     |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="d9ee8-131">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="d9ee8-131">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="d9ee8-132">在 PowerShell 7.0 中，此实验性功能可在 `Debug-Runspace` 和 `Debug-Job` cmdlet 上启用 BreakAll 参数，以允许用户在附加调试器时决定是否要让 PowerShell 在当前位置立即中断。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-132">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="d9ee8-133">在 PowerShell 7.1 中，此实验性功能还可将“运行空间”参数添加到 `*-PSBreakpoint` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-133">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="d9ee8-134">“运行空间”参数会指定一个“运行空间”对象，以便可在指定的运行空间中与断点进行交互。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-134">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="d9ee8-135">在此示例中，将启动一个作业，并将一个断点设置为当运行 `Set-PSBreakPoint` 时中断。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-135">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="d9ee8-136">运行空间存储在变量中，并通过“运行空间”参数传递到 `Get-PSBreakPoint` 命令。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-136">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="d9ee8-137">然后，则可以在 `$breakpoint` 变量中查看断点。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-137">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="d9ee8-138">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="d9ee8-138">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="d9ee8-139">在 CommandNotFoundException  后根据模糊匹配搜索来建议可能命令。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-139">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="d9ee8-140">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="d9ee8-140">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="d9ee8-141">如果 `-replace` 运算符语句中的左操作数不是字符串，则此操作数会转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-141">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="d9ee8-142">如果此功能是禁用的，`-replace` 运算符会执行区分区域性的字符串转换。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-142">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="d9ee8-143">例如，如果区域性设置为“法语(fr)”，则值 `1.2` 会转换为字符串 `1,2`。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-143">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="d9ee8-144">如果此功能是启用的：</span><span class="sxs-lookup"><span data-stu-id="d9ee8-144">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="d9ee8-145">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="d9ee8-145">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="d9ee8-146">支持在非 Windows 系统上编译为 MOF，并支持在没有 LCM 的情况下使用 `Invoke-DSCResource`。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-146">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="d9ee8-147">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="d9ee8-147">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="d9ee8-148">此功能用于检查在 shell 中键入的命令，如果所有命令都是隐式远程处理代理命令，且组成了简单管道，那么这些命令会一起进行批处理，并作为一个远程管道进行调用。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-148">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="d9ee8-149">示例：</span><span class="sxs-lookup"><span data-stu-id="d9ee8-149">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="d9ee8-150">如上所示，如果批处理功能是启用的，所有三个隐式远程处理代理命令（`Get-AllProcesses`、`Select-Custom`、`Group-Stuff`）都在远程会话中运行，并且管道中的结果是返回给客户端的唯一数据。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-150">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="d9ee8-151">这不仅减少了在客户端与远程会话之间来回发送的数据量，还减少了对象序列化和反序列化的量。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-151">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="d9ee8-152">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="d9ee8-152">PSNativePSPathResolution</span></span>

<span data-ttu-id="d9ee8-153">如果使用 FileSystem 提供程序的 PSDrive 路径传递给本机命令，那么解析的文件路径就会传递给本机命令。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-153">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="d9ee8-154">也就是说，像 `code temp:/test.txt` 这样的命令现在可以正常运行了。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-154">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="d9ee8-155">另外，在 Windows 上，如果路径以 `~` 开头，那么路径会解析为完整路径，并传递给本机命令。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-155">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="d9ee8-156">在这两种情况下，路径都会规范化为相关操作系统的目录分隔符。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-156">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="d9ee8-157">如果路径不是 PSDrive 或 `~`（在 Windows 上），则不会进行路径规范化</span><span class="sxs-lookup"><span data-stu-id="d9ee8-157">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="d9ee8-158">如果路径是用单引号引住，则不会进行解析，而是被视为文本</span><span class="sxs-lookup"><span data-stu-id="d9ee8-158">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="d9ee8-159">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="d9ee8-159">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="d9ee8-160">启用此实验性功能后，从本机命令重定向的错误记录（例如，使用重定向运算符 (`2>&1`) 时）不会写入到 `$Error` 变量，并且首选项变量 `$ErrorActionPreference` 不会影响重定向的输出。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-160">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="d9ee8-161">许多本机命令都会写入到 `stderr`，来将其作为获取额外信息的备用流。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-161">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="d9ee8-162">查找错误时，此行为可能会导致混淆，如果将 `$ErrorActionPreference` 设置为静音输出的状态，则用户可能会丢失额外的输出信息。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-162">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="d9ee8-163">当本机命令包含非零的退出代码时，`$?` 会设置为 `$false`。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-163">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="d9ee8-164">如果退出代码为零，`$?` 会设置为 `$true`。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-164">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="d9ee8-165">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="d9ee8-165">PSNullConditionalOperators</span></span>

<span data-ttu-id="d9ee8-166">为 Null 条件成员访问运算符引入新的运算符，即 `?.` 和 `?[]`。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-166">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="d9ee8-167">Null 成员访问运算符可用于标量类型和数组类型。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-167">Null member access operators can used on scalar types and array types.</span></span> <span data-ttu-id="d9ee8-168">如果变量不为 null，则返回被访问成员的值。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-168">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="d9ee8-169">如果变量的值为 null，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-169">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="d9ee8-170">只有在 `$x` 不为 null 的情况下，才访问 `propname` 属性并返回它的值。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-170">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="d9ee8-171">同样，只有在 `$x` 不为 null 的情况下，才使用索引器。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-171">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="d9ee8-172">如果 `$x` 为 null，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-172">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="d9ee8-173">`?.` 和 `?[]` 运算符是成员访问运算符，不允许在变量名称和运算符之间有空格。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-173">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="d9ee8-174">由于 PowerShell 允许 `?` 作为变量名称的一部分，因此如果在使用运算符时变量名称和运算符之间没有空格，必须消除歧义。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-174">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="d9ee8-175">为了消除歧义，变量必须在变量名称两边使用 `{}`（如 `${x?}?.propertyName` 或 `${y}?[0]`）。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-175">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="d9ee8-176">此功能已退出实验性阶段，并已成为 PowerShell 7.1 及更高版本中的主要支持功能。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-176">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="d9ee8-177">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="d9ee8-177">PSTempDrive</span></span>

<span data-ttu-id="d9ee8-178">创建映射到用户的临时目录路径的 `TEMP:` PSDrive。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-178">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="d9ee8-179">此功能已退出实验性阶段，并已成为 PowerShell 7 及更高版本中的主要支持功能。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-179">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="d9ee8-180">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="d9ee8-180">PSUnixFileStat</span></span>

<span data-ttu-id="d9ee8-181">此功能提供了新行为，可以在文件系统提供程序的输出中添加来自 Unix stat  API 的数据，以促进生成更类似于 Unix 的文件列表。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-181">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="d9ee8-182">它在名为 UnixStat  的文件系统提供程序中添加新的注释属性，其中包含来自基础 Unix 类型系统的 `stat(2)` API 的通用表达式。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-182">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="d9ee8-183">`Get-ChildItem` 的输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9ee8-183">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> <span data-ttu-id="d9ee8-184">此功能已退出实验性阶段，并已成为 PowerShell 7.1 及更高版本中的主要支持功能。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-184">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="d9ee8-185">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="d9ee8-185">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="d9ee8-186">此功能支持对缩写的 cmdlet 和函数进行 Tab 自动补全：</span><span class="sxs-lookup"><span data-stu-id="d9ee8-186">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="d9ee8-187">例如：</span><span class="sxs-lookup"><span data-stu-id="d9ee8-187">For example:</span></span>

- <span data-ttu-id="d9ee8-188">`i-psdf<tab>` 返回 `Import-PowerShellDataFile`。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-188">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="d9ee8-189">`u-akvmssdr<tab>` 返回 `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span><span class="sxs-lookup"><span data-stu-id="d9ee8-189">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="d9ee8-190">这只适用于 Tab 自动补全（交互式使用），因此 `i-psdf` 在脚本中不是有效的 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-190">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="d9ee8-191">此功能已退出实验性阶段，并已成为 PowerShell 7 及更高版本中的主要支持功能。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-191">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="d9ee8-192">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="d9ee8-192">PSSubsystemPluginModel</span></span>

<span data-ttu-id="d9ee8-193">此功能在 PowerShell 中启用子系统插件模型。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-193">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="d9ee8-194">利用此功能，可以将 `System.Management.Automation.dll` 的组件分隔到驻留在自己的程序集中的各个子系统。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-194">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="d9ee8-195">这种隔离可减少核心 PowerShell 引擎的磁盘占用，并支持这些组件成为最小 PowerShell 安装的可选功能。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-195">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="d9ee8-196">目前仅支持 CommandPredictor 子系统。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-196">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="d9ee8-197">该子系统与 PSReadLine 模块一起使用，以提供自定义预测插件。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-197">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="d9ee8-198">将来  ，Job、CommandCompleter、Remoting 和其他组件可以分隔到 `System.Management.Automation.dll` 外的子系统程序集。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-198">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="d9ee8-199">试验性功能包括新的 cmdlet [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem)。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-199">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="d9ee8-200">只有启用此功能时，此 cmdlet 才可用。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-200">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="d9ee8-201">此 cmdlet 将返回有关系统上可用子系统的信息。</span><span class="sxs-lookup"><span data-stu-id="d9ee8-201">This cmdlet returns information about the subsystems that are available on the system.</span></span>
