---
title: 用于 CustomControl 的 SelectionCondition 的 PropertyName 元素) 的 View (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: aa3955b84b8de9901f394e8108f31440fcb6c942
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780791"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="36e5a-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="36e5a-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="36e5a-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="36e5a-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="36e5a-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="36e5a-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="36e5a-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="36e5a-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="36e5a-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 用于视图 (格式的 CustomControl CustomEntries 元素) CustomEntry 的的元素 (CustomEntries 的 CustomControl 元素对于 CustomEntry for CustomControl for View (Format) EntrySelectedBy 元素 for CustomEntry for CustomControl for SelectionCondition for view (Format) EntrySelectedBy for CustomControl 的 SelectionCondition 元素 CustomControl for View (Format) </span><span class="sxs-lookup"><span data-stu-id="36e5a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="36e5a-107">语法</span><span class="sxs-lookup"><span data-stu-id="36e5a-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="36e5a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36e5a-108">Attributes and Elements</span></span>

<span data-ttu-id="36e5a-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="36e5a-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="36e5a-110">特性</span><span class="sxs-lookup"><span data-stu-id="36e5a-110">Attributes</span></span>

<span data-ttu-id="36e5a-111">无。</span><span class="sxs-lookup"><span data-stu-id="36e5a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="36e5a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="36e5a-112">Child Elements</span></span>

<span data-ttu-id="36e5a-113">无。</span><span class="sxs-lookup"><span data-stu-id="36e5a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36e5a-114">父元素</span><span class="sxs-lookup"><span data-stu-id="36e5a-114">Parent Elements</span></span>

|<span data-ttu-id="36e5a-115">元素</span><span class="sxs-lookup"><span data-stu-id="36e5a-115">Element</span></span>|<span data-ttu-id="36e5a-116">说明</span><span class="sxs-lookup"><span data-stu-id="36e5a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="36e5a-117">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="36e5a-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="36e5a-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="36e5a-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="36e5a-119">文本值</span><span class="sxs-lookup"><span data-stu-id="36e5a-119">Text Value</span></span>

<span data-ttu-id="36e5a-120">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="36e5a-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="36e5a-121">备注</span><span class="sxs-lookup"><span data-stu-id="36e5a-121">Remarks</span></span>

<span data-ttu-id="36e5a-122">选择条件必须指定至少一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="36e5a-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="36e5a-123">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="36e5a-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36e5a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36e5a-124">See Also</span></span>

[<span data-ttu-id="36e5a-125">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="36e5a-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="36e5a-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="36e5a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
