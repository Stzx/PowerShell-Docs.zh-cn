---
title: 用于 CustomControl 的 ItemSelectionCondition 的 PropertyName 元素) 的 View (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0131fa86be4be4daec1d9d24b50397fb8529f050
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785568"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="09b8b-102">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="09b8b-102">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="09b8b-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="09b8b-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="09b8b-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。</span><span class="sxs-lookup"><span data-stu-id="09b8b-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="09b8b-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="09b8b-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="09b8b-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 CustomControl 的元素 (CustomEntry 的 CustomEntries 元素 CustomEntry for View (Format) ExpressionBinding 元素 for CustomItem for CustomControl for for view (Format) ItemSelectionCondition 元素 for CustomControl for ItemSelectionCondition 的表达式绑定 (</span><span class="sxs-lookup"><span data-stu-id="09b8b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="09b8b-107">语法</span><span class="sxs-lookup"><span data-stu-id="09b8b-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="09b8b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="09b8b-108">Attributes and Elements</span></span>

<span data-ttu-id="09b8b-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="09b8b-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="09b8b-110">特性</span><span class="sxs-lookup"><span data-stu-id="09b8b-110">Attributes</span></span>

<span data-ttu-id="09b8b-111">无。</span><span class="sxs-lookup"><span data-stu-id="09b8b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="09b8b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="09b8b-112">Child Elements</span></span>

<span data-ttu-id="09b8b-113">无。</span><span class="sxs-lookup"><span data-stu-id="09b8b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="09b8b-114">父元素</span><span class="sxs-lookup"><span data-stu-id="09b8b-114">Parent Elements</span></span>

|<span data-ttu-id="09b8b-115">元素</span><span class="sxs-lookup"><span data-stu-id="09b8b-115">Element</span></span>|<span data-ttu-id="09b8b-116">说明</span><span class="sxs-lookup"><span data-stu-id="09b8b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="09b8b-117">CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="09b8b-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="09b8b-118">定义要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="09b8b-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="09b8b-119">文本值</span><span class="sxs-lookup"><span data-stu-id="09b8b-119">Text Value</span></span>

<span data-ttu-id="09b8b-120">指定触发条件的 .NET 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="09b8b-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="09b8b-121">备注</span><span class="sxs-lookup"><span data-stu-id="09b8b-121">Remarks</span></span>

<span data-ttu-id="09b8b-122">如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="09b8b-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b8b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09b8b-123">See Also</span></span>

[<span data-ttu-id="09b8b-124">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="09b8b-124">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="09b8b-125">CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="09b8b-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="09b8b-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="09b8b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
