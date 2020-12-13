---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSets Element (Format)
description: SelectionSets Element (Format)
ms.openlocfilehash: e5c928dfb82bc6963b4a87aef9ec06d34cacfdcb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654926"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="47967-103">SelectionSets Element (Format)</span><span class="sxs-lookup"><span data-stu-id="47967-103">SelectionSets Element (Format)</span></span>

<span data-ttu-id="47967-104">定义可供格式设置文件的所有视图使用的常用 .NET 对象集。</span><span class="sxs-lookup"><span data-stu-id="47967-104">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="47967-105">格式设置文件的视图和控件可以只使用选择集的名称来引用完整的对象集。</span><span class="sxs-lookup"><span data-stu-id="47967-105">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="47967-106">配置元素 SelectionSets 元素格式</span><span class="sxs-lookup"><span data-stu-id="47967-106">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="47967-107">语法</span><span class="sxs-lookup"><span data-stu-id="47967-107">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="47967-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="47967-108">Attributes and Elements</span></span>

<span data-ttu-id="47967-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSets` 。</span><span class="sxs-lookup"><span data-stu-id="47967-109">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="47967-110">每个子元素定义一组可由集名称引用的对象。</span><span class="sxs-lookup"><span data-stu-id="47967-110">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="47967-111">子元素的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="47967-111">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="47967-112">特性</span><span class="sxs-lookup"><span data-stu-id="47967-112">Attributes</span></span>

<span data-ttu-id="47967-113">无。</span><span class="sxs-lookup"><span data-stu-id="47967-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="47967-114">子元素</span><span class="sxs-lookup"><span data-stu-id="47967-114">Child Elements</span></span>

|<span data-ttu-id="47967-115">元素</span><span class="sxs-lookup"><span data-stu-id="47967-115">Element</span></span>|<span data-ttu-id="47967-116">描述</span><span class="sxs-lookup"><span data-stu-id="47967-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47967-117">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="47967-117">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="47967-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="47967-118">Required element.</span></span><br /><br /> <span data-ttu-id="47967-119">定义一组可由集名称引用的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="47967-119">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="47967-120">父元素</span><span class="sxs-lookup"><span data-stu-id="47967-120">Parent Elements</span></span>

|<span data-ttu-id="47967-121">元素</span><span class="sxs-lookup"><span data-stu-id="47967-121">Element</span></span>|<span data-ttu-id="47967-122">描述</span><span class="sxs-lookup"><span data-stu-id="47967-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47967-123">配置元素</span><span class="sxs-lookup"><span data-stu-id="47967-123">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="47967-124">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="47967-124">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="47967-125">备注</span><span class="sxs-lookup"><span data-stu-id="47967-125">Remarks</span></span>

<span data-ttu-id="47967-126">如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。</span><span class="sxs-lookup"><span data-stu-id="47967-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="47967-127">定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。</span><span class="sxs-lookup"><span data-stu-id="47967-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="47967-128">常用选择集在定义格式设置文件的视图或视图定义时由其名称指定。</span><span class="sxs-lookup"><span data-stu-id="47967-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="47967-129">在这些情况下， `SelectionSetName` 和元素的子 `ViewSelectedBy` 元素 `EntrySelectedBy` 指定要使用的集。</span><span class="sxs-lookup"><span data-stu-id="47967-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="47967-130">有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="47967-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47967-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47967-131">See Also</span></span>

[<span data-ttu-id="47967-132">配置元素</span><span class="sxs-lookup"><span data-stu-id="47967-132">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="47967-133">定义选项集</span><span class="sxs-lookup"><span data-stu-id="47967-133">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="47967-134">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="47967-134">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="47967-135">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="47967-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
