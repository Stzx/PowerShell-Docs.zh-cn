---
title: EnumerableExpansion (Format) 的 EntrySelectedBy 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8745ef9e6f326c3e8a5dbf185a595bbe93e92414
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785313"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="6b466-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b466-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="6b466-103">指定通过此定义扩展的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="6b466-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="6b466-104">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionSetName) 格式 (EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="6b466-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6b466-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b466-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b466-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6b466-106">Attributes and Elements</span></span>

<span data-ttu-id="6b466-107">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="6b466-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b466-108">特性</span><span class="sxs-lookup"><span data-stu-id="6b466-108">Attributes</span></span>

<span data-ttu-id="6b466-109">无。</span><span class="sxs-lookup"><span data-stu-id="6b466-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6b466-110">子元素</span><span class="sxs-lookup"><span data-stu-id="6b466-110">Child Elements</span></span>

<span data-ttu-id="6b466-111">无。</span><span class="sxs-lookup"><span data-stu-id="6b466-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b466-112">父元素</span><span class="sxs-lookup"><span data-stu-id="6b466-112">Parent Elements</span></span>

|<span data-ttu-id="6b466-113">元素</span><span class="sxs-lookup"><span data-stu-id="6b466-113">Element</span></span>|<span data-ttu-id="6b466-114">描述</span><span class="sxs-lookup"><span data-stu-id="6b466-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6b466-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b466-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="6b466-116">定义通过此定义扩展的 .NET 集合对象。</span><span class="sxs-lookup"><span data-stu-id="6b466-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6b466-117">文本值</span><span class="sxs-lookup"><span data-stu-id="6b466-117">Text Value</span></span>

<span data-ttu-id="6b466-118">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="6b466-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b466-119">备注</span><span class="sxs-lookup"><span data-stu-id="6b466-119">Remarks</span></span>

<span data-ttu-id="6b466-120">每个定义必须指定一个或多个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="6b466-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="6b466-121">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="6b466-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="6b466-122">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="6b466-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="6b466-123">有关定义选择集的详细信息，请参阅为[视图定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="6b466-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b466-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b466-124">See Also</span></span>

[<span data-ttu-id="6b466-125">定义选项集</span><span class="sxs-lookup"><span data-stu-id="6b466-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="6b466-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b466-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="6b466-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="6b466-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
