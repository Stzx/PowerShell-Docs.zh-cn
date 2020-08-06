---
title: 用于 ListControl (Format) 的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 56bd04c9af74bdaa7a186a208fc15a67cb08b004
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772852"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="6b120-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6b120-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="6b120-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="6b120-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="6b120-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。</span><span class="sxs-lookup"><span data-stu-id="6b120-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="6b120-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 ListEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="6b120-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6b120-106">语法</span><span class="sxs-lookup"><span data-stu-id="6b120-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b120-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6b120-107">Attributes and Elements</span></span>

<span data-ttu-id="6b120-108">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="6b120-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b120-109">特性</span><span class="sxs-lookup"><span data-stu-id="6b120-109">Attributes</span></span>

<span data-ttu-id="6b120-110">无。</span><span class="sxs-lookup"><span data-stu-id="6b120-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6b120-111">子元素</span><span class="sxs-lookup"><span data-stu-id="6b120-111">Child Elements</span></span>

<span data-ttu-id="6b120-112">无。</span><span class="sxs-lookup"><span data-stu-id="6b120-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b120-113">父元素</span><span class="sxs-lookup"><span data-stu-id="6b120-113">Parent Elements</span></span>

|<span data-ttu-id="6b120-114">元素</span><span class="sxs-lookup"><span data-stu-id="6b120-114">Element</span></span>|<span data-ttu-id="6b120-115">说明</span><span class="sxs-lookup"><span data-stu-id="6b120-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6b120-116">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="6b120-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="6b120-117">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="6b120-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6b120-118">文本值</span><span class="sxs-lookup"><span data-stu-id="6b120-118">Text Value</span></span>

<span data-ttu-id="6b120-119">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="6b120-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b120-120">备注</span><span class="sxs-lookup"><span data-stu-id="6b120-120">Remarks</span></span>

<span data-ttu-id="6b120-121">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="6b120-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="6b120-122"> (有关如何使用选择条件的详细信息，请参阅为[使用视图条目或项定义条件](./defining-conditions-for-displaying-data.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="6b120-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="6b120-123">有关列表视图的其他组件的详细信息，请参阅[列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="6b120-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b120-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b120-124">See Also</span></span>

[<span data-ttu-id="6b120-125">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="6b120-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="6b120-126">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="6b120-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="6b120-127">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="6b120-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="6b120-128">列表视图</span><span class="sxs-lookup"><span data-stu-id="6b120-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6b120-129">定义使用视图条目或项的条件</span><span class="sxs-lookup"><span data-stu-id="6b120-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="6b120-130">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="6b120-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
