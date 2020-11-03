---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 03bb3f427f86867fdfe392b7b153c14b333e0fe3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197755"
---
# <span data-ttu-id="91605-103">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="91605-103">Get-PackageProvider</span></span>

## <span data-ttu-id="91605-104">摘要</span><span class="sxs-lookup"><span data-stu-id="91605-104">SYNOPSIS</span></span>
<span data-ttu-id="91605-105">返回连接到包管理的包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="91605-105">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="91605-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91605-106">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="91605-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91605-107">DESCRIPTION</span></span>
<span data-ttu-id="91605-108">**Install-packageprovider** cmdlet 将返回连接到包管理的包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="91605-108">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="91605-109">这些提供程序的示例包括 PSModule、NuGet 和 Chocolatey。</span><span class="sxs-lookup"><span data-stu-id="91605-109">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="91605-110">你可以根据一个或多个提供程序名称的全部或部分来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="91605-110">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="91605-111">示例</span><span class="sxs-lookup"><span data-stu-id="91605-111">EXAMPLES</span></span>

### <span data-ttu-id="91605-112">示例1：获取所有当前加载的包提供程序</span><span class="sxs-lookup"><span data-stu-id="91605-112">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="91605-113">此命令将获取当前在本地计算机上加载的所有包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="91605-113">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="91605-114">示例2：获取所有可用的包提供程序</span><span class="sxs-lookup"><span data-stu-id="91605-114">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="91605-115">此命令将获取本地计算机上可用的所有包提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="91605-115">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="91605-116">示例3：动态获取包提供程序</span><span class="sxs-lookup"><span data-stu-id="91605-116">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="91605-117">如果你的计算机未安装 Chocolatey 提供程序，则此命令将自动安装 Chocolatey 提供程序。</span><span class="sxs-lookup"><span data-stu-id="91605-117">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="91605-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91605-118">PARAMETERS</span></span>

### <span data-ttu-id="91605-119">-Force</span><span class="sxs-lookup"><span data-stu-id="91605-119">-Force</span></span>
<span data-ttu-id="91605-120">指示此 cmdlet 强制执行可强制执行的所有其他操作。</span><span class="sxs-lookup"><span data-stu-id="91605-120">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="91605-121">在 **install-packageprovider** 中，这意味着 *Force* 参数的作用与 *ForceBootstrap* 参数相同。</span><span class="sxs-lookup"><span data-stu-id="91605-121">In **Get-PackageProvider** , this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="91605-122">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="91605-122">-ForceBootstrap</span></span>
<span data-ttu-id="91605-123">指示此 cmdlet 强制包管理自动安装包提供程序。</span><span class="sxs-lookup"><span data-stu-id="91605-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="91605-124">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="91605-124">-ListAvailable</span></span>
<span data-ttu-id="91605-125">获取所有已安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="91605-125">Gets all installed providers.</span></span>
<span data-ttu-id="91605-126">**Install-packageprovider** 获取 **PSModulePath** 环境变量中列出的路径中的提供程序，以及包提供程序程序集文件夹：</span><span class="sxs-lookup"><span data-stu-id="91605-126">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="91605-127">**$env:P rogramFiles\PackageManagement\ProviderAssemblies \* \* \* \* $env： LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span><span class="sxs-lookup"><span data-stu-id="91605-127">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="91605-128">如果没有此参数， **install-packageprovider** 仅获取当前会话中加载的提供程序。</span><span class="sxs-lookup"><span data-stu-id="91605-128">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="91605-129">-Name</span><span class="sxs-lookup"><span data-stu-id="91605-129">-Name</span></span>
<span data-ttu-id="91605-130">指定一个或多个提供程序名称或部分提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="91605-130">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="91605-131">用逗号分隔多个提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="91605-131">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="91605-132">此参数的有效值包括已与包一起安装的提供程序的名称;PackageManagement 附带一组默认提供程序，其中包括 **PSModule** 和 **MSI** 提供程序。</span><span class="sxs-lookup"><span data-stu-id="91605-132">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91605-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91605-133">CommonParameters</span></span>
<span data-ttu-id="91605-134">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="91605-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91605-135">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="91605-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91605-136">输入</span><span class="sxs-lookup"><span data-stu-id="91605-136">INPUTS</span></span>

## <span data-ttu-id="91605-137">输出</span><span class="sxs-lookup"><span data-stu-id="91605-137">OUTPUTS</span></span>

### <span data-ttu-id="91605-138">Install-packageprovider []</span><span class="sxs-lookup"><span data-stu-id="91605-138">PackageProvider[]</span></span>

## <span data-ttu-id="91605-139">注释</span><span class="sxs-lookup"><span data-stu-id="91605-139">NOTES</span></span>

## <span data-ttu-id="91605-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="91605-140">RELATED LINKS</span></span>

[<span data-ttu-id="91605-141">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="91605-141">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="91605-142">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91605-142">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="91605-143">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91605-143">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="91605-144">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91605-144">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
