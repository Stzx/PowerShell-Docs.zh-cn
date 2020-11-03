---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 72cdbd26a909e4be33fa32f67019e4c1f02ce3de
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198224"
---
# <span data-ttu-id="ad3b8-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="ad3b8-103">Uninstall-Module</span></span>

## <span data-ttu-id="ad3b8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ad3b8-104">SYNOPSIS</span></span>
<span data-ttu-id="ad3b8-105">卸载模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-105">Uninstalls a module.</span></span>

## <span data-ttu-id="ad3b8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ad3b8-106">SYNTAX</span></span>

### <span data-ttu-id="ad3b8-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="ad3b8-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="ad3b8-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="ad3b8-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ad3b8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ad3b8-109">DESCRIPTION</span></span>

<span data-ttu-id="ad3b8-110">`Uninstall-Module`Cmdlet 从本地计算机中卸载指定的模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="ad3b8-111">如果模块有其他模块作为依赖项，则无法卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="ad3b8-112">示例</span><span class="sxs-lookup"><span data-stu-id="ad3b8-112">EXAMPLES</span></span>

### <span data-ttu-id="ad3b8-113">示例1：卸载模块</span><span class="sxs-lookup"><span data-stu-id="ad3b8-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="ad3b8-114">此示例将卸载模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="ad3b8-115">`Uninstall-Module` 使用 **Name** 参数指定要从本地计算机中卸载的模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="ad3b8-116">示例2：使用管道卸载模块</span><span class="sxs-lookup"><span data-stu-id="ad3b8-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="ad3b8-117">在此示例中，管道用于卸载模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="ad3b8-118">`Get-InstalledModule` 使用 **Name** 参数指定模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="ad3b8-119">对象沿管道向下发送到 `Uninstall-Module` 并被卸载。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="ad3b8-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ad3b8-120">PARAMETERS</span></span>

### <span data-ttu-id="ad3b8-121">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="ad3b8-121">-AllowPrerelease</span></span>

<span data-ttu-id="ad3b8-122">允许卸载标记为预发行的模块。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-122">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="ad3b8-123">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="ad3b8-123">-AllVersions</span></span>

<span data-ttu-id="ad3b8-124">指定您要包含某个模块的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="ad3b8-125">不能将 **AllVersions** 参数与 **MinimumVersion** 、 **MaximumVersion** 或 **RequiredVersion** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="ad3b8-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ad3b8-126">-Confirm</span></span>

<span data-ttu-id="ad3b8-127">提示你在运行之前进行确认 `Uninstall-Module` 。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="ad3b8-128">-Force</span><span class="sxs-lookup"><span data-stu-id="ad3b8-128">-Force</span></span>

<span data-ttu-id="ad3b8-129">强制 `Uninstall-Module` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ad3b8-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ad3b8-130">-InputObject</span></span>

<span data-ttu-id="ad3b8-131">接受 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="ad3b8-132">例如，输出 `Get-InstalledModule` 到变量，并将该变量用作 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="ad3b8-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="ad3b8-133">-MaximumVersion</span></span>

<span data-ttu-id="ad3b8-134">指定要卸载的模块的最高或最新版本。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="ad3b8-135">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ad3b8-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="ad3b8-136">-MinimumVersion</span></span>

<span data-ttu-id="ad3b8-137">指定要卸载的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="ad3b8-138">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ad3b8-139">-Name</span><span class="sxs-lookup"><span data-stu-id="ad3b8-139">-Name</span></span>

<span data-ttu-id="ad3b8-140">指定要卸载的模块名称的数组。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-140">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="ad3b8-141">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ad3b8-141">-RequiredVersion</span></span>

<span data-ttu-id="ad3b8-142">指定要卸载的模块的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-142">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="ad3b8-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ad3b8-143">-WhatIf</span></span>

<span data-ttu-id="ad3b8-144">显示运行时将发生 `Uninstall-Module` 的情况。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="ad3b8-145">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="ad3b8-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ad3b8-146">CommonParameters</span></span>

<span data-ttu-id="ad3b8-147">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ad3b8-148">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ad3b8-149">输入</span><span class="sxs-lookup"><span data-stu-id="ad3b8-149">INPUTS</span></span>

### <span data-ttu-id="ad3b8-150">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="ad3b8-150">PSRepositoryItemInfo</span></span>

<span data-ttu-id="ad3b8-151">`Uninstall-Module` 接受管道中的 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="ad3b8-151">`Uninstall-Module` accepts **PSRepositoryItemInfo** objects from the pipeline.</span></span>

## <span data-ttu-id="ad3b8-152">输出</span><span class="sxs-lookup"><span data-stu-id="ad3b8-152">OUTPUTS</span></span>

## <span data-ttu-id="ad3b8-153">注释</span><span class="sxs-lookup"><span data-stu-id="ad3b8-153">NOTES</span></span>

## <span data-ttu-id="ad3b8-154">相关链接</span><span class="sxs-lookup"><span data-stu-id="ad3b8-154">RELATED LINKS</span></span>

[<span data-ttu-id="ad3b8-155">Find-Module</span><span class="sxs-lookup"><span data-stu-id="ad3b8-155">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="ad3b8-156">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="ad3b8-156">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="ad3b8-157">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="ad3b8-157">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="ad3b8-158">Save-Module</span><span class="sxs-lookup"><span data-stu-id="ad3b8-158">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="ad3b8-159">Update-Module</span><span class="sxs-lookup"><span data-stu-id="ad3b8-159">Update-Module</span></span>](Update-Module.md)
