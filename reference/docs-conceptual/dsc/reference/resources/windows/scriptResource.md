---
ms.date: 07/16/2020
keywords: dsc,powershell,配置,安装程序
title: DSC Script 资源
ms.openlocfilehash: 9b89981c17e87b3681c6416c7dee44a75c432ea1
ms.sourcegitcommit: eb6a7c01e6385809656ac828b9211683e0b1a6fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "89041123"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="6b862-103">DSC Script 资源</span><span class="sxs-lookup"><span data-stu-id="6b862-103">DSC Script Resource</span></span>

> <span data-ttu-id="6b862-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="6b862-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="6b862-105">Windows PowerShell Desired State Configuration (DSC) 中的 `Script` 资源提供了在目标节点上运行 Windows PowerShell 脚本的机制。</span><span class="sxs-lookup"><span data-stu-id="6b862-105">The `Script` resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="6b862-106">`Script` 资源使用 `GetScript`
`SetScript` 和 `TestScript` 属性，这些属性包含定义以执行相应的 DSC 状态操作的脚本块。</span><span class="sxs-lookup"><span data-stu-id="6b862-106">The `Script` resource uses `GetScript`
`SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b862-107">语法</span><span class="sxs-lookup"><span data-stu-id="6b862-107">Syntax</span></span>

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="6b862-108">将 `GetScript`、`TestScript` 和 `SetScript` 块存储为字符串。</span><span class="sxs-lookup"><span data-stu-id="6b862-108">`GetScript` `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="6b862-109">属性</span><span class="sxs-lookup"><span data-stu-id="6b862-109">Properties</span></span>

|  <span data-ttu-id="6b862-110">properties</span><span class="sxs-lookup"><span data-stu-id="6b862-110">Property</span></span>  |                                          <span data-ttu-id="6b862-111">说明</span><span class="sxs-lookup"><span data-stu-id="6b862-111">Description</span></span>                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="6b862-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="6b862-112">GetScript</span></span>  | <span data-ttu-id="6b862-113">一个返回节点当前状态的脚本块。</span><span class="sxs-lookup"><span data-stu-id="6b862-113">A script block that returns the current state of the Node.</span></span>                                    |
| <span data-ttu-id="6b862-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="6b862-114">SetScript</span></span>  | <span data-ttu-id="6b862-115">DSC 在节点未处于所需状态时用于强制执行符合性的脚本块。</span><span class="sxs-lookup"><span data-stu-id="6b862-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
| <span data-ttu-id="6b862-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="6b862-116">TestScript</span></span> | <span data-ttu-id="6b862-117">一个用于确定节点是否处于所需状态的脚本块。</span><span class="sxs-lookup"><span data-stu-id="6b862-117">A script block that determines if the Node is in the desired state.</span></span>                           |
| <span data-ttu-id="6b862-118">凭据</span><span class="sxs-lookup"><span data-stu-id="6b862-118">Credential</span></span> | <span data-ttu-id="6b862-119">指示要用于运行此脚本的凭据（如果需要凭据）。</span><span class="sxs-lookup"><span data-stu-id="6b862-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>        |

## <a name="common-properties"></a><span data-ttu-id="6b862-120">公共属性</span><span class="sxs-lookup"><span data-stu-id="6b862-120">Common properties</span></span>

|       <span data-ttu-id="6b862-121">properties</span><span class="sxs-lookup"><span data-stu-id="6b862-121">Property</span></span>       |                                            <span data-ttu-id="6b862-122">说明</span><span class="sxs-lookup"><span data-stu-id="6b862-122">Description</span></span>                                            |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="6b862-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="6b862-123">DependsOn</span></span>            | <span data-ttu-id="6b862-124">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="6b862-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> |
| <span data-ttu-id="6b862-125">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="6b862-125">PsDscRunAsCredential</span></span> | <span data-ttu-id="6b862-126">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="6b862-126">Sets the credential for running the entire resource as.</span></span>                                           |

> [!NOTE]
> <span data-ttu-id="6b862-127">在 WMF 5.0 中添加了 **PsDscRunAsCredential** 公共属性，用于允许在其他凭据上下文中运行任何 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="6b862-127">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="6b862-128">有关详细信息，请参阅[将凭据与 DSC 资源配合使用](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="6b862-128">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="6b862-129">其他信息</span><span class="sxs-lookup"><span data-stu-id="6b862-129">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="6b862-130">GetScript</span><span class="sxs-lookup"><span data-stu-id="6b862-130">GetScript</span></span>

<span data-ttu-id="6b862-131">DSC 不使用 `GetScript`，[Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet 执行 `GetScript` 以检索节点的当前状态。</span><span class="sxs-lookup"><span data-stu-id="6b862-131">DSC does not use the output from `GetScript` The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="6b862-132">`GetScript` 不需要返回值，如果指定返回值，则它必须是包含值为字符串的 Result 键的哈希表。</span><span class="sxs-lookup"><span data-stu-id="6b862-132">A return value is not required from `GetScript` If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="6b862-133">TestScript</span><span class="sxs-lookup"><span data-stu-id="6b862-133">TestScript</span></span>

<span data-ttu-id="6b862-134">DSC 执行 `TestScript` 以确定是否应运行 `SetScript`。</span><span class="sxs-lookup"><span data-stu-id="6b862-134">`TestScript` is executed by DSC to determine if `SetScript` should be run.</span></span> <span data-ttu-id="6b862-135">如果 `TestScript` 返回 `$false`，则 DSC 执行 `SetScript` 以使节点恢复到所需的状态。</span><span class="sxs-lookup"><span data-stu-id="6b862-135">If `TestScript` returns `$false`, DSC executes `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="6b862-136">它必须返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="6b862-136">It must return a boolean value.</span></span> <span data-ttu-id="6b862-137">`$true` 的结果表示节点是符合的，不应执行 `SetScript`。</span><span class="sxs-lookup"><span data-stu-id="6b862-137">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="6b862-138">[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet 执行 `TestScript` 以检索节点是否符合 `Script` 资源。</span><span class="sxs-lookup"><span data-stu-id="6b862-138">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes `TestScript` to retrieve the nodes compliance with the `Script` resources.</span></span> <span data-ttu-id="6b862-139">但是，在这种情况下，无论 `TestScript` 块返回什么，`SetScript` 都不会运行。</span><span class="sxs-lookup"><span data-stu-id="6b862-139">However, in this case, `SetScript` does not run, no matter what `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="6b862-140">`TestScript` 的所有输出都是其返回值的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b862-140">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="6b862-141">PowerShell 将未压缩的输出视为非零，这意味着无论节点的状态如何，`TestScript` 都将返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="6b862-141">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="6b862-142">这会导致不可预测的结果和误报，并导致在故障排除时出现问题。</span><span class="sxs-lookup"><span data-stu-id="6b862-142">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="6b862-143">SetScript</span><span class="sxs-lookup"><span data-stu-id="6b862-143">SetScript</span></span>

<span data-ttu-id="6b862-144">`SetScript` 修改节点以强制执行所需的状态。</span><span class="sxs-lookup"><span data-stu-id="6b862-144">`SetScript` modifies the node to enforce the desired state.</span></span> <span data-ttu-id="6b862-145">如果 `TestScript` 脚本块返回 `$false`，则其由 DSC 调用。</span><span class="sxs-lookup"><span data-stu-id="6b862-145">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="6b862-146">`SetScript` 应该没有返回值。</span><span class="sxs-lookup"><span data-stu-id="6b862-146">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="6b862-147">示例</span><span class="sxs-lookup"><span data-stu-id="6b862-147">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="6b862-148">示例 1：使用脚本资源编写示例文本</span><span class="sxs-lookup"><span data-stu-id="6b862-148">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="6b862-149">此示例测试每个节点上是否存在 `C:\TempFolder\TestFile.txt`。</span><span class="sxs-lookup"><span data-stu-id="6b862-149">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="6b862-150">如果它不存在，则使用 `SetScript` 创建它。</span><span class="sxs-lookup"><span data-stu-id="6b862-150">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="6b862-151">`GetScript` 返回文件的内容，并且不使用其返回值。</span><span class="sxs-lookup"><span data-stu-id="6b862-151">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="6b862-152">示例 2：使用脚本资源比较版本信息</span><span class="sxs-lookup"><span data-stu-id="6b862-152">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="6b862-153">此示例从创作计算机上的文本文件中检索符合的版本信息，并将其存储在 `$version` 变量中。</span><span class="sxs-lookup"><span data-stu-id="6b862-153">This example retrieves the _compliant_ version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="6b862-154">在生成节点的 MOF 文件时，DSC 将每个脚本块中的 `$using:version` 变量替换为 `$version` 变量的值。</span><span class="sxs-lookup"><span data-stu-id="6b862-154">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="6b862-155">在执行期间，符合的版本存储在每个节点上的文本文件中，并在后续执行时进行比较和更新。</span><span class="sxs-lookup"><span data-stu-id="6b862-155">During execution, the _compliant_ version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state.Result -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state.Result,$using:version)
                    return $true
                }
                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            }
        }
    }
}
```

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="6b862-156">示例 3：使用脚本资源中的参数</span><span class="sxs-lookup"><span data-stu-id="6b862-156">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="6b862-157">此示例通过使用 `using` 范围，从脚本资源中访问参数。</span><span class="sxs-lookup"><span data-stu-id="6b862-157">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span>
<span data-ttu-id="6b862-158">请注意，ConfigurationData 可通过类似的方式进行访问。</span><span class="sxs-lookup"><span data-stu-id="6b862-158">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="6b862-159">如示例 2 所示，版本应存储在目标节点上的本地文件中。</span><span class="sxs-lookup"><span data-stu-id="6b862-159">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="6b862-160">但本地文件路径和版本都是可配置的，这会将代码与配置数据分开。</span><span class="sxs-lookup"><span data-stu-id="6b862-160">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

```powershell
Configuration ScriptTest
{
    param
    (
        [Version]
        $Version,

        [string]
        $FilePath
    )

    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content -Path $using:FilePath
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:Version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }

                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                Set-Content -Path $using:FilePath -Value $using:Version
            }
        }
    }
}
```

<span data-ttu-id="6b862-161">生成的 MOF 文件包含通过 `using` 范围访问的变量及其值。</span><span class="sxs-lookup"><span data-stu-id="6b862-161">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="6b862-162">它们被注入每个使用变量的脚本块中。</span><span class="sxs-lookup"><span data-stu-id="6b862-162">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="6b862-163">为简洁起见，删除了测试和设置脚本：</span><span class="sxs-lookup"><span data-stu-id="6b862-163">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```

### <a name="known-limitations"></a><span data-ttu-id="6b862-164">已知限制</span><span class="sxs-lookup"><span data-stu-id="6b862-164">Known Limitations</span></span>

- <span data-ttu-id="6b862-165">使用拉取或推送服务器模型时，在脚本资源中传递的凭据并不总是可靠。</span><span class="sxs-lookup"><span data-stu-id="6b862-165">Credentials being passed within a script resource are not always reliable when using a pull or push server model.</span></span> <span data-ttu-id="6b862-166">在此情况下，建议使用完整资源，而不是使用脚本资源。</span><span class="sxs-lookup"><span data-stu-id="6b862-166">It is recommended to use a full resource rather than use a script resource in this case.</span></span>
