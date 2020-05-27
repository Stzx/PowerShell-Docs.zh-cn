---
title: 在 Windows 上安装 PowerShell
description: 介绍如何在 Windows 上安装 PowerShell
ms.date: 05/21/2020
ms.openlocfilehash: 864f297e4f569030439bd6b581ef593d36f8b910
ms.sourcegitcommit: fd6a33b9fac973b3554fecfea7f51475e650a606
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83791488"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="071a7-103">在 Windows 上安装 PowerShell</span><span class="sxs-lookup"><span data-stu-id="071a7-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="071a7-104">有多种方法可以在 Windows 中安装 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="071a7-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="071a7-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="071a7-105">Prerequisites</span></span>

<span data-ttu-id="071a7-106">Windows 7 SP1、Server 2008 R2 及更高版本支持最新版 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="071a7-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="071a7-107">若要通过 WSMan 启用 PowerShell 远程处理，需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="071a7-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="071a7-108">在低于 Windows 10 的 Windows 版本上安装[通用 C 运行时](https://www.microsoft.com/download/details.aspx?id=50410)。</span><span class="sxs-lookup"><span data-stu-id="071a7-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="071a7-109">可以通过直接下载或 Windows 更新来获取它。</span><span class="sxs-lookup"><span data-stu-id="071a7-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="071a7-110">完全修补的系统已安装此包。</span><span class="sxs-lookup"><span data-stu-id="071a7-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="071a7-111">在 Windows 7 和 Windows Server 2008 R2 上安装 Windows Management Framework (WMF) 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="071a7-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="071a7-112">有关 WMF 的详细信息，请参阅 [WMF 概述](/powershell/scripting/wmf/overview)。</span><span class="sxs-lookup"><span data-stu-id="071a7-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="071a7-113">下载安装程序包</span><span class="sxs-lookup"><span data-stu-id="071a7-113">Download the installer package</span></span>

<span data-ttu-id="071a7-114">若要在 Windows 上安装 PowerShell，请从 GitHub[“发布”][releases]页下载安装包。</span><span class="sxs-lookup"><span data-stu-id="071a7-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="071a7-115">向下滚动到“版本”页的“资产”  部分。</span><span class="sxs-lookup"><span data-stu-id="071a7-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="071a7-116">由于“资产”  部分可能处于折叠状态，因此可能需要单击展开它。</span><span class="sxs-lookup"><span data-stu-id="071a7-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="071a7-117"><a id="msi" />安装 MSI 包</span><span class="sxs-lookup"><span data-stu-id="071a7-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="071a7-118">MSI 文件如下所示：`PowerShell-<version>-win-<os-arch>.msi`。</span><span class="sxs-lookup"><span data-stu-id="071a7-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="071a7-119">例如：</span><span class="sxs-lookup"><span data-stu-id="071a7-119">For example:</span></span>

- `PowerShell-7.0.1-win-x64.msi`
- `PowerShell-7.0.1-win-x86.msi`

<span data-ttu-id="071a7-120">下载后，双击安装程序并按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="071a7-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="071a7-121">安装程序在 Windows“开始”菜单中创建一个快捷方式。</span><span class="sxs-lookup"><span data-stu-id="071a7-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="071a7-122">默认情况下，包安装位置为 `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="071a7-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="071a7-123">可以通过“开始”菜单或 `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` 启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="071a7-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="071a7-124">PowerShell 7 安装到新目录，并与 Windows PowerShell 5.1 并行运行。</span><span class="sxs-lookup"><span data-stu-id="071a7-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="071a7-125">对于 PowerShell Core 6.x，PowerShell 7 是删除 PowerShell Core 6.x 的就地升级。</span><span class="sxs-lookup"><span data-stu-id="071a7-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="071a7-126">PowerShell 7 安装到 `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="071a7-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="071a7-127">`$env:ProgramFiles\PowerShell\7` 文件夹已添加到 `$env:PATH`</span><span class="sxs-lookup"><span data-stu-id="071a7-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="071a7-128">`$env:ProgramFiles\PowerShell\6` 文件夹已删除</span><span class="sxs-lookup"><span data-stu-id="071a7-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="071a7-129">如果需要与 PowerShell 7 并行运行 PowerShell 6，请使用 [ZIP 安装](#zip)方法重新安装 PowerShell 6。</span><span class="sxs-lookup"><span data-stu-id="071a7-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="071a7-130">通过命令行进行管理安装</span><span class="sxs-lookup"><span data-stu-id="071a7-130">Administrative install from the command line</span></span>

<span data-ttu-id="071a7-131">可以通过命令行安装 MSI 包，这样管理员能够在没有用户交互的情况下部署包。</span><span class="sxs-lookup"><span data-stu-id="071a7-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="071a7-132">MSI 包中有下列控制安装选项的属性：</span><span class="sxs-lookup"><span data-stu-id="071a7-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="071a7-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - 此属性控制向 Windows 资源管理器中的上下文菜单添加“打开 PowerShell”  项的选项。</span><span class="sxs-lookup"><span data-stu-id="071a7-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="071a7-134">**ENABLE_PSREMOTING** - 此属性控制用于在安装过程中启用 PowerShell 远程处理的选项。</span><span class="sxs-lookup"><span data-stu-id="071a7-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="071a7-135">**REGISTER_MANIFEST** - 此属性控制用于注册 Windows 事件日志记录清单的选项。</span><span class="sxs-lookup"><span data-stu-id="071a7-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="071a7-136">下面的示例展示了如何在启用所有安装选项的情况下无提示安装 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="071a7-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.1-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="071a7-137">有关 `Msiexec.exe` 命令行选项的完整列表，请参阅[命令行选项](/windows/desktop/Msi/command-line-options)。</span><span class="sxs-lookup"><span data-stu-id="071a7-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="071a7-138"><a id="msix" />安装 MSIX 包</span><span class="sxs-lookup"><span data-stu-id="071a7-138"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="071a7-139">要在 Windows 10 客户端上手动安装 MSIX 包，请从 GitHub [版本][releases]页面下载 MSIX 包。</span><span class="sxs-lookup"><span data-stu-id="071a7-139">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="071a7-140">向下滚动到要安装的版本的“资产”部分。 </span><span class="sxs-lookup"><span data-stu-id="071a7-140">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="071a7-141">“资产”部分可能处于折叠状态，因此可能需要单击使其展开。</span><span class="sxs-lookup"><span data-stu-id="071a7-141">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="071a7-142">MSIX 文件类似于 - `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="071a7-142">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="071a7-143">必须使用 `Add-AppxPackage` cmdlet，才能安装此包。</span><span class="sxs-lookup"><span data-stu-id="071a7-143">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

> [!NOTE]
> <span data-ttu-id="071a7-144">MSIX 包尚未发布。</span><span class="sxs-lookup"><span data-stu-id="071a7-144">The MSIX package has not been released yet.</span></span> <span data-ttu-id="071a7-145">发布后，此包将位于 Microsoft Store 和 GitHub[“发布”][releases]页中。</span><span class="sxs-lookup"><span data-stu-id="071a7-145">When released, the package will be available in the Microsoft Store and from the GitHub [releases][releases] page.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="071a7-146"><a id="zip" />安装 ZIP 包</span><span class="sxs-lookup"><span data-stu-id="071a7-146"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="071a7-147">提供有 PowerShell 二进制 ZIP 存档，从而支持高级部署方案。</span><span class="sxs-lookup"><span data-stu-id="071a7-147">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="071a7-148">安装 ZIP 存档不会像 MSI 包一样检查先决条件。</span><span class="sxs-lookup"><span data-stu-id="071a7-148">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="071a7-149">从[发布][releases]页面下载 ZIP 存档。</span><span class="sxs-lookup"><span data-stu-id="071a7-149">Download the ZIP archive from the [releases][releases] page.</span></span> <span data-ttu-id="071a7-150">根据该文件的下载方式，你可能需要使用 `Unblock-File` cmdlet 解锁。</span><span class="sxs-lookup"><span data-stu-id="071a7-150">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="071a7-151">将内容解压到你选择的位置，然后从该位置运行 `pwsh.exe`。</span><span class="sxs-lookup"><span data-stu-id="071a7-151">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="071a7-152">为了让使用 WSMan 的远程处理能够正常运行，请确保已满足[先决条件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="071a7-152">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="071a7-153">Windows 10 IoT 企业版部署</span><span class="sxs-lookup"><span data-stu-id="071a7-153">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="071a7-154">Windows 10 IoT 企业版随附 Windows PowerShell，可用来部署 PowerShell 7。</span><span class="sxs-lookup"><span data-stu-id="071a7-154">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="071a7-155">在目标设备中创建 `PSSession`</span><span class="sxs-lookup"><span data-stu-id="071a7-155">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="071a7-156">将 ZIP 包复制到设备</span><span class="sxs-lookup"><span data-stu-id="071a7-156">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="071a7-157">连接到设备并展开存档</span><span class="sxs-lookup"><span data-stu-id="071a7-157">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="071a7-158">设置 PowerShell 7 远程处理</span><span class="sxs-lookup"><span data-stu-id="071a7-158">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="071a7-159">连接到设备上的 PowerShell 7 终结点</span><span class="sxs-lookup"><span data-stu-id="071a7-159">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="071a7-160">Windows 10 IoT 核心版部署</span><span class="sxs-lookup"><span data-stu-id="071a7-160">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="071a7-161">当你添加 IOT_POWERSHELL  功能后，Windows 10 IoT 核心版便会添加 Windows PowerShell，我们可以使用它来部署 PowerShell 7。</span><span class="sxs-lookup"><span data-stu-id="071a7-161">Windows 10 IoT Core adds Windows PowerShell when you include *IOT_POWERSHELL* feature, which we can use to deploy PowerShell 7.</span></span>
<span data-ttu-id="071a7-162">对于 IoT 核心版，还可以遵循为 Windows 10 IoT 企业版定义的步骤。</span><span class="sxs-lookup"><span data-stu-id="071a7-162">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="071a7-163">若要在随附映像中添加最新的 Powershell，请使用 [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) 命令在工作区域中添加包，然后将 OPENSRC_POWERSHELL  功能添加到映像中。</span><span class="sxs-lookup"><span data-stu-id="071a7-163">For adding the latest powershell in the shipping image, use [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) command to include the package in the workarea and add *OPENSRC_POWERSHELL* feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="071a7-164">对于 ARM64 体系结构，在你添加 IOT_POWERSHELL  功能后，它不会添加 Windows Powershell。</span><span class="sxs-lookup"><span data-stu-id="071a7-164">For ARM64 architecture, Windows Powershell is not added when you include *IOT_POWERSHELL*.</span></span> <span data-ttu-id="071a7-165">因此，基于 zip 的安装将不起作用。</span><span class="sxs-lookup"><span data-stu-id="071a7-165">So the zip based install will not work.</span></span>
> <span data-ttu-id="071a7-166">需要使用 Import-PSCoreRelease 命令将其添加到映像中。</span><span class="sxs-lookup"><span data-stu-id="071a7-166">You will need to use Import-PSCoreRelease command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="071a7-167">在 Nano Server 上进行部署</span><span class="sxs-lookup"><span data-stu-id="071a7-167">Deploying on Nano Server</span></span>

<span data-ttu-id="071a7-168">为了更好地理解这些说明，假定 Nano Server 是已运行 PowerShell 版本的“无外设”操作系统。</span><span class="sxs-lookup"><span data-stu-id="071a7-168">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="071a7-169">有关详细信息，请参阅 [Nano Server 映像生成器](/windows-server/get-started/deploy-nano-server)文档。</span><span class="sxs-lookup"><span data-stu-id="071a7-169">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="071a7-170">可以使用两种不同的方法来部署 PowerShell 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="071a7-170">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="071a7-171">脱机 - 安装 Nano Server VHD，并将 zip 文件的内容解压到安装映像中的所选位置。</span><span class="sxs-lookup"><span data-stu-id="071a7-171">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="071a7-172">联机 - 通过 PowerShell 会话传输 zip 文件，并在所需位置中将其解压。</span><span class="sxs-lookup"><span data-stu-id="071a7-172">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="071a7-173">在这两种情况下，都需要 Windows 10 x64 ZIP 版本包。</span><span class="sxs-lookup"><span data-stu-id="071a7-173">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="071a7-174">在 PowerShell 的“管理员”实例中运行命令。</span><span class="sxs-lookup"><span data-stu-id="071a7-174">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="071a7-175">PowerShell 脱机部署</span><span class="sxs-lookup"><span data-stu-id="071a7-175">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="071a7-176">使用常用 zip 实用工具将包解压到已安装的 Nano Server 映像中的目录。</span><span class="sxs-lookup"><span data-stu-id="071a7-176">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="071a7-177">卸载映像并启动。</span><span class="sxs-lookup"><span data-stu-id="071a7-177">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="071a7-178">连接到 Windows PowerShell 的收件箱实例。</span><span class="sxs-lookup"><span data-stu-id="071a7-178">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="071a7-179">按照说明使用[“另一种实例技术”](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)创建远程处理终结点。</span><span class="sxs-lookup"><span data-stu-id="071a7-179">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="071a7-180">PowerShell 联机部署</span><span class="sxs-lookup"><span data-stu-id="071a7-180">Online Deployment of PowerShell</span></span>

<span data-ttu-id="071a7-181">若要将 PowerShell 部署到 Nano Server，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="071a7-181">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="071a7-182">连接到 Windows PowerShell 的收件箱实例</span><span class="sxs-lookup"><span data-stu-id="071a7-182">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="071a7-183">将文件复制到 Nano Server 实例</span><span class="sxs-lookup"><span data-stu-id="071a7-183">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="071a7-184">输入会话</span><span class="sxs-lookup"><span data-stu-id="071a7-184">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="071a7-185">提取 ZIP 文件</span><span class="sxs-lookup"><span data-stu-id="071a7-185">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="071a7-186">如果需要基于 WSMan 的远程处理，请按照说明使用[“另一种实例技术”](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)创建远程处理终结点。</span><span class="sxs-lookup"><span data-stu-id="071a7-186">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="071a7-187">作为 .NET 全局工具安装</span><span class="sxs-lookup"><span data-stu-id="071a7-187">Install as a .NET Global tool</span></span>

<span data-ttu-id="071a7-188">如果你已安装 [.NET Core SDK](/dotnet/core/sdk)，则可以轻松地安装 PowerShell 作为 [.NET 全局工具](/dotnet/core/tools/global-tools)。</span><span class="sxs-lookup"><span data-stu-id="071a7-188">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="071a7-189">dotnet 工具安装程序将 `$env:USERPROFILE\dotnet\tools` 添加到 `$env:PATH` 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="071a7-189">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="071a7-190">不过，当前运行的 shell 没有更新后的 `$env:PATH`。</span><span class="sxs-lookup"><span data-stu-id="071a7-190">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="071a7-191">若要从新 shell 启动 PowerShell，可以键入“`pwsh`”。</span><span class="sxs-lookup"><span data-stu-id="071a7-191">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="071a7-192">如何创建远程处理终结点</span><span class="sxs-lookup"><span data-stu-id="071a7-192">How to create a remoting endpoint</span></span>

<span data-ttu-id="071a7-193">PowerShell 同时支持采用 WSMan 和 SSH 的 PowerShell 远程处理协议 (PSRP)。</span><span class="sxs-lookup"><span data-stu-id="071a7-193">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="071a7-194">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="071a7-194">For more information, see:</span></span>

- <span data-ttu-id="071a7-195">[在 PowerShell Core 中进行 SSH 远程处理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="071a7-195">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="071a7-196">[在 PowerShell Core 中进行 WSMan 远程处理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="071a7-196">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
