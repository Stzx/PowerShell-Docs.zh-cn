---
title: 对于 GroupBy (Format) ，为 ItemSelectionCondition 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f6d671035bfd2ef6323b638fdd951bb020bd6548
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780876"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="fd1f3-102">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fd1f3-102">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="fd1f3-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="fd1f3-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="fd1f3-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="fd1f3-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) 的 GroupBy 元素 (的 CustomEntries 元素对于 groupby) 格式 (CustomControl 的元素) CustomEntry 元素 for CustomControl 对于 GroupBy (格式) CustomItem 元素 for CustomEntry for GroupBy (Format) ExpressionBinding 元素 for CustomItem for groupby (format) ItemSelectionCondition 元素 for ExpressionBinding for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="fd1f3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fd1f3-107">语法</span><span class="sxs-lookup"><span data-stu-id="fd1f3-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fd1f3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fd1f3-108">Attributes and Elements</span></span>

<span data-ttu-id="fd1f3-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fd1f3-110">特性</span><span class="sxs-lookup"><span data-stu-id="fd1f3-110">Attributes</span></span>

<span data-ttu-id="fd1f3-111">无。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fd1f3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fd1f3-112">Child Elements</span></span>

<span data-ttu-id="fd1f3-113">无。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fd1f3-114">父元素</span><span class="sxs-lookup"><span data-stu-id="fd1f3-114">Parent Elements</span></span>

|<span data-ttu-id="fd1f3-115">元素</span><span class="sxs-lookup"><span data-stu-id="fd1f3-115">Element</span></span>|<span data-ttu-id="fd1f3-116">说明</span><span class="sxs-lookup"><span data-stu-id="fd1f3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fd1f3-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fd1f3-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="fd1f3-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fd1f3-119">文本值</span><span class="sxs-lookup"><span data-stu-id="fd1f3-119">Text Value</span></span>

<span data-ttu-id="fd1f3-120">指定触发条件的 .NET 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd1f3-121">备注</span><span class="sxs-lookup"><span data-stu-id="fd1f3-121">Remarks</span></span>

<span data-ttu-id="fd1f3-122">如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="fd1f3-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd1f3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd1f3-123">See Also</span></span>

[<span data-ttu-id="fd1f3-124">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fd1f3-124">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="fd1f3-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fd1f3-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="fd1f3-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="fd1f3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
