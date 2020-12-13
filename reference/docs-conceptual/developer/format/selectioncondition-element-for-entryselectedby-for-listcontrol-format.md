---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for ListControl (Format)
description: SelectionCondition Element for EntrySelectedBy for ListControl (Format)
ms.openlocfilehash: e93499691dd0046265e43abd26497b2974546083
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655087"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="976ec-103">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="976ec-103">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="976ec-104">定义使用此列表视图的定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="976ec-104">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="976ec-105">对于列表定义可以指定的选择条件数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="976ec-105">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="976ec-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy (格式) ListEntry 元素 (SelectionCondition) 格式</span><span class="sxs-lookup"><span data-stu-id="976ec-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="976ec-107">语法</span><span class="sxs-lookup"><span data-stu-id="976ec-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="976ec-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="976ec-108">Attributes and Elements</span></span>

<span data-ttu-id="976ec-109">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="976ec-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="976ec-110">特性</span><span class="sxs-lookup"><span data-stu-id="976ec-110">Attributes</span></span>

<span data-ttu-id="976ec-111">无。</span><span class="sxs-lookup"><span data-stu-id="976ec-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="976ec-112">子元素</span><span class="sxs-lookup"><span data-stu-id="976ec-112">Child Elements</span></span>

|<span data-ttu-id="976ec-113">元素</span><span class="sxs-lookup"><span data-stu-id="976ec-113">Element</span></span>|<span data-ttu-id="976ec-114">描述</span><span class="sxs-lookup"><span data-stu-id="976ec-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="976ec-115">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="976ec-115">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="976ec-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="976ec-116">Optional element.</span></span><br /><br /> <span data-ttu-id="976ec-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="976ec-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="976ec-118">用于 ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="976ec-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="976ec-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="976ec-119">Optional element.</span></span><br /><br /> <span data-ttu-id="976ec-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="976ec-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="976ec-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="976ec-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="976ec-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="976ec-122">Optional element.</span></span><br /><br /> <span data-ttu-id="976ec-123">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="976ec-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="976ec-124">用于 ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="976ec-124">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="976ec-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="976ec-125">Optional element.</span></span><br /><br /> <span data-ttu-id="976ec-126">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="976ec-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="976ec-127">父元素</span><span class="sxs-lookup"><span data-stu-id="976ec-127">Parent Elements</span></span>

|<span data-ttu-id="976ec-128">元素</span><span class="sxs-lookup"><span data-stu-id="976ec-128">Element</span></span>|<span data-ttu-id="976ec-129">描述</span><span class="sxs-lookup"><span data-stu-id="976ec-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="976ec-130">TableRowEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="976ec-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="976ec-131">定义使用此表项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="976ec-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="976ec-132">备注</span><span class="sxs-lookup"><span data-stu-id="976ec-132">Remarks</span></span>

<span data-ttu-id="976ec-133">lWhen 正在定义选择条件，以下要求适用：</span><span class="sxs-lookup"><span data-stu-id="976ec-133">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="976ec-134">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="976ec-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="976ec-135">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="976ec-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="976ec-136">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="976ec-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="976ec-137">有关列表视图的其他组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="976ec-137">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="976ec-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="976ec-138">See Also</span></span>

[<span data-ttu-id="976ec-139">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="976ec-139">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="976ec-140">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="976ec-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="976ec-141">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="976ec-141">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="976ec-142">ListEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="976ec-142">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="976ec-143">ListEntry (格式的 EntrySelectedBy 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="976ec-143">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="976ec-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="976ec-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
