---
ms.date: 08/15/2019
keywords: dsc,powershell,配置,安装程序
title: 适用于 Windows 的 Desired State Configuration (DSC) 入门
description: 本主题介绍了如何开始使用适用于 Windows 的 PowerShell Desired State Configuration (DSC)。
ms.openlocfilehash: 2b9ddba2023a3933e3ad70d7bfee798ff07f0484
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662817"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="993f2-104">适用于 Windows 的 Desired State Configuration (DSC) 入门</span><span class="sxs-lookup"><span data-stu-id="993f2-104">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="993f2-105">本主题介绍了如何开始使用适用于 Windows 的 PowerShell Desired State Configuration (DSC)。</span><span class="sxs-lookup"><span data-stu-id="993f2-105">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span> <span data-ttu-id="993f2-106">有关 DSC 的常规信息，请参阅 [Windows PowerShell Desired State Configuration 入门](../overview/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="993f2-106">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="993f2-107">支持的 Windows 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="993f2-107">Supported Windows operation system versions</span></span>

<span data-ttu-id="993f2-108">支持以下版本：</span><span class="sxs-lookup"><span data-stu-id="993f2-108">The following versions are supported:</span></span>

- <span data-ttu-id="993f2-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="993f2-109">Windows Server 2019</span></span>
- <span data-ttu-id="993f2-110">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="993f2-110">Windows Server 2016</span></span>
- <span data-ttu-id="993f2-111">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="993f2-111">Windows Server 2012R2</span></span>
- <span data-ttu-id="993f2-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="993f2-112">Windows Server 2012</span></span>
- <span data-ttu-id="993f2-113">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="993f2-113">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="993f2-114">Windows 10</span><span class="sxs-lookup"><span data-stu-id="993f2-114">Windows 10</span></span>
- <span data-ttu-id="993f2-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="993f2-115">Windows 8.1</span></span>
- <span data-ttu-id="993f2-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="993f2-116">Windows 7</span></span>

<span data-ttu-id="993f2-117">由于 [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) 独立产品 SKU 不包含 Desired State Configuraion 实现，因此无法由 PowerShell DSC 或 Azure Automation State Configuration 管理。</span><span class="sxs-lookup"><span data-stu-id="993f2-117">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku doesn't contain an implementation of Desired State Configuration so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="993f2-118">安装 DSC</span><span class="sxs-lookup"><span data-stu-id="993f2-118">Installing DSC</span></span>

<span data-ttu-id="993f2-119">PowerShell Desired State Configuration 包含在 Windows 中，并通过 Windows Management Framework 进行更新。</span><span class="sxs-lookup"><span data-stu-id="993f2-119">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span> <span data-ttu-id="993f2-120">最新版本为 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)。</span><span class="sxs-lookup"><span data-stu-id="993f2-120">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="993f2-121">无需启用 Windows Server 功能“DSC 服务”，即可使用 DSC 管理计算机。</span><span class="sxs-lookup"><span data-stu-id="993f2-121">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="993f2-122">只有在生成 Windows 拉取服务器实例时，才需要此功能。</span><span class="sxs-lookup"><span data-stu-id="993f2-122">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="993f2-123">使用适用于 Windows 的 DSC</span><span class="sxs-lookup"><span data-stu-id="993f2-123">Using DSC for Windows</span></span>

<span data-ttu-id="993f2-124">下面几个部分介绍了如何在 Windows 计算机上创建和运行 DSC 配置。</span><span class="sxs-lookup"><span data-stu-id="993f2-124">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="993f2-125">创建配置 MOF 文档</span><span class="sxs-lookup"><span data-stu-id="993f2-125">Creating a configuration MOF document</span></span>

<span data-ttu-id="993f2-126">Windows PowerShell `Configuration` 关键字用于创建配置。</span><span class="sxs-lookup"><span data-stu-id="993f2-126">The Windows PowerShell `Configuration` keyword is used to create a configuration.</span></span>
<span data-ttu-id="993f2-127">下面逐步介绍了如何使用 Windows PowerShell 创建配置文档。</span><span class="sxs-lookup"><span data-stu-id="993f2-127">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="993f2-128">定义配置并生成配置文档：</span><span class="sxs-lookup"><span data-stu-id="993f2-128">Define a configuration and generate the configuration document:</span></span>

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

#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="993f2-129">安装包含 DSC 资源的模块</span><span class="sxs-lookup"><span data-stu-id="993f2-129">Install a module containing DSC resources</span></span>

<span data-ttu-id="993f2-130">Windows PowerShell Desired State Configuration 有包含 DSC 资源的内置模块。</span><span class="sxs-lookup"><span data-stu-id="993f2-130">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="993f2-131">也可以使用 PowerShellGet cmdlet 从 PowerShell 库等外部源加载模块。</span><span class="sxs-lookup"><span data-stu-id="993f2-131">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="993f2-132">将配置应用于计算机</span><span class="sxs-lookup"><span data-stu-id="993f2-132">Apply the configuration to the machine</span></span>

> [!NOTE]
> <span data-ttu-id="993f2-133">即使在运行 `localhost` 配置的情况下，也需要将 Windows 配置为接收 PowerShell 远程命令，以允许 DSC 运行。</span><span class="sxs-lookup"><span data-stu-id="993f2-133">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="993f2-134">在提升的 PowerShell 终端中运行 `Set-WsManQuickConfig -Force`，即可轻松地正确配置环境。</span><span class="sxs-lookup"><span data-stu-id="993f2-134">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="993f2-135">可以使用 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet，将配置文档（MOF 文件）应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="993f2-135">Configuration documents (MOF files) can be applied to the machineusing the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="993f2-136">获取配置的当前状态</span><span class="sxs-lookup"><span data-stu-id="993f2-136">Get the current state of the configuration</span></span>

<span data-ttu-id="993f2-137">[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet 可查询计算机的当前状态，并返回配置的当前值。</span><span class="sxs-lookup"><span data-stu-id="993f2-137">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

```powershell
Get-DscConfiguration
```

<span data-ttu-id="993f2-138">[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet 可返回应用于计算机的当前元配置。</span><span class="sxs-lookup"><span data-stu-id="993f2-138">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="993f2-139">从计算机中删除当前配置</span><span class="sxs-lookup"><span data-stu-id="993f2-139">Remove the current configuration from a machine</span></span>

<span data-ttu-id="993f2-140">[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span><span class="sxs-lookup"><span data-stu-id="993f2-140">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="993f2-141">在本地配置管理器中配置设置</span><span class="sxs-lookup"><span data-stu-id="993f2-141">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="993f2-142">使用 [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet 将元配置 MOF 文件应用于计算机。</span><span class="sxs-lookup"><span data-stu-id="993f2-142">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="993f2-143">需要元配置 MOF 的路径。</span><span class="sxs-lookup"><span data-stu-id="993f2-143">Requires the path to the Meta Configuration MOF.</span></span>

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="993f2-144">Windows PowerShell Desired State Configuration 日志文件</span><span class="sxs-lookup"><span data-stu-id="993f2-144">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="993f2-145">DSC 日志写入 Windows 事件日志，路径为 `Microsoft-Windows-Dsc/Operational`。</span><span class="sxs-lookup"><span data-stu-id="993f2-145">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="993f2-146">可以按照 [DSC 事件日志位置](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)中的步骤操作，启用其他日志用于调试目的。</span><span class="sxs-lookup"><span data-stu-id="993f2-146">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
