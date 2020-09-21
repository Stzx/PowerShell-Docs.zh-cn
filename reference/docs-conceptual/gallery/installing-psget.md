---
ms.date: 09/19/2019
contributor: manikb
keywords: 库,powershell,cmdlet,psget
title: 安装 PowerShellGet
ms.openlocfilehash: 4a10699be9ff2b64e5848c6749bdd3dedf55e3c7
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162505"
---
# <a name="installing-powershellget"></a><span data-ttu-id="7c81c-103">安装 PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="7c81c-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="7c81c-104">PowerShellGet 是以下版本的随机模块</span><span class="sxs-lookup"><span data-stu-id="7c81c-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="7c81c-105">[Windows 10](https://www.microsoft.com/windows) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7c81c-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="7c81c-106">[Windows Server 2016](/windows-server/windows-server) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7c81c-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="7c81c-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7c81c-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="7c81c-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="7c81c-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="7c81c-109">从 PowerShell 库获取最新版本</span><span class="sxs-lookup"><span data-stu-id="7c81c-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="7c81c-110">更新 PowerShellGet 前，应始终安装最新的 NuGet 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c81c-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="7c81c-111">在提升的 PowerShell 会话中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="7c81c-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="7c81c-112">对于使用 PowerShell 5.0（或更高版本）的系统，可以安装最新的 PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="7c81c-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="7c81c-113">若要在 Windows 10、Windows Server 2016、任何安装了 WMF 5.0 或 5.1 的系统或任何安装了 PowerShell 6 的系统上安装 PowerShellGet，请通过提升的 PowerShell 会话运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="7c81c-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
```

<span data-ttu-id="7c81c-114">使用 `Update-Module` 获取更高版本。</span><span class="sxs-lookup"><span data-stu-id="7c81c-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="7c81c-115">对于运行 PowerShell 3.0 或 PowerShell 4.0 的计算机</span><span class="sxs-lookup"><span data-stu-id="7c81c-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="7c81c-116">这些说明适用于已安装 **PackageManagement 预览版**或未安装任何版本的 **PowerShellGet** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="7c81c-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="7c81c-117">两组指令都使用 `Save-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7c81c-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="7c81c-118">`Save-Module` 从已注册的存储库下载并保存模块和所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="7c81c-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="7c81c-119">模块的最新版本已保存到本地计算机上的指定路径，但尚未安装。</span><span class="sxs-lookup"><span data-stu-id="7c81c-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="7c81c-120">要在 PowerShell 3.0 或 4.0 中安装模块，请将已保存模块的文件夹复制到 `$env:ProgramFiles\WindowsPowerShell\Modules`。</span><span class="sxs-lookup"><span data-stu-id="7c81c-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="7c81c-121">有关详细信息，请参阅 [Save-Module](/powershell/module/PowershellGet/Save-Module)。</span><span class="sxs-lookup"><span data-stu-id="7c81c-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="7c81c-122">PowerShell 3.0 和 PowerShell 4.0 仅支持一种模块版本。</span><span class="sxs-lookup"><span data-stu-id="7c81c-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="7c81c-123">从 PowerShell 5.0 开始，模块安装在 `<modulename>\<version>` 中。</span><span class="sxs-lookup"><span data-stu-id="7c81c-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="7c81c-124">这使你能够并行安装多个版本。</span><span class="sxs-lookup"><span data-stu-id="7c81c-124">This allows you to install multiple versions side-by-side.</span></span> <span data-ttu-id="7c81c-125">使用 `Save-Module` 下载模块后，必须将 `<modulename>\<version>` 中的文件复制到目标计算机上的 `<modulename>` 文件夹中，如以下说明所示。</span><span class="sxs-lookup"><span data-stu-id="7c81c-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine, as shown in the instructions below.</span></span>

#### <a name="preparatory-step-on-computers-running-powershell-30"></a><span data-ttu-id="7c81c-126">运行 PowerShell 3.0 的计算机上的准备步骤</span><span class="sxs-lookup"><span data-stu-id="7c81c-126">Preparatory Step on computers running PowerShell 3.0</span></span>

<span data-ttu-id="7c81c-127">以下各节将介绍如何在目录 `$env:ProgramFiles\WindowsPowerShell\Modules` 中安装模块。</span><span class="sxs-lookup"><span data-stu-id="7c81c-127">The instructions in the sections below install the modules in directory `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>
<span data-ttu-id="7c81c-128">在 PowerShell 3.0 中，默认情况下此目录未在 `$env:PSModulePath` 中列出，因此你需要添加它，才能自动加载模块。</span><span class="sxs-lookup"><span data-stu-id="7c81c-128">In PowerShell 3.0, this directory isn't listed in `$env:PSModulePath` by default, so you'll need to add it in order for the modules to be auto-loaded.</span></span> 

<span data-ttu-id="7c81c-129">打开提升的 PowerShell 会话并运行以下命令（在未来的会话中将生效）：</span><span class="sxs-lookup"><span data-stu-id="7c81c-129">Open an elevated PowerShell session and run the following command (which will take effect in future sessions):</span></span>

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="7c81c-130">安装了 PackageManagement 预览版的计算机</span><span class="sxs-lookup"><span data-stu-id="7c81c-130">Computers with the PackageManagement Preview installed</span></span>

> [!NOTE] 
> <span data-ttu-id="7c81c-131">PackageManagement 预览版是一个可下载的组件，可使 PowerShellGet 用于 PowerShell 版本 3 和 4，但现在不再可用。</span><span class="sxs-lookup"><span data-stu-id="7c81c-131">PackageManagement Preview was a downloadable component that made PowerShellGet available to PowerShell versions 3 and 4, but it is no longer available.</span></span>
> <span data-ttu-id="7c81c-132">若要测试是否已在指定计算机上安装该组件，请运行 `Get-Module -ListAvailable PowerShellGet`。</span><span class="sxs-lookup"><span data-stu-id="7c81c-132">To test if it was installed on a given computer, run `Get-Module -ListAvailable PowerShellGet`.</span></span>

1. <span data-ttu-id="7c81c-133">从 PowerShell 会话中，使用 `Save-Module` 下载当前版本的 PowerShellGet。</span><span class="sxs-lookup"><span data-stu-id="7c81c-133">From a PowerShell session, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="7c81c-134">已下载两个文件夹：**PowerShellGet** 和 **PackageManagement**。</span><span class="sxs-lookup"><span data-stu-id="7c81c-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="7c81c-135">每个文件夹包含一个带有版本号的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="7c81c-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="7c81c-136">确保未在其他任何进程中加载 PowerShellGet 和 PackageManagement 模块 。</span><span class="sxs-lookup"><span data-stu-id="7c81c-136">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>

1. <span data-ttu-id="7c81c-137">使用提升的权限重新打开 PowerShell 控制台，并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="7c81c-137">Reopen the PowerShell console with elevated permissions and run the following command.</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % { 
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="7c81c-138">没有 PowerShellGet 的计算机</span><span class="sxs-lookup"><span data-stu-id="7c81c-138">Computers without PowerShellGet</span></span>

<span data-ttu-id="7c81c-139">对于未安装任何版本的 PowerShellGet 的计算机（使用 `Get-Module -ListAvailable PowerShellGet` 测试），需要使用安装了 PowerShellGet 的计算机来下载模块 。</span><span class="sxs-lookup"><span data-stu-id="7c81c-139">For computers without any version of **PowerShellGet** installed (test with `Get-Module -ListAvailable PowerShellGet`), a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="7c81c-140">在安装了 **PowerShellGet** 的计算机上，使用 `Save-Module` 下载 **PowerShellGet** 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="7c81c-140">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="7c81c-141">已下载两个文件夹：**PowerShellGet** 和 **PackageManagement**。</span><span class="sxs-lookup"><span data-stu-id="7c81c-141">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="7c81c-142">每个文件夹包含一个带有版本号的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="7c81c-142">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="7c81c-143">将 PowerShellGet 和 PackageManagement 文件夹中相应的 `<version>` 子文件夹分别复制到未安装 PowerShellGet 的计算机的 `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` 和 `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` 文件夹中，这需要提升的会话  。</span><span class="sxs-lookup"><span data-stu-id="7c81c-143">Copy the respective `<version>` subfolder in the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed, into folders `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` respectively, which requires an elevated session.</span></span>
   
1. <span data-ttu-id="7c81c-144">例如，如果你可以访问其他计算机上的下载文件夹（如 `ws1`），请通过 UNC 路径（如 `\\ws1\C$\LocalFolder`）从目标计算机打开具有提升权限的 PowerShell 控制台并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7c81c-144">For instance, if you can access the download folder on the other computer, say `ws1`, from the target computer via a UNC path, say `\\ws1\C$\LocalFolder`, open a PowerShell console with elevated permissions and run the following command:</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
