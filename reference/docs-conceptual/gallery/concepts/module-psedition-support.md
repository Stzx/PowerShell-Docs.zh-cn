---
ms.date: 06/10/2020
title: 具有兼容的 PowerShell 版本的模块
description: 本文介绍 PowerShellGet cmdlet 如何支持 PowerShell 模块的桌面版和核心版。
ms.openlocfilehash: 530101590cf83a1f43cbb9ce32d07a7e0ec79253
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661490"
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="052b3-103">具有兼容的 PowerShell 版本的模块</span><span class="sxs-lookup"><span data-stu-id="052b3-103">Modules with compatible PowerShell Editions</span></span>

<span data-ttu-id="052b3-104">从版本 5.1 开始，PowerShell 提供了各种版本，表现出不同的功能集和平台兼容性。</span><span class="sxs-lookup"><span data-stu-id="052b3-104">Starting with version 5.1, PowerShell is available in different editions, which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="052b3-105">**桌面版：** 在 .NET Framework 上生成，适用于 Windows 桌面、Windows Server、Windows Server Core 和大多数其他 Windows 版本上的 Windows PowerShell v4.0 和更低版本以及 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="052b3-105">**Desktop Edition:** Built on .NET Framework, applies to Windows PowerShell v4.0 and below as well as Windows PowerShell 5.1 on Windows Desktop, Windows Server, Windows Server Core and most other Windows editions.</span></span>
- <span data-ttu-id="052b3-106">**核心版：** 在 .NET Core 上生成，适用于减少了占用情况的 Windows 版本（如 Windows IoT 和 Windows Nanoserver）上的 PowerShell Core 6.0 和更高版本以及 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="052b3-106">**Core Edition:** Built on .NET Core, applies to PowerShell Core 6.0 and above as well as Windows PowerShell 5.1 on reduced footprint Windows Editions such as Windows IoT and Windows Nanoserver.</span></span>

<span data-ttu-id="052b3-107">有关 PowerShell 版本的详细信息，请参阅 [about_PowerShell_Editions][]。</span><span class="sxs-lookup"><span data-stu-id="052b3-107">For more information on PowerShell editions, see [about_PowerShell_Editions][].</span></span>

## <a name="declaring-compatible-editions"></a><span data-ttu-id="052b3-108">声明兼容的版本</span><span class="sxs-lookup"><span data-stu-id="052b3-108">Declaring compatible editions</span></span>

<span data-ttu-id="052b3-109">模块创建者可使用 `CompatiblePSEditions` 模块清单键声明其模块，使其与一个或多个 PowerShell 版本兼容。</span><span class="sxs-lookup"><span data-stu-id="052b3-109">Module authors can declare their modules to be compatible with one or more PowerShell editions using the `CompatiblePSEditions` module manifest key.</span></span> <span data-ttu-id="052b3-110">仅 PowerShell 5.1 或更高版本支持该键。</span><span class="sxs-lookup"><span data-stu-id="052b3-110">This key is only supported on PowerShell 5.1 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="052b3-111">通过 `CompatiblePSEditions` 键或使用 `$PSEdition` 变量指定模块清单后，该清单无法导入到 PowerShell v4 或更低版本。</span><span class="sxs-lookup"><span data-stu-id="052b3-111">Once a module manifest is specified with the `CompatiblePSEditions` key or uses the `$PSEdition` variable, it can not be imported on PowerShell v4 or lower.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

```powershell
$ModuleInfo | Get-Member CompatiblePSEditions
```

```Output
   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}
```

<span data-ttu-id="052b3-112">可通过 PowerShell 版本筛选列表来获取一列可用模块。</span><span class="sxs-lookup"><span data-stu-id="052b3-112">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>

```powershell
Get-Module -ListAvailable -PSEdition Desktop
```

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules

ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions
```

```powershell
Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
```

```Output
Desktop
Core
```

<span data-ttu-id="052b3-113">从 PowerShell 6 开始，`CompatiblePSEditions` 值用于确定从 `$env:windir\System32\WindowsPowerShell\v1.0\Modules` 导入模块时，模块是否兼容。</span><span class="sxs-lookup"><span data-stu-id="052b3-113">Beginning in PowerShell 6, the `CompatiblePSEditions` value is used to decide if a module is compatible when modules are imported from `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span></span>
<span data-ttu-id="052b3-114">此行为仅适用于 Windows。</span><span class="sxs-lookup"><span data-stu-id="052b3-114">This behavior only applies to Windows.</span></span> <span data-ttu-id="052b3-115">除此情况以外，该值仅用作元数据。</span><span class="sxs-lookup"><span data-stu-id="052b3-115">Outside of this scenario, the value is only used as metadata.</span></span>

## <a name="finding-compatible-modules"></a><span data-ttu-id="052b3-116">查找兼容的模块</span><span class="sxs-lookup"><span data-stu-id="052b3-116">Finding compatible modules</span></span>

<span data-ttu-id="052b3-117">PowerShell 库用户可使用 PSEdition_Desktop 和 PSEdition_Core 标记查找某特定 PowerShell 版本支持的模块列表 。</span><span class="sxs-lookup"><span data-stu-id="052b3-117">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags **PSEdition_Desktop** and **PSEdition_Core**.</span></span>

<span data-ttu-id="052b3-118">不带 PSEdition_Desktop 和 PSEdition_Core 标记的模块可以在 PowerShell Desktop 版本上运行 。</span><span class="sxs-lookup"><span data-stu-id="052b3-118">Modules without **PSEdition_Desktop** and **PSEdition_Core** tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a><span data-ttu-id="052b3-119">面向多个版本</span><span class="sxs-lookup"><span data-stu-id="052b3-119">Targeting multiple editions</span></span>

<span data-ttu-id="052b3-120">模块作者可发布面向 PowerShell 的两个版本（Desktop 和 Core）或其中之一的单一模块。</span><span class="sxs-lookup"><span data-stu-id="052b3-120">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core).</span></span>

<span data-ttu-id="052b3-121">由于模块创建者必须使用 `$PSEdition` 变量在 RootModule 或模块清单中添加所需的逻辑，因此单一模块可同时在 Desktop 和 Core 版本上运行。</span><span class="sxs-lookup"><span data-stu-id="052b3-121">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using `$PSEdition` variable.</span></span> <span data-ttu-id="052b3-122">模块可以有两套以 CoreCLR 和 FullCLR 为目标的已编译 DLL 。</span><span class="sxs-lookup"><span data-stu-id="052b3-122">Modules can have two sets of compiled DLLs targeting both **CoreCLR** and **FullCLR**.</span></span> <span data-ttu-id="052b3-123">下面是包含用于加载适当 DLL 的逻辑的打包选项。</span><span class="sxs-lookup"><span data-stu-id="052b3-123">Here are the packaging options with logic for loading proper DLLs.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="052b3-124">选项 1：打包面向多个版本和多个 PowerShell 版本的模块</span><span class="sxs-lookup"><span data-stu-id="052b3-124">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

<span data-ttu-id="052b3-125">模块文件夹内容</span><span class="sxs-lookup"><span data-stu-id="052b3-125">Module folder contents</span></span>

- <span data-ttu-id="052b3-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="052b3-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="052b3-128">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-128">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="052b3-129">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="052b3-129">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="052b3-130">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="052b3-130">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="052b3-131">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="052b3-131">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="052b3-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="052b3-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="052b3-134">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="052b3-134">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="052b3-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="052b3-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="052b3-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="052b3-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="052b3-138">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-138">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="052b3-139">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-139">Settings\DSC.psd1</span></span>
- <span data-ttu-id="052b3-140">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-140">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="052b3-141">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-141">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="052b3-142">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-142">Settings\ScriptSecurity.psd1</span></span>

<span data-ttu-id="052b3-143">`PSScriptAnalyzer.psd1` 文件的内容</span><span class="sxs-lookup"><span data-stu-id="052b3-143">Contents of `PSScriptAnalyzer.psd1` file</span></span>

```powershell
@{

# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

<span data-ttu-id="052b3-144">以下逻辑基于当前版本加载所需程序集。</span><span class="sxs-lookup"><span data-stu-id="052b3-144">Below logic loads the required assemblies depending on the current edition or version.</span></span>

<span data-ttu-id="052b3-145">`PSScriptAnalyzer.psm1` 文件的内容：</span><span class="sxs-lookup"><span data-stu-id="052b3-145">Contents of `PSScriptAnalyzer.psm1` file:</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0')
    {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
}
```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a><span data-ttu-id="052b3-146">选项 2：使用 PSD1 文件中的 $PSEdition 变量加载适当的 DLL</span><span class="sxs-lookup"><span data-stu-id="052b3-146">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs</span></span>

<span data-ttu-id="052b3-147">在 PS 5.1 或更高版本中，模块清单文件中允许使用 `$PSEdition` 全局变量。</span><span class="sxs-lookup"><span data-stu-id="052b3-147">In PS 5.1 or newer, `$PSEdition` global variable is allowed in the module manifest file.</span></span> <span data-ttu-id="052b3-148">使用此变量，模块作者可在模块清单文件中指定条件值。</span><span class="sxs-lookup"><span data-stu-id="052b3-148">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="052b3-149">可在受限语言模式或数据部分引用 `$PSEdition` 变量。</span><span class="sxs-lookup"><span data-stu-id="052b3-149">`$PSEdition` variable can be referenced in restricted language mode or a Data section.</span></span>

<span data-ttu-id="052b3-150">包含 `CompatiblePSEditions` 密钥的示例模块清单文件。</span><span class="sxs-lookup"><span data-stu-id="052b3-150">Sample module manifest file with `CompatiblePSEditions` key.</span></span>

```powershell
@{
    # Script module or binary module file associated with this manifest.
    RootModule = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrRM.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrRM.dll'
    }

    # Supported PSEditions
    CompatiblePSEditions = 'Desktop', 'Core'

    # Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
    NestedModules = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrNM1.dll',
        'coreclr\MyCoreClrNM2.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrNM1.dll',
        'clr\MyFullClrNM2.dll'
    }
}
```

<span data-ttu-id="052b3-151">模块内容</span><span class="sxs-lookup"><span data-stu-id="052b3-151">Module contents</span></span>

- <span data-ttu-id="052b3-152">ModuleWithEditions\ModuleWithEditions.psd1</span><span class="sxs-lookup"><span data-stu-id="052b3-152">ModuleWithEditions\ModuleWithEditions.psd1</span></span>
- <span data-ttu-id="052b3-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span></span>
- <span data-ttu-id="052b3-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span></span>
- <span data-ttu-id="052b3-155">ModuleWithEditions\clr\MyFullClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-155">ModuleWithEditions\clr\MyFullClrRM.dll</span></span>
- <span data-ttu-id="052b3-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span></span>
- <span data-ttu-id="052b3-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span></span>
- <span data-ttu-id="052b3-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="052b3-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span></span>

## <a name="more-details"></a><span data-ttu-id="052b3-159">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="052b3-159">More details</span></span>

[<span data-ttu-id="052b3-160">PSEditions 脚本</span><span class="sxs-lookup"><span data-stu-id="052b3-160">Scripts with PSEditions</span></span>](script-psedition-support.md)

[<span data-ttu-id="052b3-161">PowerShell 库的 PSEditions 支持</span><span class="sxs-lookup"><span data-stu-id="052b3-161">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)

[<span data-ttu-id="052b3-162">更新模块清单</span><span class="sxs-lookup"><span data-stu-id="052b3-162">Update module manifest</span></span>](/powershell/module/powershellget/update-modulemanifest)

<span data-ttu-id="052b3-163">[about_PowerShell_Editions][]</span><span class="sxs-lookup"><span data-stu-id="052b3-163">[about_PowerShell_Editions][]</span></span>

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
