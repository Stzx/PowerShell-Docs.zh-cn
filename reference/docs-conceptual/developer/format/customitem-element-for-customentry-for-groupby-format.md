---
title: GroupBy (Format) 的 CustomEntry 的 CustomItem 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783715"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="7b64b-102">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="7b64b-103">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="7b64b-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="7b64b-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="7b64b-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="7b64b-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for GroupBy (格式) </span><span class="sxs-lookup"><span data-stu-id="7b64b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7b64b-106">语法</span><span class="sxs-lookup"><span data-stu-id="7b64b-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7b64b-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7b64b-107">Attributes and Elements</span></span>

<span data-ttu-id="7b64b-108">以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。</span><span class="sxs-lookup"><span data-stu-id="7b64b-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b64b-109">特性</span><span class="sxs-lookup"><span data-stu-id="7b64b-109">Attributes</span></span>

<span data-ttu-id="7b64b-110">无。</span><span class="sxs-lookup"><span data-stu-id="7b64b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7b64b-111">子元素</span><span class="sxs-lookup"><span data-stu-id="7b64b-111">Child Elements</span></span>

|<span data-ttu-id="7b64b-112">元素</span><span class="sxs-lookup"><span data-stu-id="7b64b-112">Element</span></span>|<span data-ttu-id="7b64b-113">描述</span><span class="sxs-lookup"><span data-stu-id="7b64b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7b64b-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="7b64b-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7b64b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="7b64b-116">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="7b64b-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="7b64b-117">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="7b64b-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7b64b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="7b64b-119">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="7b64b-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="7b64b-120">NewLine Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="7b64b-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7b64b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="7b64b-122">向控件的显示添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="7b64b-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="7b64b-123">Text Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="7b64b-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7b64b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="7b64b-125">指定由控件显示的数据的附加文本。</span><span class="sxs-lookup"><span data-stu-id="7b64b-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7b64b-126">父元素</span><span class="sxs-lookup"><span data-stu-id="7b64b-126">Parent Elements</span></span>

|<span data-ttu-id="7b64b-127">元素</span><span class="sxs-lookup"><span data-stu-id="7b64b-127">Element</span></span>|<span data-ttu-id="7b64b-128">描述</span><span class="sxs-lookup"><span data-stu-id="7b64b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7b64b-129">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="7b64b-130">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="7b64b-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7b64b-131">备注</span><span class="sxs-lookup"><span data-stu-id="7b64b-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="7b64b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b64b-132">See Also</span></span>

[<span data-ttu-id="7b64b-133">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="7b64b-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="7b64b-135">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="7b64b-136">NewLine Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="7b64b-137">Text Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7b64b-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="7b64b-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7b64b-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
