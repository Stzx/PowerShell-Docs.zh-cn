---
ms.date: 09/13/2016
ms.topic: reference
title: Frame Element for CustomItem for CustomControl for View (Format)
description: Frame Element for CustomItem for CustomControl for View (Format)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652191"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="865a6-103">Frame Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="865a6-103">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="865a6-104">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="865a6-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="865a6-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="865a6-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="865a6-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries for CustomItem 的 CustomEntry 元素 (CustomControlView 的 CustomItem 元素) CustomControl (格式) </span><span class="sxs-lookup"><span data-stu-id="865a6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="865a6-107">语法</span><span class="sxs-lookup"><span data-stu-id="865a6-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="865a6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="865a6-108">Attributes and Elements</span></span>

<span data-ttu-id="865a6-109">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="865a6-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="865a6-110">特性</span><span class="sxs-lookup"><span data-stu-id="865a6-110">Attributes</span></span>

<span data-ttu-id="865a6-111">无。</span><span class="sxs-lookup"><span data-stu-id="865a6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="865a6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="865a6-112">Child Elements</span></span>

|<span data-ttu-id="865a6-113">元素</span><span class="sxs-lookup"><span data-stu-id="865a6-113">Element</span></span>|<span data-ttu-id="865a6-114">描述</span><span class="sxs-lookup"><span data-stu-id="865a6-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="865a6-115">必需的元素</span><span class="sxs-lookup"><span data-stu-id="865a6-115">Required Element</span></span>|
|[<span data-ttu-id="865a6-116">FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-116">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="865a6-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="865a6-117">Optional element.</span></span><br /><br /> <span data-ttu-id="865a6-118">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="865a6-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="865a6-119">FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-119">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="865a6-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="865a6-120">Optional element.</span></span><br /><br /> <span data-ttu-id="865a6-121">指定第一行数据向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="865a6-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="865a6-122">LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-122">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="865a6-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="865a6-123">Optional element.</span></span><br /><br /> <span data-ttu-id="865a6-124">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="865a6-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="865a6-125">RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-125">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="865a6-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="865a6-126">Optional element.</span></span><br /><br /> <span data-ttu-id="865a6-127">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="865a6-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="865a6-128">父元素</span><span class="sxs-lookup"><span data-stu-id="865a6-128">Parent Elements</span></span>

|<span data-ttu-id="865a6-129">元素</span><span class="sxs-lookup"><span data-stu-id="865a6-129">Element</span></span>|<span data-ttu-id="865a6-130">描述</span><span class="sxs-lookup"><span data-stu-id="865a6-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="865a6-131">View (格式的 CustomEntry 的 CustomItem 元素) </span><span class="sxs-lookup"><span data-stu-id="865a6-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="865a6-132">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="865a6-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="865a6-133">备注</span><span class="sxs-lookup"><span data-stu-id="865a6-133">Remarks</span></span>

<span data-ttu-id="865a6-134">不能在同一元素中指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) 和 [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) 元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="865a6-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="865a6-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="865a6-135">See Also</span></span>

[<span data-ttu-id="865a6-136">FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-136">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="865a6-137">FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-137">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="865a6-138">LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-138">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="865a6-139">RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="865a6-139">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="865a6-140">View (格式的 CustomEntry 的 CustomItem 元素) </span><span class="sxs-lookup"><span data-stu-id="865a6-140">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="865a6-141">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="865a6-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
