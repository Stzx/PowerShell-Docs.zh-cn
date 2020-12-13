---
ms.date: 09/13/2016
ms.topic: reference
title: ExpressionBinding Element for CustomItem for CustomControl for View (Format)
description: ExpressionBinding Element for CustomItem for CustomControl for View (Format)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648185"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="9904f-103">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-103">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="9904f-104">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="9904f-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="9904f-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="9904f-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 用于视图 (格式的 CustomEntries 元素) CustomEntry for CustomEntries 的 CustomControl 元素 (CustomControl for CustomItem for CustomEntry 的 CustomControl 元素) ExpressionBinding 元素 for CustomItem for CustomControl for view (format) </span><span class="sxs-lookup"><span data-stu-id="9904f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9904f-107">语法</span><span class="sxs-lookup"><span data-stu-id="9904f-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9904f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9904f-108">Attributes and Elements</span></span>

<span data-ttu-id="9904f-109">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="9904f-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9904f-110">特性</span><span class="sxs-lookup"><span data-stu-id="9904f-110">Attributes</span></span>

<span data-ttu-id="9904f-111">无。</span><span class="sxs-lookup"><span data-stu-id="9904f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9904f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9904f-112">Child Elements</span></span>

|<span data-ttu-id="9904f-113">元素</span><span class="sxs-lookup"><span data-stu-id="9904f-113">Element</span></span>|<span data-ttu-id="9904f-114">描述</span><span class="sxs-lookup"><span data-stu-id="9904f-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="9904f-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9904f-116">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="9904f-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="9904f-117">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-117">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9904f-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9904f-119">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="9904f-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="9904f-120">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-120">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9904f-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="9904f-122">指定显示集合的元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="9904f-123">用于 CustomControl for View (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素 </span><span class="sxs-lookup"><span data-stu-id="9904f-123">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="9904f-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-124">Optional element.</span></span><br /><br /> <span data-ttu-id="9904f-125">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="9904f-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="9904f-126">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-126">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9904f-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-127">Optional element.</span></span><br /><br /> <span data-ttu-id="9904f-128">指定其值由控件显示的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="9904f-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="9904f-129">用于 CustomCustomControl 的 ExpressionBinding 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9904f-129">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9904f-130">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9904f-130">Optional element.</span></span><br /><br /> <span data-ttu-id="9904f-131">指定其值由控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="9904f-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9904f-132">父元素</span><span class="sxs-lookup"><span data-stu-id="9904f-132">Parent Elements</span></span>

|<span data-ttu-id="9904f-133">元素</span><span class="sxs-lookup"><span data-stu-id="9904f-133">Element</span></span>|<span data-ttu-id="9904f-134">描述</span><span class="sxs-lookup"><span data-stu-id="9904f-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9904f-135">CustomItem Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-135">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="9904f-136">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="9904f-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9904f-137">备注</span><span class="sxs-lookup"><span data-stu-id="9904f-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="9904f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9904f-138">See Also</span></span>

[<span data-ttu-id="9904f-139">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-139">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9904f-140">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-140">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9904f-141">用于 CustomControl for View (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素 </span><span class="sxs-lookup"><span data-stu-id="9904f-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="9904f-142">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-142">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9904f-143">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-143">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9904f-144">CustomItem Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9904f-144">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9904f-145">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9904f-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
