---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControl Element for View (Format)
description: CustomControl Element for View (Format)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655474"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="50557-103">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50557-103">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="50557-104">定义视图的自定义控件格式。</span><span class="sxs-lookup"><span data-stu-id="50557-104">Defines a custom control format for the view.</span></span>

<span data-ttu-id="50557-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="50557-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50557-106">语法</span><span class="sxs-lookup"><span data-stu-id="50557-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50557-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50557-107">Attributes and Elements</span></span>

<span data-ttu-id="50557-108">以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。</span><span class="sxs-lookup"><span data-stu-id="50557-108">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="50557-109">您必须指定一个子元素。</span><span class="sxs-lookup"><span data-stu-id="50557-109">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="50557-110">特性</span><span class="sxs-lookup"><span data-stu-id="50557-110">Attributes</span></span>

<span data-ttu-id="50557-111">无。</span><span class="sxs-lookup"><span data-stu-id="50557-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50557-112">子元素</span><span class="sxs-lookup"><span data-stu-id="50557-112">Child Elements</span></span>

|<span data-ttu-id="50557-113">元素</span><span class="sxs-lookup"><span data-stu-id="50557-113">Element</span></span>|<span data-ttu-id="50557-114">描述</span><span class="sxs-lookup"><span data-stu-id="50557-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50557-115">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50557-115">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="50557-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="50557-116">Required element.</span></span><br /><br /> <span data-ttu-id="50557-117">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="50557-117">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="50557-118">父元素</span><span class="sxs-lookup"><span data-stu-id="50557-118">Parent Elements</span></span>

|<span data-ttu-id="50557-119">元素</span><span class="sxs-lookup"><span data-stu-id="50557-119">Element</span></span>|<span data-ttu-id="50557-120">描述</span><span class="sxs-lookup"><span data-stu-id="50557-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50557-121">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="50557-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="50557-122">定义用于显示一个或多个 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="50557-122">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="50557-123">备注</span><span class="sxs-lookup"><span data-stu-id="50557-123">Remarks</span></span>

<span data-ttu-id="50557-124">在大多数情况下，每个控件视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="50557-124">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="50557-125">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="50557-125">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="50557-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50557-126">See Also</span></span>

[<span data-ttu-id="50557-127">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50557-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="50557-128">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="50557-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="50557-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="50557-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
