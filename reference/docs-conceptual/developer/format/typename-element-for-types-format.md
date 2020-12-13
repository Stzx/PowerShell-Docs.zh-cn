---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for Types (Format)
description: TypeName Element for Types (Format)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664622"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="b39f6-103">TypeName Element for Types (Format)</span><span class="sxs-lookup"><span data-stu-id="b39f6-103">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="b39f6-104">指定属于选择集的对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="b39f6-104">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="b39f6-105">配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) 格式 (格式) 类型 () 格式的 TypeName 元素</span><span class="sxs-lookup"><span data-stu-id="b39f6-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b39f6-106">语法</span><span class="sxs-lookup"><span data-stu-id="b39f6-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b39f6-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b39f6-107">Attributes and Elements</span></span>

<span data-ttu-id="b39f6-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="b39f6-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="b39f6-109">`TypeName`选择集中必须至少包含一个元素。</span><span class="sxs-lookup"><span data-stu-id="b39f6-109">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="b39f6-110">特性</span><span class="sxs-lookup"><span data-stu-id="b39f6-110">Attributes</span></span>

<span data-ttu-id="b39f6-111">无。</span><span class="sxs-lookup"><span data-stu-id="b39f6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b39f6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b39f6-112">Child Elements</span></span>

<span data-ttu-id="b39f6-113">无。</span><span class="sxs-lookup"><span data-stu-id="b39f6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b39f6-114">父元素</span><span class="sxs-lookup"><span data-stu-id="b39f6-114">Parent Elements</span></span>

|<span data-ttu-id="b39f6-115">元素</span><span class="sxs-lookup"><span data-stu-id="b39f6-115">Element</span></span>|<span data-ttu-id="b39f6-116">描述</span><span class="sxs-lookup"><span data-stu-id="b39f6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b39f6-117">类型元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="b39f6-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="b39f6-118">定义选择集中的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="b39f6-118">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b39f6-119">文本值</span><span class="sxs-lookup"><span data-stu-id="b39f6-119">Text Value</span></span>

<span data-ttu-id="b39f6-120">指定 .NET 类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="b39f6-120">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="b39f6-121">备注</span><span class="sxs-lookup"><span data-stu-id="b39f6-121">Remarks</span></span>

<span data-ttu-id="b39f6-122">如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。</span><span class="sxs-lookup"><span data-stu-id="b39f6-122">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="b39f6-123">定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。</span><span class="sxs-lookup"><span data-stu-id="b39f6-123">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="b39f6-124">常用选择集在定义格式设置文件的视图时由其名称指定。</span><span class="sxs-lookup"><span data-stu-id="b39f6-124">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="b39f6-125">在这些情况下， `SelectionSetName` 视图的元素的子元素 `ViewSelectedBy` 指定了集。</span><span class="sxs-lookup"><span data-stu-id="b39f6-125">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="b39f6-126">但是，视图的不同项还可以指定仅适用于该视图项的选择集。</span><span class="sxs-lookup"><span data-stu-id="b39f6-126">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="b39f6-127">有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="b39f6-127">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b39f6-128">示例</span><span class="sxs-lookup"><span data-stu-id="b39f6-128">Example</span></span>

<span data-ttu-id="b39f6-129">下面的示例演示 `SelectionSet` 定义四个 .net 类型的元素。</span><span class="sxs-lookup"><span data-stu-id="b39f6-129">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="b39f6-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b39f6-130">See Also</span></span>

[<span data-ttu-id="b39f6-131">定义选项集</span><span class="sxs-lookup"><span data-stu-id="b39f6-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b39f6-132">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b39f6-132">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="b39f6-133">SelectionSets Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b39f6-133">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="b39f6-134">类型元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="b39f6-134">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="b39f6-135">编写 Windows PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b39f6-135">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
