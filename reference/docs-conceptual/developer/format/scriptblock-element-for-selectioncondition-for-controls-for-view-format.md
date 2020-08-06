---
title: 用于 SelectionCondition 的控件的 ScriptBlock 元素)  (格式的控件 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e5f4295a989307cb6ffb655c2c39596f3d1ea806
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785415"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="3fe3a-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3fe3a-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="3fe3a-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="3fe3a-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="3fe3a-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="3fe3a-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomEntries 元素 (Format) 的 CustomEntries 的 CustomEntry 元素，用于视图 (格式) EntrySelectedBy 元素 for CustomEntry for view (格式的控件) SelectionCondition 的控件的控件 (EntrySelectedBy 的控件) 的 ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="3fe3a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3fe3a-107">语法</span><span class="sxs-lookup"><span data-stu-id="3fe3a-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fe3a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3fe3a-108">Attributes and Elements</span></span>

<span data-ttu-id="3fe3a-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3fe3a-110">特性</span><span class="sxs-lookup"><span data-stu-id="3fe3a-110">Attributes</span></span>

<span data-ttu-id="3fe3a-111">无。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3fe3a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3fe3a-112">Child Elements</span></span>

<span data-ttu-id="3fe3a-113">无。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3fe3a-114">父元素</span><span class="sxs-lookup"><span data-stu-id="3fe3a-114">Parent Elements</span></span>

|<span data-ttu-id="3fe3a-115">元素</span><span class="sxs-lookup"><span data-stu-id="3fe3a-115">Element</span></span>|<span data-ttu-id="3fe3a-116">说明</span><span class="sxs-lookup"><span data-stu-id="3fe3a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fe3a-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3fe3a-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="3fe3a-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3fe3a-119">文本值</span><span class="sxs-lookup"><span data-stu-id="3fe3a-119">Text Value</span></span>

<span data-ttu-id="3fe3a-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fe3a-121">备注</span><span class="sxs-lookup"><span data-stu-id="3fe3a-121">Remarks</span></span>

<span data-ttu-id="3fe3a-122">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="3fe3a-123">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="3fe3a-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fe3a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe3a-124">See Also</span></span>

[<span data-ttu-id="3fe3a-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3fe3a-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="3fe3a-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3fe3a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
