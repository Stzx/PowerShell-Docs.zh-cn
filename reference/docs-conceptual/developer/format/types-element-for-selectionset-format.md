---
ms.date: 09/13/2016
ms.topic: reference
title: Types Element for SelectionSet (Format)
description: Types Element for SelectionSet (Format)
ms.openlocfilehash: ff3c24e7f52f862dc416b88d50983196ce907012
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645456"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="3a662-103">Types Element for SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="3a662-103">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="3a662-104">定义选择集中的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="3a662-104">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="3a662-105">配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) 类型元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3a662-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3a662-106">语法</span><span class="sxs-lookup"><span data-stu-id="3a662-106">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a662-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3a662-107">Attributes and Elements</span></span>

<span data-ttu-id="3a662-108">以下各节描述了元素的属性、子元素和父元素 `Types` 。</span><span class="sxs-lookup"><span data-stu-id="3a662-108">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="3a662-109">必须至少有一个子元素，但对于可添加的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="3a662-109">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="3a662-110">特性</span><span class="sxs-lookup"><span data-stu-id="3a662-110">Attributes</span></span>

<span data-ttu-id="3a662-111">无。</span><span class="sxs-lookup"><span data-stu-id="3a662-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3a662-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3a662-112">Child Elements</span></span>

|<span data-ttu-id="3a662-113">元素</span><span class="sxs-lookup"><span data-stu-id="3a662-113">Element</span></span>|<span data-ttu-id="3a662-114">描述</span><span class="sxs-lookup"><span data-stu-id="3a662-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a662-115">类型的 TypeName 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3a662-115">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="3a662-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="3a662-116">Required element.</span></span><br /><br /> <span data-ttu-id="3a662-117">指定属于选择集的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="3a662-117">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3a662-118">父元素</span><span class="sxs-lookup"><span data-stu-id="3a662-118">Parent Elements</span></span>

|<span data-ttu-id="3a662-119">元素</span><span class="sxs-lookup"><span data-stu-id="3a662-119">Element</span></span>|<span data-ttu-id="3a662-120">描述</span><span class="sxs-lookup"><span data-stu-id="3a662-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a662-121">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3a662-121">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="3a662-122">定义一组可由集名称引用的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="3a662-122">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3a662-123">备注</span><span class="sxs-lookup"><span data-stu-id="3a662-123">Remarks</span></span>

<span data-ttu-id="3a662-124">此元素定义的对象构成一个选项集，视图可使用该选项集，视图 (视图的定义可) 多个定义或指定选择条件。</span><span class="sxs-lookup"><span data-stu-id="3a662-124">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="3a662-125">有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="3a662-125">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="3a662-126">示例</span><span class="sxs-lookup"><span data-stu-id="3a662-126">Example</span></span>

<span data-ttu-id="3a662-127">此示例演示 `SelectionSet` 定义四个 .net 类型的元素。</span><span class="sxs-lookup"><span data-stu-id="3a662-127">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3a662-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a662-128">See Also</span></span>

[<span data-ttu-id="3a662-129">定义对象集</span><span class="sxs-lookup"><span data-stu-id="3a662-129">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="3a662-130">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3a662-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="3a662-131">类型的 TypeName 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3a662-131">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="3a662-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3a662-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
