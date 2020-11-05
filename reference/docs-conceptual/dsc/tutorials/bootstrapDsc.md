---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: 初始启动时使用 DSC 配置虚拟机
description: 本文介绍了如何在初始启动时使用 DSC 配置虚拟机
ms.openlocfilehash: 9fa8c4a21486aaef87e1c0a3097e5983a378d98d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656205"
---
# <a name="configure-a-virtual-machines-at-initial-boot-up-by-using-dsc"></a><span data-ttu-id="e4195-104">初始启动时使用 DSC 配置虚拟机</span><span class="sxs-lookup"><span data-stu-id="e4195-104">Configure a virtual machines at initial boot-up by using DSC</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4195-105">适用于：Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="e4195-105">Applies To: Windows PowerShell 5.0</span></span>

## <a name="requirements"></a><span data-ttu-id="e4195-106">要求</span><span class="sxs-lookup"><span data-stu-id="e4195-106">Requirements</span></span>

> [!NOTE]
> <span data-ttu-id="e4195-107">本主题所述的 DSCAutomationHostEnabled 注册表项在 PowerShell 4.0 中不可用。</span><span class="sxs-lookup"><span data-stu-id="e4195-107">The **DSCAutomationHostEnabled** registry key described in this topic is not available in PowerShell 4.0.</span></span> <span data-ttu-id="e4195-108">有关如何在初始启动时于 PowerShell 4.0 中配置新虚拟机的信息，请参阅[想要在初始启动时使用 DSC 自动配置计算机？](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span><span class="sxs-lookup"><span data-stu-id="e4195-108">For information on how to configure new virtual machines at initial boot-up in PowerShell 4.0, see [Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span></span>

<span data-ttu-id="e4195-109">若要运行这些示例，则需要：</span><span class="sxs-lookup"><span data-stu-id="e4195-109">To run these examples, you will need:</span></span>

- <span data-ttu-id="e4195-110">要使用的可启动 VHD。</span><span class="sxs-lookup"><span data-stu-id="e4195-110">A bootable VHD to work with.</span></span> <span data-ttu-id="e4195-111">可以在 [TechNet 评估中心](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016)下载具有 Windows Server 2016 评估副本的 ISO。</span><span class="sxs-lookup"><span data-stu-id="e4195-111">You can download an ISO with an evaluation copy of Windows Server 2016 at [TechNet Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016).</span></span>
  <span data-ttu-id="e4195-112">可以在[创建可启动虚拟硬盘](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10))处找到有关如何从 ISO 映像创建 VHD 的说明。</span><span class="sxs-lookup"><span data-stu-id="e4195-112">You can find instructions on how to create a VHD from an ISO image at [Creating Bootable Virtual Hard Disks](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span></span>
- <span data-ttu-id="e4195-113">已启用 Hyper-V 的主计算机。</span><span class="sxs-lookup"><span data-stu-id="e4195-113">A host computer that has Hyper-V enabled.</span></span> <span data-ttu-id="e4195-114">有关信息，请参阅 [Hyper-V 概述](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="e4195-114">For information, see [Hyper-V overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span></span>

  <span data-ttu-id="e4195-115">通过使用 DSC，可以在初始启动时对计算机实现软件安装和配置的自动化。</span><span class="sxs-lookup"><span data-stu-id="e4195-115">By using DSC, you can automate software installation and configuration for a computer at initial boot-up.</span></span> <span data-ttu-id="e4195-116">可以通过将配置 MOF 文档或元配置注入可启动媒体（例如 VHD）来执行此操作，以便它们能在初始启动过程中运行。</span><span class="sxs-lookup"><span data-stu-id="e4195-116">You do this by either injecting a configuration MOF document or a metaconfiguration into bootable media (such as a VHD) so that they are run during the initial boot-up process.</span></span> <span data-ttu-id="e4195-117">通过 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` 下的 [DSCAutomationHostEnabled 注册表项](DSCAutomationHostEnabled.md) 注册表项指定此行为。</span><span class="sxs-lookup"><span data-stu-id="e4195-117">This behavior is specified by the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key under `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span></span>
  <span data-ttu-id="e4195-118">默认情况下，此项的值为 2，这允许 DSC 在启动时运行。</span><span class="sxs-lookup"><span data-stu-id="e4195-118">By default, the value of this key is 2, which allows DSC to run at boot time.</span></span>

  <span data-ttu-id="e4195-119">如果不希望 DSC 在启动时运行，将 [DSCAutomationHostEnabled](DSCAutomationHostEnabled.md) 注册表项的值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="e4195-119">If you do not want DSC to run at boot time, set the value of the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key to 0.</span></span>

- <span data-ttu-id="e4195-120">将配置 MOF 文档注入 VHD</span><span class="sxs-lookup"><span data-stu-id="e4195-120">Inject a configuration MOF document into a VHD</span></span>
- <span data-ttu-id="e4195-121">将 DSC 元配置注入 VHD</span><span class="sxs-lookup"><span data-stu-id="e4195-121">Inject a DSC metaconfiguration into a VHD</span></span>
- <span data-ttu-id="e4195-122">启动时，请禁用 DSC</span><span class="sxs-lookup"><span data-stu-id="e4195-122">Disable DSC at boot time</span></span>

> [!NOTE]
> <span data-ttu-id="e4195-123">可以将 `Pending.mof` 和 `MetaConfig.mof` 同时注入计算机。</span><span class="sxs-lookup"><span data-stu-id="e4195-123">You can inject both `Pending.mof` and `MetaConfig.mof` into a computer at the same time.</span></span>
> <span data-ttu-id="e4195-124">如果这两个文件都存在，则在 `MetaConfig.mof` 中指定的设置优先。</span><span class="sxs-lookup"><span data-stu-id="e4195-124">If both files are present, the settings specified in `MetaConfig.mof` take precedence.</span></span>

## <a name="inject-a-configuration-mof-document-into-a-vhd"></a><span data-ttu-id="e4195-125">将配置 MOF 文档注入 VHD</span><span class="sxs-lookup"><span data-stu-id="e4195-125">Inject a configuration MOF document into a VHD</span></span>

<span data-ttu-id="e4195-126">若要在初始启动时执行配置，可以将已编译的配置 MOF 文档注入 VHD 作为其 `Pending.mof` 文件。</span><span class="sxs-lookup"><span data-stu-id="e4195-126">To enact a configuration at initial boot-up, you can inject a compiled configuration MOF document into the VHD as its `Pending.mof` file.</span></span> <span data-ttu-id="e4195-127">如果将 **DSCAutomationHostEnabled** 注册表项设置为 2（默认值），则在首次启动计算机时，DSC 将应用由 `Pending.mof` 定义的配置。</span><span class="sxs-lookup"><span data-stu-id="e4195-127">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the configuration defined by `Pending.mof` when the computer boots up for the first time.</span></span>

<span data-ttu-id="e4195-128">对于此示例，我们将使用以下配置，它将在新计算机上安装 IIS：</span><span class="sxs-lookup"><span data-stu-id="e4195-128">For this example, we will use the following configuration, which will install IIS on the new computer:</span></span>

```powershell
Configuration SampleIISInstall
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    node ('localhost')
    {
        WindowsFeature IIS
        {
            Ensure = 'Present'
            Name   = 'Web-Server'
        }
    }
}
```

### <a name="to-inject-the-configuration-mof-document-on-the-vhd"></a><span data-ttu-id="e4195-129">将配置 MOF 文档注入 VHD</span><span class="sxs-lookup"><span data-stu-id="e4195-129">To inject the configuration MOF document on the VHD</span></span>

1. <span data-ttu-id="e4195-130">通过调用 [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet，将 VHD 装入想要注入配置的位置。</span><span class="sxs-lookup"><span data-stu-id="e4195-130">Mount the VHD into which you want to inject the configuration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="e4195-131">例如：</span><span class="sxs-lookup"><span data-stu-id="e4195-131">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="e4195-132">在运行 PowerShell 5.0 或更高版本的计算机上，将以上配置 ( **SampleIISInstall** ) 保存为 PowerShell 脚本 (.ps1) 文件。</span><span class="sxs-lookup"><span data-stu-id="e4195-132">On a computer running PowerShell 5.0 or later, save the above configuration ( **SampleIISInstall** ) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="e4195-133">在 PowerShell 控制台中，导航到保存 .ps1 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4195-133">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="e4195-134">运行以下 PowerShell 命令来编译 MOF 文档（有关编译 DSC 配置的信息，请参阅 [DSC 配置](../configurations/configurations.md)：</span><span class="sxs-lookup"><span data-stu-id="e4195-134">Run the following PowerShell commands to compile the MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\SampleIISInstall.ps1
   SampleIISInstall
   ```

1. <span data-ttu-id="e4195-135">这将在名为 `SampleIISInstall` 的新文件夹中创建 `localhost.mof` 文件。</span><span class="sxs-lookup"><span data-stu-id="e4195-135">This will create a `localhost.mof` file in a new folder named `SampleIISInstall`.</span></span> <span data-ttu-id="e4195-136">通过使用 [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet，重命名该文件并将其移动到 VHD 上的正确位置，作为 `Pending.mof`。</span><span class="sxs-lookup"><span data-stu-id="e4195-136">Rename and move that file into the proper location on the VHD as `Pending.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span> <span data-ttu-id="e4195-137">例如：</span><span class="sxs-lookup"><span data-stu-id="e4195-137">For example:</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\SampleIISInstall\localhost.mof -Destination E:\Windows\System32\Configuration\Pending.mof
   ```

1. <span data-ttu-id="e4195-138">通过调用 [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet 卸除 VHD。</span><span class="sxs-lookup"><span data-stu-id="e4195-138">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="e4195-139">例如：</span><span class="sxs-lookup"><span data-stu-id="e4195-139">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="e4195-140">通过使用安装了 DSC MOF 文档的 VHD 创建 VM。</span><span class="sxs-lookup"><span data-stu-id="e4195-140">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="e4195-141">初始启动并安装操作系统之后，将安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="e4195-141">After initial boot-up and operating system installation, IIS will be installed.</span></span> <span data-ttu-id="e4195-142">可以通过调用 [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet 对此进行验证。</span><span class="sxs-lookup"><span data-stu-id="e4195-142">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="inject-a-dsc-metaconfiguration-into-a-vhd"></a><span data-ttu-id="e4195-143">将 DSC 元配置注入 VHD</span><span class="sxs-lookup"><span data-stu-id="e4195-143">Inject a DSC metaconfiguration into a VHD</span></span>

<span data-ttu-id="e4195-144">还可通过将元配置注入 VHD 作为其 `MetaConfig.mof` 文件，从而在初始启动时配置计算机以请求配置（请参阅[配置本地配置管理器 (LCM)](../managing-nodes/metaConfig.md)）。</span><span class="sxs-lookup"><span data-stu-id="e4195-144">You can also configure a computer to pull a configuration at initial boot-up by injecting a metaconfiguration (see [Configuring the Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md)) into the VHD as its `MetaConfig.mof` file.</span></span> <span data-ttu-id="e4195-145">如果将 DSCAutomationHostEnabled 注册表项设置为 2（默认值），则在首次启动计算机时，DSC 会将由 `MetaConfig.mof` 定义的元配置应用到 LCM。</span><span class="sxs-lookup"><span data-stu-id="e4195-145">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the metaconfiguration defined by `MetaConfig.mof` to the LCM when the computer boots up for the first time.</span></span> <span data-ttu-id="e4195-146">如果元配置指定 LCM 应从请求服务器请求配置，则计算机将尝试在初始启动时从该请求服务器请求配置。</span><span class="sxs-lookup"><span data-stu-id="e4195-146">If the metaconfiguration specifies that the LCM should pull configurations from a pull server, the computer will attempt to pull a configuration from that pull server at initial boot-up.</span></span> <span data-ttu-id="e4195-147">有关设置 DSC 请求服务器的信息，请参阅[设置 DSC Web 请求服务器](../pull-server/pullServer.md)。</span><span class="sxs-lookup"><span data-stu-id="e4195-147">For information about setting up a DSC pull server, see [Setting up a DSC web pull server](../pull-server/pullServer.md).</span></span>

<span data-ttu-id="e4195-148">对于此示例，我们将使用上一节中所述的配置 ( **SampleIISInstall** )，以及以下元配置：</span><span class="sxs-lookup"><span data-stu-id="e4195-148">For this example, we will use both the configuration described in the previous section ( **SampleIISInstall** ), and the following metaconfiguration:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientBootstrap
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('SampleIISInstall')
        }
    }
}
```

### <a name="to-inject-the-metaconfiguration-mof-document-on-the-vhd"></a><span data-ttu-id="e4195-149">将元配置 MOF 文档注入 VHD</span><span class="sxs-lookup"><span data-stu-id="e4195-149">To inject the metaconfiguration MOF document on the VHD</span></span>

1. <span data-ttu-id="e4195-150">通过调用 [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet，将 VHD 装入想要注入元配置的位置。</span><span class="sxs-lookup"><span data-stu-id="e4195-150">Mount the VHD into which you want to inject the metaconfiguration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="e4195-151">例如：</span><span class="sxs-lookup"><span data-stu-id="e4195-151">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="e4195-152">[设置 DSC Web 请求服务器](../pull-server/pullServer.md)，并将 SampleIISInstall 配置保存到相应的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4195-152">[Set up a DSC web pull server](../pull-server/pullServer.md), and save the **SampleIISInstall** configuration to the appropriate folder.</span></span>

1. <span data-ttu-id="e4195-153">在运行 PowerShell 5.0 或更高版本的计算机上，将以上元配置 ( **PullClientBootstrap** ) 保存为 PowerShell 脚本 (.ps1) 文件。</span><span class="sxs-lookup"><span data-stu-id="e4195-153">On a computer running PowerShell 5.0 or later, save the above metaconfiguration ( **PullClientBootstrap** ) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="e4195-154">在 PowerShell 控制台中，导航到保存 .ps1 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4195-154">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="e4195-155">运行以下 PowerShell 命令来编译元配置 MOF 文档（有关编译 DSC 配置的信息，请参阅 [DSC 配置](../configurations/configurations.md)：</span><span class="sxs-lookup"><span data-stu-id="e4195-155">Run the following PowerShell commands to compile the metaconfiguration MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\PullClientBootstrap.ps1
   PullClientBootstrap
   ```

1. <span data-ttu-id="e4195-156">这将在名为 `PullClientBootstrap` 的新文件夹中创建 `localhost.meta.mof` 文件。</span><span class="sxs-lookup"><span data-stu-id="e4195-156">This will create a `localhost.meta.mof` file in a new folder named `PullClientBootstrap`.</span></span> <span data-ttu-id="e4195-157">通过使用 [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet，重命名该文件并将其移动到 VHD 上的正确位置，作为 `MetaConfig.mof`。</span><span class="sxs-lookup"><span data-stu-id="e4195-157">Rename and move that file into the proper location on the VHD as `MetaConfig.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\PullClientBootstrap\localhost.meta.mof -Destination E:\Windows\System32\Configuration\MetaConfig.mof
   ```

1. <span data-ttu-id="e4195-158">通过调用 [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet 卸除 VHD。</span><span class="sxs-lookup"><span data-stu-id="e4195-158">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="e4195-159">例如：</span><span class="sxs-lookup"><span data-stu-id="e4195-159">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="e4195-160">通过使用安装了 DSC MOF 文档的 VHD 创建 VM。</span><span class="sxs-lookup"><span data-stu-id="e4195-160">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="e4195-161">初始启动并安装操作系统之后，DSC 将从请求服务器请求配置，并安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="e4195-161">After initial boot-up and operating system installation, DSC will pull the configuration from the pull server, and IIS will be installed.</span></span> <span data-ttu-id="e4195-162">可以通过调用 [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet 对此进行验证。</span><span class="sxs-lookup"><span data-stu-id="e4195-162">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="disable-dsc-at-boot-time"></a><span data-ttu-id="e4195-163">启动时，请禁用 DSC</span><span class="sxs-lookup"><span data-stu-id="e4195-163">Disable DSC at boot time</span></span>

<span data-ttu-id="e4195-164">默认情况下，`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled` 项的值</span><span class="sxs-lookup"><span data-stu-id="e4195-164">By default, the value of the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled`</span></span>
<span data-ttu-id="e4195-165">设置为 2，以允许在计算机处于挂起或当前状态时运行 DSC 配置。</span><span class="sxs-lookup"><span data-stu-id="e4195-165">key is set to 2, which allows a DSC configuration to run if the computer is in pending or current state.</span></span> <span data-ttu-id="e4195-166">如果不希望配置在初始启动时运行，则需要将此项的值设置为 0：</span><span class="sxs-lookup"><span data-stu-id="e4195-166">If you do not want a configuration to run at initial boot-up, you need so set the value of this key to 0:</span></span>

1. <span data-ttu-id="e4195-167">通过调用 [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet 装载 VHD。</span><span class="sxs-lookup"><span data-stu-id="e4195-167">Mount the VHD by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="e4195-168">例如：</span><span class="sxs-lookup"><span data-stu-id="e4195-168">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="e4195-169">通过调用 `reg load` 从 VHD 加载注册表 `HKLM\Software` 子项。</span><span class="sxs-lookup"><span data-stu-id="e4195-169">Load the registry `HKLM\Software` subkey from the VHD by calling `reg load`.</span></span>

   ```powershell
   reg load HKLM\Vhd E:\Windows\System32\Config\Software`
   ```

1. <span data-ttu-id="e4195-170">使用 PowerShell 注册表提供程序导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`。</span><span class="sxs-lookup"><span data-stu-id="e4195-170">Navigate to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` by using the PowerShell Registry provider.</span></span>

   ```powershell
   Set-Location HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\System`
   ```

1. <span data-ttu-id="e4195-171">将 `DSCAutomationHostEnabled` 的值更改为 0。</span><span class="sxs-lookup"><span data-stu-id="e4195-171">Change the value of `DSCAutomationHostEnabled` to 0.</span></span>

   ```powershell
   Set-ItemProperty -Path . -Name DSCAutomationHostEnabled -Value 0
   ```

5. <span data-ttu-id="e4195-172">通过运行以下命令来卸载注册表：</span><span class="sxs-lookup"><span data-stu-id="e4195-172">Unload the registry by running the following commands:</span></span>

   ```powershell
   [gc]::Collect()
   reg unload HKLM\Vhd
   ```

## <a name="see-also"></a><span data-ttu-id="e4195-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4195-173">See Also</span></span>

[<span data-ttu-id="e4195-174">DSC 配置</span><span class="sxs-lookup"><span data-stu-id="e4195-174">DSC Configurations</span></span>](../configurations/configurations.md)

[<span data-ttu-id="e4195-175">DSCAutomationHostEnabled 注册表项</span><span class="sxs-lookup"><span data-stu-id="e4195-175">DSCAutomationHostEnabled registry key</span></span>](DSCAutomationHostEnabled.md)

[<span data-ttu-id="e4195-176">配置本地配置管理器 (LCM)</span><span class="sxs-lookup"><span data-stu-id="e4195-176">Configuring the Local Configuration Manager (LCM)</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="e4195-177">设置 DSC Web 请求服务器</span><span class="sxs-lookup"><span data-stu-id="e4195-177">Setting up a DSC web pull server</span></span>](../pull-server/pullServer.md)
