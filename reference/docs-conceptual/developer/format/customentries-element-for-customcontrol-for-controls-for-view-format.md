---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntries Element for CustomControl for Controls for View (Format)
description: CustomEntries Element for CustomControl for Controls for View (Format)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652373"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="b06e6-103">CustomEntries Element for CustomControl for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b06e6-103">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="b06e6-104">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="b06e6-104">Provides the definitions for the control.</span></span> <span data-ttu-id="b06e6-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="b06e6-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b06e6-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="b06e6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b06e6-107">语法</span><span class="sxs-lookup"><span data-stu-id="b06e6-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b06e6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b06e6-108">Attributes and Elements</span></span>

<span data-ttu-id="b06e6-109">以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。</span><span class="sxs-lookup"><span data-stu-id="b06e6-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="b06e6-110">对于可指定的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="b06e6-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="b06e6-111">特性</span><span class="sxs-lookup"><span data-stu-id="b06e6-111">Attributes</span></span>

<span data-ttu-id="b06e6-112">无。</span><span class="sxs-lookup"><span data-stu-id="b06e6-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b06e6-113">子元素</span><span class="sxs-lookup"><span data-stu-id="b06e6-113">Child Elements</span></span>

|<span data-ttu-id="b06e6-114">元素</span><span class="sxs-lookup"><span data-stu-id="b06e6-114">Element</span></span>|<span data-ttu-id="b06e6-115">描述</span><span class="sxs-lookup"><span data-stu-id="b06e6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b06e6-116">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b06e6-116">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="b06e6-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="b06e6-117">Required element.</span></span><br /><br /> <span data-ttu-id="b06e6-118">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="b06e6-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b06e6-119">父元素</span><span class="sxs-lookup"><span data-stu-id="b06e6-119">Parent Elements</span></span>

|<span data-ttu-id="b06e6-120">元素</span><span class="sxs-lookup"><span data-stu-id="b06e6-120">Element</span></span>|<span data-ttu-id="b06e6-121">描述</span><span class="sxs-lookup"><span data-stu-id="b06e6-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b06e6-122">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b06e6-122">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="b06e6-123">定义视图使用的控件。</span><span class="sxs-lookup"><span data-stu-id="b06e6-123">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b06e6-124">备注</span><span class="sxs-lookup"><span data-stu-id="b06e6-124">Remarks</span></span>

<span data-ttu-id="b06e6-125">在大多数情况下，控件只有一个定义，该定义是在单个元素中指定的 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="b06e6-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="b06e6-126">但是，如果您希望使用同一控件显示不同的 .NET 对象，则可以提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="b06e6-126">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="b06e6-127">在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。</span><span class="sxs-lookup"><span data-stu-id="b06e6-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="b06e6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b06e6-128">See Also</span></span>

[<span data-ttu-id="b06e6-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b06e6-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="b06e6-130">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b06e6-130">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="b06e6-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b06e6-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
