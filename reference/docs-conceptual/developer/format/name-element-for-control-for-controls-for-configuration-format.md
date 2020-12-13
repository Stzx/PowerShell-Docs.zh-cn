---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for Control for Controls for Configuration (Format)
description: Name Element for Control for Controls for Configuration (Format)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666495"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="9264d-103">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9264d-103">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9264d-104">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="9264d-104">Specifies the name of the control.</span></span> <span data-ttu-id="9264d-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="9264d-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9264d-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于配置 (格式的控件的控件) Name 元素 (</span><span class="sxs-lookup"><span data-stu-id="9264d-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9264d-107">语法</span><span class="sxs-lookup"><span data-stu-id="9264d-107">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="9264d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9264d-108">Attributes and Elements</span></span>

<span data-ttu-id="9264d-109">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="9264d-109">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9264d-110">特性</span><span class="sxs-lookup"><span data-stu-id="9264d-110">Attributes</span></span>

<span data-ttu-id="9264d-111">无。</span><span class="sxs-lookup"><span data-stu-id="9264d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9264d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9264d-112">Child Elements</span></span>

<span data-ttu-id="9264d-113">无。</span><span class="sxs-lookup"><span data-stu-id="9264d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9264d-114">父元素</span><span class="sxs-lookup"><span data-stu-id="9264d-114">Parent Elements</span></span>

|<span data-ttu-id="9264d-115">元素</span><span class="sxs-lookup"><span data-stu-id="9264d-115">Element</span></span>|<span data-ttu-id="9264d-116">描述</span><span class="sxs-lookup"><span data-stu-id="9264d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9264d-117">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9264d-117">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="9264d-118">定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。</span><span class="sxs-lookup"><span data-stu-id="9264d-118">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9264d-119">文本值</span><span class="sxs-lookup"><span data-stu-id="9264d-119">Text Value</span></span>

<span data-ttu-id="9264d-120">指定用于引用此控件的名称。</span><span class="sxs-lookup"><span data-stu-id="9264d-120">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="9264d-121">备注</span><span class="sxs-lookup"><span data-stu-id="9264d-121">Remarks</span></span>

<span data-ttu-id="9264d-122">此处指定的名称可以用在以下元素中以引用此控件。</span><span class="sxs-lookup"><span data-stu-id="9264d-122">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="9264d-123">创建表、列表、宽控件或自定义控件视图时，可通过以下元素指定控件： [view (Format 的 GroupBy 元素) ](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="9264d-123">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="9264d-124">创建另一个公共控件时，可以通过以下元素指定此控件：用于 [CustomItem 的 ExpressionBinding 元素用于配置 (格式的控件) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="9264d-124">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="9264d-125">创建可由视图使用的控件时，可以通过以下元素指定此控件：用于 [CustomItem 的控件的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="9264d-125">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="9264d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9264d-126">See Also</span></span>

[<span data-ttu-id="9264d-127">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9264d-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="9264d-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9264d-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="9264d-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9264d-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="9264d-130">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9264d-130">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="9264d-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9264d-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
