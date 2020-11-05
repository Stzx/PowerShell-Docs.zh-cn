---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: 在 PowerShell 5.0 及更高版本中使用配置名称设置请求客户端
description: 本文介绍了如何在 PowerShell 5.0 及更高版本中使用配置名称设置拉取客户端
ms.openlocfilehash: db2b08605dd8bc7e48d9d5153861ce9b36118e21
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644909"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a><span data-ttu-id="37a79-104">在 PowerShell 5.0 及更高版本中使用配置名称设置请求客户端</span><span class="sxs-lookup"><span data-stu-id="37a79-104">Set up a Pull Client using Configuration Names in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="37a79-105">适用于：Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="37a79-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37a79-106">请求服务器（Windows 功能 DSC-Service）是 Windows Server 的一个受支持组件，不过目前没有提供新功能的计划。</span><span class="sxs-lookup"><span data-stu-id="37a79-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="37a79-107">建议开始将托管客户端转换至 [Azure Automation DSC](/azure/automation/automation-dsc-getting-started)（包括 Windows Server 上的请求服务器以外的功能）或[此处](pullserver.md#community-solutions-for-pull-service)列出的社区解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="37a79-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="37a79-108">设置请求客户端之前，应设置请求服务器。</span><span class="sxs-lookup"><span data-stu-id="37a79-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="37a79-109">虽然此顺序不是必需的，不过它帮助进行故障排除，并帮助确保注册成功。</span><span class="sxs-lookup"><span data-stu-id="37a79-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="37a79-110">若要设置请求服务器，可以使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="37a79-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="37a79-111">设置 DSC SMB 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="37a79-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="37a79-112">设置 DSC HTTP 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="37a79-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="37a79-113">每个目标节点都可以配置为下载配置、资源，甚至是报告其状态。</span><span class="sxs-lookup"><span data-stu-id="37a79-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="37a79-114">以下各部分演示如何使用 SMB 共享或 HTTP DSC 请求服务器配置请求客户端。</span><span class="sxs-lookup"><span data-stu-id="37a79-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="37a79-115">节点的 LCM 刷新时，它会访问配置的位置以下载任何已分配的配置。</span><span class="sxs-lookup"><span data-stu-id="37a79-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="37a79-116">如果有任何所需资源在节点上不存在，则它会自动从配置的位置下载它们。</span><span class="sxs-lookup"><span data-stu-id="37a79-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="37a79-117">如果使用[报表服务器](reportServer.md)配置节点，则它随后会报告操作的状态。</span><span class="sxs-lookup"><span data-stu-id="37a79-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="37a79-118">本主题适用于 PowerShell 5.0。</span><span class="sxs-lookup"><span data-stu-id="37a79-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="37a79-119">有关在 PowerShell 4.0 中设置请求客户端的信息，请参阅[在 PowerShell 4.0 中使用配置 ID 设置请求客户端](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="37a79-119">For information on setting up a pull client in PowerShell 4.0, see [Set up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="37a79-120">配置请求客户端 LCM</span><span class="sxs-lookup"><span data-stu-id="37a79-120">Configure the pull client LCM</span></span>

<span data-ttu-id="37a79-121">执行以下任何示例会创建名为 PullClientConfigName 的新输出文件夹，并在其中放入元配置 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="37a79-121">Executing any of the examples below creates a new output folder named **PullClientConfigName** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="37a79-122">在本例中，会将元配置 MOF 文件命名为 `localhost.meta.mof`。</span><span class="sxs-lookup"><span data-stu-id="37a79-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="37a79-123">若要应用配置，请调用 **Set-DscLocalConfigurationManager** cmdlet，并将 **Path** 设置为元配置 MOF 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="37a79-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="37a79-124">例如：</span><span class="sxs-lookup"><span data-stu-id="37a79-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a><span data-ttu-id="37a79-125">配置名称</span><span class="sxs-lookup"><span data-stu-id="37a79-125">Configuration Name</span></span>

<span data-ttu-id="37a79-126">以下示例将 LCM 的 ConfigurationName 属性设置为针对此用途创建的以前编译的配置名称。</span><span class="sxs-lookup"><span data-stu-id="37a79-126">The examples below sets the **ConfigurationName** property of the LCM to the name of a previously compiled Configuration, created for this purpose.</span></span> <span data-ttu-id="37a79-127">LCM 使用 ConfigurationName 在请求服务器上查找相应配置。</span><span class="sxs-lookup"><span data-stu-id="37a79-127">The **ConfigurationName** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="37a79-128">请求服务器上的配置 MOF 文件必须命名为 `<ConfigurationName>.mof`（在此例中为“ClientConfig.mof”）。</span><span class="sxs-lookup"><span data-stu-id="37a79-128">The configuration MOF file on the pull server must be named `<ConfigurationName>.mof`, in this case, "ClientConfig.mof".</span></span> <span data-ttu-id="37a79-129">有关详细信息，请参阅[将配置发布到请求服务器 (v4/v5)](publishConfigs.md)。</span><span class="sxs-lookup"><span data-stu-id="37a79-129">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="37a79-130">设置请求客户端以下载配置</span><span class="sxs-lookup"><span data-stu-id="37a79-130">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="37a79-131">必须在“请求”模式下配置每个客户端，并向其提供存储其配置的请求服务器 url。</span><span class="sxs-lookup"><span data-stu-id="37a79-131">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="37a79-132">若要执行此操作，必须为本地配置管理器 (LCM) 配置所需信息。</span><span class="sxs-lookup"><span data-stu-id="37a79-132">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="37a79-133">若要配置 LCM，可创建一个使用 **DSCLocalConfigurationManager** 特性修饰的特殊类型配置。</span><span class="sxs-lookup"><span data-stu-id="37a79-133">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="37a79-134">有关配置 LCM 的详细信息，请参阅[配置本地配置管理器](../managing-nodes/metaConfig.md)。</span><span class="sxs-lookup"><span data-stu-id="37a79-134">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="37a79-135">下面的脚本将 LCM 配置为从名为“CONTOSO-PullSrv”的服务器请求配置。</span><span class="sxs-lookup"><span data-stu-id="37a79-135">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

- <span data-ttu-id="37a79-136">在该脚本中， **ConfigurationRepositoryWeb** 块定义了请求服务器。</span><span class="sxs-lookup"><span data-stu-id="37a79-136">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="37a79-137">**ServerURL** 属性为请求服务器指定终结点。</span><span class="sxs-lookup"><span data-stu-id="37a79-137">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

- <span data-ttu-id="37a79-138">**RegistrationKey** 属性是请求服务器的所有客户端节点与该请求服务器之间的共享密钥。</span><span class="sxs-lookup"><span data-stu-id="37a79-138">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span> <span data-ttu-id="37a79-139">请求服务器上的文件中存储了相同的值。</span><span class="sxs-lookup"><span data-stu-id="37a79-139">The same value is stored in a file on the pull server.</span></span><span data-ttu-id="37a79-140"> > [!NOTE] > 注册密钥仅适用于 Web 拉取服务器。</span><span class="sxs-lookup"><span data-stu-id="37a79-140"> > [!NOTE] > Registration keys work only with **web** pull servers.</span></span> <span data-ttu-id="37a79-141">对于 SMB 请求服务器，仍必须使用 ConfigurationID 。</span><span class="sxs-lookup"><span data-stu-id="37a79-141">You must still use **ConfigurationID** with an **SMB** pull server.</span></span> <span data-ttu-id="37a79-142">> 有关使用 ConfigurationID 配置拉取服务器的信息，请参阅[使用配置 ID 设置拉取客户端](pullClientConfigId.md)</span><span class="sxs-lookup"><span data-stu-id="37a79-142">> For information about configuring a pull server by using **ConfigurationID** , see [Setting up a pull client using configuration ID](pullClientConfigId.md)</span></span>

- <span data-ttu-id="37a79-143">**ConfigurationNames** 属性是指定用于客户端节点的配置的名称的数组。</span><span class="sxs-lookup"><span data-stu-id="37a79-143">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span><span data-ttu-id="37a79-144"> >**注意：** 如果在 ConfigurationNames 中指定多个值，则必须也在你的配置中指定 PartialConfiguration 块 。</span><span class="sxs-lookup"><span data-stu-id="37a79-144"> >**Note:** If you specify more than one value in the **ConfigurationNames** , you must also specify **PartialConfiguration** blocks in your configuration.</span></span> <span data-ttu-id="37a79-145">>有关部分配置的信息，请参阅 [PowerShell Desired State Configuration 部分配置](partialConfigs.md)。</span><span class="sxs-lookup"><span data-stu-id="37a79-145">>For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
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
            ConfigurationNames = @('ClientConfig')
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="37a79-146">设置请求客户端以下载资源</span><span class="sxs-lookup"><span data-stu-id="37a79-146">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="37a79-147">如果你在 LCM 配置中只指定 ConfigurationRepositoryWeb 或 ConfigurationRepositoryShare 块（如前面的示例所示），则请求客户端会从存储“.mof”文件的相同位置请求资源。</span><span class="sxs-lookup"><span data-stu-id="37a79-147">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from same location where your ".mof" files are stored.</span></span> <span data-ttu-id="37a79-148">还可以指定客户端可以下载资源的不同位置。</span><span class="sxs-lookup"><span data-stu-id="37a79-148">You can also specify different locations where clients can download resources.</span></span> <span data-ttu-id="37a79-149">若要指定资源服务器，请使用 **ResourceRepositoryWeb** （适用于 Web 请求服务器）或 **ResourceRepositoryShare** （适用于 SMB 请求服务器）块。</span><span class="sxs-lookup"><span data-stu-id="37a79-149">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>

<span data-ttu-id="37a79-150">下面的示例演示一个元配置，它将客户端设置为从请求服务器下载配置，并从 SMB 共享下载资源。</span><span class="sxs-lookup"><span data-stu-id="37a79-150">The following example shows a metaconfiguration that sets up a client to download configurations from a Pull Server, and resources from an SMB share.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
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
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ResourceRepositoryShare SMBResources
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="37a79-151">设置请求客户端以报告状态</span><span class="sxs-lookup"><span data-stu-id="37a79-151">Set up a Pull Client to report status</span></span>

<span data-ttu-id="37a79-152">可以将单个请求服务器用于配置、资源和报告。</span><span class="sxs-lookup"><span data-stu-id="37a79-152">You can use a single pull server for configurations, resources, and reporting.</span></span> <span data-ttu-id="37a79-153">默认情况下不会为客户端配置报告。</span><span class="sxs-lookup"><span data-stu-id="37a79-153">Reporting is not configured for clients by default.</span></span> <span data-ttu-id="37a79-154">若要配置客户端以报告状态，必须创建 ReportRepositoryWeb 块。</span><span class="sxs-lookup"><span data-stu-id="37a79-154">To configure a client to report status, you have to create a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="37a79-155">下面的示例展示了将客户端设置为请求配置和资源并将报表数据发送到一个请求服务器的元配置。</span><span class="sxs-lookup"><span data-stu-id="37a79-155">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="37a79-156">报表服务器不能为 SMB 共享。</span><span class="sxs-lookup"><span data-stu-id="37a79-156">A report server cannot be an SMB share.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
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
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a><span data-ttu-id="37a79-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37a79-157">See Also</span></span>

- [<span data-ttu-id="37a79-158">使用配置 ID 设置请求客户端</span><span class="sxs-lookup"><span data-stu-id="37a79-158">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
- [<span data-ttu-id="37a79-159">设置 DSC Web 请求服务器</span><span class="sxs-lookup"><span data-stu-id="37a79-159">Setting up a DSC web pull server</span></span>](pullServer.md)
