---
ms.date: 09/13/2016
ms.topic: reference
title: Frame Element for CustomItem for Controls for View (Format)
description: Frame Element for CustomItem for Controls for View (Format)
ms.openlocfilehash: 6f26e19a6894ac213b924108a56cb80f9ffd1143
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652199"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="86651-103">Frame Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="86651-103">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="86651-104">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="86651-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="86651-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="86651-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="86651-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomEntries 元素对于 view (格式的 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view format 的 CustomItem 元素 (CustomEntry 的控件) 的控件 (格式) ) </span><span class="sxs-lookup"><span data-stu-id="86651-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="86651-107">语法</span><span class="sxs-lookup"><span data-stu-id="86651-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="86651-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="86651-108">Attributes and Elements</span></span>

<span data-ttu-id="86651-109">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="86651-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="86651-110">特性</span><span class="sxs-lookup"><span data-stu-id="86651-110">Attributes</span></span>

<span data-ttu-id="86651-111">无。</span><span class="sxs-lookup"><span data-stu-id="86651-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="86651-112">子元素</span><span class="sxs-lookup"><span data-stu-id="86651-112">Child Elements</span></span>

|<span data-ttu-id="86651-113">元素</span><span class="sxs-lookup"><span data-stu-id="86651-113">Element</span></span>|<span data-ttu-id="86651-114">描述</span><span class="sxs-lookup"><span data-stu-id="86651-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="86651-115">必需的元素</span><span class="sxs-lookup"><span data-stu-id="86651-115">Required Element</span></span>|
|[<span data-ttu-id="86651-116">View (Format) 的控件的框架的 FirstLineHanging 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-116">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="86651-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="86651-117">Optional element.</span></span><br /><br /> <span data-ttu-id="86651-118">指定第一行向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="86651-118">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="86651-119">View (Format) 的控件的框架的 FirstLineIndent 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-119">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="86651-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="86651-120">Optional element.</span></span><br /><br /> <span data-ttu-id="86651-121">指定第一行向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="86651-121">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="86651-122">View (Format) 的控件的框架的 LeftIndent 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-122">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="86651-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="86651-123">Optional element.</span></span><br /><br /> <span data-ttu-id="86651-124">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="86651-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="86651-125">View (Format) 的控件的框架的 RightIndent 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-125">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="86651-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="86651-126">Optional element.</span></span><br /><br /> <span data-ttu-id="86651-127">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="86651-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="86651-128">父元素</span><span class="sxs-lookup"><span data-stu-id="86651-128">Parent Elements</span></span>

|<span data-ttu-id="86651-129">元素</span><span class="sxs-lookup"><span data-stu-id="86651-129">Element</span></span>|<span data-ttu-id="86651-130">描述</span><span class="sxs-lookup"><span data-stu-id="86651-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86651-131">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="86651-131">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="86651-132">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="86651-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="86651-133">备注</span><span class="sxs-lookup"><span data-stu-id="86651-133">Remarks</span></span>

<span data-ttu-id="86651-134">不能在同一元素中指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) 和 [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) 元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="86651-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="86651-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86651-135">See Also</span></span>

[<span data-ttu-id="86651-136">View (Format) 的控件的框架的 FirstLineHanging 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-136">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="86651-137">View (Format) 的控件的框架的 FirstLineIndent 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-137">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="86651-138">View (Format) 的控件的框架的 LeftIndent 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-138">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="86651-139">View (Format) 的控件的框架的 RightIndent 元素 </span><span class="sxs-lookup"><span data-stu-id="86651-139">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="86651-140">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="86651-140">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="86651-141">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="86651-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
