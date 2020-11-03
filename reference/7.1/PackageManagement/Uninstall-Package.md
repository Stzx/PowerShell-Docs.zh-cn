---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 4da97d9643483db0eae4fc7d34e0e6997d16bd04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198372"
---
# <span data-ttu-id="9c286-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="9c286-103">Uninstall-Package</span></span>

## <span data-ttu-id="9c286-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9c286-104">SYNOPSIS</span></span>
<span data-ttu-id="9c286-105">卸载一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="9c286-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="9c286-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c286-106">SYNTAX</span></span>

### <span data-ttu-id="9c286-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9c286-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9c286-108">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9c286-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9c286-109">NuGet： PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9c286-109">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="9c286-110">NuGet： PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9c286-110">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="9c286-111">PowerShellGet： PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9c286-111">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="9c286-112">PowerShellGet： PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9c286-112">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="9c286-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c286-113">DESCRIPTION</span></span>

<span data-ttu-id="9c286-114">`Uninstall-Package`Cmdlet 从本地计算机中卸载一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="9c286-114">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="9c286-115">若要查找已安装的包，请使用 `Get-Package` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c286-115">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="9c286-116">示例</span><span class="sxs-lookup"><span data-stu-id="9c286-116">EXAMPLES</span></span>

### <span data-ttu-id="9c286-117">示例1：卸载包</span><span class="sxs-lookup"><span data-stu-id="9c286-117">Example 1: Uninstall a package</span></span>

<span data-ttu-id="9c286-118">`Uninstall-Package`Cmdlet 将卸载包。</span><span class="sxs-lookup"><span data-stu-id="9c286-118">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="9c286-119">**Name** 参数指定要卸载的包。</span><span class="sxs-lookup"><span data-stu-id="9c286-119">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="9c286-120">如果安装了包的多个版本，则会卸载最新版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-120">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="9c286-121">示例2：使用管道卸载包</span><span class="sxs-lookup"><span data-stu-id="9c286-121">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="9c286-122">`Get-Package` 查找特定包，并将 **softwareidentity.revisionnumber** 对象向下发送到 `Uninsall-Package` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c286-122">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="9c286-123">`Get-Package`Cmdlet 使用 **Name** 和 **RequiredVersion** 参数来指定包。</span><span class="sxs-lookup"><span data-stu-id="9c286-123">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="9c286-124">**Softwareidentity.revisionnumber** 对象沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="9c286-124">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="9c286-125">`Uninstall-Package`Cmdlet 接收对象作为 **InputObject** ，并删除包。</span><span class="sxs-lookup"><span data-stu-id="9c286-125">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="9c286-126">作为替代方法，该 `Uninstall-Package` cmdlet 可以为 **InputObject** 参数指定值：</span><span class="sxs-lookup"><span data-stu-id="9c286-126">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="9c286-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c286-127">PARAMETERS</span></span>

### <span data-ttu-id="9c286-128">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="9c286-128">-AllowClobber</span></span>

<span data-ttu-id="9c286-129">替代与现有命令冲突有关的警告消息。</span><span class="sxs-lookup"><span data-stu-id="9c286-129">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="9c286-130">覆盖与要安装的命令同名的现有命令。</span><span class="sxs-lookup"><span data-stu-id="9c286-130">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="9c286-131">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="9c286-131">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="9c286-132">允许卸载标记为预发布的包。</span><span class="sxs-lookup"><span data-stu-id="9c286-132">Allows packages marked as prerelease to be uninstalled.</span></span>

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

### <span data-ttu-id="9c286-133">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="9c286-133">-AllVersions</span></span>

<span data-ttu-id="9c286-134">指示此 cmdlet 将卸载包的所有版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-134">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="9c286-135">-Destination</span><span class="sxs-lookup"><span data-stu-id="9c286-135">-Destination</span></span>

<span data-ttu-id="9c286-136">指定输入对象的路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="9c286-136">Specifies a string of the path to the input object.</span></span>

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

### <span data-ttu-id="9c286-137">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="9c286-137">-ExcludeVersion</span></span>

<span data-ttu-id="9c286-138">切换到排除文件夹路径中的版本号。</span><span class="sxs-lookup"><span data-stu-id="9c286-138">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="9c286-139">-Force</span><span class="sxs-lookup"><span data-stu-id="9c286-139">-Force</span></span>

<span data-ttu-id="9c286-140">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="9c286-140">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9c286-141">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="9c286-141">-ForceBootstrap</span></span>

<span data-ttu-id="9c286-142">强制 **PackageManagement** 为指定的包自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="9c286-142">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="9c286-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9c286-143">-InputObject</span></span>

<span data-ttu-id="9c286-144">接受从 cmdlet 指定包的 **softwareidentity.revisionnumber** 对象的管道输入 `Get-Package` 。</span><span class="sxs-lookup"><span data-stu-id="9c286-144">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="9c286-145">**InputObject** 接受 **softwareidentity.revisionnumber** 对象作为 `Get-Package` 值或包含该对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9c286-145">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="9c286-146">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="9c286-146">-InstallUpdate</span></span>

<span data-ttu-id="9c286-147">指示 `Uninstall-Package` 卸载更新。</span><span class="sxs-lookup"><span data-stu-id="9c286-147">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

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

### <span data-ttu-id="9c286-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9c286-148">-MaximumVersion</span></span>

<span data-ttu-id="9c286-149">指定要卸载的允许的最大包版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-149">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="9c286-150">如果未指定此参数， `Uninstall-Package` 将卸载包的最新版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-150">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="9c286-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9c286-151">-MinimumVersion</span></span>

<span data-ttu-id="9c286-152">指定要卸载的允许的最小包版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-152">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="9c286-153">如果不添加此参数，则会 `Uninstall-Package` 卸载包的最新版本，该版本满足 **MaximumVersion** 参数指定的任何版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-153">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="9c286-154">-Name</span><span class="sxs-lookup"><span data-stu-id="9c286-154">-Name</span></span>

<span data-ttu-id="9c286-155">指定一个或多个包名称。</span><span class="sxs-lookup"><span data-stu-id="9c286-155">Specifies one or more package names.</span></span> <span data-ttu-id="9c286-156">多个包名称必须用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="9c286-156">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="9c286-157">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="9c286-157">-NoPathUpdate</span></span>

<span data-ttu-id="9c286-158">**NoPathUpdate** 仅适用于 `Install-Script` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c286-158">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="9c286-159">**NoPathUpdate** 是由提供程序添加的动态参数，不受支持 `Uninstall-Package` 。</span><span class="sxs-lookup"><span data-stu-id="9c286-159">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

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

### <span data-ttu-id="9c286-160">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="9c286-160">-PackageManagementProvider</span></span>

<span data-ttu-id="9c286-161">指定 **PackageManagement** 提供程序。</span><span class="sxs-lookup"><span data-stu-id="9c286-161">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="9c286-162">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="9c286-162">-ProviderName</span></span>

<span data-ttu-id="9c286-163">指定一个或多个包提供程序名称以搜索包。</span><span class="sxs-lookup"><span data-stu-id="9c286-163">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="9c286-164">可运行 `Get-PackageProvider` cmdlet 来获取包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="9c286-164">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="9c286-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9c286-165">-RequiredVersion</span></span>

<span data-ttu-id="9c286-166">指定要卸载的程序包的确切允许版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-166">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="9c286-167">如果不添加此参数，则会 `Uninstall-Package` 卸载包的最新版本，该版本满足 **MaximumVersion** 参数指定的任何版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-167">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="9c286-168">-Scope</span><span class="sxs-lookup"><span data-stu-id="9c286-168">-Scope</span></span>

<span data-ttu-id="9c286-169">指定要为其卸载包的作用域。</span><span class="sxs-lookup"><span data-stu-id="9c286-169">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="9c286-170">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="9c286-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9c286-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="9c286-171">CurrentUser</span></span>
- <span data-ttu-id="9c286-172">AllUsers</span><span class="sxs-lookup"><span data-stu-id="9c286-172">AllUsers</span></span>

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

### <span data-ttu-id="9c286-173">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="9c286-173">-SkipDependencies</span></span>

<span data-ttu-id="9c286-174">跳过软件依赖项的卸载。</span><span class="sxs-lookup"><span data-stu-id="9c286-174">Skips the uninstallation of software dependencies.</span></span>

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

### <span data-ttu-id="9c286-175">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="9c286-175">-SkipPublisherCheck</span></span>

<span data-ttu-id="9c286-176">允许你获取比你安装的版本更新的包版本。</span><span class="sxs-lookup"><span data-stu-id="9c286-176">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="9c286-177">例如，由受信任的发布者进行数字签名，但未对新版本进行数字签名的已安装包。</span><span class="sxs-lookup"><span data-stu-id="9c286-177">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="9c286-178">-Type</span><span class="sxs-lookup"><span data-stu-id="9c286-178">-Type</span></span>

<span data-ttu-id="9c286-179">指定是否使用模块、脚本或两者搜索包。</span><span class="sxs-lookup"><span data-stu-id="9c286-179">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="9c286-180">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="9c286-180">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9c286-181">模块</span><span class="sxs-lookup"><span data-stu-id="9c286-181">Module</span></span>
- <span data-ttu-id="9c286-182">Script</span><span class="sxs-lookup"><span data-stu-id="9c286-182">Script</span></span>
- <span data-ttu-id="9c286-183">全部</span><span class="sxs-lookup"><span data-stu-id="9c286-183">All</span></span>

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

### <span data-ttu-id="9c286-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9c286-184">-Confirm</span></span>

<span data-ttu-id="9c286-185">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="9c286-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9c286-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9c286-186">-WhatIf</span></span>

<span data-ttu-id="9c286-187">显示在 `Uninstall-Package` 运行 cmdlet 时会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="9c286-187">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="9c286-188">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="9c286-188">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9c286-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c286-189">CommonParameters</span></span>

<span data-ttu-id="9c286-190">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9c286-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c286-191">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9c286-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c286-192">输入</span><span class="sxs-lookup"><span data-stu-id="9c286-192">INPUTS</span></span>

### <span data-ttu-id="9c286-193">`Uninstall-Package` 接受管道中的 **softwareidentity.revisionnumber** 对象作为输入。</span><span class="sxs-lookup"><span data-stu-id="9c286-193">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="9c286-194">输出</span><span class="sxs-lookup"><span data-stu-id="9c286-194">OUTPUTS</span></span>

### <span data-ttu-id="9c286-195">`Uninstall-Package` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="9c286-195">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="9c286-196">注释</span><span class="sxs-lookup"><span data-stu-id="9c286-196">NOTES</span></span>

<span data-ttu-id="9c286-197">在命令中包含包提供程序可以使动态参数可用于 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c286-197">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="9c286-198">动态参数特定于包提供程序。</span><span class="sxs-lookup"><span data-stu-id="9c286-198">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="9c286-199">`Get-Help`Cmdlet 列出 cmdlet 的参数集，并包括提供程序的参数集。</span><span class="sxs-lookup"><span data-stu-id="9c286-199">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="9c286-200">例如， `Uninstall-Package` 具有 **PowerShellGet** 参数集，其中包括 `-NoPathUpdate` 、 `AllowClobber` 和 `SkipPublisherCheck` 。</span><span class="sxs-lookup"><span data-stu-id="9c286-200">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="9c286-201">相关链接</span><span class="sxs-lookup"><span data-stu-id="9c286-201">RELATED LINKS</span></span>

[<span data-ttu-id="9c286-202">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="9c286-202">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="9c286-203">Find-Package</span><span class="sxs-lookup"><span data-stu-id="9c286-203">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="9c286-204">Get-Package</span><span class="sxs-lookup"><span data-stu-id="9c286-204">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="9c286-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="9c286-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="9c286-206">Save-Package</span><span class="sxs-lookup"><span data-stu-id="9c286-206">Save-Package</span></span>](Save-Package.md)

