---
title: 用于) 配置 (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3bfd3efe916b4d88c024de8f959482cab515f777
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781216"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="dce73-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dce73-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="dce73-103">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="dce73-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="dce73-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="dce73-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="dce73-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) CustomEntries 元素，用于 CustomControl 的 for configuration (格式) CustomEntry 元素对于 CustomControl for control for control (format) CustomItem 元素 For CustomEntry for for for for for Control ExpressionBinding control For for Control control For CustomItem for control for control (format) )  (</span><span class="sxs-lookup"><span data-stu-id="dce73-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dce73-106">语法</span><span class="sxs-lookup"><span data-stu-id="dce73-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dce73-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dce73-107">Attributes and Elements</span></span>

<span data-ttu-id="dce73-108">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="dce73-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dce73-109">特性</span><span class="sxs-lookup"><span data-stu-id="dce73-109">Attributes</span></span>

<span data-ttu-id="dce73-110">无。</span><span class="sxs-lookup"><span data-stu-id="dce73-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dce73-111">子元素</span><span class="sxs-lookup"><span data-stu-id="dce73-111">Child Elements</span></span>

|<span data-ttu-id="dce73-112">元素</span><span class="sxs-lookup"><span data-stu-id="dce73-112">Element</span></span>|<span data-ttu-id="dce73-113">说明</span><span class="sxs-lookup"><span data-stu-id="dce73-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dce73-114">用于配置 (格式的控件的 ItemSelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="dce73-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="dce73-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dce73-115">Optional element.</span></span><br /><br /> <span data-ttu-id="dce73-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="dce73-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="dce73-117">用于配置 (格式的控件的 ItemSelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="dce73-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="dce73-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dce73-118">Optional element.</span></span><br /><br /> <span data-ttu-id="dce73-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="dce73-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dce73-120">父元素</span><span class="sxs-lookup"><span data-stu-id="dce73-120">Parent Elements</span></span>

|<span data-ttu-id="dce73-121">元素</span><span class="sxs-lookup"><span data-stu-id="dce73-121">Element</span></span>|<span data-ttu-id="dce73-122">说明</span><span class="sxs-lookup"><span data-stu-id="dce73-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dce73-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dce73-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="dce73-124">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="dce73-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dce73-125">备注</span><span class="sxs-lookup"><span data-stu-id="dce73-125">Remarks</span></span>

<span data-ttu-id="dce73-126">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="dce73-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="dce73-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dce73-127">See Also</span></span>

[<span data-ttu-id="dce73-128">用于配置 (格式的控件的 ItemSelectionCondition 的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="dce73-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="dce73-129">用于配置 (格式的控件的 ItemSelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="dce73-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="dce73-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dce73-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="dce73-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="dce73-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
