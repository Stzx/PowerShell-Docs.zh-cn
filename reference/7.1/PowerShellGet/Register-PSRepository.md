---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 300d3388c39a86cb732d50404ad7d8c28bd3034e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892185"
---
# <span data-ttu-id="cb666-103">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb666-103">Register-PSRepository</span></span>

## <span data-ttu-id="cb666-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cb666-104">SYNOPSIS</span></span>
<span data-ttu-id="cb666-105">注册 PowerShell 存储库。</span><span class="sxs-lookup"><span data-stu-id="cb666-105">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="cb666-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb666-106">SYNTAX</span></span>

### <span data-ttu-id="cb666-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="cb666-107">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="cb666-108">PSGalleryParameterSet</span><span class="sxs-lookup"><span data-stu-id="cb666-108">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="cb666-109">说明</span><span class="sxs-lookup"><span data-stu-id="cb666-109">DESCRIPTION</span></span>

<span data-ttu-id="cb666-110">`Register-PSRepository`Cmdlet 为 PowerShell 模块注册默认存储库。</span><span class="sxs-lookup"><span data-stu-id="cb666-110">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="cb666-111">注册存储库后，可以从 `Find-Module` 、 `Install-Module` 和 cmdlet 引用它 `Publish-Module` 。</span><span class="sxs-lookup"><span data-stu-id="cb666-111">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="cb666-112">已注册的存储库将成为和中的默认存储库 `Find-Module` `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="cb666-112">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="cb666-113">已注册的存储库是特定于用户的存储库。</span><span class="sxs-lookup"><span data-stu-id="cb666-113">Registered repositories are user-specific.</span></span> <span data-ttu-id="cb666-114">它们不是在整个系统范围上下文中注册的。</span><span class="sxs-lookup"><span data-stu-id="cb666-114">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="cb666-115">每个已注册的存储库都与使用 **PackageManagementProvider** 参数指定的 OneGet 包提供程序相关联。</span><span class="sxs-lookup"><span data-stu-id="cb666-115">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="cb666-116">每个 OneGet 提供程序都设计为与特定类型的存储库进行交互。</span><span class="sxs-lookup"><span data-stu-id="cb666-116">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="cb666-117">例如，NuGet 提供程序设计为与基于 NuGet 的存储库交互。</span><span class="sxs-lookup"><span data-stu-id="cb666-117">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="cb666-118">如果注册过程中未指定 OneGet 提供程序，则 PowerShellGet 会尝试查找可处理指定源位置的 OneGet 提供程序。</span><span class="sxs-lookup"><span data-stu-id="cb666-118">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="cb666-119">示例</span><span class="sxs-lookup"><span data-stu-id="cb666-119">EXAMPLES</span></span>

### <span data-ttu-id="cb666-120">示例1：注册存储库</span><span class="sxs-lookup"><span data-stu-id="cb666-120">Example 1: Register a repository</span></span>

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

<span data-ttu-id="cb666-121">第一个命令注册 `https://www.myget.org/F/powershellgetdemo/` 为当前用户的存储库。</span><span class="sxs-lookup"><span data-stu-id="cb666-121">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="cb666-122">注册 myNuGetSource 后，可以在搜索、安装和发布模块时显式引用它。</span><span class="sxs-lookup"><span data-stu-id="cb666-122">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="cb666-123">由于未指定 **PackageManagementProvider** 参数，因此不会将存储库与 OneGet 包提供程序显式关联，因此，PowerShellGet 会轮询可用的包提供程序，并将其与 NuGet 提供程序相关联。</span><span class="sxs-lookup"><span data-stu-id="cb666-123">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="cb666-124">第二个命令获取已注册的存储库并显示结果。</span><span class="sxs-lookup"><span data-stu-id="cb666-124">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="cb666-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb666-125">PARAMETERS</span></span>

### <span data-ttu-id="cb666-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="cb666-126">-Credential</span></span>

<span data-ttu-id="cb666-127">指定有权注册存储库的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="cb666-127">Specifies credentials of an account that has rights to register a repository.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-128">-Default</span><span class="sxs-lookup"><span data-stu-id="cb666-128">-Default</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-129">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="cb666-129">-InstallationPolicy</span></span>

<span data-ttu-id="cb666-130">指定安装策略。</span><span class="sxs-lookup"><span data-stu-id="cb666-130">Specifies the installation policy.</span></span> <span data-ttu-id="cb666-131">有效值为：可信、不受信任。</span><span class="sxs-lookup"><span data-stu-id="cb666-131">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="cb666-132">默认值为不受信任。</span><span class="sxs-lookup"><span data-stu-id="cb666-132">The default value is UnTrusted.</span></span>

<span data-ttu-id="cb666-133">存储库的安装策略指定从该存储库安装时的 PowerShell 行为。</span><span class="sxs-lookup"><span data-stu-id="cb666-133">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="cb666-134">从不受信任的存储库中安装模块时，系统将提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="cb666-134">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="cb666-135">可以将 **InstallationPolicy** 设置为 `Set-PSRepository` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cb666-135">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-136">-Name</span><span class="sxs-lookup"><span data-stu-id="cb666-136">-Name</span></span>

<span data-ttu-id="cb666-137">指定要注册的存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="cb666-137">Specifies the name of the repository to register.</span></span> <span data-ttu-id="cb666-138">可以使用此名称在 cmdlet （如和）中指定存储 `Find-Module` 库 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="cb666-138">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-139">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="cb666-139">-PackageManagementProvider</span></span>

<span data-ttu-id="cb666-140">指定 OneGet 包提供程序。</span><span class="sxs-lookup"><span data-stu-id="cb666-140">Specifies a OneGet package provider.</span></span> <span data-ttu-id="cb666-141">如果未指定此参数的值，则 PowerShellGet 会轮询可用的包提供程序，并将此存储库与第一个指示它可以处理存储库的包提供程序相关联。</span><span class="sxs-lookup"><span data-stu-id="cb666-141">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-142">-Proxy</span><span class="sxs-lookup"><span data-stu-id="cb666-142">-Proxy</span></span>

<span data-ttu-id="cb666-143">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="cb666-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="cb666-144">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="cb666-144">-ProxyCredential</span></span>

<span data-ttu-id="cb666-145">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cb666-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="cb666-146">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="cb666-146">-PublishLocation</span></span>

<span data-ttu-id="cb666-147">指定发布位置的 URI。</span><span class="sxs-lookup"><span data-stu-id="cb666-147">Specifies the URI of the publish location.</span></span> <span data-ttu-id="cb666-148">例如，对于基于 NuGet 的存储库，发布位置类似于 `https://someNuGetUrl.com/api/v2/Packages` 。</span><span class="sxs-lookup"><span data-stu-id="cb666-148">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-149">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="cb666-149">-ScriptPublishLocation</span></span>

<span data-ttu-id="cb666-150">指定脚本发布位置。</span><span class="sxs-lookup"><span data-stu-id="cb666-150">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-151">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="cb666-151">-ScriptSourceLocation</span></span>

<span data-ttu-id="cb666-152">指定脚本源位置。</span><span class="sxs-lookup"><span data-stu-id="cb666-152">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-153">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="cb666-153">-SourceLocation</span></span>

<span data-ttu-id="cb666-154">指定用于发现和安装此存储库中的模块的 URI。</span><span class="sxs-lookup"><span data-stu-id="cb666-154">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="cb666-155">URI 可以是 NuGet 服务器源 (最常见的情况) 、HTTP、HTTPS、FTP 或文件位置。</span><span class="sxs-lookup"><span data-stu-id="cb666-155">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="cb666-156">例如，对于基于 NuGet 的存储库，源位置类似于 `https://someNuGetUrl.com/api/v2` 。</span><span class="sxs-lookup"><span data-stu-id="cb666-156">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb666-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cb666-157">CommonParameters</span></span>

<span data-ttu-id="cb666-158">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cb666-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb666-159">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="cb666-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb666-160">输入</span><span class="sxs-lookup"><span data-stu-id="cb666-160">INPUTS</span></span>

### <span data-ttu-id="cb666-161">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="cb666-161">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="cb666-162">System.Uri</span><span class="sxs-lookup"><span data-stu-id="cb666-162">System.Uri</span></span>

## <span data-ttu-id="cb666-163">输出</span><span class="sxs-lookup"><span data-stu-id="cb666-163">OUTPUTS</span></span>

### <span data-ttu-id="cb666-164">System.Object</span><span class="sxs-lookup"><span data-stu-id="cb666-164">System.Object</span></span>

## <span data-ttu-id="cb666-165">注释</span><span class="sxs-lookup"><span data-stu-id="cb666-165">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb666-166">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="cb666-166">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="cb666-167">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="cb666-167">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="cb666-168">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="cb666-168">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="cb666-169">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="cb666-169">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="cb666-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="cb666-170">RELATED LINKS</span></span>

[<span data-ttu-id="cb666-171">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb666-171">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="cb666-172">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb666-172">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="cb666-173">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb666-173">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
