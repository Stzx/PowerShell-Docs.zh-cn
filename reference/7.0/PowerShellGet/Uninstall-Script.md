---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 640ef2187369599d35eea1bca9ad404f5dde745c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197299"
---
# <span data-ttu-id="6744e-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="6744e-103">Uninstall-Script</span></span>

## <span data-ttu-id="6744e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6744e-104">SYNOPSIS</span></span>
<span data-ttu-id="6744e-105">卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-105">Uninstalls a script.</span></span>

## <span data-ttu-id="6744e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6744e-106">SYNTAX</span></span>

### <span data-ttu-id="6744e-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="6744e-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6744e-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="6744e-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6744e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6744e-109">DESCRIPTION</span></span>

<span data-ttu-id="6744e-110">`Uninstall-Script`Cmdlet 从本地计算机中卸载指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="6744e-111">示例</span><span class="sxs-lookup"><span data-stu-id="6744e-111">EXAMPLES</span></span>

### <span data-ttu-id="6744e-112">示例1：卸载脚本</span><span class="sxs-lookup"><span data-stu-id="6744e-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="6744e-113">此示例将卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="6744e-114">`Uninstall-Script` 使用 **Name** 参数指定要从本地计算机中卸载的脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="6744e-115">示例2：使用管道卸载脚本</span><span class="sxs-lookup"><span data-stu-id="6744e-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="6744e-116">在此示例中，管道用于卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="6744e-117">`Get-InstalledScript` 使用 **Name** 参数指定脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="6744e-118">将对象向下发送到 `Uninstall-Script` ，并卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="6744e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6744e-119">PARAMETERS</span></span>

### <span data-ttu-id="6744e-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="6744e-120">-AllowPrerelease</span></span>

<span data-ttu-id="6744e-121">允许卸载标记为预发行版的脚本。</span><span class="sxs-lookup"><span data-stu-id="6744e-121">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="6744e-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6744e-122">-Confirm</span></span>

<span data-ttu-id="6744e-123">在运行之前提示你进行确认 `Uninstall-Script` 。</span><span class="sxs-lookup"><span data-stu-id="6744e-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="6744e-124">-Force</span><span class="sxs-lookup"><span data-stu-id="6744e-124">-Force</span></span>

<span data-ttu-id="6744e-125">强制 `Uninstall-Script` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="6744e-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6744e-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6744e-126">-InputObject</span></span>

<span data-ttu-id="6744e-127">接受 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="6744e-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="6744e-128">例如，输出 `Get-InstalledScript` 到变量，并将该变量用作 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="6744e-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="6744e-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="6744e-129">-MaximumVersion</span></span>

<span data-ttu-id="6744e-130">指定要卸载的脚本的最大或最新版本。</span><span class="sxs-lookup"><span data-stu-id="6744e-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="6744e-131">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="6744e-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="6744e-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="6744e-132">-MinimumVersion</span></span>

<span data-ttu-id="6744e-133">指定要卸载的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="6744e-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="6744e-134">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="6744e-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="6744e-135">-Name</span><span class="sxs-lookup"><span data-stu-id="6744e-135">-Name</span></span>

<span data-ttu-id="6744e-136">指定要卸载的脚本名称的数组。</span><span class="sxs-lookup"><span data-stu-id="6744e-136">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="6744e-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="6744e-137">-RequiredVersion</span></span>

<span data-ttu-id="6744e-138">指定要卸载的脚本的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="6744e-138">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="6744e-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6744e-139">-WhatIf</span></span>

<span data-ttu-id="6744e-140">显示运行时将发生 `Uninstall-Script` 的情况。</span><span class="sxs-lookup"><span data-stu-id="6744e-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="6744e-141">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="6744e-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="6744e-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6744e-142">CommonParameters</span></span>

<span data-ttu-id="6744e-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6744e-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6744e-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6744e-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6744e-145">输入</span><span class="sxs-lookup"><span data-stu-id="6744e-145">INPUTS</span></span>

### <span data-ttu-id="6744e-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="6744e-146">System.String[]</span></span>

### <span data-ttu-id="6744e-147">System.web. system.exception []</span><span class="sxs-lookup"><span data-stu-id="6744e-147">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="6744e-148">System.String</span><span class="sxs-lookup"><span data-stu-id="6744e-148">System.String</span></span>

## <span data-ttu-id="6744e-149">输出</span><span class="sxs-lookup"><span data-stu-id="6744e-149">OUTPUTS</span></span>

### <span data-ttu-id="6744e-150">System.Object</span><span class="sxs-lookup"><span data-stu-id="6744e-150">System.Object</span></span>

## <span data-ttu-id="6744e-151">注释</span><span class="sxs-lookup"><span data-stu-id="6744e-151">NOTES</span></span>

## <span data-ttu-id="6744e-152">相关链接</span><span class="sxs-lookup"><span data-stu-id="6744e-152">RELATED LINKS</span></span>

[<span data-ttu-id="6744e-153">Find-Script</span><span class="sxs-lookup"><span data-stu-id="6744e-153">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="6744e-154">Install-Script</span><span class="sxs-lookup"><span data-stu-id="6744e-154">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="6744e-155">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="6744e-155">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="6744e-156">Save-Script</span><span class="sxs-lookup"><span data-stu-id="6744e-156">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="6744e-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="6744e-157">Update-Script</span></span>](Update-Script.md)
