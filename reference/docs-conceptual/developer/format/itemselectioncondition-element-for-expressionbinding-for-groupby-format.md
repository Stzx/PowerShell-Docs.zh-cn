---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)
description: ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)
ms.openlocfilehash: 92120ace5ed316fbfbf1d51422071c27d5a604cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651991"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="a1e93-103">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a1e93-103">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="a1e93-104">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a1e93-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="a1e93-105">对于可为控件项指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="a1e93-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="a1e93-106">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="a1e93-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="a1e93-107">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="a1e93-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a1e93-108">语法</span><span class="sxs-lookup"><span data-stu-id="a1e93-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a1e93-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1e93-109">Attributes and Elements</span></span>

<span data-ttu-id="a1e93-110">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="a1e93-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1e93-111">特性</span><span class="sxs-lookup"><span data-stu-id="a1e93-111">Attributes</span></span>

<span data-ttu-id="a1e93-112">无。</span><span class="sxs-lookup"><span data-stu-id="a1e93-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a1e93-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a1e93-113">Child Elements</span></span>

|<span data-ttu-id="a1e93-114">元素</span><span class="sxs-lookup"><span data-stu-id="a1e93-114">Element</span></span>|<span data-ttu-id="a1e93-115">描述</span><span class="sxs-lookup"><span data-stu-id="a1e93-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1e93-116">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a1e93-116">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="a1e93-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a1e93-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a1e93-118">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="a1e93-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a1e93-119">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a1e93-119">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="a1e93-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a1e93-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a1e93-121">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="a1e93-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a1e93-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a1e93-122">Parent Elements</span></span>

|<span data-ttu-id="a1e93-123">元素</span><span class="sxs-lookup"><span data-stu-id="a1e93-123">Element</span></span>|<span data-ttu-id="a1e93-124">描述</span><span class="sxs-lookup"><span data-stu-id="a1e93-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1e93-125">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a1e93-125">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="a1e93-126">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="a1e93-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a1e93-127">备注</span><span class="sxs-lookup"><span data-stu-id="a1e93-127">Remarks</span></span>

<span data-ttu-id="a1e93-128">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a1e93-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1e93-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1e93-129">See Also</span></span>

[<span data-ttu-id="a1e93-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a1e93-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="a1e93-131">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a1e93-131">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
