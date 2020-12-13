---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for ListControl (Format)
description: SelectionSetName Element for EntrySelectedBy for ListControl (Format)
ms.openlocfilehash: 413a77f7ba06fe952e574061e58d0b5d80c5b3c4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651825"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="30ca6-103">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="30ca6-103">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="30ca6-104">为列表条目指定一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="30ca6-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="30ca6-105">对于可为条目指定的选项集数没有限制。</span><span class="sxs-lookup"><span data-stu-id="30ca6-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="30ca6-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy (格式) ListEntry 元素 (SelectionSetName) 格式</span><span class="sxs-lookup"><span data-stu-id="30ca6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30ca6-107">语法</span><span class="sxs-lookup"><span data-stu-id="30ca6-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30ca6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="30ca6-108">Attributes and Elements</span></span>

<span data-ttu-id="30ca6-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="30ca6-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="30ca6-110">特性</span><span class="sxs-lookup"><span data-stu-id="30ca6-110">Attributes</span></span>

<span data-ttu-id="30ca6-111">无。</span><span class="sxs-lookup"><span data-stu-id="30ca6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30ca6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="30ca6-112">Child Elements</span></span>

<span data-ttu-id="30ca6-113">无。</span><span class="sxs-lookup"><span data-stu-id="30ca6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="30ca6-114">父元素</span><span class="sxs-lookup"><span data-stu-id="30ca6-114">Parent Elements</span></span>

|<span data-ttu-id="30ca6-115">元素</span><span class="sxs-lookup"><span data-stu-id="30ca6-115">Element</span></span>|<span data-ttu-id="30ca6-116">描述</span><span class="sxs-lookup"><span data-stu-id="30ca6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30ca6-117">ListEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="30ca6-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="30ca6-118">定义使用此列表项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="30ca6-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="30ca6-119">文本值</span><span class="sxs-lookup"><span data-stu-id="30ca6-119">Text Value</span></span>

<span data-ttu-id="30ca6-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="30ca6-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="30ca6-121">备注</span><span class="sxs-lookup"><span data-stu-id="30ca6-121">Remarks</span></span>

<span data-ttu-id="30ca6-122">每个列表项必须至少定义一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="30ca6-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="30ca6-123">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="30ca6-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="30ca6-124">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="30ca6-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="30ca6-125">有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="30ca6-125">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="30ca6-126">有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="30ca6-126">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="30ca6-127">示例</span><span class="sxs-lookup"><span data-stu-id="30ca6-127">Example</span></span>

<span data-ttu-id="30ca6-128">下面的示例演示如何为列表视图的条目指定选择集。</span><span class="sxs-lookup"><span data-stu-id="30ca6-128">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="30ca6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30ca6-129">See Also</span></span>

[<span data-ttu-id="30ca6-130">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="30ca6-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="30ca6-131">ListEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="30ca6-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="30ca6-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="30ca6-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
