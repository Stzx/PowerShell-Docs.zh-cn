---
title: 配置 (格式的控件的 SelectionCondition 的 PropertyName 元素) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7730951a840fcfcd8bf819fff5182049bd6b6c23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773124"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="9f443-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9f443-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9f443-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="9f443-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="9f443-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用该条目。</span><span class="sxs-lookup"><span data-stu-id="9f443-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="9f443-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="9f443-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9f443-106">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素的的 CustomEntry 元素 CustomControl For Control for control (format) EntrySelectedBy 元素 For CustomEntry for EntrySelectedBy for CustomEntry 的 SelectionCondition 元素 For SelectionCondition for EntrySelectedBy for ListEntry for (format) )  (</span><span class="sxs-lookup"><span data-stu-id="9f443-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f443-107">语法</span><span class="sxs-lookup"><span data-stu-id="9f443-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f443-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9f443-108">Attributes and Elements</span></span>

<span data-ttu-id="9f443-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="9f443-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f443-110">特性</span><span class="sxs-lookup"><span data-stu-id="9f443-110">Attributes</span></span>

<span data-ttu-id="9f443-111">无。</span><span class="sxs-lookup"><span data-stu-id="9f443-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f443-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9f443-112">Child Elements</span></span>

<span data-ttu-id="9f443-113">无。</span><span class="sxs-lookup"><span data-stu-id="9f443-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9f443-114">父元素</span><span class="sxs-lookup"><span data-stu-id="9f443-114">Parent Elements</span></span>

|<span data-ttu-id="9f443-115">元素</span><span class="sxs-lookup"><span data-stu-id="9f443-115">Element</span></span>|<span data-ttu-id="9f443-116">说明</span><span class="sxs-lookup"><span data-stu-id="9f443-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f443-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9f443-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="9f443-118">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="9f443-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9f443-119">文本值</span><span class="sxs-lookup"><span data-stu-id="9f443-119">Text Value</span></span>

<span data-ttu-id="9f443-120">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="9f443-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f443-121">备注</span><span class="sxs-lookup"><span data-stu-id="9f443-121">Remarks</span></span>

<span data-ttu-id="9f443-122">选择条件必须指定至少一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="9f443-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="9f443-123">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="9f443-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f443-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f443-124">See Also</span></span>

[<span data-ttu-id="9f443-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9f443-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="9f443-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9f443-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
