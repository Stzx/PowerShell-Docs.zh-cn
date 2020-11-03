---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 8425c3e68573fe214ec5de465c8492e0bf99b309
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "93199314"
---
# <span data-ttu-id="25c82-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="25c82-103">Invoke-DscResource</span></span>

## <span data-ttu-id="25c82-104">摘要</span><span class="sxs-lookup"><span data-stu-id="25c82-104">SYNOPSIS</span></span>
<span data-ttu-id="25c82-105"> (DSC) 资源运行指定的 PowerShell 所需状态配置的方法。</span><span class="sxs-lookup"><span data-stu-id="25c82-105">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="25c82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25c82-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="25c82-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25c82-107">DESCRIPTION</span></span>

<span data-ttu-id="25c82-108">`Invoke-DscResource` cmdlet 运行指定的 PowerShell 所需状态配置 (DSC) 资源的方法。</span><span class="sxs-lookup"><span data-stu-id="25c82-108">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="25c82-109">此 cmdlet 直接调用 DSC 资源，而无需创建配置文档。</span><span class="sxs-lookup"><span data-stu-id="25c82-109">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="25c82-110">使用此 cmdlet，配置管理产品可以使用 DSC 资源来管理 windows 或 Linux。</span><span class="sxs-lookup"><span data-stu-id="25c82-110">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="25c82-111">在启用调试的情况下运行 DSC 引擎时，此 cmdlet 还可用于调试资源。</span><span class="sxs-lookup"><span data-stu-id="25c82-111">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="25c82-112">`Invoke-DscResource` 是 PowerShell 7 中的实验性功能。</span><span class="sxs-lookup"><span data-stu-id="25c82-112">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="25c82-113">若要使用 cmdlet，必须使用以下命令启用它。</span><span class="sxs-lookup"><span data-stu-id="25c82-113">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="25c82-114">示例</span><span class="sxs-lookup"><span data-stu-id="25c82-114">EXAMPLES</span></span>

### <span data-ttu-id="25c82-115">示例1：通过指定资源的必需属性来调用该资源的 Set 方法</span><span class="sxs-lookup"><span data-stu-id="25c82-115">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="25c82-116">此示例调用名为 **WindowsProcess** 的资源的 **Set** 方法，并提供必需的 **路径** 和 **参数** 属性来启动指定的 Windows 进程。</span><span class="sxs-lookup"><span data-stu-id="25c82-116">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="25c82-117">示例2：为指定模块调用资源的测试方法</span><span class="sxs-lookup"><span data-stu-id="25c82-117">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="25c82-118">此示例调用名为 **WindowsProcess** 的资源的 **测试** 方法，该资源位于名为 **PSDesiredStateConfiguration** 的模块中。</span><span class="sxs-lookup"><span data-stu-id="25c82-118">This example invokes the **Test** method of a resource named **WindowsProcess** , which is in the module named **PSDesiredStateConfiguration** .</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="25c82-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25c82-119">PARAMETERS</span></span>

### <span data-ttu-id="25c82-120">-方法</span><span class="sxs-lookup"><span data-stu-id="25c82-120">-Method</span></span>

<span data-ttu-id="25c82-121">指定此 cmdlet 调用的资源的方法。</span><span class="sxs-lookup"><span data-stu-id="25c82-121">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="25c82-122">此参数可接受的值包括： **Get** 、 **Set** 和 **Test** 。</span><span class="sxs-lookup"><span data-stu-id="25c82-122">The acceptable values for this parameter are: **Get** , **Set** , and **Test** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25c82-123">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="25c82-123">-ModuleName</span></span>

<span data-ttu-id="25c82-124">指定此 cmdlet 从中调用指定资源的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="25c82-124">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25c82-125">-Name</span><span class="sxs-lookup"><span data-stu-id="25c82-125">-Name</span></span>

<span data-ttu-id="25c82-126">指定要启动的 DSC 资源的名称。</span><span class="sxs-lookup"><span data-stu-id="25c82-126">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25c82-127">-Property</span><span class="sxs-lookup"><span data-stu-id="25c82-127">-Property</span></span>

<span data-ttu-id="25c82-128">分别在哈希表中将资源属性名称及其值指定为键和值。</span><span class="sxs-lookup"><span data-stu-id="25c82-128">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25c82-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="25c82-129">CommonParameters</span></span>

<span data-ttu-id="25c82-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="25c82-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="25c82-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="25c82-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25c82-132">输入</span><span class="sxs-lookup"><span data-stu-id="25c82-132">INPUTS</span></span>

### <span data-ttu-id="25c82-133">System.String</span><span class="sxs-lookup"><span data-stu-id="25c82-133">System.String</span></span>

### <span data-ttu-id="25c82-134">ModuleSpecification。</span><span class="sxs-lookup"><span data-stu-id="25c82-134">Microsoft.PowerShell.Commands.ModuleSpecification</span></span>

## <span data-ttu-id="25c82-135">输出</span><span class="sxs-lookup"><span data-stu-id="25c82-135">OUTPUTS</span></span>

### <span data-ttu-id="25c82-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="25c82-136">System.Object</span></span>

## <span data-ttu-id="25c82-137">注释</span><span class="sxs-lookup"><span data-stu-id="25c82-137">NOTES</span></span>

- <span data-ttu-id="25c82-138">以前，Windows PowerShell 5.1 资源在系统上下文下运行，除非使用 key **PsDscRunAsCredential** 通过用户上下文指定。</span><span class="sxs-lookup"><span data-stu-id="25c82-138">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential** .</span></span> <span data-ttu-id="25c82-139">在 PowerShell 7.0 中，资源在用户的上下文中运行，并且不再支持 **PsDscRunAsCredential** 。</span><span class="sxs-lookup"><span data-stu-id="25c82-139">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="25c82-140">使用此密钥的以前的配置将引发异常。</span><span class="sxs-lookup"><span data-stu-id="25c82-140">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="25c82-141">从 PowerShell 7 中， `Invoke-DscResource` 不再支持调用 WMI DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="25c82-141">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="25c82-142">这包括 PSDesiredStateConfiguration 中的文件和日志资源  。</span><span class="sxs-lookup"><span data-stu-id="25c82-142">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration** .</span></span>

## <span data-ttu-id="25c82-143">相关链接</span><span class="sxs-lookup"><span data-stu-id="25c82-143">RELATED LINKS</span></span>

[<span data-ttu-id="25c82-144">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="25c82-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="25c82-145">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="25c82-145">Get-DscResource</span></span>](Get-DscResource.md)
