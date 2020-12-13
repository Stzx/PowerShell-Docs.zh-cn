---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
description: SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 0c9372113a79f75cfbda67acf869164fde894ee3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651587"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="2b39f-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="2b39f-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="2b39f-104">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="2b39f-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="2b39f-105">如果此集中的任何类型存在，则满足条件。</span><span class="sxs-lookup"><span data-stu-id="2b39f-105">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="2b39f-106">配置元素 DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy) EnumerableExpansion 的 SelectionSetName 元素 (SelectionCondition 的 EntrySelectedBy) 格式 (</span><span class="sxs-lookup"><span data-stu-id="2b39f-106">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b39f-107">语法</span><span class="sxs-lookup"><span data-stu-id="2b39f-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b39f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b39f-108">Attributes and Elements</span></span>

<span data-ttu-id="2b39f-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="2b39f-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b39f-110">特性</span><span class="sxs-lookup"><span data-stu-id="2b39f-110">Attributes</span></span>

<span data-ttu-id="2b39f-111">无。</span><span class="sxs-lookup"><span data-stu-id="2b39f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b39f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2b39f-112">Child Elements</span></span>

<span data-ttu-id="2b39f-113">无。</span><span class="sxs-lookup"><span data-stu-id="2b39f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b39f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="2b39f-114">Parent Elements</span></span>

|<span data-ttu-id="2b39f-115">元素</span><span class="sxs-lookup"><span data-stu-id="2b39f-115">Element</span></span>|<span data-ttu-id="2b39f-116">描述</span><span class="sxs-lookup"><span data-stu-id="2b39f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b39f-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="2b39f-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2b39f-118">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="2b39f-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b39f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="2b39f-119">Text Value</span></span>

<span data-ttu-id="2b39f-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="2b39f-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b39f-121">备注</span><span class="sxs-lookup"><span data-stu-id="2b39f-121">Remarks</span></span>

<span data-ttu-id="2b39f-122">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="2b39f-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="2b39f-123">有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2b39f-123">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2b39f-124">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="2b39f-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="2b39f-125">有关创建和引用选项集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="2b39f-125">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b39f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b39f-126">See Also</span></span>

[<span data-ttu-id="2b39f-127">定义选项集</span><span class="sxs-lookup"><span data-stu-id="2b39f-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2b39f-128">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="2b39f-128">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="2b39f-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="2b39f-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
