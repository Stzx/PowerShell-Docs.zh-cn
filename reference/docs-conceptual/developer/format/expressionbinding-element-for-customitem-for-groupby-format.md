---
title: GroupBy (Format) 的 CustomItem 的 ExpressionBinding 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5b0017e487aab4ffcbf901cd44aad9b275b22832
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773719"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="6f480-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="6f480-103">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="6f480-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="6f480-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="6f480-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6f480-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="6f480-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6f480-106">语法</span><span class="sxs-lookup"><span data-stu-id="6f480-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="6f480-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f480-107">Attributes and Elements</span></span>

<span data-ttu-id="6f480-108">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="6f480-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f480-109">特性</span><span class="sxs-lookup"><span data-stu-id="6f480-109">Attributes</span></span>

<span data-ttu-id="6f480-110">无。</span><span class="sxs-lookup"><span data-stu-id="6f480-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6f480-111">子元素</span><span class="sxs-lookup"><span data-stu-id="6f480-111">Child Elements</span></span>

|<span data-ttu-id="6f480-112">元素</span><span class="sxs-lookup"><span data-stu-id="6f480-112">Element</span></span>|<span data-ttu-id="6f480-113">说明</span><span class="sxs-lookup"><span data-stu-id="6f480-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="6f480-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-114">Optional element.</span></span><br /><br /> <span data-ttu-id="6f480-115">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="6f480-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="6f480-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="6f480-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-117">Optional element.</span></span><br /><br /> <span data-ttu-id="6f480-118">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="6f480-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="6f480-119">[GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) ](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) </span><span class="sxs-lookup"><span data-stu-id="6f480-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="6f480-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-120">Optional element.</span></span><br /><br /> <span data-ttu-id="6f480-121">指定显示集合的元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="6f480-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="6f480-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-123">Optional element.</span></span><br /><br /> <span data-ttu-id="6f480-124">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="6f480-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="6f480-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="6f480-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-126">Optional element.</span></span><br /><br /> <span data-ttu-id="6f480-127">指定其值由控件显示的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="6f480-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="6f480-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="6f480-129">可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f480-129">Optional element.</span></span><br /><br /> <span data-ttu-id="6f480-130">指定其值由控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="6f480-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6f480-131">父元素</span><span class="sxs-lookup"><span data-stu-id="6f480-131">Parent Elements</span></span>

|<span data-ttu-id="6f480-132">元素</span><span class="sxs-lookup"><span data-stu-id="6f480-132">Element</span></span>|<span data-ttu-id="6f480-133">说明</span><span class="sxs-lookup"><span data-stu-id="6f480-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6f480-134">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="6f480-135">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="6f480-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6f480-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f480-136">See Also</span></span>

[<span data-ttu-id="6f480-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6f480-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6f480-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6f480-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6f480-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6f480-142">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f480-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="6f480-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="6f480-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
