---
title: " (格式) 展开元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: deee832254bb8a774ee2c1f5bd451d3ced1bd47a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783647"
---
# <a name="expand-element-format"></a><span data-ttu-id="c7e5e-102">Expand Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c7e5e-102">Expand Element (Format)</span></span>

<span data-ttu-id="c7e5e-103">指定为此定义扩展集合对象的方式。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="c7e5e-104">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) Expand 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="c7e5e-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c7e5e-105">语法</span><span class="sxs-lookup"><span data-stu-id="c7e5e-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c7e5e-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c7e5e-106">Attributes and Elements</span></span>

<span data-ttu-id="c7e5e-107">以下各节描述了元素的属性、子元素和父元素 `Expand` 。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c7e5e-108">特性</span><span class="sxs-lookup"><span data-stu-id="c7e5e-108">Attributes</span></span>

<span data-ttu-id="c7e5e-109">无。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c7e5e-110">子元素</span><span class="sxs-lookup"><span data-stu-id="c7e5e-110">Child Elements</span></span>

<span data-ttu-id="c7e5e-111">无。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c7e5e-112">父元素</span><span class="sxs-lookup"><span data-stu-id="c7e5e-112">Parent Elements</span></span>

|<span data-ttu-id="c7e5e-113">元素</span><span class="sxs-lookup"><span data-stu-id="c7e5e-113">Element</span></span>|<span data-ttu-id="c7e5e-114">描述</span><span class="sxs-lookup"><span data-stu-id="c7e5e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c7e5e-115">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c7e5e-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="c7e5e-116">定义特定 .NET 集合对象在视图中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c7e5e-117">文本值</span><span class="sxs-lookup"><span data-stu-id="c7e5e-117">Text Value</span></span>

<span data-ttu-id="c7e5e-118">指定以下值之一：</span><span class="sxs-lookup"><span data-stu-id="c7e5e-118">Specify one of the following values:</span></span>

- <span data-ttu-id="c7e5e-119">EnumOnly：仅显示集合中对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="c7e5e-120">CoreOnly：仅显示集合对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="c7e5e-121">Both：显示集合中的对象的属性和集合对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7e5e-122">备注</span><span class="sxs-lookup"><span data-stu-id="c7e5e-122">Remarks</span></span>

<span data-ttu-id="c7e5e-123">此元素用于定义集合对象和集合中的对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="c7e5e-124">在这种情况下，集合对象引用支持**system.object**接口的任何对象。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="c7e5e-125">默认行为是只显示集合中对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c7e5e-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7e5e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7e5e-126">See Also</span></span>

[<span data-ttu-id="c7e5e-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="c7e5e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
