---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 9778263a0a9d5db6924579c863419e87bb27ef71
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890260"
---
# <span data-ttu-id="87977-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="87977-103">Install-Package</span></span>

## <span data-ttu-id="87977-104">摘要</span><span class="sxs-lookup"><span data-stu-id="87977-104">SYNOPSIS</span></span>
<span data-ttu-id="87977-105">安装一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="87977-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="87977-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="87977-106">SYNTAX</span></span>

### <span data-ttu-id="87977-107">PackageBySearch（默认值）</span><span class="sxs-lookup"><span data-stu-id="87977-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="87977-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="87977-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="87977-109">NuGet： PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="87977-109">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="87977-110">NuGet： PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="87977-110">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="87977-111">PowerShellGet： PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="87977-111">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="87977-112">PowerShellGet： PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="87977-112">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="87977-113">说明</span><span class="sxs-lookup"><span data-stu-id="87977-113">DESCRIPTION</span></span>

<span data-ttu-id="87977-114">`Install-Package`Cmdlet 在本地计算机上安装一个或多个软件包。</span><span class="sxs-lookup"><span data-stu-id="87977-114">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="87977-115">如果有多个软件源，请使用 `Get-PackageProvider` 和 `Get-PackageSource` 显示有关提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="87977-115">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="87977-116">示例</span><span class="sxs-lookup"><span data-stu-id="87977-116">EXAMPLES</span></span>

### <span data-ttu-id="87977-117">示例 1：按包名称安装包</span><span class="sxs-lookup"><span data-stu-id="87977-117">Example 1: Install a package by package name</span></span>

<span data-ttu-id="87977-118">`Install-Package`Cmdlet 将安装软件包及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="87977-118">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="87977-119">`Install-Package` 使用参数指定包 **名称** 和 **源**。</span><span class="sxs-lookup"><span data-stu-id="87977-119">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="87977-120">**Credential** 参数使用有权安装包的域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="87977-120">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="87977-121">该命令会提示你输入用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="87977-121">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="87977-122">示例2：使用 Find-Package 安装包</span><span class="sxs-lookup"><span data-stu-id="87977-122">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="87977-123">在此示例中，由返回的对象通过 `Find-Package` 管道向下发送，由安装 `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="87977-123">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="87977-124">`Find-Package` 使用 **名称** 和 **源** 参数定位包。</span><span class="sxs-lookup"><span data-stu-id="87977-124">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="87977-125">对象被发送到管道，并将 `Install-Package` 包安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="87977-125">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="87977-126">示例 3：通过指定版本范围安装包</span><span class="sxs-lookup"><span data-stu-id="87977-126">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="87977-127">`Install-Package` 使用 **MinimumVersion** 和 **MaximumVersion** 参数指定软件版本的范围。</span><span class="sxs-lookup"><span data-stu-id="87977-127">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="87977-128">`Install-Package` 使用 **Name** 和 **Source** 参数查找包。</span><span class="sxs-lookup"><span data-stu-id="87977-128">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="87977-129">**MinimumVersion** 和 **MaximumVersion** 参数指定软件版本的范围。</span><span class="sxs-lookup"><span data-stu-id="87977-129">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="87977-130">范围内的最高版本已安装。</span><span class="sxs-lookup"><span data-stu-id="87977-130">The highest version in the range is installed.</span></span>

## <span data-ttu-id="87977-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="87977-131">PARAMETERS</span></span>

### <span data-ttu-id="87977-132">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="87977-132">-AcceptLicense</span></span>

 <span data-ttu-id="87977-133">**AcceptLicense** 会在安装过程中自动接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="87977-133">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-134">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="87977-134">-AllowClobber</span></span>

<span data-ttu-id="87977-135">替代与现有命令冲突有关的警告消息。</span><span class="sxs-lookup"><span data-stu-id="87977-135">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="87977-136">覆盖与要安装的命令同名的现有命令。</span><span class="sxs-lookup"><span data-stu-id="87977-136">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-137">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="87977-137">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="87977-138">允许安装标记为预发行版的包。</span><span class="sxs-lookup"><span data-stu-id="87977-138">Allows the installation of packages marked as prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-139">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="87977-139">-AllVersions</span></span>

<span data-ttu-id="87977-140">`Install-Package` 安装包的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="87977-140">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="87977-141">默认情况下，仅安装最新版本。</span><span class="sxs-lookup"><span data-stu-id="87977-141">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="87977-142">-Command</span><span class="sxs-lookup"><span data-stu-id="87977-142">-Command</span></span>

<span data-ttu-id="87977-143">指定要搜索的一个或多个命令 `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="87977-143">Specifies one or more commands that `Install-Package` searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-144">-Read-configfile</span><span class="sxs-lookup"><span data-stu-id="87977-144">-ConfigFile</span></span>

<span data-ttu-id="87977-145">指定包含配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="87977-145">Specifies a path that contains a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-146">-Contains</span><span class="sxs-lookup"><span data-stu-id="87977-146">-Contains</span></span>

<span data-ttu-id="87977-147">`Install-Package` 如果 **Contains** 参数指定的值与对象的任何属性值匹配，则获取这些对象。</span><span class="sxs-lookup"><span data-stu-id="87977-147">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="87977-148">-Credential</span></span>

<span data-ttu-id="87977-149">指定有权访问计算机并运行命令的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="87977-149">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="87977-150">键入用户名，如 **User01**、 **Domain01\User01** 或输入由 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="87977-150">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="87977-151">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="87977-151">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="87977-152">如果未指定 **Credential** 参数， `Install-Package` 将使用当前用户。</span><span class="sxs-lookup"><span data-stu-id="87977-152">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="87977-153">-Destination</span><span class="sxs-lookup"><span data-stu-id="87977-153">-Destination</span></span>

<span data-ttu-id="87977-154">指定输入对象的路径。</span><span class="sxs-lookup"><span data-stu-id="87977-154">Specifies a path to an input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-155">-DscResource</span><span class="sxs-lookup"><span data-stu-id="87977-155">-DscResource</span></span>

<span data-ttu-id="87977-156">指定一个或多个所需状态配置 (由搜索的 DSC) 资源 `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="87977-156">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="87977-157">使用 `Find-DscResource` cmdlet 查找 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="87977-157">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-158">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="87977-158">-ExcludeVersion</span></span>

<span data-ttu-id="87977-159">切换到排除文件夹路径中的版本号。</span><span class="sxs-lookup"><span data-stu-id="87977-159">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="87977-160">-Filter</span></span>

<span data-ttu-id="87977-161">指定在 **Name** 和 **Description** 属性中要搜索的术语。</span><span class="sxs-lookup"><span data-stu-id="87977-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-162">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="87977-162">-FilterOnTag</span></span>

<span data-ttu-id="87977-163">指定筛选结果的标记，并排除不包含指定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="87977-163">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-164">-Force</span><span class="sxs-lookup"><span data-stu-id="87977-164">-Force</span></span>

<span data-ttu-id="87977-165">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="87977-165">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="87977-166">覆盖阻止成功的限制 `Install-Package` ，但安全性除外。</span><span class="sxs-lookup"><span data-stu-id="87977-166">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="87977-167">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="87977-167">-ForceBootstrap</span></span>

<span data-ttu-id="87977-168">强制 **PackageManagement** 为指定的包自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="87977-168">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="87977-169">-标头</span><span class="sxs-lookup"><span data-stu-id="87977-169">-Headers</span></span>

<span data-ttu-id="87977-170">指定包标头。</span><span class="sxs-lookup"><span data-stu-id="87977-170">Specifies the package headers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-171">-Includes</span><span class="sxs-lookup"><span data-stu-id="87977-171">-Includes</span></span>

<span data-ttu-id="87977-172">指定是否 `Install-Package` 应找到所有包类型。</span><span class="sxs-lookup"><span data-stu-id="87977-172">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="87977-173">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="87977-173">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="87977-174">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="87977-174">Cmdlet</span></span>
- <span data-ttu-id="87977-175">DscResource</span><span class="sxs-lookup"><span data-stu-id="87977-175">DscResource</span></span>
- <span data-ttu-id="87977-176">函数</span><span class="sxs-lookup"><span data-stu-id="87977-176">Function</span></span>
- <span data-ttu-id="87977-177">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="87977-177">RoleCapability</span></span>
- <span data-ttu-id="87977-178">工作流</span><span class="sxs-lookup"><span data-stu-id="87977-178">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="87977-179">-InputObject</span></span>

<span data-ttu-id="87977-180">接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="87977-180">Accepts pipeline input.</span></span> <span data-ttu-id="87977-181">使用包的 **softwareidentity.revisionnumber** 类型指定包。</span><span class="sxs-lookup"><span data-stu-id="87977-181">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="87977-182">`Find-Package` 输出 **softwareidentity.revisionnumber** 对象。</span><span class="sxs-lookup"><span data-stu-id="87977-182">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="87977-183">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="87977-183">-InstallUpdate</span></span>

<span data-ttu-id="87977-184">指示 `Install-Package` 安装更新。</span><span class="sxs-lookup"><span data-stu-id="87977-184">Indicates that `Install-Package` installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-185">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="87977-185">-MaximumVersion</span></span>

<span data-ttu-id="87977-186">指定要安装的最大允许包版本。</span><span class="sxs-lookup"><span data-stu-id="87977-186">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="87977-187">如果未指定此参数， `Install-Package` 将安装包的最新版本。</span><span class="sxs-lookup"><span data-stu-id="87977-187">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="87977-188">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="87977-188">-MinimumVersion</span></span>

<span data-ttu-id="87977-189">指定要安装的最小允许包版本。</span><span class="sxs-lookup"><span data-stu-id="87977-189">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="87977-190">如果不添加此参数，将 `Install-Package` 安装包的最新版本，以满足 **MaximumVersion** 参数指定的任何版本。</span><span class="sxs-lookup"><span data-stu-id="87977-190">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="87977-191">-Name</span><span class="sxs-lookup"><span data-stu-id="87977-191">-Name</span></span>

<span data-ttu-id="87977-192">指定一个或多个包名称。</span><span class="sxs-lookup"><span data-stu-id="87977-192">Specifies one or more package names.</span></span> <span data-ttu-id="87977-193">多个包名称必须用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="87977-193">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="87977-194">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="87977-194">-NoPathUpdate</span></span>

<span data-ttu-id="87977-195">**NoPathUpdate** 仅适用于 `Install-Script` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87977-195">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="87977-196">**NoPathUpdate** 是由提供程序添加的动态参数，不受支持 `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="87977-196">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-197">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="87977-197">-PackageManagementProvider</span></span>

<span data-ttu-id="87977-198">指定 **PackageManagement** 提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="87977-198">Specifies the name of the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-199">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="87977-199">-ProviderName</span></span>

<span data-ttu-id="87977-200">指定一个或多个将用作包搜索限定范围的包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="87977-200">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="87977-201">可运行 `Get-PackageProvider` cmdlet 来获取包提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="87977-201">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="87977-202">-Proxy</span><span class="sxs-lookup"><span data-stu-id="87977-202">-Proxy</span></span>

<span data-ttu-id="87977-203">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="87977-203">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="87977-204">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="87977-204">-ProxyCredential</span></span>

<span data-ttu-id="87977-205">指定有权使用 **代理** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="87977-205">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="87977-206">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="87977-206">-PublishLocation</span></span>

<span data-ttu-id="87977-207">指定包的发布位置的路径。</span><span class="sxs-lookup"><span data-stu-id="87977-207">Specifies the path to a package's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-208">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="87977-208">-RequiredVersion</span></span>

<span data-ttu-id="87977-209">指定要安装的包的确切允许版本。</span><span class="sxs-lookup"><span data-stu-id="87977-209">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="87977-210">如果不添加此参数，将 `Install-Package` 安装包的最新版本，以满足 **MaximumVersion** 参数指定的任何版本。</span><span class="sxs-lookup"><span data-stu-id="87977-210">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="87977-211">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="87977-211">-RoleCapability</span></span>

<span data-ttu-id="87977-212">指定角色功能的数组。</span><span class="sxs-lookup"><span data-stu-id="87977-212">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-213">-Scope</span><span class="sxs-lookup"><span data-stu-id="87977-213">-Scope</span></span>

<span data-ttu-id="87977-214">指定要为其安装包的作用域。</span><span class="sxs-lookup"><span data-stu-id="87977-214">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="87977-215">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="87977-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="87977-216">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="87977-216">CurrentUser</span></span>
- <span data-ttu-id="87977-217">AllUsers</span><span class="sxs-lookup"><span data-stu-id="87977-217">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-218">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="87977-218">-ScriptPublishLocation</span></span>

<span data-ttu-id="87977-219">指定脚本的发布位置的路径。</span><span class="sxs-lookup"><span data-stu-id="87977-219">Specifies the path to a script's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-220">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="87977-220">-ScriptSourceLocation</span></span>

<span data-ttu-id="87977-221">指定脚本源位置。</span><span class="sxs-lookup"><span data-stu-id="87977-221">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-222">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="87977-222">-SkipDependencies</span></span>

<span data-ttu-id="87977-223">跳过软件依赖项的安装。</span><span class="sxs-lookup"><span data-stu-id="87977-223">Skips the installation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-224">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="87977-224">-SkipPublisherCheck</span></span>

<span data-ttu-id="87977-225">允许你获取比你安装的版本更新的包版本。</span><span class="sxs-lookup"><span data-stu-id="87977-225">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="87977-226">例如，由受信任的发布者进行数字签名，但未对新版本进行数字签名的已安装包。</span><span class="sxs-lookup"><span data-stu-id="87977-226">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-227">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="87977-227">-SkipValidate</span></span>

<span data-ttu-id="87977-228">跳过验证包凭据的开关。</span><span class="sxs-lookup"><span data-stu-id="87977-228">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-229">-Source</span><span class="sxs-lookup"><span data-stu-id="87977-229">-Source</span></span>

<span data-ttu-id="87977-230">指定一个或多个包源。</span><span class="sxs-lookup"><span data-stu-id="87977-230">Specifies one or more package sources.</span></span> <span data-ttu-id="87977-231">必须用逗号分隔多个包源。</span><span class="sxs-lookup"><span data-stu-id="87977-231">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="87977-232">可以通过运行 cmdlet 获取包源名称 `Get-PackageSource` 。</span><span class="sxs-lookup"><span data-stu-id="87977-232">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="87977-233">-Tag</span><span class="sxs-lookup"><span data-stu-id="87977-233">-Tag</span></span>

<span data-ttu-id="87977-234">指定要在包元数据中搜索的一个或多个字符串。</span><span class="sxs-lookup"><span data-stu-id="87977-234">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-235">-Type</span><span class="sxs-lookup"><span data-stu-id="87977-235">-Type</span></span>

<span data-ttu-id="87977-236">指定是否使用模块、脚本或两者搜索包。</span><span class="sxs-lookup"><span data-stu-id="87977-236">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="87977-237">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="87977-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="87977-238">模块</span><span class="sxs-lookup"><span data-stu-id="87977-238">Module</span></span>
- <span data-ttu-id="87977-239">Script</span><span class="sxs-lookup"><span data-stu-id="87977-239">Script</span></span>
- <span data-ttu-id="87977-240">全部</span><span class="sxs-lookup"><span data-stu-id="87977-240">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87977-241">-Confirm</span><span class="sxs-lookup"><span data-stu-id="87977-241">-Confirm</span></span>

<span data-ttu-id="87977-242">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="87977-242">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="87977-243">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="87977-243">-WhatIf</span></span>

<span data-ttu-id="87977-244">显示在 `Install-Package` 运行 cmdlet 时会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="87977-244">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="87977-245">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="87977-245">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="87977-246">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="87977-246">CommonParameters</span></span>

<span data-ttu-id="87977-247">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="87977-247">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="87977-248">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="87977-248">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="87977-249">输入</span><span class="sxs-lookup"><span data-stu-id="87977-249">INPUTS</span></span>

### <span data-ttu-id="87977-250">`Install-Package` 接受来自管道的输入。</span><span class="sxs-lookup"><span data-stu-id="87977-250">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="87977-251">输出</span><span class="sxs-lookup"><span data-stu-id="87977-251">OUTPUTS</span></span>

### <span data-ttu-id="87977-252">SoftwareIdentity[]</span><span class="sxs-lookup"><span data-stu-id="87977-252">SoftwareIdentity[]</span></span>

## <span data-ttu-id="87977-253">注释</span><span class="sxs-lookup"><span data-stu-id="87977-253">NOTES</span></span>

<span data-ttu-id="87977-254">在命令中包含包提供程序可以使动态参数可用于 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87977-254">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="87977-255">动态参数特定于包提供程序。</span><span class="sxs-lookup"><span data-stu-id="87977-255">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="87977-256">`Get-Help`Cmdlet 列出 cmdlet 的参数集，并包括提供程序的参数集。</span><span class="sxs-lookup"><span data-stu-id="87977-256">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="87977-257">例如， `Install-Package` 具有 **PowerShellGet** 参数集，其中包括 `-NoPathUpdate` 、 `AllowClobber` 和 `SkipPublisherCheck` 。</span><span class="sxs-lookup"><span data-stu-id="87977-257">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87977-258">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="87977-258">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="87977-259">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="87977-259">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="87977-260">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="87977-260">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="87977-261">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="87977-261">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="87977-262">相关链接</span><span class="sxs-lookup"><span data-stu-id="87977-262">RELATED LINKS</span></span>

[<span data-ttu-id="87977-263">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="87977-263">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="87977-264">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="87977-264">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="87977-265">Get-Help</span><span class="sxs-lookup"><span data-stu-id="87977-265">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="87977-266">Get-Package</span><span class="sxs-lookup"><span data-stu-id="87977-266">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="87977-267">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="87977-267">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="87977-268">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="87977-268">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="87977-269">Find-Package</span><span class="sxs-lookup"><span data-stu-id="87977-269">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="87977-270">Save-Package</span><span class="sxs-lookup"><span data-stu-id="87977-270">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="87977-271">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="87977-271">Uninstall-Package</span></span>](Uninstall-Package.md)
