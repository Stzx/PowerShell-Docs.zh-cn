---
ms.date: 09/13/2016
ms.topic: reference
title: View Element (Format)
description: View Element (Format)
ms.openlocfilehash: 6fed1304d94339cc90b6ae53e06483c08d937c12
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649746"
---
# <a name="view-element-format"></a><span data-ttu-id="4cb12-103">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-103">View Element (Format)</span></span>

<span data-ttu-id="4cb12-104">定义一个视图，该视图显示一个或多个 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="4cb12-104">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="4cb12-105">对于可在格式设置文件中定义的视图数没有限制。</span><span class="sxs-lookup"><span data-stu-id="4cb12-105">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="4cb12-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4cb12-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4cb12-107">语法</span><span class="sxs-lookup"><span data-stu-id="4cb12-107">Syntax</span></span>

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4cb12-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4cb12-108">Attributes and Elements</span></span>

<span data-ttu-id="4cb12-109">以下各节描述了元素的属性、子元素和父元素 `View` 。</span><span class="sxs-lookup"><span data-stu-id="4cb12-109">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="4cb12-110">您必须指定一个且仅有一个控件子元素，并且您必须指定视图的名称和使用视图的对象。</span><span class="sxs-lookup"><span data-stu-id="4cb12-110">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="4cb12-111">定义自定义控件，如何对对象分组，并指定视图是否带外是可选的。</span><span class="sxs-lookup"><span data-stu-id="4cb12-111">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="4cb12-112">特性</span><span class="sxs-lookup"><span data-stu-id="4cb12-112">Attributes</span></span>

<span data-ttu-id="4cb12-113">无。</span><span class="sxs-lookup"><span data-stu-id="4cb12-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4cb12-114">子元素</span><span class="sxs-lookup"><span data-stu-id="4cb12-114">Child Elements</span></span>

|<span data-ttu-id="4cb12-115">元素</span><span class="sxs-lookup"><span data-stu-id="4cb12-115">Element</span></span>|<span data-ttu-id="4cb12-116">描述</span><span class="sxs-lookup"><span data-stu-id="4cb12-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4cb12-117">Controls Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-117">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="4cb12-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4cb12-119">定义一组可从视图中的名称引用的控件。</span><span class="sxs-lookup"><span data-stu-id="4cb12-119">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="4cb12-120">CustomControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4cb12-120">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="4cb12-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4cb12-122">定义视图的自定义控件格式。</span><span class="sxs-lookup"><span data-stu-id="4cb12-122">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="4cb12-123">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-123">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="4cb12-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4cb12-125">定义 .NET 对象成员的分组方式。</span><span class="sxs-lookup"><span data-stu-id="4cb12-125">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="4cb12-126">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-126">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="4cb12-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-127">Optional element.</span></span><br /><br /> <span data-ttu-id="4cb12-128">定义视图的列表格式。</span><span class="sxs-lookup"><span data-stu-id="4cb12-128">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="4cb12-129">Name Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-129">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="4cb12-130">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-130">Required element.</span></span><br /><br /> <span data-ttu-id="4cb12-131">指定用于引用视图的名称。</span><span class="sxs-lookup"><span data-stu-id="4cb12-131">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="4cb12-132">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-132">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="4cb12-133">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-133">Optional element.</span></span><br /><br /> <span data-ttu-id="4cb12-134">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="4cb12-134">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="4cb12-135">View (格式的 ViewSelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="4cb12-135">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="4cb12-136">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-136">Required element.</span></span><br /><br /> <span data-ttu-id="4cb12-137">定义此视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="4cb12-137">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="4cb12-138">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-138">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="4cb12-139">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4cb12-139">Optional element.</span></span><br /><br /> <span data-ttu-id="4cb12-140">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="4cb12-140">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4cb12-141">父元素</span><span class="sxs-lookup"><span data-stu-id="4cb12-141">Parent Elements</span></span>

|<span data-ttu-id="4cb12-142">元素</span><span class="sxs-lookup"><span data-stu-id="4cb12-142">Element</span></span>|<span data-ttu-id="4cb12-143">描述</span><span class="sxs-lookup"><span data-stu-id="4cb12-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4cb12-144">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-144">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="4cb12-145">定义用于显示对象的视图。</span><span class="sxs-lookup"><span data-stu-id="4cb12-145">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4cb12-146">备注</span><span class="sxs-lookup"><span data-stu-id="4cb12-146">Remarks</span></span>

<span data-ttu-id="4cb12-147">有关不同视图和自定义控件的组件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="4cb12-147">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="4cb12-148">表视图组件</span><span class="sxs-lookup"><span data-stu-id="4cb12-148">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="4cb12-149">列表视图组件</span><span class="sxs-lookup"><span data-stu-id="4cb12-149">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="4cb12-150">宽视图组件</span><span class="sxs-lookup"><span data-stu-id="4cb12-150">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="4cb12-151">自定义控件</span><span class="sxs-lookup"><span data-stu-id="4cb12-151">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="4cb12-152">示例</span><span class="sxs-lookup"><span data-stu-id="4cb12-152">Example</span></span>

<span data-ttu-id="4cb12-153">此示例演示一个 `View` 元素，该元素定义 [System.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象的表视图。</span><span class="sxs-lookup"><span data-stu-id="4cb12-153">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="4cb12-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cb12-154">See Also</span></span>

[<span data-ttu-id="4cb12-155">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-155">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="4cb12-156">Name Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-156">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="4cb12-157">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-157">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="4cb12-158">Controls Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-158">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="4cb12-159">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-159">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="4cb12-160">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-160">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="4cb12-161">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-161">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="4cb12-162">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4cb12-162">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="4cb12-163">CustomControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4cb12-163">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="4cb12-164">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4cb12-164">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
