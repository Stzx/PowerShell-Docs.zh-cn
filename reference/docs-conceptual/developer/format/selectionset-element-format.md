---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSet Element (Format)
description: SelectionSet Element (Format)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647870"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="7eb53-103">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7eb53-103">SelectionSet Element (Format)</span></span>

<span data-ttu-id="7eb53-104">定义一组可由集名称引用的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb53-104">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="7eb53-105">配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7eb53-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7eb53-106">语法</span><span class="sxs-lookup"><span data-stu-id="7eb53-106">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7eb53-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7eb53-107">Attributes and Elements</span></span>

<span data-ttu-id="7eb53-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSet` 。</span><span class="sxs-lookup"><span data-stu-id="7eb53-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="7eb53-109">每个选项集都必须具有一个名称，并且必须指定该集的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb53-109">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="7eb53-110">特性</span><span class="sxs-lookup"><span data-stu-id="7eb53-110">Attributes</span></span>

<span data-ttu-id="7eb53-111">无。</span><span class="sxs-lookup"><span data-stu-id="7eb53-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7eb53-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7eb53-112">Child Elements</span></span>

|<span data-ttu-id="7eb53-113">元素</span><span class="sxs-lookup"><span data-stu-id="7eb53-113">Element</span></span>|<span data-ttu-id="7eb53-114">描述</span><span class="sxs-lookup"><span data-stu-id="7eb53-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7eb53-115">Name Element for SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="7eb53-115">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="7eb53-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7eb53-116">Required element.</span></span><br /><br /> <span data-ttu-id="7eb53-117">指定用于引用选项集的名称。</span><span class="sxs-lookup"><span data-stu-id="7eb53-117">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="7eb53-118">类型元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7eb53-118">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="7eb53-119">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7eb53-119">Required element.</span></span><br /><br /> <span data-ttu-id="7eb53-120">定义选择集中的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb53-120">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7eb53-121">父元素</span><span class="sxs-lookup"><span data-stu-id="7eb53-121">Parent Elements</span></span>

|<span data-ttu-id="7eb53-122">元素</span><span class="sxs-lookup"><span data-stu-id="7eb53-122">Element</span></span>|<span data-ttu-id="7eb53-123">描述</span><span class="sxs-lookup"><span data-stu-id="7eb53-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7eb53-124">SelectionSets 元素格式</span><span class="sxs-lookup"><span data-stu-id="7eb53-124">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="7eb53-125">定义可供格式设置文件的所有视图使用的常用 .NET 对象集。</span><span class="sxs-lookup"><span data-stu-id="7eb53-125">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7eb53-126">备注</span><span class="sxs-lookup"><span data-stu-id="7eb53-126">Remarks</span></span>

<span data-ttu-id="7eb53-127">如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。</span><span class="sxs-lookup"><span data-stu-id="7eb53-127">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="7eb53-128">定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。</span><span class="sxs-lookup"><span data-stu-id="7eb53-128">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="7eb53-129">常用选择集在定义格式设置文件的视图或视图定义时由其名称指定。</span><span class="sxs-lookup"><span data-stu-id="7eb53-129">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="7eb53-130">在这些情况下， `SelectionSetName` 和元素的子 `ViewSelectedBy` 元素 `EntrySelectedBy` 指定要使用的集。</span><span class="sxs-lookup"><span data-stu-id="7eb53-130">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="7eb53-131">有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="7eb53-131">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="7eb53-132">示例</span><span class="sxs-lookup"><span data-stu-id="7eb53-132">Example</span></span>

<span data-ttu-id="7eb53-133">下面的示例演示 `SelectionSet` 定义四个 .net 类型的元素。</span><span class="sxs-lookup"><span data-stu-id="7eb53-133">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```xml
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

## <a name="see-also"></a><span data-ttu-id="7eb53-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7eb53-134">See Also</span></span>

[<span data-ttu-id="7eb53-135">定义选项集</span><span class="sxs-lookup"><span data-stu-id="7eb53-135">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="7eb53-136">SelectionSet (格式的 Name 元素) </span><span class="sxs-lookup"><span data-stu-id="7eb53-136">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="7eb53-137">SelectionSets Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7eb53-137">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="7eb53-138">类型元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7eb53-138">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="7eb53-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7eb53-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
