---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 5a43e3382990209c365bb8fe5c0b320624ddfe18
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198470"
---
# <span data-ttu-id="26d63-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="26d63-103">Update-Script</span></span>

## <span data-ttu-id="26d63-104">摘要</span><span class="sxs-lookup"><span data-stu-id="26d63-104">SYNOPSIS</span></span>
<span data-ttu-id="26d63-105">更新脚本。</span><span class="sxs-lookup"><span data-stu-id="26d63-105">Updates a script.</span></span>

## <span data-ttu-id="26d63-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="26d63-106">SYNTAX</span></span>

### <span data-ttu-id="26d63-107">全部</span><span class="sxs-lookup"><span data-stu-id="26d63-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="26d63-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="26d63-108">DESCRIPTION</span></span>

<span data-ttu-id="26d63-109">`Update-Script`Cmdlet 可更新安装在本地计算机上的脚本。</span><span class="sxs-lookup"><span data-stu-id="26d63-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="26d63-110">已更新的脚本将从与安装的版本相同的存储库中下载。</span><span class="sxs-lookup"><span data-stu-id="26d63-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="26d63-111">示例</span><span class="sxs-lookup"><span data-stu-id="26d63-111">EXAMPLES</span></span>

### <span data-ttu-id="26d63-112">示例1：更新指定的脚本</span><span class="sxs-lookup"><span data-stu-id="26d63-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="26d63-113">此示例将更新已安装的脚本，并显示更新后的版本。</span><span class="sxs-lookup"><span data-stu-id="26d63-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="26d63-114">`Update-Script` 使用 **Name** 参数来指定要更新的脚本。</span><span class="sxs-lookup"><span data-stu-id="26d63-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="26d63-115">**RequiredVersion** 参数指定脚本版本。</span><span class="sxs-lookup"><span data-stu-id="26d63-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="26d63-116">`Get-InstalledScript` 显示脚本的更新版本。</span><span class="sxs-lookup"><span data-stu-id="26d63-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="26d63-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="26d63-117">PARAMETERS</span></span>

### <span data-ttu-id="26d63-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="26d63-118">-AcceptLicense</span></span>

<span data-ttu-id="26d63-119">如果包需要许可协议，则在安装过程中自动接受该协议。</span><span class="sxs-lookup"><span data-stu-id="26d63-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="26d63-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="26d63-120">-AllowPrerelease</span></span>

<span data-ttu-id="26d63-121">允许使用标记为预发行版本的更新脚本来更新脚本。</span><span class="sxs-lookup"><span data-stu-id="26d63-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="26d63-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="26d63-122">-Confirm</span></span>

<span data-ttu-id="26d63-123">在运行之前提示你进行确认 `Update-Script` 。</span><span class="sxs-lookup"><span data-stu-id="26d63-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="26d63-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="26d63-124">-Credential</span></span>

<span data-ttu-id="26d63-125">指定有权更新脚本的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26d63-125">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="26d63-126">-Force</span><span class="sxs-lookup"><span data-stu-id="26d63-126">-Force</span></span>

<span data-ttu-id="26d63-127">强制 `Update-Script` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="26d63-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="26d63-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="26d63-128">-MaximumVersion</span></span>

<span data-ttu-id="26d63-129">指定要更新的最大或最新版本的脚本。</span><span class="sxs-lookup"><span data-stu-id="26d63-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="26d63-130">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="26d63-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="26d63-131">-Name</span><span class="sxs-lookup"><span data-stu-id="26d63-131">-Name</span></span>

<span data-ttu-id="26d63-132">指定一个脚本名称或要更新的脚本名称数组。</span><span class="sxs-lookup"><span data-stu-id="26d63-132">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="26d63-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="26d63-133">-PassThru</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26d63-134">-Proxy</span><span class="sxs-lookup"><span data-stu-id="26d63-134">-Proxy</span></span>

<span data-ttu-id="26d63-135">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="26d63-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="26d63-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="26d63-136">-ProxyCredential</span></span>

<span data-ttu-id="26d63-137">指定有权使用 **代理** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26d63-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="26d63-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="26d63-138">-RequiredVersion</span></span>

<span data-ttu-id="26d63-139">指定要更新的脚本的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="26d63-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="26d63-140">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="26d63-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="26d63-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="26d63-141">-WhatIf</span></span>

<span data-ttu-id="26d63-142">显示运行时将发生 `Update-Script` 的情况。</span><span class="sxs-lookup"><span data-stu-id="26d63-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="26d63-143">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="26d63-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="26d63-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="26d63-144">CommonParameters</span></span>

<span data-ttu-id="26d63-145">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="26d63-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="26d63-146">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="26d63-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="26d63-147">输入</span><span class="sxs-lookup"><span data-stu-id="26d63-147">INPUTS</span></span>

## <span data-ttu-id="26d63-148">输出</span><span class="sxs-lookup"><span data-stu-id="26d63-148">OUTPUTS</span></span>

## <span data-ttu-id="26d63-149">注释</span><span class="sxs-lookup"><span data-stu-id="26d63-149">NOTES</span></span>

## <span data-ttu-id="26d63-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="26d63-150">RELATED LINKS</span></span>

[<span data-ttu-id="26d63-151">Find-Script</span><span class="sxs-lookup"><span data-stu-id="26d63-151">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="26d63-152">Install-Script</span><span class="sxs-lookup"><span data-stu-id="26d63-152">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="26d63-153">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="26d63-153">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="26d63-154">Save-Script</span><span class="sxs-lookup"><span data-stu-id="26d63-154">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="26d63-155">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="26d63-155">Uninstall-Script</span></span>](Uninstall-Script.md)
