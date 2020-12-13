---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)
description: ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648044"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="d78b7-103">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d78b7-103">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="d78b7-104">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d78b7-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="d78b7-105">对于可为控件项指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="d78b7-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="d78b7-106">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="d78b7-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="d78b7-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，适用于 CustomControl for view (格式) CustomEntry 元素 for for view (format) CustomEntries 元素 for CustomItem 的 CustomEntry 元素 for ExpressionBinding 的 CustomItem 元素 (CustomControl 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="d78b7-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d78b7-108">语法</span><span class="sxs-lookup"><span data-stu-id="d78b7-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d78b7-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-109">Attributes and Elements</span></span>

<span data-ttu-id="d78b7-110">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="d78b7-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d78b7-111">特性</span><span class="sxs-lookup"><span data-stu-id="d78b7-111">Attributes</span></span>

<span data-ttu-id="d78b7-112">无。</span><span class="sxs-lookup"><span data-stu-id="d78b7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d78b7-113">子元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-113">Child Elements</span></span>

|<span data-ttu-id="d78b7-114">元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-114">Element</span></span>|<span data-ttu-id="d78b7-115">描述</span><span class="sxs-lookup"><span data-stu-id="d78b7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d78b7-116">用于 View (格式的 CustomControl 的 ItemSelectionCondition 的 PropertyName 元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-116">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="d78b7-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="d78b7-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d78b7-118">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="d78b7-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d78b7-119">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="d78b7-119">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="d78b7-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="d78b7-120">Optional element.</span></span><br /><br /> <span data-ttu-id="d78b7-121">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="d78b7-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d78b7-122">父元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-122">Parent Elements</span></span>

|<span data-ttu-id="d78b7-123">元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-123">Element</span></span>|<span data-ttu-id="d78b7-124">描述</span><span class="sxs-lookup"><span data-stu-id="d78b7-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d78b7-125">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="d78b7-125">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="d78b7-126">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="d78b7-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d78b7-127">备注</span><span class="sxs-lookup"><span data-stu-id="d78b7-127">Remarks</span></span>

<span data-ttu-id="d78b7-128">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="d78b7-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="d78b7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d78b7-129">See Also</span></span>

[<span data-ttu-id="d78b7-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d78b7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="d78b7-131">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="d78b7-131">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
