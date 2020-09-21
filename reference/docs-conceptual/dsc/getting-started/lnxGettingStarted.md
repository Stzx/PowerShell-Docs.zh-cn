---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: 适用于 Linux 的 Desired State Configuration (DSC) 入门
ms.openlocfilehash: 64657dda04fa2df97fa2ad7c7a5c2d15b66a270a
ms.sourcegitcommit: 4bb44f183dcbfa8dced57f075812e02d3b45fd70
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "86301329"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="1905b-103">适用于 Linux 的 Desired State Configuration (DSC) 入门</span><span class="sxs-lookup"><span data-stu-id="1905b-103">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="1905b-104">本主题说明如何开始使用适用于 Linux 的 PowerShell Desired State Configuration (DSC)。</span><span class="sxs-lookup"><span data-stu-id="1905b-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span> <span data-ttu-id="1905b-105">有关 DSC 的常规信息，请参阅 [Windows PowerShell Desired State Configuration 入门](../overview/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1905b-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="1905b-106">支持的 Linux 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="1905b-106">Supported Linux operation system versions</span></span>

<span data-ttu-id="1905b-107">适用于 Linux 的 DSC 支持以下 Linux 操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="1905b-107">The following Linux operating system versions are supported by DSC for Linux.</span></span>

- <span data-ttu-id="1905b-108">CentOS 5、6 和 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="1905b-108">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="1905b-109">Debian GNU/Linux 6、7 和 8 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="1905b-109">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="1905b-110">Oracle Linux 5、6 和 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="1905b-110">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="1905b-111">Red Hat Enterprise Linux Server 5、6 和 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="1905b-111">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="1905b-112">SUSE Linux Enterprise Server 10、11 和 12 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="1905b-112">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="1905b-113">Ubuntu Server 12.04 LTS、14.04 LTS 和 16.04 LTS (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="1905b-113">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span></span>

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="1905b-114">安装适用于 Linux 的 DSC</span><span class="sxs-lookup"><span data-stu-id="1905b-114">Installing DSC for Linux</span></span>

<span data-ttu-id="1905b-115">必须先安装[开放式管理基础结构 (OMI)](https://github.com/Microsoft/omi)，才能安装适用于 Linux 的 DSC。</span><span class="sxs-lookup"><span data-stu-id="1905b-115">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="1905b-116">安装 OMI</span><span class="sxs-lookup"><span data-stu-id="1905b-116">Installing OMI</span></span>

<span data-ttu-id="1905b-117">适用于 Linux 的 Desired State Configuration 需要开放式管理基础结构 (OMI) CIM 服务器版本 1.0.8.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1905b-117">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="1905b-118">可从 The Open Group：[Open Management Infrastructure (OMI)（开放式管理基础结构）](https://github.com/Microsoft/omi)下载 OMI。</span><span class="sxs-lookup"><span data-stu-id="1905b-118">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="1905b-119">若要安装 OMI，请安装适用于 Linux 系统（.rpm 或.deb）和 OpenSSL 版本（ssl_098 或 ssl_100）以及体系结构 (x64/x86) 的程序包。</span><span class="sxs-lookup"><span data-stu-id="1905b-119">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="1905b-120">RPM 程序包适用于 CentOS、Red Hat Enterprise Linux、SUSE Linux Enterprise Server 和 Oracle Linux。</span><span class="sxs-lookup"><span data-stu-id="1905b-120">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="1905b-121">DEB 程序包适用于 Debian GNU/Linux 和 Ubuntu Server。</span><span class="sxs-lookup"><span data-stu-id="1905b-121">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="1905b-122">ssl_098 程序包适用于安装了 OpenSSL 0.9.8 的计算机，而 ssl_100 程序包适用于安装了 OpenSSL 1.0 的计算机。</span><span class="sxs-lookup"><span data-stu-id="1905b-122">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="1905b-123">若要确定安装的 OpenSSL 版本，请运行 `openssl version` 命令。</span><span class="sxs-lookup"><span data-stu-id="1905b-123">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="1905b-124">运行以下命令以在 CentOS 7 x64 系统上安装 OMI。</span><span class="sxs-lookup"><span data-stu-id="1905b-124">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="1905b-125">安装 DSC</span><span class="sxs-lookup"><span data-stu-id="1905b-125">Installing DSC</span></span>

<span data-ttu-id="1905b-126">适用于 Linux 的 DSC 可在[此处](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294)下载。</span><span class="sxs-lookup"><span data-stu-id="1905b-126">DSC for Linux is available for download [here](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span></span>

<span data-ttu-id="1905b-127">若要安装 DSC，请安装适用于 Linux 系统（.rpm 或.deb）和 OpenSSL 版本（ssl_098 或 ssl_100）以及体系结构 (x64/x86) 的程序包。</span><span class="sxs-lookup"><span data-stu-id="1905b-127">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="1905b-128">RPM 程序包适用于 CentOS、Red Hat Enterprise Linux、SUSE Linux Enterprise Server 和 Oracle Linux。</span><span class="sxs-lookup"><span data-stu-id="1905b-128">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="1905b-129">DEB 程序包适用于 Debian GNU/Linux 和 Ubuntu Server。</span><span class="sxs-lookup"><span data-stu-id="1905b-129">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="1905b-130">ssl_098 程序包适用于安装了 OpenSSL 0.9.8 的计算机，而 ssl_100 程序包适用于安装了 OpenSSL 1.0 的计算机。</span><span class="sxs-lookup"><span data-stu-id="1905b-130">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="1905b-131">若要确定安装的 OpenSSL 版本，请运行 openssl version 命令。</span><span class="sxs-lookup"><span data-stu-id="1905b-131">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="1905b-132">运行以下命令以在 CentOS 7 x64 系统上安装 DSC。</span><span class="sxs-lookup"><span data-stu-id="1905b-132">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="1905b-133">使用适用于 Linux 的 DSC</span><span class="sxs-lookup"><span data-stu-id="1905b-133">Using DSC for Linux</span></span>

<span data-ttu-id="1905b-134">以下章节说明了如何在 Linux 计算机上创建和运行 DSC 配置。</span><span class="sxs-lookup"><span data-stu-id="1905b-134">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="1905b-135">创建配置 MOF 文档</span><span class="sxs-lookup"><span data-stu-id="1905b-135">Creating a configuration MOF document</span></span>

<span data-ttu-id="1905b-136">使用 Windows PowerShell Configuration 关键字为 Linux 计算机创建配置，与为 Windows 计算机创建配置类似。</span><span class="sxs-lookup"><span data-stu-id="1905b-136">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="1905b-137">以下步骤描述了如何使用 Windows PowerShell 为 Linux 计算机创建配置文档。</span><span class="sxs-lookup"><span data-stu-id="1905b-137">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="1905b-138">导入 nx 模块。</span><span class="sxs-lookup"><span data-stu-id="1905b-138">Import the nx module.</span></span> <span data-ttu-id="1905b-139">此 nx Windows PowerShell 模块包含适用于 Linux 的 DSC 内置资源的架构，必须将其安装到本地计算机上并导入到配置中。</span><span class="sxs-lookup"><span data-stu-id="1905b-139">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="1905b-140">若要安装 nx 模块，请将 nx 模块目录复制到 `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` 或 `$PSHOME\Modules` 中。</span><span class="sxs-lookup"><span data-stu-id="1905b-140">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="1905b-141">该 nx 模块包含在适用于 Linux 的 DSC 安装包中。</span><span class="sxs-lookup"><span data-stu-id="1905b-141">The nx module is included in the DSC for Linux installation package.</span></span> <span data-ttu-id="1905b-142">若要在配置中导入 nx 模块，请使用 `Import-DSCResource` 命令：</span><span class="sxs-lookup"><span data-stu-id="1905b-142">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="1905b-143">定义配置并生成配置文档：</span><span class="sxs-lookup"><span data-stu-id="1905b-143">Define a configuration and generate the configuration document:</span></span>

   ```powershell
   Configuration ExampleConfiguration
   {
        Import-DscResource -Module nx

        Node  "linuxhost.contoso.com"
        {
            nxFile ExampleFile 
            {
                DestinationPath = "/tmp/example"
                Contents = "hello world `n"
                Ensure = "Present"
                Type = "File"
            }
        }
   }

   ExampleConfiguration -OutputPath:"C:\temp"
   ```

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="1905b-144">将配置推送到 Linux 计算机</span><span class="sxs-lookup"><span data-stu-id="1905b-144">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="1905b-145">可使用 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet 将配置文档（MOF 文件）推送到 Linux 计算机。</span><span class="sxs-lookup"><span data-stu-id="1905b-145">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="1905b-146">若要将此 cmdlet 和 [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) 或 [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlet 远程运用到 Linux 计算机，必须使用 CIMSession。</span><span class="sxs-lookup"><span data-stu-id="1905b-146">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="1905b-147">使用 [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet 将 CIMSession 创建到 Linux 计算机中。</span><span class="sxs-lookup"><span data-stu-id="1905b-147">The [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet is used to create a CIMSession to the Linux computer.</span></span>

<span data-ttu-id="1905b-148">以下代码表明了如何创建适用于 Linux 的 DSC CIMSession。</span><span class="sxs-lookup"><span data-stu-id="1905b-148">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

```powershell
$Node = "ostc-dsc-01"
$Credential = Get-Credential -UserName "root" -Message "Enter Password:"

#Ignore SSL certificate validation
#$opt = New-CimSessionOption -UseSsl $true -SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true

#Options for a trusted SSL certificate
$opt = New-CimSessionOption -UseSsl $true
$Sess=New-CimSession -Credential $credential -ComputerName $Node -Port 5986 -Authentication basic -SessionOption $opt -OperationTimeoutSec 90
```

> [!NOTE]
> <span data-ttu-id="1905b-149">对于“推送”模式，用户凭据必须为 Linux 计算机上的根用户。</span><span class="sxs-lookup"><span data-stu-id="1905b-149">For "Push" mode, the user credential must be the root user on the Linux computer.</span></span>
> <span data-ttu-id="1905b-150">适用于 Linux 的 DSC 仅支持 SSL/TLS 连接，使用 `New-CimSession` 时必须将 –UseSSL 参数设置为 $true。</span><span class="sxs-lookup"><span data-stu-id="1905b-150">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span>
> <span data-ttu-id="1905b-151">在 `/etc/opt/omi/conf/omiserver.conf` 文件中通过 pemfile 和 keyfile 属性指定（DSC 的）OMI 使用的 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="1905b-151">The SSL certificate used by OMI (for DSC) is specified in the file: `/etc/opt/omi/conf/omiserver.conf` with the properties: pemfile and keyfile.</span></span>
> <span data-ttu-id="1905b-152">如果 [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet 运行于的 Windows 计算机不信任此证书，你可以通过以下 CIMSession 选项选择忽略证书验证：`-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span><span class="sxs-lookup"><span data-stu-id="1905b-152">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span></span>

<span data-ttu-id="1905b-153">运行以下命令以将 DSC 配置推送到 Linux 节点。</span><span class="sxs-lookup"><span data-stu-id="1905b-153">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession $Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="1905b-154">使用请求服务器分发配置</span><span class="sxs-lookup"><span data-stu-id="1905b-154">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="1905b-155">可使用请求服务器将配置分发到 Linux 计算机，与分发到 Windows 计算机类似。</span><span class="sxs-lookup"><span data-stu-id="1905b-155">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="1905b-156">有关使用请求服务器的指南，请参阅 [Windows PowerShell Desired State Configuration 请求服务器](../pull-server/pullServer.md)。</span><span class="sxs-lookup"><span data-stu-id="1905b-156">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](../pull-server/pullServer.md).</span></span> <span data-ttu-id="1905b-157">有关通过请求服务器使用 Linux 计算机其他信息和限制条件，请参阅“适用于 Linux 的 Desired State Configuration 发行说明”。</span><span class="sxs-lookup"><span data-stu-id="1905b-157">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="1905b-158">从本地进行配置</span><span class="sxs-lookup"><span data-stu-id="1905b-158">Working with configurations locally</span></span>

<span data-ttu-id="1905b-159">适用于 Linux 的 DSC 包括用于从本地 Linux 计算机进行配置的脚本。</span><span class="sxs-lookup"><span data-stu-id="1905b-159">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="1905b-160">这些脚本位于 `/opt/microsoft/dsc/Scripts` 中，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="1905b-160">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="1905b-161">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="1905b-161">GetDscConfiguration.py</span></span>

<span data-ttu-id="1905b-162">返回应用于此计算机的当前配置。</span><span class="sxs-lookup"><span data-stu-id="1905b-162">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="1905b-163">与使用 Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet 类似。</span><span class="sxs-lookup"><span data-stu-id="1905b-163">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

`# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="1905b-164">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="1905b-164">GetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="1905b-165">返回应用于此计算机的当前元配置。</span><span class="sxs-lookup"><span data-stu-id="1905b-165">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="1905b-166">与 cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet 类似。</span><span class="sxs-lookup"><span data-stu-id="1905b-166">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

`# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="1905b-167">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="1905b-167">InstallModule.py</span></span>

<span data-ttu-id="1905b-168">安装自定义 DSC 资源模块。</span><span class="sxs-lookup"><span data-stu-id="1905b-168">Installs a custom DSC resource module.</span></span> <span data-ttu-id="1905b-169">需要包含模块共享对象库和架构 MOF 文件的 .zip 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1905b-169">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

`# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="1905b-170">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="1905b-170">RemoveModule.py</span></span>

<span data-ttu-id="1905b-171">删除自定义 DSC 资源模块。</span><span class="sxs-lookup"><span data-stu-id="1905b-171">Removes a custom DSC resource module.</span></span> <span data-ttu-id="1905b-172">需要待删除模块的名称。</span><span class="sxs-lookup"><span data-stu-id="1905b-172">Requires the name of the module to remove.</span></span>

`# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="1905b-173">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="1905b-173">StartDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="1905b-174">将配置 MOF 文件应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="1905b-174">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="1905b-175">与 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet 类似。</span><span class="sxs-lookup"><span data-stu-id="1905b-175">Similar to the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="1905b-176">需要待应用的配置 MOF 的路径。</span><span class="sxs-lookup"><span data-stu-id="1905b-176">Requires the path to the configuration MOF to apply.</span></span>

`# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="1905b-177">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="1905b-177">SetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="1905b-178">将元配置 MOF 文件应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="1905b-178">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="1905b-179">与 [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet 类似。</span><span class="sxs-lookup"><span data-stu-id="1905b-179">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="1905b-180">需要待应用的元配置 MOF 的路径。</span><span class="sxs-lookup"><span data-stu-id="1905b-180">Requires the path to the Meta Configuration MOF to apply.</span></span>

`# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="1905b-181">适用于 Linux 的 PowerShell Desired State Configuration 日志文件</span><span class="sxs-lookup"><span data-stu-id="1905b-181">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="1905b-182">为适用于 Linux 的.DSC 生成了以下日志文件。</span><span class="sxs-lookup"><span data-stu-id="1905b-182">The following log files are generated for DSC for Linux messages.</span></span>

|<span data-ttu-id="1905b-183">日志文件</span><span class="sxs-lookup"><span data-stu-id="1905b-183">Log file</span></span>|<span data-ttu-id="1905b-184">Directory</span><span class="sxs-lookup"><span data-stu-id="1905b-184">Directory</span></span>|<span data-ttu-id="1905b-185">说明</span><span class="sxs-lookup"><span data-stu-id="1905b-185">Description</span></span>|
|---|---|---|
|<span data-ttu-id="1905b-186">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="1905b-186">**omiserver.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="1905b-187">与 OMI CIM 服务器操作相关的消息。</span><span class="sxs-lookup"><span data-stu-id="1905b-187">Messages relating to the operation of the OMI CIM server.</span></span>|
|<span data-ttu-id="1905b-188">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="1905b-188">**dsc.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="1905b-189">与本地配置管理器 (LCM) 操作和 DSC 资源操作相关的消息。</span><span class="sxs-lookup"><span data-stu-id="1905b-189">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span>|
