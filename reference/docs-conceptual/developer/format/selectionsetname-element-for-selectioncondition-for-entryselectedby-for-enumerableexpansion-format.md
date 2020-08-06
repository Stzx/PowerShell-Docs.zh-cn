---
title: 用于 EntrySelectedBy for EnumerableExpansion (Format) 的 SelectionCondition 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787489"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="d2c0c-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d2c0c-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="d2c0c-103">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="d2c0c-104">如果此集中的任何类型存在，则满足条件。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="d2c0c-105">配置元素 DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy) EnumerableExpansion 的 SelectionSetName 元素 (SelectionCondition 的 EntrySelectedBy) 格式 (</span><span class="sxs-lookup"><span data-stu-id="d2c0c-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d2c0c-106">语法</span><span class="sxs-lookup"><span data-stu-id="d2c0c-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2c0c-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2c0c-107">Attributes and Elements</span></span>

<span data-ttu-id="d2c0c-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2c0c-109">特性</span><span class="sxs-lookup"><span data-stu-id="d2c0c-109">Attributes</span></span>

<span data-ttu-id="d2c0c-110">无。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d2c0c-111">子元素</span><span class="sxs-lookup"><span data-stu-id="d2c0c-111">Child Elements</span></span>

<span data-ttu-id="d2c0c-112">无。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2c0c-113">父元素</span><span class="sxs-lookup"><span data-stu-id="d2c0c-113">Parent Elements</span></span>

|<span data-ttu-id="d2c0c-114">元素</span><span class="sxs-lookup"><span data-stu-id="d2c0c-114">Element</span></span>|<span data-ttu-id="d2c0c-115">说明</span><span class="sxs-lookup"><span data-stu-id="d2c0c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2c0c-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d2c0c-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d2c0c-117">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d2c0c-118">文本值</span><span class="sxs-lookup"><span data-stu-id="d2c0c-118">Text Value</span></span>

<span data-ttu-id="d2c0c-119">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2c0c-120">备注</span><span class="sxs-lookup"><span data-stu-id="d2c0c-120">Remarks</span></span>

<span data-ttu-id="d2c0c-121">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="d2c0c-122">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d2c0c-123">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="d2c0c-124">有关创建和引用选项集的详细信息，请参阅[定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="d2c0c-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2c0c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2c0c-125">See Also</span></span>

[<span data-ttu-id="d2c0c-126">定义选项集</span><span class="sxs-lookup"><span data-stu-id="d2c0c-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d2c0c-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="d2c0c-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="d2c0c-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d2c0c-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
