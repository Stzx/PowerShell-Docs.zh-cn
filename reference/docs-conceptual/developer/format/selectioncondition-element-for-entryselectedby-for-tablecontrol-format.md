---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for TableControl (Format)
description: SelectionCondition Element for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: 22f304615c6433ffb67f3b4046b645d0c37be8a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645765"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="4fbcc-103">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4fbcc-103">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="4fbcc-104">定义必须存在才能用于此表视图定义的条件。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-104">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="4fbcc-105">对于可为表定义指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-105">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="4fbcc-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy (格式) TableRowEntry 元素 (SelectionCondition) 格式</span><span class="sxs-lookup"><span data-stu-id="4fbcc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4fbcc-107">语法</span><span class="sxs-lookup"><span data-stu-id="4fbcc-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fbcc-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4fbcc-108">Attributes and Elements</span></span>

<span data-ttu-id="4fbcc-109">以下各节介绍了 SelectionCondition 元素的属性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-109">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fbcc-110">特性</span><span class="sxs-lookup"><span data-stu-id="4fbcc-110">Attributes</span></span>

<span data-ttu-id="4fbcc-111">无。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4fbcc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4fbcc-112">Child Elements</span></span>

|<span data-ttu-id="4fbcc-113">元素</span><span class="sxs-lookup"><span data-stu-id="4fbcc-113">Element</span></span>|<span data-ttu-id="4fbcc-114">描述</span><span class="sxs-lookup"><span data-stu-id="4fbcc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fbcc-115">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="4fbcc-115">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="4fbcc-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-116">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbcc-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4fbcc-118">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="4fbcc-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="4fbcc-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-119">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbcc-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="4fbcc-121">用于 EntrySelectedBy for TableRowEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素 </span><span class="sxs-lookup"><span data-stu-id="4fbcc-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="4fbcc-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-122">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbcc-123">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="4fbcc-124">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="4fbcc-124">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="4fbcc-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-125">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbcc-126">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4fbcc-127">父元素</span><span class="sxs-lookup"><span data-stu-id="4fbcc-127">Parent Elements</span></span>

|<span data-ttu-id="4fbcc-128">元素</span><span class="sxs-lookup"><span data-stu-id="4fbcc-128">Element</span></span>|<span data-ttu-id="4fbcc-129">描述</span><span class="sxs-lookup"><span data-stu-id="4fbcc-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fbcc-130">TableRowEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4fbcc-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="4fbcc-131">定义使用此表项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4fbcc-132">备注</span><span class="sxs-lookup"><span data-stu-id="4fbcc-132">Remarks</span></span>

<span data-ttu-id="4fbcc-133">每个列表项必须至少定义一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-133">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="4fbcc-134">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="4fbcc-134">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="4fbcc-135">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-135">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="4fbcc-136">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-136">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="4fbcc-137">有关如何使用选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-137">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4fbcc-138">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="4fbcc-138">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4fbcc-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fbcc-139">See Also</span></span>

[<span data-ttu-id="4fbcc-140">创建表视图</span><span class="sxs-lookup"><span data-stu-id="4fbcc-140">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4fbcc-141">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="4fbcc-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4fbcc-142">EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4fbcc-142">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="4fbcc-143">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="4fbcc-143">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="4fbcc-144">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="4fbcc-144">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="4fbcc-145">用于 EntrySelectedBy for TableRowEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素 </span><span class="sxs-lookup"><span data-stu-id="4fbcc-145">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="4fbcc-146">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="4fbcc-146">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="4fbcc-147">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="4fbcc-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
