---
ms.date: 09/13/2016
ms.topic: reference
title: CustomItem Element for CustomEntry for GroupBy (Format)
description: CustomItem Element for CustomEntry for GroupBy (Format)
ms.openlocfilehash: 5db23ad4dad5bd66ea64b9c6e91b8224a4aa4eca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645988"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="70378-103">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-103">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="70378-104">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="70378-104">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="70378-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="70378-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="70378-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for GroupBy (格式) </span><span class="sxs-lookup"><span data-stu-id="70378-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="70378-107">语法</span><span class="sxs-lookup"><span data-stu-id="70378-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="70378-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="70378-108">Attributes and Elements</span></span>

<span data-ttu-id="70378-109">以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。</span><span class="sxs-lookup"><span data-stu-id="70378-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="70378-110">特性</span><span class="sxs-lookup"><span data-stu-id="70378-110">Attributes</span></span>

<span data-ttu-id="70378-111">无。</span><span class="sxs-lookup"><span data-stu-id="70378-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="70378-112">子元素</span><span class="sxs-lookup"><span data-stu-id="70378-112">Child Elements</span></span>

|<span data-ttu-id="70378-113">元素</span><span class="sxs-lookup"><span data-stu-id="70378-113">Element</span></span>|<span data-ttu-id="70378-114">描述</span><span class="sxs-lookup"><span data-stu-id="70378-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70378-115">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-115">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="70378-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="70378-116">Optional element.</span></span><br /><br /> <span data-ttu-id="70378-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="70378-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="70378-118">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-118">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="70378-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="70378-119">Optional element.</span></span><br /><br /> <span data-ttu-id="70378-120">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="70378-120">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="70378-121">NewLine Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-121">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="70378-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="70378-122">Optional element.</span></span><br /><br /> <span data-ttu-id="70378-123">向控件的显示添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="70378-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="70378-124">Text Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-124">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="70378-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="70378-125">Optional element.</span></span><br /><br /> <span data-ttu-id="70378-126">指定由控件显示的数据的附加文本。</span><span class="sxs-lookup"><span data-stu-id="70378-126">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="70378-127">父元素</span><span class="sxs-lookup"><span data-stu-id="70378-127">Parent Elements</span></span>

|<span data-ttu-id="70378-128">元素</span><span class="sxs-lookup"><span data-stu-id="70378-128">Element</span></span>|<span data-ttu-id="70378-129">描述</span><span class="sxs-lookup"><span data-stu-id="70378-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70378-130">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-130">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="70378-131">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="70378-131">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="70378-132">备注</span><span class="sxs-lookup"><span data-stu-id="70378-132">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="70378-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70378-133">See Also</span></span>

[<span data-ttu-id="70378-134">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-134">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="70378-135">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-135">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="70378-136">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-136">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="70378-137">NewLine Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-137">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="70378-138">Text Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="70378-138">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="70378-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="70378-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
