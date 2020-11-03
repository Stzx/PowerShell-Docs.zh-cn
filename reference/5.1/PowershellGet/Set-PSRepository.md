---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 0734bda0a3462e39f799570c853cffa3e267c5db
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198234"
---
# <span data-ttu-id="8943a-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8943a-103">Set-PSRepository</span></span>

## <span data-ttu-id="8943a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8943a-104">SYNOPSIS</span></span>
<span data-ttu-id="8943a-105">为已注册的存储库设置值。</span><span class="sxs-lookup"><span data-stu-id="8943a-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="8943a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8943a-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="8943a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8943a-107">DESCRIPTION</span></span>

<span data-ttu-id="8943a-108">`Set-PSRepository`Cmdlet 为已注册的模块存储库设置值。</span><span class="sxs-lookup"><span data-stu-id="8943a-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="8943a-109">这些设置对于当前用户是永久性的，适用于为该用户安装的所有版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8943a-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="8943a-110">示例</span><span class="sxs-lookup"><span data-stu-id="8943a-110">EXAMPLES</span></span>

### <span data-ttu-id="8943a-111">示例1：设置存储库的安装策略</span><span class="sxs-lookup"><span data-stu-id="8943a-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="8943a-112">此命令将 **myInternalSource** 存储库的安装策略设置为 " **受信任** "，以便在从此源安装模块之前不会进行提示。</span><span class="sxs-lookup"><span data-stu-id="8943a-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted** , so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="8943a-113">示例2：设置存储库的源位置和发布位置</span><span class="sxs-lookup"><span data-stu-id="8943a-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="8943a-114">此命令将 **myInternalSource** 的源位置和发布位置设置为指定的 uri。</span><span class="sxs-lookup"><span data-stu-id="8943a-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="8943a-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8943a-115">PARAMETERS</span></span>

### <span data-ttu-id="8943a-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="8943a-116">-Credential</span></span>

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

### <span data-ttu-id="8943a-117">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="8943a-117">-InstallationPolicy</span></span>

<span data-ttu-id="8943a-118">指定安装策略。</span><span class="sxs-lookup"><span data-stu-id="8943a-118">Specifies the installation policy.</span></span> <span data-ttu-id="8943a-119">有效值为： **可信** 、 **不受** 信任。</span><span class="sxs-lookup"><span data-stu-id="8943a-119">Valid values are: **Trusted** , **Untrusted** .</span></span>

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

### <span data-ttu-id="8943a-120">-Name</span><span class="sxs-lookup"><span data-stu-id="8943a-120">-Name</span></span>

<span data-ttu-id="8943a-121">指定存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="8943a-121">Specifies the name of the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8943a-122">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="8943a-122">-PackageManagementProvider</span></span>

<span data-ttu-id="8943a-123">指定包管理提供程序。</span><span class="sxs-lookup"><span data-stu-id="8943a-123">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="8943a-124">-Proxy</span><span class="sxs-lookup"><span data-stu-id="8943a-124">-Proxy</span></span>

<span data-ttu-id="8943a-125">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="8943a-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="8943a-126">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="8943a-126">-ProxyCredential</span></span>

<span data-ttu-id="8943a-127">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8943a-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="8943a-128">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="8943a-128">-PublishLocation</span></span>

<span data-ttu-id="8943a-129">指定发布位置的 URI。</span><span class="sxs-lookup"><span data-stu-id="8943a-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="8943a-130">例如，对于基于 NuGet 的存储库，发布位置类似于 `https://someNuGetUrl.com/api/v2/Packages` 。</span><span class="sxs-lookup"><span data-stu-id="8943a-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="8943a-131">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="8943a-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="8943a-132">指定脚本发布位置。</span><span class="sxs-lookup"><span data-stu-id="8943a-132">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="8943a-133">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="8943a-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="8943a-134">指定脚本源位置。</span><span class="sxs-lookup"><span data-stu-id="8943a-134">Specifies the script source location.</span></span>

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

### <span data-ttu-id="8943a-135">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="8943a-135">-SourceLocation</span></span>

<span data-ttu-id="8943a-136">指定用于发现和安装此存储库中的模块的 URI。</span><span class="sxs-lookup"><span data-stu-id="8943a-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="8943a-137">例如，对于基于 NuGet 的存储库，源位置类似于 `https://someNuGetUrl.com/api/v2` 。</span><span class="sxs-lookup"><span data-stu-id="8943a-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8943a-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8943a-138">CommonParameters</span></span>

<span data-ttu-id="8943a-139">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8943a-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8943a-140">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8943a-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8943a-141">输入</span><span class="sxs-lookup"><span data-stu-id="8943a-141">INPUTS</span></span>

### <span data-ttu-id="8943a-142">System.String</span><span class="sxs-lookup"><span data-stu-id="8943a-142">System.String</span></span>

### <span data-ttu-id="8943a-143">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="8943a-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="8943a-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="8943a-144">System.Uri</span></span>

## <span data-ttu-id="8943a-145">输出</span><span class="sxs-lookup"><span data-stu-id="8943a-145">OUTPUTS</span></span>

### <span data-ttu-id="8943a-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="8943a-146">System.Object</span></span>

## <span data-ttu-id="8943a-147">注释</span><span class="sxs-lookup"><span data-stu-id="8943a-147">NOTES</span></span>

## <span data-ttu-id="8943a-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="8943a-148">RELATED LINKS</span></span>

[<span data-ttu-id="8943a-149">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8943a-149">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="8943a-150">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8943a-150">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="8943a-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8943a-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)