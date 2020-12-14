---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)
description: PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)
ms.openlocfilehash: 1e318e3a29f07b157b9ae7343ba08759db8efbb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665815"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="8c93f-103">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8c93f-103">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="8c93f-104">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="8c93f-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8c93f-105">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用列表项。</span><span class="sxs-lookup"><span data-stu-id="8c93f-105">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="8c93f-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry 元素 (SelectionCondition 的 EntrySelectedBy) format 元素 (ListEntry) 格式 (</span><span class="sxs-lookup"><span data-stu-id="8c93f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c93f-107">语法</span><span class="sxs-lookup"><span data-stu-id="8c93f-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c93f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8c93f-108">Attributes and Elements</span></span>

<span data-ttu-id="8c93f-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="8c93f-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c93f-110">特性</span><span class="sxs-lookup"><span data-stu-id="8c93f-110">Attributes</span></span>

<span data-ttu-id="8c93f-111">无。</span><span class="sxs-lookup"><span data-stu-id="8c93f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c93f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="8c93f-112">Child Elements</span></span>

<span data-ttu-id="8c93f-113">无。</span><span class="sxs-lookup"><span data-stu-id="8c93f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8c93f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="8c93f-114">Parent Elements</span></span>

|<span data-ttu-id="8c93f-115">元素</span><span class="sxs-lookup"><span data-stu-id="8c93f-115">Element</span></span>|<span data-ttu-id="8c93f-116">描述</span><span class="sxs-lookup"><span data-stu-id="8c93f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c93f-117">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="8c93f-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8c93f-118">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="8c93f-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8c93f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="8c93f-119">Text Value</span></span>

<span data-ttu-id="8c93f-120">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="8c93f-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c93f-121">备注</span><span class="sxs-lookup"><span data-stu-id="8c93f-121">Remarks</span></span>

<span data-ttu-id="8c93f-122">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="8c93f-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="8c93f-123">有关如何使用选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8c93f-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8c93f-124">有关列表视图的其他组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="8c93f-124">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c93f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c93f-125">See Also</span></span>

[<span data-ttu-id="8c93f-126">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="8c93f-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8c93f-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="8c93f-127">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8c93f-128">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="8c93f-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="8c93f-129">用于 ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="8c93f-129">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8c93f-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8c93f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
