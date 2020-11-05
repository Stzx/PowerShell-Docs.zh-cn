---
ms.date: 12/12/2018
keywords: dsc,powershell,配置,安装程序
title: 在 PowerShell 4.0 中使用配置 ID 设置拉取客户端
description: 本文介绍了如何在 PowerShell 4.0 中使用配置 ID 设置拉取客户端
ms.openlocfilehash: 2a3d7b79f29030620cddc2b2131cb4432e41e4eb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92649006"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a><span data-ttu-id="649ad-104">在 PowerShell 4.0 中使用配置 ID 设置拉取客户端</span><span class="sxs-lookup"><span data-stu-id="649ad-104">Set up a Pull Client using Configuration IDs in PowerShell 4.0</span></span>

><span data-ttu-id="649ad-105">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="649ad-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="649ad-106">请求服务器（Windows 功能 DSC-Service）是 Windows Server 的一个受支持组件，不过目前没有提供新功能的计划。</span><span class="sxs-lookup"><span data-stu-id="649ad-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="649ad-107">建议开始将托管客户端转换至 [Azure Automation DSC](/azure/automation/automation-dsc-getting-started)（包括 Windows Server 上的请求服务器以外的功能）或[此处](pullserver.md#community-solutions-for-pull-service)列出的社区解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="649ad-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="649ad-108">设置请求客户端之前，应设置请求服务器。</span><span class="sxs-lookup"><span data-stu-id="649ad-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="649ad-109">虽然此顺序不是必需的，不过它帮助进行故障排除，并帮助确保注册成功。</span><span class="sxs-lookup"><span data-stu-id="649ad-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="649ad-110">若要设置请求服务器，可以使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="649ad-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="649ad-111">设置 DSC SMB 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="649ad-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="649ad-112">设置 DSC HTTP 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="649ad-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="649ad-113">每个目标节点都可以配置为下载配置、资源，甚至是报告其状态。</span><span class="sxs-lookup"><span data-stu-id="649ad-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="649ad-114">以下各部分演示如何使用 SMB 共享或 HTTP DSC 请求服务器配置请求客户端。</span><span class="sxs-lookup"><span data-stu-id="649ad-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="649ad-115">节点的 LCM 刷新时，它会访问配置的位置以下载任何已分配的配置。</span><span class="sxs-lookup"><span data-stu-id="649ad-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="649ad-116">如果有任何所需资源在节点上不存在，则它会自动从配置的位置下载它们。</span><span class="sxs-lookup"><span data-stu-id="649ad-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="649ad-117">如果使用[报表服务器](reportServer.md)配置节点，则它随后会报告操作的状态。</span><span class="sxs-lookup"><span data-stu-id="649ad-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="649ad-118">配置请求客户端 LCM</span><span class="sxs-lookup"><span data-stu-id="649ad-118">Configure the pull client LCM</span></span>

<span data-ttu-id="649ad-119">执行以下任何示例会创建名为 PullClientConfigID 的新输出文件夹，并在其中放入元配置 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="649ad-119">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="649ad-120">在本例中，会将元配置 MOF 文件命名为 `localhost.meta.mof`。</span><span class="sxs-lookup"><span data-stu-id="649ad-120">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="649ad-121">若要应用配置，请调用 **Set-DscLocalConfigurationManager** cmdlet，并将 **Path** 设置为元配置 MOF 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="649ad-121">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="649ad-122">例如：</span><span class="sxs-lookup"><span data-stu-id="649ad-122">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="649ad-123">配置 ID</span><span class="sxs-lookup"><span data-stu-id="649ad-123">Configuration ID</span></span>

<span data-ttu-id="649ad-124">以下示例将 LCM 的 ConfigurationID 属性设置为之前为此目的创建的 Guid。</span><span class="sxs-lookup"><span data-stu-id="649ad-124">The examples below set the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="649ad-125">LCM 使用 **ConfigurationID** 在请求服务器上查找相应配置。</span><span class="sxs-lookup"><span data-stu-id="649ad-125">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="649ad-126">请求服务器上的配置 MOF 文件必须命名为 `ConfigurationID.mof`，其中 *ConfigurationID* 是目标节点上 LCM 的 **ConfigurationID** 属性值。</span><span class="sxs-lookup"><span data-stu-id="649ad-126">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="649ad-127">有关详细信息，请参阅[将配置发布到请求服务器 (v4/v5)](publishConfigs.md)。</span><span class="sxs-lookup"><span data-stu-id="649ad-127">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="649ad-128">可以使用以下示例创建随机 Guid。</span><span class="sxs-lookup"><span data-stu-id="649ad-128">You can create a random **Guid** using the example below.</span></span>

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="649ad-129">设置请求客户端以下载配置</span><span class="sxs-lookup"><span data-stu-id="649ad-129">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="649ad-130">必须在“请求”模式下配置每个客户端，并向其提供存储其配置的请求服务器 url。</span><span class="sxs-lookup"><span data-stu-id="649ad-130">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="649ad-131">若要执行此操作，必须为本地配置管理器 (LCM) 配置所需信息。</span><span class="sxs-lookup"><span data-stu-id="649ad-131">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="649ad-132">若要配置 LCM，你需要创建一个具有 LocalConfigurationManager 块的特殊类型配置。</span><span class="sxs-lookup"><span data-stu-id="649ad-132">To configure the LCM, you create a special type of configuration, with a **LocalConfigurationManager** block.</span></span> <span data-ttu-id="649ad-133">有关配置 LCM 的详细信息，请参阅[配置本地配置管理器](../managing-nodes/metaConfig4.md)。</span><span class="sxs-lookup"><span data-stu-id="649ad-133">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig4.md).</span></span>

## <a name="http-dsc-pull-server"></a><span data-ttu-id="649ad-134">HTTP DSC 请求服务器</span><span class="sxs-lookup"><span data-stu-id="649ad-134">HTTP DSC Pull Server</span></span>

<span data-ttu-id="649ad-135">如果拉取服务器被设置为 Web 服务，请将 DownloadManagerName 设置为 WebDownloadManager。</span><span class="sxs-lookup"><span data-stu-id="649ad-135">If the pull server is set up as a web service, you set the **DownloadManagerName** to **WebDownloadManager**.</span></span> <span data-ttu-id="649ad-136">WebDownloadManager 要求你指定指向 DownloadManagerCustomData 键的 ServerUrl。</span><span class="sxs-lookup"><span data-stu-id="649ad-136">The **WebDownloadManager** requires that you specify a **ServerUrl** to the **DownloadManagerCustomData** key.</span></span> <span data-ttu-id="649ad-137">还可以指定 AllowUnsecureConnection 的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="649ad-137">You can also specify a value for **AllowUnsecureConnection** , as in the example below.</span></span> <span data-ttu-id="649ad-138">下面的脚本将 LCM 配置为从名为“PullServer”的服务器请求配置。</span><span class="sxs-lookup"><span data-stu-id="649ad-138">The following script configures the LCM to pull configurations from a server named "PullServer".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = "TRUE"}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a><span data-ttu-id="649ad-139">SMB 共享</span><span class="sxs-lookup"><span data-stu-id="649ad-139">SMB Share</span></span>

<span data-ttu-id="649ad-140">如果拉取服务器被设置为 SMB 文件共享，而不是 Web 服务，请将 DownloadManagerName 设置为 DscFileDownloadManager，而不是 WebDownLoadManager。</span><span class="sxs-lookup"><span data-stu-id="649ad-140">If the pull server is set up as an SMB file share, rather than a web service, you set the **DownloadManagerName** to **DscFileDownloadManager** rather than the **WebDownLoadManager**.</span></span> <span data-ttu-id="649ad-141">DscFileDownloadManager 要求你指定 DownloadManagerCustomData 中的 SourcePath 属性。</span><span class="sxs-lookup"><span data-stu-id="649ad-141">The **DscFileDownloadManager** requires that you specify a **SourcePath** property in the **DownloadManagerCustomData**.</span></span> <span data-ttu-id="649ad-142">下面的脚本将 LCM 配置为从“CONTOSO-SERVER”服务器上的“SmbDscShare”SMB 共享请求配置。</span><span class="sxs-lookup"><span data-stu-id="649ad-142">The following script configures the LCM to pull configurations from an SMB share named "SmbDscShare" on a server named "CONTOSO-SERVER".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
PullClientConfigId -Output "."
```

## <a name="next-steps"></a><span data-ttu-id="649ad-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="649ad-143">Next Steps</span></span>

<span data-ttu-id="649ad-144">配置请求客户端之后，可以使用以下指南执行后续步骤：</span><span class="sxs-lookup"><span data-stu-id="649ad-144">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="649ad-145">将配置发布到拉取服务器 (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="649ad-145">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="649ad-146">打包资源并将其上传到拉取服务器 (v4)</span><span class="sxs-lookup"><span data-stu-id="649ad-146">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="649ad-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="649ad-147">See Also</span></span>

- [<span data-ttu-id="649ad-148">设置 DSC Web 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="649ad-148">Set up a DSC web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="649ad-149">设置 DSC SMB 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="649ad-149">Set up a DSC SMB pull server</span></span>](pullServerSMB.md)
