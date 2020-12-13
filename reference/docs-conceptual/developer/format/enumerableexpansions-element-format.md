---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansions Element (Format)
description: EnumerableExpansions Element (Format)
ms.openlocfilehash: 789599e6ff368b4685c7937d5b6eb38618752f9e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660181"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="31206-103">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="31206-103">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="31206-104">定义在视图中显示 .NET 集合对象时如何对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="31206-104">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="31206-105">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="31206-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="31206-106">语法</span><span class="sxs-lookup"><span data-stu-id="31206-106">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="31206-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="31206-107">Attributes and Elements</span></span>

<span data-ttu-id="31206-108">以下各节描述了元素的属性、子元素和父元素 `EnumerableExpansions` 。</span><span class="sxs-lookup"><span data-stu-id="31206-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="31206-109">您可以使用的子元素数没有限制。</span><span class="sxs-lookup"><span data-stu-id="31206-109">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="31206-110">特性</span><span class="sxs-lookup"><span data-stu-id="31206-110">Attributes</span></span>

<span data-ttu-id="31206-111">无。</span><span class="sxs-lookup"><span data-stu-id="31206-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="31206-112">子元素</span><span class="sxs-lookup"><span data-stu-id="31206-112">Child Elements</span></span>

|<span data-ttu-id="31206-113">元素</span><span class="sxs-lookup"><span data-stu-id="31206-113">Element</span></span>|<span data-ttu-id="31206-114">描述</span><span class="sxs-lookup"><span data-stu-id="31206-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31206-115">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="31206-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="31206-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="31206-116">Optional element.</span></span><br /><br /> <span data-ttu-id="31206-117">定义特定 .NET 集合对象，这些对象在视图中显示时展开。</span><span class="sxs-lookup"><span data-stu-id="31206-117">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="31206-118">父元素</span><span class="sxs-lookup"><span data-stu-id="31206-118">Parent Elements</span></span>

|<span data-ttu-id="31206-119">元素</span><span class="sxs-lookup"><span data-stu-id="31206-119">Element</span></span>|<span data-ttu-id="31206-120">描述</span><span class="sxs-lookup"><span data-stu-id="31206-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31206-121">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="31206-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="31206-122">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="31206-122">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="31206-123">备注</span><span class="sxs-lookup"><span data-stu-id="31206-123">Remarks</span></span>

<span data-ttu-id="31206-124">此元素用于定义集合对象和集合中的对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="31206-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="31206-125">在这种情况下，集合对象引用支持  **system.object** 接口的任何对象。</span><span class="sxs-lookup"><span data-stu-id="31206-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="31206-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31206-126">See Also</span></span>

[<span data-ttu-id="31206-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="31206-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
