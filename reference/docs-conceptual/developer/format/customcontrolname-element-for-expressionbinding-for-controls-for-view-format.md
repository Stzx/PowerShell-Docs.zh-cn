---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControlName Element for ExpressionBinding for Controls for View (Format)
description: CustomControlName Element for ExpressionBinding for Controls for View (Format)
ms.openlocfilehash: 35e1554a9eed491f37499a7455e9c5cae3cd9e1e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655449"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="de9b6-103">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-103">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="de9b6-104">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="de9b6-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="de9b6-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="de9b6-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="de9b6-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素用于视图 (格式的控件的 CustomEntries) CustomEntry 元素的格式) CustomItem 元素 For CustomEntry 的控件 For view) 格式的控件 (ExpressionBinding 元素) CustomItem 元素 For CustomControlName 的控件 (ExpressionBindine)  (</span><span class="sxs-lookup"><span data-stu-id="de9b6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="de9b6-107">语法</span><span class="sxs-lookup"><span data-stu-id="de9b6-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="de9b6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de9b6-108">Attributes and Elements</span></span>

<span data-ttu-id="de9b6-109">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="de9b6-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="de9b6-110">特性</span><span class="sxs-lookup"><span data-stu-id="de9b6-110">Attributes</span></span>

<span data-ttu-id="de9b6-111">无。</span><span class="sxs-lookup"><span data-stu-id="de9b6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="de9b6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="de9b6-112">Child Elements</span></span>

<span data-ttu-id="de9b6-113">无。</span><span class="sxs-lookup"><span data-stu-id="de9b6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="de9b6-114">父元素</span><span class="sxs-lookup"><span data-stu-id="de9b6-114">Parent Elements</span></span>

|<span data-ttu-id="de9b6-115">元素</span><span class="sxs-lookup"><span data-stu-id="de9b6-115">Element</span></span>|<span data-ttu-id="de9b6-116">描述</span><span class="sxs-lookup"><span data-stu-id="de9b6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="de9b6-117">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-117">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="de9b6-118">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="de9b6-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="de9b6-119">文本值</span><span class="sxs-lookup"><span data-stu-id="de9b6-119">Text Value</span></span>

<span data-ttu-id="de9b6-120">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="de9b6-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="de9b6-121">备注</span><span class="sxs-lookup"><span data-stu-id="de9b6-121">Remarks</span></span>

<span data-ttu-id="de9b6-122">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="de9b6-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="de9b6-123">以下元素指定这些控件的名称：</span><span class="sxs-lookup"><span data-stu-id="de9b6-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="de9b6-124">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="de9b6-125">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="de9b6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de9b6-126">See Also</span></span>

[<span data-ttu-id="de9b6-127">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="de9b6-128">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="de9b6-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="de9b6-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="de9b6-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="de9b6-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
