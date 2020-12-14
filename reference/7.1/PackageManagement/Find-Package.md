---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: f7c963b59a31b1b5edbf227e30415d6865cc14d7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891060"
---
# <span data-ttu-id="26692-103">Find-Package</span><span class="sxs-lookup"><span data-stu-id="26692-103">Find-Package</span></span>

## <span data-ttu-id="26692-104">摘要</span><span class="sxs-lookup"><span data-stu-id="26692-104">SYNOPSIS</span></span>
<span data-ttu-id="26692-105">在可用包源中查找软件包。</span><span class="sxs-lookup"><span data-stu-id="26692-105">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="26692-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="26692-106">SYNTAX</span></span>

### <span data-ttu-id="26692-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="26692-107">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="26692-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="26692-108">PowerShellGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-AllowPrereleaseVersions] [-PackageManagementProvider <String>]
 [-PublishLocation <String>] [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
 [-Type <String>] [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>]
 [-DscResource <String[]>] [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense]
 [<CommonParameters>]
```

## <span data-ttu-id="26692-109">说明</span><span class="sxs-lookup"><span data-stu-id="26692-109">DESCRIPTION</span></span>

<span data-ttu-id="26692-110">`Find-Package` 查找包源中可用的软件包。</span><span class="sxs-lookup"><span data-stu-id="26692-110">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="26692-111">`Get-PackageProvider` 并 `Get-PackageSource` 显示有关提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="26692-111">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="26692-112">示例</span><span class="sxs-lookup"><span data-stu-id="26692-112">EXAMPLES</span></span>

### <span data-ttu-id="26692-113">示例1：从包提供程序查找所有可用的包</span><span class="sxs-lookup"><span data-stu-id="26692-113">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="26692-114">此命令查找已注册库中的所有可用 PowerShell 模块包。</span><span class="sxs-lookup"><span data-stu-id="26692-114">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="26692-115">使用 `Get-PackageProvider` 获取提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="26692-115">Use `Get-PackageProvider` to get the provider name.</span></span>

```
Find-Package -ProviderName NuGet
```

```Output
Name               Version   Source     Summary
----               -------   ------     -------
NUnit              3.11.0    MyNuGet    NUnit is a unit-testing framework for all .NET langua...
Newtonsoft.Json    12.0.1    MyNuGet    Json.NET is a popular high-performance JSON framework...
EntityFramework    6.2.0     MyNuGet    Entity Framework is Microsoft's recommended data acce...
MySql.Data         8.0.15    MyNuGet    MySql.Data.MySqlClient .Net Core Class Library
bootstrap          4.3.1     MyNuGet    Bootstrap framework in CSS. Includes fonts and JavaSc...
NuGet.Core         2.14.0    MyNuGet    NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="26692-116">`Find-Package` 使用 **provider** 参数指定提供程序 **NuGet**。</span><span class="sxs-lookup"><span data-stu-id="26692-116">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet**.</span></span>

### <span data-ttu-id="26692-117">示例2：从包源中查找包</span><span class="sxs-lookup"><span data-stu-id="26692-117">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="26692-118">此命令从指定的包源中查找最新版本的包。</span><span class="sxs-lookup"><span data-stu-id="26692-118">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="26692-119">如果未提供包源，则 `Find-Package` 搜索每个已安装的包提供程序及其包源。</span><span class="sxs-lookup"><span data-stu-id="26692-119">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="26692-120">使用 `Get-PackageSource` 获取源名称。</span><span class="sxs-lookup"><span data-stu-id="26692-120">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="26692-121">`Find-Package` 使用 **Name** 参数指定包名称 **nuget.exe**。</span><span class="sxs-lookup"><span data-stu-id="26692-121">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="26692-122">**Source** 参数指定在 **MyNuGet** 中搜索包。</span><span class="sxs-lookup"><span data-stu-id="26692-122">The **Source** parameter specifies to search for the package in **MyNuGet**.</span></span>

### <span data-ttu-id="26692-123">示例3：查找包的所有版本</span><span class="sxs-lookup"><span data-stu-id="26692-123">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="26692-124">此命令从指定的提供程序中查找所有可用的包版本。</span><span class="sxs-lookup"><span data-stu-id="26692-124">This command finds all available package versions from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.14.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.14.0-rtm-832   MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.13.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
...
NuGet.Core    1.1.229.159      MyNuGet      NuGet.Core is the core framework assembly for NuGet...
Nuget.Core    1.0.1120.104     MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="26692-125">`Find-Package` 使用 **Name** 参数指定包 **nuget.exe**。</span><span class="sxs-lookup"><span data-stu-id="26692-125">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core**.</span></span> <span data-ttu-id="26692-126">**ProviderName** 参数指定在 **MyNuGet** 中搜索包。</span><span class="sxs-lookup"><span data-stu-id="26692-126">The **ProviderName** parameter specifies to search for the package in **MyNuGet**.</span></span> <span data-ttu-id="26692-127">**AllVersions** 指定返回所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="26692-127">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="26692-128">示例4：查找具有特定名称和版本的包</span><span class="sxs-lookup"><span data-stu-id="26692-128">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="26692-129">此命令从指定的提供程序中查找特定的包版本。</span><span class="sxs-lookup"><span data-stu-id="26692-129">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="26692-130">`Find-Package` 使用 **Name** 参数指定包名称 **nuget.exe**。</span><span class="sxs-lookup"><span data-stu-id="26692-130">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="26692-131">**ProviderName** 参数指定在 **NuGet** 中搜索包。</span><span class="sxs-lookup"><span data-stu-id="26692-131">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="26692-132">**RequiredVersion** 指定仅返回版本 **2.9.0** 。</span><span class="sxs-lookup"><span data-stu-id="26692-132">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="26692-133">示例5：在一系列版本中查找包</span><span class="sxs-lookup"><span data-stu-id="26692-133">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="26692-134">此命令查找指定包的一系列版本。</span><span class="sxs-lookup"><span data-stu-id="26692-134">This command finds a range of versions for a specified package.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -MinimumVersion 2.7.0 -MaximumVersion 2.9.0 -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.6            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.7.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="26692-135">`Find-Package` 使用 **Name** 参数指定包名称 **nuget.exe**。</span><span class="sxs-lookup"><span data-stu-id="26692-135">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="26692-136">**ProviderName** 参数指定在 **NuGet** 中搜索包。</span><span class="sxs-lookup"><span data-stu-id="26692-136">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="26692-137">**MinimumVersion** 指定最低版本 **2.7.0**。</span><span class="sxs-lookup"><span data-stu-id="26692-137">**MinimumVersion** specifies the lowest version **2.7.0**.</span></span> <span data-ttu-id="26692-138">**MaximumVersion** 指定最高版本 **2.9.0**。</span><span class="sxs-lookup"><span data-stu-id="26692-138">**MaximumVersion** specifies the highest version **2.9.0**.</span></span>
<span data-ttu-id="26692-139">**AllVersions** 确定按最小值和最大值指定的范围。</span><span class="sxs-lookup"><span data-stu-id="26692-139">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="26692-140">示例6：查找文件系统中的包</span><span class="sxs-lookup"><span data-stu-id="26692-140">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="26692-141">此命令查找文件扩展名 `.nupkg` 存储在本地计算机上的包。</span><span class="sxs-lookup"><span data-stu-id="26692-141">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="26692-142">文件是从库（如 **NuGet**）下载的包。</span><span class="sxs-lookup"><span data-stu-id="26692-142">The files are packages downloaded from a gallery such as the **NuGet**.</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="26692-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="26692-143">PARAMETERS</span></span>

### <span data-ttu-id="26692-144">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="26692-144">-AcceptLicense</span></span>

<span data-ttu-id="26692-145">如果包需要许可协议，则自动接受该协议。</span><span class="sxs-lookup"><span data-stu-id="26692-145">Automatically accepts a license agreement if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-146">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="26692-146">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="26692-147">在结果中包括标记为预发行版本的包。</span><span class="sxs-lookup"><span data-stu-id="26692-147">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="26692-148">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="26692-148">-AllVersions</span></span>

<span data-ttu-id="26692-149">指示 `Find-Package` 返回包的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="26692-149">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="26692-150">默认情况下， `Find-Package` 仅返回最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="26692-150">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="26692-151">-Command</span><span class="sxs-lookup"><span data-stu-id="26692-151">-Command</span></span>

<span data-ttu-id="26692-152">指定由搜索的命令数组 `Find-Package` 。</span><span class="sxs-lookup"><span data-stu-id="26692-152">Specifies an array of commands searched by `Find-Package`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-153">-Read-configfile</span><span class="sxs-lookup"><span data-stu-id="26692-153">-ConfigFile</span></span>

<span data-ttu-id="26692-154">指定配置文件。</span><span class="sxs-lookup"><span data-stu-id="26692-154">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-155">-Contains</span><span class="sxs-lookup"><span data-stu-id="26692-155">-Contains</span></span>

<span data-ttu-id="26692-156">`Find-Package` 如果对象的属性值中的任何项与指定值完全匹配，则获取对象。</span><span class="sxs-lookup"><span data-stu-id="26692-156">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="26692-157">-Credential</span></span>

<span data-ttu-id="26692-158">指定有权搜索包的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26692-158">Specifies a user account that has permission to search for packages.</span></span>

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

### <span data-ttu-id="26692-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="26692-159">-DscResource</span></span>

<span data-ttu-id="26692-160">指定一个所需状态配置的数组 (此 cmdlet 搜索的 DSC) 资源。</span><span class="sxs-lookup"><span data-stu-id="26692-160">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-161">-Filter</span><span class="sxs-lookup"><span data-stu-id="26692-161">-Filter</span></span>

<span data-ttu-id="26692-162">指定在 **Name** 和 **Description** 属性中要搜索的术语。</span><span class="sxs-lookup"><span data-stu-id="26692-162">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-163">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="26692-163">-FilterOnTag</span></span>

<span data-ttu-id="26692-164">指定筛选结果的标记。</span><span class="sxs-lookup"><span data-stu-id="26692-164">Specifies the tag that filters the results.</span></span> <span data-ttu-id="26692-165">排除不包含指定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="26692-165">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-166">-Force</span><span class="sxs-lookup"><span data-stu-id="26692-166">-Force</span></span>

<span data-ttu-id="26692-167">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="26692-167">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="26692-168">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="26692-168">-ForceBootstrap</span></span>

<span data-ttu-id="26692-169">指示 `Find-Package` 强制 **PackageManagement** 自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="26692-169">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="26692-170">-标头</span><span class="sxs-lookup"><span data-stu-id="26692-170">-Headers</span></span>

<span data-ttu-id="26692-171">指定包的标头。</span><span class="sxs-lookup"><span data-stu-id="26692-171">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-172">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="26692-172">-IncludeDependencies</span></span>

<span data-ttu-id="26692-173">指示此 cmdlet 在结果中包括包依赖关系。</span><span class="sxs-lookup"><span data-stu-id="26692-173">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="26692-174">-Includes</span><span class="sxs-lookup"><span data-stu-id="26692-174">-Includes</span></span>

<span data-ttu-id="26692-175">指定是否 `Find-Package` 应查找某个类别中的所有包。</span><span class="sxs-lookup"><span data-stu-id="26692-175">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="26692-176">接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="26692-176">The accepted values are as follows:</span></span>

- <span data-ttu-id="26692-177">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="26692-177">Cmdlet</span></span>
- <span data-ttu-id="26692-178">DscResource</span><span class="sxs-lookup"><span data-stu-id="26692-178">DscResource</span></span>
- <span data-ttu-id="26692-179">函数</span><span class="sxs-lookup"><span data-stu-id="26692-179">Function</span></span>
- <span data-ttu-id="26692-180">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="26692-180">RoleCapability</span></span>
- <span data-ttu-id="26692-181">工作流</span><span class="sxs-lookup"><span data-stu-id="26692-181">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-182">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="26692-182">-MaximumVersion</span></span>

<span data-ttu-id="26692-183">指定要查找的最大包版本。</span><span class="sxs-lookup"><span data-stu-id="26692-183">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="26692-184">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="26692-184">-MinimumVersion</span></span>

<span data-ttu-id="26692-185">指定要查找的最小包版本。</span><span class="sxs-lookup"><span data-stu-id="26692-185">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="26692-186">如果有更高版本，则返回该版本。</span><span class="sxs-lookup"><span data-stu-id="26692-186">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="26692-187">-Name</span><span class="sxs-lookup"><span data-stu-id="26692-187">-Name</span></span>

<span data-ttu-id="26692-188">指定一个或多个包名称或包名称，其中包含通配符。</span><span class="sxs-lookup"><span data-stu-id="26692-188">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="26692-189">用逗号分隔多个包名称。</span><span class="sxs-lookup"><span data-stu-id="26692-189">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="26692-190">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="26692-190">-PackageManagementProvider</span></span>

<span data-ttu-id="26692-191">指定包管理提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="26692-191">Specifies the name of a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-192">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="26692-192">-ProviderName</span></span>

<span data-ttu-id="26692-193">指定一个或多个包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="26692-193">Specifies one or more package provider names.</span></span> <span data-ttu-id="26692-194">用逗号分隔多个包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="26692-194">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="26692-195">使用 `Get-PackageProvider` 获取可用包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="26692-195">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26692-196">-Proxy</span><span class="sxs-lookup"><span data-stu-id="26692-196">-Proxy</span></span>

<span data-ttu-id="26692-197">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="26692-197">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="26692-198">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="26692-198">-ProxyCredential</span></span>

<span data-ttu-id="26692-199">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26692-199">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="26692-200">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="26692-200">-PublishLocation</span></span>

<span data-ttu-id="26692-201">指定发布包的位置。</span><span class="sxs-lookup"><span data-stu-id="26692-201">Specifies a location for publishing the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-202">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="26692-202">-RequiredVersion</span></span>

<span data-ttu-id="26692-203">指定要查找的确切包版本。</span><span class="sxs-lookup"><span data-stu-id="26692-203">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="26692-204">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="26692-204">-RoleCapability</span></span>

<span data-ttu-id="26692-205">指定角色功能的数组。</span><span class="sxs-lookup"><span data-stu-id="26692-205">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-206">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="26692-206">-ScriptPublishLocation</span></span>

<span data-ttu-id="26692-207">指定包的脚本发布位置。</span><span class="sxs-lookup"><span data-stu-id="26692-207">Specifies a script publishing location for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-208">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="26692-208">-ScriptSourceLocation</span></span>

<span data-ttu-id="26692-209">指定脚本源位置。</span><span class="sxs-lookup"><span data-stu-id="26692-209">Specifies a script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-210">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="26692-210">-SkipValidate</span></span>

<span data-ttu-id="26692-211">用于跳过包凭据验证的开关。</span><span class="sxs-lookup"><span data-stu-id="26692-211">Switch that skips package credential validation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-212">-Source</span><span class="sxs-lookup"><span data-stu-id="26692-212">-Source</span></span>

<span data-ttu-id="26692-213">指定一个或多个包源。</span><span class="sxs-lookup"><span data-stu-id="26692-213">Specifies one or more package sources.</span></span> <span data-ttu-id="26692-214">使用 `Get-PackageSource` 获取可用包源的列表。</span><span class="sxs-lookup"><span data-stu-id="26692-214">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="26692-215">文件系统目录可用作下载包的源。</span><span class="sxs-lookup"><span data-stu-id="26692-215">A file system directory can be used as a source for download packages.</span></span>

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

### <span data-ttu-id="26692-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="26692-216">-Tag</span></span>

<span data-ttu-id="26692-217">指定要在包元数据中搜索的一个或多个字符串。</span><span class="sxs-lookup"><span data-stu-id="26692-217">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-218">-Type</span><span class="sxs-lookup"><span data-stu-id="26692-218">-Type</span></span>

<span data-ttu-id="26692-219">指定是使用模块、脚本还是搜索包。</span><span class="sxs-lookup"><span data-stu-id="26692-219">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26692-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="26692-220">CommonParameters</span></span>

<span data-ttu-id="26692-221">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="26692-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="26692-222">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="26692-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="26692-223">输入</span><span class="sxs-lookup"><span data-stu-id="26692-223">INPUTS</span></span>

### <span data-ttu-id="26692-224">无</span><span class="sxs-lookup"><span data-stu-id="26692-224">None</span></span>

<span data-ttu-id="26692-225">`Find-Package` 不接受来自管道的输入。</span><span class="sxs-lookup"><span data-stu-id="26692-225">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="26692-226">输出</span><span class="sxs-lookup"><span data-stu-id="26692-226">OUTPUTS</span></span>

### <span data-ttu-id="26692-227">SoftwareIdentify[]</span><span class="sxs-lookup"><span data-stu-id="26692-227">SoftwareIdentify[]</span></span>

<span data-ttu-id="26692-228">`Find-Package` 输出 **softwareidentity.revisionnumber** 对象。</span><span class="sxs-lookup"><span data-stu-id="26692-228">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="26692-229">注释</span><span class="sxs-lookup"><span data-stu-id="26692-229">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26692-230">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="26692-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="26692-231">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="26692-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="26692-232">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="26692-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="26692-233">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="26692-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="26692-234">相关链接</span><span class="sxs-lookup"><span data-stu-id="26692-234">RELATED LINKS</span></span>

[<span data-ttu-id="26692-235">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="26692-235">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="26692-236">Get-Package</span><span class="sxs-lookup"><span data-stu-id="26692-236">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="26692-237">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="26692-237">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="26692-238">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="26692-238">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="26692-239">Install-Package</span><span class="sxs-lookup"><span data-stu-id="26692-239">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="26692-240">Save-Package</span><span class="sxs-lookup"><span data-stu-id="26692-240">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="26692-241">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="26692-241">Uninstall-Package</span></span>](Uninstall-Package.md)
