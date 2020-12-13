---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)
description: SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 3ecf7fde99b9ee66a153eea416792f351ff62af3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647929"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="f12cb-103">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f12cb-103">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="f12cb-104">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f12cb-104">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="f12cb-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition) 格式 (EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="f12cb-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f12cb-106">语法</span><span class="sxs-lookup"><span data-stu-id="f12cb-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f12cb-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f12cb-107">Attributes and Elements</span></span>

<span data-ttu-id="f12cb-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="f12cb-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="f12cb-109">您必须指定一个 `PropertyName` 或 `ScriptBlock` 元素。</span><span class="sxs-lookup"><span data-stu-id="f12cb-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="f12cb-110">`SelectionSetName`和 `TypeName` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="f12cb-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="f12cb-111">可以指定任一元素中的一个。</span><span class="sxs-lookup"><span data-stu-id="f12cb-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f12cb-112">特性</span><span class="sxs-lookup"><span data-stu-id="f12cb-112">Attributes</span></span>

<span data-ttu-id="f12cb-113">无。</span><span class="sxs-lookup"><span data-stu-id="f12cb-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f12cb-114">子元素</span><span class="sxs-lookup"><span data-stu-id="f12cb-114">Child Elements</span></span>

|<span data-ttu-id="f12cb-115">元素</span><span class="sxs-lookup"><span data-stu-id="f12cb-115">Element</span></span>|<span data-ttu-id="f12cb-116">描述</span><span class="sxs-lookup"><span data-stu-id="f12cb-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f12cb-117">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f12cb-117">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f12cb-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f12cb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f12cb-119">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="f12cb-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f12cb-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f12cb-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f12cb-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f12cb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="f12cb-122">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="f12cb-122">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="f12cb-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f12cb-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f12cb-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f12cb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="f12cb-125">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="f12cb-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="f12cb-126">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f12cb-126">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f12cb-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f12cb-127">Optional element.</span></span><br /><br /> <span data-ttu-id="f12cb-128">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="f12cb-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f12cb-129">父元素</span><span class="sxs-lookup"><span data-stu-id="f12cb-129">Parent Elements</span></span>

|<span data-ttu-id="f12cb-130">元素</span><span class="sxs-lookup"><span data-stu-id="f12cb-130">Element</span></span>|<span data-ttu-id="f12cb-131">描述</span><span class="sxs-lookup"><span data-stu-id="f12cb-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f12cb-132">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f12cb-132">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="f12cb-133">定义通过此定义扩展哪些 .NET 集合对象。</span><span class="sxs-lookup"><span data-stu-id="f12cb-133">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f12cb-134">备注</span><span class="sxs-lookup"><span data-stu-id="f12cb-134">Remarks</span></span>

<span data-ttu-id="f12cb-135">每个定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="f12cb-135">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f12cb-136">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="f12cb-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="f12cb-137">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f12cb-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="f12cb-138">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f12cb-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="f12cb-139">有关如何使用选择条件的详细信息，请参阅 [定义 Diplaying 数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f12cb-139">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f12cb-140">有关大视图的其他组件的详细信息，请参阅 [宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f12cb-140">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f12cb-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f12cb-141">See Also</span></span>

[<span data-ttu-id="f12cb-142">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="f12cb-142">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f12cb-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f12cb-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
