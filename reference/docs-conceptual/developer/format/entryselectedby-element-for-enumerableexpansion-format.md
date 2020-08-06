---
title: EnumerableExpansion (Format) 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 031bf10cfb1aed2c737fdd53fa4f20f025351d40
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783664"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="e7355-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="e7355-103">定义使用此定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e7355-103">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="e7355-104">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EntrySelectedBy 元素用于 EnumerableExpansion (格式) </span><span class="sxs-lookup"><span data-stu-id="e7355-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7355-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7355-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7355-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e7355-106">Attributes and Elements</span></span>

<span data-ttu-id="e7355-107">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="e7355-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7355-108">特性</span><span class="sxs-lookup"><span data-stu-id="e7355-108">Attributes</span></span>

<span data-ttu-id="e7355-109">无。</span><span class="sxs-lookup"><span data-stu-id="e7355-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e7355-110">子元素</span><span class="sxs-lookup"><span data-stu-id="e7355-110">Child Elements</span></span>

|<span data-ttu-id="e7355-111">元素</span><span class="sxs-lookup"><span data-stu-id="e7355-111">Element</span></span>|<span data-ttu-id="e7355-112">描述</span><span class="sxs-lookup"><span data-stu-id="e7355-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7355-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7355-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e7355-114">Optional element.</span></span><br /><br /> <span data-ttu-id="e7355-115">定义扩展此定义的集合对象时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e7355-115">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="e7355-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7355-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e7355-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e7355-118">指定一组使用此定义如何扩展集合对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e7355-118">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="e7355-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7355-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e7355-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e7355-121">指定使用此定义如何扩展集合对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e7355-121">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e7355-122">父元素</span><span class="sxs-lookup"><span data-stu-id="e7355-122">Parent Elements</span></span>

|<span data-ttu-id="e7355-123">元素</span><span class="sxs-lookup"><span data-stu-id="e7355-123">Element</span></span>|<span data-ttu-id="e7355-124">描述</span><span class="sxs-lookup"><span data-stu-id="e7355-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7355-125">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-125">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="e7355-126">定义特定 .NET 集合对象在视图中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="e7355-126">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7355-127">备注</span><span class="sxs-lookup"><span data-stu-id="e7355-127">Remarks</span></span>

<span data-ttu-id="e7355-128">必须为定义条目指定至少一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="e7355-128">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="e7355-129">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="e7355-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="e7355-130">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e7355-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="e7355-131">有关选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e7355-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7355-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7355-132">See Also</span></span>

[<span data-ttu-id="e7355-133">定义用于显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="e7355-133">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e7355-134">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-134">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="e7355-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="e7355-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="e7355-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="e7355-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="e7355-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e7355-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
