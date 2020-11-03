---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198002"
---
# <span data-ttu-id="98c86-103">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="98c86-103">Get-OperationValidation</span></span>

## <span data-ttu-id="98c86-104">摘要</span><span class="sxs-lookup"><span data-stu-id="98c86-104">SYNOPSIS</span></span>
<span data-ttu-id="98c86-105">获取操作验证框架测试。</span><span class="sxs-lookup"><span data-stu-id="98c86-105">Gets Operation Validation Framework tests.</span></span>

## <span data-ttu-id="98c86-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="98c86-106">SYNTAX</span></span>

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="98c86-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="98c86-107">DESCRIPTION</span></span>
<span data-ttu-id="98c86-108">**OperationValidation** cmdlet 将获取已安装模块的操作验证框架测试。</span><span class="sxs-lookup"><span data-stu-id="98c86-108">The **Get-OperationValidation** cmdlet gets Operation Validation Framework tests for installed modules.</span></span>

<span data-ttu-id="98c86-109">在简单或综合性子文件夹中检查包含诊断文件夹的模块是否有 Pester 的测试。</span><span class="sxs-lookup"><span data-stu-id="98c86-109">Modules that include a Diagnostics folder are inspected for Pester tests in the Simple or Comprehensive subfolder, or both.</span></span>

## <span data-ttu-id="98c86-110">示例</span><span class="sxs-lookup"><span data-stu-id="98c86-110">EXAMPLES</span></span>

### <span data-ttu-id="98c86-111">示例1：获取操作验证测试</span><span class="sxs-lookup"><span data-stu-id="98c86-111">Example 1: Get Operation Validation tests</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

<span data-ttu-id="98c86-112">此命令从 C:\temp\modules 文件夹中名为 AddNumbers 的模块中获取验证测试。</span><span class="sxs-lookup"><span data-stu-id="98c86-112">This command gets validation tests from the module named AddNumbers in the C:\temp\modules folder.</span></span>

## <span data-ttu-id="98c86-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="98c86-113">PARAMETERS</span></span>

### <span data-ttu-id="98c86-114">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="98c86-114">-ModuleName</span></span>
<span data-ttu-id="98c86-115">指定模块的名称数组。</span><span class="sxs-lookup"><span data-stu-id="98c86-115">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c86-116">-TestType</span><span class="sxs-lookup"><span data-stu-id="98c86-116">-TestType</span></span>
<span data-ttu-id="98c86-117">指定测试类型的数组。</span><span class="sxs-lookup"><span data-stu-id="98c86-117">Specifies an array of test types.</span></span>
<span data-ttu-id="98c86-118">有效值为简单、完整或两者。</span><span class="sxs-lookup"><span data-stu-id="98c86-118">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="98c86-119">默认值为 "简单，全面"。</span><span class="sxs-lookup"><span data-stu-id="98c86-119">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c86-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="98c86-120">CommonParameters</span></span>
<span data-ttu-id="98c86-121">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="98c86-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="98c86-122">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="98c86-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="98c86-123">输入</span><span class="sxs-lookup"><span data-stu-id="98c86-123">INPUTS</span></span>

### <span data-ttu-id="98c86-124">无</span><span class="sxs-lookup"><span data-stu-id="98c86-124">None</span></span>
<span data-ttu-id="98c86-125">不能通过管道将任何输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98c86-125">You cannot pipe any input to this cmdlet.</span></span>

## <span data-ttu-id="98c86-126">输出</span><span class="sxs-lookup"><span data-stu-id="98c86-126">OUTPUTS</span></span>

### <span data-ttu-id="98c86-127">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="98c86-127">PSCustomObject</span></span>
<span data-ttu-id="98c86-128">**PSCustomObject** 描述了验证。</span><span class="sxs-lookup"><span data-stu-id="98c86-128">The **PSCustomObject** describes the validation.</span></span>

## <span data-ttu-id="98c86-129">注释</span><span class="sxs-lookup"><span data-stu-id="98c86-129">NOTES</span></span>

## <span data-ttu-id="98c86-130">相关链接</span><span class="sxs-lookup"><span data-stu-id="98c86-130">RELATED LINKS</span></span>

[<span data-ttu-id="98c86-131">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="98c86-131">Invoke-OperationValidation</span></span>](Invoke-OperationValidation.md)
