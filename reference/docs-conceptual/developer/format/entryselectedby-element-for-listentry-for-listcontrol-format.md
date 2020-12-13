---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for ListEntry for ListControl (Format)
description: EntrySelectedBy Element for ListEntry for ListControl (Format)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652293"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="8ab3a-103">EntrySelectedBy Element for ListEntry for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-103">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="8ab3a-104">定义使用此列表视图定义或要使用此定义必须存在的条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-104">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="8ab3a-105">在大多数情况下，列表视图只需要一个定义。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-105">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="8ab3a-106">但是，如果您希望使用同一列表视图为不同对象显示不同的数据，则可以为列表视图提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-106">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="8ab3a-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntry ListControl EntrySelectedBy 的 ListEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="8ab3a-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8ab3a-108">语法</span><span class="sxs-lookup"><span data-stu-id="8ab3a-108">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8ab3a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8ab3a-109">Attributes and Elements</span></span>

<span data-ttu-id="8ab3a-110">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-110">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ab3a-111">特性</span><span class="sxs-lookup"><span data-stu-id="8ab3a-111">Attributes</span></span>

<span data-ttu-id="8ab3a-112">无。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8ab3a-113">子元素</span><span class="sxs-lookup"><span data-stu-id="8ab3a-113">Child Elements</span></span>

|<span data-ttu-id="8ab3a-114">元素</span><span class="sxs-lookup"><span data-stu-id="8ab3a-114">Element</span></span>|<span data-ttu-id="8ab3a-115">描述</span><span class="sxs-lookup"><span data-stu-id="8ab3a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ab3a-116">ListControl (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="8ab3a-116">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8ab3a-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="8ab3a-118">定义要使用此列表视图定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-118">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="8ab3a-119">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-119">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8ab3a-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="8ab3a-121">指定一组使用此列表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-121">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="8ab3a-122">TypeName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-122">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8ab3a-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="8ab3a-124">指定使用此列表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-124">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8ab3a-125">父元素</span><span class="sxs-lookup"><span data-stu-id="8ab3a-125">Parent Elements</span></span>

|<span data-ttu-id="8ab3a-126">元素</span><span class="sxs-lookup"><span data-stu-id="8ab3a-126">Element</span></span>|<span data-ttu-id="8ab3a-127">描述</span><span class="sxs-lookup"><span data-stu-id="8ab3a-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ab3a-128">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="8ab3a-129">定义列表行的显示方式。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-129">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8ab3a-130">备注</span><span class="sxs-lookup"><span data-stu-id="8ab3a-130">Remarks</span></span>

<span data-ttu-id="8ab3a-131">对于列表视图定义，必须至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-131">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="8ab3a-132">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-132">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="8ab3a-133">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-133">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="8ab3a-134">有关选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-134">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8ab3a-135">有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8ab3a-136">示例</span><span class="sxs-lookup"><span data-stu-id="8ab3a-136">Example</span></span>

<span data-ttu-id="8ab3a-137">下面的示例演示如何使用 .NET 类型名称定义列表视图的对象。</span><span class="sxs-lookup"><span data-stu-id="8ab3a-137">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="8ab3a-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab3a-138">See Also</span></span>

[<span data-ttu-id="8ab3a-139">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-139">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="8ab3a-140">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-140">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8ab3a-141">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-141">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8ab3a-142">TypeName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8ab3a-142">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8ab3a-143">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="8ab3a-143">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8ab3a-144">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="8ab3a-144">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8ab3a-145">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8ab3a-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
