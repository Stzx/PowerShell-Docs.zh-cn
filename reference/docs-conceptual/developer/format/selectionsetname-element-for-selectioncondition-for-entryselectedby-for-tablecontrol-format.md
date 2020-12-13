---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)
description: SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: 2fb09e27eef1ce5d6e864c72edb595817d91f729
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655041"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="64a6f-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="64a6f-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="64a6f-104">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="64a6f-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="64a6f-105">如果此集中的任何类型存在，则满足条件，并使用表视图的这一定义显示该对象。</span><span class="sxs-lookup"><span data-stu-id="64a6f-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="64a6f-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 的 TableRowEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 元素，TableRowEntry 的 SelectionSetName) 格式 (</span><span class="sxs-lookup"><span data-stu-id="64a6f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="64a6f-107">语法</span><span class="sxs-lookup"><span data-stu-id="64a6f-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64a6f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="64a6f-108">Attributes and Elements</span></span>

<span data-ttu-id="64a6f-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="64a6f-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="64a6f-110">特性</span><span class="sxs-lookup"><span data-stu-id="64a6f-110">Attributes</span></span>

<span data-ttu-id="64a6f-111">无。</span><span class="sxs-lookup"><span data-stu-id="64a6f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="64a6f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="64a6f-112">Child Elements</span></span>

<span data-ttu-id="64a6f-113">无。</span><span class="sxs-lookup"><span data-stu-id="64a6f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="64a6f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="64a6f-114">Parent Elements</span></span>

|<span data-ttu-id="64a6f-115">元素</span><span class="sxs-lookup"><span data-stu-id="64a6f-115">Element</span></span>|<span data-ttu-id="64a6f-116">描述</span><span class="sxs-lookup"><span data-stu-id="64a6f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64a6f-117">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="64a6f-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="64a6f-118">定义必须存在才能用于此表视图定义的条件。</span><span class="sxs-lookup"><span data-stu-id="64a6f-118">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="64a6f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="64a6f-119">Text Value</span></span>

<span data-ttu-id="64a6f-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="64a6f-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="64a6f-121">备注</span><span class="sxs-lookup"><span data-stu-id="64a6f-121">Remarks</span></span>

<span data-ttu-id="64a6f-122">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="64a6f-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="64a6f-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="64a6f-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="64a6f-124">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="64a6f-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="64a6f-125">有关创建和引用选项集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="64a6f-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="64a6f-126">有关大视图的其他组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="64a6f-126">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="64a6f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64a6f-127">See Also</span></span>

[<span data-ttu-id="64a6f-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="64a6f-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="64a6f-129">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="64a6f-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="64a6f-130">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="64a6f-130">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="64a6f-131">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="64a6f-131">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="64a6f-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="64a6f-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
