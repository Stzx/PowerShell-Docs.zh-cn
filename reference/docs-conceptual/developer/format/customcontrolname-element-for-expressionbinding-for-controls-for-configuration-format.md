---
title: 用于) 配置 (格式的控件的 ExpressionBinding 的 CustomControlName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 690b6ae01b8116b72fbd00aef574feda1fd737b0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786027"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="4ab62-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4ab62-103">指定公共控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4ab62-103">Specifies the name of a common control.</span></span> <span data-ttu-id="4ab62-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="4ab62-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4ab62-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) CustomEntries 元素，用于 CustomControl 的 for configuration (格式) CustomEntry 元素对于 CustomControl for control for control (format) CustomItem 元素 For CustomEntry for for for for for Control ExpressionBinding control For for Control control For CustomItem for control for control (format) )  (</span><span class="sxs-lookup"><span data-stu-id="4ab62-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4ab62-106">语法</span><span class="sxs-lookup"><span data-stu-id="4ab62-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4ab62-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4ab62-107">Attributes and Elements</span></span>

<span data-ttu-id="4ab62-108">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="4ab62-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ab62-109">特性</span><span class="sxs-lookup"><span data-stu-id="4ab62-109">Attributes</span></span>

<span data-ttu-id="4ab62-110">无。</span><span class="sxs-lookup"><span data-stu-id="4ab62-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4ab62-111">子元素</span><span class="sxs-lookup"><span data-stu-id="4ab62-111">Child Elements</span></span>

<span data-ttu-id="4ab62-112">无。</span><span class="sxs-lookup"><span data-stu-id="4ab62-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4ab62-113">父元素</span><span class="sxs-lookup"><span data-stu-id="4ab62-113">Parent Elements</span></span>

|<span data-ttu-id="4ab62-114">元素</span><span class="sxs-lookup"><span data-stu-id="4ab62-114">Element</span></span>|<span data-ttu-id="4ab62-115">说明</span><span class="sxs-lookup"><span data-stu-id="4ab62-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4ab62-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="4ab62-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="4ab62-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4ab62-118">文本值</span><span class="sxs-lookup"><span data-stu-id="4ab62-118">Text Value</span></span>

<span data-ttu-id="4ab62-119">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4ab62-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ab62-120">备注</span><span class="sxs-lookup"><span data-stu-id="4ab62-120">Remarks</span></span>

<span data-ttu-id="4ab62-121">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="4ab62-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="4ab62-122">以下元素指定这些控件的名称：</span><span class="sxs-lookup"><span data-stu-id="4ab62-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="4ab62-123">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="4ab62-124">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="4ab62-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab62-125">See Also</span></span>

[<span data-ttu-id="4ab62-126">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="4ab62-127">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="4ab62-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4ab62-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="4ab62-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4ab62-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
