---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 812ff0b9ea57e2aa3ccb1f24656a94d4de9c641b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198560"
---
# <span data-ttu-id="d0a7d-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="d0a7d-103">Uninstall-Script</span></span>

## <span data-ttu-id="d0a7d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d0a7d-104">SYNOPSIS</span></span>
<span data-ttu-id="d0a7d-105">卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-105">Uninstalls a script.</span></span>

## <span data-ttu-id="d0a7d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0a7d-106">SYNTAX</span></span>

### <span data-ttu-id="d0a7d-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="d0a7d-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d0a7d-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="d0a7d-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d0a7d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d0a7d-109">DESCRIPTION</span></span>

<span data-ttu-id="d0a7d-110">`Uninstall-Script`Cmdlet 从本地计算机中卸载指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="d0a7d-111">示例</span><span class="sxs-lookup"><span data-stu-id="d0a7d-111">EXAMPLES</span></span>

### <span data-ttu-id="d0a7d-112">示例1：卸载脚本</span><span class="sxs-lookup"><span data-stu-id="d0a7d-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="d0a7d-113">此示例将卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="d0a7d-114">`Uninstall-Script` 使用 **Name** 参数指定要从本地计算机中卸载的脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="d0a7d-115">示例2：使用管道卸载脚本</span><span class="sxs-lookup"><span data-stu-id="d0a7d-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="d0a7d-116">在此示例中，管道用于卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="d0a7d-117">`Get-InstalledScript` 使用 **Name** 参数指定脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="d0a7d-118">将对象向下发送到 `Uninstall-Script` ，并卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="d0a7d-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0a7d-119">PARAMETERS</span></span>

### <span data-ttu-id="d0a7d-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="d0a7d-120">-AllowPrerelease</span></span>

<span data-ttu-id="d0a7d-121">允许卸载标记为预发行版的脚本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-121">Allows you to uninstall a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d0a7d-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d0a7d-122">-Confirm</span></span>

<span data-ttu-id="d0a7d-123">在运行之前提示你进行确认 `Uninstall-Script` 。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="d0a7d-124">-Force</span><span class="sxs-lookup"><span data-stu-id="d0a7d-124">-Force</span></span>

<span data-ttu-id="d0a7d-125">强制 `Uninstall-Script` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d0a7d-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d0a7d-126">-InputObject</span></span>

<span data-ttu-id="d0a7d-127">接受 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="d0a7d-128">例如，输出 `Get-InstalledScript` 到变量，并将该变量用作 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d0a7d-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d0a7d-129">-MaximumVersion</span></span>

<span data-ttu-id="d0a7d-130">指定要卸载的脚本的最大或最新版本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="d0a7d-131">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d0a7d-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d0a7d-132">-MinimumVersion</span></span>

<span data-ttu-id="d0a7d-133">指定要卸载的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="d0a7d-134">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d0a7d-135">-Name</span><span class="sxs-lookup"><span data-stu-id="d0a7d-135">-Name</span></span>

<span data-ttu-id="d0a7d-136">指定要卸载的脚本名称的数组。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-136">Specifies an array of script names to uninstall.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d0a7d-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="d0a7d-137">-RequiredVersion</span></span>

<span data-ttu-id="d0a7d-138">指定要卸载的脚本的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-138">Specifies the exact version number of the script to uninstall.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d0a7d-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d0a7d-139">-WhatIf</span></span>

<span data-ttu-id="d0a7d-140">显示运行时将发生 `Uninstall-Script` 的情况。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="d0a7d-141">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="d0a7d-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d0a7d-142">CommonParameters</span></span>

<span data-ttu-id="d0a7d-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d0a7d-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d0a7d-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0a7d-145">输入</span><span class="sxs-lookup"><span data-stu-id="d0a7d-145">INPUTS</span></span>

### <span data-ttu-id="d0a7d-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d0a7d-146">System.String[]</span></span>

### <span data-ttu-id="d0a7d-147">System.web. system.exception []</span><span class="sxs-lookup"><span data-stu-id="d0a7d-147">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="d0a7d-148">System.String</span><span class="sxs-lookup"><span data-stu-id="d0a7d-148">System.String</span></span>

## <span data-ttu-id="d0a7d-149">输出</span><span class="sxs-lookup"><span data-stu-id="d0a7d-149">OUTPUTS</span></span>

### <span data-ttu-id="d0a7d-150">System.Object</span><span class="sxs-lookup"><span data-stu-id="d0a7d-150">System.Object</span></span>

## <span data-ttu-id="d0a7d-151">注释</span><span class="sxs-lookup"><span data-stu-id="d0a7d-151">NOTES</span></span>

## <span data-ttu-id="d0a7d-152">相关链接</span><span class="sxs-lookup"><span data-stu-id="d0a7d-152">RELATED LINKS</span></span>

[<span data-ttu-id="d0a7d-153">Find-Script</span><span class="sxs-lookup"><span data-stu-id="d0a7d-153">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="d0a7d-154">Install-Script</span><span class="sxs-lookup"><span data-stu-id="d0a7d-154">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="d0a7d-155">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d0a7d-155">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="d0a7d-156">Save-Script</span><span class="sxs-lookup"><span data-stu-id="d0a7d-156">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="d0a7d-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="d0a7d-157">Update-Script</span></span>](Update-Script.md)
