---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: 9d62706d5788f1ae2c97da4bf1f6143eed2ad8f9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197734"
---
# <span data-ttu-id="ef683-103">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="ef683-103">Find-DscResource</span></span>

## <span data-ttu-id="ef683-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ef683-104">SYNOPSIS</span></span>
<span data-ttu-id="ef683-105"> (DSC) 资源中查找所需的状态配置。</span><span class="sxs-lookup"><span data-stu-id="ef683-105">Finds Desired State Configuration (DSC) resources.</span></span>

## <span data-ttu-id="ef683-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef683-106">SYNTAX</span></span>

### <span data-ttu-id="ef683-107">全部</span><span class="sxs-lookup"><span data-stu-id="ef683-107">All</span></span>

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ef683-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef683-108">DESCRIPTION</span></span>

<span data-ttu-id="ef683-109">`Find-DscResource`Cmdlet 可搜索已注册的存储库，以查找模块中包含的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-109">The `Find-DscResource` cmdlet searches registered repositories to find DSC resources contained in modules.</span></span> <span data-ttu-id="ef683-110">默认情况下， `Find-DscResource` 搜索所有已注册的存储库。</span><span class="sxs-lookup"><span data-stu-id="ef683-110">By default `Find-DscResource` searches all registered repositories.</span></span>

<span data-ttu-id="ef683-111">对于找到的每个模块 `Find-DscResource` ，都将返回 **PSGetDscResourceInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="ef683-111">For each module found by `Find-DscResource`, a **PSGetDscResourceInfo** object is returned.</span></span>
<span data-ttu-id="ef683-112">可以通过管道将 **PSGetDscResourceInfo** 对象发送到 `Install-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef683-112">**PSGetDscResourceInfo** objects can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="ef683-113">`Install-Module` 安装模块。</span><span class="sxs-lookup"><span data-stu-id="ef683-113">`Install-Module` installs the module.</span></span>

## <span data-ttu-id="ef683-114">示例</span><span class="sxs-lookup"><span data-stu-id="ef683-114">EXAMPLES</span></span>

### <span data-ttu-id="ef683-115">示例1：查找所有 DSC 资源</span><span class="sxs-lookup"><span data-stu-id="ef683-115">Example 1: Find all DSC resources</span></span>

<span data-ttu-id="ef683-116">`Find-DscResource` 返回已注册存储库中的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-116">`Find-DscResource` returns DSC resources from registered repositories.</span></span> <span data-ttu-id="ef683-117">若要搜索特定存储库，请使用 **存储库** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef683-117">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### <span data-ttu-id="ef683-118">示例2：按名称查找 DSC 资源</span><span class="sxs-lookup"><span data-stu-id="ef683-118">Example 2: Find a DSC resource by name</span></span>

<span data-ttu-id="ef683-119">`Find-DscResource` 按名称定位 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-119">`Find-DscResource` locates DSC resources by name.</span></span> <span data-ttu-id="ef683-120">使用逗号分隔资源名称的数组。</span><span class="sxs-lookup"><span data-stu-id="ef683-120">Use commas to separate an array of resource names.</span></span>

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

<span data-ttu-id="ef683-121">`Find-DscResource` 使用 **Name** 参数查找指定的 DSC 资源数组。</span><span class="sxs-lookup"><span data-stu-id="ef683-121">`Find-DscResource` uses the **Name** parameter to find the specified array of DSC resources.</span></span>

### <span data-ttu-id="ef683-122">示例3：查找 DSC 资源并安装它</span><span class="sxs-lookup"><span data-stu-id="ef683-122">Example 3: Find a DSC resource and install it</span></span>

<span data-ttu-id="ef683-123">`Find-DscResource` 定位 DSC 资源，并将对象向下发送到要安装的管道。</span><span class="sxs-lookup"><span data-stu-id="ef683-123">`Find-DscResource` locates a DSC resource and sends the object down the pipeline to be installed.</span></span>
<span data-ttu-id="ef683-124">安装后，请使用 `Get-InstalledModule` 查看结果。</span><span class="sxs-lookup"><span data-stu-id="ef683-124">After the installation, use `Get-InstalledModule` to view the results.</span></span>

<span data-ttu-id="ef683-125">同一个模块中的多个资源可以通过管道向下发送到 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="ef683-125">Multiple resources from the same module can be sent down the pipeline to the `Install-Module`.</span></span>
<span data-ttu-id="ef683-126">`Install-Module` 尝试仅安装该模块一次。</span><span class="sxs-lookup"><span data-stu-id="ef683-126">`Install-Module` attempts to only install the module once.</span></span>

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

<span data-ttu-id="ef683-127">`Find-DscResource` 使用 **Name** 参数查找名为 **xWebsite** 的资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-127">`Find-DscResource` uses the **Name** parameter to find the resource named **xWebsite** .</span></span> <span data-ttu-id="ef683-128">对象通过管道向下发送到 `Install-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef683-128">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="ef683-129">`Install-Module` 安装资源的 **xWebAdministration** 模块。</span><span class="sxs-lookup"><span data-stu-id="ef683-129">`Install-Module` installs the **xWebAdministration** module for the resource.</span></span>

### <span data-ttu-id="ef683-130">示例4：查找模块中的所有 DSC 资源</span><span class="sxs-lookup"><span data-stu-id="ef683-130">Example 4: Find all DSC resources in a module</span></span>

<span data-ttu-id="ef683-131">`Find-DscResource` 查找指定模块中包含的所有 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-131">`Find-DscResource` finds all the DSC resources contained in a specified module.</span></span> <span data-ttu-id="ef683-132">默认情况下，将显示当前版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-132">By default, the current version is displayed.</span></span> <span data-ttu-id="ef683-133">若要显示其他版本，请使用 **AllVersions** 或 **RequiredVersions** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef683-133">To display other versions, use the **AllVersions** or **RequiredVersions** parameters.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

<span data-ttu-id="ef683-134">`Find-DscResource` 使用 **ModuleName** 参数指定 **xWebAdministration** ，并查找模块中包含的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-134">`Find-DscResource` uses the **ModuleName** parameter to specify the **xWebAdministration** and find the DSC resources contained in the module.</span></span> <span data-ttu-id="ef683-135">显示每个资源的当前版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-135">The current version of each resource is displayed.</span></span>

### <span data-ttu-id="ef683-136">示例5：按标记和所需版本查找 DSC 资源</span><span class="sxs-lookup"><span data-stu-id="ef683-136">Example 5: Find a DSC resource by tag and required version</span></span>

<span data-ttu-id="ef683-137">可以使用参数 **标记** 和 **RequiredVersion** 定位 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-137">DSC resources can be located using the parameters **Tag** and **RequiredVersion** .</span></span> <span data-ttu-id="ef683-138">**标记** 显示存储库中包含指定标记的每个资源的当前版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-138">**Tag** displays the current version of every resource that contains the specified tag in the repository.</span></span>
<span data-ttu-id="ef683-139">**RequiredVersion** 需要 **ModuleName** 参数， **Name** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="ef683-139">**RequiredVersion** needs the **ModuleName** parameter and the **Name** parameter is optional.</span></span> <span data-ttu-id="ef683-140">**Name** 和 **ModuleName** 参数会限制输出。</span><span class="sxs-lookup"><span data-stu-id="ef683-140">The **Name** and **ModuleName** parameters limit the output.</span></span> <span data-ttu-id="ef683-141">使用 **AllVersions** 参数显示 DSC 资源的可用版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-141">Use the **AllVersions** parameter to display a DSC resource's available versions.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### <span data-ttu-id="ef683-142">示例6：使用筛选器查找资源</span><span class="sxs-lookup"><span data-stu-id="ef683-142">Example 6: Find a resource by using a filter</span></span>

<span data-ttu-id="ef683-143">`Find-DscResource` 查找所有资源，并使用 **Filter** 参数按 **域** 指定结果。</span><span class="sxs-lookup"><span data-stu-id="ef683-143">`Find-DscResource` finds all resources and uses the **Filter** parameter to specify the results by **Domain** .</span></span> <span data-ttu-id="ef683-144">**Filter** 参数在对象的说明或模块名称中查找筛选器值。</span><span class="sxs-lookup"><span data-stu-id="ef683-144">The **Filter** parameter finds the filter value in the object's description or module name.</span></span> <span data-ttu-id="ef683-145">使用 `Select-Object` cmdlet 查看对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ef683-145">Use the `Select-Object` cmdlet to view an object's properties.</span></span>

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

## <span data-ttu-id="ef683-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef683-146">PARAMETERS</span></span>

### <span data-ttu-id="ef683-147">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="ef683-147">-AllowPrerelease</span></span>

<span data-ttu-id="ef683-148">在结果中包括标记为预发行的资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-148">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="ef683-149">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="ef683-149">-AllVersions</span></span>

<span data-ttu-id="ef683-150">**AllVersions** 参数显示每个 DSC 资源的可用版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-150">The **AllVersions** parameter displays each of a DSC resource's available versions.</span></span> <span data-ttu-id="ef683-151">不能将 **AllVersions** 参数与 **MinimumVersion** 、 **MaximumVersion** 或 **RequiredVersion** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="ef683-151">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="ef683-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="ef683-152">-Filter</span></span>

<span data-ttu-id="ef683-153">基于 **PackageManagement** 提供程序的搜索语法查找资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-153">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="ef683-154">例如，指定要在 **ModuleName** 和 **Description** 属性内搜索的字词。</span><span class="sxs-lookup"><span data-stu-id="ef683-154">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="ef683-155">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="ef683-155">-MaximumVersion</span></span>

<span data-ttu-id="ef683-156">指定要包含在结果中的资源的最大版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-156">Specifies the maximum version of the resource to include in results.</span></span> <span data-ttu-id="ef683-157">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef683-157">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ef683-158">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="ef683-158">-MinimumVersion</span></span>

<span data-ttu-id="ef683-159">指定要包含在结果中的资源的最低版本。</span><span class="sxs-lookup"><span data-stu-id="ef683-159">Specifies the minimum version of the resource to include in results.</span></span> <span data-ttu-id="ef683-160">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef683-160">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ef683-161">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="ef683-161">-ModuleName</span></span>

<span data-ttu-id="ef683-162">指定包含 DSC 资源的模块。</span><span class="sxs-lookup"><span data-stu-id="ef683-162">Specifies a module that contains the DSC resource.</span></span>

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

### <span data-ttu-id="ef683-163">-Name</span><span class="sxs-lookup"><span data-stu-id="ef683-163">-Name</span></span>

<span data-ttu-id="ef683-164">指定资源的名称。</span><span class="sxs-lookup"><span data-stu-id="ef683-164">Specifies the name of a resource.</span></span> <span data-ttu-id="ef683-165">默认值为 "所有资源"。</span><span class="sxs-lookup"><span data-stu-id="ef683-165">The default is all resources.</span></span> <span data-ttu-id="ef683-166">使用逗号分隔资源名称的数组。</span><span class="sxs-lookup"><span data-stu-id="ef683-166">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef683-167">-Proxy</span><span class="sxs-lookup"><span data-stu-id="ef683-167">-Proxy</span></span>

<span data-ttu-id="ef683-168">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="ef683-168">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef683-169">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ef683-169">-ProxyCredential</span></span>

<span data-ttu-id="ef683-170">指定有权使用 **代理** 参数中指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ef683-170">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef683-171">-Repository</span><span class="sxs-lookup"><span data-stu-id="ef683-171">-Repository</span></span>

<span data-ttu-id="ef683-172">指定要在其中搜索资源的存储库。</span><span class="sxs-lookup"><span data-stu-id="ef683-172">Specifies a repository to search for resources.</span></span> <span data-ttu-id="ef683-173">使用逗号分隔存储库名称数组。</span><span class="sxs-lookup"><span data-stu-id="ef683-173">Use commas to separate an array of repository names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef683-174">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ef683-174">-RequiredVersion</span></span>

<span data-ttu-id="ef683-175">指定要包含在结果中的模块的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="ef683-175">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="ef683-176">无法在同一命令中使用 **RequiredVersion** 和 **MinimumVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef683-176">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ef683-177">-Tag</span><span class="sxs-lookup"><span data-stu-id="ef683-177">-Tag</span></span>

<span data-ttu-id="ef683-178">指定对存储库中的模块进行分类的标记。</span><span class="sxs-lookup"><span data-stu-id="ef683-178">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="ef683-179">使用逗号分隔标记数组。</span><span class="sxs-lookup"><span data-stu-id="ef683-179">Use commas to separate an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef683-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ef683-180">CommonParameters</span></span>

<span data-ttu-id="ef683-181">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ef683-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef683-182">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ef683-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef683-183">输入</span><span class="sxs-lookup"><span data-stu-id="ef683-183">INPUTS</span></span>

## <span data-ttu-id="ef683-184">输出</span><span class="sxs-lookup"><span data-stu-id="ef683-184">OUTPUTS</span></span>

### <span data-ttu-id="ef683-185">PSGetDscResourceInfo</span><span class="sxs-lookup"><span data-stu-id="ef683-185">PSGetDscResourceInfo</span></span>

<span data-ttu-id="ef683-186">`Find-DscResource` 返回 **PSGetDscResourceInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="ef683-186">`Find-DscResource` returns a **PSGetDscResourceInfo** object.</span></span>

## <span data-ttu-id="ef683-187">注释</span><span class="sxs-lookup"><span data-stu-id="ef683-187">NOTES</span></span>

## <span data-ttu-id="ef683-188">相关链接</span><span class="sxs-lookup"><span data-stu-id="ef683-188">RELATED LINKS</span></span>

[<span data-ttu-id="ef683-189">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="ef683-189">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="ef683-190">Install-Module</span><span class="sxs-lookup"><span data-stu-id="ef683-190">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="ef683-191">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ef683-191">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="ef683-192">Select-Object</span><span class="sxs-lookup"><span data-stu-id="ef683-192">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="ef683-193">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="ef683-193">Uninstall-Module</span></span>](Uninstall-Module.md)
