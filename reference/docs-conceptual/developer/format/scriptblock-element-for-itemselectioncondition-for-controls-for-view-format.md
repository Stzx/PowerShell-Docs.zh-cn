---
title: 用于 ItemSelectionCondition 的控件的 ScriptBlock 元素)  (格式的控件 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74b3e23005f595c4c550320849cac5b196e9d479
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787659"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="51b11-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="51b11-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="51b11-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="51b11-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="51b11-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="51b11-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="51b11-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="51b11-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="51b11-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) CustomEntry 的 CustomEntries 元素对于视图 (格式的控件) 用于视图 (格式的控件的 CustomEntry 的控件) ExpressionBinding 元素，用于视图 (格式的 CustomItem 的控件的控件) ItemSelectionCondition 的控件 (的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="51b11-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="51b11-107">语法</span><span class="sxs-lookup"><span data-stu-id="51b11-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="51b11-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="51b11-108">Attributes and Elements</span></span>

<span data-ttu-id="51b11-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="51b11-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="51b11-110">特性</span><span class="sxs-lookup"><span data-stu-id="51b11-110">Attributes</span></span>

<span data-ttu-id="51b11-111">无。</span><span class="sxs-lookup"><span data-stu-id="51b11-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="51b11-112">子元素</span><span class="sxs-lookup"><span data-stu-id="51b11-112">Child Elements</span></span>

<span data-ttu-id="51b11-113">无。</span><span class="sxs-lookup"><span data-stu-id="51b11-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="51b11-114">父元素</span><span class="sxs-lookup"><span data-stu-id="51b11-114">Parent Elements</span></span>

|<span data-ttu-id="51b11-115">元素</span><span class="sxs-lookup"><span data-stu-id="51b11-115">Element</span></span>|<span data-ttu-id="51b11-116">说明</span><span class="sxs-lookup"><span data-stu-id="51b11-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51b11-117">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="51b11-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="51b11-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="51b11-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="51b11-119">文本值</span><span class="sxs-lookup"><span data-stu-id="51b11-119">Text Value</span></span>

<span data-ttu-id="51b11-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="51b11-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="51b11-121">备注</span><span class="sxs-lookup"><span data-stu-id="51b11-121">Remarks</span></span>

<span data-ttu-id="51b11-122">如果使用此元素，则在定义选择条件时，不能指定[PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="51b11-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="51b11-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51b11-123">See Also</span></span>

[<span data-ttu-id="51b11-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="51b11-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="51b11-125">View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="51b11-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="51b11-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="51b11-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
