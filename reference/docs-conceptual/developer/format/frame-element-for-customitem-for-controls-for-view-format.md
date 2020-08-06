---
title: View (Format) 的控件的 CustomItem 的框架元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5ade36c183a026cb9001a2abbe91d31638a87108
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773447"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="ec504-102">Frame Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ec504-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="ec504-103">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="ec504-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="ec504-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="ec504-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ec504-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomEntries 元素对于 view (格式的 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view format 的 CustomItem 元素 (CustomEntry 的控件) 的控件 (格式) ) </span><span class="sxs-lookup"><span data-stu-id="ec504-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec504-106">语法</span><span class="sxs-lookup"><span data-stu-id="ec504-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec504-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ec504-107">Attributes and Elements</span></span>

<span data-ttu-id="ec504-108">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="ec504-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec504-109">特性</span><span class="sxs-lookup"><span data-stu-id="ec504-109">Attributes</span></span>

<span data-ttu-id="ec504-110">无。</span><span class="sxs-lookup"><span data-stu-id="ec504-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ec504-111">子元素</span><span class="sxs-lookup"><span data-stu-id="ec504-111">Child Elements</span></span>

|<span data-ttu-id="ec504-112">元素</span><span class="sxs-lookup"><span data-stu-id="ec504-112">Element</span></span>|<span data-ttu-id="ec504-113">说明</span><span class="sxs-lookup"><span data-stu-id="ec504-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="ec504-114">必需的元素</span><span class="sxs-lookup"><span data-stu-id="ec504-114">Required Element</span></span>|
|[<span data-ttu-id="ec504-115">View (Format) 的控件的框架的 FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="ec504-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ec504-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ec504-117">指定第一行向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="ec504-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="ec504-118">View (Format) 的控件的框架的 FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="ec504-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ec504-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ec504-120">指定第一行向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="ec504-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="ec504-121">View (Format) 的控件的框架的 LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="ec504-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ec504-122">Optional element.</span></span><br /><br /> <span data-ttu-id="ec504-123">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="ec504-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="ec504-124">View (Format) 的控件的框架的 RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="ec504-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ec504-125">Optional element.</span></span><br /><br /> <span data-ttu-id="ec504-126">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="ec504-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ec504-127">父元素</span><span class="sxs-lookup"><span data-stu-id="ec504-127">Parent Elements</span></span>

|<span data-ttu-id="ec504-128">元素</span><span class="sxs-lookup"><span data-stu-id="ec504-128">Element</span></span>|<span data-ttu-id="ec504-129">说明</span><span class="sxs-lookup"><span data-stu-id="ec504-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec504-130">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ec504-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="ec504-131">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="ec504-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ec504-132">备注</span><span class="sxs-lookup"><span data-stu-id="ec504-132">Remarks</span></span>

<span data-ttu-id="ec504-133">不能在同一元素中指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)和[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="ec504-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec504-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec504-134">See Also</span></span>

[<span data-ttu-id="ec504-135">View (Format) 的控件的框架的 FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="ec504-136">View (Format) 的控件的框架的 FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="ec504-137">View (Format) 的控件的框架的 LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="ec504-138">View (Format) 的控件的框架的 RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="ec504-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="ec504-139">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ec504-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="ec504-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ec504-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
