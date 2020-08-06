---
title: GroupBy (Format) 的 ExpressionBinding 的 CustomControlName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 06e612b25accf81467108ca48500943153efd575
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785993"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="37a3c-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="37a3c-103">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="37a3c-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="37a3c-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="37a3c-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="37a3c-105">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="37a3c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="37a3c-106">语法</span><span class="sxs-lookup"><span data-stu-id="37a3c-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="37a3c-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="37a3c-107">Attributes and Elements</span></span>

<span data-ttu-id="37a3c-108">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="37a3c-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="37a3c-109">特性</span><span class="sxs-lookup"><span data-stu-id="37a3c-109">Attributes</span></span>

<span data-ttu-id="37a3c-110">无。</span><span class="sxs-lookup"><span data-stu-id="37a3c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="37a3c-111">子元素</span><span class="sxs-lookup"><span data-stu-id="37a3c-111">Child Elements</span></span>

<span data-ttu-id="37a3c-112">无。</span><span class="sxs-lookup"><span data-stu-id="37a3c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="37a3c-113">父元素</span><span class="sxs-lookup"><span data-stu-id="37a3c-113">Parent Elements</span></span>

|<span data-ttu-id="37a3c-114">元素</span><span class="sxs-lookup"><span data-stu-id="37a3c-114">Element</span></span>|<span data-ttu-id="37a3c-115">说明</span><span class="sxs-lookup"><span data-stu-id="37a3c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="37a3c-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="37a3c-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="37a3c-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="37a3c-118">文本值</span><span class="sxs-lookup"><span data-stu-id="37a3c-118">Text Value</span></span>

<span data-ttu-id="37a3c-119">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="37a3c-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="37a3c-120">备注</span><span class="sxs-lookup"><span data-stu-id="37a3c-120">Remarks</span></span>

<span data-ttu-id="37a3c-121">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="37a3c-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="37a3c-122">以下元素指定这些控件的名称：</span><span class="sxs-lookup"><span data-stu-id="37a3c-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="37a3c-123">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="37a3c-124">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="37a3c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37a3c-125">See Also</span></span>

[<span data-ttu-id="37a3c-126">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="37a3c-127">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="37a3c-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37a3c-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="37a3c-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="37a3c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
