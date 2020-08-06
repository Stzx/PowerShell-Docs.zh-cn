---
title: CustomControl (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 52858dba5c7a5222b5410835f3374546ce8b88a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785347"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="c57f8-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="c57f8-103">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="c57f8-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="c57f8-104">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="c57f8-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="c57f8-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) CustomControl 元素 for view (Format) CustomEntries 元素 for CustomControl for CustomEntry for CustomEntries for for CustomControl for CustomItem for CustomEntry for CustomControl for EntrySelectedBy for CustomEntry for CustomControl for SelectionCondition EntrySelectedBy CustomControl for view (format) 元素 () </span><span class="sxs-lookup"><span data-stu-id="c57f8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c57f8-106">语法</span><span class="sxs-lookup"><span data-stu-id="c57f8-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c57f8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c57f8-107">Attributes and Elements</span></span>

<span data-ttu-id="c57f8-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="c57f8-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c57f8-109">特性</span><span class="sxs-lookup"><span data-stu-id="c57f8-109">Attributes</span></span>

<span data-ttu-id="c57f8-110">无。</span><span class="sxs-lookup"><span data-stu-id="c57f8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c57f8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="c57f8-111">Child Elements</span></span>

|<span data-ttu-id="c57f8-112">元素</span><span class="sxs-lookup"><span data-stu-id="c57f8-112">Element</span></span>|<span data-ttu-id="c57f8-113">描述</span><span class="sxs-lookup"><span data-stu-id="c57f8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c57f8-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="c57f8-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c57f8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="c57f8-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="c57f8-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="c57f8-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="c57f8-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c57f8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c57f8-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="c57f8-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="c57f8-120">SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) </span><span class="sxs-lookup"><span data-stu-id="c57f8-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="c57f8-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c57f8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c57f8-122">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="c57f8-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="c57f8-123">TypeName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="c57f8-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c57f8-124">Optional element.</span></span><br /><br /> <span data-ttu-id="c57f8-125">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="c57f8-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c57f8-126">父元素</span><span class="sxs-lookup"><span data-stu-id="c57f8-126">Parent Elements</span></span>

|<span data-ttu-id="c57f8-127">元素</span><span class="sxs-lookup"><span data-stu-id="c57f8-127">Element</span></span>|<span data-ttu-id="c57f8-128">描述</span><span class="sxs-lookup"><span data-stu-id="c57f8-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c57f8-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="c57f8-130">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="c57f8-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c57f8-131">备注</span><span class="sxs-lookup"><span data-stu-id="c57f8-131">Remarks</span></span>

<span data-ttu-id="c57f8-132">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="c57f8-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="c57f8-133">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="c57f8-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="c57f8-134">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="c57f8-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="c57f8-135">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="c57f8-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c57f8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c57f8-136">See Also</span></span>

[<span data-ttu-id="c57f8-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c57f8-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c57f8-139">SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) </span><span class="sxs-lookup"><span data-stu-id="c57f8-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c57f8-140">TypeName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c57f8-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="c57f8-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c57f8-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="c57f8-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
