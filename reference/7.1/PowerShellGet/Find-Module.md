---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: 22ac0b5651ffa9f055a5c436f56711dc33f95f6e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198359"
---
# <span data-ttu-id="faa03-103">Find-Module</span><span class="sxs-lookup"><span data-stu-id="faa03-103">Find-Module</span></span>

## <span data-ttu-id="faa03-104">摘要</span><span class="sxs-lookup"><span data-stu-id="faa03-104">SYNOPSIS</span></span>
<span data-ttu-id="faa03-105">查找存储库中与指定条件匹配的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-105">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="faa03-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="faa03-106">SYNTAX</span></span>

### <span data-ttu-id="faa03-107">全部</span><span class="sxs-lookup"><span data-stu-id="faa03-107">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="faa03-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="faa03-108">DESCRIPTION</span></span>

<span data-ttu-id="faa03-109">`Find-Module`Cmdlet 可在存储库中查找与指定条件匹配的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-109">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="faa03-110">`Find-Module` 返回它找到的每个模块的 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="faa03-110">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="faa03-111">这些对象可通过管道向下发送到 cmdlet，例如 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="faa03-111">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="faa03-112">第一次 `Find-Module` 尝试使用存储库时，系统可能会提示您安装更新。</span><span class="sxs-lookup"><span data-stu-id="faa03-112">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="faa03-113">如果存储库源未注册 `Register-PSRepository` 到 cmdlet，则会返回错误。</span><span class="sxs-lookup"><span data-stu-id="faa03-113">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="faa03-114">`Find-Module` 如果未使用限制版本的参数，则返回模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-114">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="faa03-115">若要获取存储库的模块版本的列表，请使用参数 **AllVersions** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-115">To get a repository's list of a module's versions, use the parameter **AllVersions** .</span></span>

<span data-ttu-id="faa03-116">如果指定了 **MinimumVersion** 参数，则将 `Find-Module` 返回等于或大于最小值的模块的版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-116">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="faa03-117">如果存储库中有可用的更新版本，则返回较新版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-117">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="faa03-118">如果指定了 **MaximumVersion** 参数，则将 `Find-Module` 返回最新版本的模块，该模块不超过指定的版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-118">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="faa03-119">如果指定了 **RequiredVersion** 参数，则 `Find-Module` 仅返回与指定版本完全匹配的模块版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-119">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="faa03-120">`Find-Module` 搜索所有可用的模块，因为源之间的名称冲突可能会发生。</span><span class="sxs-lookup"><span data-stu-id="faa03-120">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="faa03-121">下面的示例使用 [PowerShell 库](https://www.powershellgallery.com/) 作为唯一的已注册存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-121">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="faa03-122">`Get-PSRepository` 显示已注册的存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-122">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="faa03-123">如果有多个已注册的存储库，请使用 `-Repository` 参数指定存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="faa03-123">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="faa03-124">示例</span><span class="sxs-lookup"><span data-stu-id="faa03-124">EXAMPLES</span></span>

### <span data-ttu-id="faa03-125">示例1：按名称查找模块</span><span class="sxs-lookup"><span data-stu-id="faa03-125">Example 1: Find a module by name</span></span>

<span data-ttu-id="faa03-126">此示例查找默认存储库中的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-126">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="faa03-127">`Find-Module`Cmdlet 使用 **Name** 参数来指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-127">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="faa03-128">示例2：查找具有类似名称的模块</span><span class="sxs-lookup"><span data-stu-id="faa03-128">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="faa03-129">此示例使用 `*`) 通配符 (星号来查找具有类似名称的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-129">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

<span data-ttu-id="faa03-130">`Find-Module`Cmdlet 将 **Name** 参数与星号一起使用 (`*`) 通配符来查找包含 **PowerShell** 的所有模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-130">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell** .</span></span>

### <span data-ttu-id="faa03-131">示例3：按最低版本查找模块</span><span class="sxs-lookup"><span data-stu-id="faa03-131">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="faa03-132">此示例将搜索模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-132">This example searches for a module's minimum version.</span></span> <span data-ttu-id="faa03-133">如果存储库包含较新版本的模块，则返回较新版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-133">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="faa03-134">`Find-Module`Cmdlet 使用 **Name** 参数来指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-134">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="faa03-135">**MinimumVersion** 指定版本 **1.6.5** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-135">The **MinimumVersion** specifies version **1.6.5** .</span></span> <span data-ttu-id="faa03-136">`Find-Module` 返回 PowerShellGet 版本 **2.1.0** ，因为它超过最低版本并且是最新版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-136">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="faa03-137">示例4：查找特定版本的模块</span><span class="sxs-lookup"><span data-stu-id="faa03-137">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="faa03-138">此示例将返回一个对象，该对象表示模块的特定版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-138">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="faa03-139">如果找不到指定版本，则会返回错误。</span><span class="sxs-lookup"><span data-stu-id="faa03-139">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="faa03-140">`Find-Module`Cmdlet 使用 **Name** 参数来指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-140">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="faa03-141">**RequiredVersion** 参数指定版本 **1.6.5** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-141">The **RequiredVersion** parameter specifies version **1.6.5** .</span></span>

### <span data-ttu-id="faa03-142">示例5：查找特定存储库中的模块</span><span class="sxs-lookup"><span data-stu-id="faa03-142">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="faa03-143">此示例使用 **存储库** 参数查找特定存储库中的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-143">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="faa03-144">`Find-Module`Cmdlet 使用 **Name** 参数来指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-144">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="faa03-145">**存储库** 参数指定搜索 **PSGallery** 存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-145">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="faa03-146">示例6：在多个存储库中查找模块</span><span class="sxs-lookup"><span data-stu-id="faa03-146">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="faa03-147">此示例使用 `Register-PSRepository` 指定存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-147">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="faa03-148">`Find-Module` 使用存储库搜索模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-148">`Find-Module` uses the repository to search for a module.</span></span>

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

<span data-ttu-id="faa03-149">`Register-PSRepository`Cmdlet 将注册一个新存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-149">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="faa03-150">**Name** 参数将命名为 **MySource** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-150">The **Name** parameter assigns the name **MySource** .</span></span> <span data-ttu-id="faa03-151">**SourceLocation** 参数指定存储库的地址。</span><span class="sxs-lookup"><span data-stu-id="faa03-151">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="faa03-152">`Find-Module`Cmdlet 将 **Name** 参数与星号一起使用 (`*`) 通配符来指定 **Contoso** 模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-152">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="faa03-153">**存储库** 参数指定搜索两个存储库，即 **PSGallery** 和 **MySource** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-153">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource** .</span></span>

### <span data-ttu-id="faa03-154">示例7：查找包含 DSC 资源的模块</span><span class="sxs-lookup"><span data-stu-id="faa03-154">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="faa03-155">此命令返回包含 DSC 资源的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-155">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="faa03-156">**包含** 参数具有四个用于搜索存储库的预定义功能。</span><span class="sxs-lookup"><span data-stu-id="faa03-156">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="faa03-157">使用 "选项卡-完成" 显示 **包含** 参数支持的四项功能。</span><span class="sxs-lookup"><span data-stu-id="faa03-157">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

<span data-ttu-id="faa03-158">`Find-Module`Cmdlet 使用 **存储** 库参数搜索存储库 **PSGallery** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-158">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery** .</span></span>
<span data-ttu-id="faa03-159">**包含** 参数指定 **get-dscresource** ，它是参数可在存储库中搜索的功能。</span><span class="sxs-lookup"><span data-stu-id="faa03-159">The **Includes** parameter specifies **DscResource** , which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="faa03-160">示例8：查找带有筛选器的模块</span><span class="sxs-lookup"><span data-stu-id="faa03-160">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="faa03-161">在此示例中，若要查找模块，请使用筛选器搜索存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-161">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="faa03-162">对于基于 NuGet 的存储库， **筛选器** 参数会搜索参数的名称、说明和标记。</span><span class="sxs-lookup"><span data-stu-id="faa03-162">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="faa03-163">`Find-Module`Cmdlet 使用 **筛选器** 参数在存储库中搜索 **AppDomain** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-163">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain** .</span></span>

## <span data-ttu-id="faa03-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="faa03-164">PARAMETERS</span></span>

### <span data-ttu-id="faa03-165">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="faa03-165">-AllowPrerelease</span></span>

<span data-ttu-id="faa03-166">包含在标记为预发行版的结果模块中。</span><span class="sxs-lookup"><span data-stu-id="faa03-166">Includes in the results modules marked as a pre-release.</span></span>

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

### <span data-ttu-id="faa03-167">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="faa03-167">-AllVersions</span></span>

<span data-ttu-id="faa03-168">指定在结果中包括某个模块的所有版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-168">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="faa03-169">不能将 **AllVersions** 参数与 **MinimumVersion** 、 **MaximumVersion** 或 **RequiredVersion** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="faa03-169">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="faa03-170">-Command</span><span class="sxs-lookup"><span data-stu-id="faa03-170">-Command</span></span>

<span data-ttu-id="faa03-171">指定要在模块中查找的命令数组。</span><span class="sxs-lookup"><span data-stu-id="faa03-171">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="faa03-172">命令可以是函数或工作流。</span><span class="sxs-lookup"><span data-stu-id="faa03-172">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="faa03-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="faa03-173">-Credential</span></span>

<span data-ttu-id="faa03-174">指定有权为指定的包提供程序或源安装模块的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="faa03-174">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="faa03-175">-DscResource</span><span class="sxs-lookup"><span data-stu-id="faa03-175">-DscResource</span></span>

<span data-ttu-id="faa03-176">指定包含 DSC 资源的模块的名称或名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="faa03-176">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="faa03-177">在提供多个参数时，按 PowerShell 约定执行 **或** 搜索。</span><span class="sxs-lookup"><span data-stu-id="faa03-177">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

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

### <span data-ttu-id="faa03-178">-Filter</span><span class="sxs-lookup"><span data-stu-id="faa03-178">-Filter</span></span>

<span data-ttu-id="faa03-179">基于 **PackageManagement** 提供程序特定的搜索语法指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="faa03-179">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="faa03-180">对于 NuGet 模块，此参数等效于使用 [PowerShell 库](https://www.powershellgallery.com/) 网站上的搜索栏进行搜索。</span><span class="sxs-lookup"><span data-stu-id="faa03-180">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

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

### <span data-ttu-id="faa03-181">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="faa03-181">-IncludeDependencies</span></span>

<span data-ttu-id="faa03-182">指示此操作包含依赖于在 **Name** 参数中指定的模块的所有模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-182">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="faa03-183">-Includes</span><span class="sxs-lookup"><span data-stu-id="faa03-183">-Includes</span></span>

<span data-ttu-id="faa03-184">仅返回那些包含特定类型的 PowerShell 功能的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-184">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="faa03-185">例如，你可能只想查找包含 **get-dscresource** 的模块。</span><span class="sxs-lookup"><span data-stu-id="faa03-185">For example, you might only want to find modules that include **DSCResource** .</span></span> <span data-ttu-id="faa03-186">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="faa03-186">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="faa03-187">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="faa03-187">Cmdlet</span></span>
- <span data-ttu-id="faa03-188">DscResource</span><span class="sxs-lookup"><span data-stu-id="faa03-188">DscResource</span></span>
- <span data-ttu-id="faa03-189">函数</span><span class="sxs-lookup"><span data-stu-id="faa03-189">Function</span></span>
- <span data-ttu-id="faa03-190">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="faa03-190">RoleCapability</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="faa03-191">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="faa03-191">-MaximumVersion</span></span>

<span data-ttu-id="faa03-192">指定要包括在搜索结果中的模块的最大或最新版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-192">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="faa03-193">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-193">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="faa03-194">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="faa03-194">-MinimumVersion</span></span>

<span data-ttu-id="faa03-195">指定要包括在结果中的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="faa03-195">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="faa03-196">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-196">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="faa03-197">-Name</span><span class="sxs-lookup"><span data-stu-id="faa03-197">-Name</span></span>

<span data-ttu-id="faa03-198">指定要在存储库中搜索的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="faa03-198">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="faa03-199">接受以逗号分隔的模块名称列表。</span><span class="sxs-lookup"><span data-stu-id="faa03-199">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="faa03-200">可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="faa03-200">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="faa03-201">-Proxy</span><span class="sxs-lookup"><span data-stu-id="faa03-201">-Proxy</span></span>

<span data-ttu-id="faa03-202">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="faa03-202">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="faa03-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="faa03-203">-ProxyCredential</span></span>

<span data-ttu-id="faa03-204">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="faa03-204">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="faa03-205">-Repository</span><span class="sxs-lookup"><span data-stu-id="faa03-205">-Repository</span></span>

<span data-ttu-id="faa03-206">使用 " **存储库** " 参数可以指定要搜索模块的存储库。</span><span class="sxs-lookup"><span data-stu-id="faa03-206">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="faa03-207">当注册多个存储库时使用。</span><span class="sxs-lookup"><span data-stu-id="faa03-207">Used when multiple repositories are registered.</span></span> <span data-ttu-id="faa03-208">接受以逗号分隔的存储库列表。</span><span class="sxs-lookup"><span data-stu-id="faa03-208">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="faa03-209">若要注册存储库，请使用 `Register-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="faa03-209">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="faa03-210">若要显示已注册的存储库，请使用 `Get-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="faa03-210">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="faa03-211">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="faa03-211">-RequiredVersion</span></span>

<span data-ttu-id="faa03-212">指定要包含在结果中的模块的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="faa03-212">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="faa03-213">对于 **MinimumVersion** 或 **MaximumVersion** ，不能在同一命令中使用 **RequiredVersion** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-213">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="faa03-214">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="faa03-214">-RoleCapability</span></span>

<span data-ttu-id="faa03-215">指定角色功能的数组。</span><span class="sxs-lookup"><span data-stu-id="faa03-215">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="faa03-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="faa03-216">-Tag</span></span>

<span data-ttu-id="faa03-217">指定标记的数组。</span><span class="sxs-lookup"><span data-stu-id="faa03-217">Specifies an array of tags.</span></span> <span data-ttu-id="faa03-218">示例标记包括 **DesiredStateConfiguration** 、 **DSC** 、 **DSCResourceKit** 或 **PSModule** 。</span><span class="sxs-lookup"><span data-stu-id="faa03-218">Example tags include **DesiredStateConfiguration** , **DSC** , **DSCResourceKit** , or **PSModule** .</span></span>

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

### <span data-ttu-id="faa03-219">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="faa03-219">CommonParameters</span></span>

<span data-ttu-id="faa03-220">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="faa03-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="faa03-221">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="faa03-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="faa03-222">输入</span><span class="sxs-lookup"><span data-stu-id="faa03-222">INPUTS</span></span>

### <span data-ttu-id="faa03-223">System.String[]</span><span class="sxs-lookup"><span data-stu-id="faa03-223">System.String[]</span></span>

### <span data-ttu-id="faa03-224">System.String</span><span class="sxs-lookup"><span data-stu-id="faa03-224">System.String</span></span>

### <span data-ttu-id="faa03-225">System.Uri</span><span class="sxs-lookup"><span data-stu-id="faa03-225">System.Uri</span></span>

### <span data-ttu-id="faa03-226">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="faa03-226">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="faa03-227">输出</span><span class="sxs-lookup"><span data-stu-id="faa03-227">OUTPUTS</span></span>

### <span data-ttu-id="faa03-228">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="faa03-228">PSRepositoryItemInfo</span></span>

<span data-ttu-id="faa03-229">`Find-Module` 创建可通过管道向下发送到 cmdlet （如）的 **PSRepositoryItemInfo** 对象 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="faa03-229">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="faa03-230">注释</span><span class="sxs-lookup"><span data-stu-id="faa03-230">NOTES</span></span>

<span data-ttu-id="faa03-231">此 cmdlet 在 powershell 5.0 或更高版本的 PowerShell、Windows 7 或 Windows 2008 R2 及更高版本的 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="faa03-231">This cmdlet runs on PowerShell 5.0 or later releases of PowerShell, on Windows 7, or Windows 2008 R2 and later releases of Windows.</span></span>

## <span data-ttu-id="faa03-232">相关链接</span><span class="sxs-lookup"><span data-stu-id="faa03-232">RELATED LINKS</span></span>

[<span data-ttu-id="faa03-233">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="faa03-233">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="faa03-234">Install-Module</span><span class="sxs-lookup"><span data-stu-id="faa03-234">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="faa03-235">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="faa03-235">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="faa03-236">Save-Module</span><span class="sxs-lookup"><span data-stu-id="faa03-236">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="faa03-237">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="faa03-237">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="faa03-238">Update-Module</span><span class="sxs-lookup"><span data-stu-id="faa03-238">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="faa03-239">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="faa03-239">Register-PSRepository</span></span>](Register-PSRepository.md)

