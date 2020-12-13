---
ms.date: 09/13/2016
ms.topic: reference
title: ExpressionBinding Element for CustomItem for Controls for View (Format)
description: ExpressionBinding Element for CustomItem for Controls for View (Format)
ms.openlocfilehash: da87bb26d21dcb051871e67997cc3fba7ce73c74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649888"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="e93a5-103">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-103">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="e93a5-104">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="e93a5-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="e93a5-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e93a5-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomEntries 元素对于视图 (格式的 CustomControl for view (format) CustomEntry 元素 For CustomEntries For view format 的控件的 CustomItem 元素 (CustomEntry for view) 格式的控件 (ExpressionBinding 元素) ) </span><span class="sxs-lookup"><span data-stu-id="e93a5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e93a5-107">语法</span><span class="sxs-lookup"><span data-stu-id="e93a5-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e93a5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e93a5-108">Attributes and Elements</span></span>

<span data-ttu-id="e93a5-109">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="e93a5-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e93a5-110">特性</span><span class="sxs-lookup"><span data-stu-id="e93a5-110">Attributes</span></span>

<span data-ttu-id="e93a5-111">无。</span><span class="sxs-lookup"><span data-stu-id="e93a5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e93a5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e93a5-112">Child Elements</span></span>

|<span data-ttu-id="e93a5-113">元素</span><span class="sxs-lookup"><span data-stu-id="e93a5-113">Element</span></span>|<span data-ttu-id="e93a5-114">描述</span><span class="sxs-lookup"><span data-stu-id="e93a5-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="e93a5-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e93a5-116">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="e93a5-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="e93a5-117">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-117">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e93a5-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e93a5-119">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="e93a5-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="e93a5-120">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-120">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e93a5-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e93a5-122">指定显示集合的元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-122">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="e93a5-123">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="e93a5-123">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e93a5-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e93a5-125">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e93a5-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="e93a5-126">PropertyName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-126">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e93a5-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-127">Optional element.</span></span><br /><br /> <span data-ttu-id="e93a5-128">指定其值由控件显示的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="e93a5-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="e93a5-129">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-129">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e93a5-130">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e93a5-130">Optional element.</span></span><br /><br /> <span data-ttu-id="e93a5-131">指定其值由控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="e93a5-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e93a5-132">父元素</span><span class="sxs-lookup"><span data-stu-id="e93a5-132">Parent Elements</span></span>

|<span data-ttu-id="e93a5-133">元素</span><span class="sxs-lookup"><span data-stu-id="e93a5-133">Element</span></span>|<span data-ttu-id="e93a5-134">描述</span><span class="sxs-lookup"><span data-stu-id="e93a5-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e93a5-135">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-135">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="e93a5-136">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="e93a5-136">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e93a5-137">备注</span><span class="sxs-lookup"><span data-stu-id="e93a5-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e93a5-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e93a5-138">See Also</span></span>

[<span data-ttu-id="e93a5-139">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="e93a5-140">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-140">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e93a5-141">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-141">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e93a5-142">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="e93a5-142">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e93a5-143">PropertyName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-143">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e93a5-144">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e93a5-144">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e93a5-145">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e93a5-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
