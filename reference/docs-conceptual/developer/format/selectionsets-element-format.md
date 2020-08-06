---
title: " (格式) 的 SelectionSets 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 718b08e02220f285ef215fdca727492fd4407466
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785194"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="f8e3e-102">SelectionSets Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f8e3e-102">SelectionSets Element (Format)</span></span>

<span data-ttu-id="f8e3e-103">定义可供格式设置文件的所有视图使用的常用 .NET 对象集。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-103">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="f8e3e-104">格式设置文件的视图和控件可以只使用选择集的名称来引用完整的对象集。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-104">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="f8e3e-105">配置元素 SelectionSets 元素格式</span><span class="sxs-lookup"><span data-stu-id="f8e3e-105">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="f8e3e-106">语法</span><span class="sxs-lookup"><span data-stu-id="f8e3e-106">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8e3e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-107">Attributes and Elements</span></span>

<span data-ttu-id="f8e3e-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSets` 。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-108">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="f8e3e-109">每个子元素定义一组可由集名称引用的对象。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-109">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="f8e3e-110">子元素的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-110">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8e3e-111">特性</span><span class="sxs-lookup"><span data-stu-id="f8e3e-111">Attributes</span></span>

<span data-ttu-id="f8e3e-112">无。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8e3e-113">子元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-113">Child Elements</span></span>

|<span data-ttu-id="f8e3e-114">元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-114">Element</span></span>|<span data-ttu-id="f8e3e-115">描述</span><span class="sxs-lookup"><span data-stu-id="f8e3e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8e3e-116">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f8e3e-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="f8e3e-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-117">Required element.</span></span><br /><br /> <span data-ttu-id="f8e3e-118">定义一组可由集名称引用的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-118">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f8e3e-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-119">Parent Elements</span></span>

|<span data-ttu-id="f8e3e-120">元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-120">Element</span></span>|<span data-ttu-id="f8e3e-121">描述</span><span class="sxs-lookup"><span data-stu-id="f8e3e-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8e3e-122">配置元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-122">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="f8e3e-123">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-123">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8e3e-124">备注</span><span class="sxs-lookup"><span data-stu-id="f8e3e-124">Remarks</span></span>

<span data-ttu-id="f8e3e-125">如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-125">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="f8e3e-126">定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-126">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="f8e3e-127">常用选择集在定义格式设置文件的视图或视图定义时由其名称指定。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-127">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="f8e3e-128">在这些情况下， `SelectionSetName` 和元素的子 `ViewSelectedBy` 元素 `EntrySelectedBy` 指定要使用的集。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-128">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="f8e3e-129">有关选择集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-129">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8e3e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8e3e-130">See Also</span></span>

[<span data-ttu-id="f8e3e-131">配置元素</span><span class="sxs-lookup"><span data-stu-id="f8e3e-131">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="f8e3e-132">定义选项集</span><span class="sxs-lookup"><span data-stu-id="f8e3e-132">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f8e3e-133">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f8e3e-133">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="f8e3e-134">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f8e3e-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
