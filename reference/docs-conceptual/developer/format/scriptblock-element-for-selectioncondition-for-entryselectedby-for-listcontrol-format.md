---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)
description: ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659898"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="fe968-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fe968-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="fe968-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="fe968-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="fe968-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。</span><span class="sxs-lookup"><span data-stu-id="fe968-105">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="fe968-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 ListEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="fe968-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fe968-107">语法</span><span class="sxs-lookup"><span data-stu-id="fe968-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe968-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fe968-108">Attributes and Elements</span></span>

<span data-ttu-id="fe968-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="fe968-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe968-110">特性</span><span class="sxs-lookup"><span data-stu-id="fe968-110">Attributes</span></span>

<span data-ttu-id="fe968-111">无。</span><span class="sxs-lookup"><span data-stu-id="fe968-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe968-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fe968-112">Child Elements</span></span>

<span data-ttu-id="fe968-113">无。</span><span class="sxs-lookup"><span data-stu-id="fe968-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fe968-114">父元素</span><span class="sxs-lookup"><span data-stu-id="fe968-114">Parent Elements</span></span>

|<span data-ttu-id="fe968-115">元素</span><span class="sxs-lookup"><span data-stu-id="fe968-115">Element</span></span>|<span data-ttu-id="fe968-116">描述</span><span class="sxs-lookup"><span data-stu-id="fe968-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe968-117">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="fe968-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="fe968-118">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="fe968-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fe968-119">文本值</span><span class="sxs-lookup"><span data-stu-id="fe968-119">Text Value</span></span>

<span data-ttu-id="fe968-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="fe968-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe968-121">备注</span><span class="sxs-lookup"><span data-stu-id="fe968-121">Remarks</span></span>

<span data-ttu-id="fe968-122">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="fe968-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="fe968-123"> (有关如何使用选择条件的详细信息，请参阅为 [使用视图条目或项定义条件](./defining-conditions-for-displaying-data.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="fe968-123">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="fe968-124">有关列表视图的其他组件的详细信息，请参阅 [列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="fe968-124">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe968-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe968-125">See Also</span></span>

[<span data-ttu-id="fe968-126">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="fe968-126">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="fe968-127">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="fe968-127">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="fe968-128">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="fe968-128">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="fe968-129">列表视图</span><span class="sxs-lookup"><span data-stu-id="fe968-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="fe968-130">定义使用视图条目或项的条件</span><span class="sxs-lookup"><span data-stu-id="fe968-130">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="fe968-131">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="fe968-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
