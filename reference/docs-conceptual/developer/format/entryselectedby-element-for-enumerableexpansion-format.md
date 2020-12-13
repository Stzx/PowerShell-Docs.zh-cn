---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for EnumerableExpansion (Format)
description: EntrySelectedBy Element for EnumerableExpansion (Format)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652328"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="f3697-103">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-103">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="f3697-104">定义使用此定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f3697-104">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="f3697-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EntrySelectedBy 元素用于 EnumerableExpansion (格式) </span><span class="sxs-lookup"><span data-stu-id="f3697-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f3697-106">语法</span><span class="sxs-lookup"><span data-stu-id="f3697-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3697-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f3697-107">Attributes and Elements</span></span>

<span data-ttu-id="f3697-108">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="f3697-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3697-109">特性</span><span class="sxs-lookup"><span data-stu-id="f3697-109">Attributes</span></span>

<span data-ttu-id="f3697-110">无。</span><span class="sxs-lookup"><span data-stu-id="f3697-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f3697-111">子元素</span><span class="sxs-lookup"><span data-stu-id="f3697-111">Child Elements</span></span>

|<span data-ttu-id="f3697-112">元素</span><span class="sxs-lookup"><span data-stu-id="f3697-112">Element</span></span>|<span data-ttu-id="f3697-113">描述</span><span class="sxs-lookup"><span data-stu-id="f3697-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3697-114">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-114">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f3697-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3697-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f3697-116">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f3697-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="f3697-117">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-117">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f3697-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3697-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f3697-119">指定一组使用此定义如何扩展集合对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="f3697-119">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="f3697-120">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-120">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="f3697-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f3697-121">Optional element.</span></span><br /><br /> <span data-ttu-id="f3697-122">指定使用此定义如何扩展集合对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="f3697-122">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f3697-123">父元素</span><span class="sxs-lookup"><span data-stu-id="f3697-123">Parent Elements</span></span>

|<span data-ttu-id="f3697-124">元素</span><span class="sxs-lookup"><span data-stu-id="f3697-124">Element</span></span>|<span data-ttu-id="f3697-125">描述</span><span class="sxs-lookup"><span data-stu-id="f3697-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3697-126">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-126">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="f3697-127">定义特定 .NET 集合对象在视图中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="f3697-127">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3697-128">备注</span><span class="sxs-lookup"><span data-stu-id="f3697-128">Remarks</span></span>

<span data-ttu-id="f3697-129">必须为定义条目指定至少一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="f3697-129">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="f3697-130">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="f3697-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="f3697-131">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="f3697-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="f3697-132">有关选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f3697-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3697-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3697-133">See Also</span></span>

[<span data-ttu-id="f3697-134">定义用于显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="f3697-134">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f3697-135">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-135">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="f3697-136">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-136">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="f3697-137">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-137">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="f3697-138">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f3697-138">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="f3697-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f3697-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
