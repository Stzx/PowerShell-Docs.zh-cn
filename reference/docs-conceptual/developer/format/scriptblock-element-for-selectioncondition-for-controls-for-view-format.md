---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for Controls for View (Format)
description: ScriptBlock Element for SelectionCondition for Controls for View (Format)
ms.openlocfilehash: 7eed3b8a06bc45396026b8e2a7454447b3090d74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664943"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="82d63-103">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d63-103">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="82d63-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="82d63-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="82d63-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="82d63-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="82d63-106">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="82d63-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="82d63-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomEntries 元素 (Format) 的 CustomEntries 的 CustomEntry 元素，用于视图 (格式) EntrySelectedBy 元素 for CustomEntry for view (格式的控件) SelectionCondition 的控件的控件 (EntrySelectedBy 的控件) 的 ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="82d63-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82d63-108">语法</span><span class="sxs-lookup"><span data-stu-id="82d63-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82d63-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="82d63-109">Attributes and Elements</span></span>

<span data-ttu-id="82d63-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="82d63-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82d63-111">特性</span><span class="sxs-lookup"><span data-stu-id="82d63-111">Attributes</span></span>

<span data-ttu-id="82d63-112">无。</span><span class="sxs-lookup"><span data-stu-id="82d63-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82d63-113">子元素</span><span class="sxs-lookup"><span data-stu-id="82d63-113">Child Elements</span></span>

<span data-ttu-id="82d63-114">无。</span><span class="sxs-lookup"><span data-stu-id="82d63-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="82d63-115">父元素</span><span class="sxs-lookup"><span data-stu-id="82d63-115">Parent Elements</span></span>

|<span data-ttu-id="82d63-116">元素</span><span class="sxs-lookup"><span data-stu-id="82d63-116">Element</span></span>|<span data-ttu-id="82d63-117">描述</span><span class="sxs-lookup"><span data-stu-id="82d63-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82d63-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d63-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="82d63-119">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="82d63-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="82d63-120">文本值</span><span class="sxs-lookup"><span data-stu-id="82d63-120">Text Value</span></span>

<span data-ttu-id="82d63-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="82d63-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="82d63-122">备注</span><span class="sxs-lookup"><span data-stu-id="82d63-122">Remarks</span></span>

<span data-ttu-id="82d63-123">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="82d63-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="82d63-124">有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="82d63-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82d63-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82d63-125">See Also</span></span>

[<span data-ttu-id="82d63-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d63-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="82d63-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="82d63-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
