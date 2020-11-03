---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 6f22da7040413f64e9e96a7df57401a0701156bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197747"
---
# <span data-ttu-id="2c1c6-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="2c1c6-103">Uninstall-Package</span></span>

## <span data-ttu-id="2c1c6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2c1c6-104">SYNOPSIS</span></span>
<span data-ttu-id="2c1c6-105">卸载一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="2c1c6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c1c6-106">SYNTAX</span></span>

### <span data-ttu-id="2c1c6-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="2c1c6-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-108">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="2c1c6-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-109">msi:PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="2c1c6-109">msi:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-110">msi:PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="2c1c6-110">msi:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-111">Programs:PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="2c1c6-111">Programs:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-112">Programs:PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="2c1c6-112">Programs:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-113">NuGet： PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="2c1c6-113">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-114">NuGet： PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="2c1c6-114">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-115">PowerShellGet： PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="2c1c6-115">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="2c1c6-116">PowerShellGet： PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="2c1c6-116">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="2c1c6-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c1c6-117">DESCRIPTION</span></span>

<span data-ttu-id="2c1c6-118">`Uninstall-Package`Cmdlet 从本地计算机中卸载一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-118">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="2c1c6-119">若要查找已安装的包，请使用 `Get-Package` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-119">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="2c1c6-120">示例</span><span class="sxs-lookup"><span data-stu-id="2c1c6-120">EXAMPLES</span></span>

### <span data-ttu-id="2c1c6-121">示例1：卸载包</span><span class="sxs-lookup"><span data-stu-id="2c1c6-121">Example 1: Uninstall a package</span></span>

<span data-ttu-id="2c1c6-122">`Uninstall-Package`Cmdlet 将卸载包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-122">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="2c1c6-123">**Name** 参数指定要卸载的包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-123">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="2c1c6-124">如果安装了包的多个版本，则会卸载最新版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-124">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="2c1c6-125">示例2：使用管道卸载包</span><span class="sxs-lookup"><span data-stu-id="2c1c6-125">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="2c1c6-126">`Get-Package` 查找特定包，并将 **softwareidentity.revisionnumber** 对象向下发送到 `Uninsall-Package` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-126">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="2c1c6-127">`Get-Package`Cmdlet 使用 **Name** 和 **RequiredVersion** 参数来指定包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-127">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="2c1c6-128">**Softwareidentity.revisionnumber** 对象沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-128">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="2c1c6-129">`Uninstall-Package`Cmdlet 接收对象作为 **InputObject** ，并删除包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-129">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="2c1c6-130">作为替代方法，该 `Uninstall-Package` cmdlet 可以为 **InputObject** 参数指定值：</span><span class="sxs-lookup"><span data-stu-id="2c1c6-130">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="2c1c6-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c1c6-131">PARAMETERS</span></span>

### <span data-ttu-id="2c1c6-132">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="2c1c6-132">-AllowClobber</span></span>

<span data-ttu-id="2c1c6-133">替代与现有命令冲突有关的警告消息。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-133">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="2c1c6-134">覆盖与要安装的命令同名的现有命令。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-134">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-135">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="2c1c6-135">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="2c1c6-136">允许卸载标记为预发布的包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-136">Allows packages marked as prerelease to be uninstalled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-137">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="2c1c6-137">-AllVersions</span></span>

<span data-ttu-id="2c1c6-138">指示此 cmdlet 将卸载包的所有版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-138">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="2c1c6-139">-Destination</span><span class="sxs-lookup"><span data-stu-id="2c1c6-139">-Destination</span></span>

<span data-ttu-id="2c1c6-140">指定输入对象的路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-140">Specifies a string of the path to the input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-141">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="2c1c6-141">-ExcludeVersion</span></span>

<span data-ttu-id="2c1c6-142">切换到排除文件夹路径中的版本号。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-142">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-143">-Force</span><span class="sxs-lookup"><span data-stu-id="2c1c6-143">-Force</span></span>

<span data-ttu-id="2c1c6-144">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2c1c6-145">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="2c1c6-145">-ForceBootstrap</span></span>

<span data-ttu-id="2c1c6-146">强制 **PackageManagement** 为指定的包自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-146">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="2c1c6-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2c1c6-147">-InputObject</span></span>

<span data-ttu-id="2c1c6-148">接受从 cmdlet 指定包的 **softwareidentity.revisionnumber** 对象的管道输入 `Get-Package` 。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-148">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="2c1c6-149">**InputObject** 接受 **softwareidentity.revisionnumber** 对象作为 `Get-Package` 值或包含该对象的变量。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-149">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="2c1c6-150">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="2c1c6-150">-InstallUpdate</span></span>

<span data-ttu-id="2c1c6-151">指示 `Uninstall-Package` 卸载更新。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-151">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-152">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2c1c6-152">-MaximumVersion</span></span>

<span data-ttu-id="2c1c6-153">指定要卸载的允许的最大包版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-153">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="2c1c6-154">如果未指定此参数， `Uninstall-Package` 将卸载包的最新版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-154">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="2c1c6-155">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2c1c6-155">-MinimumVersion</span></span>

<span data-ttu-id="2c1c6-156">指定要卸载的允许的最小包版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-156">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="2c1c6-157">如果不添加此参数，则会 `Uninstall-Package` 卸载包的最新版本，该版本满足 **MaximumVersion** 参数指定的任何版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-157">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="2c1c6-158">-Name</span><span class="sxs-lookup"><span data-stu-id="2c1c6-158">-Name</span></span>

<span data-ttu-id="2c1c6-159">指定一个或多个包名称。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-159">Specifies one or more package names.</span></span> <span data-ttu-id="2c1c6-160">多个包名称必须用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-160">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="2c1c6-161">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="2c1c6-161">-NoPathUpdate</span></span>

<span data-ttu-id="2c1c6-162">**NoPathUpdate** 仅适用于 `Install-Script` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-162">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="2c1c6-163">**NoPathUpdate** 是由提供程序添加的动态参数，不受支持 `Uninstall-Package` 。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-163">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-164">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="2c1c6-164">-PackageManagementProvider</span></span>

<span data-ttu-id="2c1c6-165">指定 **PackageManagement** 提供程序。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-165">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-166">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="2c1c6-166">-ProviderName</span></span>

<span data-ttu-id="2c1c6-167">指定一个或多个包提供程序名称以搜索包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-167">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="2c1c6-168">可运行 `Get-PackageProvider` cmdlet 来获取包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-168">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2c1c6-169">-RequiredVersion</span></span>

<span data-ttu-id="2c1c6-170">指定要卸载的程序包的确切允许版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-170">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="2c1c6-171">如果不添加此参数，则会 `Uninstall-Package` 卸载包的最新版本，该版本满足 **MaximumVersion** 参数指定的任何版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-171">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="2c1c6-172">-Scope</span><span class="sxs-lookup"><span data-stu-id="2c1c6-172">-Scope</span></span>

<span data-ttu-id="2c1c6-173">指定要为其卸载包的作用域。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-173">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="2c1c6-174">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c1c6-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2c1c6-175">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="2c1c6-175">CurrentUser</span></span>
- <span data-ttu-id="2c1c6-176">AllUsers</span><span class="sxs-lookup"><span data-stu-id="2c1c6-176">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch, PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-177">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="2c1c6-177">-SkipDependencies</span></span>

<span data-ttu-id="2c1c6-178">跳过软件依赖项的卸载。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-178">Skips the uninstallation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-179">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="2c1c6-179">-SkipPublisherCheck</span></span>

<span data-ttu-id="2c1c6-180">允许你获取比你安装的版本更新的包版本。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-180">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="2c1c6-181">例如，由受信任的发布者进行数字签名，但未对新版本进行数字签名的已安装包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-181">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-182">-Type</span><span class="sxs-lookup"><span data-stu-id="2c1c6-182">-Type</span></span>

<span data-ttu-id="2c1c6-183">指定是否使用模块、脚本或两者搜索包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-183">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="2c1c6-184">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c1c6-184">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2c1c6-185">模块</span><span class="sxs-lookup"><span data-stu-id="2c1c6-185">Module</span></span>
- <span data-ttu-id="2c1c6-186">Script</span><span class="sxs-lookup"><span data-stu-id="2c1c6-186">Script</span></span>
- <span data-ttu-id="2c1c6-187">全部</span><span class="sxs-lookup"><span data-stu-id="2c1c6-187">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2c1c6-188">-Confirm</span></span>

<span data-ttu-id="2c1c6-189">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-189">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2c1c6-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2c1c6-190">-WhatIf</span></span>

<span data-ttu-id="2c1c6-191">显示在 `Uninstall-Package` 运行 cmdlet 时会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-191">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="2c1c6-192">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-192">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2c1c6-193">-AdditionalArguments</span><span class="sxs-lookup"><span data-stu-id="2c1c6-193">-AdditionalArguments</span></span>

<span data-ttu-id="2c1c6-194">指定其他参数。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-194">Specifies additional arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageByInputObject, msi:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-195">-IncludeSystemComponent</span><span class="sxs-lookup"><span data-stu-id="2c1c6-195">-IncludeSystemComponent</span></span>

<span data-ttu-id="2c1c6-196">指定此 cmdlet 将卸载系统组件。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-196">Specifies that this cmdlet uninstalls system components.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageByInputObject, Programs:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-197">-IncludeWindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="2c1c6-197">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="2c1c6-198">指示此 cmdlet 通过 Windows Installer 卸载包。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-198">Indicates that this cmdlet uninstalls the package through Windows Installer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageByInputObject, Programs:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c1c6-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c1c6-199">CommonParameters</span></span>

<span data-ttu-id="2c1c6-200">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c1c6-201">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c1c6-202">输入</span><span class="sxs-lookup"><span data-stu-id="2c1c6-202">INPUTS</span></span>

### <span data-ttu-id="2c1c6-203">`Uninstall-Package` 接受管道中的 **softwareidentity.revisionnumber** 对象作为输入。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-203">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="2c1c6-204">输出</span><span class="sxs-lookup"><span data-stu-id="2c1c6-204">OUTPUTS</span></span>

### <span data-ttu-id="2c1c6-205">`Uninstall-Package` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-205">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="2c1c6-206">注释</span><span class="sxs-lookup"><span data-stu-id="2c1c6-206">NOTES</span></span>

<span data-ttu-id="2c1c6-207">在命令中包含包提供程序可以使动态参数可用于 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-207">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="2c1c6-208">动态参数特定于包提供程序。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-208">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="2c1c6-209">`Get-Help`Cmdlet 列出 cmdlet 的参数集，并包括提供程序的参数集。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-209">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="2c1c6-210">例如， `Uninstall-Package` 具有 **PowerShellGet** 参数集，其中包括 `-NoPathUpdate` 、 `AllowClobber` 和 `SkipPublisherCheck` 。</span><span class="sxs-lookup"><span data-stu-id="2c1c6-210">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="2c1c6-211">相关链接</span><span class="sxs-lookup"><span data-stu-id="2c1c6-211">RELATED LINKS</span></span>

[<span data-ttu-id="2c1c6-212">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="2c1c6-212">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="2c1c6-213">Find-Package</span><span class="sxs-lookup"><span data-stu-id="2c1c6-213">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="2c1c6-214">Get-Package</span><span class="sxs-lookup"><span data-stu-id="2c1c6-214">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="2c1c6-215">Install-Package</span><span class="sxs-lookup"><span data-stu-id="2c1c6-215">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="2c1c6-216">Save-Package</span><span class="sxs-lookup"><span data-stu-id="2c1c6-216">Save-Package</span></span>](Save-Package.md)
