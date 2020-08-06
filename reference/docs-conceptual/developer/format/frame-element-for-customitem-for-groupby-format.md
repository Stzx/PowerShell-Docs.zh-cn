---
title: GroupBy (Format) 的 CustomItem 的框架元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785755"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="1a545-102">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="1a545-103">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="1a545-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="1a545-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="1a545-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1a545-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomControl 元素 for CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem (格式) </span><span class="sxs-lookup"><span data-stu-id="1a545-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1a545-106">语法</span><span class="sxs-lookup"><span data-stu-id="1a545-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1a545-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a545-107">Attributes and Elements</span></span>

<span data-ttu-id="1a545-108">以下各节描述了元素的属性、子元素和父元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="1a545-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1a545-109">特性</span><span class="sxs-lookup"><span data-stu-id="1a545-109">Attributes</span></span>

<span data-ttu-id="1a545-110">无。</span><span class="sxs-lookup"><span data-stu-id="1a545-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1a545-111">子元素</span><span class="sxs-lookup"><span data-stu-id="1a545-111">Child Elements</span></span>

|<span data-ttu-id="1a545-112">元素</span><span class="sxs-lookup"><span data-stu-id="1a545-112">Element</span></span>|<span data-ttu-id="1a545-113">描述</span><span class="sxs-lookup"><span data-stu-id="1a545-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="1a545-114">必需的元素</span><span class="sxs-lookup"><span data-stu-id="1a545-114">Required Element</span></span>|
|[<span data-ttu-id="1a545-115">FirstLineHanging Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="1a545-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1a545-116">Optional element.</span></span><br /><br /> <span data-ttu-id="1a545-117">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="1a545-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="1a545-118">FirstLineIndent Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="1a545-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1a545-119">Optional element.</span></span><br /><br /> <span data-ttu-id="1a545-120">指定第一行数据向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="1a545-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="1a545-121">LeftIndent Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="1a545-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1a545-122">Optional element.</span></span><br /><br /> <span data-ttu-id="1a545-123">指定数据从左边距向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="1a545-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="1a545-124">[GroupBy (格式的帧的 RightIndent 元素) ](./rightindent-element-for-frame-for-groupby-format.md)RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="1a545-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="1a545-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1a545-125">Optional element.</span></span><br /><br /> <span data-ttu-id="1a545-126">指定数据从右边缘向外移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="1a545-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1a545-127">父元素</span><span class="sxs-lookup"><span data-stu-id="1a545-127">Parent Elements</span></span>

|<span data-ttu-id="1a545-128">元素</span><span class="sxs-lookup"><span data-stu-id="1a545-128">Element</span></span>|<span data-ttu-id="1a545-129">描述</span><span class="sxs-lookup"><span data-stu-id="1a545-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1a545-130">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="1a545-131">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="1a545-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1a545-132">备注</span><span class="sxs-lookup"><span data-stu-id="1a545-132">Remarks</span></span>

<span data-ttu-id="1a545-133">不能在同一元素中指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)和[FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md)元素 `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="1a545-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a545-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a545-134">See Also</span></span>

[<span data-ttu-id="1a545-135">FirstLineHanging Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a545-136">FirstLineIndent Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a545-137">LeftIndent Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a545-138">RightIndent Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a545-139">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1a545-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="1a545-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1a545-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
