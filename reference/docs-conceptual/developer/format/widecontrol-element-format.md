---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl Element (Format)
description: WideControl Element (Format)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651276"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="faacb-103">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="faacb-103">WideControl Element (Format)</span></span>

<span data-ttu-id="faacb-104">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="faacb-104">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="faacb-105">此视图显示每个对象的单个属性值或脚本值。</span><span class="sxs-lookup"><span data-stu-id="faacb-105">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="faacb-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="faacb-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="faacb-107">语法</span><span class="sxs-lookup"><span data-stu-id="faacb-107">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="faacb-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="faacb-108">Attributes and Elements</span></span>

<span data-ttu-id="faacb-109">以下各节描述了元素的属性、子元素和父元素 `WideControl` 。</span><span class="sxs-lookup"><span data-stu-id="faacb-109">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="faacb-110">不能同时指定 `AutoSize` 和 `ColumnNumber` 元素。</span><span class="sxs-lookup"><span data-stu-id="faacb-110">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="faacb-111">特性</span><span class="sxs-lookup"><span data-stu-id="faacb-111">Attributes</span></span>

<span data-ttu-id="faacb-112">无。</span><span class="sxs-lookup"><span data-stu-id="faacb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="faacb-113">子元素</span><span class="sxs-lookup"><span data-stu-id="faacb-113">Child Elements</span></span>

|<span data-ttu-id="faacb-114">元素</span><span class="sxs-lookup"><span data-stu-id="faacb-114">Element</span></span>|<span data-ttu-id="faacb-115">描述</span><span class="sxs-lookup"><span data-stu-id="faacb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="faacb-116">AutoSize Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="faacb-116">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="faacb-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="faacb-117">Optional element.</span></span><br /><br /> <span data-ttu-id="faacb-118">指定是否根据数据大小调整列大小和列数。</span><span class="sxs-lookup"><span data-stu-id="faacb-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="faacb-119">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="faacb-119">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="faacb-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="faacb-120">Optional element.</span></span><br /><br /> <span data-ttu-id="faacb-121">指定宽视图中显示的列数。</span><span class="sxs-lookup"><span data-stu-id="faacb-121">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="faacb-122">WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="faacb-122">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="faacb-123">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="faacb-123">Required element.</span></span><br /><br /> <span data-ttu-id="faacb-124">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="faacb-124">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="faacb-125">父元素</span><span class="sxs-lookup"><span data-stu-id="faacb-125">Parent Elements</span></span>

|<span data-ttu-id="faacb-126">元素</span><span class="sxs-lookup"><span data-stu-id="faacb-126">Element</span></span>|<span data-ttu-id="faacb-127">描述</span><span class="sxs-lookup"><span data-stu-id="faacb-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="faacb-128">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="faacb-128">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="faacb-129">定义用于显示一个或多个 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="faacb-129">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="faacb-130">备注</span><span class="sxs-lookup"><span data-stu-id="faacb-130">Remarks</span></span>

<span data-ttu-id="faacb-131">定义宽视图时，可以添加 `AutoSize` 元素或， `ColumnNumber` 但不能同时添加这两个元素。</span><span class="sxs-lookup"><span data-stu-id="faacb-131">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="faacb-132">在大多数情况下，每个宽视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="faacb-132">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="faacb-133">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="faacb-133">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="faacb-134">有关宽视图组件的详细信息，请参阅 [宽视图组件](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="faacb-134">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="faacb-135">示例</span><span class="sxs-lookup"><span data-stu-id="faacb-135">Example</span></span>

<span data-ttu-id="faacb-136">下面的示例演示一个 `WideControl` 元素，该元素用于显示 [system.object](/dotnet/api/System.Diagnostics.Process) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="faacb-136">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="faacb-137">有关宽视图的完整示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="faacb-137">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="faacb-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faacb-138">See Also</span></span>

[<span data-ttu-id="faacb-139">WideControl 的 Autosize 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="faacb-139">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="faacb-140">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="faacb-140">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="faacb-141">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="faacb-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="faacb-142">WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="faacb-142">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="faacb-143">宽视图 (Basic)</span><span class="sxs-lookup"><span data-stu-id="faacb-143">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="faacb-144">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="faacb-144">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="faacb-145">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="faacb-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
