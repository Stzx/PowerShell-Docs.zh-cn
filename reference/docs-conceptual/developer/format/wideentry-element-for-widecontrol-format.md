---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntry Element for WideControl (Format)
description: WideEntry Element for WideControl (Format)
ms.openlocfilehash: 3faaf767d11914792effd6765beed956a502c642
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664541"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="efb02-103">WideEntry Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="efb02-103">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="efb02-104">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="efb02-104">Provides a definition of the wide view.</span></span>

<span data-ttu-id="efb02-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="efb02-106">语法</span><span class="sxs-lookup"><span data-stu-id="efb02-106">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="efb02-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="efb02-107">Attributes and Elements</span></span>

<span data-ttu-id="efb02-108">以下各节描述了元素的属性、子元素和父元素 `WideEntry` 。</span><span class="sxs-lookup"><span data-stu-id="efb02-108">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="efb02-109">您必须指定一个 `WideItem` 子元素。</span><span class="sxs-lookup"><span data-stu-id="efb02-109">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="efb02-110">特性</span><span class="sxs-lookup"><span data-stu-id="efb02-110">Attributes</span></span>

<span data-ttu-id="efb02-111">无。</span><span class="sxs-lookup"><span data-stu-id="efb02-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="efb02-112">子元素</span><span class="sxs-lookup"><span data-stu-id="efb02-112">Child Elements</span></span>

|<span data-ttu-id="efb02-113">元素</span><span class="sxs-lookup"><span data-stu-id="efb02-113">Element</span></span>|<span data-ttu-id="efb02-114">描述</span><span class="sxs-lookup"><span data-stu-id="efb02-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="efb02-115">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="efb02-115">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="efb02-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="efb02-116">Optional element.</span></span><br /><br /> <span data-ttu-id="efb02-117">定义使用此宽项定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="efb02-117">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="efb02-118">WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-118">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="efb02-119">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="efb02-119">Required element.</span></span><br /><br /> <span data-ttu-id="efb02-120">定义要显示其值的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="efb02-120">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="efb02-121">父元素</span><span class="sxs-lookup"><span data-stu-id="efb02-121">Parent Elements</span></span>

|<span data-ttu-id="efb02-122">元素</span><span class="sxs-lookup"><span data-stu-id="efb02-122">Element</span></span>|<span data-ttu-id="efb02-123">描述</span><span class="sxs-lookup"><span data-stu-id="efb02-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="efb02-124">WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-124">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="efb02-125">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="efb02-125">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="efb02-126">备注</span><span class="sxs-lookup"><span data-stu-id="efb02-126">Remarks</span></span>

<span data-ttu-id="efb02-127">宽视图是显示每个对象的单个属性值或脚本值的列表格式。</span><span class="sxs-lookup"><span data-stu-id="efb02-127">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="efb02-128">与其他类型的视图不同，每个视图定义只能指定一个 item 元素。</span><span class="sxs-lookup"><span data-stu-id="efb02-128">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="efb02-129">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="efb02-129">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="efb02-130">示例</span><span class="sxs-lookup"><span data-stu-id="efb02-130">Example</span></span>

<span data-ttu-id="efb02-131">下面的示例演示一个 `WideEntry` 元素，该元素定义单个 `WideItem` 元素。</span><span class="sxs-lookup"><span data-stu-id="efb02-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="efb02-132">`WideItem`元素定义其值在视图中显示的属性。</span><span class="sxs-lookup"><span data-stu-id="efb02-132">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="efb02-133">有关宽视图的完整示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="efb02-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="efb02-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efb02-134">See Also</span></span>

[<span data-ttu-id="efb02-135">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="efb02-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="efb02-136">WideEntry 的 SelectionCondition 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-136">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="efb02-137">WideEntry 的 SelectionSetName 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-137">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="efb02-138">WideEntry (格式的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="efb02-138">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="efb02-139">WideEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-139">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="efb02-140">WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="efb02-140">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="efb02-141">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="efb02-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
