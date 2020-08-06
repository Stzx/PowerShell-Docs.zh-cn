---
title: 用于控件 (格式) 的控件的名称元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 109f3a40606dbe82322decf0c69d2367c75175f6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781080"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="23ceb-102">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="23ceb-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="23ceb-103">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="23ceb-103">Specifies the name of the control.</span></span>

<span data-ttu-id="23ceb-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 控件的控件 (Name 元素) Name 元素用于控件 (格式) </span><span class="sxs-lookup"><span data-stu-id="23ceb-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="23ceb-105">语法</span><span class="sxs-lookup"><span data-stu-id="23ceb-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="23ceb-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23ceb-106">Attributes and Elements</span></span>

<span data-ttu-id="23ceb-107">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="23ceb-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="23ceb-108">特性</span><span class="sxs-lookup"><span data-stu-id="23ceb-108">Attributes</span></span>

<span data-ttu-id="23ceb-109">无。</span><span class="sxs-lookup"><span data-stu-id="23ceb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="23ceb-110">子元素</span><span class="sxs-lookup"><span data-stu-id="23ceb-110">Child Elements</span></span>

<span data-ttu-id="23ceb-111">无。</span><span class="sxs-lookup"><span data-stu-id="23ceb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="23ceb-112">父元素</span><span class="sxs-lookup"><span data-stu-id="23ceb-112">Parent Elements</span></span>

|<span data-ttu-id="23ceb-113">元素</span><span class="sxs-lookup"><span data-stu-id="23ceb-113">Element</span></span>|<span data-ttu-id="23ceb-114">说明</span><span class="sxs-lookup"><span data-stu-id="23ceb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="23ceb-115">View (格式的控件控件元素) </span><span class="sxs-lookup"><span data-stu-id="23ceb-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="23ceb-116">定义可供视图使用的控件以及用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="23ceb-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="23ceb-117">文本值</span><span class="sxs-lookup"><span data-stu-id="23ceb-117">Text Value</span></span>

<span data-ttu-id="23ceb-118">指定用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="23ceb-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="23ceb-119">备注</span><span class="sxs-lookup"><span data-stu-id="23ceb-119">Remarks</span></span>

<span data-ttu-id="23ceb-120">此处指定的名称可以用在以下元素中以引用此控件。</span><span class="sxs-lookup"><span data-stu-id="23ceb-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="23ceb-121">创建表、列表、宽控件或自定义控件视图时，可通过以下元素指定控件： [view (Format 的 GroupBy 元素) ](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="23ceb-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="23ceb-122">当创建可供视图使用的另一个控件时，可以通过以下元素指定此控件：用于[控件的 CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="23ceb-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="23ceb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23ceb-123">See Also</span></span>

[<span data-ttu-id="23ceb-124">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="23ceb-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="23ceb-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="23ceb-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="23ceb-126">View (格式的控件控件元素) </span><span class="sxs-lookup"><span data-stu-id="23ceb-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="23ceb-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="23ceb-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
