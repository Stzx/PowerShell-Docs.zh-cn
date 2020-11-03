---
description: 列出旨在与 PowerShell 提供程序一起使用的 cmdlet。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 3391dce21cec5080020640be75e4c4df9da0c812
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200326"
---
# <a name="about-core-commands"></a><span data-ttu-id="85ec2-104">关于核心命令</span><span class="sxs-lookup"><span data-stu-id="85ec2-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="85ec2-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="85ec2-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="85ec2-106">列出旨在与 PowerShell 提供程序一起使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85ec2-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="85ec2-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="85ec2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="85ec2-108">PowerShell 包括一组 cmdlet，这些 cmdlet 专门用于管理 Windows PowerShell 提供程序公开的数据存储中的项。</span><span class="sxs-lookup"><span data-stu-id="85ec2-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by Windows PowerShell providers.</span></span>
<span data-ttu-id="85ec2-109">您可以通过相同的方式使用这些 cmdlet 来管理提供商提供的所有不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="85ec2-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="85ec2-110">有关提供程序的详细信息，请键入 "get-help about_providers"。</span><span class="sxs-lookup"><span data-stu-id="85ec2-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="85ec2-111">例如，你可以使用 Get-ChildItem cmdlet 来列出文件系统目录中的文件、注册表项下的注册表项或你编写或下载的提供程序公开的项。</span><span class="sxs-lookup"><span data-stu-id="85ec2-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="85ec2-112">下面是专为与提供程序一起使用的 PowerShell cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="85ec2-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="85ec2-113">Get-childitem cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="85ec2-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="85ec2-114">Get-ChildItem</span></span>

<span data-ttu-id="85ec2-115">内容 cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-115">Content cmdlets</span></span>

- <span data-ttu-id="85ec2-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="85ec2-116">Add-Content</span></span>
- <span data-ttu-id="85ec2-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="85ec2-117">Clear-Content</span></span>
- <span data-ttu-id="85ec2-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="85ec2-118">Get-Content</span></span>
- <span data-ttu-id="85ec2-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="85ec2-119">Set-Content</span></span>

<span data-ttu-id="85ec2-120">项 cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-120">Item cmdlets</span></span>

- <span data-ttu-id="85ec2-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-121">Clear-Item</span></span>
- <span data-ttu-id="85ec2-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-122">Copy-Item</span></span>
- <span data-ttu-id="85ec2-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-123">Get-Item</span></span>
- <span data-ttu-id="85ec2-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-124">Invoke-Item</span></span>
- <span data-ttu-id="85ec2-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-125">Move-Item</span></span>
- <span data-ttu-id="85ec2-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-126">New-Item</span></span>
- <span data-ttu-id="85ec2-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-127">Remove-Item</span></span>
- <span data-ttu-id="85ec2-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-128">Rename-Item</span></span>
- <span data-ttu-id="85ec2-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="85ec2-129">Set-Item</span></span>

<span data-ttu-id="85ec2-130">Set-itemproperty cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="85ec2-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="85ec2-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="85ec2-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-133">Get-ItemProperty</span></span>
- <span data-ttu-id="85ec2-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-134">Move-ItemProperty</span></span>
- <span data-ttu-id="85ec2-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-135">New-ItemProperty</span></span>
- <span data-ttu-id="85ec2-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="85ec2-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="85ec2-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="85ec2-138">Set-ItemProperty</span></span>

<span data-ttu-id="85ec2-139">位置 cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-139">Location cmdlets</span></span>

- <span data-ttu-id="85ec2-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="85ec2-140">Get-Location</span></span>
- <span data-ttu-id="85ec2-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="85ec2-141">Pop-Location</span></span>
- <span data-ttu-id="85ec2-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="85ec2-142">Push-Location</span></span>
- <span data-ttu-id="85ec2-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="85ec2-143">Set-Location</span></span>

<span data-ttu-id="85ec2-144">路径 cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-144">Path cmdlets</span></span>

- <span data-ttu-id="85ec2-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="85ec2-145">Join-Path</span></span>
- <span data-ttu-id="85ec2-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="85ec2-146">Convert-Path</span></span>
- <span data-ttu-id="85ec2-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="85ec2-147">Split-Path</span></span>
- <span data-ttu-id="85ec2-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="85ec2-148">Resolve-Path</span></span>
- <span data-ttu-id="85ec2-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="85ec2-149">Test-Path</span></span>

<span data-ttu-id="85ec2-150">New-psdrive cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="85ec2-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="85ec2-151">Get-PSDrive</span></span>
- <span data-ttu-id="85ec2-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="85ec2-152">New-PSDrive</span></span>
- <span data-ttu-id="85ec2-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="85ec2-153">Remove-PSDrive</span></span>

<span data-ttu-id="85ec2-154">PSProvider cmdlet</span><span class="sxs-lookup"><span data-stu-id="85ec2-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="85ec2-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="85ec2-155">Get-PSProvider</span></span>

<span data-ttu-id="85ec2-156">有关 cmdlet 的详细信息，请键入 `get-help <cmdlet-name>` 。</span><span class="sxs-lookup"><span data-stu-id="85ec2-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="85ec2-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85ec2-157">SEE ALSO</span></span>

[<span data-ttu-id="85ec2-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="85ec2-158">about_Providers</span></span>](about_Providers.md)
