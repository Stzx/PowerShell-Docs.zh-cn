---
title: 用于 SelectionCondition 的控件的 ScriptBlock 元素) 配置 (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 24584aacd7869abd3dcfc6ff546e6dea4c2c04fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785432"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="b4064-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b4064-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b4064-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="b4064-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="b4064-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="b4064-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="b4064-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="b4064-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b4064-106">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素的的 CustomEntry 元素 CustomControl for control for control (Format) EntrySelectedBy 元素 for CustomEntry for control (Format for for control Format) SelectionCondition 元素 for EntrySelectedBy for control (format) </span><span class="sxs-lookup"><span data-stu-id="b4064-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4064-107">语法</span><span class="sxs-lookup"><span data-stu-id="b4064-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b4064-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b4064-108">Attributes and Elements</span></span>

<span data-ttu-id="b4064-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="b4064-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b4064-110">特性</span><span class="sxs-lookup"><span data-stu-id="b4064-110">Attributes</span></span>

<span data-ttu-id="b4064-111">无。</span><span class="sxs-lookup"><span data-stu-id="b4064-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b4064-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b4064-112">Child Elements</span></span>

<span data-ttu-id="b4064-113">无。</span><span class="sxs-lookup"><span data-stu-id="b4064-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b4064-114">父元素</span><span class="sxs-lookup"><span data-stu-id="b4064-114">Parent Elements</span></span>

|<span data-ttu-id="b4064-115">元素</span><span class="sxs-lookup"><span data-stu-id="b4064-115">Element</span></span>|<span data-ttu-id="b4064-116">说明</span><span class="sxs-lookup"><span data-stu-id="b4064-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4064-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b4064-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b4064-118">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="b4064-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b4064-119">文本值</span><span class="sxs-lookup"><span data-stu-id="b4064-119">Text Value</span></span>

<span data-ttu-id="b4064-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="b4064-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4064-121">备注</span><span class="sxs-lookup"><span data-stu-id="b4064-121">Remarks</span></span>

<span data-ttu-id="b4064-122">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="b4064-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="b4064-123">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b4064-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4064-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4064-124">See Also</span></span>

[<span data-ttu-id="b4064-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b4064-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="b4064-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b4064-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
