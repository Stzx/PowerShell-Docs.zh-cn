---
title: " (Format) 的控件的 CustomItem 的框架元素Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781471"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="dbb48-102">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="dbb48-103">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="dbb48-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="dbb48-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="dbb48-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="dbb48-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 的控件的配置框架元素) CustomItem 的控件 (</span><span class="sxs-lookup"><span data-stu-id="dbb48-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dbb48-106">语法</span><span class="sxs-lookup"><span data-stu-id="dbb48-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dbb48-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-107">Attributes and Elements</span></span>

<span data-ttu-id="dbb48-108">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="dbb48-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dbb48-109">特性</span><span class="sxs-lookup"><span data-stu-id="dbb48-109">Attributes</span></span>

<span data-ttu-id="dbb48-110">无。</span><span class="sxs-lookup"><span data-stu-id="dbb48-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dbb48-111">子元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-111">Child Elements</span></span>

|<span data-ttu-id="dbb48-112">元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-112">Element</span></span>|<span data-ttu-id="dbb48-113">说明</span><span class="sxs-lookup"><span data-stu-id="dbb48-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="dbb48-114">必需的元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-114">Required Element</span></span>|
|[<span data-ttu-id="dbb48-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="dbb48-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dbb48-116">Optional element.</span></span><br /><br /> <span data-ttu-id="dbb48-117">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="dbb48-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="dbb48-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="dbb48-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dbb48-119">Optional element.</span></span><br /><br /> <span data-ttu-id="dbb48-120">指定第一行数据向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="dbb48-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="dbb48-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="dbb48-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dbb48-122">Optional element.</span></span><br /><br /> <span data-ttu-id="dbb48-123">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="dbb48-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="dbb48-124">RightIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="dbb48-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dbb48-125">Optional element.</span></span><br /><br /> <span data-ttu-id="dbb48-126">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="dbb48-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dbb48-127">父元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-127">Parent Elements</span></span>

|<span data-ttu-id="dbb48-128">元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-128">Element</span></span>|<span data-ttu-id="dbb48-129">说明</span><span class="sxs-lookup"><span data-stu-id="dbb48-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dbb48-130">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="dbb48-131">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="dbb48-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dbb48-132">备注</span><span class="sxs-lookup"><span data-stu-id="dbb48-132">Remarks</span></span>

<span data-ttu-id="dbb48-133">不能在同一元素中指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)和[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="dbb48-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb48-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbb48-134">See Also</span></span>

[<span data-ttu-id="dbb48-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="dbb48-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="dbb48-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="dbb48-138">RightIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb48-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="dbb48-139">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="dbb48-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="dbb48-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="dbb48-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
