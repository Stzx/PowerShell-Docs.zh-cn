---
title: 用于控件的 Name 元素 (Format) 的控件 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783528"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="16d15-102">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16d15-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="16d15-103">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="16d15-103">Specifies the name of the control.</span></span> <span data-ttu-id="16d15-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="16d15-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="16d15-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于配置 (格式的控件的控件) Name 元素 (</span><span class="sxs-lookup"><span data-stu-id="16d15-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="16d15-106">语法</span><span class="sxs-lookup"><span data-stu-id="16d15-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="16d15-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="16d15-107">Attributes and Elements</span></span>

<span data-ttu-id="16d15-108">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="16d15-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="16d15-109">特性</span><span class="sxs-lookup"><span data-stu-id="16d15-109">Attributes</span></span>

<span data-ttu-id="16d15-110">无。</span><span class="sxs-lookup"><span data-stu-id="16d15-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16d15-111">子元素</span><span class="sxs-lookup"><span data-stu-id="16d15-111">Child Elements</span></span>

<span data-ttu-id="16d15-112">无。</span><span class="sxs-lookup"><span data-stu-id="16d15-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="16d15-113">父元素</span><span class="sxs-lookup"><span data-stu-id="16d15-113">Parent Elements</span></span>

|<span data-ttu-id="16d15-114">元素</span><span class="sxs-lookup"><span data-stu-id="16d15-114">Element</span></span>|<span data-ttu-id="16d15-115">说明</span><span class="sxs-lookup"><span data-stu-id="16d15-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16d15-116">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16d15-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="16d15-117">定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。</span><span class="sxs-lookup"><span data-stu-id="16d15-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="16d15-118">文本值</span><span class="sxs-lookup"><span data-stu-id="16d15-118">Text Value</span></span>

<span data-ttu-id="16d15-119">指定用于引用此控件的名称。</span><span class="sxs-lookup"><span data-stu-id="16d15-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="16d15-120">备注</span><span class="sxs-lookup"><span data-stu-id="16d15-120">Remarks</span></span>

<span data-ttu-id="16d15-121">此处指定的名称可以用在以下元素中以引用此控件。</span><span class="sxs-lookup"><span data-stu-id="16d15-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="16d15-122">创建表、列表、宽控件或自定义控件视图时，可通过以下元素指定控件： [view (Format 的 GroupBy 元素) ](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="16d15-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="16d15-123">创建另一个公共控件时，可以通过以下元素指定此控件：用于[CustomItem 的 ExpressionBinding 元素用于配置 (格式的控件) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="16d15-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="16d15-124">创建可由视图使用的控件时，可以通过以下元素指定此控件：用于[CustomItem 的控件的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="16d15-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="16d15-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16d15-125">See Also</span></span>

[<span data-ttu-id="16d15-126">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16d15-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="16d15-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16d15-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="16d15-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="16d15-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="16d15-129">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="16d15-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="16d15-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="16d15-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
