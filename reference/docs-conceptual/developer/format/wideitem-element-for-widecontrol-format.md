---
ms.date: 09/13/2016
ms.topic: reference
title: WideItem Element for WideControl (Format)
description: WideItem Element for WideControl (Format)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647794"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="dbb02-103">WideItem Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb02-103">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="dbb02-104">定义要显示其值的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="dbb02-104">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="dbb02-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="dbb02-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dbb02-106">语法</span><span class="sxs-lookup"><span data-stu-id="dbb02-106">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dbb02-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dbb02-107">Attributes and Elements</span></span>

<span data-ttu-id="dbb02-108">以下各节描述了元素的属性、子元素和父元素 `WideItem` 。</span><span class="sxs-lookup"><span data-stu-id="dbb02-108">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="dbb02-109">`FormatString` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="dbb02-109">The `FormatString` element is optional.</span></span> <span data-ttu-id="dbb02-110">但是，您必须指定 `PropertyName` 或 `ScriptBlock` 元素，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="dbb02-110">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="dbb02-111">特性</span><span class="sxs-lookup"><span data-stu-id="dbb02-111">Attributes</span></span>

<span data-ttu-id="dbb02-112">无。</span><span class="sxs-lookup"><span data-stu-id="dbb02-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dbb02-113">子元素</span><span class="sxs-lookup"><span data-stu-id="dbb02-113">Child Elements</span></span>

|<span data-ttu-id="dbb02-114">元素</span><span class="sxs-lookup"><span data-stu-id="dbb02-114">Element</span></span>|<span data-ttu-id="dbb02-115">描述</span><span class="sxs-lookup"><span data-stu-id="dbb02-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dbb02-116">FormatString Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb02-116">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="dbb02-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dbb02-117">Optional element.</span></span><br /><br /> <span data-ttu-id="dbb02-118">指定定义属性或脚本值在视图中显示方式的格式模式。</span><span class="sxs-lookup"><span data-stu-id="dbb02-118">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="dbb02-119">WideItem (格式的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="dbb02-119">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="dbb02-120">指定对象的属性，其值显示在宽视图中。</span><span class="sxs-lookup"><span data-stu-id="dbb02-120">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="dbb02-121">WideItem 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="dbb02-121">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="dbb02-122">指定其值在宽视图中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="dbb02-122">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dbb02-123">父元素</span><span class="sxs-lookup"><span data-stu-id="dbb02-123">Parent Elements</span></span>

|<span data-ttu-id="dbb02-124">元素</span><span class="sxs-lookup"><span data-stu-id="dbb02-124">Element</span></span>|<span data-ttu-id="dbb02-125">描述</span><span class="sxs-lookup"><span data-stu-id="dbb02-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dbb02-126">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="dbb02-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="dbb02-127">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="dbb02-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dbb02-128">备注</span><span class="sxs-lookup"><span data-stu-id="dbb02-128">Remarks</span></span>

<span data-ttu-id="dbb02-129">有关宽视图组件的详细信息，请参阅 [宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb02-129">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="dbb02-130">示例</span><span class="sxs-lookup"><span data-stu-id="dbb02-130">Example</span></span>

<span data-ttu-id="dbb02-131">下面的示例演示一个 `WideEntry` 元素，该元素定义单个 `WideItem` 元素。</span><span class="sxs-lookup"><span data-stu-id="dbb02-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="dbb02-132">`WideItem`元素定义其值在视图中显示的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="dbb02-132">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="dbb02-133">有关宽视图的完整示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb02-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb02-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbb02-134">See Also</span></span>

[<span data-ttu-id="dbb02-135">FormatString Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb02-135">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="dbb02-136">WideItem (格式的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="dbb02-136">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="dbb02-137">WideItem 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="dbb02-137">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="dbb02-138">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="dbb02-138">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="dbb02-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="dbb02-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
