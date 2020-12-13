---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntries Element for CustomControl for GroupBy (Format)
description: CustomEntries Element for CustomControl for GroupBy (Format)
ms.openlocfilehash: cde59d38b83930cb64a3a0040891783e4ab96723
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666784"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="ea98e-103">CustomEntries Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ea98e-103">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="ea98e-104">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="ea98e-104">Provides the definitions for the control.</span></span> <span data-ttu-id="ea98e-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="ea98e-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ea98e-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomEntries 元素 for 元素 for CustomControl for GroupBy (格式) CustomControl 元素 (</span><span class="sxs-lookup"><span data-stu-id="ea98e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ea98e-107">语法</span><span class="sxs-lookup"><span data-stu-id="ea98e-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea98e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ea98e-108">Attributes and Elements</span></span>

<span data-ttu-id="ea98e-109">以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。</span><span class="sxs-lookup"><span data-stu-id="ea98e-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="ea98e-110">对于可指定的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="ea98e-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea98e-111">特性</span><span class="sxs-lookup"><span data-stu-id="ea98e-111">Attributes</span></span>

<span data-ttu-id="ea98e-112">无。</span><span class="sxs-lookup"><span data-stu-id="ea98e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea98e-113">子元素</span><span class="sxs-lookup"><span data-stu-id="ea98e-113">Child Elements</span></span>

|<span data-ttu-id="ea98e-114">元素</span><span class="sxs-lookup"><span data-stu-id="ea98e-114">Element</span></span>|<span data-ttu-id="ea98e-115">描述</span><span class="sxs-lookup"><span data-stu-id="ea98e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea98e-116">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ea98e-116">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="ea98e-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="ea98e-117">Required element.</span></span><br /><br /> <span data-ttu-id="ea98e-118">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="ea98e-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ea98e-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ea98e-119">Parent Elements</span></span>

|<span data-ttu-id="ea98e-120">元素</span><span class="sxs-lookup"><span data-stu-id="ea98e-120">Element</span></span>|<span data-ttu-id="ea98e-121">描述</span><span class="sxs-lookup"><span data-stu-id="ea98e-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea98e-122">CustomControl Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ea98e-122">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="ea98e-123">定义显示新组的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ea98e-123">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ea98e-124">备注</span><span class="sxs-lookup"><span data-stu-id="ea98e-124">Remarks</span></span>

<span data-ttu-id="ea98e-125">在大多数情况下，控件只有一个定义，该定义是在单个元素中指定的 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="ea98e-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="ea98e-126">但是，如果要使用相同的控件来显示不同的组，则可以提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="ea98e-126">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="ea98e-127">在这些情况下，可以 `CustomEntry` 为组定义元素。</span><span class="sxs-lookup"><span data-stu-id="ea98e-127">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea98e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea98e-128">See Also</span></span>

[<span data-ttu-id="ea98e-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ea98e-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="ea98e-130">CustomControl Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ea98e-130">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="ea98e-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ea98e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
