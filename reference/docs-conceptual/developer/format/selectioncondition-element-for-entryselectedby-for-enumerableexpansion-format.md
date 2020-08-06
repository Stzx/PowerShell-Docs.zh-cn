---
title: EnumerableExpansion (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d5858145e092dc962174a776889a4f62db366d71
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785330"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="4d750-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4d750-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="4d750-103">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="4d750-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="4d750-104">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition) 格式 (EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="4d750-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4d750-105">语法</span><span class="sxs-lookup"><span data-stu-id="4d750-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4d750-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4d750-106">Attributes and Elements</span></span>

<span data-ttu-id="4d750-107">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="4d750-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="4d750-108">您必须指定一个 `PropertyName` 或 `ScriptBlock` 元素。</span><span class="sxs-lookup"><span data-stu-id="4d750-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="4d750-109">`SelectionSetName`和 `TypeName` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d750-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="4d750-110">可以指定任一元素中的一个。</span><span class="sxs-lookup"><span data-stu-id="4d750-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4d750-111">特性</span><span class="sxs-lookup"><span data-stu-id="4d750-111">Attributes</span></span>

<span data-ttu-id="4d750-112">无。</span><span class="sxs-lookup"><span data-stu-id="4d750-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4d750-113">子元素</span><span class="sxs-lookup"><span data-stu-id="4d750-113">Child Elements</span></span>

|<span data-ttu-id="4d750-114">元素</span><span class="sxs-lookup"><span data-stu-id="4d750-114">Element</span></span>|<span data-ttu-id="4d750-115">描述</span><span class="sxs-lookup"><span data-stu-id="4d750-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4d750-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4d750-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4d750-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4d750-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4d750-118">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="4d750-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4d750-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4d750-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4d750-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4d750-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4d750-121">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="4d750-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="4d750-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4d750-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4d750-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4d750-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4d750-124">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="4d750-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="4d750-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4d750-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4d750-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4d750-126">Optional element.</span></span><br /><br /> <span data-ttu-id="4d750-127">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="4d750-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4d750-128">父元素</span><span class="sxs-lookup"><span data-stu-id="4d750-128">Parent Elements</span></span>

|<span data-ttu-id="4d750-129">元素</span><span class="sxs-lookup"><span data-stu-id="4d750-129">Element</span></span>|<span data-ttu-id="4d750-130">描述</span><span class="sxs-lookup"><span data-stu-id="4d750-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4d750-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4d750-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="4d750-132">定义通过此定义扩展哪些 .NET 集合对象。</span><span class="sxs-lookup"><span data-stu-id="4d750-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4d750-133">备注</span><span class="sxs-lookup"><span data-stu-id="4d750-133">Remarks</span></span>

<span data-ttu-id="4d750-134">每个定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="4d750-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="4d750-135">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="4d750-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="4d750-136">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="4d750-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="4d750-137">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="4d750-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="4d750-138">有关如何使用选择条件的详细信息，请参阅[定义 Diplaying 数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4d750-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4d750-139">有关大视图的其他组件的详细信息，请参阅[宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="4d750-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d750-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d750-140">See Also</span></span>

[<span data-ttu-id="4d750-141">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="4d750-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4d750-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4d750-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
