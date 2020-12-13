---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)
description: EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)
ms.openlocfilehash: 4821f22560f35034f90d018e5a109004f331441f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655356"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="e7f46-103">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7f46-103">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="e7f46-104">定义使用此自定义项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="e7f46-104">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="e7f46-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) EntrySelectedBy 的 CustomEntry 元素 (</span><span class="sxs-lookup"><span data-stu-id="e7f46-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7f46-106">语法</span><span class="sxs-lookup"><span data-stu-id="e7f46-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7f46-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e7f46-107">Attributes and Elements</span></span>

<span data-ttu-id="e7f46-108">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="e7f46-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7f46-109">特性</span><span class="sxs-lookup"><span data-stu-id="e7f46-109">Attributes</span></span>

<span data-ttu-id="e7f46-110">无。</span><span class="sxs-lookup"><span data-stu-id="e7f46-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e7f46-111">子元素</span><span class="sxs-lookup"><span data-stu-id="e7f46-111">Child Elements</span></span>

|<span data-ttu-id="e7f46-112">元素</span><span class="sxs-lookup"><span data-stu-id="e7f46-112">Element</span></span>|<span data-ttu-id="e7f46-113">描述</span><span class="sxs-lookup"><span data-stu-id="e7f46-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7f46-114">CustomEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-114">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="e7f46-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e7f46-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e7f46-116">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e7f46-116">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e7f46-117">CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-117">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="e7f46-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e7f46-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e7f46-119">指定一组使用控件视图的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e7f46-119">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="e7f46-120">CustomEntry (格式的 EntrySelectedBy 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-120">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e7f46-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e7f46-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e7f46-122">指定使用控件视图的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e7f46-122">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e7f46-123">父元素</span><span class="sxs-lookup"><span data-stu-id="e7f46-123">Parent Elements</span></span>

|<span data-ttu-id="e7f46-124">元素</span><span class="sxs-lookup"><span data-stu-id="e7f46-124">Element</span></span>|<span data-ttu-id="e7f46-125">描述</span><span class="sxs-lookup"><span data-stu-id="e7f46-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7f46-126">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-126">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="e7f46-127">定义特定 .NET 对象使用的控件。</span><span class="sxs-lookup"><span data-stu-id="e7f46-127">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7f46-128">备注</span><span class="sxs-lookup"><span data-stu-id="e7f46-128">Remarks</span></span>

<span data-ttu-id="e7f46-129">您必须为某个条目指定至少一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="e7f46-129">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="e7f46-130">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="e7f46-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="e7f46-131">选择条件用于定义要使用的项必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e7f46-131">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="e7f46-132">有关选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e7f46-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e7f46-133">有关自定义控件视图组件的详细信息，请参阅 [自定义控件视图](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="e7f46-133">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7f46-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7f46-134">See Also</span></span>

[<span data-ttu-id="e7f46-135">CustomEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-135">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="e7f46-136">CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-136">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e7f46-137">CustomEntry (格式的 EntrySelectedBy 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-137">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e7f46-138">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="e7f46-138">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e7f46-139">自定义控件视图</span><span class="sxs-lookup"><span data-stu-id="e7f46-139">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e7f46-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e7f46-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
