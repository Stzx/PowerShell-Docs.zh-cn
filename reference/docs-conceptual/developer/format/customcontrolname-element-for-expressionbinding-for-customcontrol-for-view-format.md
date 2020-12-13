---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControlName Element for ExpressionBinding for CustomControl for View (Format)
description: CustomControlName Element for ExpressionBinding for CustomControl for View (Format)
ms.openlocfilehash: 24b27428c07d7178f0069f6d0e5b7ffc555efe34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666801"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="486ea-103">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="486ea-103">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="486ea-104">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="486ea-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="486ea-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="486ea-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="486ea-106">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) 用于视图 (格式的 CustomEntries 元素) CustomEntry 的 CustomControl 的元素 (CustomEntries 的 CustomItem 的 CustomEntry 元素) ExpressionBinding 元素 for CustomItem 的 CustomControlName 元素 (CustomItem) 格式的元素 (</span><span class="sxs-lookup"><span data-stu-id="486ea-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="486ea-107">语法</span><span class="sxs-lookup"><span data-stu-id="486ea-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="486ea-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="486ea-108">Attributes and Elements</span></span>

<span data-ttu-id="486ea-109">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="486ea-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="486ea-110">特性</span><span class="sxs-lookup"><span data-stu-id="486ea-110">Attributes</span></span>

<span data-ttu-id="486ea-111">无。</span><span class="sxs-lookup"><span data-stu-id="486ea-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="486ea-112">子元素</span><span class="sxs-lookup"><span data-stu-id="486ea-112">Child Elements</span></span>

<span data-ttu-id="486ea-113">无。</span><span class="sxs-lookup"><span data-stu-id="486ea-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="486ea-114">父元素</span><span class="sxs-lookup"><span data-stu-id="486ea-114">Parent Elements</span></span>

|<span data-ttu-id="486ea-115">元素</span><span class="sxs-lookup"><span data-stu-id="486ea-115">Element</span></span>|<span data-ttu-id="486ea-116">描述</span><span class="sxs-lookup"><span data-stu-id="486ea-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="486ea-117">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="486ea-117">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="486ea-118">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="486ea-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="486ea-119">文本值</span><span class="sxs-lookup"><span data-stu-id="486ea-119">Text Value</span></span>

<span data-ttu-id="486ea-120">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="486ea-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="486ea-121">备注</span><span class="sxs-lookup"><span data-stu-id="486ea-121">Remarks</span></span>

<span data-ttu-id="486ea-122">您可以创建可供格式设置文件的所有视图使用的公共控件，并可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="486ea-122">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="486ea-123">以下元素指定这些控件的名称。</span><span class="sxs-lookup"><span data-stu-id="486ea-123">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="486ea-124">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="486ea-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="486ea-125">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="486ea-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="486ea-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="486ea-126">See Also</span></span>

[<span data-ttu-id="486ea-127">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="486ea-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="486ea-128">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="486ea-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="486ea-129">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="486ea-129">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="486ea-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="486ea-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
