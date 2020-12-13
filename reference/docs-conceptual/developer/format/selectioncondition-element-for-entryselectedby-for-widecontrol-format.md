---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for WideControl (Format)
description: SelectionCondition Element for EntrySelectedBy for WideControl (Format)
ms.openlocfilehash: 8c51ca72edc6ad174dc289c61a8987e8f9495d19
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655104"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="f3928-103">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-103">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="f3928-104">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f3928-104">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="f3928-105">对于可为宽输入定义指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="f3928-105">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="f3928-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (SelectionCondition) 格式</span><span class="sxs-lookup"><span data-stu-id="f3928-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f3928-107">语法</span><span class="sxs-lookup"><span data-stu-id="f3928-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3928-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f3928-108">Attributes and Elements</span></span>

<span data-ttu-id="f3928-109">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="f3928-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="f3928-110">您必须指定一个 `PropertyName` 或 `ScriptBlock` 元素。</span><span class="sxs-lookup"><span data-stu-id="f3928-110">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="f3928-111">`SelectionSetName`和 `TypeName` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="f3928-111">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="f3928-112">可以指定任一元素中的一个。</span><span class="sxs-lookup"><span data-stu-id="f3928-112">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3928-113">特性</span><span class="sxs-lookup"><span data-stu-id="f3928-113">Attributes</span></span>

<span data-ttu-id="f3928-114">无。</span><span class="sxs-lookup"><span data-stu-id="f3928-114">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f3928-115">子元素</span><span class="sxs-lookup"><span data-stu-id="f3928-115">Child Elements</span></span>

|<span data-ttu-id="f3928-116">元素</span><span class="sxs-lookup"><span data-stu-id="f3928-116">Element</span></span>|<span data-ttu-id="f3928-117">描述</span><span class="sxs-lookup"><span data-stu-id="f3928-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3928-118">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-118">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="f3928-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3928-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f3928-120">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="f3928-120">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f3928-121">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="f3928-121">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f3928-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3928-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f3928-123">指定触发条件的脚本块。</span><span class="sxs-lookup"><span data-stu-id="f3928-123">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="f3928-124">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-124">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="f3928-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3928-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f3928-126">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="f3928-126">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="f3928-127">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="f3928-127">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f3928-128">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3928-128">Optional element.</span></span><br /><br /> <span data-ttu-id="f3928-129">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="f3928-129">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f3928-130">父元素</span><span class="sxs-lookup"><span data-stu-id="f3928-130">Parent Elements</span></span>

|<span data-ttu-id="f3928-131">元素</span><span class="sxs-lookup"><span data-stu-id="f3928-131">Element</span></span>|<span data-ttu-id="f3928-132">描述</span><span class="sxs-lookup"><span data-stu-id="f3928-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3928-133">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-133">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="f3928-134">定义使用此宽项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="f3928-134">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3928-135">备注</span><span class="sxs-lookup"><span data-stu-id="f3928-135">Remarks</span></span>

<span data-ttu-id="f3928-136">每个宽条目都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="f3928-136">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f3928-137">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="f3928-137">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="f3928-138">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f3928-138">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="f3928-139">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f3928-139">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="f3928-140">有关如何使用选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f3928-140">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f3928-141">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f3928-141">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3928-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3928-142">See Also</span></span>

[<span data-ttu-id="f3928-143">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="f3928-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f3928-144">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="f3928-144">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f3928-145">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-145">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="f3928-146">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-146">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="f3928-147">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="f3928-147">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f3928-148">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f3928-148">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="f3928-149">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="f3928-149">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f3928-150">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f3928-150">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
