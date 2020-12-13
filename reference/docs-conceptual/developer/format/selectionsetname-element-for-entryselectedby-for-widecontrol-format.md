---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for WideControl (Format)
description: SelectionSetName Element for EntrySelectedBy for WideControl (Format)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651702"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="3e074-103">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3e074-103">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="3e074-104">为定义指定一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="3e074-104">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="3e074-105">当显示其中一个对象时，将使用该定义。</span><span class="sxs-lookup"><span data-stu-id="3e074-105">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="3e074-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (SelectionSetName) 格式</span><span class="sxs-lookup"><span data-stu-id="3e074-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3e074-107">语法</span><span class="sxs-lookup"><span data-stu-id="3e074-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="3e074-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3e074-108">Attributes and Elements</span></span>

<span data-ttu-id="3e074-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="3e074-109">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3e074-110">特性</span><span class="sxs-lookup"><span data-stu-id="3e074-110">Attributes</span></span>

<span data-ttu-id="3e074-111">无。</span><span class="sxs-lookup"><span data-stu-id="3e074-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3e074-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3e074-112">Child Elements</span></span>

<span data-ttu-id="3e074-113">无。</span><span class="sxs-lookup"><span data-stu-id="3e074-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3e074-114">父元素</span><span class="sxs-lookup"><span data-stu-id="3e074-114">Parent Elements</span></span>

|<span data-ttu-id="3e074-115">元素</span><span class="sxs-lookup"><span data-stu-id="3e074-115">Element</span></span>|<span data-ttu-id="3e074-116">描述</span><span class="sxs-lookup"><span data-stu-id="3e074-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3e074-117">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3e074-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="3e074-118">定义使用此宽项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="3e074-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3e074-119">文本值</span><span class="sxs-lookup"><span data-stu-id="3e074-119">Text Value</span></span>

<span data-ttu-id="3e074-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="3e074-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e074-121">备注</span><span class="sxs-lookup"><span data-stu-id="3e074-121">Remarks</span></span>

<span data-ttu-id="3e074-122">每个定义必须指定一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="3e074-122">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="3e074-123">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="3e074-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="3e074-124">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="3e074-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="3e074-125">有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="3e074-125">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="3e074-126">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="3e074-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3e074-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e074-127">See Also</span></span>

[<span data-ttu-id="3e074-128">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="3e074-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="3e074-129">定义选项集</span><span class="sxs-lookup"><span data-stu-id="3e074-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="3e074-130">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3e074-130">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="3e074-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3e074-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
