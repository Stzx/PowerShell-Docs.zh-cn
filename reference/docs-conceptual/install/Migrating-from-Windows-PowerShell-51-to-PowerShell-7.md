---
title: 从 Windows PowerShell 5.1 迁移到 PowerShell 7
description: 为 Windows 平台从 PowerShell 5.1 更新到 PowerShell 7。
ms.date: 03/25/2020
ms.openlocfilehash: cb14a4f159b6dc33f31386da4264c0ebb640aef8
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "83809203"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a><span data-ttu-id="f8236-103">从 Windows PowerShell 5.1 迁移到 PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="f8236-103">Migrating from Windows PowerShell 5.1 to PowerShell 7</span></span>

<span data-ttu-id="f8236-104">PowerShell 7 是专为云、本地和混合环境设计的，它包含增强功能和[新功能](../whats-new/What-s-New-in-PowerShell-70.md)。</span><span class="sxs-lookup"><span data-stu-id="f8236-104">Designed for cloud, on-premises, and hybrid environments, PowerShell 7 is packed with enhancements and [new features](../whats-new/What-s-New-in-PowerShell-70.md).</span></span>

- <span data-ttu-id="f8236-105">与 Windows PowerShell 并行安装和运行</span><span class="sxs-lookup"><span data-stu-id="f8236-105">Installs and runs side-by-side with Windows PowerShell</span></span>
- <span data-ttu-id="f8236-106">提升了与现有 Windows PowerShell 模块的兼容性</span><span class="sxs-lookup"><span data-stu-id="f8236-106">Improved compatibility with existing Windows PowerShell modules</span></span>
- <span data-ttu-id="f8236-107">新语言功能（如三元运算符和 `ForEach-Object -Parallel`）</span><span class="sxs-lookup"><span data-stu-id="f8236-107">New language features, like ternary operators and `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="f8236-108">提高了性能</span><span class="sxs-lookup"><span data-stu-id="f8236-108">Improved performance</span></span>
- <span data-ttu-id="f8236-109">基于 SSH 的远程处理</span><span class="sxs-lookup"><span data-stu-id="f8236-109">SSH-based remoting</span></span>
- <span data-ttu-id="f8236-110">跨平台互操作性</span><span class="sxs-lookup"><span data-stu-id="f8236-110">Cross-platform interoperability</span></span>
- <span data-ttu-id="f8236-111">支持 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="f8236-111">Support for Docker containers</span></span>

<span data-ttu-id="f8236-112">PowerShell 7 与 Windows PowerShell 并行运行，可便于你在部署前轻松地测试和比较各个版本。</span><span class="sxs-lookup"><span data-stu-id="f8236-112">PowerShell 7 works side-by-side with Windows PowerShell letting you easily test and compare between editions before deployment.</span></span> <span data-ttu-id="f8236-113">迁移简单、快捷、安全，</span><span class="sxs-lookup"><span data-stu-id="f8236-113">Migration is simple, quick, and safe.</span></span>

<span data-ttu-id="f8236-114">以下 Windows 操作系统支持 PowerShell 7：</span><span class="sxs-lookup"><span data-stu-id="f8236-114">PowerShell 7 is supported on the following Windows operating systems:</span></span>

- <span data-ttu-id="f8236-115">Windows 8.1 和 10</span><span class="sxs-lookup"><span data-stu-id="f8236-115">Windows 8.1 and 10</span></span>
- <span data-ttu-id="f8236-116">Windows Server 2012、2012 R2、2016 和 2019</span><span class="sxs-lookup"><span data-stu-id="f8236-116">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>

<span data-ttu-id="f8236-117">PowerShell 7 还在 macOS 和多个 Linux 发行版本上运行。</span><span class="sxs-lookup"><span data-stu-id="f8236-117">PowerShell 7 also runs on macOS and several Linux distributions.</span></span> <span data-ttu-id="f8236-118">若要获取受支持操作系统的列表，并了解支持生命周期，请参阅 [PowerShell 支持生命周期](/powershell/scripting/powershell-support-lifecycle)。</span><span class="sxs-lookup"><span data-stu-id="f8236-118">For a list of supported operating systems and information about the support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

## <a name="installing-powershell-7"></a><span data-ttu-id="f8236-119">安装 PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="f8236-119">Installing PowerShell 7</span></span>

<span data-ttu-id="f8236-120">为了实现灵活性并满足 IT、DevOps 工程师和开发人员的需求，有多种 PowerShell 7 安装方法可供选择。</span><span class="sxs-lookup"><span data-stu-id="f8236-120">For flexibility and to support the needs of IT, DevOps engineers, and developers, there are several options available to install PowerShell 7.</span></span> <span data-ttu-id="f8236-121">在大多数情况下，可以简化为以下几种安装方法：</span><span class="sxs-lookup"><span data-stu-id="f8236-121">In most cases, the installation options can be reduced to the following methods:</span></span>

- <span data-ttu-id="f8236-122">使用 [MSI 包](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)部署 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8236-122">Deploy PowerShell using the [MSI package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)</span></span>
- <span data-ttu-id="f8236-123">使用 [ZIP 包](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)部署 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8236-123">Deploy PowerShell using the [ZIP package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)</span></span>

> [!NOTE]
> <span data-ttu-id="f8236-124">可以使用 [System Center Configuration Manager (SCCM)](/configmgr/apps/) 等管理产品来部署和更新 MSI 包。</span><span class="sxs-lookup"><span data-stu-id="f8236-124">The MSI package can be deployed and updated with management products such as [System Center Configuration Manager (SCCM)](/configmgr/apps/).</span></span> <span data-ttu-id="f8236-125">包是从 [GitHub“发布”页](https://github.com/PowerShell/PowerShell/releases)下载的。</span><span class="sxs-lookup"><span data-stu-id="f8236-125">Download the packages from [GitHub Release page](https://github.com/PowerShell/PowerShell/releases).</span></span>

<span data-ttu-id="f8236-126">必须有管理员权限，才能部署 MSI 包。</span><span class="sxs-lookup"><span data-stu-id="f8236-126">Deploying the MSI package requires Administrator permission.</span></span> <span data-ttu-id="f8236-127">任何用户都可以部署 ZIP 包。</span><span class="sxs-lookup"><span data-stu-id="f8236-127">The ZIP package can be deployed by any user.</span></span> <span data-ttu-id="f8236-128">在进行完整安装之前，ZIP 包是安装 PowerShell 7 进行测试的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="f8236-128">The ZIP package is the easiest way to install PowerShell 7 for testing, before committing to a full installation.</span></span>

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a><span data-ttu-id="f8236-129">并行使用 PowerShell 7 与 Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="f8236-129">Using PowerShell 7 side-by-side with Windows PowerShell 5.1</span></span>

<span data-ttu-id="f8236-130">根据设计，PowerShell 7 可以与 Windows PowerShell 5.1 共存。</span><span class="sxs-lookup"><span data-stu-id="f8236-130">PowerShell 7 is designed to coexist with Windows PowerShell 5.1.</span></span> <span data-ttu-id="f8236-131">以下功能可确保你的 PowerShell 投资受到保护，并能轻松迁移到 PowerShell 7。</span><span class="sxs-lookup"><span data-stu-id="f8236-131">The following features ensure that your investment in PowerShell is protected and your migration to PowerShell 7 is simple.</span></span>

- <span data-ttu-id="f8236-132">独立的安装路径和可执行文件名</span><span class="sxs-lookup"><span data-stu-id="f8236-132">Separate installation path and executable name</span></span>
- <span data-ttu-id="f8236-133">独立的 PSModulePath</span><span class="sxs-lookup"><span data-stu-id="f8236-133">Separate PSModulePath</span></span>
- <span data-ttu-id="f8236-134">每个版本的独立配置文件</span><span class="sxs-lookup"><span data-stu-id="f8236-134">Separate profiles for each version</span></span>
- <span data-ttu-id="f8236-135">提升了模块兼容性</span><span class="sxs-lookup"><span data-stu-id="f8236-135">Improved module compatibility</span></span>
- <span data-ttu-id="f8236-136">新增了远程处理终结点</span><span class="sxs-lookup"><span data-stu-id="f8236-136">New remoting endpoints</span></span>
- <span data-ttu-id="f8236-137">组策略支持</span><span class="sxs-lookup"><span data-stu-id="f8236-137">Group policy support</span></span>
- <span data-ttu-id="f8236-138">独立的事件日志</span><span class="sxs-lookup"><span data-stu-id="f8236-138">Separate Event logs</span></span>

### <a name="separate-installation-path-and-executable-name"></a><span data-ttu-id="f8236-139">独立的安装路径和可执行文件名</span><span class="sxs-lookup"><span data-stu-id="f8236-139">Separate installation path and executable name</span></span>

<span data-ttu-id="f8236-140">PowerShell 7 安装到新目录，这样就能与 Windows PowerShell 5.1 并行执行了。</span><span class="sxs-lookup"><span data-stu-id="f8236-140">PowerShell 7 installs to a new directory, enabling side-by-side execution with Windows PowerShell 5.1.</span></span>

<span data-ttu-id="f8236-141">按版本列出的安装位置：</span><span class="sxs-lookup"><span data-stu-id="f8236-141">Install locations by version:</span></span>

- <span data-ttu-id="f8236-142">Windows PowerShell 5.1：`$env:WINDIR\System32\WindowsPowerShell\v1.0`</span><span class="sxs-lookup"><span data-stu-id="f8236-142">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`</span></span>
- <span data-ttu-id="f8236-143">PowerShell Core 6.x：`$env:ProgramFiles\PowerShell\6`</span><span class="sxs-lookup"><span data-stu-id="f8236-143">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`</span></span>
- <span data-ttu-id="f8236-144">PowerShell 7：`$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="f8236-144">PowerShell 7: `$env:ProgramFiles\PowerShell\7`</span></span>

<span data-ttu-id="f8236-145">新位置会添加到 PATH 中，这样就能同时运行 Windows PowerShell 5.1 和 PowerShell 7 了。</span><span class="sxs-lookup"><span data-stu-id="f8236-145">The new location is added to your PATH allowing you to run both Windows PowerShell 5.1 and PowerShell 7.</span></span> <span data-ttu-id="f8236-146">若要从 PowerShell Core 6.x 迁移到 PowerShell 7，则会删除 PowerShell 6，并替换 PATH。</span><span class="sxs-lookup"><span data-stu-id="f8236-146">If you're migrating from PowerShell Core 6.x to PowerShell 7, PowerShell 6 is removed and the PATH replaced.</span></span>

<span data-ttu-id="f8236-147">在 Windows PowerShell 中，PowerShell 可执行文件名为 `powershell.exe`。</span><span class="sxs-lookup"><span data-stu-id="f8236-147">In Windows PowerShell, the PowerShell executable is named `powershell.exe`.</span></span> <span data-ttu-id="f8236-148">在版本 6 及更高版本中，可执行文件名为 `pwsh.exe`。</span><span class="sxs-lookup"><span data-stu-id="f8236-148">In version 6 and above, the executable is named `pwsh.exe`.</span></span> <span data-ttu-id="f8236-149">使用新名称，可以轻松支持两个版本的并行执行。</span><span class="sxs-lookup"><span data-stu-id="f8236-149">The new name makes it easy to support side-by-side execution of both versions.</span></span>

### <a name="separate-psmodulepath"></a><span data-ttu-id="f8236-150">独立的 PSModulePath</span><span class="sxs-lookup"><span data-stu-id="f8236-150">Separate PSModulePath</span></span>

<span data-ttu-id="f8236-151">默认情况下，Windows PowerShell 和 PowerShell 7 将模块存储在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="f8236-151">By default, Windows PowerShell and PowerShell 7 store modules in different locations.</span></span> <span data-ttu-id="f8236-152">PowerShell 7 将这些位置合并到 `$Env:PSModulePath` 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="f8236-152">PowerShell 7 combines those locations in the `$Env:PSModulePath` environment variable.</span></span> <span data-ttu-id="f8236-153">当按名称导入模块时，PowerShell 检查由 `$Env:PSModulePath` 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="f8236-153">When importing a module by name, PowerShell checks the location specified by `$Env:PSModulePath`.</span></span> <span data-ttu-id="f8236-154">这样，PowerShell 7 就可以同时加载核心模块和桌面模块了。</span><span class="sxs-lookup"><span data-stu-id="f8236-154">This allows PowerShell 7 to load both Core and Desktop modules.</span></span>

|            <span data-ttu-id="f8236-155">安装范围</span><span class="sxs-lookup"><span data-stu-id="f8236-155">Install Scope</span></span>            |                <span data-ttu-id="f8236-156">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="f8236-156">Windows PowerShell 5.1</span></span>                 |             <span data-ttu-id="f8236-157">PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="f8236-157">PowerShell 7.0</span></span>             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="f8236-158">PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="f8236-158">PowerShell modules</span></span>                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| <span data-ttu-id="f8236-159">用户已安装</span><span class="sxs-lookup"><span data-stu-id="f8236-159">User installed</span></span><br><span data-ttu-id="f8236-160">AllUsers 范围</span><span class="sxs-lookup"><span data-stu-id="f8236-160">AllUsers scope</span></span>    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| <span data-ttu-id="f8236-161">用户已安装</span><span class="sxs-lookup"><span data-stu-id="f8236-161">User installed</span></span><br><span data-ttu-id="f8236-162">CurrentUser 范围</span><span class="sxs-lookup"><span data-stu-id="f8236-162">CurrentUser scope</span></span> | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

<span data-ttu-id="f8236-163">下面的示例展示了每个版本的 `$Env:PSModulePath` 默认值。</span><span class="sxs-lookup"><span data-stu-id="f8236-163">The following examples show the default values of `$Env:PSModulePath` for each version.</span></span>

- <span data-ttu-id="f8236-164">对于 Windows PowerShell 5.1：</span><span class="sxs-lookup"><span data-stu-id="f8236-164">For Windows PowerShell 5.1:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- <span data-ttu-id="f8236-165">对于 PowerShell 7：</span><span class="sxs-lookup"><span data-stu-id="f8236-165">For PowerShell 7:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

<span data-ttu-id="f8236-166">请注意，为了提供模块自动加载功能，PowerShell 7 同时包含 Windows PowerShell 路径和 PowerShell 7 路径。</span><span class="sxs-lookup"><span data-stu-id="f8236-166">Notice that PowerShell 7 includes the Windows PowerShell paths and the PowerShell 7 paths to provide autoloading of modules.</span></span>

> [!NOTE]
> <span data-ttu-id="f8236-167">如果你更改了 PSModulePath 环境变量或安装了自定义模块或应用程序，可能还存在其他路径。</span><span class="sxs-lookup"><span data-stu-id="f8236-167">Additional paths may exist if you have changed the PSModulePath environment variable or installed custom modules or applications.</span></span>

<span data-ttu-id="f8236-168">有关详细信息，请参阅 [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences) 中的 `PSModulePath`。</span><span class="sxs-lookup"><span data-stu-id="f8236-168">For more information, see `PSModulePath` in [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).</span></span>

<span data-ttu-id="f8236-169">若要详细了解模块，请参阅 [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules)。</span><span class="sxs-lookup"><span data-stu-id="f8236-169">For more information about Modules, see [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).</span></span>

### <a name="separate-profiles"></a><span data-ttu-id="f8236-170">独立的配置文件</span><span class="sxs-lookup"><span data-stu-id="f8236-170">Separate profiles</span></span>

<span data-ttu-id="f8236-171">PowerShell 配置文件是在 PowerShell 启动时执行的脚本。</span><span class="sxs-lookup"><span data-stu-id="f8236-171">A PowerShell profile is a script that executes when PowerShell starts.</span></span> <span data-ttu-id="f8236-172">此脚本通过添加命令、别名、函数、变量、模块和 PowerShell 驱动器来自定义环境。</span><span class="sxs-lookup"><span data-stu-id="f8236-172">This script customizes your environment by adding commands, aliases, functions, variables, modules, and PowerShell drives.</span></span> <span data-ttu-id="f8236-173">配置文件脚本让这些自定义对每个会话都可用，而不必手动重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="f8236-173">The profile script makes these customizations available in every session without having to manually recreate them.</span></span>

<span data-ttu-id="f8236-174">在 PowerShell 7 中，配置文件的位置路径发生了更改。</span><span class="sxs-lookup"><span data-stu-id="f8236-174">The path to the location of the profile has changed in PowerShell 7.</span></span>

- <span data-ttu-id="f8236-175">在 Windows PowerShell 5.1 中，配置文件的位置为 `$HOME\Documents\WindowsPowerShell`。</span><span class="sxs-lookup"><span data-stu-id="f8236-175">In Windows PowerShell 5.1, the location of the profile is `$HOME\Documents\WindowsPowerShell`.</span></span>
- <span data-ttu-id="f8236-176">在 PowerShell 7 中，配置文件的位置为 `$HOME\Documents\PowerShell`。</span><span class="sxs-lookup"><span data-stu-id="f8236-176">In PowerShell 7, the location of the profile is `$HOME\Documents\PowerShell`.</span></span>

<span data-ttu-id="f8236-177">配置文件的文件名也发生了更改：</span><span class="sxs-lookup"><span data-stu-id="f8236-177">The profile filenames have also changed:</span></span>

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

<span data-ttu-id="f8236-178">有关详细信息，请参阅 [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles)。</span><span class="sxs-lookup"><span data-stu-id="f8236-178">For more information [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a><span data-ttu-id="f8236-179">PowerShell 7 与 Windows PowerShell 5.1 模块的兼容性</span><span class="sxs-lookup"><span data-stu-id="f8236-179">PowerShell 7 compatibility with Windows PowerShell 5.1 modules</span></span>

<span data-ttu-id="f8236-180">你在 Windows PowerShell 5.1 中使用的大多数模块都已与 PowerShell 7 兼容，包括 Azure PowerShell 和 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="f8236-180">Most of the modules you use in Windows PowerShell 5.1 already work with PowerShell 7, including Azure PowerShell and Active Directory.</span></span> <span data-ttu-id="f8236-181">我们将继续与其他团队合作，共同添加对包括 Microsoft Graph、Office 365 在内的更多模块的本机 PowerShell 7 支持。</span><span class="sxs-lookup"><span data-stu-id="f8236-181">We're continuing to work with other teams to add native PowerShell 7 support for more modules including Microsoft Graph, Office 365, and others.</span></span> <span data-ttu-id="f8236-182">有关受支持模块的当前列表，请参阅 [PowerShell 7 模块兼容性](/powershell/scripting/whats-new/module-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="f8236-182">For the current list of supported modules, see [PowerShell 7 module compatibility](/powershell/scripting/whats-new/module-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="f8236-183">在 Windows 上，我们还向 `Import-Module` 添加了 UseWindowsPowerShell 开关，为使用不兼容模块的用户简化转换到 PowerShell 7 的过程。</span><span class="sxs-lookup"><span data-stu-id="f8236-183">On Windows, we've also added a **UseWindowsPowerShell** switch to `Import-Module` to ease the transition to PowerShell 7 for those using incompatible modules.</span></span> <span data-ttu-id="f8236-184">若要详细了解此功能，请参阅 [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility)。</span><span class="sxs-lookup"><span data-stu-id="f8236-184">For more information on this functionality, see [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).</span></span>

### <a name="powershell-remoting"></a><span data-ttu-id="f8236-185">PowerShell 远程处理</span><span class="sxs-lookup"><span data-stu-id="f8236-185">PowerShell Remoting</span></span>

<span data-ttu-id="f8236-186">使用 PowerShell 远程处理，可以在一台或多台远程计算机上运行任何 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="f8236-186">PowerShell remoting lets you run any PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="f8236-187">你可以建立持久连接、启动交互会话并在远程计算机上运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f8236-187">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

#### <a name="ws-management-remoting"></a><span data-ttu-id="f8236-188">WS-Management 远程处理</span><span class="sxs-lookup"><span data-stu-id="f8236-188">WS-Management remoting</span></span>

<span data-ttu-id="f8236-189">Windows PowerShell 5.1 及更低版本使用 WS-Management (WSMAN) 协议进行连接协商和数据传输。</span><span class="sxs-lookup"><span data-stu-id="f8236-189">Windows PowerShell 5.1 and below use the WS-Management (WSMAN) protocol for connection negotiation and data transport.</span></span> <span data-ttu-id="f8236-190">Windows 远程管理 (WinRM) 使用 WSMAN 协议。</span><span class="sxs-lookup"><span data-stu-id="f8236-190">Windows Remote Management (WinRM) uses the WSMAN protocol.</span></span> <span data-ttu-id="f8236-191">如果 WinRM 已启用，PowerShell 7 使用现有 Windows PowerShell 5.1 终结点 `Microsoft.PowerShell` 进行远程连接。</span><span class="sxs-lookup"><span data-stu-id="f8236-191">If WinRM has been enabled, PowerShell 7 uses the existing Windows PowerShell 5.1 endpoint named `Microsoft.PowerShell` for remoting connections.</span></span> <span data-ttu-id="f8236-192">若要将 PowerShell 7 更新为包含自己的终结点，请运行 `Enable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8236-192">To update PowerShell 7 to include its own endpoint, run the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="f8236-193">若要了解如何连接到特定终结点，请参阅 [PowerShell Core 中的 WS-Management 远程处理](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)</span><span class="sxs-lookup"><span data-stu-id="f8236-193">For information about connecting to specific endpoints, see [WS-Management Remoting in PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)</span></span>

<span data-ttu-id="f8236-194">若要使用 Windows PowerShell 远程处理，必须配置远程计算机以进行远程管理。</span><span class="sxs-lookup"><span data-stu-id="f8236-194">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="f8236-195">有关详细信息（包括说明），请参阅[关于远程要求](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)。</span><span class="sxs-lookup"><span data-stu-id="f8236-195">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="f8236-196">若要详细了解如何使用远程处理，请参阅[关于远程](/powershell/module/microsoft.powershell.core/about/about_remote)</span><span class="sxs-lookup"><span data-stu-id="f8236-196">For more information about working with remoting, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote)</span></span>

#### <a name="ssh-based-remoting"></a><span data-ttu-id="f8236-197">基于 SSH 的远程处理</span><span class="sxs-lookup"><span data-stu-id="f8236-197">SSH-based remoting</span></span>

<span data-ttu-id="f8236-198">基于 SSH 的远程处理是在 PowerShell Core 6.x 中引入，以支持其他无法使用 Windows 本机组件（如 WinRM）的操作系统。</span><span class="sxs-lookup"><span data-stu-id="f8236-198">SSH-based remoting was added in PowerShell Core 6.x to support other operating systems that can't use Windows native components like **WinRM**.</span></span> <span data-ttu-id="f8236-199">SSH 远程处理在目标计算机上创建一个 PowerShell 托管进程作为 SSH 子系统。</span><span class="sxs-lookup"><span data-stu-id="f8236-199">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="f8236-200">有关在 Windows 或 Linux 上设置基于 SSH 的远程处理的详细信息和示例，请参阅：[通过 SSH 进行 PowerShell 远程处理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)。</span><span class="sxs-lookup"><span data-stu-id="f8236-200">For details and examples on setting up SSH-based remoting on Windows or Linux, see: [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="f8236-201">PowerShell 库 (PSGallery) 包含自动配置基于 SSH 的远程处理的模块和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8236-201">The PowerShell Gallery (PSGallery) contains a module and cmdlet that automatically configures SSH-based remoting.</span></span> <span data-ttu-id="f8236-202">安装 [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) 中的 `Microsoft.PowerShell.RemotingTools` 模块，然后运行 `Enable-SSH` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8236-202">Install the `Microsoft.PowerShell.RemotingTools` module from the [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) and run the `Enable-SSH` cmdlet.</span></span>

<span data-ttu-id="f8236-203">`New-PSSession`、`Enter-PSSession` 和 `Invoke-Command` cmdlet 有支持 SSH 连接的新参数集。</span><span class="sxs-lookup"><span data-stu-id="f8236-203">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets have new parameter sets to support SSH connections.</span></span>

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="f8236-204">若要创建远程会话，请使用 HostName 参数指定目标计算机，并通过 UserName 提供用户名。</span><span class="sxs-lookup"><span data-stu-id="f8236-204">To create a remote session, specify the target computer with the **HostName** parameter and provide the user name with **UserName**.</span></span> <span data-ttu-id="f8236-205">当以交互方式运行 cmdlet 时，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="f8236-205">When running the cmdlets interactively, you're prompted for a password.</span></span>

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

<span data-ttu-id="f8236-206">或者，在使用 HostName 参数时，提供用户名信息，后跟 at 符号 (`@`) 和计算机名。</span><span class="sxs-lookup"><span data-stu-id="f8236-206">Alternatively, when using the **HostName** parameter, provide the username information followed by the at sign (`@`), followed by the computer name.</span></span>

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

<span data-ttu-id="f8236-207">还可以使用包含 KeyFilePath 参数的私钥文件来设置 SSH 密钥身份验证。</span><span class="sxs-lookup"><span data-stu-id="f8236-207">You may set up SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span>
<span data-ttu-id="f8236-208">有关详细信息，请参阅 [OpenSSH 密钥管理](/windows-server/administration/openssh/openssh_keymanagement)。</span><span class="sxs-lookup"><span data-stu-id="f8236-208">For more information, see [OpenSSH Key Management](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

### <a name="group-policy-supported"></a><span data-ttu-id="f8236-209">已支持组策略</span><span class="sxs-lookup"><span data-stu-id="f8236-209">Group Policy supported</span></span>

<span data-ttu-id="f8236-210">PowerShell 包含组策略设置，有助于为企业环境中的服务器定义一致的选项值。</span><span class="sxs-lookup"><span data-stu-id="f8236-210">PowerShell includes Group Policy settings to help you define consistent option values for servers in an enterprise environment.</span></span> <span data-ttu-id="f8236-211">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="f8236-211">These settings include:</span></span>

- <span data-ttu-id="f8236-212">控制台会话配置：设置运行 PowerShell 的配置终结点。</span><span class="sxs-lookup"><span data-stu-id="f8236-212">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="f8236-213">启用模块日志记录：设置模块的 LogPipelineExecutionDetails 属性。</span><span class="sxs-lookup"><span data-stu-id="f8236-213">Turn on Module Logging: Sets the LogPipelineExecutionDetails property of modules.</span></span>
- <span data-ttu-id="f8236-214">启用 Power Shell 脚本块日志记录：启用所有 PowerShell 脚本的详细日志记录。</span><span class="sxs-lookup"><span data-stu-id="f8236-214">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="f8236-215">启用脚本执行：设置 PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="f8236-215">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="f8236-216">启用 PowerShell 脚本：可便于将 PowerShell 命令输入和输出捕获到基于文本的脚本中。</span><span class="sxs-lookup"><span data-stu-id="f8236-216">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="f8236-217">设置 Update-Help 的默认源路径：将“可更新的帮助”的源设置为目录，而不是 Internet。</span><span class="sxs-lookup"><span data-stu-id="f8236-217">Set the default source path for Update-Help: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="f8236-218">有关详细信息，请参阅 [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings)。</span><span class="sxs-lookup"><span data-stu-id="f8236-218">For more information, see [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).</span></span>

<span data-ttu-id="f8236-219">PowerShell 7 在 `$PSHOME` 中添加组策略模板和安装脚本。</span><span class="sxs-lookup"><span data-stu-id="f8236-219">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="f8236-220">组策略工具使用管理模板文件（`.admx`、`.adml`），以在用户界面中填充策略设置。</span><span class="sxs-lookup"><span data-stu-id="f8236-220">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="f8236-221">这样，管理员就能管理基于注册表的策略设置。</span><span class="sxs-lookup"><span data-stu-id="f8236-221">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="f8236-222">`InstallPSCorePolicyDefinitions.ps1` 脚本在本地计算机上安装 PowerShell Core 管理模板。</span><span class="sxs-lookup"><span data-stu-id="f8236-222">The `InstallPSCorePolicyDefinitions.ps1` script installs PowerShell Core Administrative Templates on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a><span data-ttu-id="f8236-223">独立的事件日志</span><span class="sxs-lookup"><span data-stu-id="f8236-223">Separate Event Logs</span></span>

<span data-ttu-id="f8236-224">Windows PowerShell 和 PowerShell 7 记录事件来分隔事件日志。</span><span class="sxs-lookup"><span data-stu-id="f8236-224">Windows PowerShell and PowerShell 7 log events to separate event logs.</span></span> <span data-ttu-id="f8236-225">若要获取 PowerShell 日志列表，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f8236-225">Use the following command to get a list of the PowerShell logs.</span></span>

```powershell
Get-WinEvent -ListLog *PowerShell*
```

<span data-ttu-id="f8236-226">有关详细信息，请参阅 [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows)。</span><span class="sxs-lookup"><span data-stu-id="f8236-226">For more information, see [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).</span></span>

## <a name="improved-editing-experience-with-visual-studio-code"></a><span data-ttu-id="f8236-227">提升了使用 Visual Studio Code 的编辑体验</span><span class="sxs-lookup"><span data-stu-id="f8236-227">Improved editing experience with Visual Studio Code</span></span>

<span data-ttu-id="f8236-228">包含 [PowerShell 扩展](https://code.visualstudio.com/docs/languages/powershell)的 [Visual Studio Code (VSCode)](https://code.visualstudio.com/) 是 PowerShell 7 支持的脚本环境。</span><span class="sxs-lookup"><span data-stu-id="f8236-228">[Visual Studio Code (VSCode)](https://code.visualstudio.com/) with the [PowerShell Extension](https://code.visualstudio.com/docs/languages/powershell) is the supported scripting environment for PowerShell 7.</span></span> <span data-ttu-id="f8236-229">Windows PowerShell 集成脚本环境 (ISE) 只支持 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f8236-229">The Windows PowerShell Integrated Scripting Environment (ISE) only supports Windows PowerShell.</span></span>

<span data-ttu-id="f8236-230">更新后的 PowerShell 扩展包括：</span><span class="sxs-lookup"><span data-stu-id="f8236-230">The updated PowerShell extension includes:</span></span>

- <span data-ttu-id="f8236-231">新增了 ISE 兼容性模式</span><span class="sxs-lookup"><span data-stu-id="f8236-231">New ISE compatibility mode</span></span>
- <span data-ttu-id="f8236-232">集成控制台中的 PSReadLine，包括语法突出显示、多行编辑和退回搜索</span><span class="sxs-lookup"><span data-stu-id="f8236-232">PSReadLine in the Integrated Console, including syntax highlighting, multi-line editing, and back search</span></span>
- <span data-ttu-id="f8236-233">提升了稳定性和性能</span><span class="sxs-lookup"><span data-stu-id="f8236-233">Stability and performance improvements</span></span>
- <span data-ttu-id="f8236-234">新增了 CodeLens 集成</span><span class="sxs-lookup"><span data-stu-id="f8236-234">New CodeLens integration</span></span>
- <span data-ttu-id="f8236-235">提升了路径自动完成</span><span class="sxs-lookup"><span data-stu-id="f8236-235">Improved path auto-completion</span></span>

<span data-ttu-id="f8236-236">若要更轻松地转换到 Visual Studio Code，请使用“命令面板”中的“启用 ISE 模式”功能。</span><span class="sxs-lookup"><span data-stu-id="f8236-236">To make the transition to Visual Studio Code easier, use the **Enable ISE Mode** function available in the **Command Palette**.</span></span> <span data-ttu-id="f8236-237">此功能将 VSCode 切换为 ISE 样式布局。</span><span class="sxs-lookup"><span data-stu-id="f8236-237">This function switches VSCode into an ISE-style layout.</span></span> <span data-ttu-id="f8236-238">借助 ISE 样式布局，可以通过熟悉的用户体验来使用 PowerShell 的所有新特性和功能。</span><span class="sxs-lookup"><span data-stu-id="f8236-238">The ISE-style layout gives you all the new features and capabilities of PowerShell in a familiar user experience.</span></span>

<span data-ttu-id="f8236-239">若要切换到新 ISE 布局，请按 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> 打开“命令面板”，键入“`PowerShell`”，然后选中“PowerShell:启用 ISE 模式”。</span><span class="sxs-lookup"><span data-stu-id="f8236-239">To switch to the new ISE layout, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the **Command Palette**, type `PowerShell` and select **PowerShell: Enable ISE Mode**.</span></span>

<span data-ttu-id="f8236-240">若要将布局设置为原始布局，请打开“命令面板”，然后选中“PowerShell:禁用 ISE 模式(还原为默认值)”。</span><span class="sxs-lookup"><span data-stu-id="f8236-240">To set the layout to the original layout, open the **Command Palette**, select **PowerShell: Disable ISE Mode (restore to defaults)**.</span></span>

<span data-ttu-id="f8236-241">若要详细了解如何将 VSCode 布局自定义为 ISE，请参阅[如何在 Visual Studio Code 中复制 ISE 体验](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)</span><span class="sxs-lookup"><span data-stu-id="f8236-241">For details about customizing the VSCode layout to ISE, see [How to Replicate the ISE Experience in Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)</span></span>

> [!NOTE]
> <span data-ttu-id="f8236-242">目前还没有使用新功能来更新 ISE 的计划。</span><span class="sxs-lookup"><span data-stu-id="f8236-242">There no plans to update the ISE with new features.</span></span> <span data-ttu-id="f8236-243">ISE 现在是最新版 Windows 10 和 Windows Server 中的用户不可卸载功能。</span><span class="sxs-lookup"><span data-stu-id="f8236-243">The ISE is now a user-uninstallable feature in the latest versions of Windows 10 and Windows Server.</span></span> <span data-ttu-id="f8236-244">目前还没有永久删除 ISE 的计划。</span><span class="sxs-lookup"><span data-stu-id="f8236-244">There are no plans to permanently remove the ISE.</span></span> <span data-ttu-id="f8236-245">PowerShell 团队及其合作伙伴专注于改进用于 Visual Studio Code 的 PowerShell 扩展中的脚本体验。</span><span class="sxs-lookup"><span data-stu-id="f8236-245">The PowerShell Team and its partners are focused on improving the scripting experience in the PowerShell extension for Visual Studio Code.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8236-246">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f8236-246">Next Steps</span></span>

<span data-ttu-id="f8236-247">掌握了有效迁移的知识，现在就[安装 PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) 吧！</span><span class="sxs-lookup"><span data-stu-id="f8236-247">Armed with the knowledge to effectively migrate, [install PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) now!</span></span>
