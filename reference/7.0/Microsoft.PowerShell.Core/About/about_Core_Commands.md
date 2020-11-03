---
description: 列出旨在与 PowerShell 提供程序一起使用的 cmdlet。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 5c784518ae30108813d32497f654198e7d10b379
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199613"
---
# <a name="about-core-commands"></a><span data-ttu-id="ff77a-104">关于核心命令</span><span class="sxs-lookup"><span data-stu-id="ff77a-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="ff77a-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ff77a-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ff77a-106">列出旨在与 PowerShell 提供程序一起使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff77a-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="ff77a-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="ff77a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ff77a-108">PowerShell 包括一组 cmdlet，这些 cmdlet 专门用于管理 PowerShell 提供程序公开的数据存储中的项。</span><span class="sxs-lookup"><span data-stu-id="ff77a-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="ff77a-109">您可以通过相同的方式使用这些 cmdlet 来管理提供商提供的所有不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="ff77a-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="ff77a-110">有关提供程序的详细信息，请键入 "get-help about_providers"。</span><span class="sxs-lookup"><span data-stu-id="ff77a-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="ff77a-111">例如，你可以使用 Get-ChildItem cmdlet 来列出文件系统目录中的文件、注册表项下的注册表项或你编写或下载的提供程序公开的项。</span><span class="sxs-lookup"><span data-stu-id="ff77a-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="ff77a-112">下面是专为与提供程序一起使用的 PowerShell cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="ff77a-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="ff77a-113">Get-childitem cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="ff77a-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="ff77a-114">Get-ChildItem</span></span>

<span data-ttu-id="ff77a-115">内容 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-115">Content cmdlets</span></span>

- <span data-ttu-id="ff77a-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="ff77a-116">Add-Content</span></span>
- <span data-ttu-id="ff77a-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="ff77a-117">Clear-Content</span></span>
- <span data-ttu-id="ff77a-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="ff77a-118">Get-Content</span></span>
- <span data-ttu-id="ff77a-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="ff77a-119">Set-Content</span></span>

<span data-ttu-id="ff77a-120">项 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-120">Item cmdlets</span></span>

- <span data-ttu-id="ff77a-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-121">Clear-Item</span></span>
- <span data-ttu-id="ff77a-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-122">Copy-Item</span></span>
- <span data-ttu-id="ff77a-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-123">Get-Item</span></span>
- <span data-ttu-id="ff77a-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-124">Invoke-Item</span></span>
- <span data-ttu-id="ff77a-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-125">Move-Item</span></span>
- <span data-ttu-id="ff77a-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-126">New-Item</span></span>
- <span data-ttu-id="ff77a-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-127">Remove-Item</span></span>
- <span data-ttu-id="ff77a-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-128">Rename-Item</span></span>
- <span data-ttu-id="ff77a-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="ff77a-129">Set-Item</span></span>

<span data-ttu-id="ff77a-130">Set-itemproperty cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="ff77a-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="ff77a-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="ff77a-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-133">Get-ItemProperty</span></span>
- <span data-ttu-id="ff77a-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-134">Move-ItemProperty</span></span>
- <span data-ttu-id="ff77a-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-135">New-ItemProperty</span></span>
- <span data-ttu-id="ff77a-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="ff77a-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="ff77a-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ff77a-138">Set-ItemProperty</span></span>

<span data-ttu-id="ff77a-139">位置 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-139">Location cmdlets</span></span>

- <span data-ttu-id="ff77a-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="ff77a-140">Get-Location</span></span>
- <span data-ttu-id="ff77a-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="ff77a-141">Pop-Location</span></span>
- <span data-ttu-id="ff77a-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="ff77a-142">Push-Location</span></span>
- <span data-ttu-id="ff77a-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="ff77a-143">Set-Location</span></span>

<span data-ttu-id="ff77a-144">路径 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-144">Path cmdlets</span></span>

- <span data-ttu-id="ff77a-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="ff77a-145">Join-Path</span></span>
- <span data-ttu-id="ff77a-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="ff77a-146">Convert-Path</span></span>
- <span data-ttu-id="ff77a-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="ff77a-147">Split-Path</span></span>
- <span data-ttu-id="ff77a-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="ff77a-148">Resolve-Path</span></span>
- <span data-ttu-id="ff77a-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="ff77a-149">Test-Path</span></span>

<span data-ttu-id="ff77a-150">New-psdrive cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="ff77a-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ff77a-151">Get-PSDrive</span></span>
- <span data-ttu-id="ff77a-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ff77a-152">New-PSDrive</span></span>
- <span data-ttu-id="ff77a-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ff77a-153">Remove-PSDrive</span></span>

<span data-ttu-id="ff77a-154">PSProvider cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff77a-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="ff77a-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="ff77a-155">Get-PSProvider</span></span>

<span data-ttu-id="ff77a-156">有关 cmdlet 的详细信息，请键入 `get-help <cmdlet-name>` 。</span><span class="sxs-lookup"><span data-stu-id="ff77a-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff77a-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff77a-157">SEE ALSO</span></span>

[<span data-ttu-id="ff77a-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ff77a-158">about_Providers</span></span>](about_Providers.md)
