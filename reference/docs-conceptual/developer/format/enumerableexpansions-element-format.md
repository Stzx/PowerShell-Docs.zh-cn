---
title: " (格式) 的 EnumerableExpansions 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774008"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="fce8c-102">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fce8c-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="fce8c-103">定义在视图中显示 .NET 集合对象时如何对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fce8c-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="fce8c-104">配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="fce8c-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fce8c-105">语法</span><span class="sxs-lookup"><span data-stu-id="fce8c-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fce8c-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fce8c-106">Attributes and Elements</span></span>

<span data-ttu-id="fce8c-107">以下各节描述了元素的属性、子元素和父元素 `EnumerableExpansions` 。</span><span class="sxs-lookup"><span data-stu-id="fce8c-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="fce8c-108">您可以使用的子元素数没有限制。</span><span class="sxs-lookup"><span data-stu-id="fce8c-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="fce8c-109">特性</span><span class="sxs-lookup"><span data-stu-id="fce8c-109">Attributes</span></span>

<span data-ttu-id="fce8c-110">无。</span><span class="sxs-lookup"><span data-stu-id="fce8c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fce8c-111">子元素</span><span class="sxs-lookup"><span data-stu-id="fce8c-111">Child Elements</span></span>

|<span data-ttu-id="fce8c-112">元素</span><span class="sxs-lookup"><span data-stu-id="fce8c-112">Element</span></span>|<span data-ttu-id="fce8c-113">说明</span><span class="sxs-lookup"><span data-stu-id="fce8c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fce8c-114">EnumerableExpansion Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fce8c-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="fce8c-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="fce8c-115">Optional element.</span></span><br /><br /> <span data-ttu-id="fce8c-116">定义特定 .NET 集合对象，这些对象在视图中显示时展开。</span><span class="sxs-lookup"><span data-stu-id="fce8c-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fce8c-117">父元素</span><span class="sxs-lookup"><span data-stu-id="fce8c-117">Parent Elements</span></span>

|<span data-ttu-id="fce8c-118">元素</span><span class="sxs-lookup"><span data-stu-id="fce8c-118">Element</span></span>|<span data-ttu-id="fce8c-119">说明</span><span class="sxs-lookup"><span data-stu-id="fce8c-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fce8c-120">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fce8c-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="fce8c-121">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="fce8c-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fce8c-122">备注</span><span class="sxs-lookup"><span data-stu-id="fce8c-122">Remarks</span></span>

<span data-ttu-id="fce8c-123">此元素用于定义集合对象和集合中的对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="fce8c-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="fce8c-124">在这种情况下，集合对象引用支持**system.object**接口的任何对象。</span><span class="sxs-lookup"><span data-stu-id="fce8c-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="fce8c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fce8c-125">See Also</span></span>

[<span data-ttu-id="fce8c-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="fce8c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
