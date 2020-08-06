---
title: View (Format) 的控件的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1c14b2638249bdbfe25f7a96e917d66ea10ed239
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787574"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="32366-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="32366-103">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="32366-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="32366-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="32366-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="32366-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (格式) CustomEntries 元素 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view (Format 的控件的 EntrySelectedBy 元素 (CustomEntry for view) 格式的控件 (SelectionCondition 元素) ) </span><span class="sxs-lookup"><span data-stu-id="32366-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="32366-106">语法</span><span class="sxs-lookup"><span data-stu-id="32366-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32366-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="32366-107">Attributes and Elements</span></span>

<span data-ttu-id="32366-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="32366-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="32366-109">特性</span><span class="sxs-lookup"><span data-stu-id="32366-109">Attributes</span></span>

<span data-ttu-id="32366-110">无。</span><span class="sxs-lookup"><span data-stu-id="32366-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="32366-111">子元素</span><span class="sxs-lookup"><span data-stu-id="32366-111">Child Elements</span></span>

|<span data-ttu-id="32366-112">元素</span><span class="sxs-lookup"><span data-stu-id="32366-112">Element</span></span>|<span data-ttu-id="32366-113">说明</span><span class="sxs-lookup"><span data-stu-id="32366-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32366-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="32366-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="32366-115">Optional element.</span></span><br /><br /> <span data-ttu-id="32366-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="32366-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="32366-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="32366-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="32366-118">Optional element.</span></span><br /><br /> <span data-ttu-id="32366-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="32366-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="32366-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="32366-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="32366-121">Optional element.</span></span><br /><br /> <span data-ttu-id="32366-122">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="32366-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="32366-123">TypeName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="32366-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="32366-124">Optional element.</span></span><br /><br /> <span data-ttu-id="32366-125">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="32366-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="32366-126">父元素</span><span class="sxs-lookup"><span data-stu-id="32366-126">Parent Elements</span></span>

|<span data-ttu-id="32366-127">元素</span><span class="sxs-lookup"><span data-stu-id="32366-127">Element</span></span>|<span data-ttu-id="32366-128">说明</span><span class="sxs-lookup"><span data-stu-id="32366-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32366-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="32366-130">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="32366-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="32366-131">备注</span><span class="sxs-lookup"><span data-stu-id="32366-131">Remarks</span></span>

<span data-ttu-id="32366-132">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="32366-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="32366-133">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="32366-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="32366-134">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="32366-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="32366-135">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="32366-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32366-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32366-136">See Also</span></span>

[<span data-ttu-id="32366-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="32366-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="32366-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="32366-140">TypeName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="32366-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="32366-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="32366-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="32366-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
