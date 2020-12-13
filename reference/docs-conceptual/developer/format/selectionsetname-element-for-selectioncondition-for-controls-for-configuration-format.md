---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)
description: SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)
ms.openlocfilehash: 4177aace5a6a9374900e7339167c69b531c1e2e7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651658"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="158b4-103">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="158b4-103">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="158b4-104">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="158b4-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="158b4-105">如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。</span><span class="sxs-lookup"><span data-stu-id="158b4-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="158b4-106">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="158b4-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="158b4-107">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 的控件 (CustomEntries 元素) CustomEntry 元素对于 CustomControl for control for control (format) EntrySelectedBy 元素 For CustomEntry For For control (format For For For control for For SelectionCondition EntrySelectedBy for control for control (SelectionSetName) ) </span><span class="sxs-lookup"><span data-stu-id="158b4-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="158b4-108">语法</span><span class="sxs-lookup"><span data-stu-id="158b4-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="158b4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="158b4-109">Attributes and Elements</span></span>

<span data-ttu-id="158b4-110">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="158b4-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="158b4-111">特性</span><span class="sxs-lookup"><span data-stu-id="158b4-111">Attributes</span></span>

<span data-ttu-id="158b4-112">无。</span><span class="sxs-lookup"><span data-stu-id="158b4-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="158b4-113">子元素</span><span class="sxs-lookup"><span data-stu-id="158b4-113">Child Elements</span></span>

<span data-ttu-id="158b4-114">无。</span><span class="sxs-lookup"><span data-stu-id="158b4-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="158b4-115">父元素</span><span class="sxs-lookup"><span data-stu-id="158b4-115">Parent Elements</span></span>

|<span data-ttu-id="158b4-116">元素</span><span class="sxs-lookup"><span data-stu-id="158b4-116">Element</span></span>|<span data-ttu-id="158b4-117">描述</span><span class="sxs-lookup"><span data-stu-id="158b4-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="158b4-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="158b4-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="158b4-119">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="158b4-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="158b4-120">文本值</span><span class="sxs-lookup"><span data-stu-id="158b4-120">Text Value</span></span>

<span data-ttu-id="158b4-121">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="158b4-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="158b4-122">备注</span><span class="sxs-lookup"><span data-stu-id="158b4-122">Remarks</span></span>

<span data-ttu-id="158b4-123">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="158b4-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="158b4-124">有关创建和引用选项集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="158b4-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="158b4-125">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="158b4-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="158b4-126">有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="158b4-126">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="158b4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="158b4-127">See Also</span></span>

[<span data-ttu-id="158b4-128">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="158b4-128">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="158b4-129">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="158b4-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="158b4-130">定义选项集</span><span class="sxs-lookup"><span data-stu-id="158b4-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="158b4-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="158b4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
