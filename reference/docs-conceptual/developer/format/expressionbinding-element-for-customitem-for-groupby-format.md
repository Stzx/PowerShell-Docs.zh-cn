---
ms.date: 09/13/2016
ms.topic: reference
title: ExpressionBinding Element for CustomItem for GroupBy (Format)
description: ExpressionBinding Element for CustomItem for GroupBy (Format)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655302"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="e9cc7-103">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-103">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="e9cc7-104">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="e9cc7-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e9cc7-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="e9cc7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9cc7-107">语法</span><span class="sxs-lookup"><span data-stu-id="e9cc7-107">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e9cc7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e9cc7-108">Attributes and Elements</span></span>

<span data-ttu-id="e9cc7-109">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9cc7-110">特性</span><span class="sxs-lookup"><span data-stu-id="e9cc7-110">Attributes</span></span>

<span data-ttu-id="e9cc7-111">无。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9cc7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e9cc7-112">Child Elements</span></span>

|<span data-ttu-id="e9cc7-113">元素</span><span class="sxs-lookup"><span data-stu-id="e9cc7-113">Element</span></span>|<span data-ttu-id="e9cc7-114">描述</span><span class="sxs-lookup"><span data-stu-id="e9cc7-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="e9cc7-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e9cc7-116">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="e9cc7-117">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-117">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="e9cc7-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e9cc7-119">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-119">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="e9cc7-120">[GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) ](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) </span><span class="sxs-lookup"><span data-stu-id="e9cc7-120">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="e9cc7-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e9cc7-122">指定显示集合的元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="e9cc7-123">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-123">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="e9cc7-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e9cc7-125">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="e9cc7-126">PropertyName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-126">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="e9cc7-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-127">Optional element.</span></span><br /><br /> <span data-ttu-id="e9cc7-128">指定其值由控件显示的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="e9cc7-129">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-129">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="e9cc7-130">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-130">Optional element.</span></span><br /><br /> <span data-ttu-id="e9cc7-131">指定其值由控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e9cc7-132">父元素</span><span class="sxs-lookup"><span data-stu-id="e9cc7-132">Parent Elements</span></span>

|<span data-ttu-id="e9cc7-133">元素</span><span class="sxs-lookup"><span data-stu-id="e9cc7-133">Element</span></span>|<span data-ttu-id="e9cc7-134">描述</span><span class="sxs-lookup"><span data-stu-id="e9cc7-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9cc7-135">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-135">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e9cc7-136">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="e9cc7-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e9cc7-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9cc7-137">See Also</span></span>

[<span data-ttu-id="e9cc7-138">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-138">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e9cc7-139">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-139">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e9cc7-140">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-140">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e9cc7-141">PropertyName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-141">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e9cc7-142">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-142">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e9cc7-143">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9cc7-143">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e9cc7-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e9cc7-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
