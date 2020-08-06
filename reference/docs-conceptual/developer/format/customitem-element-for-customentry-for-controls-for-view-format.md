---
title: View (Format) 的控件的 CustomEntry 的 CustomItem 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 747ea14e7118be62ebee00e7d80af2dccb5c8353
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785840"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="5c291-102">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="5c291-103">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="5c291-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="5c291-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="5c291-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="5c291-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomControl 元素，用于控件的视图 (格式) CustomEntries 元素 (CustomEntry 的控件) CustomEntries 的控件，用于查看 (格式) CustomItem 元素 (</span><span class="sxs-lookup"><span data-stu-id="5c291-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c291-106">语法</span><span class="sxs-lookup"><span data-stu-id="5c291-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c291-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5c291-107">Attributes and Elements</span></span>

<span data-ttu-id="5c291-108">以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。</span><span class="sxs-lookup"><span data-stu-id="5c291-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="5c291-109">有关详细信息，请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="5c291-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c291-110">特性</span><span class="sxs-lookup"><span data-stu-id="5c291-110">Attributes</span></span>

<span data-ttu-id="5c291-111">无。</span><span class="sxs-lookup"><span data-stu-id="5c291-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c291-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5c291-112">Child Elements</span></span>

|<span data-ttu-id="5c291-113">元素</span><span class="sxs-lookup"><span data-stu-id="5c291-113">Element</span></span>|<span data-ttu-id="5c291-114">描述</span><span class="sxs-lookup"><span data-stu-id="5c291-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c291-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5c291-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="5c291-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5c291-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="5c291-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="5c291-118">Frame Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5c291-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="5c291-119">Optional element.</span></span><br /><br /> <span data-ttu-id="5c291-120">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="5c291-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="5c291-121">NewLine Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5c291-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="5c291-122">Optional element.</span></span><br /><br /> <span data-ttu-id="5c291-123">向控件的显示添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="5c291-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="5c291-124">Text Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5c291-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="5c291-125">Optional element.</span></span><br /><br /> <span data-ttu-id="5c291-126">向控件的显示添加文本，如括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="5c291-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5c291-127">父元素</span><span class="sxs-lookup"><span data-stu-id="5c291-127">Parent Elements</span></span>

|<span data-ttu-id="5c291-128">元素</span><span class="sxs-lookup"><span data-stu-id="5c291-128">Element</span></span>|<span data-ttu-id="5c291-129">描述</span><span class="sxs-lookup"><span data-stu-id="5c291-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c291-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="5c291-131">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="5c291-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5c291-132">备注</span><span class="sxs-lookup"><span data-stu-id="5c291-132">Remarks</span></span>

<span data-ttu-id="5c291-133">指定元素的子元素时 `CustomItem` ，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="5c291-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="5c291-134">必须按以下顺序添加子元素： `ExpressionBinding` 、 `NewLine` 、 `Text` 和 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="5c291-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="5c291-135">您可以指定的序列数量没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="5c291-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="5c291-136">在每个序列中，可使用的元素数没有最大限制 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="5c291-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c291-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c291-137">See Also</span></span>

[<span data-ttu-id="5c291-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5c291-139">Frame Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5c291-140">NewLine Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5c291-141">Text Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c291-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5c291-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="5c291-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
