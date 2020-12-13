---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)
description: ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)
ms.openlocfilehash: c005215f7b7984541806d2f5de47372d536787ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665198"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="1eaaf-103">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="1eaaf-103">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="1eaaf-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="1eaaf-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="1eaaf-106">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="1eaaf-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) CustomEntry 的 CustomEntries 元素对于视图 (格式的控件) 用于视图 (格式的控件的 CustomEntry 的控件) ExpressionBinding 元素，用于视图 (格式的 CustomItem 的控件的控件) ItemSelectionCondition 的控件 (的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="1eaaf-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1eaaf-108">语法</span><span class="sxs-lookup"><span data-stu-id="1eaaf-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1eaaf-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1eaaf-109">Attributes and Elements</span></span>

<span data-ttu-id="1eaaf-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1eaaf-111">特性</span><span class="sxs-lookup"><span data-stu-id="1eaaf-111">Attributes</span></span>

<span data-ttu-id="1eaaf-112">无。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1eaaf-113">子元素</span><span class="sxs-lookup"><span data-stu-id="1eaaf-113">Child Elements</span></span>

<span data-ttu-id="1eaaf-114">无。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1eaaf-115">父元素</span><span class="sxs-lookup"><span data-stu-id="1eaaf-115">Parent Elements</span></span>

|<span data-ttu-id="1eaaf-116">元素</span><span class="sxs-lookup"><span data-stu-id="1eaaf-116">Element</span></span>|<span data-ttu-id="1eaaf-117">描述</span><span class="sxs-lookup"><span data-stu-id="1eaaf-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1eaaf-118">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="1eaaf-118">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="1eaaf-119">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1eaaf-120">文本值</span><span class="sxs-lookup"><span data-stu-id="1eaaf-120">Text Value</span></span>

<span data-ttu-id="1eaaf-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="1eaaf-122">备注</span><span class="sxs-lookup"><span data-stu-id="1eaaf-122">Remarks</span></span>

<span data-ttu-id="1eaaf-123">如果使用此元素，则在定义选择条件时，不能指定 [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="1eaaf-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="1eaaf-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eaaf-124">See Also</span></span>

[<span data-ttu-id="1eaaf-125">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="1eaaf-125">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="1eaaf-126">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="1eaaf-126">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="1eaaf-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1eaaf-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
