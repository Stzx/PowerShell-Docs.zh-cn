---
title: ListControl (Format) 的 SelectionCondition for EntrySelectedBy 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3f0a6b6b381f39492da36dab271503fc7cf6e7fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785551"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="d4c9d-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d4c9d-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="d4c9d-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="d4c9d-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用列表项。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="d4c9d-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry 元素 (SelectionCondition 的 EntrySelectedBy) format 元素 (ListEntry) 格式 (</span><span class="sxs-lookup"><span data-stu-id="d4c9d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d4c9d-106">语法</span><span class="sxs-lookup"><span data-stu-id="d4c9d-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4c9d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4c9d-107">Attributes and Elements</span></span>

<span data-ttu-id="d4c9d-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4c9d-109">特性</span><span class="sxs-lookup"><span data-stu-id="d4c9d-109">Attributes</span></span>

<span data-ttu-id="d4c9d-110">无。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4c9d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="d4c9d-111">Child Elements</span></span>

<span data-ttu-id="d4c9d-112">无。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d4c9d-113">父元素</span><span class="sxs-lookup"><span data-stu-id="d4c9d-113">Parent Elements</span></span>

|<span data-ttu-id="d4c9d-114">元素</span><span class="sxs-lookup"><span data-stu-id="d4c9d-114">Element</span></span>|<span data-ttu-id="d4c9d-115">说明</span><span class="sxs-lookup"><span data-stu-id="d4c9d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4c9d-116">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="d4c9d-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d4c9d-117">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d4c9d-118">文本值</span><span class="sxs-lookup"><span data-stu-id="d4c9d-118">Text Value</span></span>

<span data-ttu-id="d4c9d-119">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4c9d-120">备注</span><span class="sxs-lookup"><span data-stu-id="d4c9d-120">Remarks</span></span>

<span data-ttu-id="d4c9d-121">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="d4c9d-122">有关如何使用选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d4c9d-123">有关列表视图的其他组件的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c9d-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c9d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c9d-124">See Also</span></span>

[<span data-ttu-id="d4c9d-125">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="d4c9d-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d4c9d-126">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="d4c9d-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d4c9d-127">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d4c9d-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="d4c9d-128">用于 ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="d4c9d-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d4c9d-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d4c9d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
