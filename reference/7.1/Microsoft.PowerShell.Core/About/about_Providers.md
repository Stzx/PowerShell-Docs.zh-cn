---
description: 介绍 PowerShell 提供程序如何提供对在命令行中无法轻松访问的数据和组件的访问。 数据以类似于文件系统驱动器的一致格式显示。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 08ea1679516b58e326eeb3d90fc1aaef4e983a34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200438"
---
# <a name="about-providers"></a><span data-ttu-id="23951-105">关于提供程序</span><span class="sxs-lookup"><span data-stu-id="23951-105">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="23951-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="23951-106">Short description</span></span>
<span data-ttu-id="23951-107">介绍 PowerShell 提供程序如何提供对在命令行中无法轻松访问的数据和组件的访问。</span><span class="sxs-lookup"><span data-stu-id="23951-107">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="23951-108">数据以类似于文件系统驱动器的一致格式显示。</span><span class="sxs-lookup"><span data-stu-id="23951-108">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="23951-109">长说明</span><span class="sxs-lookup"><span data-stu-id="23951-109">Long description</span></span>

<span data-ttu-id="23951-110">PowerShell 提供程序是 .NET 程序，可提供对专用数据存储区的访问权限，便于查看和管理。</span><span class="sxs-lookup"><span data-stu-id="23951-110">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="23951-111">数据显示在驱动器中，你可以访问路径中的数据，就像在硬盘驱动器上访问数据一样。</span><span class="sxs-lookup"><span data-stu-id="23951-111">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="23951-112">你可以使用提供程序支持的任何内置 cmdlet 来管理提供程序驱动器中的数据。</span><span class="sxs-lookup"><span data-stu-id="23951-112">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="23951-113">而且，你可以使用专为数据设计的自定义 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23951-113">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="23951-114">提供程序还可以向内置 cmdlet 添加动态参数。</span><span class="sxs-lookup"><span data-stu-id="23951-114">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="23951-115">仅当你将 cmdlet 与提供程序数据结合使用时，这些参数才可用。</span><span class="sxs-lookup"><span data-stu-id="23951-115">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="23951-116">内置提供程序</span><span class="sxs-lookup"><span data-stu-id="23951-116">Built-in providers</span></span>

<span data-ttu-id="23951-117">PowerShell 包含一组内置提供程序，可用于访问不同类型的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="23951-117">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="23951-118">提供程序</span><span class="sxs-lookup"><span data-stu-id="23951-118">Provider</span></span>   |   <span data-ttu-id="23951-119">驱动器 () </span><span class="sxs-lookup"><span data-stu-id="23951-119">Drive(s)</span></span>  |<span data-ttu-id="23951-120">OutputType</span><span class="sxs-lookup"><span data-stu-id="23951-120">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="23951-121">Alias</span><span class="sxs-lookup"><span data-stu-id="23951-121">Alias</span></span>       |<span data-ttu-id="23951-122">Alias:</span><span class="sxs-lookup"><span data-stu-id="23951-122">Alias:</span></span>       |<span data-ttu-id="23951-123">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="23951-123">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="23951-124">证书</span><span class="sxs-lookup"><span data-stu-id="23951-124">Certificate</span></span> |<span data-ttu-id="23951-125">Cert:</span><span class="sxs-lookup"><span data-stu-id="23951-125">Cert:</span></span>        |<span data-ttu-id="23951-126">Microsoft.powershell.commands.x509storelocation。</span><span class="sxs-lookup"><span data-stu-id="23951-126">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="23951-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="23951-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="23951-128">环境</span><span class="sxs-lookup"><span data-stu-id="23951-128">Environment</span></span> |<span data-ttu-id="23951-129">Env:</span><span class="sxs-lookup"><span data-stu-id="23951-129">Env:</span></span>         |<span data-ttu-id="23951-130">DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="23951-130">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="23951-131">FileSystem</span><span class="sxs-lookup"><span data-stu-id="23951-131">FileSystem</span></span>  |<span data-ttu-id="23951-132">C： ( \* ) </span><span class="sxs-lookup"><span data-stu-id="23951-132">C: (\*)</span></span>       |<span data-ttu-id="23951-133">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="23951-133">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="23951-134">System.IO.DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="23951-134">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="23951-135">函数</span><span class="sxs-lookup"><span data-stu-id="23951-135">Function</span></span>    |<span data-ttu-id="23951-136">函数：</span><span class="sxs-lookup"><span data-stu-id="23951-136">Function:</span></span>    |<span data-ttu-id="23951-137">System.web. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="23951-137">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="23951-138">注册表</span><span class="sxs-lookup"><span data-stu-id="23951-138">Registry</span></span>    |<span data-ttu-id="23951-139">HKLM： HKCU：</span><span class="sxs-lookup"><span data-stu-id="23951-139">HKLM: HKCU:</span></span>  |<span data-ttu-id="23951-140">。 RegistryKey</span><span class="sxs-lookup"><span data-stu-id="23951-140">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="23951-141">变量</span><span class="sxs-lookup"><span data-stu-id="23951-141">Variable</span></span>    |<span data-ttu-id="23951-142">Variable:</span><span class="sxs-lookup"><span data-stu-id="23951-142">Variable:</span></span>    |<span data-ttu-id="23951-143">System.Management.Automation.PSVariable</span><span class="sxs-lookup"><span data-stu-id="23951-143">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="23951-144">WSMan</span><span class="sxs-lookup"><span data-stu-id="23951-144">WSMan</span></span>       |<span data-ttu-id="23951-145">WSMan：</span><span class="sxs-lookup"><span data-stu-id="23951-145">WSMan:</span></span>       |<span data-ttu-id="23951-146">WSManConfigContainerElement。</span><span class="sxs-lookup"><span data-stu-id="23951-146">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="23951-147"> (\ * ) 文件系统驱动器在每个系统上各不相同。</span><span class="sxs-lookup"><span data-stu-id="23951-147">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="23951-148">您还可以创建自己的 PowerShell 提供程序，并可以安装其他人开发的提供程序。</span><span class="sxs-lookup"><span data-stu-id="23951-148">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="23951-149">若要列出会话中可用的提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-149">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="23951-150">安装和删除提供程序</span><span class="sxs-lookup"><span data-stu-id="23951-150">Installing and removing providers</span></span>

<span data-ttu-id="23951-151">提供程序通常通过 PowerShell 模块进行安装。</span><span class="sxs-lookup"><span data-stu-id="23951-151">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="23951-152">导入模块会将提供程序加载到会话中。</span><span class="sxs-lookup"><span data-stu-id="23951-152">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="23951-153">无法卸载内置提供程序。</span><span class="sxs-lookup"><span data-stu-id="23951-153">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="23951-154">你可以卸载其他模块加载的提供程序。</span><span class="sxs-lookup"><span data-stu-id="23951-154">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="23951-155">可以使用 cmdlet 从当前会话中卸载提供程序 `Remove-Module` 。</span><span class="sxs-lookup"><span data-stu-id="23951-155">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="23951-156">此 cmdlet 不会卸载提供程序，但它会使提供程序在会话中不可用。</span><span class="sxs-lookup"><span data-stu-id="23951-156">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="23951-157">你还可以使用 `Remove-PSDrive` cmdlet 从当前会话中删除任何驱动器。</span><span class="sxs-lookup"><span data-stu-id="23951-157">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="23951-158">驱动器上的这些数据不受影响，但该驱动器在该会话中不再可用。</span><span class="sxs-lookup"><span data-stu-id="23951-158">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="23951-159">查看提供程序</span><span class="sxs-lookup"><span data-stu-id="23951-159">Viewing providers</span></span>

<span data-ttu-id="23951-160">若要查看计算机上的 PowerShell 提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-160">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="23951-161">输出会列出内置提供程序以及添加到会话中的提供程序。</span><span class="sxs-lookup"><span data-stu-id="23951-161">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="23951-162">提供程序 cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-162">The provider cmdlets</span></span>

<span data-ttu-id="23951-163">以下 cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="23951-163">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="23951-164">您可以使用相同的 cmdlet 来管理提供程序公开的不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="23951-164">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="23951-165">了解管理一个提供程序的数据后，可以对任何提供程序的数据使用相同的过程。</span><span class="sxs-lookup"><span data-stu-id="23951-165">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="23951-166">例如，cmdlet 会 `New-Item` 创建一个新项。</span><span class="sxs-lookup"><span data-stu-id="23951-166">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="23951-167">在 `C:` **FileSystem** 提供程序支持的驱动器中，可以使用 `New-Item` 来创建新的文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="23951-167">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="23951-168">在 **注册表** 提供程序支持的驱动器中，可以使用 `New-Item` 来创建新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="23951-168">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="23951-169">在 `Alias:` 驱动器中，可以使用 `New-Item` 创建新别名。</span><span class="sxs-lookup"><span data-stu-id="23951-169">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="23951-170">有关以下任何 cmdlet 的详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-170">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="23951-171">Get-childitem cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-171">ChildItem cmdlets</span></span>

- [<span data-ttu-id="23951-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="23951-172">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="23951-173">内容 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-173">Content Cmdlets</span></span>

- [<span data-ttu-id="23951-174">Add-Content</span><span class="sxs-lookup"><span data-stu-id="23951-174">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="23951-175">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="23951-175">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="23951-176">Get-Content</span><span class="sxs-lookup"><span data-stu-id="23951-176">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="23951-177">Set-Content</span><span class="sxs-lookup"><span data-stu-id="23951-177">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="23951-178">项 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-178">Item Cmdlets</span></span>

- [<span data-ttu-id="23951-179">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="23951-179">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="23951-180">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="23951-180">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="23951-181">Get-Item</span><span class="sxs-lookup"><span data-stu-id="23951-181">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="23951-182">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="23951-182">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="23951-183">Move-Item</span><span class="sxs-lookup"><span data-stu-id="23951-183">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="23951-184">New-Item</span><span class="sxs-lookup"><span data-stu-id="23951-184">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="23951-185">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="23951-185">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="23951-186">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="23951-186">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="23951-187">Set-Item</span><span class="sxs-lookup"><span data-stu-id="23951-187">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="23951-188">Set-itemproperty cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-188">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="23951-189">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-189">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="23951-190">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-190">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="23951-191">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-191">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="23951-192">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-192">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="23951-193">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-193">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="23951-194">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-194">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="23951-195">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-195">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="23951-196">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="23951-196">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="23951-197">位置 cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-197">Location cmdlets</span></span>

- [<span data-ttu-id="23951-198">Get-Location</span><span class="sxs-lookup"><span data-stu-id="23951-198">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="23951-199">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="23951-199">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="23951-200">Push-Location</span><span class="sxs-lookup"><span data-stu-id="23951-200">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="23951-201">Set-Location</span><span class="sxs-lookup"><span data-stu-id="23951-201">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="23951-202">路径 cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-202">Path cmdlets</span></span>

- [<span data-ttu-id="23951-203">Join-Path</span><span class="sxs-lookup"><span data-stu-id="23951-203">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="23951-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="23951-204">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="23951-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="23951-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="23951-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="23951-206">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="23951-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="23951-207">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="23951-208">New-psdrive cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-208">PSDrive cmdlets</span></span>

- [<span data-ttu-id="23951-209">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="23951-209">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="23951-210">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="23951-210">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="23951-211">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="23951-211">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="23951-212">PSProvider Cmdlet</span><span class="sxs-lookup"><span data-stu-id="23951-212">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="23951-213">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="23951-213">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="23951-214">查看提供程序数据</span><span class="sxs-lookup"><span data-stu-id="23951-214">Viewing provider data</span></span>

<span data-ttu-id="23951-215">提供程序的主要优点是，它以一种熟悉且一致的方式公开其数据。</span><span class="sxs-lookup"><span data-stu-id="23951-215">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="23951-216">数据显示模型是文件系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="23951-216">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="23951-217">提供程序允许您查看、导航和更改数据存储中的项，就好像它们是文件系统中的数据一样。</span><span class="sxs-lookup"><span data-stu-id="23951-217">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="23951-218">数据存储区由它所支持的驱动器的名称访问。</span><span class="sxs-lookup"><span data-stu-id="23951-218">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="23951-219">此驱动器在 cmdlet 的默认显示中列出 `Get-PSProvider` ，但你可以使用 cmdlet 获取有关提供程序驱动器的信息 `Get-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="23951-219">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="23951-220">例如，若要获取 Function：驱动器的所有属性，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-220">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="23951-221">与在文件系统驱动器上一样，你可以在提供程序驱动器中查看和移动数据。</span><span class="sxs-lookup"><span data-stu-id="23951-221">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="23951-222">若要查看提供程序驱动器的内容，请使用 Get-Item 或 Get-ChildItem cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23951-222">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="23951-223">键入驱动器名称后跟一个冒号 (： ) 。</span><span class="sxs-lookup"><span data-stu-id="23951-223">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="23951-224">例如，若要查看 Alias：驱动器的内容，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-224">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="23951-225">可以通过在路径中包括驱动器名称，从另一个驱动器查看和管理任何驱动器中的数据。</span><span class="sxs-lookup"><span data-stu-id="23951-225">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="23951-226">例如，若要查看其他驱动器中的 HKLM：驱动器中的 HKLM\Software 注册表项，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-226">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="23951-227">若要打开驱动器，请使用 Set-Location cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23951-227">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="23951-228">指定驱动器路径时，请记住冒号。</span><span class="sxs-lookup"><span data-stu-id="23951-228">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="23951-229">例如，若要将你的位置更改为 Cert：驱动器的根目录，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-229">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="23951-230">然后，若要查看 Cert：驱动器的内容，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-230">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="23951-231">通过分层数据移动</span><span class="sxs-lookup"><span data-stu-id="23951-231">Moving through hierarchical data</span></span>

<span data-ttu-id="23951-232">与硬盘驱动器一样，你可以通过提供商驱动器进行移动。</span><span class="sxs-lookup"><span data-stu-id="23951-232">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="23951-233">如果数据排列在项中项的层次结构中，请使用反斜杠 (`\`) 来指示子项。</span><span class="sxs-lookup"><span data-stu-id="23951-233">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="23951-234">使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="23951-234">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="23951-235">例如，若要将你的位置更改为 HKLM\Software 注册表项，请键入 Set-Location 命令，例如：</span><span class="sxs-lookup"><span data-stu-id="23951-235">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="23951-236">如果完全限定名称中的任何元素包含空格，则必须将名称用双引号引起来 (`"`) 。</span><span class="sxs-lookup"><span data-stu-id="23951-236">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="23951-237">下面的示例显示了包含空格的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="23951-237">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="23951-238">还可以对位置使用相对引用。</span><span class="sxs-lookup"><span data-stu-id="23951-238">You can also use relative references to locations.</span></span> <span data-ttu-id="23951-239">一个点 (`.`) 表示当前位置。</span><span class="sxs-lookup"><span data-stu-id="23951-239">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="23951-240">例如，如果你在 `HKLM:\Software\Microsoft` 注册表项中，并且想要列出注册表项中的注册表子项 `HKLM:\Software\Microsoft\PowerShell` ，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="23951-240">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="23951-241">另外，双点 (`..`) 是指直接位于当前位置上方的目录或容器。</span><span class="sxs-lookup"><span data-stu-id="23951-241">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="23951-242">您可以使用双点 (`..`) 在提供程序层次结构中导航。</span><span class="sxs-lookup"><span data-stu-id="23951-242">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="23951-243">提供商主页</span><span class="sxs-lookup"><span data-stu-id="23951-243">Provider Home</span></span>

<span data-ttu-id="23951-244">提供程序还具有 **主** 位置。</span><span class="sxs-lookup"><span data-stu-id="23951-244">Providers also have a **Home** location.</span></span>  <span data-ttu-id="23951-245">此位置由提供程序所支持的全部共享 `PSDrives` 。</span><span class="sxs-lookup"><span data-stu-id="23951-245">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="23951-246">可以通过查看提供程序的 **Home** 属性来检索它。</span><span class="sxs-lookup"><span data-stu-id="23951-246">It can be retrieved by viewing the **Home** property of the provider.</span></span>

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

<span data-ttu-id="23951-247">**FileSystem** 提供程序是唯一具有 **Home** 默认值的提供程序。</span><span class="sxs-lookup"><span data-stu-id="23951-247">The **FileSystem** provider is the only provider that has a default value for **Home** .</span></span> <span data-ttu-id="23951-248">它的值与相同 `$Home` 。</span><span class="sxs-lookup"><span data-stu-id="23951-248">It's the same value as `$Home`.</span></span> <span data-ttu-id="23951-249">有关详细信息，请参阅 [about_Automatic_Variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="23951-249">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="23951-250">你可以使用其属性为当前会话设置提供程序的 **主** 目录。</span><span class="sxs-lookup"><span data-stu-id="23951-250">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="23951-251">`~`字符可用于表示提供程序的主目录。</span><span class="sxs-lookup"><span data-stu-id="23951-251">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="23951-252">如果提供程序没有设置 **主** 位置，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="23951-252">If the provider doesn't have a **Home** location set, you see an error.</span></span>

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="23951-253">查找动态参数</span><span class="sxs-lookup"><span data-stu-id="23951-253">Finding dynamic parameters</span></span>

<span data-ttu-id="23951-254">动态参数是由提供程序添加到 cmdlet 的 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="23951-254">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="23951-255">这些参数仅在 cmdlet 与添加它们的提供程序一起使用时才可用。</span><span class="sxs-lookup"><span data-stu-id="23951-255">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="23951-256">例如， `Cert:` 驱动器将 **CodeSigningCert** 参数添加到 `Get-Item` 和 `Get-ChildItem` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23951-256">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="23951-257">仅当在驱动器中使用或时，才可以使用此参数 `Get-Item` `Get-ChildItem` `Cert:` 。</span><span class="sxs-lookup"><span data-stu-id="23951-257">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="23951-258">有关提供程序支持的动态参数的列表，请参阅提供程序的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="23951-258">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="23951-259">类型：</span><span class="sxs-lookup"><span data-stu-id="23951-259">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="23951-260">例如：</span><span class="sxs-lookup"><span data-stu-id="23951-260">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="23951-261">了解提供程序</span><span class="sxs-lookup"><span data-stu-id="23951-261">Learning about providers</span></span>

<span data-ttu-id="23951-262">尽管所有提供程序数据都显示在驱动器中，并且你使用相同的方法在这些数据中移动，但相似性却停止了。</span><span class="sxs-lookup"><span data-stu-id="23951-262">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="23951-263">提供程序公开的数据存储可能与 Active Directory 位置和 Microsoft Exchange Server 邮箱不同。</span><span class="sxs-lookup"><span data-stu-id="23951-263">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="23951-264">有关各个 PowerShell 提供程序的信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-264">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="23951-265">例如：</span><span class="sxs-lookup"><span data-stu-id="23951-265">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="23951-266">有关提供程序的帮助主题的列表，请键入：</span><span class="sxs-lookup"><span data-stu-id="23951-266">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="23951-267">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23951-267">See also</span></span>

[<span data-ttu-id="23951-268">about_Locations</span><span class="sxs-lookup"><span data-stu-id="23951-268">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="23951-269">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="23951-269">about_Path_Syntax</span></span>](about_Path_Syntax.md)

