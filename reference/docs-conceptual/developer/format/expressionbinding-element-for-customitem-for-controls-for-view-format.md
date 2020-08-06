---
title: View (Format) 的控件的 CustomItem 的 ExpressionBinding 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773804"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="e3653-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="e3653-103">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="e3653-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="e3653-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e3653-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomEntries 元素对于视图 (格式的 CustomControl for view (format) CustomEntry 元素 For CustomEntries For view format 的控件的 CustomItem 元素 (CustomEntry for view) 格式的控件 (ExpressionBinding 元素) ) </span><span class="sxs-lookup"><span data-stu-id="e3653-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3653-106">语法</span><span class="sxs-lookup"><span data-stu-id="e3653-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e3653-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3653-107">Attributes and Elements</span></span>

<span data-ttu-id="e3653-108">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="e3653-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3653-109">特性</span><span class="sxs-lookup"><span data-stu-id="e3653-109">Attributes</span></span>

<span data-ttu-id="e3653-110">无。</span><span class="sxs-lookup"><span data-stu-id="e3653-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3653-111">子元素</span><span class="sxs-lookup"><span data-stu-id="e3653-111">Child Elements</span></span>

|<span data-ttu-id="e3653-112">元素</span><span class="sxs-lookup"><span data-stu-id="e3653-112">Element</span></span>|<span data-ttu-id="e3653-113">说明</span><span class="sxs-lookup"><span data-stu-id="e3653-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="e3653-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-114">Optional element.</span></span><br /><br /> <span data-ttu-id="e3653-115">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="e3653-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="e3653-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e3653-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e3653-118">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="e3653-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="e3653-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e3653-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e3653-121">指定显示集合的元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="e3653-122">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="e3653-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e3653-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-123">Optional element.</span></span><br /><br /> <span data-ttu-id="e3653-124">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e3653-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="e3653-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e3653-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-126">Optional element.</span></span><br /><br /> <span data-ttu-id="e3653-127">指定其值由控件显示的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="e3653-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="e3653-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e3653-129">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e3653-129">Optional element.</span></span><br /><br /> <span data-ttu-id="e3653-130">指定其值由控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="e3653-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e3653-131">父元素</span><span class="sxs-lookup"><span data-stu-id="e3653-131">Parent Elements</span></span>

|<span data-ttu-id="e3653-132">元素</span><span class="sxs-lookup"><span data-stu-id="e3653-132">Element</span></span>|<span data-ttu-id="e3653-133">说明</span><span class="sxs-lookup"><span data-stu-id="e3653-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3653-134">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="e3653-135">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="e3653-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3653-136">备注</span><span class="sxs-lookup"><span data-stu-id="e3653-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e3653-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3653-137">See Also</span></span>

[<span data-ttu-id="e3653-138">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="e3653-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e3653-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e3653-141">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="e3653-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e3653-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e3653-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3653-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e3653-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e3653-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
