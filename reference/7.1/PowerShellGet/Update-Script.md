---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 25da03724603b0000c46ae2da69d63cdf2f36cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891677"
---
# <span data-ttu-id="8572d-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="8572d-103">Update-Script</span></span>

## <span data-ttu-id="8572d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8572d-104">SYNOPSIS</span></span>
<span data-ttu-id="8572d-105">更新脚本。</span><span class="sxs-lookup"><span data-stu-id="8572d-105">Updates a script.</span></span>

## <span data-ttu-id="8572d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8572d-106">SYNTAX</span></span>

### <span data-ttu-id="8572d-107">全部</span><span class="sxs-lookup"><span data-stu-id="8572d-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8572d-108">说明</span><span class="sxs-lookup"><span data-stu-id="8572d-108">DESCRIPTION</span></span>

<span data-ttu-id="8572d-109">`Update-Script`Cmdlet 可更新安装在本地计算机上的脚本。</span><span class="sxs-lookup"><span data-stu-id="8572d-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="8572d-110">已更新的脚本将从与安装的版本相同的存储库中下载。</span><span class="sxs-lookup"><span data-stu-id="8572d-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="8572d-111">示例</span><span class="sxs-lookup"><span data-stu-id="8572d-111">EXAMPLES</span></span>

### <span data-ttu-id="8572d-112">示例1：更新指定的脚本</span><span class="sxs-lookup"><span data-stu-id="8572d-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="8572d-113">此示例将更新已安装的脚本，并显示更新后的版本。</span><span class="sxs-lookup"><span data-stu-id="8572d-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="8572d-114">`Update-Script` 使用 **Name** 参数来指定要更新的脚本。</span><span class="sxs-lookup"><span data-stu-id="8572d-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="8572d-115">**RequiredVersion** 参数指定脚本版本。</span><span class="sxs-lookup"><span data-stu-id="8572d-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="8572d-116">`Get-InstalledScript` 显示脚本的更新版本。</span><span class="sxs-lookup"><span data-stu-id="8572d-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="8572d-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8572d-117">PARAMETERS</span></span>

### <span data-ttu-id="8572d-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="8572d-118">-AcceptLicense</span></span>

<span data-ttu-id="8572d-119">如果包需要许可协议，则在安装过程中自动接受该协议。</span><span class="sxs-lookup"><span data-stu-id="8572d-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="8572d-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="8572d-120">-AllowPrerelease</span></span>

<span data-ttu-id="8572d-121">允许使用标记为预发行版本的更新脚本来更新脚本。</span><span class="sxs-lookup"><span data-stu-id="8572d-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="8572d-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8572d-122">-Confirm</span></span>

<span data-ttu-id="8572d-123">在运行之前提示你进行确认 `Update-Script` 。</span><span class="sxs-lookup"><span data-stu-id="8572d-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="8572d-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="8572d-124">-Credential</span></span>

<span data-ttu-id="8572d-125">指定有权更新脚本的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8572d-125">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="8572d-126">-Force</span><span class="sxs-lookup"><span data-stu-id="8572d-126">-Force</span></span>

<span data-ttu-id="8572d-127">强制 `Update-Script` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="8572d-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8572d-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8572d-128">-MaximumVersion</span></span>

<span data-ttu-id="8572d-129">指定要更新的最大或最新版本的脚本。</span><span class="sxs-lookup"><span data-stu-id="8572d-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="8572d-130">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="8572d-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="8572d-131">-Name</span><span class="sxs-lookup"><span data-stu-id="8572d-131">-Name</span></span>

<span data-ttu-id="8572d-132">指定一个脚本名称或要更新的脚本名称数组。</span><span class="sxs-lookup"><span data-stu-id="8572d-132">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="8572d-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8572d-133">-PassThru</span></span>

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

### <span data-ttu-id="8572d-134">-Proxy</span><span class="sxs-lookup"><span data-stu-id="8572d-134">-Proxy</span></span>

<span data-ttu-id="8572d-135">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="8572d-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="8572d-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="8572d-136">-ProxyCredential</span></span>

<span data-ttu-id="8572d-137">指定有权使用 **代理** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8572d-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="8572d-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8572d-138">-RequiredVersion</span></span>

<span data-ttu-id="8572d-139">指定要更新的脚本的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="8572d-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="8572d-140">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="8572d-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="8572d-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8572d-141">-WhatIf</span></span>

<span data-ttu-id="8572d-142">显示运行时将发生 `Update-Script` 的情况。</span><span class="sxs-lookup"><span data-stu-id="8572d-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="8572d-143">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="8572d-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8572d-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8572d-144">CommonParameters</span></span>

<span data-ttu-id="8572d-145">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8572d-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8572d-146">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8572d-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8572d-147">输入</span><span class="sxs-lookup"><span data-stu-id="8572d-147">INPUTS</span></span>

### <span data-ttu-id="8572d-148">System.String[]</span><span class="sxs-lookup"><span data-stu-id="8572d-148">System.String[]</span></span>

### <span data-ttu-id="8572d-149">System.String</span><span class="sxs-lookup"><span data-stu-id="8572d-149">System.String</span></span>

### <span data-ttu-id="8572d-150">System.Uri</span><span class="sxs-lookup"><span data-stu-id="8572d-150">System.Uri</span></span>

### <span data-ttu-id="8572d-151">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="8572d-151">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="8572d-152">输出</span><span class="sxs-lookup"><span data-stu-id="8572d-152">OUTPUTS</span></span>

### <span data-ttu-id="8572d-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="8572d-153">System.Object</span></span>

## <span data-ttu-id="8572d-154">注释</span><span class="sxs-lookup"><span data-stu-id="8572d-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8572d-155">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="8572d-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="8572d-156">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="8572d-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="8572d-157">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="8572d-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="8572d-158">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="8572d-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="8572d-159">相关链接</span><span class="sxs-lookup"><span data-stu-id="8572d-159">RELATED LINKS</span></span>

[<span data-ttu-id="8572d-160">Find-Script</span><span class="sxs-lookup"><span data-stu-id="8572d-160">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="8572d-161">Install-Script</span><span class="sxs-lookup"><span data-stu-id="8572d-161">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="8572d-162">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="8572d-162">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="8572d-163">Save-Script</span><span class="sxs-lookup"><span data-stu-id="8572d-163">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="8572d-164">卸载-脚本</span><span class="sxs-lookup"><span data-stu-id="8572d-164">Uninstall-Script</span></span>](Uninstall-Script.md)

