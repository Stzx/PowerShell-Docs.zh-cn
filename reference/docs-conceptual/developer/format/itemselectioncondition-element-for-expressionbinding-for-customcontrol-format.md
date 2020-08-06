---
title: CustomControl (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6a5c66a63c02980b16c2d2d9dd689410c8aec51c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781182"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="85a3d-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="85a3d-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="85a3d-103">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="85a3d-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="85a3d-104">对于可为控件项指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="85a3d-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="85a3d-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="85a3d-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="85a3d-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，适用于 CustomControl for view (格式) CustomEntry 元素 for for view (format) CustomEntries 元素 for CustomItem 的 CustomEntry 元素 for ExpressionBinding 的 CustomItem 元素 (CustomControl 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="85a3d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="85a3d-107">语法</span><span class="sxs-lookup"><span data-stu-id="85a3d-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85a3d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85a3d-108">Attributes and Elements</span></span>

<span data-ttu-id="85a3d-109">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="85a3d-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="85a3d-110">特性</span><span class="sxs-lookup"><span data-stu-id="85a3d-110">Attributes</span></span>

<span data-ttu-id="85a3d-111">无。</span><span class="sxs-lookup"><span data-stu-id="85a3d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="85a3d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="85a3d-112">Child Elements</span></span>

|<span data-ttu-id="85a3d-113">元素</span><span class="sxs-lookup"><span data-stu-id="85a3d-113">Element</span></span>|<span data-ttu-id="85a3d-114">说明</span><span class="sxs-lookup"><span data-stu-id="85a3d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="85a3d-115">用于 View (格式的 CustomControl 的 ItemSelectionCondition 的 PropertyName 元素</span><span class="sxs-lookup"><span data-stu-id="85a3d-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="85a3d-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="85a3d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="85a3d-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="85a3d-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="85a3d-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="85a3d-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="85a3d-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="85a3d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="85a3d-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="85a3d-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="85a3d-121">父元素</span><span class="sxs-lookup"><span data-stu-id="85a3d-121">Parent Elements</span></span>

|<span data-ttu-id="85a3d-122">元素</span><span class="sxs-lookup"><span data-stu-id="85a3d-122">Element</span></span>|<span data-ttu-id="85a3d-123">说明</span><span class="sxs-lookup"><span data-stu-id="85a3d-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="85a3d-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="85a3d-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="85a3d-125">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="85a3d-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="85a3d-126">备注</span><span class="sxs-lookup"><span data-stu-id="85a3d-126">Remarks</span></span>

<span data-ttu-id="85a3d-127">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="85a3d-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="85a3d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85a3d-128">See Also</span></span>

[<span data-ttu-id="85a3d-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="85a3d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="85a3d-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="85a3d-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
