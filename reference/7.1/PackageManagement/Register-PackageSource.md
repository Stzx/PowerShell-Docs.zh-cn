---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 8b57540658a88fa56533c3f5c360273913c3543b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198375"
---
# <span data-ttu-id="10083-103">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="10083-103">Register-PackageSource</span></span>

## <span data-ttu-id="10083-104">摘要</span><span class="sxs-lookup"><span data-stu-id="10083-104">SYNOPSIS</span></span>
<span data-ttu-id="10083-105">为指定的包提供程序添加包源。</span><span class="sxs-lookup"><span data-stu-id="10083-105">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="10083-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10083-106">SYNTAX</span></span>

### <span data-ttu-id="10083-107">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="10083-107">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="10083-108">NuGet</span><span class="sxs-lookup"><span data-stu-id="10083-108">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="10083-109">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="10083-109">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="10083-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10083-110">DESCRIPTION</span></span>

<span data-ttu-id="10083-111">`Register-PackageSource`Cmdlet 为指定的包提供程序添加包源。</span><span class="sxs-lookup"><span data-stu-id="10083-111">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="10083-112">包源始终由包提供程序进行管理。</span><span class="sxs-lookup"><span data-stu-id="10083-112">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="10083-113">如果包提供程序无法添加或替换包源，则提供程序会生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="10083-113">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="10083-114">示例</span><span class="sxs-lookup"><span data-stu-id="10083-114">EXAMPLES</span></span>

### <span data-ttu-id="10083-115">示例 1：为 NuGet 提供程序注册包源</span><span class="sxs-lookup"><span data-stu-id="10083-115">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="10083-116">此命令向 **NuGet** 提供程序的基于 web 的位置注册包源。</span><span class="sxs-lookup"><span data-stu-id="10083-116">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="10083-117">默认情况下，源不受信任。</span><span class="sxs-lookup"><span data-stu-id="10083-117">By default, sources aren't trusted.</span></span> <span data-ttu-id="10083-118">安装包之前，系统将提示你确认源是否受信任。</span><span class="sxs-lookup"><span data-stu-id="10083-118">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="10083-119">若要重写默认值，请使用 `-Trusted` 参数。</span><span class="sxs-lookup"><span data-stu-id="10083-119">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="10083-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10083-120">PARAMETERS</span></span>

### <span data-ttu-id="10083-121">-Read-configfile</span><span class="sxs-lookup"><span data-stu-id="10083-121">-ConfigFile</span></span>

<span data-ttu-id="10083-122">指定配置文件。</span><span class="sxs-lookup"><span data-stu-id="10083-122">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="10083-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="10083-123">-Credential</span></span>

<span data-ttu-id="10083-124">指定有权访问经过身份验证的位置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="10083-124">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="10083-125">-Force</span><span class="sxs-lookup"><span data-stu-id="10083-125">-Force</span></span>

<span data-ttu-id="10083-126">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="10083-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="10083-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="10083-127">-ForceBootstrap</span></span>

<span data-ttu-id="10083-128">指示此 cmdlet 自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="10083-128">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="10083-129">-Location</span><span class="sxs-lookup"><span data-stu-id="10083-129">-Location</span></span>

<span data-ttu-id="10083-130">指定包源位置。</span><span class="sxs-lookup"><span data-stu-id="10083-130">Specifies the package source location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10083-131">-Name</span><span class="sxs-lookup"><span data-stu-id="10083-131">-Name</span></span>

<span data-ttu-id="10083-132">指定要注册的包源的名称。</span><span class="sxs-lookup"><span data-stu-id="10083-132">Specifies the name of the package source to register.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10083-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="10083-133">-PackageManagementProvider</span></span>

<span data-ttu-id="10083-134">指定包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="10083-134">Specifies the Package Management provider.</span></span>

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

### <span data-ttu-id="10083-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="10083-135">-ProviderName</span></span>

<span data-ttu-id="10083-136">指定包提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="10083-136">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="10083-137">-Proxy</span><span class="sxs-lookup"><span data-stu-id="10083-137">-Proxy</span></span>

<span data-ttu-id="10083-138">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="10083-138">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="10083-139">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="10083-139">-ProxyCredential</span></span>

<span data-ttu-id="10083-140">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="10083-140">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="10083-141">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="10083-141">-PublishLocation</span></span>

<span data-ttu-id="10083-142">指定发布位置。</span><span class="sxs-lookup"><span data-stu-id="10083-142">Specifies the publish location.</span></span>

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

### <span data-ttu-id="10083-143">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="10083-143">-ScriptPublishLocation</span></span>

<span data-ttu-id="10083-144">指定脚本发布位置。</span><span class="sxs-lookup"><span data-stu-id="10083-144">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="10083-145">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="10083-145">-ScriptSourceLocation</span></span>

<span data-ttu-id="10083-146">指定脚本源位置。</span><span class="sxs-lookup"><span data-stu-id="10083-146">Specifies the script source location.</span></span>

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

### <span data-ttu-id="10083-147">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="10083-147">-SkipValidate</span></span>

<span data-ttu-id="10083-148">跳过验证包源凭据的开关。</span><span class="sxs-lookup"><span data-stu-id="10083-148">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="10083-149">-Trusted</span><span class="sxs-lookup"><span data-stu-id="10083-149">-Trusted</span></span>

<span data-ttu-id="10083-150">指示信任包源。</span><span class="sxs-lookup"><span data-stu-id="10083-150">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="10083-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="10083-151">-Confirm</span></span>

<span data-ttu-id="10083-152">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="10083-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="10083-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="10083-153">-WhatIf</span></span>

<span data-ttu-id="10083-154">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="10083-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="10083-155">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="10083-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="10083-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10083-156">CommonParameters</span></span>

<span data-ttu-id="10083-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="10083-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10083-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="10083-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10083-159">输入</span><span class="sxs-lookup"><span data-stu-id="10083-159">INPUTS</span></span>

## <span data-ttu-id="10083-160">输出</span><span class="sxs-lookup"><span data-stu-id="10083-160">OUTPUTS</span></span>

## <span data-ttu-id="10083-161">注释</span><span class="sxs-lookup"><span data-stu-id="10083-161">NOTES</span></span>

## <span data-ttu-id="10083-162">相关链接</span><span class="sxs-lookup"><span data-stu-id="10083-162">RELATED LINKS</span></span>

[<span data-ttu-id="10083-163">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="10083-163">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="10083-164">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="10083-164">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="10083-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="10083-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="10083-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="10083-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

