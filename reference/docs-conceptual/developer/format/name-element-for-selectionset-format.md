---
title: SelectionSet (Format) 的 Name 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1fc33eeb87a6912ed6793629ab1969cd65b5f0c5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773294"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="c25ef-102">Name Element for SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="c25ef-102">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="c25ef-103">指定用于引用选项集的名称。</span><span class="sxs-lookup"><span data-stu-id="c25ef-103">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="c25ef-104">配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) SelectionSet (格式的 Name 元素) </span><span class="sxs-lookup"><span data-stu-id="c25ef-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c25ef-105">语法</span><span class="sxs-lookup"><span data-stu-id="c25ef-105">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c25ef-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c25ef-106">Attributes and Elements</span></span>

<span data-ttu-id="c25ef-107">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="c25ef-107">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c25ef-108">特性</span><span class="sxs-lookup"><span data-stu-id="c25ef-108">Attributes</span></span>

<span data-ttu-id="c25ef-109">无。</span><span class="sxs-lookup"><span data-stu-id="c25ef-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c25ef-110">子元素</span><span class="sxs-lookup"><span data-stu-id="c25ef-110">Child Elements</span></span>

<span data-ttu-id="c25ef-111">无。</span><span class="sxs-lookup"><span data-stu-id="c25ef-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c25ef-112">父元素</span><span class="sxs-lookup"><span data-stu-id="c25ef-112">Parent Elements</span></span>

|<span data-ttu-id="c25ef-113">元素</span><span class="sxs-lookup"><span data-stu-id="c25ef-113">Element</span></span>|<span data-ttu-id="c25ef-114">说明</span><span class="sxs-lookup"><span data-stu-id="c25ef-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c25ef-115">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c25ef-115">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="c25ef-116">定义一组可由集名称引用的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="c25ef-116">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c25ef-117">文本值</span><span class="sxs-lookup"><span data-stu-id="c25ef-117">Text Value</span></span>

<span data-ttu-id="c25ef-118">指定名称以引用选项集。</span><span class="sxs-lookup"><span data-stu-id="c25ef-118">Specify the name to reference the selection set.</span></span> <span data-ttu-id="c25ef-119">对于可使用哪些字符没有任何限制。</span><span class="sxs-lookup"><span data-stu-id="c25ef-119">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="c25ef-120">备注</span><span class="sxs-lookup"><span data-stu-id="c25ef-120">Remarks</span></span>

<span data-ttu-id="c25ef-121">此处指定的名称用于 `SelectionSetName` 元素。</span><span class="sxs-lookup"><span data-stu-id="c25ef-121">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="c25ef-122">视图可以使用的选项集 (视图的视图定义可以具有多个定义) 或指定选择条件。</span><span class="sxs-lookup"><span data-stu-id="c25ef-122">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="c25ef-123">有关选择集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="c25ef-123">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="c25ef-124">示例</span><span class="sxs-lookup"><span data-stu-id="c25ef-124">Example</span></span>

<span data-ttu-id="c25ef-125">此示例演示 `SelectionSet` 定义四个 .net 类型的元素。</span><span class="sxs-lookup"><span data-stu-id="c25ef-125">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="c25ef-126">选择集的名称为 "FileSystemTypes"。</span><span class="sxs-lookup"><span data-stu-id="c25ef-126">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c25ef-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c25ef-127">See Also</span></span>

[<span data-ttu-id="c25ef-128">定义选项集</span><span class="sxs-lookup"><span data-stu-id="c25ef-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c25ef-129">SelectionSet Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c25ef-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="c25ef-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="c25ef-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
