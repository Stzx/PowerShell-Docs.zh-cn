---
title: ListControl (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 29626b181f21d168e1ebf973e01afeb411d9ef54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772767"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="a4b81-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a4b81-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="a4b81-103">定义使用此列表视图的定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a4b81-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="a4b81-104">对于列表定义可以指定的选择条件数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="a4b81-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="a4b81-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy (格式) ListEntry 元素 (SelectionCondition) 格式</span><span class="sxs-lookup"><span data-stu-id="a4b81-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4b81-106">语法</span><span class="sxs-lookup"><span data-stu-id="a4b81-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4b81-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a4b81-107">Attributes and Elements</span></span>

<span data-ttu-id="a4b81-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="a4b81-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4b81-109">特性</span><span class="sxs-lookup"><span data-stu-id="a4b81-109">Attributes</span></span>

<span data-ttu-id="a4b81-110">无。</span><span class="sxs-lookup"><span data-stu-id="a4b81-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4b81-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a4b81-111">Child Elements</span></span>

|<span data-ttu-id="a4b81-112">元素</span><span class="sxs-lookup"><span data-stu-id="a4b81-112">Element</span></span>|<span data-ttu-id="a4b81-113">描述</span><span class="sxs-lookup"><span data-stu-id="a4b81-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4b81-114">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="a4b81-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="a4b81-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a4b81-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a4b81-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="a4b81-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a4b81-117">用于 ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="a4b81-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="a4b81-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a4b81-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a4b81-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="a4b81-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="a4b81-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a4b81-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="a4b81-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a4b81-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a4b81-122">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="a4b81-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="a4b81-123">用于 ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="a4b81-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="a4b81-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a4b81-124">Optional element.</span></span><br /><br /> <span data-ttu-id="a4b81-125">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="a4b81-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a4b81-126">父元素</span><span class="sxs-lookup"><span data-stu-id="a4b81-126">Parent Elements</span></span>

|<span data-ttu-id="a4b81-127">元素</span><span class="sxs-lookup"><span data-stu-id="a4b81-127">Element</span></span>|<span data-ttu-id="a4b81-128">描述</span><span class="sxs-lookup"><span data-stu-id="a4b81-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4b81-129">TableRowEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a4b81-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="a4b81-130">定义使用此表项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="a4b81-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a4b81-131">备注</span><span class="sxs-lookup"><span data-stu-id="a4b81-131">Remarks</span></span>

<span data-ttu-id="a4b81-132">lWhen 正在定义选择条件，以下要求适用：</span><span class="sxs-lookup"><span data-stu-id="a4b81-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="a4b81-133">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a4b81-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="a4b81-134">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a4b81-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="a4b81-135">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a4b81-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a4b81-136">有关列表视图的其他组件的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="a4b81-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4b81-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4b81-137">See Also</span></span>

[<span data-ttu-id="a4b81-138">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="a4b81-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a4b81-139">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="a4b81-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a4b81-140">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a4b81-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="a4b81-141">ListEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="a4b81-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="a4b81-142">ListEntry (格式的 EntrySelectedBy 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="a4b81-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="a4b81-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a4b81-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
