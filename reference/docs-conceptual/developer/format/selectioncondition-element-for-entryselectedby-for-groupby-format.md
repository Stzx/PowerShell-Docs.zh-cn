---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for GroupBy (Format)
description: SelectionCondition Element for EntrySelectedBy for GroupBy (Format)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664750"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="00380-103">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-103">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="00380-104">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="00380-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="00380-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="00380-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="00380-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="00380-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="00380-107">语法</span><span class="sxs-lookup"><span data-stu-id="00380-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="00380-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="00380-108">Attributes and Elements</span></span>

<span data-ttu-id="00380-109">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="00380-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="00380-110">特性</span><span class="sxs-lookup"><span data-stu-id="00380-110">Attributes</span></span>

<span data-ttu-id="00380-111">无。</span><span class="sxs-lookup"><span data-stu-id="00380-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="00380-112">子元素</span><span class="sxs-lookup"><span data-stu-id="00380-112">Child Elements</span></span>

|<span data-ttu-id="00380-113">元素</span><span class="sxs-lookup"><span data-stu-id="00380-113">Element</span></span>|<span data-ttu-id="00380-114">描述</span><span class="sxs-lookup"><span data-stu-id="00380-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00380-115">PropertyName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-115">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="00380-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="00380-116">Optional element.</span></span><br /><br /> <span data-ttu-id="00380-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="00380-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="00380-118">GroupBy (格式的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="00380-118">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="00380-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="00380-119">Optional element.</span></span><br /><br /> <span data-ttu-id="00380-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="00380-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="00380-121">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-121">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="00380-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="00380-122">Optional element.</span></span><br /><br /> <span data-ttu-id="00380-123">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="00380-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="00380-124">GroupBy (格式的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="00380-124">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="00380-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="00380-125">Optional element.</span></span><br /><br /> <span data-ttu-id="00380-126">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="00380-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="00380-127">父元素</span><span class="sxs-lookup"><span data-stu-id="00380-127">Parent Elements</span></span>

|<span data-ttu-id="00380-128">元素</span><span class="sxs-lookup"><span data-stu-id="00380-128">Element</span></span>|<span data-ttu-id="00380-129">描述</span><span class="sxs-lookup"><span data-stu-id="00380-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00380-130">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-130">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="00380-131">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="00380-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="00380-132">备注</span><span class="sxs-lookup"><span data-stu-id="00380-132">Remarks</span></span>

<span data-ttu-id="00380-133">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="00380-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="00380-134">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="00380-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="00380-135">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="00380-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="00380-136">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="00380-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00380-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00380-137">See Also</span></span>

[<span data-ttu-id="00380-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="00380-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="00380-140">SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) </span><span class="sxs-lookup"><span data-stu-id="00380-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="00380-141">GroupBy (格式的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="00380-141">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="00380-142">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00380-142">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="00380-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="00380-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
