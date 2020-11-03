---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: d73d8d6a30e6b7c08b5a0b7988ea2327be34002a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198258"
---
# <span data-ttu-id="1a55a-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="1a55a-103">Invoke-DscResource</span></span>

## <span data-ttu-id="1a55a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1a55a-104">SYNOPSIS</span></span>
<span data-ttu-id="1a55a-105">运行指定的 DSC 资源的方法。</span><span class="sxs-lookup"><span data-stu-id="1a55a-105">Runs a method of a specified DSC resource.</span></span>

## <span data-ttu-id="1a55a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a55a-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [-Method] <String> -ModuleName <ModuleSpecification> -Property <Hashtable>
 [<CommonParameters>]
```

## <span data-ttu-id="1a55a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a55a-107">DESCRIPTION</span></span>
<span data-ttu-id="1a55a-108">**Get-dscresource** CMDLET (DSC) 资源中运行指定的 Windows PowerShell Desired State Configuration 的方法。</span><span class="sxs-lookup"><span data-stu-id="1a55a-108">The **Invoke-DscResource** cmdlet runs a method of a specified Windows PowerShell Desired State Configuration (DSC) resource.</span></span>
<span data-ttu-id="1a55a-109">运行此 cmdlet 之前，请将本地 Configuration Manager (LCM) 的刷新模式设置为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="1a55a-109">Before you run this cmdlet, set the refresh mode of the Local Configuration Manager (LCM) to Disabled.</span></span>

<span data-ttu-id="1a55a-110">此 cmdlet 直接调用 DSC 资源，而无需创建配置文档。</span><span class="sxs-lookup"><span data-stu-id="1a55a-110">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span>
<span data-ttu-id="1a55a-111">使用此 cmdlet，配置管理产品可以使用 DSC 资源管理 windows。</span><span class="sxs-lookup"><span data-stu-id="1a55a-111">Using this cmdlet, configuration management products can manage windows by using DSC resources.</span></span>
<span data-ttu-id="1a55a-112">此 cmdlet 还可用于在 DSC 引擎或 LCM 正在启用调试的情况下调试资源。</span><span class="sxs-lookup"><span data-stu-id="1a55a-112">This cmdlet also enables debugging of resources when the DSC engine or LCM is running with debugging enabled.</span></span>

## <span data-ttu-id="1a55a-113">示例</span><span class="sxs-lookup"><span data-stu-id="1a55a-113">EXAMPLES</span></span>

### <span data-ttu-id="1a55a-114">示例1：通过指定资源的必需属性来调用该资源的 Set 方法</span><span class="sxs-lookup"><span data-stu-id="1a55a-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

```
PS C:\> Invoke-DscResource -Name Log -Method Set -Property @{Message = 'Hello World'} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="1a55a-115">此命令调用名为 Log 的资源的 **Set** 方法，并为其指定 **消息** 属性。</span><span class="sxs-lookup"><span data-stu-id="1a55a-115">This command invokes the **Set** method of a resource named Log and specifies a **Message** property for it.</span></span>

### <span data-ttu-id="1a55a-116">示例2：为指定模块调用资源的测试方法</span><span class="sxs-lookup"><span data-stu-id="1a55a-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

```
PS C:\> Invoke-DscResource -Name WindowsProcess -Method Test -Property @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="1a55a-117">此命令调用名为 WindowsProcess 的资源的 **测试** 方法，该资源位于名为 PSDesiredStateConfiguration 的模块中。</span><span class="sxs-lookup"><span data-stu-id="1a55a-117">This command invokes the **Test** method of a resource named WindowsProcess, which is in the module named PSDesiredStateConfiguration.</span></span>

## <span data-ttu-id="1a55a-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a55a-118">PARAMETERS</span></span>

### <span data-ttu-id="1a55a-119">-方法</span><span class="sxs-lookup"><span data-stu-id="1a55a-119">-Method</span></span>
<span data-ttu-id="1a55a-120">指定此 cmdlet 调用的资源的方法。</span><span class="sxs-lookup"><span data-stu-id="1a55a-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="1a55a-121">此参数可接受的值包括： Get、Set 和 Test。</span><span class="sxs-lookup"><span data-stu-id="1a55a-121">The acceptable values for this parameter are: Get, Set, and Test.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a55a-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="1a55a-122">-ModuleName</span></span>
<span data-ttu-id="1a55a-123">指定此 cmdlet 从中调用指定资源的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="1a55a-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a55a-124">-Name</span><span class="sxs-lookup"><span data-stu-id="1a55a-124">-Name</span></span>
<span data-ttu-id="1a55a-125">指定要启动的 DSC 资源的名称。</span><span class="sxs-lookup"><span data-stu-id="1a55a-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a55a-126">-Property</span><span class="sxs-lookup"><span data-stu-id="1a55a-126">-Property</span></span>
<span data-ttu-id="1a55a-127">分别在哈希表中将资源属性名称及其值指定为键和值。</span><span class="sxs-lookup"><span data-stu-id="1a55a-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="1a55a-128">使用 **Get-DscResource** cmdlet 可以发现资源属性及其类型。</span><span class="sxs-lookup"><span data-stu-id="1a55a-128">Use the **Get-DscResource** cmdlet to discover resource properties and their types.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a55a-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1a55a-129">CommonParameters</span></span>
<span data-ttu-id="1a55a-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="1a55a-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a55a-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="1a55a-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a55a-132">输入</span><span class="sxs-lookup"><span data-stu-id="1a55a-132">INPUTS</span></span>

## <span data-ttu-id="1a55a-133">输出</span><span class="sxs-lookup"><span data-stu-id="1a55a-133">OUTPUTS</span></span>

### <span data-ttu-id="1a55a-134">CimInstance、system.string 和 System.object</span><span class="sxs-lookup"><span data-stu-id="1a55a-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="1a55a-135">注释</span><span class="sxs-lookup"><span data-stu-id="1a55a-135">NOTES</span></span>

## <span data-ttu-id="1a55a-136">相关链接</span><span class="sxs-lookup"><span data-stu-id="1a55a-136">RELATED LINKS</span></span>

[<span data-ttu-id="1a55a-137">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="1a55a-137">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="1a55a-138">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a55a-138">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="1a55a-139">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="1a55a-139">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="1a55a-140">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="1a55a-140">Get-DscResource</span></span>](Get-DscResource.md)

[<span data-ttu-id="1a55a-141">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a55a-141">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="1a55a-142">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="1a55a-142">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)

[<span data-ttu-id="1a55a-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a55a-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="1a55a-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a55a-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
