---
title: EnumerableExpansion (Format) 的 SelectionCondition for EntrySelectedBy 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783460"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="0b5cc-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0b5cc-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="0b5cc-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="0b5cc-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="0b5cc-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy 的元素) EnumerableExpansion (格式) </span><span class="sxs-lookup"><span data-stu-id="0b5cc-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b5cc-106">语法</span><span class="sxs-lookup"><span data-stu-id="0b5cc-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b5cc-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0b5cc-107">Attributes and Elements</span></span>

<span data-ttu-id="0b5cc-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b5cc-109">特性</span><span class="sxs-lookup"><span data-stu-id="0b5cc-109">Attributes</span></span>

<span data-ttu-id="0b5cc-110">无。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b5cc-111">子元素</span><span class="sxs-lookup"><span data-stu-id="0b5cc-111">Child Elements</span></span>

<span data-ttu-id="0b5cc-112">无。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b5cc-113">父元素</span><span class="sxs-lookup"><span data-stu-id="0b5cc-113">Parent Elements</span></span>

|<span data-ttu-id="0b5cc-114">元素</span><span class="sxs-lookup"><span data-stu-id="0b5cc-114">Element</span></span>|<span data-ttu-id="0b5cc-115">描述</span><span class="sxs-lookup"><span data-stu-id="0b5cc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b5cc-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0b5cc-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0b5cc-117">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0b5cc-118">文本值</span><span class="sxs-lookup"><span data-stu-id="0b5cc-118">Text Value</span></span>

<span data-ttu-id="0b5cc-119">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b5cc-120">备注</span><span class="sxs-lookup"><span data-stu-id="0b5cc-120">Remarks</span></span>

<span data-ttu-id="0b5cc-121">选择条件必须指定至少一个要计算的属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="0b5cc-122">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5cc-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b5cc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b5cc-123">See Also</span></span>

[<span data-ttu-id="0b5cc-124">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="0b5cc-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0b5cc-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0b5cc-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="0b5cc-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0b5cc-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="0b5cc-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="0b5cc-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
