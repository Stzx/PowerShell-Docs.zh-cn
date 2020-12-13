---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for CustomEntry for GroupBy (Format)
description: EntrySelectedBy Element for CustomEntry for GroupBy (Format)
ms.openlocfilehash: 5af4abe081ca268699d281a1b586a584107b9a83
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652355"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="293e5-103">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-103">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="293e5-104">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="293e5-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="293e5-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="293e5-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="293e5-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for 元素 for CustomControl for groupby (format) CustomEntry 元素 for CustomControl for groupby (格式) EntrySelectedBy 元素</span><span class="sxs-lookup"><span data-stu-id="293e5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="293e5-107">语法</span><span class="sxs-lookup"><span data-stu-id="293e5-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="293e5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="293e5-108">Attributes and Elements</span></span>

<span data-ttu-id="293e5-109">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="293e5-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="293e5-110">必须为定义至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="293e5-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="293e5-111">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="293e5-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="293e5-112">特性</span><span class="sxs-lookup"><span data-stu-id="293e5-112">Attributes</span></span>

<span data-ttu-id="293e5-113">无。</span><span class="sxs-lookup"><span data-stu-id="293e5-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="293e5-114">子元素</span><span class="sxs-lookup"><span data-stu-id="293e5-114">Child Elements</span></span>

|<span data-ttu-id="293e5-115">元素</span><span class="sxs-lookup"><span data-stu-id="293e5-115">Element</span></span>|<span data-ttu-id="293e5-116">描述</span><span class="sxs-lookup"><span data-stu-id="293e5-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="293e5-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="293e5-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="293e5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="293e5-119">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="293e5-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="293e5-120">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-120">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="293e5-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="293e5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="293e5-122">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="293e5-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="293e5-123">TypeName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-123">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="293e5-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="293e5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="293e5-125">指定使用控件的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="293e5-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="293e5-126">父元素</span><span class="sxs-lookup"><span data-stu-id="293e5-126">Parent Elements</span></span>

|<span data-ttu-id="293e5-127">元素</span><span class="sxs-lookup"><span data-stu-id="293e5-127">Element</span></span>|<span data-ttu-id="293e5-128">描述</span><span class="sxs-lookup"><span data-stu-id="293e5-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="293e5-129">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="293e5-130">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="293e5-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="293e5-131">备注</span><span class="sxs-lookup"><span data-stu-id="293e5-131">Remarks</span></span>

<span data-ttu-id="293e5-132">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="293e5-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="293e5-133">有关选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="293e5-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="293e5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="293e5-134">See Also</span></span>

[<span data-ttu-id="293e5-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="293e5-136">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-136">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="293e5-137">TypeName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-137">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="293e5-138">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="293e5-138">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="293e5-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="293e5-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
