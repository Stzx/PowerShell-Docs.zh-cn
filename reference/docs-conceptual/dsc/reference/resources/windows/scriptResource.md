---
ms.date: 09/20/2019
keywords: dsc,powershell,配置,安装程序
title: DSC Script 资源
ms.openlocfilehash: 50d4667396c8c619079288ec51599152ed2d6cd5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557016"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="94dd8-103">DSC Script 资源</span><span class="sxs-lookup"><span data-stu-id="94dd8-103">DSC Script Resource</span></span>

> <span data-ttu-id="94dd8-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="94dd8-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="94dd8-105">Windows PowerShell Desired State Configuration (DSC) 中的 **Script** 资源提供了在目标节点上运行 Windows PowerShell 脚本的机制。</span><span class="sxs-lookup"><span data-stu-id="94dd8-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="94dd8-106">**Script** 资源使用 **GetScript**、**SetScript** 和 **TestScript** 属性，这些属性包含定义用于执行相应 DSC 状态操作的脚本块。</span><span class="sxs-lookup"><span data-stu-id="94dd8-106">The **Script** resource uses **GetScript**, **SetScript**, and **TestScript** properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="94dd8-107">语法</span><span class="sxs-lookup"><span data-stu-id="94dd8-107">Syntax</span></span>

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
> <span data-ttu-id="94dd8-108">**GetScript**、**TestScript** 和 **SetScript** 块作为字符串存储。</span><span class="sxs-lookup"><span data-stu-id="94dd8-108">**GetScript**, **TestScript**, and **SetScript** blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="94dd8-109">属性</span><span class="sxs-lookup"><span data-stu-id="94dd8-109">Properties</span></span>

|<span data-ttu-id="94dd8-110">properties</span><span class="sxs-lookup"><span data-stu-id="94dd8-110">Property</span></span> |<span data-ttu-id="94dd8-111">说明</span><span class="sxs-lookup"><span data-stu-id="94dd8-111">Description</span></span> |
|---|---|
|<span data-ttu-id="94dd8-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="94dd8-112">GetScript</span></span> |<span data-ttu-id="94dd8-113">一个返回节点当前状态的脚本块。</span><span class="sxs-lookup"><span data-stu-id="94dd8-113">A script block that returns the current state of the Node.</span></span> |
|<span data-ttu-id="94dd8-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="94dd8-114">SetScript</span></span> |<span data-ttu-id="94dd8-115">DSC 在节点未处于所需状态时用于强制执行符合性的脚本块。</span><span class="sxs-lookup"><span data-stu-id="94dd8-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
|<span data-ttu-id="94dd8-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="94dd8-116">TestScript</span></span> |<span data-ttu-id="94dd8-117">一个用于确定节点是否处于所需状态的脚本块。</span><span class="sxs-lookup"><span data-stu-id="94dd8-117">A script block that determines if the Node is in the desired state.</span></span> |
|<span data-ttu-id="94dd8-118">凭据</span><span class="sxs-lookup"><span data-stu-id="94dd8-118">Credential</span></span> |<span data-ttu-id="94dd8-119">指示要用于运行此脚本的凭据（如果需要凭据）。</span><span class="sxs-lookup"><span data-stu-id="94dd8-119">Indicates the credentials to use for running this script, if credentials are required.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="94dd8-120">公共属性</span><span class="sxs-lookup"><span data-stu-id="94dd8-120">Common properties</span></span>

|<span data-ttu-id="94dd8-121">properties</span><span class="sxs-lookup"><span data-stu-id="94dd8-121">Property</span></span> |<span data-ttu-id="94dd8-122">说明</span><span class="sxs-lookup"><span data-stu-id="94dd8-122">Description</span></span> |
|---|---|
|<span data-ttu-id="94dd8-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="94dd8-123">DependsOn</span></span> |<span data-ttu-id="94dd8-124">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="94dd8-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="94dd8-125">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="94dd8-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="94dd8-126">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="94dd8-126">PsDscRunAsCredential</span></span> |<span data-ttu-id="94dd8-127">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="94dd8-127">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="94dd8-128">在 WMF 5.0 中添加了 **PsDscRunAsCredential** 公共属性，用于允许在其他凭据上下文中运行任何 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="94dd8-128">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="94dd8-129">有关详细信息，请参阅[将凭据与 DSC 资源配合使用](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="94dd8-129">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="94dd8-130">其他信息</span><span class="sxs-lookup"><span data-stu-id="94dd8-130">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="94dd8-131">GetScript</span><span class="sxs-lookup"><span data-stu-id="94dd8-131">GetScript</span></span>

<span data-ttu-id="94dd8-132">DSC 不使用来自 **GetScript** 的输出。</span><span class="sxs-lookup"><span data-stu-id="94dd8-132">DSC does not use the output from **GetScript**.</span></span> <span data-ttu-id="94dd8-133">[Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet 执行 **GetScript** 以检索节点的当前状态。</span><span class="sxs-lookup"><span data-stu-id="94dd8-133">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes **GetScript** to retrieve a node's current state.</span></span> <span data-ttu-id="94dd8-134">**GetScript** 不需要返回值。</span><span class="sxs-lookup"><span data-stu-id="94dd8-134">A return value is not required from **GetScript**.</span></span> <span data-ttu-id="94dd8-135">如果指定返回值，则它必须是包含值为字符串的 **Result** 键的哈希表。</span><span class="sxs-lookup"><span data-stu-id="94dd8-135">If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="94dd8-136">TestScript</span><span class="sxs-lookup"><span data-stu-id="94dd8-136">TestScript</span></span>

<span data-ttu-id="94dd8-137">DSC 执行 **TestScript** 以确定是否应运行 **SetScript**。</span><span class="sxs-lookup"><span data-stu-id="94dd8-137">**TestScript** is executed by DSC to determine if **SetScript** should be run.</span></span> <span data-ttu-id="94dd8-138">如果 **TestScript** 返回 `$false`，则 DSC 执行 **SetScript** 以使节点恢复到所需的状态。</span><span class="sxs-lookup"><span data-stu-id="94dd8-138">If **TestScript** returns `$false`, DSC executes **SetScript** to bring the node back to the desired state.</span></span> <span data-ttu-id="94dd8-139">它必须返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="94dd8-139">It must return a boolean value.</span></span> <span data-ttu-id="94dd8-140">`$true` 的结果表示节点是符合的，不应执行 **SetScript**。</span><span class="sxs-lookup"><span data-stu-id="94dd8-140">A result of `$true` indicates that the node is compliant and **SetScript** should not executed.</span></span>

<span data-ttu-id="94dd8-141">[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet 执行 **TestScript** 以检索节点是否符合 **Script** 资源。</span><span class="sxs-lookup"><span data-stu-id="94dd8-141">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes **TestScript** to retrieve the nodes compliance with the **Script** resources.</span></span>
<span data-ttu-id="94dd8-142">但是，在这种情况下，无论 **TestScript** 块返回什么，**SetScript** 都不会运行。</span><span class="sxs-lookup"><span data-stu-id="94dd8-142">However, in this case, **SetScript** does not run, no matter what **TestScript** block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="94dd8-143">**TestScript** 的所有输出都是其返回值的一部分。</span><span class="sxs-lookup"><span data-stu-id="94dd8-143">All output from your **TestScript** is part of its return value.</span></span> <span data-ttu-id="94dd8-144">PowerShell 将未压缩的输出视为非零，这意味着无论节点的状态如何，**TestScript** 都将返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="94dd8-144">PowerShell interprets unsuppressed output as non-zero, which means that your **TestScript** will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="94dd8-145">这会导致不可预测的结果和误报，并导致在故障排除时出现问题。</span><span class="sxs-lookup"><span data-stu-id="94dd8-145">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="94dd8-146">SetScript</span><span class="sxs-lookup"><span data-stu-id="94dd8-146">SetScript</span></span>

<span data-ttu-id="94dd8-147">**SetScript** 修改节点以强制执行所需的状态。</span><span class="sxs-lookup"><span data-stu-id="94dd8-147">**SetScript** modifies the node to enforce the desired state.</span></span> <span data-ttu-id="94dd8-148">如果 **TestScript** 脚本块返回 `$false`，则其由 DSC 调用。</span><span class="sxs-lookup"><span data-stu-id="94dd8-148">It is called by DSC if the **TestScript** script block returns `$false`.</span></span> <span data-ttu-id="94dd8-149">**SetScript** 应该没有返回值。</span><span class="sxs-lookup"><span data-stu-id="94dd8-149">The **SetScript** should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="94dd8-150">示例</span><span class="sxs-lookup"><span data-stu-id="94dd8-150">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="94dd8-151">示例 1：使用脚本资源编写示例文本</span><span class="sxs-lookup"><span data-stu-id="94dd8-151">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="94dd8-152">此示例测试每个节点上是否存在 `C:\TempFolder\TestFile.txt`。</span><span class="sxs-lookup"><span data-stu-id="94dd8-152">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="94dd8-153">如果它不存在，则使用 `SetScript` 创建它。</span><span class="sxs-lookup"><span data-stu-id="94dd8-153">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="94dd8-154">`GetScript` 返回文件的内容，并且不使用其返回值。</span><span class="sxs-lookup"><span data-stu-id="94dd8-154">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="94dd8-155">示例 2：使用脚本资源比较版本信息</span><span class="sxs-lookup"><span data-stu-id="94dd8-155">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="94dd8-156">此示例从创作计算机上的文本文件中检索符合的版本信息，并将其存储在 `$version` 变量中。</span><span class="sxs-lookup"><span data-stu-id="94dd8-156">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="94dd8-157">在生成节点的 MOF 文件时，DSC 将每个脚本块中的 `$using:version` 变量替换为 `$version` 变量的值。</span><span class="sxs-lookup"><span data-stu-id="94dd8-157">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="94dd8-158">在执行期间，符合的版本存储在每个节点上的文本文件中，并在后续执行时进行比较和更新。</span><span class="sxs-lookup"><span data-stu-id="94dd8-158">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

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

                if( $state['Result'] -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
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

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="94dd8-159">示例 3：使用脚本资源中的参数</span><span class="sxs-lookup"><span data-stu-id="94dd8-159">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="94dd8-160">此示例通过使用 `using` 范围，从脚本资源中访问参数。</span><span class="sxs-lookup"><span data-stu-id="94dd8-160">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span> <span data-ttu-id="94dd8-161">请注意，ConfigurationData 可通过类似的方式进行访问。</span><span class="sxs-lookup"><span data-stu-id="94dd8-161">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="94dd8-162">如示例 2 所示，版本应存储在目标节点上的本地文件中。</span><span class="sxs-lookup"><span data-stu-id="94dd8-162">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="94dd8-163">但本地文件路径和版本都是可配置的，这会将代码与配置数据分开。</span><span class="sxs-lookup"><span data-stu-id="94dd8-163">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

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

<span data-ttu-id="94dd8-164">生成的 MOF 文件包含通过 `using` 范围访问的变量及其值。</span><span class="sxs-lookup"><span data-stu-id="94dd8-164">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="94dd8-165">它们被注入每个使用变量的脚本块中。</span><span class="sxs-lookup"><span data-stu-id="94dd8-165">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="94dd8-166">为简洁起见，删除了测试和设置脚本：</span><span class="sxs-lookup"><span data-stu-id="94dd8-166">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```
