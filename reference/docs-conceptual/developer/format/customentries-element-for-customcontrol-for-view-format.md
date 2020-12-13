---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntries Element for CustomControl for View (Format)
description: CustomEntries Element for CustomControl for View (Format)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649985"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="fae83-103">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="fae83-103">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="fae83-104">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="fae83-104">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="fae83-105">自定义控件视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="fae83-105">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="fae83-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，CustomControl 的元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="fae83-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fae83-107">语法</span><span class="sxs-lookup"><span data-stu-id="fae83-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fae83-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fae83-108">Attributes and Elements</span></span>

<span data-ttu-id="fae83-109">以下各节描述了元素的属性、子元素和父元素 `CustomControlEntries` 。</span><span class="sxs-lookup"><span data-stu-id="fae83-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="fae83-110">您必须指定一个或多个子元素。</span><span class="sxs-lookup"><span data-stu-id="fae83-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fae83-111">特性</span><span class="sxs-lookup"><span data-stu-id="fae83-111">Attributes</span></span>

<span data-ttu-id="fae83-112">无。</span><span class="sxs-lookup"><span data-stu-id="fae83-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fae83-113">子元素</span><span class="sxs-lookup"><span data-stu-id="fae83-113">Child Elements</span></span>

|<span data-ttu-id="fae83-114">元素</span><span class="sxs-lookup"><span data-stu-id="fae83-114">Element</span></span>|<span data-ttu-id="fae83-115">描述</span><span class="sxs-lookup"><span data-stu-id="fae83-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fae83-116">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="fae83-116">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="fae83-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="fae83-117">Required element.</span></span><br /><br /> <span data-ttu-id="fae83-118">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="fae83-118">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fae83-119">父元素</span><span class="sxs-lookup"><span data-stu-id="fae83-119">Parent Elements</span></span>

|<span data-ttu-id="fae83-120">元素</span><span class="sxs-lookup"><span data-stu-id="fae83-120">Element</span></span>|<span data-ttu-id="fae83-121">描述</span><span class="sxs-lookup"><span data-stu-id="fae83-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fae83-122">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="fae83-122">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="fae83-123">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="fae83-123">Required element.</span></span><br /><br /> <span data-ttu-id="fae83-124">定义视图的自定义控件格式。</span><span class="sxs-lookup"><span data-stu-id="fae83-124">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fae83-125">备注</span><span class="sxs-lookup"><span data-stu-id="fae83-125">Remarks</span></span>

<span data-ttu-id="fae83-126">在大多数情况下，控件只有一个定义，该定义在单个元素中定义 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="fae83-126">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="fae83-127">但是，如果希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="fae83-127">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="fae83-128">在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。</span><span class="sxs-lookup"><span data-stu-id="fae83-128">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="fae83-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fae83-129">See Also</span></span>

[<span data-ttu-id="fae83-130">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="fae83-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="fae83-131">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="fae83-131">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="fae83-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="fae83-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
