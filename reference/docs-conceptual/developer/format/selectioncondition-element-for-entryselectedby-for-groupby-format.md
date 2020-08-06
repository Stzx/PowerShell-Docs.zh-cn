---
title: GroupBy (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0930d8076c314c12cac6cdfa2b33716b7efeb6a9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772835"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="cfc57-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="cfc57-103">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="cfc57-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="cfc57-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="cfc57-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="cfc57-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="cfc57-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cfc57-106">语法</span><span class="sxs-lookup"><span data-stu-id="cfc57-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cfc57-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cfc57-107">Attributes and Elements</span></span>

<span data-ttu-id="cfc57-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="cfc57-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cfc57-109">特性</span><span class="sxs-lookup"><span data-stu-id="cfc57-109">Attributes</span></span>

<span data-ttu-id="cfc57-110">无。</span><span class="sxs-lookup"><span data-stu-id="cfc57-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cfc57-111">子元素</span><span class="sxs-lookup"><span data-stu-id="cfc57-111">Child Elements</span></span>

|<span data-ttu-id="cfc57-112">元素</span><span class="sxs-lookup"><span data-stu-id="cfc57-112">Element</span></span>|<span data-ttu-id="cfc57-113">说明</span><span class="sxs-lookup"><span data-stu-id="cfc57-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cfc57-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="cfc57-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cfc57-115">Optional element.</span></span><br /><br /> <span data-ttu-id="cfc57-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="cfc57-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="cfc57-117">GroupBy (格式的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="cfc57-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="cfc57-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cfc57-118">Optional element.</span></span><br /><br /> <span data-ttu-id="cfc57-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="cfc57-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="cfc57-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="cfc57-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cfc57-121">Optional element.</span></span><br /><br /> <span data-ttu-id="cfc57-122">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="cfc57-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="cfc57-123">GroupBy (格式的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="cfc57-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="cfc57-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cfc57-124">Optional element.</span></span><br /><br /> <span data-ttu-id="cfc57-125">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="cfc57-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cfc57-126">父元素</span><span class="sxs-lookup"><span data-stu-id="cfc57-126">Parent Elements</span></span>

|<span data-ttu-id="cfc57-127">元素</span><span class="sxs-lookup"><span data-stu-id="cfc57-127">Element</span></span>|<span data-ttu-id="cfc57-128">说明</span><span class="sxs-lookup"><span data-stu-id="cfc57-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cfc57-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="cfc57-130">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="cfc57-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cfc57-131">备注</span><span class="sxs-lookup"><span data-stu-id="cfc57-131">Remarks</span></span>

<span data-ttu-id="cfc57-132">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="cfc57-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="cfc57-133">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="cfc57-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="cfc57-134">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="cfc57-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="cfc57-135">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc57-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cfc57-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc57-136">See Also</span></span>

[<span data-ttu-id="cfc57-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cfc57-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cfc57-139">SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) </span><span class="sxs-lookup"><span data-stu-id="cfc57-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cfc57-140">GroupBy (格式的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="cfc57-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="cfc57-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cfc57-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="cfc57-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="cfc57-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
