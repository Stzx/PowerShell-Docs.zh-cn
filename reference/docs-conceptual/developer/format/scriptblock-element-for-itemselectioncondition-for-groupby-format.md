---
title: 对于 GroupBy (Format) ，为 ItemSelectionCondition 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7738b180f328c7360275058cdb9dea01df6ea285
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787642"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="5da07-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5da07-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="5da07-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="5da07-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="5da07-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="5da07-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="5da07-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="5da07-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5da07-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) 的 GroupBy 元素 (的 CustomEntries 元素对于 groupby) 格式 (CustomControl 的元素) CustomEntry 元素 for CustomControl 对于 GroupBy (格式) CustomItem 元素 for CustomEntry for GroupBy (Format) ExpressionBinding 元素 for CustomItem for GroupBy (format) ItemSelectionCondition 元素 for ExpressionBinding for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="5da07-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5da07-107">语法</span><span class="sxs-lookup"><span data-stu-id="5da07-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5da07-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5da07-108">Attributes and Elements</span></span>

<span data-ttu-id="5da07-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="5da07-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5da07-110">特性</span><span class="sxs-lookup"><span data-stu-id="5da07-110">Attributes</span></span>

<span data-ttu-id="5da07-111">无。</span><span class="sxs-lookup"><span data-stu-id="5da07-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5da07-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5da07-112">Child Elements</span></span>

<span data-ttu-id="5da07-113">无。</span><span class="sxs-lookup"><span data-stu-id="5da07-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5da07-114">父元素</span><span class="sxs-lookup"><span data-stu-id="5da07-114">Parent Elements</span></span>

|<span data-ttu-id="5da07-115">元素</span><span class="sxs-lookup"><span data-stu-id="5da07-115">Element</span></span>|<span data-ttu-id="5da07-116">说明</span><span class="sxs-lookup"><span data-stu-id="5da07-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5da07-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5da07-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="5da07-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="5da07-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5da07-119">文本值</span><span class="sxs-lookup"><span data-stu-id="5da07-119">Text Value</span></span>

<span data-ttu-id="5da07-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="5da07-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="5da07-121">备注</span><span class="sxs-lookup"><span data-stu-id="5da07-121">Remarks</span></span>

<span data-ttu-id="5da07-122">如果使用此元素，则在定义选择条件时，不能指定[PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5da07-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5da07-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5da07-123">See Also</span></span>

[<span data-ttu-id="5da07-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5da07-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="5da07-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5da07-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="5da07-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="5da07-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
