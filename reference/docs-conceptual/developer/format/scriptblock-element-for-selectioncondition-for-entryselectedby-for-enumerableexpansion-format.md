---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
description: ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: bd72a9bc914ea6543d8dab768b5e20e9a580ada7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664908"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="9d69e-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9d69e-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="9d69e-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="9d69e-104">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="9d69e-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy) 格式 (EnumerableExpansion 的 ScriptBlock 元素) SelectionCondition (格式) </span><span class="sxs-lookup"><span data-stu-id="9d69e-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d69e-106">语法</span><span class="sxs-lookup"><span data-stu-id="9d69e-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d69e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9d69e-107">Attributes and Elements</span></span>

<span data-ttu-id="9d69e-108">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="9d69e-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d69e-109">特性</span><span class="sxs-lookup"><span data-stu-id="9d69e-109">Attributes</span></span>

<span data-ttu-id="9d69e-110">无。</span><span class="sxs-lookup"><span data-stu-id="9d69e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d69e-111">子元素</span><span class="sxs-lookup"><span data-stu-id="9d69e-111">Child Elements</span></span>

<span data-ttu-id="9d69e-112">无。</span><span class="sxs-lookup"><span data-stu-id="9d69e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d69e-113">父元素</span><span class="sxs-lookup"><span data-stu-id="9d69e-113">Parent Elements</span></span>

|<span data-ttu-id="9d69e-114">元素</span><span class="sxs-lookup"><span data-stu-id="9d69e-114">Element</span></span>|<span data-ttu-id="9d69e-115">描述</span><span class="sxs-lookup"><span data-stu-id="9d69e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d69e-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9d69e-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9d69e-117">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="9d69e-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9d69e-118">文本值</span><span class="sxs-lookup"><span data-stu-id="9d69e-118">Text Value</span></span>

<span data-ttu-id="9d69e-119">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="9d69e-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d69e-120">备注</span><span class="sxs-lookup"><span data-stu-id="9d69e-120">Remarks</span></span>

<span data-ttu-id="9d69e-121">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="9d69e-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="9d69e-122">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="9d69e-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d69e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d69e-123">See Also</span></span>

[<span data-ttu-id="9d69e-124">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="9d69e-124">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9d69e-125">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9d69e-125">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="9d69e-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9d69e-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="9d69e-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9d69e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
