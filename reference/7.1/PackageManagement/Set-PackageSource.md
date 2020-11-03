---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: ad5384f7d708cc708991d4150bf883139007ae1b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198373"
---
# <span data-ttu-id="e5f5d-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e5f5d-103">Set-PackageSource</span></span>

## <span data-ttu-id="e5f5d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e5f5d-104">SYNOPSIS</span></span>
<span data-ttu-id="e5f5d-105">替换指定包提供程序的包源。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="e5f5d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5f5d-106">SYNTAX</span></span>

### <span data-ttu-id="e5f5d-107">SourceBySearch (默认值) </span><span class="sxs-lookup"><span data-stu-id="e5f5d-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="e5f5d-108">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="e5f5d-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e5f5d-109">NuGet： SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="e5f5d-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="e5f5d-110">NuGet： SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="e5f5d-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="e5f5d-111">PowerShellGet： SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="e5f5d-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="e5f5d-112">PowerShellGet： SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="e5f5d-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="e5f5d-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5f5d-113">DESCRIPTION</span></span>

<span data-ttu-id="e5f5d-114">`Set-PackageSource`替换指定包提供程序的包源。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="e5f5d-115">包源始终由包提供程序进行管理。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="e5f5d-116">示例</span><span class="sxs-lookup"><span data-stu-id="e5f5d-116">EXAMPLES</span></span>

### <span data-ttu-id="e5f5d-117">示例1：更改包源</span><span class="sxs-lookup"><span data-stu-id="e5f5d-117">Example 1: Change a package source</span></span>

<span data-ttu-id="e5f5d-118">此命令更改包源的现有名称。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="e5f5d-119">源设置为 " **受信任** "，这会在安装包时消除用于验证源的提示。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-119">The source is set to **Trusted** , which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="e5f5d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5f5d-120">PARAMETERS</span></span>

### <span data-ttu-id="e5f5d-121">-Read-configfile</span><span class="sxs-lookup"><span data-stu-id="e5f5d-121">-ConfigFile</span></span>

<span data-ttu-id="e5f5d-122">指定配置文件。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="e5f5d-123">-Credential</span></span>

<span data-ttu-id="e5f5d-124">指定有权安装包提供程序的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-124">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="e5f5d-125">-Force</span><span class="sxs-lookup"><span data-stu-id="e5f5d-125">-Force</span></span>

<span data-ttu-id="e5f5d-126">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e5f5d-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e5f5d-127">-ForceBootstrap</span></span>

<span data-ttu-id="e5f5d-128">指示 `Set-PackageSource` 强制 **PackageManagement** 自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="e5f5d-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e5f5d-129">-InputObject</span></span>

<span data-ttu-id="e5f5d-130">指定表示要更改的包的包源 ID 对象。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="e5f5d-131">包源 Id 是 cmdlet 结果的一部分 `Get-PackageSource` 。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-132">-Location</span><span class="sxs-lookup"><span data-stu-id="e5f5d-132">-Location</span></span>

<span data-ttu-id="e5f5d-133">指定当前包的源位置。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-133">Specifies the current package source location.</span></span> <span data-ttu-id="e5f5d-134">该值可以是 URI、文件路径或包提供程序支持的任何其他目标格式。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-135">-Name</span><span class="sxs-lookup"><span data-stu-id="e5f5d-135">-Name</span></span>

<span data-ttu-id="e5f5d-136">指定包源的名称。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-136">Specifies a package source's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: SourceName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="e5f5d-137">-NewLocation</span></span>

<span data-ttu-id="e5f5d-138">指定包源的新位置。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="e5f5d-139">该值可以是 URI、文件路径或包提供程序支持的任何其他目标格式。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="e5f5d-140">-NewName</span><span class="sxs-lookup"><span data-stu-id="e5f5d-140">-NewName</span></span>

<span data-ttu-id="e5f5d-141">指定分配给包源的新名称。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-141">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="e5f5d-142">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="e5f5d-142">-PackageManagementProvider</span></span>

<span data-ttu-id="e5f5d-143">指定包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-143">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="e5f5d-144">-ProviderName</span></span>

<span data-ttu-id="e5f5d-145">指定提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-145">Specifies a provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-146">-Proxy</span><span class="sxs-lookup"><span data-stu-id="e5f5d-146">-Proxy</span></span>

<span data-ttu-id="e5f5d-147">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="e5f5d-148">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e5f5d-148">-ProxyCredential</span></span>

<span data-ttu-id="e5f5d-149">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e5f5d-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="e5f5d-150">-PublishLocation</span></span>

<span data-ttu-id="e5f5d-151">指定发布位置。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="e5f5d-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="e5f5d-153">指定脚本发布位置。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="e5f5d-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="e5f5d-155">指定脚本源位置。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-156">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="e5f5d-156">-SkipValidate</span></span>

<span data-ttu-id="e5f5d-157">跳过验证包源凭据的开关。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5f5d-158">-Trusted</span><span class="sxs-lookup"><span data-stu-id="e5f5d-158">-Trusted</span></span>

<span data-ttu-id="e5f5d-159">指示源是受信任的包提供程序。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="e5f5d-160">受信任的源不会提示验证安装包。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="e5f5d-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e5f5d-161">-Confirm</span></span>

<span data-ttu-id="e5f5d-162">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e5f5d-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e5f5d-163">-WhatIf</span></span>

<span data-ttu-id="e5f5d-164">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e5f5d-165">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e5f5d-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e5f5d-166">CommonParameters</span></span>

<span data-ttu-id="e5f5d-167">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5f5d-168">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5f5d-169">输入</span><span class="sxs-lookup"><span data-stu-id="e5f5d-169">INPUTS</span></span>

### <span data-ttu-id="e5f5d-170">`Set-PackageSource` 不接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="e5f5d-171">输出</span><span class="sxs-lookup"><span data-stu-id="e5f5d-171">OUTPUTS</span></span>

### <span data-ttu-id="e5f5d-172">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="e5f5d-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e5f5d-173">注释</span><span class="sxs-lookup"><span data-stu-id="e5f5d-173">NOTES</span></span>

## <span data-ttu-id="e5f5d-174">相关链接</span><span class="sxs-lookup"><span data-stu-id="e5f5d-174">RELATED LINKS</span></span>

[<span data-ttu-id="e5f5d-175">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e5f5d-175">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e5f5d-176">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e5f5d-176">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="e5f5d-177">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e5f5d-177">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="e5f5d-178">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e5f5d-178">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

