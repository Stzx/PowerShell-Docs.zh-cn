---
title: 属性类型 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 96fdd38ba10eb748ab0762f0c910463dd472494d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782372"
---
# <a name="attribute-types"></a><span data-ttu-id="61947-102">属性类型</span><span class="sxs-lookup"><span data-stu-id="61947-102">Attribute Types</span></span>

<span data-ttu-id="61947-103">Cmdlet 属性可以按功能分组。</span><span class="sxs-lookup"><span data-stu-id="61947-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="61947-104">以下各节介绍了可用的属性，并说明了在调用特性时运行时的作用。</span><span class="sxs-lookup"><span data-stu-id="61947-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="61947-105">Cmdlet 属性</span><span class="sxs-lookup"><span data-stu-id="61947-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="61947-106">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="61947-106">Cmdlet</span></span>

<span data-ttu-id="61947-107">将 .NET Framework 类标识为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61947-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="61947-108">这是必需的基本属性。</span><span class="sxs-lookup"><span data-stu-id="61947-108">This is the required base attribute.</span></span>
<span data-ttu-id="61947-109">有关详细信息，请参阅[Cmdlet 特性声明](./cmdlet-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="61947-110">参数属性</span><span class="sxs-lookup"><span data-stu-id="61947-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="61947-111">参数</span><span class="sxs-lookup"><span data-stu-id="61947-111">Parameter</span></span>

<span data-ttu-id="61947-112">将 cmdlet 类中的公共属性标识为 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="61947-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="61947-113">有关详细信息，请参阅[参数属性声明](./parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="61947-114">Alias</span><span class="sxs-lookup"><span data-stu-id="61947-114">Alias</span></span>

<span data-ttu-id="61947-115">指定参数的一个或多个别名。</span><span class="sxs-lookup"><span data-stu-id="61947-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="61947-116">有关详细信息，请参阅[Alias 特性声明](./alias-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="61947-117">参数验证特性</span><span class="sxs-lookup"><span data-stu-id="61947-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="61947-118">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="61947-118">ValidateCount</span></span>

<span data-ttu-id="61947-119">指定 cmdlet 参数允许的最小和最大参数数量。</span><span class="sxs-lookup"><span data-stu-id="61947-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="61947-120">有关详细信息，请参阅[ValidateCount 特性声明](./validatecount-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="61947-121">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="61947-121">ValidateLength</span></span>

<span data-ttu-id="61947-122">指定 cmdlet 参数参数的最小和最大字符数。</span><span class="sxs-lookup"><span data-stu-id="61947-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="61947-123">有关详细信息，请参阅[ValidateLength 特性声明](./validatelength-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="61947-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="61947-124">ValidatePattern</span></span>

<span data-ttu-id="61947-125">指定 cmdlet 参数参数必须匹配的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="61947-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="61947-126">有关详细信息，请参阅[ValidatePattern 特性声明](./validatepattern-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="61947-127">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="61947-127">ValidateRange</span></span>

<span data-ttu-id="61947-128">指定 cmdlet 参数参数的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="61947-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="61947-129">有关详细信息，请参阅[ValidateRange 特性声明](./validaterange-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="61947-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="61947-130">ValidateSet</span></span>

<span data-ttu-id="61947-131">为 cmdlet 参数参数指定一组有效值。</span><span class="sxs-lookup"><span data-stu-id="61947-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="61947-132">有关详细信息，请参阅[ValidateSet 特性声明](./validateset-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="61947-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="61947-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61947-133">See Also</span></span>

[<span data-ttu-id="61947-134">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="61947-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
