---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)
description: ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)
ms.openlocfilehash: fe366fa31b93e8d69409cc49c3fe2c350d4d06d9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665092"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="0c229-103">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0c229-103">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="0c229-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="0c229-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="0c229-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="0c229-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="0c229-106">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="0c229-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="0c229-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) 的 GroupBy 元素 (的 CustomEntries 元素对于 groupby) 格式 (CustomControl 的元素) CustomEntry 元素 for CustomControl 对于 GroupBy (格式) CustomItem 元素 for CustomEntry for GroupBy (Format) ExpressionBinding 元素 for CustomItem for GroupBy (format) ItemSelectionCondition 元素 for ExpressionBinding for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="0c229-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c229-108">语法</span><span class="sxs-lookup"><span data-stu-id="0c229-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c229-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c229-109">Attributes and Elements</span></span>

<span data-ttu-id="0c229-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="0c229-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c229-111">特性</span><span class="sxs-lookup"><span data-stu-id="0c229-111">Attributes</span></span>

<span data-ttu-id="0c229-112">无。</span><span class="sxs-lookup"><span data-stu-id="0c229-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0c229-113">子元素</span><span class="sxs-lookup"><span data-stu-id="0c229-113">Child Elements</span></span>

<span data-ttu-id="0c229-114">无。</span><span class="sxs-lookup"><span data-stu-id="0c229-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0c229-115">父元素</span><span class="sxs-lookup"><span data-stu-id="0c229-115">Parent Elements</span></span>

|<span data-ttu-id="0c229-116">元素</span><span class="sxs-lookup"><span data-stu-id="0c229-116">Element</span></span>|<span data-ttu-id="0c229-117">描述</span><span class="sxs-lookup"><span data-stu-id="0c229-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c229-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0c229-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="0c229-119">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="0c229-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0c229-120">文本值</span><span class="sxs-lookup"><span data-stu-id="0c229-120">Text Value</span></span>

<span data-ttu-id="0c229-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="0c229-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c229-122">备注</span><span class="sxs-lookup"><span data-stu-id="0c229-122">Remarks</span></span>

<span data-ttu-id="0c229-123">如果使用此元素，则在定义选择条件时，不能指定 [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="0c229-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c229-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c229-124">See Also</span></span>

[<span data-ttu-id="0c229-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0c229-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="0c229-126">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0c229-126">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="0c229-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="0c229-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
