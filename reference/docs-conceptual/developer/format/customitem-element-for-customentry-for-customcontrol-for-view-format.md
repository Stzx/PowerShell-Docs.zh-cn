---
title: 用于 CustomControl for View (Format) 的 CustomEntry 的 CustomItem 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 25101c9c156ef91657f51db7044bf9a6653142a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785823"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="861d4-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="861d4-103">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="861d4-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="861d4-104">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="861d4-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="861d4-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) CustomItem 的 CustomEntry 元素 (</span><span class="sxs-lookup"><span data-stu-id="861d4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="861d4-106">语法</span><span class="sxs-lookup"><span data-stu-id="861d4-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="861d4-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="861d4-107">Attributes and Elements</span></span>

<span data-ttu-id="861d4-108">以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。</span><span class="sxs-lookup"><span data-stu-id="861d4-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="861d4-109">特性</span><span class="sxs-lookup"><span data-stu-id="861d4-109">Attributes</span></span>

<span data-ttu-id="861d4-110">无。</span><span class="sxs-lookup"><span data-stu-id="861d4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="861d4-111">子元素</span><span class="sxs-lookup"><span data-stu-id="861d4-111">Child Elements</span></span>

|<span data-ttu-id="861d4-112">元素</span><span class="sxs-lookup"><span data-stu-id="861d4-112">Element</span></span>|<span data-ttu-id="861d4-113">描述</span><span class="sxs-lookup"><span data-stu-id="861d4-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="861d4-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="861d4-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="861d4-115">Optional element.</span></span><br /><br /> <span data-ttu-id="861d4-116">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="861d4-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="861d4-117">Frame Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="861d4-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="861d4-118">Optional element.</span></span><br /><br /> <span data-ttu-id="861d4-119">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="861d4-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="861d4-120">用于视图 (格式的自定义控件的 CustomItem 的换行符元素) </span><span class="sxs-lookup"><span data-stu-id="861d4-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="861d4-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="861d4-121">Optional element.</span></span><br /><br /> <span data-ttu-id="861d4-122">向控件的显示添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="861d4-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="861d4-123">用于 View (格式的 CustomControl 的 CustomItem 的文本元素) </span><span class="sxs-lookup"><span data-stu-id="861d4-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="861d4-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="861d4-124">Optional element.</span></span><br /><br /> <span data-ttu-id="861d4-125">指定由控件显示的数据的附加文本。</span><span class="sxs-lookup"><span data-stu-id="861d4-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="861d4-126">父元素</span><span class="sxs-lookup"><span data-stu-id="861d4-126">Parent Elements</span></span>

|<span data-ttu-id="861d4-127">元素</span><span class="sxs-lookup"><span data-stu-id="861d4-127">Element</span></span>|<span data-ttu-id="861d4-128">描述</span><span class="sxs-lookup"><span data-stu-id="861d4-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="861d4-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="861d4-130">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="861d4-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="861d4-131">备注</span><span class="sxs-lookup"><span data-stu-id="861d4-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="861d4-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="861d4-132">See Also</span></span>

[<span data-ttu-id="861d4-133">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="861d4-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861d4-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861d4-135">Frame Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861d4-136">NewLine Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="861d4-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861d4-137">用于 View (格式的 CustomControl 的 CustomItem 的文本元素) </span><span class="sxs-lookup"><span data-stu-id="861d4-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="861d4-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="861d4-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
