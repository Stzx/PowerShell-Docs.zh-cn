---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 8c96b4cd56073a9185ca4b0f0f13b866b839931d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196991"
---
# <span data-ttu-id="0f185-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="0f185-103">Get-InstalledModule</span></span>

## <span data-ttu-id="0f185-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0f185-104">SYNOPSIS</span></span>
<span data-ttu-id="0f185-105">获取由 PowerShellGet 安装的计算机上的模块列表。</span><span class="sxs-lookup"><span data-stu-id="0f185-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="0f185-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f185-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="0f185-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f185-107">DESCRIPTION</span></span>

<span data-ttu-id="0f185-108">`Get-InstalledModule`Cmdlet 可获取使用 PowerShellGet 安装在计算机上的 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="0f185-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="0f185-109">若要查看系统上安装的所有模块，请使用 `Get-Module -ListAvailable` 命令。</span><span class="sxs-lookup"><span data-stu-id="0f185-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="0f185-110">示例</span><span class="sxs-lookup"><span data-stu-id="0f185-110">EXAMPLES</span></span>

### <span data-ttu-id="0f185-111">示例 1：获取所有已安装的模块</span><span class="sxs-lookup"><span data-stu-id="0f185-111">Example 1: Get all installed modules</span></span>

```powershell
Get-InstalledModule
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
2.0.0      PSGTEST-UploadMultipleVersionOfP... Module     GalleryINT     Module for DAC functionality
1.3.5      AzureAutomationDebug                Module     PSGallery      Module for debugging Azure Automation runbooks, emulating AA native cmdlets
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="0f185-112">此命令获取所有已安装的模块。</span><span class="sxs-lookup"><span data-stu-id="0f185-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="0f185-113">示例 2：获取特定版本的模块</span><span class="sxs-lookup"><span data-stu-id="0f185-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="0f185-114">此命令从版本 1.0 到版本 2.0 获取 AzureRM.Automation 模块的版本。</span><span class="sxs-lookup"><span data-stu-id="0f185-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="0f185-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f185-115">PARAMETERS</span></span>

### <span data-ttu-id="0f185-116">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="0f185-116">-AllowPrerelease</span></span>

<span data-ttu-id="0f185-117">包含在标记为预发行的结果模块中。</span><span class="sxs-lookup"><span data-stu-id="0f185-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="0f185-118">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="0f185-118">-AllVersions</span></span>

<span data-ttu-id="0f185-119">指示你想要获取某个模块的所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="0f185-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="0f185-120">不能将 **AllVersions** 参数与 **MinimumVersion** 、 **MaximumVersion** 或 **RequiredVersion** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="0f185-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="0f185-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="0f185-121">-MaximumVersion</span></span>

<span data-ttu-id="0f185-122">指定要获取的模块的最高或最新版本。</span><span class="sxs-lookup"><span data-stu-id="0f185-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="0f185-123">MaximumVersion  和 RequiredVersion  参数互斥，不能在同一命令中使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="0f185-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="0f185-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="0f185-124">-MinimumVersion</span></span>

<span data-ttu-id="0f185-125">指定要获取的单个模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="0f185-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="0f185-126">MinimumVersion  和 RequiredVersion  参数互斥，不能在同一命令中使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="0f185-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="0f185-127">-Name</span><span class="sxs-lookup"><span data-stu-id="0f185-127">-Name</span></span>

<span data-ttu-id="0f185-128">指定要获取的模块的名称数组。</span><span class="sxs-lookup"><span data-stu-id="0f185-128">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="0f185-129">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="0f185-129">-RequiredVersion</span></span>

<span data-ttu-id="0f185-130">指定要获取的模块的确切版本。</span><span class="sxs-lookup"><span data-stu-id="0f185-130">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="0f185-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f185-131">CommonParameters</span></span>

<span data-ttu-id="0f185-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0f185-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f185-133">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0f185-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0f185-134">输入</span><span class="sxs-lookup"><span data-stu-id="0f185-134">INPUTS</span></span>

### <span data-ttu-id="0f185-135">System.String[]</span><span class="sxs-lookup"><span data-stu-id="0f185-135">System.String[]</span></span>

### <span data-ttu-id="0f185-136">System.String</span><span class="sxs-lookup"><span data-stu-id="0f185-136">System.String</span></span>

## <span data-ttu-id="0f185-137">输出</span><span class="sxs-lookup"><span data-stu-id="0f185-137">OUTPUTS</span></span>

### <span data-ttu-id="0f185-138">System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="0f185-138">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="0f185-139">注释</span><span class="sxs-lookup"><span data-stu-id="0f185-139">NOTES</span></span>

## <span data-ttu-id="0f185-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="0f185-140">RELATED LINKS</span></span>
