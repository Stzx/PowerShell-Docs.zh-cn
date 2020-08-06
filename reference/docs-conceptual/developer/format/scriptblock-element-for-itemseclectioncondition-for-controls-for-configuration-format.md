---
title: 用于 ItemSeclectionCondition 的控件的 ScriptBlock 元素) 配置 (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f44b1a7f059fa5f41c19eed93762b61eda5110e8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772886"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="f7ade-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ade-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f7ade-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="f7ade-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f7ade-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="f7ade-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="f7ade-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="f7ade-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f7ade-106">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for 的 CustomEntry 元素配置 (格式) 的 CustomEntry 的 CustomItem 元素，用于 ExpressionBinding 的控件的配置元素的的控件 CustomItem 的控件) ItemSelectionCondition 的控件 (的控件) 格式 ( (</span><span class="sxs-lookup"><span data-stu-id="f7ade-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7ade-107">语法</span><span class="sxs-lookup"><span data-stu-id="f7ade-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7ade-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7ade-108">Attributes and Elements</span></span>

<span data-ttu-id="f7ade-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="f7ade-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7ade-110">特性</span><span class="sxs-lookup"><span data-stu-id="f7ade-110">Attributes</span></span>

<span data-ttu-id="f7ade-111">无。</span><span class="sxs-lookup"><span data-stu-id="f7ade-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7ade-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f7ade-112">Child Elements</span></span>

<span data-ttu-id="f7ade-113">无。</span><span class="sxs-lookup"><span data-stu-id="f7ade-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7ade-114">父元素</span><span class="sxs-lookup"><span data-stu-id="f7ade-114">Parent Elements</span></span>

|<span data-ttu-id="f7ade-115">元素</span><span class="sxs-lookup"><span data-stu-id="f7ade-115">Element</span></span>|<span data-ttu-id="f7ade-116">说明</span><span class="sxs-lookup"><span data-stu-id="f7ade-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7ade-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ade-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="f7ade-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f7ade-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7ade-119">文本值</span><span class="sxs-lookup"><span data-stu-id="f7ade-119">Text Value</span></span>

<span data-ttu-id="f7ade-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="f7ade-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7ade-121">备注</span><span class="sxs-lookup"><span data-stu-id="f7ade-121">Remarks</span></span>

<span data-ttu-id="f7ade-122">如果使用此元素，则在定义选择条件时，不能指定[PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f7ade-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7ade-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ade-123">See Also</span></span>

[<span data-ttu-id="f7ade-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ade-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="f7ade-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ade-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="f7ade-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f7ade-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
