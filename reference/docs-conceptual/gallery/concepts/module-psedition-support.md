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
# <a name="modules-with-compatible-powershell-editions"></a>具有兼容的 PowerShell 版本的模块

从版本 5.1 开始，PowerShell 提供了各种版本，表现出不同的功能集和平台兼容性。

- **桌面版：** 在 .NET Framework 上生成，适用于 Windows 桌面、Windows Server、Windows Server Core 和大多数其他 Windows 版本上的 Windows PowerShell v4.0 和更低版本以及 Windows PowerShell 5.1。
- **核心版：** 在 .NET Core 上生成，适用于减少了占用情况的 Windows 版本（如 Windows IoT 和 Windows Nanoserver）上的 PowerShell Core 6.0 和更高版本以及 Windows PowerShell 5.1。

有关 PowerShell 版本的详细信息，请参阅 [about_PowerShell_Editions][]。

## <a name="declaring-compatible-editions"></a>声明兼容的版本

模块创建者可使用 `CompatiblePSEditions` 模块清单键声明其模块，使其与一个或多个 PowerShell 版本兼容。 仅 PowerShell 5.1 或更高版本支持该键。

> [!NOTE]
> 通过 `CompatiblePSEditions` 键或使用 `$PSEdition` 变量指定模块清单后，该清单无法导入到 PowerShell v4 或更低版本。

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

可通过 PowerShell 版本筛选列表来获取一列可用模块。

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

从 PowerShell 6 开始，`CompatiblePSEditions` 值用于确定从 `$env:windir\System32\WindowsPowerShell\v1.0\Modules` 导入模块时，模块是否兼容。
此行为仅适用于 Windows。 除此情况以外，该值仅用作元数据。

## <a name="finding-compatible-modules"></a>查找兼容的模块

PowerShell 库用户可使用 PSEdition_Desktop 和 PSEdition_Core 标记查找某特定 PowerShell 版本支持的模块列表 。

不带 PSEdition_Desktop 和 PSEdition_Core 标记的模块可以在 PowerShell Desktop 版本上运行 。

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a>面向多个版本

模块作者可发布面向 PowerShell 的两个版本（Desktop 和 Core）或其中之一的单一模块。

由于模块创建者必须使用 `$PSEdition` 变量在 RootModule 或模块清单中添加所需的逻辑，因此单一模块可同时在 Desktop 和 Core 版本上运行。 模块可以有两套以 CoreCLR 和 FullCLR 为目标的已编译 DLL 。 下面是包含用于加载适当 DLL 的逻辑的打包选项。

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a>选项 1：打包面向多个版本和多个 PowerShell 版本的模块

模块文件夹内容

- Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- PSScriptAnalyzer.psd1
- PSScriptAnalyzer.psm1
- ScriptAnalyzer.format.ps1xml
- ScriptAnalyzer.types.ps1xml
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- en-US\about_PSScriptAnalyzer.help.txt
- en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- Settings\CmdletDesign.psd1
- Settings\DSC.psd1
- Settings\ScriptFunctions.psd1
- Settings\ScriptingStyle.psd1
- Settings\ScriptSecurity.psd1

`PSScriptAnalyzer.psd1` 文件的内容

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

以下逻辑基于当前版本加载所需程序集。

`PSScriptAnalyzer.psm1` 文件的内容：

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

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a>选项 2：使用 PSD1 文件中的 $PSEdition 变量加载适当的 DLL

在 PS 5.1 或更高版本中，模块清单文件中允许使用 `$PSEdition` 全局变量。 使用此变量，模块作者可在模块清单文件中指定条件值。 可在受限语言模式或数据部分引用 `$PSEdition` 变量。

包含 `CompatiblePSEditions` 密钥的示例模块清单文件。

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

模块内容

- ModuleWithEditions\ModuleWithEditions.psd1
- ModuleWithEditions\clr\MyFullClrNM1.dll
- ModuleWithEditions\clr\MyFullClrNM2.dll
- ModuleWithEditions\clr\MyFullClrRM.dll
- ModuleWithEditions\coreclr\MyCoreClrNM1.dll
- ModuleWithEditions\coreclr\MyCoreClrNM2.dll
- ModuleWithEditions\coreclr\MyCoreClrRM.dll

## <a name="more-details"></a>更多详细信息

[PSEditions 脚本](script-psedition-support.md)

[PowerShell 库的 PSEditions 支持](../how-to/finding-packages/searching-by-compatibility.md)

[更新模块清单](/powershell/module/powershellget/update-modulemanifest)

[about_PowerShell_Editions][]

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
