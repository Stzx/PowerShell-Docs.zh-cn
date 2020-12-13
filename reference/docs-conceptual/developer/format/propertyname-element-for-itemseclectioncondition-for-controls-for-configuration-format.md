---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)
description: PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)
ms.openlocfilehash: 860683eb54b2a3579767640c1d3f0937897b8f8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655129"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="21690-103">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="21690-103">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="21690-104">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="21690-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="21690-105">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="21690-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="21690-106">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="21690-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="21690-107">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for 的 CustomEntry 元素配置 (格式) 的 CustomEntry 的 CustomItem 元素，用于 ExpressionBinding 的元素 for CustomItem for configuration 元素 for for for for Control for for Control for for Control for for Control for control (format 元素 for ItemSelectionCondition for configuration) 格式的控件 ()  (</span><span class="sxs-lookup"><span data-stu-id="21690-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21690-108">语法</span><span class="sxs-lookup"><span data-stu-id="21690-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="21690-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="21690-109">Attributes and Elements</span></span>

<span data-ttu-id="21690-110">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="21690-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="21690-111">特性</span><span class="sxs-lookup"><span data-stu-id="21690-111">Attributes</span></span>

<span data-ttu-id="21690-112">无。</span><span class="sxs-lookup"><span data-stu-id="21690-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21690-113">子元素</span><span class="sxs-lookup"><span data-stu-id="21690-113">Child Elements</span></span>

<span data-ttu-id="21690-114">无。</span><span class="sxs-lookup"><span data-stu-id="21690-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="21690-115">父元素</span><span class="sxs-lookup"><span data-stu-id="21690-115">Parent Elements</span></span>

|<span data-ttu-id="21690-116">元素</span><span class="sxs-lookup"><span data-stu-id="21690-116">Element</span></span>|<span data-ttu-id="21690-117">描述</span><span class="sxs-lookup"><span data-stu-id="21690-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21690-118">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="21690-118">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="21690-119">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="21690-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="21690-120">文本值</span><span class="sxs-lookup"><span data-stu-id="21690-120">Text Value</span></span>

<span data-ttu-id="21690-121">指定触发条件的 .NET 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="21690-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="21690-122">备注</span><span class="sxs-lookup"><span data-stu-id="21690-122">Remarks</span></span>

<span data-ttu-id="21690-123">如果使用此元素，则在定义选择条件时，不能指定 [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="21690-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="21690-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21690-124">See Also</span></span>

[<span data-ttu-id="21690-125">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="21690-125">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="21690-126">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="21690-126">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="21690-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="21690-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
