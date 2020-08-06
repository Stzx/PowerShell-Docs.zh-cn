---
title: 用于 CustomControl 的 CustomItem for () Format 的 Frame 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4864ea1a865f77c9de6e495d7e8296e81c19b366
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781437"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="cc88e-102">Frame Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cc88e-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="cc88e-103">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="cc88e-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="cc88e-104">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="cc88e-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="cc88e-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries for CustomItem 的 CustomEntry 元素 (CustomControlView 的 CustomItem 元素) CustomControl (格式) </span><span class="sxs-lookup"><span data-stu-id="cc88e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc88e-106">语法</span><span class="sxs-lookup"><span data-stu-id="cc88e-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc88e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-107">Attributes and Elements</span></span>

<span data-ttu-id="cc88e-108">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="cc88e-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc88e-109">特性</span><span class="sxs-lookup"><span data-stu-id="cc88e-109">Attributes</span></span>

<span data-ttu-id="cc88e-110">无。</span><span class="sxs-lookup"><span data-stu-id="cc88e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc88e-111">子元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-111">Child Elements</span></span>

|<span data-ttu-id="cc88e-112">元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-112">Element</span></span>|<span data-ttu-id="cc88e-113">说明</span><span class="sxs-lookup"><span data-stu-id="cc88e-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="cc88e-114">必需的元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-114">Required Element</span></span>|
|[<span data-ttu-id="cc88e-115">FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc88e-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cc88e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="cc88e-117">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="cc88e-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="cc88e-118">FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc88e-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cc88e-119">Optional element.</span></span><br /><br /> <span data-ttu-id="cc88e-120">指定第一行数据向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="cc88e-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="cc88e-121">LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc88e-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cc88e-122">Optional element.</span></span><br /><br /> <span data-ttu-id="cc88e-123">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="cc88e-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="cc88e-124">RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc88e-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="cc88e-125">Optional element.</span></span><br /><br /> <span data-ttu-id="cc88e-126">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="cc88e-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cc88e-127">父元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-127">Parent Elements</span></span>

|<span data-ttu-id="cc88e-128">元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-128">Element</span></span>|<span data-ttu-id="cc88e-129">说明</span><span class="sxs-lookup"><span data-stu-id="cc88e-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc88e-130">View (格式的 CustomEntry 的 CustomItem 元素) </span><span class="sxs-lookup"><span data-stu-id="cc88e-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc88e-131">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="cc88e-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cc88e-132">备注</span><span class="sxs-lookup"><span data-stu-id="cc88e-132">Remarks</span></span>

<span data-ttu-id="cc88e-133">不能在同一元素中指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)和[FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="cc88e-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc88e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc88e-134">See Also</span></span>

[<span data-ttu-id="cc88e-135">FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc88e-136">FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc88e-137">LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc88e-138">RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="cc88e-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc88e-139">View (格式的 CustomEntry 的 CustomItem 元素) </span><span class="sxs-lookup"><span data-stu-id="cc88e-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc88e-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="cc88e-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
