---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)
description: SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651879"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="94b19-103">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="94b19-103">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="94b19-104">指定通过此定义扩展的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="94b19-104">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="94b19-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionSetName) 格式 (EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="94b19-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="94b19-106">语法</span><span class="sxs-lookup"><span data-stu-id="94b19-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="94b19-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="94b19-107">Attributes and Elements</span></span>

<span data-ttu-id="94b19-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="94b19-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="94b19-109">特性</span><span class="sxs-lookup"><span data-stu-id="94b19-109">Attributes</span></span>

<span data-ttu-id="94b19-110">无。</span><span class="sxs-lookup"><span data-stu-id="94b19-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="94b19-111">子元素</span><span class="sxs-lookup"><span data-stu-id="94b19-111">Child Elements</span></span>

<span data-ttu-id="94b19-112">无。</span><span class="sxs-lookup"><span data-stu-id="94b19-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="94b19-113">父元素</span><span class="sxs-lookup"><span data-stu-id="94b19-113">Parent Elements</span></span>

|<span data-ttu-id="94b19-114">元素</span><span class="sxs-lookup"><span data-stu-id="94b19-114">Element</span></span>|<span data-ttu-id="94b19-115">描述</span><span class="sxs-lookup"><span data-stu-id="94b19-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="94b19-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="94b19-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="94b19-117">定义通过此定义扩展的 .NET 集合对象。</span><span class="sxs-lookup"><span data-stu-id="94b19-117">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="94b19-118">文本值</span><span class="sxs-lookup"><span data-stu-id="94b19-118">Text Value</span></span>

<span data-ttu-id="94b19-119">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="94b19-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="94b19-120">备注</span><span class="sxs-lookup"><span data-stu-id="94b19-120">Remarks</span></span>

<span data-ttu-id="94b19-121">每个定义必须指定一个或多个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="94b19-121">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="94b19-122">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="94b19-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="94b19-123">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="94b19-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="94b19-124">有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="94b19-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94b19-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94b19-125">See Also</span></span>

[<span data-ttu-id="94b19-126">定义选项集</span><span class="sxs-lookup"><span data-stu-id="94b19-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="94b19-127">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="94b19-127">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="94b19-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="94b19-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
