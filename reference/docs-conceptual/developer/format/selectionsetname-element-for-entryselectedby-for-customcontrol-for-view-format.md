---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)
description: SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)
ms.openlocfilehash: a158c5476fb3a168a146ce67565c0ed6f7859519
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651920"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="0c455-103">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="0c455-103">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="0c455-104">为列表条目指定一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="0c455-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="0c455-105">对于可为条目指定的选项集数没有限制。</span><span class="sxs-lookup"><span data-stu-id="0c455-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="0c455-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries 的 EntrySelectedBy 元素 (CustomEntry 的 SelectionSetName 元素 EntrySelectedBy) 格式 (</span><span class="sxs-lookup"><span data-stu-id="0c455-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c455-107">语法</span><span class="sxs-lookup"><span data-stu-id="0c455-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c455-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c455-108">Attributes and Elements</span></span>

<span data-ttu-id="0c455-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="0c455-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c455-110">特性</span><span class="sxs-lookup"><span data-stu-id="0c455-110">Attributes</span></span>

<span data-ttu-id="0c455-111">无。</span><span class="sxs-lookup"><span data-stu-id="0c455-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0c455-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0c455-112">Child Elements</span></span>

<span data-ttu-id="0c455-113">无。</span><span class="sxs-lookup"><span data-stu-id="0c455-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0c455-114">父元素</span><span class="sxs-lookup"><span data-stu-id="0c455-114">Parent Elements</span></span>

|<span data-ttu-id="0c455-115">元素</span><span class="sxs-lookup"><span data-stu-id="0c455-115">Element</span></span>|<span data-ttu-id="0c455-116">描述</span><span class="sxs-lookup"><span data-stu-id="0c455-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c455-117">View (格式的 CustomEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="0c455-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="0c455-118">定义使用此自定义项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="0c455-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0c455-119">文本值</span><span class="sxs-lookup"><span data-stu-id="0c455-119">Text Value</span></span>

<span data-ttu-id="0c455-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="0c455-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c455-121">备注</span><span class="sxs-lookup"><span data-stu-id="0c455-121">Remarks</span></span>

<span data-ttu-id="0c455-122">每个自定义控件项必须至少定义一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="0c455-122">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="0c455-123">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="0c455-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="0c455-124">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="0c455-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="0c455-125">有关定义选择集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="0c455-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0c455-126">有关自定义控件视图组件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="0c455-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c455-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c455-127">See Also</span></span>

[<span data-ttu-id="0c455-128">View (格式的 CustomEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="0c455-128">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0c455-129">自定义控件视图</span><span class="sxs-lookup"><span data-stu-id="0c455-129">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="0c455-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="0c455-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
