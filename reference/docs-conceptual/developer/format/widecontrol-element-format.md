---
title: " (格式) 的 WideControl 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: b6f19cf94dcb440eeaf53547db407287e5462520
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784973"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="7627e-102">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7627e-102">WideControl Element (Format)</span></span>

<span data-ttu-id="7627e-103">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="7627e-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="7627e-104">此视图显示每个对象的单个属性值或脚本值。</span><span class="sxs-lookup"><span data-stu-id="7627e-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="7627e-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7627e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7627e-106">语法</span><span class="sxs-lookup"><span data-stu-id="7627e-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7627e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7627e-107">Attributes and Elements</span></span>

<span data-ttu-id="7627e-108">以下各节描述了元素的属性、子元素和父元素 `WideControl` 。</span><span class="sxs-lookup"><span data-stu-id="7627e-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="7627e-109">不能同时指定 `AutoSize` 和 `ColumnNumber` 元素。</span><span class="sxs-lookup"><span data-stu-id="7627e-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="7627e-110">特性</span><span class="sxs-lookup"><span data-stu-id="7627e-110">Attributes</span></span>

<span data-ttu-id="7627e-111">无。</span><span class="sxs-lookup"><span data-stu-id="7627e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7627e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7627e-112">Child Elements</span></span>

|<span data-ttu-id="7627e-113">元素</span><span class="sxs-lookup"><span data-stu-id="7627e-113">Element</span></span>|<span data-ttu-id="7627e-114">说明</span><span class="sxs-lookup"><span data-stu-id="7627e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7627e-115">AutoSize Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7627e-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="7627e-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7627e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="7627e-117">指定是否根据数据大小调整列大小和列数。</span><span class="sxs-lookup"><span data-stu-id="7627e-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="7627e-118">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7627e-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="7627e-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7627e-119">Optional element.</span></span><br /><br /> <span data-ttu-id="7627e-120">指定宽视图中显示的列数。</span><span class="sxs-lookup"><span data-stu-id="7627e-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="7627e-121">WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7627e-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="7627e-122">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7627e-122">Required element.</span></span><br /><br /> <span data-ttu-id="7627e-123">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="7627e-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7627e-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7627e-124">Parent Elements</span></span>

|<span data-ttu-id="7627e-125">元素</span><span class="sxs-lookup"><span data-stu-id="7627e-125">Element</span></span>|<span data-ttu-id="7627e-126">说明</span><span class="sxs-lookup"><span data-stu-id="7627e-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7627e-127">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7627e-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="7627e-128">定义用于显示一个或多个 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="7627e-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7627e-129">备注</span><span class="sxs-lookup"><span data-stu-id="7627e-129">Remarks</span></span>

<span data-ttu-id="7627e-130">定义宽视图时，可以添加 `AutoSize` 元素或， `ColumnNumber` 但不能同时添加这两个元素。</span><span class="sxs-lookup"><span data-stu-id="7627e-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="7627e-131">在大多数情况下，每个宽视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="7627e-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="7627e-132">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="7627e-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="7627e-133">有关宽视图组件的详细信息，请参阅[宽视图组件](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="7627e-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7627e-134">示例</span><span class="sxs-lookup"><span data-stu-id="7627e-134">Example</span></span>

<span data-ttu-id="7627e-135">下面的示例演示一个 `WideControl` 元素，该元素用于显示[system.object](/dotnet/api/System.Diagnostics.Process)对象的属性。</span><span class="sxs-lookup"><span data-stu-id="7627e-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

<span data-ttu-id="7627e-136">有关宽视图的完整示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="7627e-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7627e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7627e-137">See Also</span></span>

[<span data-ttu-id="7627e-138">WideControl 的 Autosize 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7627e-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="7627e-139">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7627e-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="7627e-140">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7627e-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="7627e-141">WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7627e-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="7627e-142">宽视图 (Basic)</span><span class="sxs-lookup"><span data-stu-id="7627e-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="7627e-143">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="7627e-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7627e-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7627e-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
