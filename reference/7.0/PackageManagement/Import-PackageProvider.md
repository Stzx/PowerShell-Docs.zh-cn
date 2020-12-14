---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 570ed2a314c498fe59546d30cba17913bc91b70c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890468"
---
# <span data-ttu-id="7ef22-103">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="7ef22-103">Import-PackageProvider</span></span>

## <span data-ttu-id="7ef22-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7ef22-104">SYNOPSIS</span></span>
<span data-ttu-id="7ef22-105">将包管理包提供程序添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="7ef22-105">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="7ef22-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ef22-106">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="7ef22-107">说明</span><span class="sxs-lookup"><span data-stu-id="7ef22-107">DESCRIPTION</span></span>

<span data-ttu-id="7ef22-108">`Import-PackageProvider`Cmdlet 可将一个或多个包提供程序添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="7ef22-108">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="7ef22-109">必须在本地计算机上安装导入的提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ef22-109">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="7ef22-110">若要获取可用提供程序的列表，请运行 `Get-PackageProvider -ListAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="7ef22-110">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="7ef22-111">请注意，包提供程序名称可以与其模块名称不同。</span><span class="sxs-lookup"><span data-stu-id="7ef22-111">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="7ef22-112">出于安全原因， **PackageManagement** 要求基于 c # 的提供程序包含 `provider.manifest` 。</span><span class="sxs-lookup"><span data-stu-id="7ef22-112">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="7ef22-113">有关如何使用注入的生成提供程序的详细信息 `provider.manifest` ，请参阅 `.csproj` 上的项目文件 [https://github.com/oneget/oneget](https://github.com/oneget/oneget) 。</span><span class="sxs-lookup"><span data-stu-id="7ef22-113">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="7ef22-114">示例</span><span class="sxs-lookup"><span data-stu-id="7ef22-114">EXAMPLES</span></span>

### <span data-ttu-id="7ef22-115">示例1：从本地计算机导入包提供程序</span><span class="sxs-lookup"><span data-stu-id="7ef22-115">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="7ef22-116">此命令在 Nuget 提供程序安装在本地计算机上后导入它。</span><span class="sxs-lookup"><span data-stu-id="7ef22-116">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="7ef22-117">示例2：导入特定版本的包提供程序</span><span class="sxs-lookup"><span data-stu-id="7ef22-117">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="7ef22-118">此命令查找、安装和导入特定版本的 Nuget 包提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ef22-118">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="7ef22-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ef22-119">PARAMETERS</span></span>

### <span data-ttu-id="7ef22-120">-Force</span><span class="sxs-lookup"><span data-stu-id="7ef22-120">-Force</span></span>

<span data-ttu-id="7ef22-121">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="7ef22-121">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="7ef22-122">重新导入包提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ef22-122">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="7ef22-123">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="7ef22-123">-ForceBootstrap</span></span>

<span data-ttu-id="7ef22-124">指示此 cmdlet 强制包管理自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ef22-124">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="7ef22-125">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="7ef22-125">-MaximumVersion</span></span>

<span data-ttu-id="7ef22-126">指定要导入的包提供程序的最大允许版本。</span><span class="sxs-lookup"><span data-stu-id="7ef22-126">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="7ef22-127">如果未添加此参数，则将 `Import-PackageProvider` 导入提供程序的最高可用版本。</span><span class="sxs-lookup"><span data-stu-id="7ef22-127">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

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

### <span data-ttu-id="7ef22-128">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="7ef22-128">-MinimumVersion</span></span>

<span data-ttu-id="7ef22-129">指定要导入的包提供程序的最小允许版本。</span><span class="sxs-lookup"><span data-stu-id="7ef22-129">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="7ef22-130">如果未添加此参数，则将 `Import-PackageProvider` 导入同时满足使用 *MaximumVersion* 参数指定的任何最高版本的包的最高可用版本。</span><span class="sxs-lookup"><span data-stu-id="7ef22-130">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="7ef22-131">-Name</span><span class="sxs-lookup"><span data-stu-id="7ef22-131">-Name</span></span>

<span data-ttu-id="7ef22-132">指定一个或多个包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="7ef22-132">Specifies one or more package provider names.</span></span> <span data-ttu-id="7ef22-133">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="7ef22-133">Wildcards are not permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7ef22-134">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="7ef22-134">-RequiredVersion</span></span>

<span data-ttu-id="7ef22-135">指定要导入的包提供程序的确切版本。</span><span class="sxs-lookup"><span data-stu-id="7ef22-135">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="7ef22-136">如果未添加此参数，则将 `Import-PackageProvider` 导入最高可用版本的提供程序，该版本还满足使用 **MaximumVersion** 参数指定的任何最高版本。</span><span class="sxs-lookup"><span data-stu-id="7ef22-136">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="7ef22-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ef22-137">CommonParameters</span></span>

<span data-ttu-id="7ef22-138">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7ef22-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ef22-139">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7ef22-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ef22-140">输入</span><span class="sxs-lookup"><span data-stu-id="7ef22-140">INPUTS</span></span>

### <span data-ttu-id="7ef22-141">Install-packageprovider。</span><span class="sxs-lookup"><span data-stu-id="7ef22-141">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="7ef22-142">可以通过管道将返回的 **install-packageprovider** 对象传递 `Get-PackageProvider` 给 `Import-PackageProvider` 。</span><span class="sxs-lookup"><span data-stu-id="7ef22-142">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="7ef22-143">输出</span><span class="sxs-lookup"><span data-stu-id="7ef22-143">OUTPUTS</span></span>

## <span data-ttu-id="7ef22-144">注释</span><span class="sxs-lookup"><span data-stu-id="7ef22-144">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ef22-145">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="7ef22-145">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="7ef22-146">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="7ef22-146">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="7ef22-147">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="7ef22-147">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="7ef22-148">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="7ef22-148">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="7ef22-149">相关链接</span><span class="sxs-lookup"><span data-stu-id="7ef22-149">RELATED LINKS</span></span>

[<span data-ttu-id="7ef22-150">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="7ef22-150">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="7ef22-151">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7ef22-151">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="7ef22-152">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7ef22-152">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="7ef22-153">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7ef22-153">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="7ef22-154">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="7ef22-154">Get-PackageProvider</span></span>](Get-PackageProvider.md)
