---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)
description: SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645786"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="ba793-103">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-103">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ba793-104">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="ba793-104">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="ba793-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="ba793-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ba793-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素，用于 for for for for for for for for for for for for for for for for CustomEntry CustomControl EntrySelectedBy CustomEntry) </span><span class="sxs-lookup"><span data-stu-id="ba793-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ba793-107">语法</span><span class="sxs-lookup"><span data-stu-id="ba793-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ba793-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba793-108">Attributes and Elements</span></span>

<span data-ttu-id="ba793-109">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="ba793-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ba793-110">特性</span><span class="sxs-lookup"><span data-stu-id="ba793-110">Attributes</span></span>

<span data-ttu-id="ba793-111">无。</span><span class="sxs-lookup"><span data-stu-id="ba793-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ba793-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ba793-112">Child Elements</span></span>

|<span data-ttu-id="ba793-113">元素</span><span class="sxs-lookup"><span data-stu-id="ba793-113">Element</span></span>|<span data-ttu-id="ba793-114">描述</span><span class="sxs-lookup"><span data-stu-id="ba793-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ba793-115">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-115">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="ba793-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ba793-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ba793-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="ba793-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="ba793-118">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-118">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="ba793-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ba793-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ba793-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="ba793-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="ba793-121">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-121">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="ba793-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ba793-122">Optional element.</span></span><br /><br /> <span data-ttu-id="ba793-123">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="ba793-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="ba793-124">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-124">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="ba793-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ba793-125">Optional element.</span></span><br /><br /> <span data-ttu-id="ba793-126">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="ba793-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ba793-127">父元素</span><span class="sxs-lookup"><span data-stu-id="ba793-127">Parent Elements</span></span>

|<span data-ttu-id="ba793-128">元素</span><span class="sxs-lookup"><span data-stu-id="ba793-128">Element</span></span>|<span data-ttu-id="ba793-129">描述</span><span class="sxs-lookup"><span data-stu-id="ba793-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ba793-130">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-130">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="ba793-131">定义使用此公共控件定义的此项的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="ba793-131">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ba793-132">备注</span><span class="sxs-lookup"><span data-stu-id="ba793-132">Remarks</span></span>

<span data-ttu-id="ba793-133">定义选择条件时，必须遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="ba793-133">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="ba793-134">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ba793-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="ba793-135">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ba793-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="ba793-136">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ba793-136">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba793-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba793-137">See Also</span></span>

[<span data-ttu-id="ba793-138">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-138">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="ba793-139">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-139">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="ba793-140">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-140">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="ba793-141">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-141">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="ba793-142">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba793-142">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="ba793-143">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="ba793-143">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
