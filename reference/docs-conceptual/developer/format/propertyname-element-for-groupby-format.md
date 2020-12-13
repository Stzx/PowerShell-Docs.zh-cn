---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for GroupBy (Format)
description: PropertyName Element for GroupBy (Format)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666138"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="48a43-103">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="48a43-103">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="48a43-104">指定在新组的值发生更改时启动新组的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="48a43-104">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="48a43-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) GroupBy 元素 (groupby) 格式的 PropertyName 元素 (</span><span class="sxs-lookup"><span data-stu-id="48a43-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48a43-106">语法</span><span class="sxs-lookup"><span data-stu-id="48a43-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="48a43-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48a43-107">Attributes and Elements</span></span>

<span data-ttu-id="48a43-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="48a43-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="48a43-109">特性</span><span class="sxs-lookup"><span data-stu-id="48a43-109">Attributes</span></span>

<span data-ttu-id="48a43-110">无。</span><span class="sxs-lookup"><span data-stu-id="48a43-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48a43-111">子元素</span><span class="sxs-lookup"><span data-stu-id="48a43-111">Child Elements</span></span>

<span data-ttu-id="48a43-112">无。</span><span class="sxs-lookup"><span data-stu-id="48a43-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="48a43-113">父元素</span><span class="sxs-lookup"><span data-stu-id="48a43-113">Parent Elements</span></span>

|<span data-ttu-id="48a43-114">元素</span><span class="sxs-lookup"><span data-stu-id="48a43-114">Element</span></span>|<span data-ttu-id="48a43-115">描述</span><span class="sxs-lookup"><span data-stu-id="48a43-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48a43-116">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="48a43-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="48a43-117">定义一组 .NET 对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="48a43-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="48a43-118">文本值</span><span class="sxs-lookup"><span data-stu-id="48a43-118">Text Value</span></span>

<span data-ttu-id="48a43-119">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="48a43-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="48a43-120">备注</span><span class="sxs-lookup"><span data-stu-id="48a43-120">Remarks</span></span>

<span data-ttu-id="48a43-121">每当此属性的值发生更改时，Windows PowerShell 就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="48a43-121">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="48a43-122">如果指定此元素，则不能指定 [ScriptBlock](./scriptblock-element-for-groupby-format.md) 元素来启动新组。</span><span class="sxs-lookup"><span data-stu-id="48a43-122">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="48a43-123">示例</span><span class="sxs-lookup"><span data-stu-id="48a43-123">Example</span></span>

<span data-ttu-id="48a43-124">下面的示例演示如何在属性的值更改时启动新组。</span><span class="sxs-lookup"><span data-stu-id="48a43-124">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="48a43-125">有关包括此元素的完整格式化文件的示例，请参阅 [ (GroupBy) 的宽视图 ](./wide-view-groupby.md)。</span><span class="sxs-lookup"><span data-stu-id="48a43-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48a43-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48a43-126">See Also</span></span>

[<span data-ttu-id="48a43-127">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="48a43-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="48a43-128">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="48a43-128">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="48a43-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="48a43-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
