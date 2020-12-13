---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)
description: ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)
ms.openlocfilehash: 6bd3d386ba64b33a1744fcc9e602cf13404765a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648083"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="a4e77-103">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a4e77-103">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a4e77-104">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a4e77-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="a4e77-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="a4e77-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a4e77-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) CustomEntries 元素，用于 CustomControl 的 for configuration (格式) CustomEntry 元素对于 CustomControl for control for control (format) CustomItem 元素 For CustomEntry for for for for for Control ExpressionBinding control For for Control control For CustomItem for control for control (format) )  (</span><span class="sxs-lookup"><span data-stu-id="a4e77-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4e77-107">语法</span><span class="sxs-lookup"><span data-stu-id="a4e77-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4e77-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a4e77-108">Attributes and Elements</span></span>

<span data-ttu-id="a4e77-109">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="a4e77-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4e77-110">特性</span><span class="sxs-lookup"><span data-stu-id="a4e77-110">Attributes</span></span>

<span data-ttu-id="a4e77-111">无。</span><span class="sxs-lookup"><span data-stu-id="a4e77-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4e77-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a4e77-112">Child Elements</span></span>

|<span data-ttu-id="a4e77-113">元素</span><span class="sxs-lookup"><span data-stu-id="a4e77-113">Element</span></span>|<span data-ttu-id="a4e77-114">描述</span><span class="sxs-lookup"><span data-stu-id="a4e77-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4e77-115">用于配置 (格式的控件的 ItemSelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="a4e77-115">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a4e77-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a4e77-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a4e77-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="a4e77-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a4e77-118">用于配置 (格式的控件的 ItemSelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="a4e77-118">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a4e77-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a4e77-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a4e77-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="a4e77-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a4e77-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a4e77-121">Parent Elements</span></span>

|<span data-ttu-id="a4e77-122">元素</span><span class="sxs-lookup"><span data-stu-id="a4e77-122">Element</span></span>|<span data-ttu-id="a4e77-123">描述</span><span class="sxs-lookup"><span data-stu-id="a4e77-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4e77-124">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a4e77-124">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="a4e77-125">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="a4e77-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a4e77-126">备注</span><span class="sxs-lookup"><span data-stu-id="a4e77-126">Remarks</span></span>

<span data-ttu-id="a4e77-127">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a4e77-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4e77-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4e77-128">See Also</span></span>

[<span data-ttu-id="a4e77-129">用于配置 (格式的控件的 ItemSelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="a4e77-129">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a4e77-130">用于配置 (格式的控件的 ItemSelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="a4e77-130">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a4e77-131">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a4e77-131">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="a4e77-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a4e77-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
