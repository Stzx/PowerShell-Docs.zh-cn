---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)
description: SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)
ms.openlocfilehash: c6466e3ac6e1f194df9172468d26448f9630da6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655005"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="065f4-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="065f4-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="065f4-104">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="065f4-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="065f4-105">如果此集中的任何类型存在，则满足条件，并使用此大视图的定义显示该对象。</span><span class="sxs-lookup"><span data-stu-id="065f4-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="065f4-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 元素，WideEntry 的 SelectionSetName) 格式 (</span><span class="sxs-lookup"><span data-stu-id="065f4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="065f4-107">语法</span><span class="sxs-lookup"><span data-stu-id="065f4-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="065f4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="065f4-108">Attributes and Elements</span></span>

<span data-ttu-id="065f4-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="065f4-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="065f4-110">特性</span><span class="sxs-lookup"><span data-stu-id="065f4-110">Attributes</span></span>

<span data-ttu-id="065f4-111">无。</span><span class="sxs-lookup"><span data-stu-id="065f4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="065f4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="065f4-112">Child Elements</span></span>

<span data-ttu-id="065f4-113">无。</span><span class="sxs-lookup"><span data-stu-id="065f4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="065f4-114">父元素</span><span class="sxs-lookup"><span data-stu-id="065f4-114">Parent Elements</span></span>

|<span data-ttu-id="065f4-115">元素</span><span class="sxs-lookup"><span data-stu-id="065f4-115">Element</span></span>|<span data-ttu-id="065f4-116">描述</span><span class="sxs-lookup"><span data-stu-id="065f4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="065f4-117">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="065f4-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="065f4-118">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="065f4-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="065f4-119">文本值</span><span class="sxs-lookup"><span data-stu-id="065f4-119">Text Value</span></span>

<span data-ttu-id="065f4-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="065f4-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="065f4-121">备注</span><span class="sxs-lookup"><span data-stu-id="065f4-121">Remarks</span></span>

<span data-ttu-id="065f4-122">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="065f4-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="065f4-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="065f4-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="065f4-124">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="065f4-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="065f4-125">有关创建和引用选项集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="065f4-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="065f4-126">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="065f4-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="065f4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="065f4-127">See Also</span></span>

[<span data-ttu-id="065f4-128">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="065f4-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="065f4-129">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="065f4-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="065f4-130">定义选项集</span><span class="sxs-lookup"><span data-stu-id="065f4-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="065f4-131">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="065f4-131">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="065f4-132">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="065f4-132">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="065f4-133">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="065f4-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
