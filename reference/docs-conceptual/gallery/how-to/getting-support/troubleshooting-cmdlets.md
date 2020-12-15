---
ms.date: 12/01/2020
title: cmdlet 故障排除
description: 本文提供了有关使用 PowerShell 库排查错误的信息和步骤
ms.openlocfilehash: 980da8ea7b8a09513f33a9939d512c437b755d8d
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913312"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="f9da9-103">cmdlet 故障排除</span><span class="sxs-lookup"><span data-stu-id="f9da9-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="f9da9-104">如何解决“警告：无法下载包‘你的包名称’”问题</span><span class="sxs-lookup"><span data-stu-id="f9da9-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="f9da9-105">收到 `Install-Module` 或 `Update-Module` 有时在某些计算机上失败的报告。</span><span class="sxs-lookup"><span data-stu-id="f9da9-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="f9da9-106">根据我们的调查，此问题与网络连接有关。</span><span class="sxs-lookup"><span data-stu-id="f9da9-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="f9da9-107">最近，我们更新了 NuGet 提供程序，使其可以可靠地下载包。</span><span class="sxs-lookup"><span data-stu-id="f9da9-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="f9da9-108">你可以按照以下说明安装 NuGet 提供程序的最新版本，然后安装或更新你的模块。</span><span class="sxs-lookup"><span data-stu-id="f9da9-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="f9da9-109">下面，我们使用“Azure”模块作为示例。</span><span class="sxs-lookup"><span data-stu-id="f9da9-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="f9da9-110">所需的网络终结点</span><span class="sxs-lookup"><span data-stu-id="f9da9-110">Required network endpoints</span></span>

<span data-ttu-id="f9da9-111">安装和更新 cmdlet 需要通过 Internet 访问连接 PowerShell 库使用的网络终结点。</span><span class="sxs-lookup"><span data-stu-id="f9da9-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="f9da9-112">请确保网络访问策略允许连接以下终结点。</span><span class="sxs-lookup"><span data-stu-id="f9da9-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="f9da9-113">`psg-prod-eastus.azureedge.net` - CDN 主机名</span><span class="sxs-lookup"><span data-stu-id="f9da9-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="f9da9-114">`az818661.vo.msecnd.net` - CDN 主机名</span><span class="sxs-lookup"><span data-stu-id="f9da9-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="f9da9-115">`devopsgallerystorage.blob.core.windows.net` - 存储帐户主机名</span><span class="sxs-lookup"><span data-stu-id="f9da9-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="f9da9-116">`*.powershellgallery.com` - 网站</span><span class="sxs-lookup"><span data-stu-id="f9da9-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="f9da9-117">`go.microsoft.com` - 重定向服务</span><span class="sxs-lookup"><span data-stu-id="f9da9-117">`go.microsoft.com` - redirection service</span></span>

> [!NOTE]
> <span data-ttu-id="f9da9-118">当 PowerShell 库服务发生中断时，与 PowerShell 库进行交互的 cmdlet 可能会失败，并出现意外错误。</span><span class="sxs-lookup"><span data-stu-id="f9da9-118">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="f9da9-119">若要查看 PowerShell 库的当前状态，请参阅 GitHub 上的 [PowerShell 库状态](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md)页面。</span><span class="sxs-lookup"><span data-stu-id="f9da9-119">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
