---
ms.date: 09/13/2016
ms.topic: reference
title: Frame Element for CustomItem for Controls for Configuration (Format)
description: Frame Element for CustomItem for Controls for Configuration (Format)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652245"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="a039c-103">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-103">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a039c-104">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="a039c-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="a039c-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="a039c-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a039c-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 的控件的配置框架元素) CustomItem 的控件 (</span><span class="sxs-lookup"><span data-stu-id="a039c-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a039c-107">语法</span><span class="sxs-lookup"><span data-stu-id="a039c-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a039c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a039c-108">Attributes and Elements</span></span>

<span data-ttu-id="a039c-109">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="a039c-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a039c-110">特性</span><span class="sxs-lookup"><span data-stu-id="a039c-110">Attributes</span></span>

<span data-ttu-id="a039c-111">无。</span><span class="sxs-lookup"><span data-stu-id="a039c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a039c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a039c-112">Child Elements</span></span>

|<span data-ttu-id="a039c-113">元素</span><span class="sxs-lookup"><span data-stu-id="a039c-113">Element</span></span>|<span data-ttu-id="a039c-114">描述</span><span class="sxs-lookup"><span data-stu-id="a039c-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="a039c-115">必需的元素</span><span class="sxs-lookup"><span data-stu-id="a039c-115">Required Element</span></span>|
|[<span data-ttu-id="a039c-116">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-116">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="a039c-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a039c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a039c-118">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="a039c-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="a039c-119">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-119">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="a039c-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a039c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a039c-121">指定第一行数据向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="a039c-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="a039c-122">LeftIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-122">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="a039c-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a039c-123">Optional element.</span></span><br /><br /> <span data-ttu-id="a039c-124">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="a039c-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="a039c-125">RightIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-125">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="a039c-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a039c-126">Optional element.</span></span><br /><br /> <span data-ttu-id="a039c-127">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="a039c-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a039c-128">父元素</span><span class="sxs-lookup"><span data-stu-id="a039c-128">Parent Elements</span></span>

|<span data-ttu-id="a039c-129">元素</span><span class="sxs-lookup"><span data-stu-id="a039c-129">Element</span></span>|<span data-ttu-id="a039c-130">描述</span><span class="sxs-lookup"><span data-stu-id="a039c-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a039c-131">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="a039c-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="a039c-132">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="a039c-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a039c-133">备注</span><span class="sxs-lookup"><span data-stu-id="a039c-133">Remarks</span></span>

<span data-ttu-id="a039c-134">不能在同一元素中指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) 和 [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) 元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="a039c-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="a039c-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a039c-135">See Also</span></span>

[<span data-ttu-id="a039c-136">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-136">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="a039c-137">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-137">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="a039c-138">LeftIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-138">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="a039c-139">RightIndent Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a039c-139">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="a039c-140">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="a039c-140">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="a039c-141">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a039c-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
