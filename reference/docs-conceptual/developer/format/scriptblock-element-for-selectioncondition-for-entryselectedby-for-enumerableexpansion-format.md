---
title: 用于 EnumerableExpansion (Format) 的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 71fd969fd3e5c0a4e39762c9a026982a8ca2a9d1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785364"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="31d17-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="31d17-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="31d17-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="31d17-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="31d17-104">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy) 格式 (EnumerableExpansion 的 ScriptBlock 元素) SelectionCondition (格式) </span><span class="sxs-lookup"><span data-stu-id="31d17-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="31d17-105">语法</span><span class="sxs-lookup"><span data-stu-id="31d17-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="31d17-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="31d17-106">Attributes and Elements</span></span>

<span data-ttu-id="31d17-107">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="31d17-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="31d17-108">特性</span><span class="sxs-lookup"><span data-stu-id="31d17-108">Attributes</span></span>

<span data-ttu-id="31d17-109">无。</span><span class="sxs-lookup"><span data-stu-id="31d17-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="31d17-110">子元素</span><span class="sxs-lookup"><span data-stu-id="31d17-110">Child Elements</span></span>

<span data-ttu-id="31d17-111">无。</span><span class="sxs-lookup"><span data-stu-id="31d17-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="31d17-112">父元素</span><span class="sxs-lookup"><span data-stu-id="31d17-112">Parent Elements</span></span>

|<span data-ttu-id="31d17-113">元素</span><span class="sxs-lookup"><span data-stu-id="31d17-113">Element</span></span>|<span data-ttu-id="31d17-114">说明</span><span class="sxs-lookup"><span data-stu-id="31d17-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31d17-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="31d17-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="31d17-116">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="31d17-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="31d17-117">文本值</span><span class="sxs-lookup"><span data-stu-id="31d17-117">Text Value</span></span>

<span data-ttu-id="31d17-118">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="31d17-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="31d17-119">备注</span><span class="sxs-lookup"><span data-stu-id="31d17-119">Remarks</span></span>

<span data-ttu-id="31d17-120">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="31d17-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="31d17-121">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="31d17-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31d17-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31d17-122">See Also</span></span>

[<span data-ttu-id="31d17-123">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="31d17-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="31d17-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="31d17-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="31d17-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="31d17-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="31d17-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="31d17-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
