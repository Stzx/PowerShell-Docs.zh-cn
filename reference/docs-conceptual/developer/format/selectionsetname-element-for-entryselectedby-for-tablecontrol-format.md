---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for TableControl (Format)
description: SelectionSetName Element for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: a5a395f718d0e1a2d7f33d120ce4fd2ff787cc34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651785"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f31dd-103">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f31dd-103">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f31dd-104">指定使用此表视图项的一组 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="f31dd-104">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="f31dd-105">对于可为条目指定的选项集数没有限制。</span><span class="sxs-lookup"><span data-stu-id="f31dd-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="f31dd-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 元素 (SelectionSetName) EntrySelectedBy (格式) </span><span class="sxs-lookup"><span data-stu-id="f31dd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f31dd-107">语法</span><span class="sxs-lookup"><span data-stu-id="f31dd-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f31dd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f31dd-108">Attributes and Elements</span></span>

<span data-ttu-id="f31dd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f31dd-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f31dd-110">特性</span><span class="sxs-lookup"><span data-stu-id="f31dd-110">Attributes</span></span>

<span data-ttu-id="f31dd-111">无。</span><span class="sxs-lookup"><span data-stu-id="f31dd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f31dd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f31dd-112">Child Elements</span></span>

<span data-ttu-id="f31dd-113">无。</span><span class="sxs-lookup"><span data-stu-id="f31dd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f31dd-114">父元素</span><span class="sxs-lookup"><span data-stu-id="f31dd-114">Parent Elements</span></span>

|<span data-ttu-id="f31dd-115">元素</span><span class="sxs-lookup"><span data-stu-id="f31dd-115">Element</span></span>|<span data-ttu-id="f31dd-116">描述</span><span class="sxs-lookup"><span data-stu-id="f31dd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f31dd-117">EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f31dd-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="f31dd-118">定义使用此项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="f31dd-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f31dd-119">文本值</span><span class="sxs-lookup"><span data-stu-id="f31dd-119">Text Value</span></span>

<span data-ttu-id="f31dd-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="f31dd-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f31dd-121">备注</span><span class="sxs-lookup"><span data-stu-id="f31dd-121">Remarks</span></span>

<span data-ttu-id="f31dd-122">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="f31dd-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f31dd-123">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="f31dd-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="f31dd-124">有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="f31dd-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f31dd-125">如果为某个条目指定了选择集，则无法指定类型名称。</span><span class="sxs-lookup"><span data-stu-id="f31dd-125">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="f31dd-126">有关如何指定 .NET 类型的详细信息，请参阅 [EntrySelectedBy For TableRowEntry 的 TypeName 元素 (Format) ](./typename-element-for-entryselectedby-for-tablecontrol-format.md)。</span><span class="sxs-lookup"><span data-stu-id="f31dd-126">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="f31dd-127">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f31dd-127">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f31dd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f31dd-128">See Also</span></span>

[<span data-ttu-id="f31dd-129">EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f31dd-129">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="f31dd-130">为视图定义对象集</span><span class="sxs-lookup"><span data-stu-id="f31dd-130">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f31dd-131">创建表视图</span><span class="sxs-lookup"><span data-stu-id="f31dd-131">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f31dd-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f31dd-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
