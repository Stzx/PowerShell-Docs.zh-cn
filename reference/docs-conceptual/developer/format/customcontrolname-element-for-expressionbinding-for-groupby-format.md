---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControlName Element for ExpressionBinding for GroupBy (Format)
description: CustomControlName Element for ExpressionBinding for GroupBy (Format)
ms.openlocfilehash: bb7dbd449137628da1794628c5a7d7e10158dd46
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655439"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="2172f-103">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-103">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="2172f-104">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="2172f-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="2172f-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="2172f-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2172f-106">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="2172f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2172f-107">语法</span><span class="sxs-lookup"><span data-stu-id="2172f-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2172f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2172f-108">Attributes and Elements</span></span>

<span data-ttu-id="2172f-109">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="2172f-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2172f-110">特性</span><span class="sxs-lookup"><span data-stu-id="2172f-110">Attributes</span></span>

<span data-ttu-id="2172f-111">无。</span><span class="sxs-lookup"><span data-stu-id="2172f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2172f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2172f-112">Child Elements</span></span>

<span data-ttu-id="2172f-113">无。</span><span class="sxs-lookup"><span data-stu-id="2172f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2172f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="2172f-114">Parent Elements</span></span>

|<span data-ttu-id="2172f-115">元素</span><span class="sxs-lookup"><span data-stu-id="2172f-115">Element</span></span>|<span data-ttu-id="2172f-116">描述</span><span class="sxs-lookup"><span data-stu-id="2172f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2172f-117">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-117">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="2172f-118">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="2172f-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2172f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="2172f-119">Text Value</span></span>

<span data-ttu-id="2172f-120">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="2172f-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="2172f-121">备注</span><span class="sxs-lookup"><span data-stu-id="2172f-121">Remarks</span></span>

<span data-ttu-id="2172f-122">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="2172f-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="2172f-123">以下元素指定这些控件的名称：</span><span class="sxs-lookup"><span data-stu-id="2172f-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="2172f-124">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="2172f-125">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="2172f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2172f-126">See Also</span></span>

[<span data-ttu-id="2172f-127">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="2172f-128">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="2172f-129">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2172f-129">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="2172f-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="2172f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
