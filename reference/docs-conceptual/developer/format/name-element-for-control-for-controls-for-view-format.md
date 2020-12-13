---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for Control for Controls for View (Format)
description: Name Element for Control for Controls for View (Format)
ms.openlocfilehash: 52b7170777a35596767c34f2d58106dfa6479567
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666478"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="93e6e-103">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="93e6e-103">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="93e6e-104">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="93e6e-104">Specifies the name of the control.</span></span>

<span data-ttu-id="93e6e-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 控件的控件 (Name 元素) Name 元素用于控件 (格式) </span><span class="sxs-lookup"><span data-stu-id="93e6e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93e6e-106">语法</span><span class="sxs-lookup"><span data-stu-id="93e6e-106">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93e6e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="93e6e-107">Attributes and Elements</span></span>

<span data-ttu-id="93e6e-108">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="93e6e-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93e6e-109">特性</span><span class="sxs-lookup"><span data-stu-id="93e6e-109">Attributes</span></span>

<span data-ttu-id="93e6e-110">无。</span><span class="sxs-lookup"><span data-stu-id="93e6e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93e6e-111">子元素</span><span class="sxs-lookup"><span data-stu-id="93e6e-111">Child Elements</span></span>

<span data-ttu-id="93e6e-112">无。</span><span class="sxs-lookup"><span data-stu-id="93e6e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93e6e-113">父元素</span><span class="sxs-lookup"><span data-stu-id="93e6e-113">Parent Elements</span></span>

|<span data-ttu-id="93e6e-114">元素</span><span class="sxs-lookup"><span data-stu-id="93e6e-114">Element</span></span>|<span data-ttu-id="93e6e-115">描述</span><span class="sxs-lookup"><span data-stu-id="93e6e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93e6e-116">View (格式的控件控件元素) </span><span class="sxs-lookup"><span data-stu-id="93e6e-116">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="93e6e-117">定义可供视图使用的控件以及用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="93e6e-117">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="93e6e-118">文本值</span><span class="sxs-lookup"><span data-stu-id="93e6e-118">Text Value</span></span>

<span data-ttu-id="93e6e-119">指定用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="93e6e-119">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="93e6e-120">备注</span><span class="sxs-lookup"><span data-stu-id="93e6e-120">Remarks</span></span>

<span data-ttu-id="93e6e-121">此处指定的名称可以用在以下元素中以引用此控件。</span><span class="sxs-lookup"><span data-stu-id="93e6e-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="93e6e-122">创建表、列表、宽控件或自定义控件视图时，可通过以下元素指定控件： [view (Format 的 GroupBy 元素) ](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="93e6e-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="93e6e-123">当创建可供视图使用的另一个控件时，可以通过以下元素指定此控件：用于 [控件的 CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="93e6e-123">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="93e6e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93e6e-124">See Also</span></span>

[<span data-ttu-id="93e6e-125">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="93e6e-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="93e6e-126">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="93e6e-126">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="93e6e-127">View (格式的控件控件元素) </span><span class="sxs-lookup"><span data-stu-id="93e6e-127">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="93e6e-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="93e6e-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
