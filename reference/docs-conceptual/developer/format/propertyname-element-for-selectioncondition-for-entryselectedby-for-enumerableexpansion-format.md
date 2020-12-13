---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
description: PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 8e28118894661b50e90a5ccc86a36fbbe77e4b03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665832"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="d5f50-103">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d5f50-103">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="d5f50-104">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="d5f50-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="d5f50-105">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="d5f50-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="d5f50-106">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy 的元素) EnumerableExpansion (格式) </span><span class="sxs-lookup"><span data-stu-id="d5f50-106">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d5f50-107">语法</span><span class="sxs-lookup"><span data-stu-id="d5f50-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d5f50-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d5f50-108">Attributes and Elements</span></span>

<span data-ttu-id="d5f50-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="d5f50-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d5f50-110">特性</span><span class="sxs-lookup"><span data-stu-id="d5f50-110">Attributes</span></span>

<span data-ttu-id="d5f50-111">无。</span><span class="sxs-lookup"><span data-stu-id="d5f50-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d5f50-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d5f50-112">Child Elements</span></span>

<span data-ttu-id="d5f50-113">无。</span><span class="sxs-lookup"><span data-stu-id="d5f50-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d5f50-114">父元素</span><span class="sxs-lookup"><span data-stu-id="d5f50-114">Parent Elements</span></span>

|<span data-ttu-id="d5f50-115">元素</span><span class="sxs-lookup"><span data-stu-id="d5f50-115">Element</span></span>|<span data-ttu-id="d5f50-116">描述</span><span class="sxs-lookup"><span data-stu-id="d5f50-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5f50-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d5f50-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d5f50-118">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d5f50-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d5f50-119">文本值</span><span class="sxs-lookup"><span data-stu-id="d5f50-119">Text Value</span></span>

<span data-ttu-id="d5f50-120">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="d5f50-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5f50-121">备注</span><span class="sxs-lookup"><span data-stu-id="d5f50-121">Remarks</span></span>

<span data-ttu-id="d5f50-122">选择条件必须指定至少一个要计算的属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="d5f50-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="d5f50-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d5f50-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5f50-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5f50-124">See Also</span></span>

[<span data-ttu-id="d5f50-125">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="d5f50-125">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d5f50-126">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d5f50-126">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="d5f50-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d5f50-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="d5f50-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d5f50-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
