---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 2637cc092d3be2bb3bff051268ef288c81ef3ad7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197550"
---
# <span data-ttu-id="7030e-103">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="7030e-103">New-DscChecksum</span></span>

## <span data-ttu-id="7030e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7030e-104">SYNOPSIS</span></span>
<span data-ttu-id="7030e-105">创建 DSC 文档和 DSC 资源的校验和文件。</span><span class="sxs-lookup"><span data-stu-id="7030e-105">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="7030e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7030e-106">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7030e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7030e-107">DESCRIPTION</span></span>

<span data-ttu-id="7030e-108">**New-dscchecksum** Cmdlet 为 PowerShell 所需状态配置生成校验和文件 (DSC) 文档和压缩的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="7030e-108">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="7030e-109">此 cmdlet 为每个要在拉取模式下使用的配置和资源生成校验和文件。</span><span class="sxs-lookup"><span data-stu-id="7030e-109">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="7030e-110">DSC 服务使用校验和，以确保目标节点上存在正确的配置和资源。</span><span class="sxs-lookup"><span data-stu-id="7030e-110">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="7030e-111">将校验和与关联的 DSC 文档以及 DSC 服务存储中的压缩 DSC 资源放置在一起。</span><span class="sxs-lookup"><span data-stu-id="7030e-111">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="7030e-112">示例</span><span class="sxs-lookup"><span data-stu-id="7030e-112">EXAMPLES</span></span>

### <span data-ttu-id="7030e-113">示例1：为特定路径中的所有配置创建校验和文件</span><span class="sxs-lookup"><span data-stu-id="7030e-113">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="7030e-114">此命令为路径 C:\DSC\Configurations 中的所有配置创建校验和文件。</span><span class="sxs-lookup"><span data-stu-id="7030e-114">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="7030e-115">将跳过任何已存在的校验和文件。</span><span class="sxs-lookup"><span data-stu-id="7030e-115">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="7030e-116">示例2：为特定路径中的所有配置创建校验和文件，并覆盖现有的校验和文件</span><span class="sxs-lookup"><span data-stu-id="7030e-116">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="7030e-117">此命令为路径 C:\DSC\Configurations 中的所有配置创建新的校验和文件。</span><span class="sxs-lookup"><span data-stu-id="7030e-117">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="7030e-118">指定 *Force* 参数会使命令覆盖已存在的任何校验和文件。</span><span class="sxs-lookup"><span data-stu-id="7030e-118">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="7030e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7030e-119">PARAMETERS</span></span>

### <span data-ttu-id="7030e-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7030e-120">-Confirm</span></span>

<span data-ttu-id="7030e-121">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="7030e-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7030e-122">-Force</span><span class="sxs-lookup"><span data-stu-id="7030e-122">-Force</span></span>

<span data-ttu-id="7030e-123">指示该 cmdlet 将覆盖指定的输出文件（如果它已存在）。</span><span class="sxs-lookup"><span data-stu-id="7030e-123">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="7030e-124">-OutPath</span><span class="sxs-lookup"><span data-stu-id="7030e-124">-OutPath</span></span>

<span data-ttu-id="7030e-125">指定输出校验和文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="7030e-125">Specifies the path and file name of the output checksum file.</span></span>

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

### <span data-ttu-id="7030e-126">-Path</span><span class="sxs-lookup"><span data-stu-id="7030e-126">-Path</span></span>

<span data-ttu-id="7030e-127">指定输入文件的路径。</span><span class="sxs-lookup"><span data-stu-id="7030e-127">Specifies the path of the input file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7030e-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7030e-128">-WhatIf</span></span>

<span data-ttu-id="7030e-129">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7030e-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7030e-130">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="7030e-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7030e-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7030e-131">CommonParameters</span></span>

<span data-ttu-id="7030e-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7030e-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7030e-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7030e-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7030e-134">输入</span><span class="sxs-lookup"><span data-stu-id="7030e-134">INPUTS</span></span>

### <span data-ttu-id="7030e-135">无</span><span class="sxs-lookup"><span data-stu-id="7030e-135">None</span></span>

## <span data-ttu-id="7030e-136">输出</span><span class="sxs-lookup"><span data-stu-id="7030e-136">OUTPUTS</span></span>

### <span data-ttu-id="7030e-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="7030e-137">System.Object</span></span>

## <span data-ttu-id="7030e-138">注释</span><span class="sxs-lookup"><span data-stu-id="7030e-138">NOTES</span></span>

## <span data-ttu-id="7030e-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="7030e-139">RELATED LINKS</span></span>

[<span data-ttu-id="7030e-140">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="7030e-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)
