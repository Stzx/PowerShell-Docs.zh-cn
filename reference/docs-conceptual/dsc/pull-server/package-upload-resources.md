---
ms.date: 12/12/2018
keywords: dsc,powershell,配置,安装程序
title: 打包资源并将其上传到拉取服务器
description: 本文介绍了如何将资源上传到拉取服务器，以便可以通过由 DSC 管理的节点上的配置下载这些资源。
ms.openlocfilehash: a19d04346a0ae546cfcaf70701fde870d3839f65
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661695"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="6438e-104">打包资源并将其上传到拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6438e-104">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="6438e-105">以下部分假定你已设置拉取服务器。</span><span class="sxs-lookup"><span data-stu-id="6438e-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="6438e-106">如果尚未设置拉取服务器，则可以使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="6438e-106">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="6438e-107">设置 DSC SMB 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6438e-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="6438e-108">设置 DSC HTTP 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6438e-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="6438e-109">每个目标节点都可以配置为下载配置、资源，甚至是报告其状态。</span><span class="sxs-lookup"><span data-stu-id="6438e-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="6438e-110">本文将演示如何上传资源以便下载，以及如何将客户端配置为自动下载资源。</span><span class="sxs-lookup"><span data-stu-id="6438e-110">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="6438e-111">当节点通过“拉取”  或“推送”  (v5) 接收已分配的配置时，将从 LCM 中指定的位置自动下载配置所需的任何资源。</span><span class="sxs-lookup"><span data-stu-id="6438e-111">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="6438e-112">包资源模块</span><span class="sxs-lookup"><span data-stu-id="6438e-112">Package Resource Modules</span></span>

<span data-ttu-id="6438e-113">可供客户端下载的每个资源必须存储在 `.zip` 文件中。</span><span class="sxs-lookup"><span data-stu-id="6438e-113">Each resource available for a client to download must be stored in a `.zip` file.</span></span> <span data-ttu-id="6438e-114">下面的示例将显示使用 [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) 资源所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="6438e-114">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="6438e-115">如果有任何使用 PowerShell 4.0 的客户端，则将需要展开资源文件夹结构并删除任何版本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6438e-115">If you have any clients using PowerShell 4.0, you will need to flatten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="6438e-116">有关详细信息，请参阅[多个资源版本](../configurations/import-dscresource.md#multiple-resource-versions)。</span><span class="sxs-lookup"><span data-stu-id="6438e-116">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="6438e-117">可以使用喜欢的任何实用工具、脚本或方法压缩资源目录。</span><span class="sxs-lookup"><span data-stu-id="6438e-117">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="6438e-118">在 Windows 上，可以右键单击 `xPSDesiredStateConfiguration` 目录并选择“发送到”，然后选择“压缩文件夹” 。</span><span class="sxs-lookup"><span data-stu-id="6438e-118">In Windows, you can _right-click_ on the `xPSDesiredStateConfiguration` directory, and select **Send To** , then **Compressed Folder**.</span></span>

![右键单击 - 发送到 - 压缩文件夹](media/package-upload-resources/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="6438e-120">命名资源存档</span><span class="sxs-lookup"><span data-stu-id="6438e-120">Naming the Resource Archive</span></span>

<span data-ttu-id="6438e-121">资源存档需要采用以下格式命名：</span><span class="sxs-lookup"><span data-stu-id="6438e-121">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="6438e-122">在上面的示例中，应将 `xPSDesiredStateConfiguration.zip` 重命名为 `xPSDesiredStateConfiguration_8.4.4.0.zip`。</span><span class="sxs-lookup"><span data-stu-id="6438e-122">In the example above, `xPSDesiredStateConfiguration.zip` should be renamed `xPSDesiredStateConfiguration_8.4.4.0.zip`.</span></span>

### <a name="create-checksums"></a><span data-ttu-id="6438e-123">创建校验和</span><span class="sxs-lookup"><span data-stu-id="6438e-123">Create CheckSums</span></span>

<span data-ttu-id="6438e-124">压缩并重命名资源模块后，需要创建校验和  。</span><span class="sxs-lookup"><span data-stu-id="6438e-124">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span> <span data-ttu-id="6438e-125">客户端上的 LCM 使用校验和  来确定该资源是否已更改，以及是否需要重新下载。</span><span class="sxs-lookup"><span data-stu-id="6438e-125">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="6438e-126">可以使用 [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet 创建校验和，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="6438e-126">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="6438e-127">不会显示任何输出，但现在应看到“xPSDesiredStateConfiguration_8.4.4.0.zip.checksum”。</span><span class="sxs-lookup"><span data-stu-id="6438e-127">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="6438e-128">也可以使用 `-Path` 参数对文件的目录运行 `New-DSCCheckSum`。</span><span class="sxs-lookup"><span data-stu-id="6438e-128">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="6438e-129">如果校验和已存在，则可以强制使用 `-Force` 参数重新创建校验和。</span><span class="sxs-lookup"><span data-stu-id="6438e-129">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="6438e-130">存储资源存档的位置</span><span class="sxs-lookup"><span data-stu-id="6438e-130">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="6438e-131">在 DSC HTTP 拉取服务器上</span><span class="sxs-lookup"><span data-stu-id="6438e-131">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="6438e-132">当按照[设置 DSC HTTP 拉取服务器](pullServer.md)中所述设置 HTTP 拉取服务器时，指定 ModulePath  和 ConfigurationPath  键的目录。</span><span class="sxs-lookup"><span data-stu-id="6438e-132">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="6438e-133">ConfigurationPath  键指示应存储任何“.mof”文件的位置。</span><span class="sxs-lookup"><span data-stu-id="6438e-133">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="6438e-134">ModulePath  键指示应存储任何 DSC 资源模块的位置。</span><span class="sxs-lookup"><span data-stu-id="6438e-134">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="6438e-135">在 SMB 共享上</span><span class="sxs-lookup"><span data-stu-id="6438e-135">On an SMB Share</span></span>

<span data-ttu-id="6438e-136">如果在设置拉取客户端时指定了 ResourceRepositoryShare，则将存档和校验和存储在 ResourceRepositoryShare 块的 SourcePath 目录中。</span><span class="sxs-lookup"><span data-stu-id="6438e-136">If you specified a **ResourceRepositoryShare** , when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

<span data-ttu-id="6438e-137">如果在设置拉取客户端时仅指定了 ConfigurationRepositoryShare，则将存档和校验和存储在 ConfigurationRepositoryShare 块的 SourcePath 目录中。</span><span class="sxs-lookup"><span data-stu-id="6438e-137">If you specified only a **ConfigurationRepositoryShare** , when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="6438e-138">正在更新资源</span><span class="sxs-lookup"><span data-stu-id="6438e-138">Updating resources</span></span>

<span data-ttu-id="6438e-139">可以强制节点通过更改存档名称中的版本号或创建新的校验和来更新其资源。</span><span class="sxs-lookup"><span data-stu-id="6438e-139">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="6438e-140">拉取客户端将在 LCM 刷新后检查所需资源的较新版本，以及更新的校验和。</span><span class="sxs-lookup"><span data-stu-id="6438e-140">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="6438e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6438e-141">See also</span></span>

- [<span data-ttu-id="6438e-142">设置 DSC SMB 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6438e-142">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="6438e-143">设置 DSC HTTP 拉取服务器</span><span class="sxs-lookup"><span data-stu-id="6438e-143">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
