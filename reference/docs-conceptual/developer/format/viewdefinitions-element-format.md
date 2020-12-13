---
ms.date: 09/13/2016
ms.topic: reference
title: ViewDefinitions Element (Format)
description: ViewDefinitions Element (Format)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664587"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="a1418-103">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a1418-103">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="a1418-104">定义用于显示 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="a1418-104">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="a1418-105">这些视图可以采用表格格式、列表格式、宽格式和自定义控件格式显示对象的属性和脚本值。</span><span class="sxs-lookup"><span data-stu-id="a1418-105">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="a1418-106">配置元素 (格式) ViewDefinitions (格式 XML) 元素</span><span class="sxs-lookup"><span data-stu-id="a1418-106">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="a1418-107">语法</span><span class="sxs-lookup"><span data-stu-id="a1418-107">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a1418-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1418-108">Attributes and Elements</span></span>

<span data-ttu-id="a1418-109">以下各节描述了元素的属性、子元素和父元素 `ViewDefinitions` 。</span><span class="sxs-lookup"><span data-stu-id="a1418-109">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="a1418-110">对于可以在格式设置文件中定义的视图数量没有限制，可以按任意顺序添加它们。</span><span class="sxs-lookup"><span data-stu-id="a1418-110">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1418-111">特性</span><span class="sxs-lookup"><span data-stu-id="a1418-111">Attributes</span></span>

<span data-ttu-id="a1418-112">无。</span><span class="sxs-lookup"><span data-stu-id="a1418-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a1418-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a1418-113">Child Elements</span></span>

|<span data-ttu-id="a1418-114">元素</span><span class="sxs-lookup"><span data-stu-id="a1418-114">Element</span></span>|<span data-ttu-id="a1418-115">描述</span><span class="sxs-lookup"><span data-stu-id="a1418-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1418-116">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a1418-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="a1418-117">定义用于显示一个或多个 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="a1418-117">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a1418-118">父元素</span><span class="sxs-lookup"><span data-stu-id="a1418-118">Parent Elements</span></span>

|<span data-ttu-id="a1418-119">元素</span><span class="sxs-lookup"><span data-stu-id="a1418-119">Element</span></span>|<span data-ttu-id="a1418-120">描述</span><span class="sxs-lookup"><span data-stu-id="a1418-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1418-121">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a1418-121">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="a1418-122">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="a1418-122">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a1418-123">备注</span><span class="sxs-lookup"><span data-stu-id="a1418-123">Remarks</span></span>

<span data-ttu-id="a1418-124">有关不同视图类型的组件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a1418-124">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="a1418-125">创建表视图</span><span class="sxs-lookup"><span data-stu-id="a1418-125">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="a1418-126">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="a1418-126">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="a1418-127">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="a1418-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="a1418-128">自定义控件</span><span class="sxs-lookup"><span data-stu-id="a1418-128">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="a1418-129">示例</span><span class="sxs-lookup"><span data-stu-id="a1418-129">Example</span></span>

<span data-ttu-id="a1418-130">此示例演示一个 `ViewDefinitions` 元素，该元素包含表视图和列表视图的父元素。</span><span class="sxs-lookup"><span data-stu-id="a1418-130">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="a1418-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1418-131">See Also</span></span>

[<span data-ttu-id="a1418-132">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a1418-132">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="a1418-133">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a1418-133">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="a1418-134">创建表视图</span><span class="sxs-lookup"><span data-stu-id="a1418-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a1418-135">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="a1418-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a1418-136">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="a1418-136">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a1418-137">自定义控件</span><span class="sxs-lookup"><span data-stu-id="a1418-137">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a1418-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a1418-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
