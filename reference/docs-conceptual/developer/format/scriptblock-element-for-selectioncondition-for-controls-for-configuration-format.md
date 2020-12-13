---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)
description: ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)
ms.openlocfilehash: 42e9d2b00f7690e46242b2c4602245e4bf391bbf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664952"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="f4ffd-103">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f4ffd-103">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f4ffd-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f4ffd-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="f4ffd-106">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f4ffd-107">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素的的 CustomEntry 元素 CustomControl for control for control (Format) EntrySelectedBy 元素 for CustomEntry for control (Format for for control Format) SelectionCondition 元素 for EntrySelectedBy for control (format) </span><span class="sxs-lookup"><span data-stu-id="f4ffd-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4ffd-108">语法</span><span class="sxs-lookup"><span data-stu-id="f4ffd-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4ffd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f4ffd-109">Attributes and Elements</span></span>

<span data-ttu-id="f4ffd-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4ffd-111">特性</span><span class="sxs-lookup"><span data-stu-id="f4ffd-111">Attributes</span></span>

<span data-ttu-id="f4ffd-112">无。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4ffd-113">子元素</span><span class="sxs-lookup"><span data-stu-id="f4ffd-113">Child Elements</span></span>

<span data-ttu-id="f4ffd-114">无。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4ffd-115">父元素</span><span class="sxs-lookup"><span data-stu-id="f4ffd-115">Parent Elements</span></span>

|<span data-ttu-id="f4ffd-116">元素</span><span class="sxs-lookup"><span data-stu-id="f4ffd-116">Element</span></span>|<span data-ttu-id="f4ffd-117">描述</span><span class="sxs-lookup"><span data-stu-id="f4ffd-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4ffd-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f4ffd-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="f4ffd-119">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-119">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4ffd-120">文本值</span><span class="sxs-lookup"><span data-stu-id="f4ffd-120">Text Value</span></span>

<span data-ttu-id="f4ffd-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4ffd-122">备注</span><span class="sxs-lookup"><span data-stu-id="f4ffd-122">Remarks</span></span>

<span data-ttu-id="f4ffd-123">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f4ffd-124">有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4ffd-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4ffd-125">See Also</span></span>

[<span data-ttu-id="f4ffd-126">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f4ffd-126">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="f4ffd-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f4ffd-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
