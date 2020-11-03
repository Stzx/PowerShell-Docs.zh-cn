---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: 7eba6a561ff0220d0624c49b109f1558822f1064
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "93199178"
---
# <span data-ttu-id="96f6b-103">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="96f6b-103">Get-DscResource</span></span>

## <span data-ttu-id="96f6b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="96f6b-104">SYNOPSIS</span></span>
<span data-ttu-id="96f6b-105">获取计算机上存在的 (DSC) 资源的所需状态配置。</span><span class="sxs-lookup"><span data-stu-id="96f6b-105">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="96f6b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="96f6b-106">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="96f6b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="96f6b-107">DESCRIPTION</span></span>

<span data-ttu-id="96f6b-108">`Get-DscResource`Cmdlet 检索计算机上存在的 POWERSHELL DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-108">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="96f6b-109">此 cmdlet 仅发现 PSModulePath 中安装的资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-109">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="96f6b-110">其中显示了有关由用户创建的内置和自定义提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="96f6b-110">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="96f6b-111">此 cmdlet 还显示有关复合资源的详细信息，复合资源是打包为模块或在运行时在会话中创建的其他配置。</span><span class="sxs-lookup"><span data-stu-id="96f6b-111">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="96f6b-112">示例</span><span class="sxs-lookup"><span data-stu-id="96f6b-112">EXAMPLES</span></span>

### <span data-ttu-id="96f6b-113">示例1：获取本地计算机上的所有资源</span><span class="sxs-lookup"><span data-stu-id="96f6b-113">Example 1: Get all resources on the local computer</span></span>

```powershell
 Get-DscResource
```

<span data-ttu-id="96f6b-114">此命令将获取本地计算机上的所有资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-114">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="96f6b-115">示例2：通过指定名称获取资源</span><span class="sxs-lookup"><span data-stu-id="96f6b-115">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="96f6b-116">此命令将获取 WindowsFeature 资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-116">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="96f6b-117">示例3：获取模块中的所有资源</span><span class="sxs-lookup"><span data-stu-id="96f6b-117">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="96f6b-118">此命令从 xHyper-V 模块获取所有资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-118">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="96f6b-119">示例4：使用通配符获取资源</span><span class="sxs-lookup"><span data-stu-id="96f6b-119">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="96f6b-120">此命令将获取与 **Name** 参数指定的通配符模式匹配的所有资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-120">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="96f6b-121">示例5：获取资源语法</span><span class="sxs-lookup"><span data-stu-id="96f6b-121">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="96f6b-122">此命令将获取 WindowsFeature 资源，并显示该资源的语法。</span><span class="sxs-lookup"><span data-stu-id="96f6b-122">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="96f6b-123">示例6：获取资源的所有属性</span><span class="sxs-lookup"><span data-stu-id="96f6b-123">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="96f6b-124">此命令将获取 User 资源，然后使用管道运算符返回 User 资源的所有属性。</span><span class="sxs-lookup"><span data-stu-id="96f6b-124">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="96f6b-125">示例7：从指定的模块中获取具有指定版本的所有资源</span><span class="sxs-lookup"><span data-stu-id="96f6b-125">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="96f6b-126">此命令从 xHyper-V 模块获取版本3.0.0.0 的所有资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-126">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="96f6b-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="96f6b-127">PARAMETERS</span></span>

### <span data-ttu-id="96f6b-128">-Module</span><span class="sxs-lookup"><span data-stu-id="96f6b-128">-Module</span></span>

<span data-ttu-id="96f6b-129">指定要为其查看 DSC 资源的模块的名称或完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="96f6b-129">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="96f6b-130">-Name</span><span class="sxs-lookup"><span data-stu-id="96f6b-130">-Name</span></span>

<span data-ttu-id="96f6b-131">指定要查看的 DSC 资源的名称数组。</span><span class="sxs-lookup"><span data-stu-id="96f6b-131">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="96f6b-132">-语法</span><span class="sxs-lookup"><span data-stu-id="96f6b-132">-Syntax</span></span>

<span data-ttu-id="96f6b-133">指示该 cmdlet 返回指定 DSC 资源的语法视图。</span><span class="sxs-lookup"><span data-stu-id="96f6b-133">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="96f6b-134">返回的语法演示了如何使用 PowerShell 脚本中的资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-134">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

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

### <span data-ttu-id="96f6b-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="96f6b-135">CommonParameters</span></span>

<span data-ttu-id="96f6b-136">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="96f6b-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="96f6b-137">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="96f6b-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="96f6b-138">输入</span><span class="sxs-lookup"><span data-stu-id="96f6b-138">INPUTS</span></span>

### <span data-ttu-id="96f6b-139">System.String[]</span><span class="sxs-lookup"><span data-stu-id="96f6b-139">System.String[]</span></span>

### <span data-ttu-id="96f6b-140">System.Object</span><span class="sxs-lookup"><span data-stu-id="96f6b-140">System.Object</span></span>

## <span data-ttu-id="96f6b-141">输出</span><span class="sxs-lookup"><span data-stu-id="96f6b-141">OUTPUTS</span></span>

### <span data-ttu-id="96f6b-142">DesiredStateConfiguration. DscResourceInfo []</span><span class="sxs-lookup"><span data-stu-id="96f6b-142">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="96f6b-143">string[]</span><span class="sxs-lookup"><span data-stu-id="96f6b-143">string[]</span></span>

## <span data-ttu-id="96f6b-144">注释</span><span class="sxs-lookup"><span data-stu-id="96f6b-144">NOTES</span></span>

- <span data-ttu-id="96f6b-145">`Get-DscResource` 在低于7.0 的 PowerShell 版本中找不到基于类的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="96f6b-145">`Get-DscResource` does not find Class based DSC resources in PowerShell versions below 7.0.</span></span>

## <span data-ttu-id="96f6b-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="96f6b-146">RELATED LINKS</span></span>

[<span data-ttu-id="96f6b-147">PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="96f6b-147">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="96f6b-148">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="96f6b-148">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
