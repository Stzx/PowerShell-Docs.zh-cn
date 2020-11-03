---
description: 描述 Windows PowerShell 5.1 中包含的新功能。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5 1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200657"
---
# <a name="about_windows_powershell_51"></a>about_Windows_PowerShell_5 1

## <a name="short-description"></a>简短说明

描述 Windows PowerShell 5.1 中包含的新功能。

## <a name="long-description"></a>详细说明

Windows PowerShell 5.1 包含重要的新功能，这些功能可扩展其用途、提高其可用性，并使你能够更轻松、全面地控制和管理基于 Windows 的环境。

Windows PowerShell 5.1 向后兼容。 为 Windows PowerShell 4.0、Windows PowerShell 3.0 和 Windows PowerShell 2.0 设计的 cmdlet、提供程序、模块、管理单元、脚本、函数和配置文件通常适用于 Windows PowerShell 5.1，无需更改。

- 新 cmdlet：本地用户和组；Get-ComputerInfo
- PowerShellGet 改进包括强制签名模块和安装 JEA 模块
- PackageManagement 增加了对容器、CBS 安装程序、基于 EXE 的安装程序、CAB 包的支持
- DSC 和 PowerShell 类的调试改进
- 安全增强包括强制执行来自请求服务器和使用 PowerShellGet cmdlet 时的目录签名模块
- 响应大量的用户请求和问题

默认情况下，windows PowerShell 5.1 安装在 Windows Server 2016 和 Windows 10 上。 若要在 Windows Server 2012 R2、Windows 8.1 Enterprise 或 Windows 8.1 Pro 上安装 Windows PowerShell 5.1，请参阅 [安装和配置 WMF 5.1](/powershell/scripting/wmf/setup/install-configure)。
在安装 Windows Management Framework 5.1 之前，请务必阅读下载详细信息并满足所有系统要求。

你还可以在 [Windows powershell 中的新增功能](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50)中了解有关 windows powershell 5.1 的更改。

## <a name="new-scenarios-and-features-in-wmf-51"></a>WMF 5.1 中的新方案和功能

> 注意：此信息是预发布版本，可能会进行更改。

### <a name="powershell-editions"></a>PowerShell 版本
从 5.1 版本开始，PowerShell 在具有不同功能集和平台兼容性的不同版本中可用。

- **桌面版：** 基于 .NET Framework 而构建，兼容面向在 Windows 完整占用空间版本（例如，Server Core 和 Windows Desktop）上运行的 PowerShell 版本的脚本和模块。
- **核心版：** 以 .NET Core 为基础构建，提供与面向在缩减功能 Windows 版本（如 Nano Server 和 Windows IoT）上运行的 PowerShell 版本的脚本和模块的兼容性。

**详细了解如何使用 PowerShell 版本**

- [使用 $PSVersionTable 确定正在运行的 PowerShell 版本](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [使用 PSEdition 参数按 CompatiblePSEditions 筛选 Get-Module 结果](/powershell/module/microsoft.powershell.core/get-module)
- [阻止脚本执行，除非在 PowerShell 的兼容版本上运行](/powershell/scripting/gallery/concepts/script-psedition-support)
- [声明模块与特定 PowerShell 版本的兼容性](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a>目录 Cmdlet

在 [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) 模块中新增了两个新 cmdlet；这两个 cmdlet 可用于生成和验证 Windows 目录文件。

#### <a name="new-filecatalog"></a>New-FileCatalog

New-FileCatalog 用于为文件夹和文件集合创建 Windows 目录文件。
该目录文件包含指定路径中的所有文件的哈希值。 用户可以分发文件夹集合以及代表这些文件夹的对应的目录文件。 该信息对于验证自目录创建以来是否对文件夹进行了任何更改很有用。

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

支持目录版本 1 和 2。 版本 1 使用 SHA1 哈希算法来创建文件哈希值；版本 2 则使用 SHA256。 Windows Server 2008 R2 或 Windows 7 不支持目录版本 2。 你应在 Windows 8、Windows Server 2012 及更高版本的操作系统上使用目录版本 2。

若要验证目录文件（上面示例中的 Pester.cat 文件）的完整性，应使用 [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet 对其进行签名。

#### <a name="test-filecatalog"></a>Test-FileCatalog

Test-FileCatalog 用于验证代表一组文件夹的目录。

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

此 cmdlet 将目录中找到的所有文件的哈希值及其相对路径与磁盘中的进行比较。 如果它检测到文件哈希值和路径之间存在任何不匹配，将返回状态 ValidationFailed。 用户可通过使用 *-Detailed* 参数检索所有这些信息。 它还在“签名”属性中显示目录的签名状态，该结果与针对目录文件调用 [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet 的结果相同。 用户也可以使用 -FilesToSkip 参数在验证过程中跳过任何文件。

### <a name="module-analysis-cache"></a>模块分析缓存

从 WMF 5.1 开始，PowerShell 针对用于缓存有关模块的数据（如它导出的命令）的文件提供了控制。

默认情况下，此缓存存储在文件 `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` 中。 缓存通常在启动时进行读取（同时搜索命令），在模块导入一段时间之后在后台线程上进行写入。

若要更改缓存的默认位置，可在启动 PowerShell 前，设置 `$env:PSModuleAnalysisCachePath` 环境变量。 对此环境变量进行的更改只影响子进程。 值应指定 PowerShell 有权创建和写入文件的完整路径（包括文件名）。 若要禁用文件缓存，请将此值设置为无效位置，例如：

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

这会将路径设置为无效设备。 如果 PowerShell 无法写入路径，则不会返回任何错误，不过你可能会看到通过使用跟踪器进行报告的错误：

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

从缓存写出时，PowerShell 会检查不再存在的模块以避免进行不必要的大型缓存。 有时不需要这些检查，在这种情况下可以通过设置关闭它们：

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

此环境变量的设置会在当前进程中立即生效。

### <a name="specifying-module-version"></a>指定模块版本

在 WMF 5.1 中，`using module` 的行为方式与 PowerShell 中其他与模块相关的构造相同。 以前无法指定特定模块版本；如果有多个版本存在，则这会导致错误。

在 WMF 5.1 中：

* 可以使用 [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor)。
  此哈希表具有与 `Get-Module -FullyQualifiedName` 相同的格式。

  **示例：** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* 如果有多个版本的模块，则 PowerShell 会使用与 `Import-Module`**相同的解析逻辑** ，不会返回错误 - - 行为与 `Import-Module` 和 `Import-DscResource` 相同。

### <a name="improvements-to-pester"></a>针对 Pester 的改进

在 WMF 5.1 中，随 PowerShell 一起提供的 Pester 的版本已从3.3.5 更新为3.4.0，并添加了 GitHub [PR # 484](https://github.com/pester/Pester/pull/484)，这为 Nano Server 上的 Pester 启用了更好的行为。

可以通过在 https://github.com/pester/Pester/blob/master/CHANGELOG.md 处检查 ChangeLog.md 文件查看版本 3.3.5 到 3.4.0 的更改

## <a name="keywords"></a>字

Windows PowerShell 5.1 中的新增功能
