---
title: TableControl (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4a829f9daef22c4b3fd6b21dfb3af2f8539bdeb3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780281"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="483a7-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="483a7-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="483a7-103">定义必须存在才能用于此表视图定义的条件。</span><span class="sxs-lookup"><span data-stu-id="483a7-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="483a7-104">对于可为表定义指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="483a7-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="483a7-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy (格式) TableRowEntry 元素 (SelectionCondition) 格式</span><span class="sxs-lookup"><span data-stu-id="483a7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="483a7-106">语法</span><span class="sxs-lookup"><span data-stu-id="483a7-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="483a7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="483a7-107">Attributes and Elements</span></span>

<span data-ttu-id="483a7-108">以下各节介绍了 SelectionCondition 元素的属性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="483a7-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="483a7-109">特性</span><span class="sxs-lookup"><span data-stu-id="483a7-109">Attributes</span></span>

<span data-ttu-id="483a7-110">无。</span><span class="sxs-lookup"><span data-stu-id="483a7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="483a7-111">子元素</span><span class="sxs-lookup"><span data-stu-id="483a7-111">Child Elements</span></span>

|<span data-ttu-id="483a7-112">元素</span><span class="sxs-lookup"><span data-stu-id="483a7-112">Element</span></span>|<span data-ttu-id="483a7-113">描述</span><span class="sxs-lookup"><span data-stu-id="483a7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="483a7-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="483a7-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="483a7-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="483a7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="483a7-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="483a7-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="483a7-117">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="483a7-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="483a7-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="483a7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="483a7-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="483a7-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="483a7-120">用于 EntrySelectedBy for TableRowEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素</span><span class="sxs-lookup"><span data-stu-id="483a7-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="483a7-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="483a7-121">Optional element.</span></span><br /><br /> <span data-ttu-id="483a7-122">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="483a7-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="483a7-123">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="483a7-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="483a7-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="483a7-124">Optional element.</span></span><br /><br /> <span data-ttu-id="483a7-125">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="483a7-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="483a7-126">父元素</span><span class="sxs-lookup"><span data-stu-id="483a7-126">Parent Elements</span></span>

|<span data-ttu-id="483a7-127">元素</span><span class="sxs-lookup"><span data-stu-id="483a7-127">Element</span></span>|<span data-ttu-id="483a7-128">描述</span><span class="sxs-lookup"><span data-stu-id="483a7-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="483a7-129">TableRowEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="483a7-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="483a7-130">定义使用此表项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="483a7-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="483a7-131">备注</span><span class="sxs-lookup"><span data-stu-id="483a7-131">Remarks</span></span>

<span data-ttu-id="483a7-132">每个列表项必须至少定义一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="483a7-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="483a7-133">定义选择条件时，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="483a7-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="483a7-134">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="483a7-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="483a7-135">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="483a7-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="483a7-136">有关如何使用选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="483a7-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="483a7-137">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="483a7-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="483a7-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="483a7-138">See Also</span></span>

[<span data-ttu-id="483a7-139">创建表视图</span><span class="sxs-lookup"><span data-stu-id="483a7-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="483a7-140">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="483a7-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="483a7-141">EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="483a7-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="483a7-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="483a7-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="483a7-143">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="483a7-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="483a7-144">用于 EntrySelectedBy for TableRowEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素</span><span class="sxs-lookup"><span data-stu-id="483a7-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="483a7-145">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="483a7-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="483a7-146">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="483a7-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
