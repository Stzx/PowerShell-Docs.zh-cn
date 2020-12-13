---
ms.date: 09/13/2016
ms.topic: reference
title: 属性类型
description: 属性类型
ms.openlocfilehash: 65640f2f8449887dedb9fae137eb16b6252f1d57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667107"
---
# <a name="attribute-types"></a><span data-ttu-id="0f481-103">属性类型</span><span class="sxs-lookup"><span data-stu-id="0f481-103">Attribute Types</span></span>

<span data-ttu-id="0f481-104">Cmdlet 属性可以按功能分组。</span><span class="sxs-lookup"><span data-stu-id="0f481-104">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="0f481-105">以下各节介绍了可用的属性，并说明了在调用特性时运行时的作用。</span><span class="sxs-lookup"><span data-stu-id="0f481-105">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="0f481-106">Cmdlet 属性</span><span class="sxs-lookup"><span data-stu-id="0f481-106">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="0f481-107">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0f481-107">Cmdlet</span></span>

<span data-ttu-id="0f481-108">将 .NET Framework 类标识为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f481-108">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="0f481-109">这是必需的基本属性。</span><span class="sxs-lookup"><span data-stu-id="0f481-109">This is the required base attribute.</span></span>
<span data-ttu-id="0f481-110">有关详细信息，请参阅 [Cmdlet 特性声明](./cmdlet-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-110">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="0f481-111">参数属性</span><span class="sxs-lookup"><span data-stu-id="0f481-111">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="0f481-112">参数</span><span class="sxs-lookup"><span data-stu-id="0f481-112">Parameter</span></span>

<span data-ttu-id="0f481-113">将 cmdlet 类中的公共属性标识为 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="0f481-113">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="0f481-114">有关详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-114">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="0f481-115">Alias</span><span class="sxs-lookup"><span data-stu-id="0f481-115">Alias</span></span>

<span data-ttu-id="0f481-116">指定参数的一个或多个别名。</span><span class="sxs-lookup"><span data-stu-id="0f481-116">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="0f481-117">有关详细信息，请参阅 [Alias 特性声明](./alias-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-117">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="0f481-118">参数验证特性</span><span class="sxs-lookup"><span data-stu-id="0f481-118">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="0f481-119">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="0f481-119">ValidateCount</span></span>

<span data-ttu-id="0f481-120">指定 cmdlet 参数允许的最小和最大参数数量。</span><span class="sxs-lookup"><span data-stu-id="0f481-120">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="0f481-121">有关详细信息，请参阅 [ValidateCount 特性声明](./validatecount-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-121">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="0f481-122">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="0f481-122">ValidateLength</span></span>

<span data-ttu-id="0f481-123">指定 cmdlet 参数参数的最小和最大字符数。</span><span class="sxs-lookup"><span data-stu-id="0f481-123">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="0f481-124">有关详细信息，请参阅 [ValidateLength 特性声明](./validatelength-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-124">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="0f481-125">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="0f481-125">ValidatePattern</span></span>

<span data-ttu-id="0f481-126">指定 cmdlet 参数参数必须匹配的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="0f481-126">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="0f481-127">有关详细信息，请参阅 [ValidatePattern 特性声明](./validatepattern-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-127">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="0f481-128">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="0f481-128">ValidateRange</span></span>

<span data-ttu-id="0f481-129">指定 cmdlet 参数参数的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="0f481-129">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="0f481-130">有关详细信息，请参阅 [ValidateRange 特性声明](./validaterange-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-130">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="0f481-131">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="0f481-131">ValidateSet</span></span>

<span data-ttu-id="0f481-132">为 cmdlet 参数参数指定一组有效值。</span><span class="sxs-lookup"><span data-stu-id="0f481-132">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="0f481-133">有关详细信息，请参阅 [ValidateSet 特性声明](./validateset-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="0f481-133">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f481-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f481-134">See Also</span></span>

[<span data-ttu-id="0f481-135">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="0f481-135">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
