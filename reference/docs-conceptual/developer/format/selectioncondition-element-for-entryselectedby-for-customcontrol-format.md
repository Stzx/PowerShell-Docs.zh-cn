---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for CustomControl (Format)
description: SelectionCondition Element for EntrySelectedBy for CustomControl (Format)
ms.openlocfilehash: 6d4cc5a2d5fef0445d586e320b3729d3a7044063
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649767"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="ae0ae-103">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-103">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="ae0ae-104">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="ae0ae-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ae0ae-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) CustomControl 元素 for view (Format) CustomEntries 元素 for CustomControl for CustomEntry for CustomEntries for for CustomControl for CustomItem for CustomEntry for CustomControl for EntrySelectedBy for CustomEntry for CustomControl for SelectionCondition EntrySelectedBy CustomControl for view (format) 元素 () </span><span class="sxs-lookup"><span data-stu-id="ae0ae-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ae0ae-107">语法</span><span class="sxs-lookup"><span data-stu-id="ae0ae-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae0ae-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ae0ae-108">Attributes and Elements</span></span>

<span data-ttu-id="ae0ae-109">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae0ae-110">特性</span><span class="sxs-lookup"><span data-stu-id="ae0ae-110">Attributes</span></span>

<span data-ttu-id="ae0ae-111">无。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ae0ae-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ae0ae-112">Child Elements</span></span>

|<span data-ttu-id="ae0ae-113">元素</span><span class="sxs-lookup"><span data-stu-id="ae0ae-113">Element</span></span>|<span data-ttu-id="ae0ae-114">描述</span><span class="sxs-lookup"><span data-stu-id="ae0ae-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae0ae-115">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-115">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ae0ae-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ae0ae-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="ae0ae-118">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-118">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ae0ae-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ae0ae-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="ae0ae-121">SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) </span><span class="sxs-lookup"><span data-stu-id="ae0ae-121">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ae0ae-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-122">Optional element.</span></span><br /><br /> <span data-ttu-id="ae0ae-123">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="ae0ae-124">TypeName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-124">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ae0ae-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-125">Optional element.</span></span><br /><br /> <span data-ttu-id="ae0ae-126">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ae0ae-127">父元素</span><span class="sxs-lookup"><span data-stu-id="ae0ae-127">Parent Elements</span></span>

|<span data-ttu-id="ae0ae-128">元素</span><span class="sxs-lookup"><span data-stu-id="ae0ae-128">Element</span></span>|<span data-ttu-id="ae0ae-129">描述</span><span class="sxs-lookup"><span data-stu-id="ae0ae-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae0ae-130">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-130">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="ae0ae-131">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ae0ae-132">备注</span><span class="sxs-lookup"><span data-stu-id="ae0ae-132">Remarks</span></span>

<span data-ttu-id="ae0ae-133">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="ae0ae-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="ae0ae-134">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="ae0ae-135">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="ae0ae-136">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae0ae-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae0ae-137">See Also</span></span>

[<span data-ttu-id="ae0ae-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ae0ae-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ae0ae-140">SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) </span><span class="sxs-lookup"><span data-stu-id="ae0ae-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ae0ae-141">TypeName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-141">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ae0ae-142">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae0ae-142">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ae0ae-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ae0ae-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
