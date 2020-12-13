---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)
description: ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648061"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="13e20-103">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-103">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="13e20-104">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="13e20-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="13e20-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="13e20-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="13e20-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素用于视图 (格式的控件的 CustomEntries) CustomEntry 元素的格式) CustomItem 元素 For CustomEntry 的控件 For view) 格式的控件 (ExpressionBinding 元素 CustomItem 的控件) ItemSelectionCondition ( (</span><span class="sxs-lookup"><span data-stu-id="13e20-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13e20-107">语法</span><span class="sxs-lookup"><span data-stu-id="13e20-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13e20-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13e20-108">Attributes and Elements</span></span>

<span data-ttu-id="13e20-109">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="13e20-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="13e20-110">特性</span><span class="sxs-lookup"><span data-stu-id="13e20-110">Attributes</span></span>

<span data-ttu-id="13e20-111">无。</span><span class="sxs-lookup"><span data-stu-id="13e20-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="13e20-112">子元素</span><span class="sxs-lookup"><span data-stu-id="13e20-112">Child Elements</span></span>

|<span data-ttu-id="13e20-113">元素</span><span class="sxs-lookup"><span data-stu-id="13e20-113">Element</span></span>|<span data-ttu-id="13e20-114">描述</span><span class="sxs-lookup"><span data-stu-id="13e20-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13e20-115">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-115">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="13e20-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="13e20-116">Optional element.</span></span><br /><br /> <span data-ttu-id="13e20-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="13e20-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="13e20-118">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-118">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="13e20-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="13e20-119">Optional element.</span></span><br /><br /> <span data-ttu-id="13e20-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="13e20-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="13e20-121">父元素</span><span class="sxs-lookup"><span data-stu-id="13e20-121">Parent Elements</span></span>

|<span data-ttu-id="13e20-122">元素</span><span class="sxs-lookup"><span data-stu-id="13e20-122">Element</span></span>|<span data-ttu-id="13e20-123">描述</span><span class="sxs-lookup"><span data-stu-id="13e20-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13e20-124">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-124">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="13e20-125">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="13e20-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="13e20-126">备注</span><span class="sxs-lookup"><span data-stu-id="13e20-126">Remarks</span></span>

<span data-ttu-id="13e20-127">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="13e20-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="13e20-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13e20-128">See Also</span></span>

[<span data-ttu-id="13e20-129">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-129">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="13e20-130">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-130">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="13e20-131">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e20-131">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="13e20-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="13e20-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
