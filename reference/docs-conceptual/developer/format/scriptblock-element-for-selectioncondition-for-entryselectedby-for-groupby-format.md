---
title: 用于 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e70e1555a8f2fe0d15d3e864d80d35527af81b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785381"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="02da0-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02da0-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="02da0-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="02da0-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="02da0-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="02da0-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="02da0-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="02da0-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="02da0-106">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="02da0-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="02da0-107">语法</span><span class="sxs-lookup"><span data-stu-id="02da0-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02da0-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02da0-108">Attributes and Elements</span></span>

<span data-ttu-id="02da0-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="02da0-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="02da0-110">特性</span><span class="sxs-lookup"><span data-stu-id="02da0-110">Attributes</span></span>

<span data-ttu-id="02da0-111">无。</span><span class="sxs-lookup"><span data-stu-id="02da0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="02da0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="02da0-112">Child Elements</span></span>

<span data-ttu-id="02da0-113">无。</span><span class="sxs-lookup"><span data-stu-id="02da0-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="02da0-114">父元素</span><span class="sxs-lookup"><span data-stu-id="02da0-114">Parent Elements</span></span>

|<span data-ttu-id="02da0-115">元素</span><span class="sxs-lookup"><span data-stu-id="02da0-115">Element</span></span>|<span data-ttu-id="02da0-116">描述</span><span class="sxs-lookup"><span data-stu-id="02da0-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02da0-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02da0-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="02da0-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="02da0-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="02da0-119">文本值</span><span class="sxs-lookup"><span data-stu-id="02da0-119">Text Value</span></span>

<span data-ttu-id="02da0-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="02da0-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="02da0-121">备注</span><span class="sxs-lookup"><span data-stu-id="02da0-121">Remarks</span></span>

<span data-ttu-id="02da0-122">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="02da0-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="02da0-123">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="02da0-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02da0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02da0-124">See Also</span></span>

[<span data-ttu-id="02da0-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02da0-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="02da0-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="02da0-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
