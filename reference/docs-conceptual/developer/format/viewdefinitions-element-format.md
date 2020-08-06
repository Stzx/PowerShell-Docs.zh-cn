---
title: " (格式) 的 ViewDefinitions 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772478"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="26356-102">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="26356-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="26356-103">定义用于显示 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="26356-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="26356-104">这些视图可以采用表格格式、列表格式、宽格式和自定义控件格式显示对象的属性和脚本值。</span><span class="sxs-lookup"><span data-stu-id="26356-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="26356-105">配置元素 (格式) ViewDefinitions (格式 XML) 元素</span><span class="sxs-lookup"><span data-stu-id="26356-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="26356-106">语法</span><span class="sxs-lookup"><span data-stu-id="26356-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="26356-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="26356-107">Attributes and Elements</span></span>

<span data-ttu-id="26356-108">以下各节描述了元素的属性、子元素和父元素 `ViewDefinitions` 。</span><span class="sxs-lookup"><span data-stu-id="26356-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="26356-109">对于可以在格式设置文件中定义的视图数量没有限制，可以按任意顺序添加它们。</span><span class="sxs-lookup"><span data-stu-id="26356-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="26356-110">特性</span><span class="sxs-lookup"><span data-stu-id="26356-110">Attributes</span></span>

<span data-ttu-id="26356-111">无。</span><span class="sxs-lookup"><span data-stu-id="26356-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="26356-112">子元素</span><span class="sxs-lookup"><span data-stu-id="26356-112">Child Elements</span></span>

|<span data-ttu-id="26356-113">元素</span><span class="sxs-lookup"><span data-stu-id="26356-113">Element</span></span>|<span data-ttu-id="26356-114">说明</span><span class="sxs-lookup"><span data-stu-id="26356-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26356-115">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="26356-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="26356-116">定义用于显示一个或多个 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="26356-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="26356-117">父元素</span><span class="sxs-lookup"><span data-stu-id="26356-117">Parent Elements</span></span>

|<span data-ttu-id="26356-118">元素</span><span class="sxs-lookup"><span data-stu-id="26356-118">Element</span></span>|<span data-ttu-id="26356-119">说明</span><span class="sxs-lookup"><span data-stu-id="26356-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26356-120">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="26356-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="26356-121">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="26356-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26356-122">备注</span><span class="sxs-lookup"><span data-stu-id="26356-122">Remarks</span></span>

<span data-ttu-id="26356-123">有关不同视图类型的组件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="26356-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="26356-124">创建表视图</span><span class="sxs-lookup"><span data-stu-id="26356-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="26356-125">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="26356-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="26356-126">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="26356-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="26356-127">自定义控件</span><span class="sxs-lookup"><span data-stu-id="26356-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="26356-128">示例</span><span class="sxs-lookup"><span data-stu-id="26356-128">Example</span></span>

<span data-ttu-id="26356-129">此示例演示一个 `ViewDefinitions` 元素，该元素包含表视图和列表视图的父元素。</span><span class="sxs-lookup"><span data-stu-id="26356-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="26356-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26356-130">See Also</span></span>

[<span data-ttu-id="26356-131">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="26356-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="26356-132">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="26356-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="26356-133">创建表视图</span><span class="sxs-lookup"><span data-stu-id="26356-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="26356-134">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="26356-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="26356-135">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="26356-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="26356-136">自定义控件</span><span class="sxs-lookup"><span data-stu-id="26356-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="26356-137">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="26356-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
