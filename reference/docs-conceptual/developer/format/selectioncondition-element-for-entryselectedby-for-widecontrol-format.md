---
title: WideControl (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4115ad1ee8729ea4fc16bc19698018d2f4ed9be1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772699"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="942ab-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="942ab-103">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="942ab-103">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="942ab-104">对于可为宽输入定义指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="942ab-104">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="942ab-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (SelectionCondition) 格式</span><span class="sxs-lookup"><span data-stu-id="942ab-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="942ab-106">语法</span><span class="sxs-lookup"><span data-stu-id="942ab-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="942ab-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="942ab-107">Attributes and Elements</span></span>

<span data-ttu-id="942ab-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="942ab-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="942ab-109">您必须指定一个 `PropertyName` 或 `ScriptBlock` 元素。</span><span class="sxs-lookup"><span data-stu-id="942ab-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="942ab-110">`SelectionSetName`和 `TypeName` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="942ab-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="942ab-111">可以指定任一元素中的一个。</span><span class="sxs-lookup"><span data-stu-id="942ab-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="942ab-112">特性</span><span class="sxs-lookup"><span data-stu-id="942ab-112">Attributes</span></span>

<span data-ttu-id="942ab-113">无。</span><span class="sxs-lookup"><span data-stu-id="942ab-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="942ab-114">子元素</span><span class="sxs-lookup"><span data-stu-id="942ab-114">Child Elements</span></span>

|<span data-ttu-id="942ab-115">元素</span><span class="sxs-lookup"><span data-stu-id="942ab-115">Element</span></span>|<span data-ttu-id="942ab-116">描述</span><span class="sxs-lookup"><span data-stu-id="942ab-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="942ab-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="942ab-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="942ab-118">Optional element.</span></span><br /><br /> <span data-ttu-id="942ab-119">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="942ab-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="942ab-120">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="942ab-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="942ab-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="942ab-121">Optional element.</span></span><br /><br /> <span data-ttu-id="942ab-122">指定触发条件的脚本块。</span><span class="sxs-lookup"><span data-stu-id="942ab-122">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="942ab-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="942ab-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="942ab-124">Optional element.</span></span><br /><br /> <span data-ttu-id="942ab-125">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="942ab-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="942ab-126">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="942ab-126">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="942ab-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="942ab-127">Optional element.</span></span><br /><br /> <span data-ttu-id="942ab-128">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="942ab-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="942ab-129">父元素</span><span class="sxs-lookup"><span data-stu-id="942ab-129">Parent Elements</span></span>

|<span data-ttu-id="942ab-130">元素</span><span class="sxs-lookup"><span data-stu-id="942ab-130">Element</span></span>|<span data-ttu-id="942ab-131">描述</span><span class="sxs-lookup"><span data-stu-id="942ab-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="942ab-132">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-132">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="942ab-133">定义使用此宽项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="942ab-133">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="942ab-134">备注</span><span class="sxs-lookup"><span data-stu-id="942ab-134">Remarks</span></span>

<span data-ttu-id="942ab-135">每个宽条目都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="942ab-135">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="942ab-136">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="942ab-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="942ab-137">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="942ab-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="942ab-138">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="942ab-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="942ab-139">有关如何使用选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="942ab-139">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="942ab-140">有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="942ab-140">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="942ab-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="942ab-141">See Also</span></span>

[<span data-ttu-id="942ab-142">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="942ab-142">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="942ab-143">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="942ab-143">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="942ab-144">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-144">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="942ab-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="942ab-146">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="942ab-146">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="942ab-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="942ab-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="942ab-148">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="942ab-148">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="942ab-149">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="942ab-149">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
