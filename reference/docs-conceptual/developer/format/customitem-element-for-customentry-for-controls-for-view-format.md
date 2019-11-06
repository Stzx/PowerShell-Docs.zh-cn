---
title: 用于视图（格式）的 CustomEntry 的 CustomItem 元素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363936"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="3569e-102">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3569e-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="3569e-103">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="3569e-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="3569e-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="3569e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="3569e-105">配置元素（格式） ViewDefinitions 元素（格式） View 元素（format） Controls 元素（format） Control 元素 for View （format） CustomControl 元素的控件元素，用于控件的 View （format） CustomEntries 元素CustomControl for view （Format） CustomEntry 元素 for CustomEntries for view （format） CustomItem 元素 for view （format）元素 for CustomEntry 的控件</span><span class="sxs-lookup"><span data-stu-id="3569e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3569e-106">语法</span><span class="sxs-lookup"><span data-stu-id="3569e-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3569e-107">属性和元素</span><span class="sxs-lookup"><span data-stu-id="3569e-107">Attributes and Elements</span></span>

<span data-ttu-id="3569e-108">以下各节介绍了 `CustomItem` 元素的属性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3569e-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="3569e-109">有关详细信息，请参阅 "备注"。</span><span class="sxs-lookup"><span data-stu-id="3569e-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="3569e-110">属性</span><span class="sxs-lookup"><span data-stu-id="3569e-110">Attributes</span></span>

<span data-ttu-id="3569e-111">无。</span><span class="sxs-lookup"><span data-stu-id="3569e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3569e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3569e-112">Child Elements</span></span>

|<span data-ttu-id="3569e-113">元素</span><span class="sxs-lookup"><span data-stu-id="3569e-113">Element</span></span>|<span data-ttu-id="3569e-114">描述</span><span class="sxs-lookup"><span data-stu-id="3569e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3569e-115">用于视图的控件的 CustomItem 的 ExpressionBinding 元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="3569e-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3569e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="3569e-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="3569e-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="3569e-118">用于视图的控件的 CustomItem 的框架元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="3569e-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3569e-119">Optional element.</span></span><br /><br /> <span data-ttu-id="3569e-120">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="3569e-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="3569e-121">用于视图的控件的 CustomItem 的换行符元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="3569e-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3569e-122">Optional element.</span></span><br /><br /> <span data-ttu-id="3569e-123">向控件的显示添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="3569e-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="3569e-124">用于视图的控件的 CustomItem 的文本元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="3569e-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3569e-125">Optional element.</span></span><br /><br /> <span data-ttu-id="3569e-126">向控件的显示添加文本，如括号或方括号。</span><span class="sxs-lookup"><span data-stu-id="3569e-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3569e-127">父元素</span><span class="sxs-lookup"><span data-stu-id="3569e-127">Parent Elements</span></span>

|<span data-ttu-id="3569e-128">元素</span><span class="sxs-lookup"><span data-stu-id="3569e-128">Element</span></span>|<span data-ttu-id="3569e-129">描述</span><span class="sxs-lookup"><span data-stu-id="3569e-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3569e-130">用于视图的控件的 CustomEntries 的 CustomEntry 元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="3569e-131">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="3569e-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3569e-132">备注</span><span class="sxs-lookup"><span data-stu-id="3569e-132">Remarks</span></span>

<span data-ttu-id="3569e-133">指定 `CustomItem` 元素的子元素时，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="3569e-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="3569e-134">必须按以下顺序添加子元素： `ExpressionBinding`、`NewLine`、`Text` 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="3569e-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="3569e-135">您可以指定的序列数量没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="3569e-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="3569e-136">在每个序列中，可使用的 `ExpressionBinding` 元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="3569e-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="3569e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3569e-137">See Also</span></span>

[<span data-ttu-id="3569e-138">用于视图的控件的 CustomItem 的 ExpressionBinding 元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="3569e-139">用于视图的控件的 CustomItem 的框架元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="3569e-140">用于视图的控件的 CustomItem 的换行符元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="3569e-141">用于视图的控件的 CustomItem 的文本元素（格式）</span><span class="sxs-lookup"><span data-stu-id="3569e-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="3569e-142">编写 PowerShell 格式化文件</span><span class="sxs-lookup"><span data-stu-id="3569e-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)