---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 427f50a697186354c889e85bf080189f5ee4af9c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197268"
---
# <span data-ttu-id="6a03a-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="6a03a-103">Uninstall-Module</span></span>

## <span data-ttu-id="6a03a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6a03a-104">SYNOPSIS</span></span>
<span data-ttu-id="6a03a-105">卸载模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-105">Uninstalls a module.</span></span>

## <span data-ttu-id="6a03a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a03a-106">SYNTAX</span></span>

### <span data-ttu-id="6a03a-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="6a03a-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="6a03a-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="6a03a-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6a03a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a03a-109">DESCRIPTION</span></span>

<span data-ttu-id="6a03a-110">`Uninstall-Module`Cmdlet 从本地计算机中卸载指定的模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="6a03a-111">如果模块有其他模块作为依赖项，则无法卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="6a03a-112">示例</span><span class="sxs-lookup"><span data-stu-id="6a03a-112">EXAMPLES</span></span>

### <span data-ttu-id="6a03a-113">示例1：卸载模块</span><span class="sxs-lookup"><span data-stu-id="6a03a-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="6a03a-114">此示例将卸载模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="6a03a-115">`Uninstall-Module` 使用 **Name** 参数指定要从本地计算机中卸载的模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="6a03a-116">示例2：使用管道卸载模块</span><span class="sxs-lookup"><span data-stu-id="6a03a-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="6a03a-117">在此示例中，管道用于卸载模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="6a03a-118">`Get-InstalledModule` 使用 **Name** 参数指定模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="6a03a-119">对象沿管道向下发送到 `Uninstall-Module` 并被卸载。</span><span class="sxs-lookup"><span data-stu-id="6a03a-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="6a03a-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a03a-120">PARAMETERS</span></span>

### <span data-ttu-id="6a03a-121">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="6a03a-121">-AllowPrerelease</span></span>

<span data-ttu-id="6a03a-122">允许卸载标记为预发行的模块。</span><span class="sxs-lookup"><span data-stu-id="6a03a-122">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="6a03a-123">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="6a03a-123">-AllVersions</span></span>

<span data-ttu-id="6a03a-124">指定您要包含某个模块的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="6a03a-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="6a03a-125">不能将 **AllVersions** 参数与 **MinimumVersion** 、 **MaximumVersion** 或 **RequiredVersion** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="6a03a-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="6a03a-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6a03a-126">-Confirm</span></span>

<span data-ttu-id="6a03a-127">提示你在运行之前进行确认 `Uninstall-Module` 。</span><span class="sxs-lookup"><span data-stu-id="6a03a-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="6a03a-128">-Force</span><span class="sxs-lookup"><span data-stu-id="6a03a-128">-Force</span></span>

<span data-ttu-id="6a03a-129">强制 `Uninstall-Module` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="6a03a-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6a03a-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6a03a-130">-InputObject</span></span>

<span data-ttu-id="6a03a-131">接受 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="6a03a-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="6a03a-132">例如，输出 `Get-InstalledModule` 到变量，并将该变量用作 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="6a03a-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="6a03a-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="6a03a-133">-MaximumVersion</span></span>

<span data-ttu-id="6a03a-134">指定要卸载的模块的最高或最新版本。</span><span class="sxs-lookup"><span data-stu-id="6a03a-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="6a03a-135">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="6a03a-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="6a03a-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="6a03a-136">-MinimumVersion</span></span>

<span data-ttu-id="6a03a-137">指定要卸载的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="6a03a-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="6a03a-138">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="6a03a-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="6a03a-139">-Name</span><span class="sxs-lookup"><span data-stu-id="6a03a-139">-Name</span></span>

<span data-ttu-id="6a03a-140">指定要卸载的模块名称的数组。</span><span class="sxs-lookup"><span data-stu-id="6a03a-140">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="6a03a-141">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="6a03a-141">-RequiredVersion</span></span>

<span data-ttu-id="6a03a-142">指定要卸载的模块的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="6a03a-142">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="6a03a-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6a03a-143">-WhatIf</span></span>

<span data-ttu-id="6a03a-144">显示运行时将发生 `Uninstall-Module` 的情况。</span><span class="sxs-lookup"><span data-stu-id="6a03a-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="6a03a-145">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="6a03a-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="6a03a-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a03a-146">CommonParameters</span></span>

<span data-ttu-id="6a03a-147">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6a03a-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a03a-148">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6a03a-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a03a-149">输入</span><span class="sxs-lookup"><span data-stu-id="6a03a-149">INPUTS</span></span>

### <span data-ttu-id="6a03a-150">System.String[]</span><span class="sxs-lookup"><span data-stu-id="6a03a-150">System.String[]</span></span>

### <span data-ttu-id="6a03a-151">System.web. system.exception []</span><span class="sxs-lookup"><span data-stu-id="6a03a-151">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="6a03a-152">System.String</span><span class="sxs-lookup"><span data-stu-id="6a03a-152">System.String</span></span>

## <span data-ttu-id="6a03a-153">输出</span><span class="sxs-lookup"><span data-stu-id="6a03a-153">OUTPUTS</span></span>

### <span data-ttu-id="6a03a-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="6a03a-154">System.Object</span></span>

## <span data-ttu-id="6a03a-155">注释</span><span class="sxs-lookup"><span data-stu-id="6a03a-155">NOTES</span></span>

## <span data-ttu-id="6a03a-156">相关链接</span><span class="sxs-lookup"><span data-stu-id="6a03a-156">RELATED LINKS</span></span>

[<span data-ttu-id="6a03a-157">Find-Module</span><span class="sxs-lookup"><span data-stu-id="6a03a-157">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="6a03a-158">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="6a03a-158">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="6a03a-159">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="6a03a-159">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="6a03a-160">Save-Module</span><span class="sxs-lookup"><span data-stu-id="6a03a-160">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="6a03a-161">Update-Module</span><span class="sxs-lookup"><span data-stu-id="6a03a-161">Update-Module</span></span>](Update-Module.md)
