---
ms.date: 09/13/2016
ms.topic: reference
title: CustomItem Element for CustomEntry for Controls for Configuration (Format)
description: CustomItem Element for CustomEntry for Controls for Configuration (Format)
ms.openlocfilehash: 06c399e982b6ac0fba9c11e20c468fe8bef6f694
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666767"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="393d8-103">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-103">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="393d8-104">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="393d8-104">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="393d8-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="393d8-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="393d8-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 元素 for CustomItem 的控件</span><span class="sxs-lookup"><span data-stu-id="393d8-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="393d8-107">语法</span><span class="sxs-lookup"><span data-stu-id="393d8-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="393d8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="393d8-108">Attributes and Elements</span></span>

<span data-ttu-id="393d8-109">以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。</span><span class="sxs-lookup"><span data-stu-id="393d8-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="393d8-110">有关详细信息，请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="393d8-110">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="393d8-111">特性</span><span class="sxs-lookup"><span data-stu-id="393d8-111">Attributes</span></span>

<span data-ttu-id="393d8-112">无。</span><span class="sxs-lookup"><span data-stu-id="393d8-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="393d8-113">子元素</span><span class="sxs-lookup"><span data-stu-id="393d8-113">Child Elements</span></span>

|<span data-ttu-id="393d8-114">元素</span><span class="sxs-lookup"><span data-stu-id="393d8-114">Element</span></span>|<span data-ttu-id="393d8-115">描述</span><span class="sxs-lookup"><span data-stu-id="393d8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="393d8-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="393d8-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="393d8-117">Optional element.</span></span><br /><br /> <span data-ttu-id="393d8-118">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="393d8-118">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="393d8-119">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-119">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="393d8-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="393d8-120">Optional element.</span></span><br /><br /> <span data-ttu-id="393d8-121">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="393d8-121">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="393d8-122">NewLine Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-122">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="393d8-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="393d8-123">Optional element.</span></span><br /><br /> <span data-ttu-id="393d8-124">向控件的显示添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="393d8-124">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="393d8-125">Text Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-125">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="393d8-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="393d8-126">Optional element.</span></span><br /><br /> <span data-ttu-id="393d8-127">向控件的显示添加文本，如括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="393d8-127">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="393d8-128">父元素</span><span class="sxs-lookup"><span data-stu-id="393d8-128">Parent Elements</span></span>

|<span data-ttu-id="393d8-129">元素</span><span class="sxs-lookup"><span data-stu-id="393d8-129">Element</span></span>|<span data-ttu-id="393d8-130">描述</span><span class="sxs-lookup"><span data-stu-id="393d8-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="393d8-131">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-131">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="393d8-132">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="393d8-132">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="393d8-133">备注</span><span class="sxs-lookup"><span data-stu-id="393d8-133">Remarks</span></span>

<span data-ttu-id="393d8-134">指定元素的子元素时 `CustomItem` ，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="393d8-134">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="393d8-135">必须按以下顺序添加子元素： `ExpressionBinding` 、 `NewLine` 、 `Text` 和 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="393d8-135">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="393d8-136">您可以指定的序列数量没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="393d8-136">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="393d8-137">在每个序列中，可使用的元素数没有最大限制 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="393d8-137">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="393d8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="393d8-138">See Also</span></span>

[<span data-ttu-id="393d8-139">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-139">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="393d8-140">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-140">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="393d8-141">NewLine Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-141">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="393d8-142">Text Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="393d8-142">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="393d8-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="393d8-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
