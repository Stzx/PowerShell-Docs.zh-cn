---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 88dcb47bee268af3553bb797aaa264e27ed8c51c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889634"
---
# <span data-ttu-id="9602d-103">PackageManagement 模块</span><span class="sxs-lookup"><span data-stu-id="9602d-103">PackageManagement Module</span></span>

## <span data-ttu-id="9602d-104">描述</span><span class="sxs-lookup"><span data-stu-id="9602d-104">Description</span></span>

<span data-ttu-id="9602d-105">本主题显示包管理 Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="9602d-105">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9602d-106">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="9602d-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="9602d-107">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="9602d-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="9602d-108">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="9602d-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="9602d-109">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="9602d-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="9602d-110">PackageManagement Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9602d-110">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="9602d-111">Find-Package</span><span class="sxs-lookup"><span data-stu-id="9602d-111">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="9602d-112">在可用包源中查找软件包。</span><span class="sxs-lookup"><span data-stu-id="9602d-112">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="9602d-113">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="9602d-113">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="9602d-114">返回可供安装的包管理包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="9602d-114">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="9602d-115">Get-Package</span><span class="sxs-lookup"><span data-stu-id="9602d-115">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="9602d-116">返回使用 **PackageManagement** 安装的所有软件包的列表。</span><span class="sxs-lookup"><span data-stu-id="9602d-116">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="9602d-117">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="9602d-117">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="9602d-118">返回连接到包管理的包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="9602d-118">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="9602d-119">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9602d-119">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="9602d-120">获取为包提供程序注册的包源的列表。</span><span class="sxs-lookup"><span data-stu-id="9602d-120">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="9602d-121">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="9602d-121">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="9602d-122">将包管理包提供程序添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9602d-122">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="9602d-123">Install-Package</span><span class="sxs-lookup"><span data-stu-id="9602d-123">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="9602d-124">安装一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="9602d-124">Installs one or more software packages.</span></span>

### [<span data-ttu-id="9602d-125">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="9602d-125">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="9602d-126">安装一个或多个包管理包提供程序。</span><span class="sxs-lookup"><span data-stu-id="9602d-126">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="9602d-127">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9602d-127">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="9602d-128">为指定的包提供程序添加包源。</span><span class="sxs-lookup"><span data-stu-id="9602d-128">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="9602d-129">Save-Package</span><span class="sxs-lookup"><span data-stu-id="9602d-129">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="9602d-130">将包保存到本地计算机，但不安装它们。</span><span class="sxs-lookup"><span data-stu-id="9602d-130">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="9602d-131">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9602d-131">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="9602d-132">替换指定包提供程序的包源。</span><span class="sxs-lookup"><span data-stu-id="9602d-132">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="9602d-133">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="9602d-133">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="9602d-134">卸载一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="9602d-134">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="9602d-135">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9602d-135">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="9602d-136">删除已注册的包源。</span><span class="sxs-lookup"><span data-stu-id="9602d-136">Removes a registered package source.</span></span>

