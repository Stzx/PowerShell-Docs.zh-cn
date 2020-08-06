---
title: 配置 (格式的控件的 ItemSeclectionCondition 的 PropertyName 元素) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0e304af1dbe816753d6dcd1dd8149f950f2a0941
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785585"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="f2cfd-102">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f2cfd-102">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f2cfd-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f2cfd-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="f2cfd-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f2cfd-106">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for 的 CustomEntry 元素配置 (格式) 的 CustomEntry 的 CustomItem 元素，用于 ExpressionBinding 的元素 for CustomItem for configuration 元素 for for for for Control for for Control for for Control for for Control for control (format 元素 for ItemSelectionCondition for configuration) 格式的控件 ()  (</span><span class="sxs-lookup"><span data-stu-id="f2cfd-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f2cfd-107">语法</span><span class="sxs-lookup"><span data-stu-id="f2cfd-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2cfd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2cfd-108">Attributes and Elements</span></span>

<span data-ttu-id="f2cfd-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2cfd-110">特性</span><span class="sxs-lookup"><span data-stu-id="f2cfd-110">Attributes</span></span>

<span data-ttu-id="f2cfd-111">无。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f2cfd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f2cfd-112">Child Elements</span></span>

<span data-ttu-id="f2cfd-113">无。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f2cfd-114">父元素</span><span class="sxs-lookup"><span data-stu-id="f2cfd-114">Parent Elements</span></span>

|<span data-ttu-id="f2cfd-115">元素</span><span class="sxs-lookup"><span data-stu-id="f2cfd-115">Element</span></span>|<span data-ttu-id="f2cfd-116">说明</span><span class="sxs-lookup"><span data-stu-id="f2cfd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2cfd-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f2cfd-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="f2cfd-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f2cfd-119">文本值</span><span class="sxs-lookup"><span data-stu-id="f2cfd-119">Text Value</span></span>

<span data-ttu-id="f2cfd-120">指定触发条件的 .NET 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2cfd-121">备注</span><span class="sxs-lookup"><span data-stu-id="f2cfd-121">Remarks</span></span>

<span data-ttu-id="f2cfd-122">如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f2cfd-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2cfd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2cfd-123">See Also</span></span>

[<span data-ttu-id="f2cfd-124">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f2cfd-124">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="f2cfd-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f2cfd-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="f2cfd-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f2cfd-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
