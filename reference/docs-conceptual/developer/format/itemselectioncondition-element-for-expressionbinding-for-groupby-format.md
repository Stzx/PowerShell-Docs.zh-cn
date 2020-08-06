---
title: GroupBy (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a9b74f1882efc578f7d9ab27b8cd2f8a52833ab8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773430"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="a239e-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a239e-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="a239e-103">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a239e-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="a239e-104">对于可为控件项指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="a239e-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="a239e-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="a239e-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="a239e-106">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="a239e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a239e-107">语法</span><span class="sxs-lookup"><span data-stu-id="a239e-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a239e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a239e-108">Attributes and Elements</span></span>

<span data-ttu-id="a239e-109">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="a239e-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a239e-110">特性</span><span class="sxs-lookup"><span data-stu-id="a239e-110">Attributes</span></span>

<span data-ttu-id="a239e-111">无。</span><span class="sxs-lookup"><span data-stu-id="a239e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a239e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a239e-112">Child Elements</span></span>

|<span data-ttu-id="a239e-113">元素</span><span class="sxs-lookup"><span data-stu-id="a239e-113">Element</span></span>|<span data-ttu-id="a239e-114">说明</span><span class="sxs-lookup"><span data-stu-id="a239e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a239e-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a239e-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="a239e-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a239e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a239e-117">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="a239e-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a239e-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a239e-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="a239e-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a239e-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a239e-120">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="a239e-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a239e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a239e-121">Parent Elements</span></span>

|<span data-ttu-id="a239e-122">元素</span><span class="sxs-lookup"><span data-stu-id="a239e-122">Element</span></span>|<span data-ttu-id="a239e-123">说明</span><span class="sxs-lookup"><span data-stu-id="a239e-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a239e-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a239e-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="a239e-125">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="a239e-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a239e-126">备注</span><span class="sxs-lookup"><span data-stu-id="a239e-126">Remarks</span></span>

<span data-ttu-id="a239e-127">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a239e-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a239e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a239e-128">See Also</span></span>

[<span data-ttu-id="a239e-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a239e-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="a239e-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a239e-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
