---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for SelectionSet (Format)
description: Name Element for SelectionSet (Format)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666445"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="0a5dd-103">Name Element for SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="0a5dd-103">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="0a5dd-104">指定用于引用选项集的名称。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-104">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="0a5dd-105">配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) SelectionSet (格式的 Name 元素) </span><span class="sxs-lookup"><span data-stu-id="0a5dd-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0a5dd-106">语法</span><span class="sxs-lookup"><span data-stu-id="0a5dd-106">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0a5dd-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0a5dd-107">Attributes and Elements</span></span>

<span data-ttu-id="0a5dd-108">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-108">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0a5dd-109">特性</span><span class="sxs-lookup"><span data-stu-id="0a5dd-109">Attributes</span></span>

<span data-ttu-id="0a5dd-110">无。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0a5dd-111">子元素</span><span class="sxs-lookup"><span data-stu-id="0a5dd-111">Child Elements</span></span>

<span data-ttu-id="0a5dd-112">无。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0a5dd-113">父元素</span><span class="sxs-lookup"><span data-stu-id="0a5dd-113">Parent Elements</span></span>

|<span data-ttu-id="0a5dd-114">元素</span><span class="sxs-lookup"><span data-stu-id="0a5dd-114">Element</span></span>|<span data-ttu-id="0a5dd-115">描述</span><span class="sxs-lookup"><span data-stu-id="0a5dd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0a5dd-116">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="0a5dd-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="0a5dd-117">定义一组可由集名称引用的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-117">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0a5dd-118">文本值</span><span class="sxs-lookup"><span data-stu-id="0a5dd-118">Text Value</span></span>

<span data-ttu-id="0a5dd-119">指定名称以引用选项集。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-119">Specify the name to reference the selection set.</span></span> <span data-ttu-id="0a5dd-120">对于可使用哪些字符没有任何限制。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-120">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a5dd-121">备注</span><span class="sxs-lookup"><span data-stu-id="0a5dd-121">Remarks</span></span>

<span data-ttu-id="0a5dd-122">此处指定的名称用于 `SelectionSetName` 元素。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-122">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="0a5dd-123">视图可以使用的选项集 (视图的视图定义可以具有多个定义) 或指定选择条件。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-123">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="0a5dd-124">有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="0a5dd-125">示例</span><span class="sxs-lookup"><span data-stu-id="0a5dd-125">Example</span></span>

<span data-ttu-id="0a5dd-126">此示例演示 `SelectionSet` 定义四个 .net 类型的元素。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="0a5dd-127">选择集的名称为 "FileSystemTypes"。</span><span class="sxs-lookup"><span data-stu-id="0a5dd-127">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0a5dd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a5dd-128">See Also</span></span>

[<span data-ttu-id="0a5dd-129">定义选项集</span><span class="sxs-lookup"><span data-stu-id="0a5dd-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0a5dd-130">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="0a5dd-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="0a5dd-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="0a5dd-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
