---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)
description: ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651960"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="5b16f-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5b16f-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="5b16f-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="5b16f-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="5b16f-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用宽输入定义。</span><span class="sxs-lookup"><span data-stu-id="5b16f-105">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="5b16f-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 WideEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="5b16f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5b16f-107">语法</span><span class="sxs-lookup"><span data-stu-id="5b16f-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5b16f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5b16f-108">Attributes and Elements</span></span>

<span data-ttu-id="5b16f-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="5b16f-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5b16f-110">特性</span><span class="sxs-lookup"><span data-stu-id="5b16f-110">Attributes</span></span>

<span data-ttu-id="5b16f-111">无。</span><span class="sxs-lookup"><span data-stu-id="5b16f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5b16f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5b16f-112">Child Elements</span></span>

<span data-ttu-id="5b16f-113">无。</span><span class="sxs-lookup"><span data-stu-id="5b16f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5b16f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="5b16f-114">Parent Elements</span></span>

|<span data-ttu-id="5b16f-115">元素</span><span class="sxs-lookup"><span data-stu-id="5b16f-115">Element</span></span>|<span data-ttu-id="5b16f-116">描述</span><span class="sxs-lookup"><span data-stu-id="5b16f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5b16f-117">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="5b16f-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="5b16f-118">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="5b16f-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5b16f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="5b16f-119">Text Value</span></span>

<span data-ttu-id="5b16f-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="5b16f-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b16f-121">备注</span><span class="sxs-lookup"><span data-stu-id="5b16f-121">Remarks</span></span>

<span data-ttu-id="5b16f-122">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="5b16f-122">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="5b16f-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="5b16f-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="5b16f-124">有关大视图的其他组件的详细信息，请参阅 [宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="5b16f-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b16f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b16f-125">See Also</span></span>

[<span data-ttu-id="5b16f-126">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="5b16f-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5b16f-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="5b16f-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5b16f-128">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="5b16f-128">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="5b16f-129">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="5b16f-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="5b16f-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="5b16f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
