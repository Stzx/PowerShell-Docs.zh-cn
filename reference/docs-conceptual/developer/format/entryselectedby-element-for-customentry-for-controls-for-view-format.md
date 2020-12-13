---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for CustomEntry for Controls for View (Format)
description: EntrySelectedBy Element for CustomEntry for Controls for View (Format)
ms.openlocfilehash: 29b0574a95d81962fb3f72a526f89273baeea647
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660266"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="327b2-103">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="327b2-103">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="327b2-104">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="327b2-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="327b2-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="327b2-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="327b2-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomControl 元素，用于控件的视图 (格式) CustomEntries 元素 (CustomEntry 的控件) CustomEntries 的控件，用于查看 (格式的控件) EntrySelectedBy 元素</span><span class="sxs-lookup"><span data-stu-id="327b2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="327b2-107">语法</span><span class="sxs-lookup"><span data-stu-id="327b2-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="327b2-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="327b2-108">Attributes and Elements</span></span>

<span data-ttu-id="327b2-109">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="327b2-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="327b2-110">必须为定义至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="327b2-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="327b2-111">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="327b2-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="327b2-112">特性</span><span class="sxs-lookup"><span data-stu-id="327b2-112">Attributes</span></span>

<span data-ttu-id="327b2-113">无。</span><span class="sxs-lookup"><span data-stu-id="327b2-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="327b2-114">子元素</span><span class="sxs-lookup"><span data-stu-id="327b2-114">Child Elements</span></span>

|<span data-ttu-id="327b2-115">元素</span><span class="sxs-lookup"><span data-stu-id="327b2-115">Element</span></span>|<span data-ttu-id="327b2-116">描述</span><span class="sxs-lookup"><span data-stu-id="327b2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="327b2-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="327b2-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="327b2-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="327b2-118">Optional element.</span></span><br /><br /> <span data-ttu-id="327b2-119">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="327b2-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="327b2-120">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="327b2-120">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="327b2-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="327b2-121">Optional element.</span></span><br /><br /> <span data-ttu-id="327b2-122">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="327b2-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="327b2-123">TypeName Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="327b2-123">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="327b2-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="327b2-124">Optional element.</span></span><br /><br /> <span data-ttu-id="327b2-125">指定使用控件的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="327b2-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="327b2-126">父元素</span><span class="sxs-lookup"><span data-stu-id="327b2-126">Parent Elements</span></span>

|<span data-ttu-id="327b2-127">元素</span><span class="sxs-lookup"><span data-stu-id="327b2-127">Element</span></span>|<span data-ttu-id="327b2-128">描述</span><span class="sxs-lookup"><span data-stu-id="327b2-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="327b2-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="327b2-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="327b2-130">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="327b2-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="327b2-131">备注</span><span class="sxs-lookup"><span data-stu-id="327b2-131">Remarks</span></span>

<span data-ttu-id="327b2-132">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="327b2-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="327b2-133">有关选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="327b2-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="327b2-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="327b2-134">See Also</span></span>

[<span data-ttu-id="327b2-135">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="327b2-135">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="327b2-136">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="327b2-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
