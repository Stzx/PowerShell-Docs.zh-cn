---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)
description: ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665125"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="205bc-103">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="205bc-103">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="205bc-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="205bc-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="205bc-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="205bc-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="205bc-106">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="205bc-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="205bc-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 CustomControl 的元素 (CustomEntry 的 CustomEntries 元素 CustomEntry for View (Format) ExpressionBinding 元素 for CustomItem for CustomControl for for View (Format) ItemSelectionCondition 元素 for CustomControl for ItemSelectionCondition for CustomControl for view (格式) ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="205bc-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="205bc-108">语法</span><span class="sxs-lookup"><span data-stu-id="205bc-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="205bc-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="205bc-109">Attributes and Elements</span></span>

<span data-ttu-id="205bc-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="205bc-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="205bc-111">特性</span><span class="sxs-lookup"><span data-stu-id="205bc-111">Attributes</span></span>

<span data-ttu-id="205bc-112">无。</span><span class="sxs-lookup"><span data-stu-id="205bc-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="205bc-113">子元素</span><span class="sxs-lookup"><span data-stu-id="205bc-113">Child Elements</span></span>

<span data-ttu-id="205bc-114">无。</span><span class="sxs-lookup"><span data-stu-id="205bc-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="205bc-115">父元素</span><span class="sxs-lookup"><span data-stu-id="205bc-115">Parent Elements</span></span>

|<span data-ttu-id="205bc-116">元素</span><span class="sxs-lookup"><span data-stu-id="205bc-116">Element</span></span>|<span data-ttu-id="205bc-117">描述</span><span class="sxs-lookup"><span data-stu-id="205bc-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="205bc-118">CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="205bc-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="205bc-119">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="205bc-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="205bc-120">文本值</span><span class="sxs-lookup"><span data-stu-id="205bc-120">Text Value</span></span>

<span data-ttu-id="205bc-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="205bc-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="205bc-122">备注</span><span class="sxs-lookup"><span data-stu-id="205bc-122">Remarks</span></span>

<span data-ttu-id="205bc-123">如果使用此元素，则在定义选择条件时，不能指定 [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="205bc-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="205bc-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="205bc-124">See Also</span></span>

[<span data-ttu-id="205bc-125">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="205bc-125">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="205bc-126">CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="205bc-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="205bc-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="205bc-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
