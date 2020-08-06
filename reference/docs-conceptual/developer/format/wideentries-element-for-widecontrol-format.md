---
title: WideControl (Format) 的 WideEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785041"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="a4cec-102">WideEntries Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a4cec-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="a4cec-103">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="a4cec-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="a4cec-104">宽视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="a4cec-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="a4cec-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a4cec-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4cec-106">语法</span><span class="sxs-lookup"><span data-stu-id="a4cec-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4cec-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a4cec-107">Attributes and Elements</span></span>

<span data-ttu-id="a4cec-108">以下各节描述了元素的属性、子元素和父元素 `WideEntries` 。</span><span class="sxs-lookup"><span data-stu-id="a4cec-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="a4cec-109">必须至少指定一个子元素。</span><span class="sxs-lookup"><span data-stu-id="a4cec-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4cec-110">特性</span><span class="sxs-lookup"><span data-stu-id="a4cec-110">Attributes</span></span>

<span data-ttu-id="a4cec-111">无。</span><span class="sxs-lookup"><span data-stu-id="a4cec-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4cec-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a4cec-112">Child Elements</span></span>

|<span data-ttu-id="a4cec-113">元素</span><span class="sxs-lookup"><span data-stu-id="a4cec-113">Element</span></span>|<span data-ttu-id="a4cec-114">说明</span><span class="sxs-lookup"><span data-stu-id="a4cec-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4cec-115">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a4cec-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="a4cec-116">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="a4cec-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a4cec-117">父元素</span><span class="sxs-lookup"><span data-stu-id="a4cec-117">Parent Elements</span></span>

|<span data-ttu-id="a4cec-118">元素</span><span class="sxs-lookup"><span data-stu-id="a4cec-118">Element</span></span>|<span data-ttu-id="a4cec-119">说明</span><span class="sxs-lookup"><span data-stu-id="a4cec-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4cec-120">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a4cec-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="a4cec-121">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="a4cec-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a4cec-122">备注</span><span class="sxs-lookup"><span data-stu-id="a4cec-122">Remarks</span></span>

<span data-ttu-id="a4cec-123">宽视图是显示每个对象的单个属性值或脚本值的列表格式。</span><span class="sxs-lookup"><span data-stu-id="a4cec-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="a4cec-124">有关宽视图组件的详细信息，请参阅[宽视图组件](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="a4cec-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a4cec-125">示例</span><span class="sxs-lookup"><span data-stu-id="a4cec-125">Example</span></span>

<span data-ttu-id="a4cec-126">下面的示例演示一个 `WideEntries` 元素，该元素定义单个 `WideEntry` 元素。</span><span class="sxs-lookup"><span data-stu-id="a4cec-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="a4cec-127">`WideEntry`元素包含一个 `WideItem` 元素，该元素定义要在视图中显示的属性或脚本值。</span><span class="sxs-lookup"><span data-stu-id="a4cec-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="a4cec-128">有关宽视图的完整示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="a4cec-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4cec-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4cec-129">See Also</span></span>

[<span data-ttu-id="a4cec-130">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="a4cec-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a4cec-131">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a4cec-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="a4cec-132">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a4cec-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="a4cec-133">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a4cec-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
