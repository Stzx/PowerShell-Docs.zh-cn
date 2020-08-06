---
title: 用于 CustomControl for View (Format) 的 CustomItem 的 ExpressionBinding 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1885a2820c0cb250aa6fda80544f58d06136cfeb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773787"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="641fe-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="641fe-103">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="641fe-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="641fe-104">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="641fe-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 用于视图 (格式的 CustomEntries 元素) CustomEntry for CustomEntries 的 CustomControl 元素 (CustomControl for CustomItem for CustomEntry 的 CustomControl 元素) ExpressionBinding 元素 for CustomItem for CustomControl for view (format) </span><span class="sxs-lookup"><span data-stu-id="641fe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="641fe-106">语法</span><span class="sxs-lookup"><span data-stu-id="641fe-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="641fe-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="641fe-107">Attributes and Elements</span></span>

<span data-ttu-id="641fe-108">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="641fe-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="641fe-109">特性</span><span class="sxs-lookup"><span data-stu-id="641fe-109">Attributes</span></span>

<span data-ttu-id="641fe-110">无。</span><span class="sxs-lookup"><span data-stu-id="641fe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="641fe-111">子元素</span><span class="sxs-lookup"><span data-stu-id="641fe-111">Child Elements</span></span>

|<span data-ttu-id="641fe-112">元素</span><span class="sxs-lookup"><span data-stu-id="641fe-112">Element</span></span>|<span data-ttu-id="641fe-113">说明</span><span class="sxs-lookup"><span data-stu-id="641fe-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="641fe-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-114">Optional element.</span></span><br /><br /> <span data-ttu-id="641fe-115">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="641fe-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="641fe-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="641fe-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-117">Optional element.</span></span><br /><br /> <span data-ttu-id="641fe-118">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="641fe-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="641fe-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="641fe-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-120">Optional element.</span></span><br /><br /> <span data-ttu-id="641fe-121">指定显示集合的元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="641fe-122">用于 CustomControl for View (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="641fe-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="641fe-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-123">Optional element.</span></span><br /><br /> <span data-ttu-id="641fe-124">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="641fe-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="641fe-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="641fe-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-126">Optional element.</span></span><br /><br /> <span data-ttu-id="641fe-127">指定其值由控件显示的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="641fe-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="641fe-128">用于 CustomCustomControl 的 ExpressionBinding 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="641fe-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="641fe-129">可选元素。</span><span class="sxs-lookup"><span data-stu-id="641fe-129">Optional element.</span></span><br /><br /> <span data-ttu-id="641fe-130">指定其值由控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="641fe-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="641fe-131">父元素</span><span class="sxs-lookup"><span data-stu-id="641fe-131">Parent Elements</span></span>

|<span data-ttu-id="641fe-132">元素</span><span class="sxs-lookup"><span data-stu-id="641fe-132">Element</span></span>|<span data-ttu-id="641fe-133">说明</span><span class="sxs-lookup"><span data-stu-id="641fe-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="641fe-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="641fe-135">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="641fe-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="641fe-136">备注</span><span class="sxs-lookup"><span data-stu-id="641fe-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="641fe-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="641fe-137">See Also</span></span>

[<span data-ttu-id="641fe-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="641fe-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="641fe-140">用于 CustomControl for View (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="641fe-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="641fe-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="641fe-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="641fe-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="641fe-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="641fe-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="641fe-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
