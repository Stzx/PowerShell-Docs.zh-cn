---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: ceae77cb6ef2e36f62da7872e9592292e6065ada
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198136"
---
# <span data-ttu-id="6dbb2-103">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6dbb2-103">Install-PackageProvider</span></span>

## <span data-ttu-id="6dbb2-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6dbb2-104">SYNOPSIS</span></span>
<span data-ttu-id="6dbb2-105">安装一个或多个包管理包提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-105">Installs one or more Package Management package providers.</span></span>

## <span data-ttu-id="6dbb2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6dbb2-106">SYNTAX</span></span>

### <span data-ttu-id="6dbb2-107">PackageBySearch（默认值）</span><span class="sxs-lookup"><span data-stu-id="6dbb2-107">PackageBySearch (Default)</span></span>

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="6dbb2-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="6dbb2-108">PackageByInputObject</span></span>

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="6dbb2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6dbb2-109">DESCRIPTION</span></span>

<span data-ttu-id="6dbb2-110">**Install-packageprovider** cmdlet 安装在使用 **PowerShellGet** 注册的包源中可用的匹配包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-110">The **Install-PackageProvider** cmdlet installs matching Package Management providers that are available in package sources registered with **PowerShellGet** .</span></span>
<span data-ttu-id="6dbb2-111">默认情况下，这包括在使用 **PackageManagement** 标记的 PowerShell 库中可用的模块。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-111">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** tag.</span></span>
<span data-ttu-id="6dbb2-112">**PowerShellGet** 包管理提供程序用于查找这些存储库中的提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-112">The **PowerShellGet** Package Management provider is used for finding providers in these repositories.</span></span>

<span data-ttu-id="6dbb2-113">此 cmdlet 还会安装可使用包管理引导应用程序进行匹配包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-113">This cmdlet also installs matching Package Management providers that are available using the Package Management bootstrapping application.</span></span>

<span data-ttu-id="6dbb2-114">此 cmdlet 还会安装包管理 Azure Blob 存储中提供的匹配包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-114">This cmdlet also installs matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="6dbb2-115">使用引导程序提供程序查找并安装它们。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-115">Use the bootstrapper provider to find and install them.</span></span>

<span data-ttu-id="6dbb2-116">为了首次执行，PackageManagement 需要 internet 连接才能下载 Nuget 包提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-116">In order to execute the first time, PackageManagement requires an internet connection to download the Nuget package provider.</span></span>
<span data-ttu-id="6dbb2-117">但是，如果您的计算机没有 internet 连接并且您需要使用 Nuget 或 PowerShellGet 提供程序，则可以将其下载到其他计算机上，然后将它们复制到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-117">However, if your computer does not have an internet connection and you need to use the Nuget or PowerShellGet provider, you can download them on another computer and copy them to your target computer.</span></span>
<span data-ttu-id="6dbb2-118">使用以下步骤来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6dbb2-118">Use the following steps to do this:</span></span>

1.
<span data-ttu-id="6dbb2-119">运行 `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` 从具有 internet 连接的计算机上安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-119">Run `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` to install the provider from a computer with an internet connection.</span></span>

2.
<span data-ttu-id="6dbb2-120">安装后，可以在或中找到安装的提供 `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` 程序 `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` 。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-120">After the install, you can find the provider installed in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>`.</span></span>

3.
<span data-ttu-id="6dbb2-121">将 \<ProviderName\> 该文件夹（在本例中为 Nuget 文件夹）放置在目标计算机上的相应位置。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-121">Place the \<ProviderName\> folder, which in this case is the Nuget folder, in the corresponding location on your target computer.</span></span>
<span data-ttu-id="6dbb2-122">如果目标计算机是 Nano server，则需要从 Nano Server 运行 **install-packageprovider** 以下载正确的 Nuget 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-122">If your target computer is a Nano server, you need to run **Install-PackageProvider** from Nano Server to download the correct Nuget binaries.</span></span>

4.
<span data-ttu-id="6dbb2-123">重新启动 PowerShell 以自动加载包提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-123">Restart PowerShell to auto-load the package provider.</span></span>
<span data-ttu-id="6dbb2-124">或者，运行 `Get-PackageProvider -ListAvailable` 以列出计算机上可用的所有包提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-124">Alternatively, run `Get-PackageProvider -ListAvailable` to list all the package providers available on the computer.</span></span>
<span data-ttu-id="6dbb2-125">然后，使用 `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` 将提供程序导入到当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-125">Then use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` to import the provider to the current PowerShell session.</span></span>

## <span data-ttu-id="6dbb2-126">示例</span><span class="sxs-lookup"><span data-stu-id="6dbb2-126">EXAMPLES</span></span>

### <span data-ttu-id="6dbb2-127">示例1：从 PowerShell 库安装包提供程序</span><span class="sxs-lookup"><span data-stu-id="6dbb2-127">Example 1: Install a package provider from the PowerShell Gallery</span></span>

```
PS C:\> Install-PackageProvider -Name "Gistprovider" -Verbose
```

<span data-ttu-id="6dbb2-128">此命令从 PowerShell 库安装 Gistprovider。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-128">This command installs the Gistprovider from the PowerShell Gallery.</span></span>

### <span data-ttu-id="6dbb2-129">示例2：安装包提供程序的指定版本</span><span class="sxs-lookup"><span data-stu-id="6dbb2-129">Example 2: Install a specified version of a package provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
PS C:\> Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.216" -Force
```

<span data-ttu-id="6dbb2-130">此示例将安装 Nuget 包提供程序的指定版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-130">This example installs a specified version of the Nuget package provider.</span></span>

<span data-ttu-id="6dbb2-131">第一个命令将查找名为 Nuget 的包提供程序的所有版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-131">The first command finds all versions of the package provider named Nuget.</span></span>
<span data-ttu-id="6dbb2-132">第二个命令安装 Nuget 包提供程序的指定版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-132">The second command installs a specified version of the Nuget package provider.</span></span>

### <span data-ttu-id="6dbb2-133">示例3：查找提供程序并安装它</span><span class="sxs-lookup"><span data-stu-id="6dbb2-133">Example 3: Find a provider and install it</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" | Install-PackageProvider -Verbose
```

<span data-ttu-id="6dbb2-134">此命令使用 **install-packageprovider** 和管道搜索 Gist 提供程序并安装它。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-134">This command uses **Find-PackageProvider** and the pipeline to search for the Gist provider and install it.</span></span>

### <span data-ttu-id="6dbb2-135">示例4：将提供程序安装到当前用户的模块文件夹</span><span class="sxs-lookup"><span data-stu-id="6dbb2-135">Example 4: Install a provider to the current user's module folder</span></span>

```
PS C:\> Install-PackageProvider -Name Gistprovider -Verbose -Scope CurrentUser
```

<span data-ttu-id="6dbb2-136">此命令将包提供程序安装到 $env： LOCALAPPDATA\PackageManagement\ProviderAssemblies，以便只有当前用户可以使用它。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-136">This command installs a package provider to $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies so that only the current user can use it.</span></span>

## <span data-ttu-id="6dbb2-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6dbb2-137">PARAMETERS</span></span>

### <span data-ttu-id="6dbb2-138">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="6dbb2-138">-AllVersions</span></span>

<span data-ttu-id="6dbb2-139">指示此 cmdlet 安装包提供程序的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-139">Indicates that this cmdlet installs all available versions of the package provider.</span></span>
<span data-ttu-id="6dbb2-140">默认情况下， **install-packageprovider** 仅返回可用的最高版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-140">By default, **Install-PackageProvider** only returns the highest available version.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="6dbb2-141">-Credential</span></span>

<span data-ttu-id="6dbb2-142">指定有权安装包提供程序的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-142">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-143">-Force</span><span class="sxs-lookup"><span data-stu-id="6dbb2-143">-Force</span></span>

<span data-ttu-id="6dbb2-144">指示此 cmdlet 强制执行可强制执行的与此 cmdlet 的所有操作。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-144">Indicates that this cmdlet forces all actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="6dbb2-145">目前，这意味着 *Force* 参数的作用与 *ForceBootstrap* 参数相同。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-145">Currently, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-146">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="6dbb2-146">-ForceBootstrap</span></span>

<span data-ttu-id="6dbb2-147">指示此 cmdlet 自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-147">Indicates that this cmdlet automatically installs the package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6dbb2-148">-InputObject</span></span>

<span data-ttu-id="6dbb2-149">指定 **softwareidentity.revisionnumber** 对象。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-149">Specifies a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="6dbb2-150">使用 **install-packageprovider** Cmdlet 获取 **softwareidentity.revisionnumber** 对象，以便通过管道加入 **install-packageprovider** 。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-150">Use the **Find-PackageProvider** cmdlet to obtain a **SoftwareIdentity** object to pipe into **Install-PackageProvider** .</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="6dbb2-151">-MaximumVersion</span></span>

<span data-ttu-id="6dbb2-152">指定要安装的包提供程序的最大允许版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-152">Specifies the maximum allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="6dbb2-153">如果未添加此参数，则 **install-packageprovider** 将安装提供程序的最高可用版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-153">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-154">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="6dbb2-154">-MinimumVersion</span></span>

<span data-ttu-id="6dbb2-155">指定要安装的包提供程序的最小允许版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-155">Specifies the minimum allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="6dbb2-156">如果未添加此参数，则 **install-packageprovider** 将安装包的最高可用版本，同时满足 *MaximumVersion* 参数指定的任何要求。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-156">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the package that also satisfies any requirement specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-157">-Name</span><span class="sxs-lookup"><span data-stu-id="6dbb2-157">-Name</span></span>

<span data-ttu-id="6dbb2-158">指定一个或多个包提供程序模块名称。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-158">Specifies one or more package provider module names.</span></span>
<span data-ttu-id="6dbb2-159">用逗号分隔多个包名称。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-159">Separate multiple package names with commas.</span></span>
<span data-ttu-id="6dbb2-160">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-160">Wildcard characters are not supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-161">-Proxy</span><span class="sxs-lookup"><span data-stu-id="6dbb2-161">-Proxy</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="6dbb2-162">-ProxyCredential</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-163">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="6dbb2-163">-RequiredVersion</span></span>

<span data-ttu-id="6dbb2-164">指定要安装的包提供程序的确切允许版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-164">Specifies the exact allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="6dbb2-165">如果未添加此参数，则 **install-packageprovider** 将安装提供程序的最高版本，同时满足 *MaximumVersion* 参数指定的任何最高版本。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-165">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-166">-Scope</span><span class="sxs-lookup"><span data-stu-id="6dbb2-166">-Scope</span></span>

<span data-ttu-id="6dbb2-167">指定提供程序的安装范围。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-167">Specifies the installation scope of the provider.</span></span>
<span data-ttu-id="6dbb2-168">此参数的可接受值为： **AllUsers** 和 **CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-168">The acceptable values for this parameter are: **AllUsers** and **CurrentUser** .</span></span>

<span data-ttu-id="6dbb2-169">**AllUsers** 作用域会将提供程序安装到计算机的所有用户都可以访问的位置。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-169">The **AllUsers** scope installs providers in a location that is accessible to all users of the computer.</span></span>
<span data-ttu-id="6dbb2-170">默认情况下，这是 **$env:P rogramfiles\packagemanagement\providerassemblies.**</span><span class="sxs-lookup"><span data-stu-id="6dbb2-170">By default, this is **$env:ProgramFiles\PackageManagement\ProviderAssemblies.**</span></span>

<span data-ttu-id="6dbb2-171">**CurrentUser** 作用域在只能由当前用户访问的位置安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-171">The **CurrentUser** scope installs providers in a location where they are only accessible to the current user.</span></span>
<span data-ttu-id="6dbb2-172">默认情况下，这是 **$env： LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span><span class="sxs-lookup"><span data-stu-id="6dbb2-172">By default, this is **$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-173">-Source</span><span class="sxs-lookup"><span data-stu-id="6dbb2-173">-Source</span></span>

<span data-ttu-id="6dbb2-174">指定一个或多个包源。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-174">Specifies one or more package sources.</span></span>
<span data-ttu-id="6dbb2-175">使用 Get-PackageSource cmdlet 获取可用包源的列表。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-175">Use the Get-PackageSource cmdlet to get a list of available package sources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6dbb2-176">-Confirm</span></span>

<span data-ttu-id="6dbb2-177">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-177">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6dbb2-178">-WhatIf</span></span>

<span data-ttu-id="6dbb2-179">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6dbb2-180">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-180">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6dbb2-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6dbb2-181">CommonParameters</span></span>

<span data-ttu-id="6dbb2-182">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6dbb2-183">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6dbb2-184">输入</span><span class="sxs-lookup"><span data-stu-id="6dbb2-184">INPUTS</span></span>

### <span data-ttu-id="6dbb2-185">Softwareidentity.revisionnumber。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-185">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="6dbb2-186">可以通过管道将 **softwareidentity.revisionnumber** 对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-186">You can pipe a **SoftwareIdentity** object to this cmdlet.</span></span>
<span data-ttu-id="6dbb2-187">使用 Find-PackageProvider 获取可通过管道传递到 **install-packageprovider** 的 **softwareidentity.revisionnumber** 对象。</span><span class="sxs-lookup"><span data-stu-id="6dbb2-187">Use Find-PackageProvider to get a **SoftwareIdentity** object that can be piped into **Install-PackageProvider** .</span></span>

## <span data-ttu-id="6dbb2-188">输出</span><span class="sxs-lookup"><span data-stu-id="6dbb2-188">OUTPUTS</span></span>

## <span data-ttu-id="6dbb2-189">注释</span><span class="sxs-lookup"><span data-stu-id="6dbb2-189">NOTES</span></span>

## <span data-ttu-id="6dbb2-190">相关链接</span><span class="sxs-lookup"><span data-stu-id="6dbb2-190">RELATED LINKS</span></span>

[<span data-ttu-id="6dbb2-191">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6dbb2-191">Find-PackageProvider</span></span>](Find-PackageProvider.md)

[<span data-ttu-id="6dbb2-192">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6dbb2-192">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="6dbb2-193">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6dbb2-193">Import-PackageProvider</span></span>](Import-PackageProvider.md)
