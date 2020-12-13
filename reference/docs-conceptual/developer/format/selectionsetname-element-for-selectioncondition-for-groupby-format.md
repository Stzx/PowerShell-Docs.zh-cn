---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for GroupBy (Format)
description: SelectionSetName Element for SelectionCondition for GroupBy (Format)
ms.openlocfilehash: a4f28c1caba3790718b99f63659cb0cbed8def16
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654994"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="9073f-103">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9073f-103">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="9073f-104">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="9073f-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="9073f-105">如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。</span><span class="sxs-lookup"><span data-stu-id="9073f-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="9073f-106">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="9073f-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9073f-107">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="9073f-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9073f-108">语法</span><span class="sxs-lookup"><span data-stu-id="9073f-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9073f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9073f-109">Attributes and Elements</span></span>

<span data-ttu-id="9073f-110">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="9073f-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9073f-111">特性</span><span class="sxs-lookup"><span data-stu-id="9073f-111">Attributes</span></span>

<span data-ttu-id="9073f-112">无。</span><span class="sxs-lookup"><span data-stu-id="9073f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9073f-113">子元素</span><span class="sxs-lookup"><span data-stu-id="9073f-113">Child Elements</span></span>

<span data-ttu-id="9073f-114">无。</span><span class="sxs-lookup"><span data-stu-id="9073f-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9073f-115">父元素</span><span class="sxs-lookup"><span data-stu-id="9073f-115">Parent Elements</span></span>

|<span data-ttu-id="9073f-116">元素</span><span class="sxs-lookup"><span data-stu-id="9073f-116">Element</span></span>|<span data-ttu-id="9073f-117">描述</span><span class="sxs-lookup"><span data-stu-id="9073f-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9073f-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9073f-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="9073f-119">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="9073f-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9073f-120">文本值</span><span class="sxs-lookup"><span data-stu-id="9073f-120">Text Value</span></span>

<span data-ttu-id="9073f-121">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="9073f-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="9073f-122">备注</span><span class="sxs-lookup"><span data-stu-id="9073f-122">Remarks</span></span>

<span data-ttu-id="9073f-123">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="9073f-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="9073f-124">有关创建和引用选项集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="9073f-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="9073f-125">如果指定此元素，则不能指定 [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="9073f-125">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="9073f-126">有关定义选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="9073f-126">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9073f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9073f-127">See Also</span></span>

[<span data-ttu-id="9073f-128">TypeName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9073f-128">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="9073f-129">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9073f-129">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="9073f-130">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="9073f-130">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9073f-131">定义选项集</span><span class="sxs-lookup"><span data-stu-id="9073f-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="9073f-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9073f-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
