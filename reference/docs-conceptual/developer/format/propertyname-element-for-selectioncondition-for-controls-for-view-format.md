---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for SelectionCondition for Controls for View (Format)
description: PropertyName Element for SelectionCondition for Controls for View (Format)
ms.openlocfilehash: 7783e5a9b7f8ec3d3077d87778e9f77ffe858a7f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665866"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="82d14-103">PropertyName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d14-103">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="82d14-104">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="82d14-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="82d14-105">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用该条目。</span><span class="sxs-lookup"><span data-stu-id="82d14-105">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="82d14-106">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="82d14-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="82d14-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomEntries 元素 (Format) 用于视图 (格式的控件的 CustomEntries 的 CustomEntry 元素) EntrySelectedBy 元素 for CustomEntry for view (格式的控件) SelectionCondition 的控件 (EntrySelectedBy 的控件) </span><span class="sxs-lookup"><span data-stu-id="82d14-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82d14-108">语法</span><span class="sxs-lookup"><span data-stu-id="82d14-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82d14-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="82d14-109">Attributes and Elements</span></span>

<span data-ttu-id="82d14-110">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="82d14-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82d14-111">特性</span><span class="sxs-lookup"><span data-stu-id="82d14-111">Attributes</span></span>

<span data-ttu-id="82d14-112">无。</span><span class="sxs-lookup"><span data-stu-id="82d14-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82d14-113">子元素</span><span class="sxs-lookup"><span data-stu-id="82d14-113">Child Elements</span></span>

<span data-ttu-id="82d14-114">无。</span><span class="sxs-lookup"><span data-stu-id="82d14-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="82d14-115">父元素</span><span class="sxs-lookup"><span data-stu-id="82d14-115">Parent Elements</span></span>

|<span data-ttu-id="82d14-116">元素</span><span class="sxs-lookup"><span data-stu-id="82d14-116">Element</span></span>|<span data-ttu-id="82d14-117">描述</span><span class="sxs-lookup"><span data-stu-id="82d14-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82d14-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d14-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="82d14-119">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="82d14-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="82d14-120">文本值</span><span class="sxs-lookup"><span data-stu-id="82d14-120">Text Value</span></span>

<span data-ttu-id="82d14-121">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="82d14-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="82d14-122">备注</span><span class="sxs-lookup"><span data-stu-id="82d14-122">Remarks</span></span>

<span data-ttu-id="82d14-123">选择条件必须指定至少一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="82d14-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="82d14-124">有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="82d14-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82d14-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82d14-125">See Also</span></span>

[<span data-ttu-id="82d14-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d14-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="82d14-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="82d14-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
