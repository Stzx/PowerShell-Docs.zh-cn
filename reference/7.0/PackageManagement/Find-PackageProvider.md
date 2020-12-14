---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: ac6acb8017ca992f10f377cf921f59c7b99bea4a
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890604"
---
# <span data-ttu-id="e484c-103">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e484c-103">Find-PackageProvider</span></span>

## <span data-ttu-id="e484c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e484c-104">SYNOPSIS</span></span>
<span data-ttu-id="e484c-105">返回可供安装的包管理包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="e484c-105">Returns a list of Package Management package providers available for installation.</span></span>

## <span data-ttu-id="e484c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e484c-106">SYNTAX</span></span>

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="e484c-107">说明</span><span class="sxs-lookup"><span data-stu-id="e484c-107">DESCRIPTION</span></span>

<span data-ttu-id="e484c-108">**Install-packageprovider** cmdlet 查找匹配的 PackageManagement 提供程序，这些提供程序在使用 PowerShellGet 注册的包源中可用。</span><span class="sxs-lookup"><span data-stu-id="e484c-108">The **Find-PackageProvider** cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet.</span></span>
<span data-ttu-id="e484c-109">这些包提供程序都能用 Install-PackageProvider cmdlet 直接进行安装。</span><span class="sxs-lookup"><span data-stu-id="e484c-109">These are package providers available for installation with the Install-PackageProvider cmdlet.</span></span>
<span data-ttu-id="e484c-110">默认情况下，这包括在使用 **PackageManagement** 和 **提供程序** 标记的 PowerShell 库中可用的模块。</span><span class="sxs-lookup"><span data-stu-id="e484c-110">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** and **Provider** tags.</span></span>

<span data-ttu-id="e484c-111">**Install-packageprovider** 还查找包管理 Azure Blob 存储中提供的匹配包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="e484c-111">**Find-PackageProvider** also finds matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="e484c-112">使用引导程序提供程序查找并安装它们。</span><span class="sxs-lookup"><span data-stu-id="e484c-112">Use the bootstrapper provider to find and install them.</span></span>

## <span data-ttu-id="e484c-113">示例</span><span class="sxs-lookup"><span data-stu-id="e484c-113">EXAMPLES</span></span>

### <span data-ttu-id="e484c-114">示例1：查找所有可用的包提供程序</span><span class="sxs-lookup"><span data-stu-id="e484c-114">Example 1: Find all available package providers</span></span>

```
PS C:\> Find-PackageProvider
```

<span data-ttu-id="e484c-115">此命令获取包管理支持的存储库中可用的所有包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="e484c-115">This command gets a list of all package providers that are available on the repositories supported by Package Management.</span></span>
<span data-ttu-id="e484c-116">默认情况下，这些包提供程序在 PowerShell 库上提供，并使用包管理引导应用程序。</span><span class="sxs-lookup"><span data-stu-id="e484c-116">By default, those package providers are available on the PowerShell Gallery and by using the Package Management bootstrapping application.</span></span>

### <span data-ttu-id="e484c-117">示例2：查找提供程序的所有版本</span><span class="sxs-lookup"><span data-stu-id="e484c-117">Example 2: Find all versions of a provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

<span data-ttu-id="e484c-118">此命令将查找名为 Nuget 的包提供程序的所有版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-118">This command finds all versions of the package provider named Nuget.</span></span>

### <span data-ttu-id="e484c-119">示例3：从指定的源查找提供程序</span><span class="sxs-lookup"><span data-stu-id="e484c-119">Example 3: Find a provider from a specified source</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

<span data-ttu-id="e484c-120">此命令使用指定的包源查找可用的包提供程序。</span><span class="sxs-lookup"><span data-stu-id="e484c-120">This command finds a package provider available by using a specified package source.</span></span>

## <span data-ttu-id="e484c-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e484c-121">PARAMETERS</span></span>

### <span data-ttu-id="e484c-122">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e484c-122">-AllVersions</span></span>

<span data-ttu-id="e484c-123">指示此 cmdlet 返回包提供程序的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-123">Indicates that this cmdlet returns all available versions of the package provider.</span></span>
<span data-ttu-id="e484c-124">默认情况下， **install-packageprovider** 仅返回最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-124">By default, **Find-PackageProvider** only returns the newest available version.</span></span>

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

### <span data-ttu-id="e484c-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="e484c-125">-Credential</span></span>

<span data-ttu-id="e484c-126">指定有权搜索包提供程序的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e484c-126">Specifies a user account that has permission to search for package providers.</span></span>

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

### <span data-ttu-id="e484c-127">-Force</span><span class="sxs-lookup"><span data-stu-id="e484c-127">-Force</span></span>

<span data-ttu-id="e484c-128">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="e484c-128">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="e484c-129">目前，这等效于 *ForceBootstrap* 参数。</span><span class="sxs-lookup"><span data-stu-id="e484c-129">Currently, this is equivalent to the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="e484c-130">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e484c-130">-ForceBootstrap</span></span>

<span data-ttu-id="e484c-131">指示此 cmdlet 强制包管理自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="e484c-131">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="e484c-132">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="e484c-132">-IncludeDependencies</span></span>

<span data-ttu-id="e484c-133">指示此 cmdlet 包含依赖项。</span><span class="sxs-lookup"><span data-stu-id="e484c-133">Indicates that this cmdlet includes dependencies.</span></span>

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

### <span data-ttu-id="e484c-134">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e484c-134">-MaximumVersion</span></span>

<span data-ttu-id="e484c-135">指定要查找的包提供程序的最大允许版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-135">Specifies the maximum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="e484c-136">如果未添加此参数，则 **install-packageprovider** 将查找提供程序的最高可用版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-136">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e484c-137">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e484c-137">-MinimumVersion</span></span>

<span data-ttu-id="e484c-138">指定要查找的包提供程序的最小允许版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-138">Specifies the minimum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="e484c-139">如果未添加此参数，则 **install-packageprovider** 将查找同时满足 *MaximumVersion* 参数指定的任何最大指定版本的包的最高可用版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-139">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the package that also satisfies any maximum specified version specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e484c-140">-Name</span><span class="sxs-lookup"><span data-stu-id="e484c-140">-Name</span></span>

<span data-ttu-id="e484c-141">指定一个或多个包提供程序模块名称或提供程序名称和通配符。</span><span class="sxs-lookup"><span data-stu-id="e484c-141">Specifies one or more package provider module names, or provider names with wildcard characters.</span></span>
<span data-ttu-id="e484c-142">用逗号分隔多个包名称。</span><span class="sxs-lookup"><span data-stu-id="e484c-142">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e484c-143">-Proxy</span><span class="sxs-lookup"><span data-stu-id="e484c-143">-Proxy</span></span>

<span data-ttu-id="e484c-144">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="e484c-144">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="e484c-145">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e484c-145">-ProxyCredential</span></span>

<span data-ttu-id="e484c-146">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e484c-146">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e484c-147">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e484c-147">-RequiredVersion</span></span>

<span data-ttu-id="e484c-148">指定要查找的包提供程序的确切允许版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-148">Specifies the exact allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="e484c-149">如果未添加此参数，则 **install-packageprovider** 将查找同时满足 *MaximumVersion* 参数指定的任何最高版本的提供程序的最高可用版本。</span><span class="sxs-lookup"><span data-stu-id="e484c-149">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e484c-150">-Source</span><span class="sxs-lookup"><span data-stu-id="e484c-150">-Source</span></span>

<span data-ttu-id="e484c-151">指定一个或多个包源。</span><span class="sxs-lookup"><span data-stu-id="e484c-151">Specifies one or more package sources.</span></span>
<span data-ttu-id="e484c-152">可以通过使用 Get-PackageSource cmdlet 获取可用包源的列表。</span><span class="sxs-lookup"><span data-stu-id="e484c-152">You can get a list of available package sources by using the Get-PackageSource cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e484c-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e484c-153">CommonParameters</span></span>

<span data-ttu-id="e484c-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e484c-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e484c-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e484c-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e484c-156">输入</span><span class="sxs-lookup"><span data-stu-id="e484c-156">INPUTS</span></span>

## <span data-ttu-id="e484c-157">输出</span><span class="sxs-lookup"><span data-stu-id="e484c-157">OUTPUTS</span></span>

### <span data-ttu-id="e484c-158">Softwareidentity.revisionnumber。</span><span class="sxs-lookup"><span data-stu-id="e484c-158">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="e484c-159">此 cmdlet 将返回 **softwareidentity.revisionnumber** 对象。</span><span class="sxs-lookup"><span data-stu-id="e484c-159">This cmdlet returns a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="e484c-160">可以通过管道将 **softwareidentity.revisionnumber** 对象传递到 **install-packageprovider** 中，以安装 **install-packageprovider** 的结果。</span><span class="sxs-lookup"><span data-stu-id="e484c-160">A **SoftwareIdentity** object can be piped into **Install-PackageProvider** to install the results of **Find-PackageProvider**.</span></span>

## <span data-ttu-id="e484c-161">注释</span><span class="sxs-lookup"><span data-stu-id="e484c-161">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e484c-162">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="e484c-162">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="e484c-163">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="e484c-163">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="e484c-164">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="e484c-164">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="e484c-165">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="e484c-165">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="e484c-166">相关链接</span><span class="sxs-lookup"><span data-stu-id="e484c-166">RELATED LINKS</span></span>

[<span data-ttu-id="e484c-167">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e484c-167">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e484c-168">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e484c-168">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="e484c-169">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e484c-169">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="e484c-170">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e484c-170">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="e484c-171">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e484c-171">Install-PackageProvider</span></span>](Install-PackageProvider.md)
