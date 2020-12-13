---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for CustomControl for View (Format)
description: ScriptBlock Element for SelectionCondition for CustomControl for View (Format)
ms.openlocfilehash: 78b977548243b6f3a658f15a0249d8cad12e2f1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664917"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="3ea09-103">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3ea09-103">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="3ea09-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="3ea09-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="3ea09-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="3ea09-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="3ea09-106">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="3ea09-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="3ea09-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) CustomControl 元素 for view (Format) CustomEntries 元素 for CustomControl for CustomEntry for CustomEntries for for CustomControl for CustomItem for CustomEntry for CustomControl for SelectionCondition for EntrySelectedBy for CustomControl SelectionCondition for view (format) CustomControl 元素（for 的元素 (</span><span class="sxs-lookup"><span data-stu-id="3ea09-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3ea09-108">语法</span><span class="sxs-lookup"><span data-stu-id="3ea09-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3ea09-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3ea09-109">Attributes and Elements</span></span>

<span data-ttu-id="3ea09-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="3ea09-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3ea09-111">特性</span><span class="sxs-lookup"><span data-stu-id="3ea09-111">Attributes</span></span>

<span data-ttu-id="3ea09-112">无。</span><span class="sxs-lookup"><span data-stu-id="3ea09-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3ea09-113">子元素</span><span class="sxs-lookup"><span data-stu-id="3ea09-113">Child Elements</span></span>

<span data-ttu-id="3ea09-114">无。</span><span class="sxs-lookup"><span data-stu-id="3ea09-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3ea09-115">父元素</span><span class="sxs-lookup"><span data-stu-id="3ea09-115">Parent Elements</span></span>

|<span data-ttu-id="3ea09-116">元素</span><span class="sxs-lookup"><span data-stu-id="3ea09-116">Element</span></span>|<span data-ttu-id="3ea09-117">描述</span><span class="sxs-lookup"><span data-stu-id="3ea09-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3ea09-118">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 </span><span class="sxs-lookup"><span data-stu-id="3ea09-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="3ea09-119">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="3ea09-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3ea09-120">文本值</span><span class="sxs-lookup"><span data-stu-id="3ea09-120">Text Value</span></span>

<span data-ttu-id="3ea09-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="3ea09-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ea09-122">备注</span><span class="sxs-lookup"><span data-stu-id="3ea09-122">Remarks</span></span>

<span data-ttu-id="3ea09-123">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="3ea09-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="3ea09-124">有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="3ea09-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ea09-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ea09-125">See Also</span></span>

[<span data-ttu-id="3ea09-126">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 </span><span class="sxs-lookup"><span data-stu-id="3ea09-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="3ea09-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3ea09-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
