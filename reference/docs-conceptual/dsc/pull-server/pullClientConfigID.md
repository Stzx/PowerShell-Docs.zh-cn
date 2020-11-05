---
ms.date: 12/12/2018
keywords: dsc,powershell,配置,安装程序
title: 在 PowerShell 5.0 及更高版本中使用配置 ID 设置请求客户端
description: 本文介绍了如何在 PowerShell 5.0 及更高版本中使用配置 ID 设置拉取客户端
ms.openlocfilehash: 601858c08ce9a893a8941823d27fef3a60882b48
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664314"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a><span data-ttu-id="6b1fd-104">在 PowerShell 5.0 及更高版本中使用配置 ID 设置请求客户端</span><span class="sxs-lookup"><span data-stu-id="6b1fd-104">Set up a Pull Client using Configuration IDs in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="6b1fd-105">适用于：Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6b1fd-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b1fd-106">请求服务器（Windows 功能 DSC-Service）是 Windows Server 的一个受支持组件，不过目前没有提供新功能的计划。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="6b1fd-107">建议开始将托管客户端转换至 [Azure Automation DSC](/azure/automation/automation-dsc-getting-started)（包括 Windows Server 上的请求服务器以外的功能）或[此处](pullserver.md#community-solutions-for-pull-service)列出的社区解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="6b1fd-108">设置请求客户端之前，应设置请求服务器。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="6b1fd-109">虽然此顺序不是必需的，不过它帮助进行故障排除，并帮助确保注册成功。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="6b1fd-110">若要设置请求服务器，可以使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="6b1fd-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="6b1fd-111">设置 DSC SMB 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6b1fd-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="6b1fd-112">设置 DSC HTTP 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6b1fd-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="6b1fd-113">每个目标节点都可以配置为下载配置、资源，甚至是报告其状态。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="6b1fd-114">以下各部分演示如何使用 SMB 共享或 HTTP DSC 请求服务器配置请求客户端。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="6b1fd-115">节点的 LCM 刷新时，它会访问配置的位置以下载任何已分配的配置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="6b1fd-116">如果有任何所需资源在节点上不存在，则它会自动从配置的位置下载它们。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="6b1fd-117">如果使用[报表服务器](reportServer.md)配置节点，则它随后会报告操作的状态。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1fd-118">本主题适用于 PowerShell 5.0。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="6b1fd-119">有关在 PowerShell 4.0 中设置请求客户端的信息，请参阅[在 PowerShell 4.0 中使用配置 ID 设置请求客户端](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="6b1fd-119">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="6b1fd-120">配置请求客户端 LCM</span><span class="sxs-lookup"><span data-stu-id="6b1fd-120">Configure the pull client LCM</span></span>

<span data-ttu-id="6b1fd-121">执行以下任何示例会创建名为 PullClientConfigID 的新输出文件夹，并在其中放入元配置 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-121">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="6b1fd-122">在本例中，会将元配置 MOF 文件命名为 `localhost.meta.mof`。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="6b1fd-123">若要应用配置，请调用 **Set-DscLocalConfigurationManager** cmdlet，并将 **Path** 设置为元配置 MOF 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="6b1fd-124">例如：</span><span class="sxs-lookup"><span data-stu-id="6b1fd-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="6b1fd-125">配置 ID</span><span class="sxs-lookup"><span data-stu-id="6b1fd-125">Configuration ID</span></span>

<span data-ttu-id="6b1fd-126">以下示例将 LCM 的 ConfigurationID 属性设置为之前为此目的创建的 Guid。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-126">The examples below sets the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="6b1fd-127">LCM 使用 **ConfigurationID** 在请求服务器上查找相应配置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-127">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="6b1fd-128">请求服务器上的配置 MOF 文件必须命名为 `ConfigurationID.mof`，其中 *ConfigurationID* 是目标节点上 LCM 的 **ConfigurationID** 属性值。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-128">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="6b1fd-129">有关详细信息，请参阅[将配置发布到请求服务器 (v4/v5)](publishConfigs.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-129">For more information see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="6b1fd-130">可以使用以下示例，或使用 [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet 创建随机 Guid。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-130">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="6b1fd-131">有关在环境中使用 Guid 的详细信息，请参阅[规划 Guid](secureserver.md#guids)。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-131">For more information about using **Guids** in your environment, see [Plan for Guids](secureserver.md#guids).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="6b1fd-132">设置请求客户端以下载配置</span><span class="sxs-lookup"><span data-stu-id="6b1fd-132">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="6b1fd-133">必须在“请求”模式下配置每个客户端，并向其提供存储其配置的请求服务器 url。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-133">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="6b1fd-134">若要执行此操作，必须为本地配置管理器 (LCM) 配置所需信息。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-134">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="6b1fd-135">若要配置 LCM，可创建一个使用 **DSCLocalConfigurationManager** 特性修饰的特殊类型配置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-135">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="6b1fd-136">有关配置 LCM 的详细信息，请参阅[配置本地配置管理器](../managing-nodes/metaConfig.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-136">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="6b1fd-137">HTTP DSC 请求服务器</span><span class="sxs-lookup"><span data-stu-id="6b1fd-137">HTTP DSC Pull Server</span></span>

<span data-ttu-id="6b1fd-138">下面的脚本将 LCM 配置为从名为“CONTOSO-PullSrv”的服务器请求配置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-138">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }
    }
}
PullClientConfigID
```

<span data-ttu-id="6b1fd-139">在该脚本中， **ConfigurationRepositoryWeb** 块定义了请求服务器。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-139">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="6b1fd-140">ServerUrl 指定 DSC 请求的 url</span><span class="sxs-lookup"><span data-stu-id="6b1fd-140">The **ServerUrl** specifies the url of the DSC Pull</span></span>

### <a name="smb-share"></a><span data-ttu-id="6b1fd-141">SMB 共享</span><span class="sxs-lookup"><span data-stu-id="6b1fd-141">SMB Share</span></span>

<span data-ttu-id="6b1fd-142">下面的脚本将 LCM 配置为从 SMB 共享 `\\SMBPullServer\Pull` 请求配置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-142">The following script configures the LCM to pull configurations from the SMB Share `\\SMBPullServer\Pull`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Pull'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="6b1fd-143">在该脚本中，ConfigurationRepositoryShare 块定义请求服务器（在此例中只是 SMB 共享）。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-143">In the script, the **ConfigurationRepositoryShare** block defines the pull server, which in this case, is just an SMB share.</span></span>

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="6b1fd-144">设置请求客户端以下载资源</span><span class="sxs-lookup"><span data-stu-id="6b1fd-144">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="6b1fd-145">如果你在 LCM 配置中只指定 ConfigurationRepositoryWeb 或 ConfigurationRepositoryShare 块（如前面的示例所示），则请求客户端会从用于检索配置的相同位置请求资源。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-145">If you specify only the **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous examples), the pull client will pull resources from the same location it retrieves its configurations.</span></span> <span data-ttu-id="6b1fd-146">还可以为资源指定不同的位置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-146">You can also specify separate locations for resources.</span></span> <span data-ttu-id="6b1fd-147">若要将资源位置指定为单独的服务器，请使用 ResourceRepositoryWeb 块。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-147">To specify a resource location as a separate server, use the **ResourceRepositoryWeb** block.</span></span> <span data-ttu-id="6b1fd-148">若要将资源位置指定为 SMB 共享，请使用 ResourceRepositoryShare 块。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-148">To specify a resource location as an SMB share, use the **ResourceRepositoryShare** block.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1fd-149">可以将 ConfigurationRepositoryWeb 与 ResourceRepositoryShare，或是 ConfigurationRepositoryShare 与 ResourceRepositoryWeb 组合使用。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-149">You can combine **ConfigurationRepositoryWeb** with **ResourceRepositoryShare** or **ConfigurationRepositoryShare** with **ResourceRepositoryWeb**.</span></span> <span data-ttu-id="6b1fd-150">下面未显示这类用法的示例。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-150">Examples of this are not shown below.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="6b1fd-151">HTTP DSC 请求服务器</span><span class="sxs-lookup"><span data-stu-id="6b1fd-151">HTTP DSC Pull Server</span></span>

<span data-ttu-id="6b1fd-152">以下元配置将请求客户端配置为从 CONTOSO-PullSrv 获取其配置，并从 CONTOSO-ResourceSrv 获取其资源。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-152">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="6b1fd-153">SMB 共享</span><span class="sxs-lookup"><span data-stu-id="6b1fd-153">SMB Share</span></span>

<span data-ttu-id="6b1fd-154">下面的示例演示一个元配置，它将客户端设置为从 SMB 共享 `\\SMBPullServer\Configurations` 请求配置，并从 SMB 共享 `\\SMBPullServer\Resources` 请求资源。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-154">The following example shows a metaconfiguration that sets up a client to pull configurations from the SMB share `\\SMBPullServer\Configurations`, and resources from the SMB share `\\SMBPullServer\Resources`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Configurations'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

#### <a name="automatically-download-resources-in-push-mode"></a><span data-ttu-id="6b1fd-155">在推送模式下自动下载资源</span><span class="sxs-lookup"><span data-stu-id="6b1fd-155">Automatically download Resources in Push Mode</span></span>

<span data-ttu-id="6b1fd-156">从 PowerShell 5.0 开始，请求客户端可以从 SMB 共享下载模块，即使是针对推送模式进行配置也是如此。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-156">Beginning in PowerShell 5.0, your pull clients can download modules from an SMB share, even when they are configured for **Push** mode.</span></span> <span data-ttu-id="6b1fd-157">这在不想设置请求服务器的情形中特别有用。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-157">This is especially useful in scenarios where you do not want to set up a Pull Server.</span></span> <span data-ttu-id="6b1fd-158">ResourceRepositoryShare 块可以在不指定 ConfigurationRepositoryShare 的情况下进行使用。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-158">The **ResourceRepositoryShare** block can be used without specifying a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="6b1fd-159">下面的示例演示一个元配置，它将客户端设置为从 SMB 共享 `\\SMBPullServer\Resources` 请求资源。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-159">The following example shows a metaconfiguration that sets up a client to pull resources from an SMB Share `\\SMBPullServer\Resources`.</span></span> <span data-ttu-id="6b1fd-160">向节点推送配置时，它会从指定共享自动下载任何所需资源。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-160">When the Node is **PUSHED** a configuration, it will automatically download any required resources, from the share specified.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Push'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="6b1fd-161">设置请求客户端以报告状态</span><span class="sxs-lookup"><span data-stu-id="6b1fd-161">Set up a Pull Client to report status</span></span>

<span data-ttu-id="6b1fd-162">默认情况下，节点不会向已配置的请求服务器发送报告。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-162">By default, Nodes will not send reports to a configured Pull Server.</span></span> <span data-ttu-id="6b1fd-163">虽然你可以将一个请求服务器用于配置、资源和报告，但必须创建 **ReportRepositoryWeb** 块来设置报表。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-163">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="6b1fd-164">HTTP DSC 请求服务器</span><span class="sxs-lookup"><span data-stu-id="6b1fd-164">HTTP DSC Pull Server</span></span>

<span data-ttu-id="6b1fd-165">下面的示例展示了将客户端设置为请求配置和资源并将报表数据发送到一个请求服务器的元配置。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-165">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="6b1fd-166">若要指定报表服务器，请使用 **ReportRepositoryWeb** 块。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-166">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="6b1fd-167">报表服务器不能为 SMB 服务器。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-167">A report server cannot be an SMB server.</span></span> <span data-ttu-id="6b1fd-168">以下元配置将请求客户端配置为从 **CONTOSO-PullSrv** 获取其配置、从 **CONTOSO-ResourceSrv** 获取资源、将状态报告发送到 **CONTOSO-ReportSrv** ：</span><span class="sxs-lookup"><span data-stu-id="6b1fd-168">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv** , and to send status reports to **CONTOSO-ReportSrv** :</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="6b1fd-169">SMB 共享</span><span class="sxs-lookup"><span data-stu-id="6b1fd-169">SMB Share</span></span>

<span data-ttu-id="6b1fd-170">报表服务器不能为 SMB 共享。</span><span class="sxs-lookup"><span data-stu-id="6b1fd-170">A report server cannot be an SMB share.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b1fd-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b1fd-171">Next Steps</span></span>

<span data-ttu-id="6b1fd-172">配置请求客户端之后，可以使用以下指南执行后续步骤：</span><span class="sxs-lookup"><span data-stu-id="6b1fd-172">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="6b1fd-173">将配置发布到拉取服务器 (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="6b1fd-173">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="6b1fd-174">打包资源并将其上传到拉取服务器 (v4)</span><span class="sxs-lookup"><span data-stu-id="6b1fd-174">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="6b1fd-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b1fd-175">See Also</span></span>

- [<span data-ttu-id="6b1fd-176">使用配置名称设置请求客户端</span><span class="sxs-lookup"><span data-stu-id="6b1fd-176">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)
