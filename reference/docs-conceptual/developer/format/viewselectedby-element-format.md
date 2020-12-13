---
ms.date: 09/13/2016
ms.topic: reference
title: ViewSelectedBy Element (Format)
description: ViewSelectedBy Element (Format)
ms.openlocfilehash: ac3c7de299b3009a067a476a024c6a6fcb5dce02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667702"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="9626f-103">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9626f-103">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="9626f-104">定义视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="9626f-104">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="9626f-105">每个视图必须至少指定一个 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="9626f-105">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="9626f-106">ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9626f-106">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9626f-107">语法</span><span class="sxs-lookup"><span data-stu-id="9626f-107">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9626f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9626f-108">Attributes and Elements</span></span>

<span data-ttu-id="9626f-109">以下各节描述了元素的属性、子元素和父元素 `ViewSelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="9626f-109">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="9626f-110">此元素必须包含至少一个 `TypeName` 或 `SelectionSetName` 子元素。</span><span class="sxs-lookup"><span data-stu-id="9626f-110">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="9626f-111">对于可以指定的子元素数没有限制，也没有其顺序。</span><span class="sxs-lookup"><span data-stu-id="9626f-111">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="9626f-112">特性</span><span class="sxs-lookup"><span data-stu-id="9626f-112">Attributes</span></span>

<span data-ttu-id="9626f-113">无。</span><span class="sxs-lookup"><span data-stu-id="9626f-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9626f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="9626f-114">Child Elements</span></span>

|<span data-ttu-id="9626f-115">元素</span><span class="sxs-lookup"><span data-stu-id="9626f-115">Element</span></span>|<span data-ttu-id="9626f-116">描述</span><span class="sxs-lookup"><span data-stu-id="9626f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9626f-117">TypeName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9626f-117">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="9626f-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9626f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9626f-119">指定视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="9626f-119">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="9626f-120">SelectionSetName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9626f-120">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="9626f-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9626f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="9626f-122">指定视图显示的一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="9626f-122">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9626f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="9626f-123">Parent Elements</span></span>

|<span data-ttu-id="9626f-124">元素</span><span class="sxs-lookup"><span data-stu-id="9626f-124">Element</span></span>|<span data-ttu-id="9626f-125">描述</span><span class="sxs-lookup"><span data-stu-id="9626f-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9626f-126">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9626f-126">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="9626f-127">定义一个视图，该视图显示一个或多个 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="9626f-127">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9626f-128">备注</span><span class="sxs-lookup"><span data-stu-id="9626f-128">Remarks</span></span>

<span data-ttu-id="9626f-129">有关此元素在不同视图中的使用方式的详细信息，请参阅 [表视图组件](./creating-a-table-view.md)、 [列表视图](./creating-a-list-view.md)组件、 [宽视图组件](./creating-a-wide-view.md)和 [自定义控件组件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="9626f-129">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="9626f-130">`SelectionSetName`当格式设置文件定义了由多个视图显示的一组对象时，使用元素。</span><span class="sxs-lookup"><span data-stu-id="9626f-130">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="9626f-131">有关如何定义和引用选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="9626f-131">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="9626f-132">示例</span><span class="sxs-lookup"><span data-stu-id="9626f-132">Example</span></span>

<span data-ttu-id="9626f-133">下面的示例演示如何为列表视图指定 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象。</span><span class="sxs-lookup"><span data-stu-id="9626f-133">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="9626f-134">表、宽视图和自定义视图使用相同的架构。</span><span class="sxs-lookup"><span data-stu-id="9626f-134">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="9626f-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9626f-135">See Also</span></span>

[<span data-ttu-id="9626f-136">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="9626f-136">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9626f-137">创建表视图</span><span class="sxs-lookup"><span data-stu-id="9626f-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9626f-138">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="9626f-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9626f-139">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="9626f-139">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="9626f-140">定义选项集</span><span class="sxs-lookup"><span data-stu-id="9626f-140">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="9626f-141">SelectionSetName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9626f-141">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="9626f-142">TypeName 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9626f-142">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="9626f-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9626f-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
