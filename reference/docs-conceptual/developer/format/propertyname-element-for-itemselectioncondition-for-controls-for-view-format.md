---
title: View (Format) 的控件的 ItemSelectionCondition 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c6517b8f63e0511ce071926ac3ac39ba82e7ed21
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783477"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="8a346-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="8a346-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="8a346-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="8a346-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8a346-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="8a346-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="8a346-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="8a346-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8a346-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) CustomEntry 的 CustomEntries 元素对于视图 (格式的控件) 用于视图 (格式的控件的 CustomEntry 的控件) ExpressionBinding 元素，适用于视图 (格式的 CustomItem 的控件) ItemSelectionCondition 的控件 (ExpressionBinding 的控件) </span><span class="sxs-lookup"><span data-stu-id="8a346-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a346-107">语法</span><span class="sxs-lookup"><span data-stu-id="8a346-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a346-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8a346-108">Attributes and Elements</span></span>

<span data-ttu-id="8a346-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="8a346-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a346-110">特性</span><span class="sxs-lookup"><span data-stu-id="8a346-110">Attributes</span></span>

<span data-ttu-id="8a346-111">无。</span><span class="sxs-lookup"><span data-stu-id="8a346-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a346-112">子元素</span><span class="sxs-lookup"><span data-stu-id="8a346-112">Child Elements</span></span>

<span data-ttu-id="8a346-113">无。</span><span class="sxs-lookup"><span data-stu-id="8a346-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8a346-114">父元素</span><span class="sxs-lookup"><span data-stu-id="8a346-114">Parent Elements</span></span>

|<span data-ttu-id="8a346-115">元素</span><span class="sxs-lookup"><span data-stu-id="8a346-115">Element</span></span>|<span data-ttu-id="8a346-116">说明</span><span class="sxs-lookup"><span data-stu-id="8a346-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a346-117">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="8a346-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="8a346-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="8a346-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8a346-119">文本值</span><span class="sxs-lookup"><span data-stu-id="8a346-119">Text Value</span></span>

<span data-ttu-id="8a346-120">指定触发条件的 .NET 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="8a346-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a346-121">备注</span><span class="sxs-lookup"><span data-stu-id="8a346-121">Remarks</span></span>

<span data-ttu-id="8a346-122">如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="8a346-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a346-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a346-123">See Also</span></span>

[<span data-ttu-id="8a346-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="8a346-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="8a346-125">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="8a346-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="8a346-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8a346-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
