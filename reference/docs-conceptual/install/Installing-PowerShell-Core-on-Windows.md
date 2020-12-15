---
title: 在 Windows 上安装 PowerShell
description: 介绍如何在 Windows 上安装 PowerShell
ms.date: 11/11/2020
ms.openlocfilehash: 039db904a315bd3ad3f4e1358d414c98c3a84be5
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661420"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="97a78-103">在 Windows 上安装 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97a78-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="97a78-104">有多种方法可以在 Windows 中安装 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97a78-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97a78-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="97a78-105">Prerequisites</span></span>

<span data-ttu-id="97a78-106">Windows 7 SP1、Server 2008 R2 及更高版本支持最新版 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97a78-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="97a78-107">若要通过 WSMan 启用 PowerShell 远程处理，需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="97a78-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="97a78-108">在低于 Windows 10 的 Windows 版本上安装[通用 C 运行时](https://www.microsoft.com/download/details.aspx?id=50410)。</span><span class="sxs-lookup"><span data-stu-id="97a78-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="97a78-109">可以通过直接下载或 Windows 更新来获取它。</span><span class="sxs-lookup"><span data-stu-id="97a78-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="97a78-110">完全修补的系统已安装此包。</span><span class="sxs-lookup"><span data-stu-id="97a78-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="97a78-111">在 Windows 7 和 Windows Server 2008 R2 上安装 Windows Management Framework (WMF) 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="97a78-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="97a78-112">有关 WMF 的详细信息，请参阅 [WMF 概述](/powershell/scripting/wmf/overview)。</span><span class="sxs-lookup"><span data-stu-id="97a78-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="97a78-113">下载安装程序包</span><span class="sxs-lookup"><span data-stu-id="97a78-113">Download the installer package</span></span>

<span data-ttu-id="97a78-114">若要在 Windows 上安装 PowerShell，请从 GitHub 下载[最新][]安装包。</span><span class="sxs-lookup"><span data-stu-id="97a78-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="97a78-115">你也可以在[版本][]页上找到最新的预览版。</span><span class="sxs-lookup"><span data-stu-id="97a78-115">You can also find the latest preview version on the [releases][] page.</span></span> <span data-ttu-id="97a78-116">向下滚动到“版本”页的“资产”  部分。</span><span class="sxs-lookup"><span data-stu-id="97a78-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="97a78-117">由于“资产”  部分可能处于折叠状态，因此可能需要单击展开它。</span><span class="sxs-lookup"><span data-stu-id="97a78-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="97a78-118"><a id="msi" />安装 MSI 包</span><span class="sxs-lookup"><span data-stu-id="97a78-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="97a78-119">MSI 文件如下所示：`PowerShell-<version>-win-<os-arch>.msi`。</span><span class="sxs-lookup"><span data-stu-id="97a78-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="97a78-120">例如：</span><span class="sxs-lookup"><span data-stu-id="97a78-120">For example:</span></span>

- `PowerShell-7.1.0-win-x64.msi`
- `PowerShell-7.1.0-win-x86.msi`

<span data-ttu-id="97a78-121">下载后，双击安装程序并按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="97a78-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="97a78-122">安装程序在 Windows“开始”菜单中创建一个快捷方式。</span><span class="sxs-lookup"><span data-stu-id="97a78-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="97a78-123">默认情况下，包安装位置为 `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="97a78-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="97a78-124">可以通过“开始”菜单或 `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` 启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97a78-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="97a78-125">PowerShell 7.1 安装到新目录，并与 Windows PowerShell 5.1 并行运行。</span><span class="sxs-lookup"><span data-stu-id="97a78-125">PowerShell 7.1 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span>
> <span data-ttu-id="97a78-126">PowerShell 7.1 是就地升级，升级后会替换 PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="97a78-126">PowerShell 7.1 is an in-place upgrade that replaces PowerShell 6.x.</span></span> <span data-ttu-id="97a78-127">或 PowerShell 7.0。</span><span class="sxs-lookup"><span data-stu-id="97a78-127">or PowerShell 7.0.</span></span>
>
> - <span data-ttu-id="97a78-128">PowerShell 7.1 安装到 `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="97a78-128">PowerShell 7.1 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="97a78-129">`$env:ProgramFiles\PowerShell\7` 文件夹已添加到 `$env:PATH`</span><span class="sxs-lookup"><span data-stu-id="97a78-129">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="97a78-130">`$env:ProgramFiles\PowerShell\6` 文件夹已删除</span><span class="sxs-lookup"><span data-stu-id="97a78-130">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="97a78-131">如果需要与其他版本并行运行 PowerShell 7.1，请使用 [ZIP 安装](#zip)方法将其他版本安装到其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="97a78-131">If you need to run PowerShell 7.1 side-by-side with other versions, use the [ZIP install](#zip) method to install the other version to a different folder.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="97a78-132">通过命令行进行管理安装</span><span class="sxs-lookup"><span data-stu-id="97a78-132">Administrative install from the command line</span></span>

<span data-ttu-id="97a78-133">可以通过命令行安装 MSI 包，这样管理员能够在没有用户交互的情况下部署包。</span><span class="sxs-lookup"><span data-stu-id="97a78-133">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="97a78-134">MSI 包中有下列控制安装选项的属性：</span><span class="sxs-lookup"><span data-stu-id="97a78-134">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="97a78-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - 此属性控制向 Windows 资源管理器中的上下文菜单添加“打开 PowerShell”  项的选项。</span><span class="sxs-lookup"><span data-stu-id="97a78-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="97a78-136">**ENABLE_PSREMOTING** - 此属性控制用于在安装过程中启用 PowerShell 远程处理的选项。</span><span class="sxs-lookup"><span data-stu-id="97a78-136">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="97a78-137">**REGISTER_MANIFEST** - 此属性控制用于注册 Windows 事件日志记录清单的选项。</span><span class="sxs-lookup"><span data-stu-id="97a78-137">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="97a78-138">下面的示例展示了如何在启用所有安装选项的情况下无提示安装 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97a78-138">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.1.0-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="97a78-139">有关 `Msiexec.exe` 命令行选项的完整列表，请参阅[命令行选项](/windows/desktop/Msi/command-line-options)。</span><span class="sxs-lookup"><span data-stu-id="97a78-139">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="97a78-140">在安装过程中创建注册表项</span><span class="sxs-lookup"><span data-stu-id="97a78-140">Registry keys created during installation</span></span>

<span data-ttu-id="97a78-141">从 PowerShell 7.1 开始，MSI 包将创建用于存储 PowerShell 安装位置和版本的注册表项。</span><span class="sxs-lookup"><span data-stu-id="97a78-141">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="97a78-142">这些值位于 `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>` 中。</span><span class="sxs-lookup"><span data-stu-id="97a78-142">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="97a78-143">每种内部版本类型（发行版或预览版）、主要版本和体系结构的 `<GUID>` 的值都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="97a78-143">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="97a78-144">发布</span><span class="sxs-lookup"><span data-stu-id="97a78-144">Release</span></span>    | <span data-ttu-id="97a78-145">体系结构</span><span class="sxs-lookup"><span data-stu-id="97a78-145">Architecture</span></span> |                                          <span data-ttu-id="97a78-146">注册表项</span><span class="sxs-lookup"><span data-stu-id="97a78-146">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="97a78-147">7.1.x 版本</span><span class="sxs-lookup"><span data-stu-id="97a78-147">7.1.x Release</span></span> |     <span data-ttu-id="97a78-148">x86</span><span class="sxs-lookup"><span data-stu-id="97a78-148">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="97a78-149">7.1.x 版本</span><span class="sxs-lookup"><span data-stu-id="97a78-149">7.1.x Release</span></span> |     <span data-ttu-id="97a78-150">X64</span><span class="sxs-lookup"><span data-stu-id="97a78-150">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="97a78-151">7.1.x 预览版</span><span class="sxs-lookup"><span data-stu-id="97a78-151">7.1.x Preview</span></span> |     <span data-ttu-id="97a78-152">x86</span><span class="sxs-lookup"><span data-stu-id="97a78-152">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="97a78-153">7.1.x 预览版</span><span class="sxs-lookup"><span data-stu-id="97a78-153">7.1.x Preview</span></span> |     <span data-ttu-id="97a78-154">X64</span><span class="sxs-lookup"><span data-stu-id="97a78-154">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="97a78-155">管理员和开发人员可以使用此值查找 PowerShell 的路径。</span><span class="sxs-lookup"><span data-stu-id="97a78-155">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="97a78-156">所有预览版本和次要版本的 `<GUID>` 值都是相同的。</span><span class="sxs-lookup"><span data-stu-id="97a78-156">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="97a78-157">每个主要版本的 `<GUID>` 值都有所变化。</span><span class="sxs-lookup"><span data-stu-id="97a78-157">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="97a78-158"><a id="zip" />安装 ZIP 包</span><span class="sxs-lookup"><span data-stu-id="97a78-158"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="97a78-159">提供有 PowerShell 二进制 ZIP 存档，从而支持高级部署方案。</span><span class="sxs-lookup"><span data-stu-id="97a78-159">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="97a78-160">从[版本][版本]页下载以下 ZIP 存档之一。</span><span class="sxs-lookup"><span data-stu-id="97a78-160">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="97a78-161">PowerShell-7.1.0-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="97a78-161">PowerShell-7.1.0-win-x64.zip</span></span>
- <span data-ttu-id="97a78-162">PowerShell-7.1.0-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="97a78-162">PowerShell-7.1.0-win-x86.zip</span></span>
- <span data-ttu-id="97a78-163">PowerShell-7.1.0-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="97a78-163">PowerShell-7.1.0-win-arm64.zip</span></span>
- <span data-ttu-id="97a78-164">PowerShell-7.1.0-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="97a78-164">PowerShell-7.1.0-win-arm32.zip</span></span>

<span data-ttu-id="97a78-165">根据该文件的下载方式，你可能需要使用 `Unblock-File` cmdlet 解锁。</span><span class="sxs-lookup"><span data-stu-id="97a78-165">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="97a78-166">将内容解压到你选择的位置，然后从该位置运行 `pwsh.exe`。</span><span class="sxs-lookup"><span data-stu-id="97a78-166">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="97a78-167">与安装 MSI 包不一样，安装 ZIP 存档不会检查先决条件。</span><span class="sxs-lookup"><span data-stu-id="97a78-167">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="97a78-168">为了让使用 WSMan 的远程处理能够正常运行，请确保已满足[先决条件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="97a78-168">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="97a78-169">使用此方法在类似于 Microsoft Surface Pro X 的计算机上安装基于 ARM 的 PowerShell 版本。为获得最佳结果，请将 PowerShell 安装到 `$env:ProgramFiles\PowerShell\7` 文件夹。</span><span class="sxs-lookup"><span data-stu-id="97a78-169">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="97a78-170">Windows 10 IoT 企业版部署</span><span class="sxs-lookup"><span data-stu-id="97a78-170">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="97a78-171">Windows 10 IoT 企业版随附 Windows PowerShell，可用来部署 PowerShell 7。</span><span class="sxs-lookup"><span data-stu-id="97a78-171">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="97a78-172">在目标设备中创建 `PSSession`</span><span class="sxs-lookup"><span data-stu-id="97a78-172">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="97a78-173">将 ZIP 包复制到设备</span><span class="sxs-lookup"><span data-stu-id="97a78-173">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="97a78-174">连接到设备并展开存档</span><span class="sxs-lookup"><span data-stu-id="97a78-174">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="97a78-175">设置 PowerShell 7 远程处理</span><span class="sxs-lookup"><span data-stu-id="97a78-175">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="97a78-176">连接到设备上的 PowerShell 7 终结点</span><span class="sxs-lookup"><span data-stu-id="97a78-176">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="97a78-177">Windows 10 IoT 核心版部署</span><span class="sxs-lookup"><span data-stu-id="97a78-177">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="97a78-178">当你添加 IOT_POWERSHELL  功能后，Windows 10 IoT 核心版便会添加 Windows PowerShell，我们可以使用它来部署 PowerShell 7。</span><span class="sxs-lookup"><span data-stu-id="97a78-178">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="97a78-179">对于 IoT 核心版，还可以遵循为 Windows 10 IoT 企业版定义的步骤。</span><span class="sxs-lookup"><span data-stu-id="97a78-179">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="97a78-180">若要在随附映像中添加最新的 PowerShell，请使用 [Import-PSCoreRelease][] 命令在工作区域中添加包，然后将 OPENSRC_POWERSHELL 功能添加到映像中。</span><span class="sxs-lookup"><span data-stu-id="97a78-180">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="97a78-181">对于 ARM64 体系结构，在你添加 IOT_POWERSHELL 功能后，它不会添加 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97a78-181">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="97a78-182">因此，基于 zip 的安装将不起作用。</span><span class="sxs-lookup"><span data-stu-id="97a78-182">So the zip based install will not work.</span></span> <span data-ttu-id="97a78-183">需要使用 `Import-PSCoreRelease` 命令将其添加到映像中。</span><span class="sxs-lookup"><span data-stu-id="97a78-183">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="97a78-184">在 Nano Server 上进行部署</span><span class="sxs-lookup"><span data-stu-id="97a78-184">Deploying on Nano Server</span></span>

<span data-ttu-id="97a78-185">为了更好地理解这些说明，假定 Nano Server 是已运行 PowerShell 版本的“无外设”操作系统。</span><span class="sxs-lookup"><span data-stu-id="97a78-185">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="97a78-186">有关详细信息，请参阅 [Nano Server 映像生成器](/windows-server/get-started/deploy-nano-server)文档。</span><span class="sxs-lookup"><span data-stu-id="97a78-186">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="97a78-187">可以使用两种不同的方法来部署 PowerShell 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="97a78-187">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="97a78-188">脱机 - 安装 Nano Server VHD，并将 zip 文件的内容解压到安装映像中的所选位置。</span><span class="sxs-lookup"><span data-stu-id="97a78-188">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="97a78-189">联机 - 通过 PowerShell 会话传输 zip 文件，并在所需位置中将其解压。</span><span class="sxs-lookup"><span data-stu-id="97a78-189">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="97a78-190">在这两种情况下，都需要 Windows 10 x64 ZIP 版本包。</span><span class="sxs-lookup"><span data-stu-id="97a78-190">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="97a78-191">在 PowerShell 的“管理员”实例中运行命令。</span><span class="sxs-lookup"><span data-stu-id="97a78-191">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="97a78-192">PowerShell 脱机部署</span><span class="sxs-lookup"><span data-stu-id="97a78-192">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="97a78-193">使用常用 zip 实用工具将包解压到已安装的 Nano Server 映像中的目录。</span><span class="sxs-lookup"><span data-stu-id="97a78-193">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="97a78-194">卸载映像并启动。</span><span class="sxs-lookup"><span data-stu-id="97a78-194">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="97a78-195">连接到 Windows PowerShell 的内置实例。</span><span class="sxs-lookup"><span data-stu-id="97a78-195">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="97a78-196">按照说明使用[“另一种实例技术”][]创建远程处理终结点。</span><span class="sxs-lookup"><span data-stu-id="97a78-196">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="97a78-197">PowerShell 联机部署</span><span class="sxs-lookup"><span data-stu-id="97a78-197">Online Deployment of PowerShell</span></span>

<span data-ttu-id="97a78-198">若要将 PowerShell 部署到 Nano Server，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="97a78-198">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="97a78-199">连接到 Windows PowerShell 的内置实例</span><span class="sxs-lookup"><span data-stu-id="97a78-199">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="97a78-200">将文件复制到 Nano Server 实例</span><span class="sxs-lookup"><span data-stu-id="97a78-200">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="97a78-201">输入会话</span><span class="sxs-lookup"><span data-stu-id="97a78-201">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="97a78-202">提取 ZIP 文件</span><span class="sxs-lookup"><span data-stu-id="97a78-202">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="97a78-203">如果需要基于 WSMan 的远程处理，请按照说明使用[“另一种实例技术”][]创建远程处理终结点。</span><span class="sxs-lookup"><span data-stu-id="97a78-203">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="97a78-204">作为 .NET 全局工具安装</span><span class="sxs-lookup"><span data-stu-id="97a78-204">Install as a .NET Global tool</span></span>

<span data-ttu-id="97a78-205">如果你已安装 [.NET Core SDK](/dotnet/core/sdk)，则可以轻松地安装 PowerShell 作为 [.NET 全局工具](/dotnet/core/tools/global-tools)。</span><span class="sxs-lookup"><span data-stu-id="97a78-205">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="97a78-206">dotnet 工具安装程序将 `$env:USERPROFILE\dotnet\tools` 添加到 `$env:PATH` 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="97a78-206">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="97a78-207">不过，当前运行的 shell 没有更新后的 `$env:PATH`。</span><span class="sxs-lookup"><span data-stu-id="97a78-207">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="97a78-208">若要从新 shell 启动 PowerShell，可以键入“`pwsh`”。</span><span class="sxs-lookup"><span data-stu-id="97a78-208">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="97a78-209">通过 Winget 安装 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97a78-209">Install PowerShell via Winget</span></span>

<span data-ttu-id="97a78-210">通过 `winget` 命令行工具，开发人员可以在 Windows 10 计算机上查找、安装、升级、删除和配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="97a78-210">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="97a78-211">此工具是 Windows 程序包管理器服务的客户端接口。</span><span class="sxs-lookup"><span data-stu-id="97a78-211">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="97a78-212">目前 `winget` 是预览功能。</span><span class="sxs-lookup"><span data-stu-id="97a78-212">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="97a78-213">当前并非所有计划功能都可用。</span><span class="sxs-lookup"><span data-stu-id="97a78-213">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="97a78-214">不应在生产部署方案中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="97a78-214">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="97a78-215">若要查看系统要求列表和安装说明，请参阅 [winget] 文档。</span><span class="sxs-lookup"><span data-stu-id="97a78-215">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="97a78-216">通过以下命令，可使用已发布的 `winget` 包安装 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="97a78-216">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="97a78-217">搜索最新版本的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97a78-217">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.0
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="97a78-218">使用 `--exact` 参数安装 PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="97a78-218">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><span data-ttu-id="97a78-219"><a id="msix" />从 Microsoft Store 安装</span><span class="sxs-lookup"><span data-stu-id="97a78-219"><a id="msix" />Installing from the Microsoft Store</span></span>

<span data-ttu-id="97a78-220">PowerShell 7.1 已发布到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="97a78-220">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="97a78-221">你可以在 [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) 网站上或在 Windows 应用商店应用程序中找到 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="97a78-221">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="97a78-222">Microsoft Store 包的权益：</span><span class="sxs-lookup"><span data-stu-id="97a78-222">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="97a78-223">直接内置于 Windows 10 的自动更新</span><span class="sxs-lookup"><span data-stu-id="97a78-223">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="97a78-224">与其他软件分发机制（如 Intune 和 SCCM）集成</span><span class="sxs-lookup"><span data-stu-id="97a78-224">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

<span data-ttu-id="97a78-225">的限制：</span><span class="sxs-lookup"><span data-stu-id="97a78-225">Limitations:</span></span>

<span data-ttu-id="97a78-226">MSIX 包在应用程序沙盒中运行，后者用于虚拟化对某些文件系统和注册表位置的访问。</span><span class="sxs-lookup"><span data-stu-id="97a78-226">MSIX packages run in an application sandbox that virtualizes access to some filesystem and registry locations.</span></span>

- <span data-ttu-id="97a78-227">HKEY_CURRENT_USER 下的所有注册表更改都将在写入到专用、每个用户、每个应用位置时进行复制。</span><span class="sxs-lookup"><span data-stu-id="97a78-227">All registry changes under HKEY_CURRENT_USER are copied on write to a private, per-user, per-app location.</span></span> <span data-ttu-id="97a78-228">因此，这些值不能用于其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="97a78-228">Therefore, those values are not available to other applications.</span></span>
- <span data-ttu-id="97a78-229">不能修改存储在 `$PSHOME` 中的任何系统级配置设置。</span><span class="sxs-lookup"><span data-stu-id="97a78-229">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="97a78-230">其中包括 WSMAN 配置。</span><span class="sxs-lookup"><span data-stu-id="97a78-230">This includes the WSMAN configuration.</span></span> <span data-ttu-id="97a78-231">这可以防止远程会话连接到 PowerShell 的基于应用商店的安装。</span><span class="sxs-lookup"><span data-stu-id="97a78-231">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="97a78-232">支持用户级配置和 SSH 远程处理。</span><span class="sxs-lookup"><span data-stu-id="97a78-232">User-level configurations and SSH remoting are supported.</span></span>

<span data-ttu-id="97a78-233">有关详细信息，请参阅[了解打包的桌面应用如何在 Windows 上运行](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes)。</span><span class="sxs-lookup"><span data-stu-id="97a78-233">For more information, see [Understanding how packaged desktop apps run on Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span></span>

### <a name="using-the-msix-package"></a><span data-ttu-id="97a78-234">使用 MSIX 包</span><span class="sxs-lookup"><span data-stu-id="97a78-234">Using the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="97a78-235">PowerShell 的预览版本包含一个 MSIX 包。</span><span class="sxs-lookup"><span data-stu-id="97a78-235">The preview builds of PowerShell include an MSIX package.</span></span> <span data-ttu-id="97a78-236">MSIX 包尚未获得正式支持。</span><span class="sxs-lookup"><span data-stu-id="97a78-236">The MSIX package is not officially supported.</span></span> <span data-ttu-id="97a78-237">生成此包的目的是为了在预览期间进行测试。</span><span class="sxs-lookup"><span data-stu-id="97a78-237">The package is built for testing purposes during the preview period.</span></span>

<span data-ttu-id="97a78-238">要在 Windows 10 客户端上手动安装 MSIX 包，请从 GitHub [版本][版本]页下载 MSIX 包。</span><span class="sxs-lookup"><span data-stu-id="97a78-238">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="97a78-239">向下滚动到要安装的版本的“资产”部分。 </span><span class="sxs-lookup"><span data-stu-id="97a78-239">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="97a78-240">“资产”部分可能处于折叠状态，因此可能需要单击使其展开。</span><span class="sxs-lookup"><span data-stu-id="97a78-240">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="97a78-241">MSIX 文件类似于 - `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="97a78-241">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="97a78-242">必须使用 `Add-AppxPackage` cmdlet，才能安装此包。</span><span class="sxs-lookup"><span data-stu-id="97a78-242">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="97a78-243">如何创建远程处理终结点</span><span class="sxs-lookup"><span data-stu-id="97a78-243">How to create a remoting endpoint</span></span>

<span data-ttu-id="97a78-244">PowerShell 同时支持采用 WSMan 和 SSH 的 PowerShell 远程处理协议 (PSRP)。</span><span class="sxs-lookup"><span data-stu-id="97a78-244">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="97a78-245">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="97a78-245">For more information, see:</span></span>

- <span data-ttu-id="97a78-246">[在 PowerShell Core 中进行 SSH 远程处理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="97a78-246">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="97a78-247">[在 PowerShell Core 中进行 WSMan 远程处理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="97a78-247">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="97a78-248">升级现有安装</span><span class="sxs-lookup"><span data-stu-id="97a78-248">Upgrading an existing installation</span></span>

<span data-ttu-id="97a78-249">若要在升级时获得最佳结果，应使用首次安装 PowerShell 时使用的相同安装方法。</span><span class="sxs-lookup"><span data-stu-id="97a78-249">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="97a78-250">每个安装方法都会将 PowerShell 安装在不同的位置中。</span><span class="sxs-lookup"><span data-stu-id="97a78-250">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="97a78-251">如果你不确定如何安装 PowerShell，可以将安装的位置与本文中的包信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="97a78-251">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="97a78-252">如果是通过 MSI 包安装的，则该信息将显示在“程序和功能”控制面板中。</span><span class="sxs-lookup"><span data-stu-id="97a78-252">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="97a78-253">安装支持</span><span class="sxs-lookup"><span data-stu-id="97a78-253">Installation support</span></span>

<span data-ttu-id="97a78-254">Microsoft 支持本文档中的安装方法。</span><span class="sxs-lookup"><span data-stu-id="97a78-254">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="97a78-255">其他源可能会提供其他安装方法。</span><span class="sxs-lookup"><span data-stu-id="97a78-255">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="97a78-256">尽管这些工具和方法可能有效，但 Microsoft 无法支持这些方法。</span><span class="sxs-lookup"><span data-stu-id="97a78-256">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[版本]: https://github.com/PowerShell/PowerShell/releases
[releases]: https://github.com/PowerShell/PowerShell/releases
[latest]: https://github.com/PowerShell/PowerShell/releases/latest
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
