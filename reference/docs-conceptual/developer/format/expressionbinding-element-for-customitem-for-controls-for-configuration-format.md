---
title: 用于) 配置 (格式的控件的 CustomItem 的 ExpressionBinding 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1ad83fa9d915822eaefb490658f8a219defdddf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773906"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="170f0-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="170f0-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="170f0-103">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="170f0-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="170f0-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="170f0-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="170f0-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的的 CustomEntry 元素 (CustomControl 的元素 for CustomItem 的控件 CustomEntry 的控件) </span><span class="sxs-lookup"><span data-stu-id="170f0-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="170f0-106">语法</span><span class="sxs-lookup"><span data-stu-id="170f0-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="170f0-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="170f0-107">Attributes and Elements</span></span>

<span data-ttu-id="170f0-108">以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="170f0-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="170f0-109">特性</span><span class="sxs-lookup"><span data-stu-id="170f0-109">Attributes</span></span>

<span data-ttu-id="170f0-110">无。</span><span class="sxs-lookup"><span data-stu-id="170f0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="170f0-111">子元素</span><span class="sxs-lookup"><span data-stu-id="170f0-111">Child Elements</span></span>

|<span data-ttu-id="170f0-112">元素</span><span class="sxs-lookup"><span data-stu-id="170f0-112">Element</span></span>|<span data-ttu-id="170f0-113">说明</span><span class="sxs-lookup"><span data-stu-id="170f0-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="170f0-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-114">Optional element.</span></span><br /><br /> <span data-ttu-id="170f0-115">定义此控件使用的控件。</span><span class="sxs-lookup"><span data-stu-id="170f0-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="170f0-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="170f0-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="170f0-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-117">Optional element.</span></span><br /><br /> <span data-ttu-id="170f0-118">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="170f0-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="170f0-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="170f0-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="170f0-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-120">Optional element.</span></span><br /><br /> <span data-ttu-id="170f0-121">指定控件所显示的集合元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="170f0-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="170f0-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="170f0-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-123">Optional element.</span></span><br /><br /> <span data-ttu-id="170f0-124">定义要使用此公共控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="170f0-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="170f0-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="170f0-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="170f0-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-126">Optional element.</span></span><br /><br /> <span data-ttu-id="170f0-127">指定 .NET 属性，其值由公共控件显示。</span><span class="sxs-lookup"><span data-stu-id="170f0-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="170f0-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="170f0-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="170f0-129">可选元素。</span><span class="sxs-lookup"><span data-stu-id="170f0-129">Optional element.</span></span><br /><br /> <span data-ttu-id="170f0-130">指定其值由公共控件显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="170f0-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="170f0-131">父元素</span><span class="sxs-lookup"><span data-stu-id="170f0-131">Parent Elements</span></span>

|<span data-ttu-id="170f0-132">元素</span><span class="sxs-lookup"><span data-stu-id="170f0-132">Element</span></span>|<span data-ttu-id="170f0-133">说明</span><span class="sxs-lookup"><span data-stu-id="170f0-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="170f0-134">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="170f0-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="170f0-135">定义自定义控件视图显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="170f0-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="170f0-136">备注</span><span class="sxs-lookup"><span data-stu-id="170f0-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="170f0-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="170f0-137">See Also</span></span>

[<span data-ttu-id="170f0-138">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="170f0-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="170f0-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="170f0-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
