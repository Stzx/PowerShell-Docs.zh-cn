---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)
description: PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)
ms.openlocfilehash: bda34b0c1e97fb85536132bedcec3986072801b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665696"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="4b2d6-103">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="4b2d6-103">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="4b2d6-104">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="4b2d6-105">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="4b2d6-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition 的 EntrySelectedBy) format 元素 (WideEntry) 格式 (</span><span class="sxs-lookup"><span data-stu-id="4b2d6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b2d6-107">语法</span><span class="sxs-lookup"><span data-stu-id="4b2d6-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b2d6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4b2d6-108">Attributes and Elements</span></span>

<span data-ttu-id="4b2d6-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b2d6-110">特性</span><span class="sxs-lookup"><span data-stu-id="4b2d6-110">Attributes</span></span>

<span data-ttu-id="4b2d6-111">无。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b2d6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4b2d6-112">Child Elements</span></span>

<span data-ttu-id="4b2d6-113">无。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4b2d6-114">父元素</span><span class="sxs-lookup"><span data-stu-id="4b2d6-114">Parent Elements</span></span>

|<span data-ttu-id="4b2d6-115">元素</span><span class="sxs-lookup"><span data-stu-id="4b2d6-115">Element</span></span>|<span data-ttu-id="4b2d6-116">描述</span><span class="sxs-lookup"><span data-stu-id="4b2d6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b2d6-117">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="4b2d6-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="4b2d6-118">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4b2d6-119">文本值</span><span class="sxs-lookup"><span data-stu-id="4b2d6-119">Text Value</span></span>

<span data-ttu-id="4b2d6-120">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b2d6-121">备注</span><span class="sxs-lookup"><span data-stu-id="4b2d6-121">Remarks</span></span>

<span data-ttu-id="4b2d6-122">选择条件必须指定至少一个要计算的属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="4b2d6-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4b2d6-124">有关大视图的其他组件的详细信息，请参阅 [宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d6-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b2d6-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b2d6-125">See Also</span></span>

[<span data-ttu-id="4b2d6-126">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="4b2d6-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4b2d6-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="4b2d6-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4b2d6-128">用于 WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="4b2d6-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="4b2d6-129">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="4b2d6-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="4b2d6-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4b2d6-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
