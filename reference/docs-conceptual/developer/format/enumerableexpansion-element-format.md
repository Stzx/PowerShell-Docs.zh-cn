---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion Element (Format)
description: EnumerableExpansion Element (Format)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668008"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="524d2-103">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="524d2-103">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="524d2-104">定义特定 .NET 集合对象在视图中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="524d2-104">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="524d2-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="524d2-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="524d2-106">语法</span><span class="sxs-lookup"><span data-stu-id="524d2-106">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="524d2-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="524d2-107">Attributes and Elements</span></span>

<span data-ttu-id="524d2-108">以下各节描述了元素的属性、子元素和父元素 `EnumerableExpansion` 。</span><span class="sxs-lookup"><span data-stu-id="524d2-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="524d2-109">特性</span><span class="sxs-lookup"><span data-stu-id="524d2-109">Attributes</span></span>

<span data-ttu-id="524d2-110">无。</span><span class="sxs-lookup"><span data-stu-id="524d2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="524d2-111">子元素</span><span class="sxs-lookup"><span data-stu-id="524d2-111">Child Elements</span></span>

|<span data-ttu-id="524d2-112">元素</span><span class="sxs-lookup"><span data-stu-id="524d2-112">Element</span></span>|<span data-ttu-id="524d2-113">描述</span><span class="sxs-lookup"><span data-stu-id="524d2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="524d2-114">EntrySelectedBy Element for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="524d2-114">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="524d2-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="524d2-115">Optional element.</span></span><br /><br /> <span data-ttu-id="524d2-116">定义通过此定义扩展哪些 .NET 集合对象。</span><span class="sxs-lookup"><span data-stu-id="524d2-116">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="524d2-117">Expand Element (Format)</span><span class="sxs-lookup"><span data-stu-id="524d2-117">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="524d2-118">指定为此定义扩展集合对象的方式。</span><span class="sxs-lookup"><span data-stu-id="524d2-118">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="524d2-119">父元素</span><span class="sxs-lookup"><span data-stu-id="524d2-119">Parent Elements</span></span>

|<span data-ttu-id="524d2-120">元素</span><span class="sxs-lookup"><span data-stu-id="524d2-120">Element</span></span>|<span data-ttu-id="524d2-121">描述</span><span class="sxs-lookup"><span data-stu-id="524d2-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="524d2-122">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="524d2-122">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="524d2-123">定义 .NET 集合对象在视图中显示时的扩展方式。</span><span class="sxs-lookup"><span data-stu-id="524d2-123">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="524d2-124">备注</span><span class="sxs-lookup"><span data-stu-id="524d2-124">Remarks</span></span>

<span data-ttu-id="524d2-125">此元素用于定义集合对象和集合中的对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="524d2-125">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="524d2-126">在这种情况下，集合对象引用支持  **system.object** 接口的任何对象。</span><span class="sxs-lookup"><span data-stu-id="524d2-126">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="524d2-127">默认行为是只显示集合中对象的属性。</span><span class="sxs-lookup"><span data-stu-id="524d2-127">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="524d2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="524d2-128">See Also</span></span>

[<span data-ttu-id="524d2-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="524d2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
