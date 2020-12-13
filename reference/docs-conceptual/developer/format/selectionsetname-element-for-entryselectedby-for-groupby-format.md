---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for GroupBy (Format)
description: SelectionSetName Element for EntrySelectedBy for GroupBy (Format)
ms.openlocfilehash: 7ebe5d884061243c8b4af196788187d84c15a92e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651848"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="45e35-103">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="45e35-103">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="45e35-104">为列表条目指定一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="45e35-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="45e35-105">对于可为条目指定的选项集数没有限制。</span><span class="sxs-lookup"><span data-stu-id="45e35-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="45e35-106">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="45e35-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="45e35-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="45e35-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45e35-108">语法</span><span class="sxs-lookup"><span data-stu-id="45e35-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45e35-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45e35-109">Attributes and Elements</span></span>

<span data-ttu-id="45e35-110">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="45e35-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45e35-111">特性</span><span class="sxs-lookup"><span data-stu-id="45e35-111">Attributes</span></span>

<span data-ttu-id="45e35-112">无。</span><span class="sxs-lookup"><span data-stu-id="45e35-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45e35-113">子元素</span><span class="sxs-lookup"><span data-stu-id="45e35-113">Child Elements</span></span>

<span data-ttu-id="45e35-114">无。</span><span class="sxs-lookup"><span data-stu-id="45e35-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="45e35-115">父元素</span><span class="sxs-lookup"><span data-stu-id="45e35-115">Parent Elements</span></span>

|<span data-ttu-id="45e35-116">元素</span><span class="sxs-lookup"><span data-stu-id="45e35-116">Element</span></span>|<span data-ttu-id="45e35-117">描述</span><span class="sxs-lookup"><span data-stu-id="45e35-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45e35-118">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="45e35-118">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="45e35-119">定义使用此自定义项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="45e35-119">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="45e35-120">文本值</span><span class="sxs-lookup"><span data-stu-id="45e35-120">Text Value</span></span>

<span data-ttu-id="45e35-121">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="45e35-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="45e35-122">备注</span><span class="sxs-lookup"><span data-stu-id="45e35-122">Remarks</span></span>

<span data-ttu-id="45e35-123">每个自定义控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="45e35-123">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="45e35-124">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="45e35-124">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="45e35-125">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="45e35-125">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="45e35-126">有关定义选择集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="45e35-126">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="45e35-127">有关自定义控件视图组件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="45e35-127">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45e35-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45e35-128">See Also</span></span>

[<span data-ttu-id="45e35-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="45e35-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="45e35-130">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="45e35-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="45e35-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="45e35-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
