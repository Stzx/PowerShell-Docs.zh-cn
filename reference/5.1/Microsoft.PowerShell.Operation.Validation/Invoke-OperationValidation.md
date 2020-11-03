---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/invoke-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-OperationValidation
ms.openlocfilehash: 6c9d4001392de48032a0fe1ba3667db90ea614fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198001"
---
# <span data-ttu-id="f5aa6-103">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="f5aa6-103">Invoke-OperationValidation</span></span>

## <span data-ttu-id="f5aa6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f5aa6-104">SYNOPSIS</span></span>

<span data-ttu-id="f5aa6-105">调用操作验证框架测试。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-105">Invokes Operation Validation Framework tests.</span></span>

## <span data-ttu-id="f5aa6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5aa6-106">SYNTAX</span></span>

### <span data-ttu-id="f5aa6-107">FileAndTest (默认值) </span><span class="sxs-lookup"><span data-stu-id="f5aa6-107">FileAndTest (Default)</span></span>

```
Invoke-OperationValidation [-TestInfo <PSObject[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="f5aa6-108">`Path`</span><span class="sxs-lookup"><span data-stu-id="f5aa6-108">Path</span></span>

```
Invoke-OperationValidation [-testFilePath <String[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="f5aa6-109">UseGetOperationTest</span><span class="sxs-lookup"><span data-stu-id="f5aa6-109">UseGetOperationTest</span></span>

```
Invoke-OperationValidation [-ModuleName <String[]>] [-TestType <String[]>] [-IncludePesterOutput] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f5aa6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5aa6-110">DESCRIPTION</span></span>

<span data-ttu-id="f5aa6-111">**OperationValidation** cmdlet 为指定的模块调用操作验证框架测试。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-111">The **Invoke-OperationValidation** cmdlet invokes Operation Validation Framework tests for a specified module.</span></span>

## <span data-ttu-id="f5aa6-112">示例</span><span class="sxs-lookup"><span data-stu-id="f5aa6-112">EXAMPLES</span></span>

### <span data-ttu-id="f5aa6-113">示例1：调用操作验证测试</span><span class="sxs-lookup"><span data-stu-id="f5aa6-113">Example 1: Invoke an Operation Validation test</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "OperationValidation" | Invoke-OperationValidation -IncludePesterOutput
Describing Simple Test Suite
 [+] first Operational test 20ms
 [+] second Operational test 19ms
 [+] third Operational test 9ms
Tests completed in 48ms
Passed: 3 Failed: 0 Skipped: 0 Pending: 0
Describing Scenario targeted tests
   Context The RemoteAccess service
    [+] The service is running 37ms
   Context The Firewall Rules
    [+] A rule for TCP port 3389 is enabled 1.19s
    [+] A rule for UDP port 3389 is enabled 11ms
Tests completed in 1.24s
Passed: 3 Failed: 0 Skipped: 0 Pending: 0




   Module: OperationValidation




Result  Name
------- --------
Passed  Simple Test Suite::first Operational test
Passed  Simple Test Suite::second Operational test
Passed  Simple Test Suite::third Operational test
Passed  Scenario targeted tests:The RemoteAccess service:The service is running
Passed  Scenario targeted tests:The Firewall Rules:A rule for TCP port 3389 is enabled
Passed  Scenario targeted tests:The Firewall Rules:A rule for UDP port 3389 is enabled
```

<span data-ttu-id="f5aa6-114">此命令获取名为 OperationValidation 的模块，并使用管道运算符将其传递给运行测试的 **OperationValidation** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-114">This command gets the module named OperationValidation, and uses the pipeline operator to pass it to the **Invoke-OperationValidation** cmdlet, which runs the test.</span></span>

## <span data-ttu-id="f5aa6-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5aa6-115">PARAMETERS</span></span>

### <span data-ttu-id="f5aa6-116">-IncludePesterOutput</span><span class="sxs-lookup"><span data-stu-id="f5aa6-116">-IncludePesterOutput</span></span>

<span data-ttu-id="f5aa6-117">包含 Pester 测试输出。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-117">Includes Pester test output.</span></span>
<span data-ttu-id="f5aa6-118">默认值为 $False。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-118">The default is $False.</span></span>

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

### <span data-ttu-id="f5aa6-119">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="f5aa6-119">-ModuleName</span></span>

<span data-ttu-id="f5aa6-120">指定模块的名称数组。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-120">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f5aa6-121">-testFilePath</span><span class="sxs-lookup"><span data-stu-id="f5aa6-121">-testFilePath</span></span>

<span data-ttu-id="f5aa6-122">指定操作验证框架测试文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-122">Specifies the path of an Operation Validation Framework test file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f5aa6-123">-TestInfo</span><span class="sxs-lookup"><span data-stu-id="f5aa6-123">-TestInfo</span></span>

<span data-ttu-id="f5aa6-124">指定一个自定义对象，该对象指定文件的路径以及要运行的测试的名称。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-124">Specifies a custom object that specifies the path to the file and the name of the test to run.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: FileAndTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f5aa6-125">-TestType</span><span class="sxs-lookup"><span data-stu-id="f5aa6-125">-TestType</span></span>

<span data-ttu-id="f5aa6-126">指定测试类型的数组。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-126">Specifies an array of test types.</span></span>
<span data-ttu-id="f5aa6-127">有效值为简单、完整或两者。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-127">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="f5aa6-128">默认值为 "简单，全面"。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-128">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f5aa6-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f5aa6-129">-Confirm</span></span>

<span data-ttu-id="f5aa6-130">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f5aa6-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f5aa6-131">-WhatIf</span></span>

<span data-ttu-id="f5aa6-132">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f5aa6-133">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f5aa6-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f5aa6-134">CommonParameters</span></span>
<span data-ttu-id="f5aa6-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5aa6-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f5aa6-137">输入</span><span class="sxs-lookup"><span data-stu-id="f5aa6-137">INPUTS</span></span>

### <span data-ttu-id="f5aa6-138">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="f5aa6-138">PSCustomObject</span></span>

<span data-ttu-id="f5aa6-139">可以通过管道将 **OperationValidation** 的输出传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-139">You can pipe the output of **Get-OperationValidation** to this cmdlet.</span></span>

## <span data-ttu-id="f5aa6-140">输出</span><span class="sxs-lookup"><span data-stu-id="f5aa6-140">OUTPUTS</span></span>

### <span data-ttu-id="f5aa6-141">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="f5aa6-141">PSCustomObject</span></span>

<span data-ttu-id="f5aa6-142">**PSCustomObject** 描述验证是否成功。</span><span class="sxs-lookup"><span data-stu-id="f5aa6-142">The **PSCustomObject** describes whether the validation was successful.</span></span>

## <span data-ttu-id="f5aa6-143">注释</span><span class="sxs-lookup"><span data-stu-id="f5aa6-143">NOTES</span></span>

## <span data-ttu-id="f5aa6-144">相关链接</span><span class="sxs-lookup"><span data-stu-id="f5aa6-144">RELATED LINKS</span></span>

[<span data-ttu-id="f5aa6-145">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="f5aa6-145">Get-OperationValidation</span></span>](Get-OperationValidation.md)
