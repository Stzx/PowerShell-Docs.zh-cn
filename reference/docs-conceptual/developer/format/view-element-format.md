---
title: " (格式的 View 元素) |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785024"
---
# <a name="view-element-format"></a><span data-ttu-id="21405-102">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-102">View Element (Format)</span></span>

<span data-ttu-id="21405-103">定义一个视图，该视图显示一个或多个 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="21405-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="21405-104">对于可在格式设置文件中定义的视图数没有限制。</span><span class="sxs-lookup"><span data-stu-id="21405-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="21405-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="21405-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21405-106">语法</span><span class="sxs-lookup"><span data-stu-id="21405-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="21405-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="21405-107">Attributes and Elements</span></span>

<span data-ttu-id="21405-108">以下各节描述了元素的属性、子元素和父元素 `View` 。</span><span class="sxs-lookup"><span data-stu-id="21405-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="21405-109">您必须指定一个且仅有一个控件子元素，并且您必须指定视图的名称和使用视图的对象。</span><span class="sxs-lookup"><span data-stu-id="21405-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="21405-110">定义自定义控件，如何对对象分组，并指定视图是否带外是可选的。</span><span class="sxs-lookup"><span data-stu-id="21405-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="21405-111">特性</span><span class="sxs-lookup"><span data-stu-id="21405-111">Attributes</span></span>

<span data-ttu-id="21405-112">无。</span><span class="sxs-lookup"><span data-stu-id="21405-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21405-113">子元素</span><span class="sxs-lookup"><span data-stu-id="21405-113">Child Elements</span></span>

|<span data-ttu-id="21405-114">元素</span><span class="sxs-lookup"><span data-stu-id="21405-114">Element</span></span>|<span data-ttu-id="21405-115">描述</span><span class="sxs-lookup"><span data-stu-id="21405-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21405-116">Controls Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="21405-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="21405-117">Optional element.</span></span><br /><br /> <span data-ttu-id="21405-118">定义一组可从视图中的名称引用的控件。</span><span class="sxs-lookup"><span data-stu-id="21405-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="21405-119">CustomControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="21405-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="21405-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="21405-120">Optional element.</span></span><br /><br /> <span data-ttu-id="21405-121">定义视图的自定义控件格式。</span><span class="sxs-lookup"><span data-stu-id="21405-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="21405-122">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="21405-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="21405-123">Optional element.</span></span><br /><br /> <span data-ttu-id="21405-124">定义 .NET 对象成员的分组方式。</span><span class="sxs-lookup"><span data-stu-id="21405-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="21405-125">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="21405-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="21405-126">Optional element.</span></span><br /><br /> <span data-ttu-id="21405-127">定义视图的列表格式。</span><span class="sxs-lookup"><span data-stu-id="21405-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="21405-128">Name Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="21405-129">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="21405-129">Required element.</span></span><br /><br /> <span data-ttu-id="21405-130">指定用于引用视图的名称。</span><span class="sxs-lookup"><span data-stu-id="21405-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="21405-131">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="21405-132">可选元素。</span><span class="sxs-lookup"><span data-stu-id="21405-132">Optional element.</span></span><br /><br /> <span data-ttu-id="21405-133">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="21405-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="21405-134">View (格式的 ViewSelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="21405-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="21405-135">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="21405-135">Required element.</span></span><br /><br /> <span data-ttu-id="21405-136">定义此视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="21405-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="21405-137">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="21405-138">可选元素。</span><span class="sxs-lookup"><span data-stu-id="21405-138">Optional element.</span></span><br /><br /> <span data-ttu-id="21405-139">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="21405-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="21405-140">父元素</span><span class="sxs-lookup"><span data-stu-id="21405-140">Parent Elements</span></span>

|<span data-ttu-id="21405-141">元素</span><span class="sxs-lookup"><span data-stu-id="21405-141">Element</span></span>|<span data-ttu-id="21405-142">描述</span><span class="sxs-lookup"><span data-stu-id="21405-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21405-143">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="21405-144">定义用于显示对象的视图。</span><span class="sxs-lookup"><span data-stu-id="21405-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="21405-145">备注</span><span class="sxs-lookup"><span data-stu-id="21405-145">Remarks</span></span>

<span data-ttu-id="21405-146">有关不同视图和自定义控件的组件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="21405-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="21405-147">表视图组件</span><span class="sxs-lookup"><span data-stu-id="21405-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="21405-148">列表视图组件</span><span class="sxs-lookup"><span data-stu-id="21405-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="21405-149">宽视图组件</span><span class="sxs-lookup"><span data-stu-id="21405-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="21405-150">自定义控件</span><span class="sxs-lookup"><span data-stu-id="21405-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="21405-151">示例</span><span class="sxs-lookup"><span data-stu-id="21405-151">Example</span></span>

<span data-ttu-id="21405-152">此示例演示一个 `View` 元素，该元素定义[System.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)对象的表视图。</span><span class="sxs-lookup"><span data-stu-id="21405-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="21405-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21405-153">See Also</span></span>

[<span data-ttu-id="21405-154">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="21405-155">Name Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="21405-156">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="21405-157">Controls Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="21405-158">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="21405-159">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="21405-160">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="21405-161">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="21405-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="21405-162">CustomControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="21405-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="21405-163">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="21405-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
