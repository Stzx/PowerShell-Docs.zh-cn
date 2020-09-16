---
ms.date: 08/15/2019
keywords: dsc,powershell,配置,安装程序
title: 适用于 Windows 的 Desired State Configuration (DSC) 入门
ms.openlocfilehash: 00e1cf545b19f054b4b1ff468c9f6ad94e5cef55
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236316"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="c3761-103">适用于 Windows 的 Desired State Configuration (DSC) 入门</span><span class="sxs-lookup"><span data-stu-id="c3761-103">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="c3761-104">本主题介绍了如何开始使用适用于 Windows 的 PowerShell Desired State Configuration (DSC)。</span><span class="sxs-lookup"><span data-stu-id="c3761-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span>
<span data-ttu-id="c3761-105">有关 DSC 的常规信息，请参阅 [Windows PowerShell Desired State Configuration 入门](../overview/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3761-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="c3761-106">支持的 Windows 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="c3761-106">Supported Windows operation system versions</span></span>

<span data-ttu-id="c3761-107">支持以下版本：</span><span class="sxs-lookup"><span data-stu-id="c3761-107">The following versions are supported:</span></span>

- <span data-ttu-id="c3761-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c3761-108">Windows Server 2019</span></span>
- <span data-ttu-id="c3761-109">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c3761-109">Windows Server 2016</span></span>
- <span data-ttu-id="c3761-110">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="c3761-110">Windows Server 2012R2</span></span>
- <span data-ttu-id="c3761-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c3761-111">Windows Server 2012</span></span>
- <span data-ttu-id="c3761-112">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c3761-112">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="c3761-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3761-113">Windows 10</span></span>
- <span data-ttu-id="c3761-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c3761-114">Windows 8.1</span></span>
- <span data-ttu-id="c3761-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c3761-115">Windows 7</span></span>

<span data-ttu-id="c3761-116">由于 [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) 独立产品 SKU 不包含 Desired State Configuraion 实现，因此无法由 PowerShell DSC 或 Azure Automation State Configuration 管理。</span><span class="sxs-lookup"><span data-stu-id="c3761-116">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku doesn't contain an implementation of Desired State Configuration so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="c3761-117">安装 DSC</span><span class="sxs-lookup"><span data-stu-id="c3761-117">Installing DSC</span></span>

<span data-ttu-id="c3761-118">PowerShell Desired State Configuration 包含在 Windows 中，并通过 Windows Management Framework 进行更新。</span><span class="sxs-lookup"><span data-stu-id="c3761-118">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span> <span data-ttu-id="c3761-119">最新版本为 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)。</span><span class="sxs-lookup"><span data-stu-id="c3761-119">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="c3761-120">无需启用 Windows Server 功能“DSC 服务”，即可使用 DSC 管理计算机。</span><span class="sxs-lookup"><span data-stu-id="c3761-120">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="c3761-121">只有在生成 Windows 拉取服务器实例时，才需要此功能。</span><span class="sxs-lookup"><span data-stu-id="c3761-121">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="c3761-122">使用适用于 Windows 的 DSC</span><span class="sxs-lookup"><span data-stu-id="c3761-122">Using DSC for Windows</span></span>

<span data-ttu-id="c3761-123">下面几个部分介绍了如何在 Windows 计算机上创建和运行 DSC 配置。</span><span class="sxs-lookup"><span data-stu-id="c3761-123">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="c3761-124">创建配置 MOF 文档</span><span class="sxs-lookup"><span data-stu-id="c3761-124">Creating a configuration MOF document</span></span>

<span data-ttu-id="c3761-125">Windows PowerShell `Configuration` 关键字用于创建配置。</span><span class="sxs-lookup"><span data-stu-id="c3761-125">The Windows PowerShell `Configuration` keyword is used to create a configuration.</span></span>
<span data-ttu-id="c3761-126">下面逐步介绍了如何使用 Windows PowerShell 创建配置文档。</span><span class="sxs-lookup"><span data-stu-id="c3761-126">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="c3761-127">定义配置并生成配置文档：</span><span class="sxs-lookup"><span data-stu-id="c3761-127">Define a configuration and generate the configuration document:</span></span>

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```

#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="c3761-128">安装包含 DSC 资源的模块</span><span class="sxs-lookup"><span data-stu-id="c3761-128">Install a module containing DSC resources</span></span>

<span data-ttu-id="c3761-129">Windows PowerShell Desired State Configuration 有包含 DSC 资源的内置模块。</span><span class="sxs-lookup"><span data-stu-id="c3761-129">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="c3761-130">也可以使用 PowerShellGet cmdlet 从 PowerShell 库等外部源加载模块。</span><span class="sxs-lookup"><span data-stu-id="c3761-130">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="c3761-131">将配置应用于计算机</span><span class="sxs-lookup"><span data-stu-id="c3761-131">Apply the configuration to the machine</span></span>

> [!NOTE]
> <span data-ttu-id="c3761-132">即使在运行 `localhost` 配置的情况下，也需要将 Windows 配置为接收 PowerShell 远程命令，以允许 DSC 运行。</span><span class="sxs-lookup"><span data-stu-id="c3761-132">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="c3761-133">在提升的 PowerShell 终端中运行 `Set-WsManQuickConfig -Force`，即可轻松地正确配置环境。</span><span class="sxs-lookup"><span data-stu-id="c3761-133">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="c3761-134">可以使用 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet，将配置文档（MOF 文件）应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="c3761-134">Configuration documents (MOF files) can be applied to the machineusing the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="c3761-135">获取配置的当前状态</span><span class="sxs-lookup"><span data-stu-id="c3761-135">Get the current state of the configuration</span></span>

<span data-ttu-id="c3761-136">[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet 可查询计算机的当前状态，并返回配置的当前值。</span><span class="sxs-lookup"><span data-stu-id="c3761-136">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

```powershell
Get-DscConfiguration
```

<span data-ttu-id="c3761-137">[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet 可返回应用于计算机的当前元配置。</span><span class="sxs-lookup"><span data-stu-id="c3761-137">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="c3761-138">从计算机中删除当前配置</span><span class="sxs-lookup"><span data-stu-id="c3761-138">Remove the current configuration from a machine</span></span>

<span data-ttu-id="c3761-139">[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span><span class="sxs-lookup"><span data-stu-id="c3761-139">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="c3761-140">在本地配置管理器中配置设置</span><span class="sxs-lookup"><span data-stu-id="c3761-140">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="c3761-141">使用 [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet 将元配置 MOF 文件应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="c3761-141">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span>
<span data-ttu-id="c3761-142">需要元配置 MOF 的路径。</span><span class="sxs-lookup"><span data-stu-id="c3761-142">Requires the path to the Meta Configuration MOF.</span></span>

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="c3761-143">Windows PowerShell Desired State Configuration 日志文件</span><span class="sxs-lookup"><span data-stu-id="c3761-143">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="c3761-144">DSC 日志写入 Windows 事件日志，路径为 `Microsoft-Windows-Dsc/Operational`。</span><span class="sxs-lookup"><span data-stu-id="c3761-144">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="c3761-145">可以按照 [DSC 事件日志位置](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)中的步骤操作，启用其他日志用于调试目的。</span><span class="sxs-lookup"><span data-stu-id="c3761-145">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
