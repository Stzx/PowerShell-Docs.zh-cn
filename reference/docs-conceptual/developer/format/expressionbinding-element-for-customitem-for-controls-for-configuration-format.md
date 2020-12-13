---
ms.date: 09/13/2016
ms.topic: reference
title: ExpressionBinding Element for CustomItem for Controls for Configuration (Format)
description: ExpressionBinding Element for CustomItem for Controls for Configuration (Format)
ms.openlocfilehash: 1abcf2173e18d45839161b4c7e59f1ad238f81a1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655331"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="4a6ff-103">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-103">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4a6ff-104">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="4a6ff-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4a6ff-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的的 CustomEntry 元素 (CustomControl 的元素 for CustomItem 的控件 CustomEntry 的控件) </span><span class="sxs-lookup"><span data-stu-id="4a6ff-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4a6ff-107">语法</span><span class="sxs-lookup"><span data-stu-id="4a6ff-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4a6ff-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-108">Attributes and Elements</span></span>

<span data-ttu-id="4a6ff-109">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4a6ff-110">特性</span><span class="sxs-lookup"><span data-stu-id="4a6ff-110">Attributes</span></span>

<span data-ttu-id="4a6ff-111">无。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4a6ff-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-112">Child Elements</span></span>

|<span data-ttu-id="4a6ff-113">元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-113">Element</span></span>|<span data-ttu-id="4a6ff-114">描述</span><span class="sxs-lookup"><span data-stu-id="4a6ff-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="4a6ff-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4a6ff-116">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="4a6ff-117">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-117">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="4a6ff-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4a6ff-119">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="4a6ff-120">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-120">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="4a6ff-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4a6ff-122">指定控件所显示的集合元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-122">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="4a6ff-123">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-123">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="4a6ff-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4a6ff-125">定义要使用此公共控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-125">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="4a6ff-126">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-126">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="4a6ff-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-127">Optional element.</span></span><br /><br /> <span data-ttu-id="4a6ff-128">指定 .NET 属性，其值由公共控件显示。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-128">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="4a6ff-129">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-129">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="4a6ff-130">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-130">Optional element.</span></span><br /><br /> <span data-ttu-id="4a6ff-131">指定其值由公共控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-131">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4a6ff-132">父元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-132">Parent Elements</span></span>

|<span data-ttu-id="4a6ff-133">元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-133">Element</span></span>|<span data-ttu-id="4a6ff-134">描述</span><span class="sxs-lookup"><span data-stu-id="4a6ff-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4a6ff-135">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-135">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4a6ff-136">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4a6ff-137">备注</span><span class="sxs-lookup"><span data-stu-id="4a6ff-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4a6ff-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6ff-138">See Also</span></span>

[<span data-ttu-id="4a6ff-139">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="4a6ff-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4a6ff-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
