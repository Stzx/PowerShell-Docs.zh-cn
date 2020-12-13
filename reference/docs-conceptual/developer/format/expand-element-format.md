---
ms.date: 09/13/2016
ms.topic: reference
title: Expand Element (Format)
description: Expand Element (Format)
ms.openlocfilehash: 518e132e3e74b921d4e51966fc60088a22ef63f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667940"
---
# <a name="expand-element-format"></a><span data-ttu-id="79d4d-103">Expand Element (Format)</span><span class="sxs-lookup"><span data-stu-id="79d4d-103">Expand Element (Format)</span></span>

<span data-ttu-id="79d4d-104">指定为此定义扩展集合对象的方式。</span><span class="sxs-lookup"><span data-stu-id="79d4d-104">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="79d4d-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) Expand 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="79d4d-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="79d4d-106">语法</span><span class="sxs-lookup"><span data-stu-id="79d4d-106">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="79d4d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79d4d-107">Attributes and Elements</span></span>

<span data-ttu-id="79d4d-108">以下各节描述了元素的属性、子元素和父元素 `Expand` 。</span><span class="sxs-lookup"><span data-stu-id="79d4d-108">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="79d4d-109">特性</span><span class="sxs-lookup"><span data-stu-id="79d4d-109">Attributes</span></span>

<span data-ttu-id="79d4d-110">无。</span><span class="sxs-lookup"><span data-stu-id="79d4d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="79d4d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="79d4d-111">Child Elements</span></span>

<span data-ttu-id="79d4d-112">无。</span><span class="sxs-lookup"><span data-stu-id="79d4d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="79d4d-113">父元素</span><span class="sxs-lookup"><span data-stu-id="79d4d-113">Parent Elements</span></span>

|<span data-ttu-id="79d4d-114">元素</span><span class="sxs-lookup"><span data-stu-id="79d4d-114">Element</span></span>|<span data-ttu-id="79d4d-115">描述</span><span class="sxs-lookup"><span data-stu-id="79d4d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79d4d-116">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="79d4d-116">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="79d4d-117">定义特定 .NET 集合对象在视图中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="79d4d-117">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="79d4d-118">文本值</span><span class="sxs-lookup"><span data-stu-id="79d4d-118">Text Value</span></span>

<span data-ttu-id="79d4d-119">指定以下值之一：</span><span class="sxs-lookup"><span data-stu-id="79d4d-119">Specify one of the following values:</span></span>

- <span data-ttu-id="79d4d-120">EnumOnly：仅显示集合中对象的属性。</span><span class="sxs-lookup"><span data-stu-id="79d4d-120">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="79d4d-121">CoreOnly：仅显示集合对象的属性。</span><span class="sxs-lookup"><span data-stu-id="79d4d-121">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="79d4d-122">Both：显示集合中的对象的属性和集合对象的属性。</span><span class="sxs-lookup"><span data-stu-id="79d4d-122">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="79d4d-123">备注</span><span class="sxs-lookup"><span data-stu-id="79d4d-123">Remarks</span></span>

<span data-ttu-id="79d4d-124">此元素用于定义集合对象和集合中的对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="79d4d-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="79d4d-125">在这种情况下，集合对象引用支持  **system.object** 接口的任何对象。</span><span class="sxs-lookup"><span data-stu-id="79d4d-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="79d4d-126">默认行为是只显示集合中对象的属性。</span><span class="sxs-lookup"><span data-stu-id="79d4d-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="79d4d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79d4d-127">See Also</span></span>

[<span data-ttu-id="79d4d-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="79d4d-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
