---
title: View (Format) 的控件的 ExpressionBinding 的 ItemSelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781199"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="b329a-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="b329a-103">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="b329a-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="b329a-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="b329a-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b329a-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素用于视图 (格式的控件的 CustomEntries) CustomEntry 元素的格式) CustomItem 元素 For CustomEntry 的控件 For view) 格式的控件 (ExpressionBinding 元素 CustomItem 的控件) ItemSelectionCondition ( (</span><span class="sxs-lookup"><span data-stu-id="b329a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b329a-106">语法</span><span class="sxs-lookup"><span data-stu-id="b329a-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b329a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b329a-107">Attributes and Elements</span></span>

<span data-ttu-id="b329a-108">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="b329a-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b329a-109">特性</span><span class="sxs-lookup"><span data-stu-id="b329a-109">Attributes</span></span>

<span data-ttu-id="b329a-110">无。</span><span class="sxs-lookup"><span data-stu-id="b329a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b329a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b329a-111">Child Elements</span></span>

|<span data-ttu-id="b329a-112">元素</span><span class="sxs-lookup"><span data-stu-id="b329a-112">Element</span></span>|<span data-ttu-id="b329a-113">说明</span><span class="sxs-lookup"><span data-stu-id="b329a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b329a-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="b329a-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b329a-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b329a-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="b329a-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="b329a-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="b329a-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b329a-118">Optional element.</span></span><br /><br /> <span data-ttu-id="b329a-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="b329a-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b329a-120">父元素</span><span class="sxs-lookup"><span data-stu-id="b329a-120">Parent Elements</span></span>

|<span data-ttu-id="b329a-121">元素</span><span class="sxs-lookup"><span data-stu-id="b329a-121">Element</span></span>|<span data-ttu-id="b329a-122">说明</span><span class="sxs-lookup"><span data-stu-id="b329a-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b329a-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="b329a-124">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="b329a-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b329a-125">备注</span><span class="sxs-lookup"><span data-stu-id="b329a-125">Remarks</span></span>

<span data-ttu-id="b329a-126">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="b329a-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="b329a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b329a-127">See Also</span></span>

[<span data-ttu-id="b329a-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="b329a-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="b329a-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="b329a-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b329a-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b329a-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
