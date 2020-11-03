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
# <a name="about_windows_powershell_51"></a><span data-ttu-id="4e653-104">about_Windows_PowerShell_5 1</span><span class="sxs-lookup"><span data-stu-id="4e653-104">about_Windows_PowerShell_5.1</span></span>

## <a name="short-description"></a><span data-ttu-id="4e653-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="4e653-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="4e653-106">描述 Windows PowerShell 5.1 中包含的新功能。</span><span class="sxs-lookup"><span data-stu-id="4e653-106">Describes new features that are included in Windows PowerShell 5.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="4e653-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="4e653-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="4e653-108">Windows PowerShell 5.1 包含重要的新功能，这些功能可扩展其用途、提高其可用性，并使你能够更轻松、全面地控制和管理基于 Windows 的环境。</span><span class="sxs-lookup"><span data-stu-id="4e653-108">Windows PowerShell 5.1 includes significant new features that extend its use, improve its usability, and allow you to control and manage Windows-based environments more easily and comprehensively.</span></span>

<span data-ttu-id="4e653-109">Windows PowerShell 5.1 向后兼容。</span><span class="sxs-lookup"><span data-stu-id="4e653-109">Windows PowerShell 5.1 is backward-compatible.</span></span> <span data-ttu-id="4e653-110">为 Windows PowerShell 4.0、Windows PowerShell 3.0 和 Windows PowerShell 2.0 设计的 cmdlet、提供程序、模块、管理单元、脚本、函数和配置文件通常适用于 Windows PowerShell 5.1，无需更改。</span><span class="sxs-lookup"><span data-stu-id="4e653-110">Cmdlets, providers, modules, snap-ins, scripts, functions, and profiles that were designed for Windows PowerShell 4.0, Windows PowerShell 3.0, and Windows PowerShell 2.0 generally work in Windows PowerShell 5.1 without changes.</span></span>

- <span data-ttu-id="4e653-111">新 cmdlet：本地用户和组；Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="4e653-111">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="4e653-112">PowerShellGet 改进包括强制签名模块和安装 JEA 模块</span><span class="sxs-lookup"><span data-stu-id="4e653-112">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="4e653-113">PackageManagement 增加了对容器、CBS 安装程序、基于 EXE 的安装程序、CAB 包的支持</span><span class="sxs-lookup"><span data-stu-id="4e653-113">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="4e653-114">DSC 和 PowerShell 类的调试改进</span><span class="sxs-lookup"><span data-stu-id="4e653-114">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="4e653-115">安全增强包括强制执行来自请求服务器和使用 PowerShellGet cmdlet 时的目录签名模块</span><span class="sxs-lookup"><span data-stu-id="4e653-115">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="4e653-116">响应大量的用户请求和问题</span><span class="sxs-lookup"><span data-stu-id="4e653-116">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="4e653-117">默认情况下，windows PowerShell 5.1 安装在 Windows Server 2016 和 Windows 10 上。</span><span class="sxs-lookup"><span data-stu-id="4e653-117">Windows PowerShell 5.1 is installed by default on Windows Server 2016 and Windows 10.</span></span> <span data-ttu-id="4e653-118">若要在 Windows Server 2012 R2、Windows 8.1 Enterprise 或 Windows 8.1 Pro 上安装 Windows PowerShell 5.1，请参阅 [安装和配置 WMF 5.1](/powershell/scripting/wmf/setup/install-configure)。</span><span class="sxs-lookup"><span data-stu-id="4e653-118">To install Windows PowerShell 5.1 on Windows Server 2012 R2, Windows 8.1 Enterprise, or Windows 8.1 Pro, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
<span data-ttu-id="4e653-119">在安装 Windows Management Framework 5.1 之前，请务必阅读下载详细信息并满足所有系统要求。</span><span class="sxs-lookup"><span data-stu-id="4e653-119">Be sure to read the download details, and meet all system requirements, before you install Windows Management Framework 5.1.</span></span>

<span data-ttu-id="4e653-120">你还可以在 [Windows powershell 中的新增功能](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50)中了解有关 windows powershell 5.1 的更改。</span><span class="sxs-lookup"><span data-stu-id="4e653-120">You can also read about changes to Windows PowerShell 5.1 in [What's New in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span></span>

## <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="4e653-121">WMF 5.1 中的新方案和功能</span><span class="sxs-lookup"><span data-stu-id="4e653-121">New Scenarios and Features in WMF 5.1</span></span>

> <span data-ttu-id="4e653-122">注意：此信息是预发布版本，可能会进行更改。</span><span class="sxs-lookup"><span data-stu-id="4e653-122">Note: This information is preliminary and subject to change.</span></span>

### <a name="powershell-editions"></a><span data-ttu-id="4e653-123">PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="4e653-123">PowerShell Editions</span></span>
<span data-ttu-id="4e653-124">从 5.1 版本开始，PowerShell 在具有不同功能集和平台兼容性的不同版本中可用。</span><span class="sxs-lookup"><span data-stu-id="4e653-124">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="4e653-125">**桌面版：** 基于 .NET Framework 而构建，兼容面向在 Windows 完整占用空间版本（例如，Server Core 和 Windows Desktop）上运行的 PowerShell 版本的脚本和模块。</span><span class="sxs-lookup"><span data-stu-id="4e653-125">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="4e653-126">**核心版：** 以 .NET Core 为基础构建，提供与面向在缩减功能 Windows 版本（如 Nano Server 和 Windows IoT）上运行的 PowerShell 版本的脚本和模块的兼容性。</span><span class="sxs-lookup"><span data-stu-id="4e653-126">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="4e653-127">**详细了解如何使用 PowerShell 版本**</span><span class="sxs-lookup"><span data-stu-id="4e653-127">**Learn more about using PowerShell Editions**</span></span>

- [<span data-ttu-id="4e653-128">使用 $PSVersionTable 确定正在运行的 PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="4e653-128">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="4e653-129">使用 PSEdition 参数按 CompatiblePSEditions 筛选 Get-Module 结果</span><span class="sxs-lookup"><span data-stu-id="4e653-129">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="4e653-130">阻止脚本执行，除非在 PowerShell 的兼容版本上运行</span><span class="sxs-lookup"><span data-stu-id="4e653-130">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/scripting/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="4e653-131">声明模块与特定 PowerShell 版本的兼容性</span><span class="sxs-lookup"><span data-stu-id="4e653-131">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a><span data-ttu-id="4e653-132">目录 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4e653-132">Catalog Cmdlets</span></span>

<span data-ttu-id="4e653-133">在 [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) 模块中新增了两个新 cmdlet；这两个 cmdlet 可用于生成和验证 Windows 目录文件。</span><span class="sxs-lookup"><span data-stu-id="4e653-133">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) module; these generate and validate Windows catalog files.</span></span>

#### <a name="new-filecatalog"></a><span data-ttu-id="4e653-134">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="4e653-134">New-FileCatalog</span></span>

<span data-ttu-id="4e653-135">New-FileCatalog 用于为文件夹和文件集合创建 Windows 目录文件。</span><span class="sxs-lookup"><span data-stu-id="4e653-135">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span>
<span data-ttu-id="4e653-136">该目录文件包含指定路径中的所有文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="4e653-136">This catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="4e653-137">用户可以分发文件夹集合以及代表这些文件夹的对应的目录文件。</span><span class="sxs-lookup"><span data-stu-id="4e653-137">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span> <span data-ttu-id="4e653-138">该信息对于验证自目录创建以来是否对文件夹进行了任何更改很有用。</span><span class="sxs-lookup"><span data-stu-id="4e653-138">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="4e653-139">支持目录版本 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="4e653-139">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="4e653-140">版本 1 使用 SHA1 哈希算法来创建文件哈希值；版本 2 则使用 SHA256。</span><span class="sxs-lookup"><span data-stu-id="4e653-140">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span> <span data-ttu-id="4e653-141">Windows Server 2008 R2 或 Windows 7 不支持目录版本 2。</span><span class="sxs-lookup"><span data-stu-id="4e653-141">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7*.</span></span> <span data-ttu-id="4e653-142">你应在 Windows 8、Windows Server 2012 及更高版本的操作系统上使用目录版本 2。</span><span class="sxs-lookup"><span data-stu-id="4e653-142">You should use catalog version 2 on *Windows 8* , *Windows Server 2012* , and later operating systems.</span></span>

<span data-ttu-id="4e653-143">若要验证目录文件（上面示例中的 Pester.cat 文件）的完整性，应使用 [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet 对其进行签名。</span><span class="sxs-lookup"><span data-stu-id="4e653-143">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet.</span></span>

#### <a name="test-filecatalog"></a><span data-ttu-id="4e653-144">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="4e653-144">Test-FileCatalog</span></span>

<span data-ttu-id="4e653-145">Test-FileCatalog 用于验证代表一组文件夹的目录。</span><span class="sxs-lookup"><span data-stu-id="4e653-145">Test-FileCatalog validates the catalog representing a set of folders.</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="4e653-146">此 cmdlet 将目录中找到的所有文件的哈希值及其相对路径与磁盘中的进行比较。</span><span class="sxs-lookup"><span data-stu-id="4e653-146">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk*.</span></span> <span data-ttu-id="4e653-147">如果它检测到文件哈希值和路径之间存在任何不匹配，将返回状态 ValidationFailed。</span><span class="sxs-lookup"><span data-stu-id="4e653-147">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed*.</span></span> <span data-ttu-id="4e653-148">用户可通过使用 *-Detailed* 参数检索所有这些信息。</span><span class="sxs-lookup"><span data-stu-id="4e653-148">Users can retrieve all this information by using the *-Detailed* parameter.</span></span> <span data-ttu-id="4e653-149">它还在“签名”属性中显示目录的签名状态，该结果与针对目录文件调用 [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet 的结果相同。</span><span class="sxs-lookup"><span data-stu-id="4e653-149">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet on the catalog file.</span></span> <span data-ttu-id="4e653-150">用户也可以使用 -FilesToSkip 参数在验证过程中跳过任何文件。</span><span class="sxs-lookup"><span data-stu-id="4e653-150">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span>

### <a name="module-analysis-cache"></a><span data-ttu-id="4e653-151">模块分析缓存</span><span class="sxs-lookup"><span data-stu-id="4e653-151">Module Analysis Cache</span></span>

<span data-ttu-id="4e653-152">从 WMF 5.1 开始，PowerShell 针对用于缓存有关模块的数据（如它导出的命令）的文件提供了控制。</span><span class="sxs-lookup"><span data-stu-id="4e653-152">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="4e653-153">默认情况下，此缓存存储在文件 `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` 中。</span><span class="sxs-lookup"><span data-stu-id="4e653-153">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="4e653-154">缓存通常在启动时进行读取（同时搜索命令），在模块导入一段时间之后在后台线程上进行写入。</span><span class="sxs-lookup"><span data-stu-id="4e653-154">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="4e653-155">若要更改缓存的默认位置，可在启动 PowerShell 前，设置 `$env:PSModuleAnalysisCachePath` 环境变量。</span><span class="sxs-lookup"><span data-stu-id="4e653-155">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="4e653-156">对此环境变量进行的更改只影响子进程。</span><span class="sxs-lookup"><span data-stu-id="4e653-156">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="4e653-157">值应指定 PowerShell 有权创建和写入文件的完整路径（包括文件名）。</span><span class="sxs-lookup"><span data-stu-id="4e653-157">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="4e653-158">若要禁用文件缓存，请将此值设置为无效位置，例如：</span><span class="sxs-lookup"><span data-stu-id="4e653-158">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="4e653-159">这会将路径设置为无效设备。</span><span class="sxs-lookup"><span data-stu-id="4e653-159">This sets the path to an invalid device.</span></span> <span data-ttu-id="4e653-160">如果 PowerShell 无法写入路径，则不会返回任何错误，不过你可能会看到通过使用跟踪器进行报告的错误：</span><span class="sxs-lookup"><span data-stu-id="4e653-160">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

<span data-ttu-id="4e653-161">从缓存写出时，PowerShell 会检查不再存在的模块以避免进行不必要的大型缓存。</span><span class="sxs-lookup"><span data-stu-id="4e653-161">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="4e653-162">有时不需要这些检查，在这种情况下可以通过设置关闭它们：</span><span class="sxs-lookup"><span data-stu-id="4e653-162">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="4e653-163">此环境变量的设置会在当前进程中立即生效。</span><span class="sxs-lookup"><span data-stu-id="4e653-163">Setting this environment variable will take effect immediately in the current process.</span></span>

### <a name="specifying-module-version"></a><span data-ttu-id="4e653-164">指定模块版本</span><span class="sxs-lookup"><span data-stu-id="4e653-164">Specifying module version</span></span>

<span data-ttu-id="4e653-165">在 WMF 5.1 中，`using module` 的行为方式与 PowerShell 中其他与模块相关的构造相同。</span><span class="sxs-lookup"><span data-stu-id="4e653-165">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span> <span data-ttu-id="4e653-166">以前无法指定特定模块版本；如果有多个版本存在，则这会导致错误。</span><span class="sxs-lookup"><span data-stu-id="4e653-166">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="4e653-167">在 WMF 5.1 中：</span><span class="sxs-lookup"><span data-stu-id="4e653-167">In WMF 5.1:</span></span>

* <span data-ttu-id="4e653-168">可以使用 [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor)。</span><span class="sxs-lookup"><span data-stu-id="4e653-168">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span></span>
  <span data-ttu-id="4e653-169">此哈希表具有与 `Get-Module -FullyQualifiedName` 相同的格式。</span><span class="sxs-lookup"><span data-stu-id="4e653-169">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="4e653-170">**示例：** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="4e653-170">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

* <span data-ttu-id="4e653-171">如果有多个版本的模块，则 PowerShell 会使用与 `Import-Module`**相同的解析逻辑** ，不会返回错误 - - 行为与 `Import-Module` 和 `Import-DscResource` 相同。</span><span class="sxs-lookup"><span data-stu-id="4e653-171">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

### <a name="improvements-to-pester"></a><span data-ttu-id="4e653-172">针对 Pester 的改进</span><span class="sxs-lookup"><span data-stu-id="4e653-172">Improvements to Pester</span></span>

<span data-ttu-id="4e653-173">在 WMF 5.1 中，随 PowerShell 一起提供的 Pester 的版本已从3.3.5 更新为3.4.0，并添加了 GitHub [PR # 484](https://github.com/pester/Pester/pull/484)，这为 Nano Server 上的 Pester 启用了更好的行为。</span><span class="sxs-lookup"><span data-stu-id="4e653-173">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of GitHub [PR# 484](https://github.com/pester/Pester/pull/484), which enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="4e653-174">可以通过在 https://github.com/pester/Pester/blob/master/CHANGELOG.md 处检查 ChangeLog.md 文件查看版本 3.3.5 到 3.4.0 的更改</span><span class="sxs-lookup"><span data-stu-id="4e653-174">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>

## <a name="keywords"></a><span data-ttu-id="4e653-175">字</span><span class="sxs-lookup"><span data-stu-id="4e653-175">KEYWORDS</span></span>

<span data-ttu-id="4e653-176">Windows PowerShell 5.1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="4e653-176">What's New in Windows PowerShell 5.1</span></span>
