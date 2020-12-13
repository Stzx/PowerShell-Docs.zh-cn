---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntries Element for WideControl (Format)
description: WideEntries Element for WideControl (Format)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651244"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="0755e-103">WideEntries Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="0755e-103">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="0755e-104">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="0755e-104">Provides the definitions of the wide view.</span></span> <span data-ttu-id="0755e-105">宽视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="0755e-105">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="0755e-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="0755e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0755e-107">语法</span><span class="sxs-lookup"><span data-stu-id="0755e-107">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="0755e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0755e-108">Attributes and Elements</span></span>

<span data-ttu-id="0755e-109">以下各节描述了元素的属性、子元素和父元素 `WideEntries` 。</span><span class="sxs-lookup"><span data-stu-id="0755e-109">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="0755e-110">必须至少指定一个子元素。</span><span class="sxs-lookup"><span data-stu-id="0755e-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="0755e-111">特性</span><span class="sxs-lookup"><span data-stu-id="0755e-111">Attributes</span></span>

<span data-ttu-id="0755e-112">无。</span><span class="sxs-lookup"><span data-stu-id="0755e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0755e-113">子元素</span><span class="sxs-lookup"><span data-stu-id="0755e-113">Child Elements</span></span>

|<span data-ttu-id="0755e-114">元素</span><span class="sxs-lookup"><span data-stu-id="0755e-114">Element</span></span>|<span data-ttu-id="0755e-115">描述</span><span class="sxs-lookup"><span data-stu-id="0755e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0755e-116">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="0755e-116">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="0755e-117">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="0755e-117">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0755e-118">父元素</span><span class="sxs-lookup"><span data-stu-id="0755e-118">Parent Elements</span></span>

|<span data-ttu-id="0755e-119">元素</span><span class="sxs-lookup"><span data-stu-id="0755e-119">Element</span></span>|<span data-ttu-id="0755e-120">描述</span><span class="sxs-lookup"><span data-stu-id="0755e-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0755e-121">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="0755e-121">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="0755e-122">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="0755e-122">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0755e-123">备注</span><span class="sxs-lookup"><span data-stu-id="0755e-123">Remarks</span></span>

<span data-ttu-id="0755e-124">宽视图是显示每个对象的单个属性值或脚本值的列表格式。</span><span class="sxs-lookup"><span data-stu-id="0755e-124">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="0755e-125">有关宽视图组件的详细信息，请参阅 [宽视图组件](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="0755e-125">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="0755e-126">示例</span><span class="sxs-lookup"><span data-stu-id="0755e-126">Example</span></span>

<span data-ttu-id="0755e-127">下面的示例演示一个 `WideEntries` 元素，该元素定义单个 `WideEntry` 元素。</span><span class="sxs-lookup"><span data-stu-id="0755e-127">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="0755e-128">`WideEntry`元素包含一个 `WideItem` 元素，该元素定义要在视图中显示的属性或脚本值。</span><span class="sxs-lookup"><span data-stu-id="0755e-128">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="0755e-129">有关宽视图的完整示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="0755e-129">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0755e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0755e-130">See Also</span></span>

[<span data-ttu-id="0755e-131">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="0755e-131">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0755e-132">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="0755e-132">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="0755e-133">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="0755e-133">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="0755e-134">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="0755e-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
