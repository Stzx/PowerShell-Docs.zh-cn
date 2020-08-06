---
title: 用于 WideControl (Format) 的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787608"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="58cd3-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="58cd3-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="58cd3-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="58cd3-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="58cd3-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用宽输入定义。</span><span class="sxs-lookup"><span data-stu-id="58cd3-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="58cd3-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 WideEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="58cd3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="58cd3-106">语法</span><span class="sxs-lookup"><span data-stu-id="58cd3-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58cd3-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="58cd3-107">Attributes and Elements</span></span>

<span data-ttu-id="58cd3-108">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="58cd3-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="58cd3-109">特性</span><span class="sxs-lookup"><span data-stu-id="58cd3-109">Attributes</span></span>

<span data-ttu-id="58cd3-110">无。</span><span class="sxs-lookup"><span data-stu-id="58cd3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58cd3-111">子元素</span><span class="sxs-lookup"><span data-stu-id="58cd3-111">Child Elements</span></span>

<span data-ttu-id="58cd3-112">无。</span><span class="sxs-lookup"><span data-stu-id="58cd3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58cd3-113">父元素</span><span class="sxs-lookup"><span data-stu-id="58cd3-113">Parent Elements</span></span>

|<span data-ttu-id="58cd3-114">元素</span><span class="sxs-lookup"><span data-stu-id="58cd3-114">Element</span></span>|<span data-ttu-id="58cd3-115">说明</span><span class="sxs-lookup"><span data-stu-id="58cd3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58cd3-116">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="58cd3-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="58cd3-117">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="58cd3-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="58cd3-118">文本值</span><span class="sxs-lookup"><span data-stu-id="58cd3-118">Text Value</span></span>

<span data-ttu-id="58cd3-119">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="58cd3-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="58cd3-120">备注</span><span class="sxs-lookup"><span data-stu-id="58cd3-120">Remarks</span></span>

<span data-ttu-id="58cd3-121">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="58cd3-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="58cd3-122">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="58cd3-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="58cd3-123">有关大视图的其他组件的详细信息，请参阅[宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="58cd3-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58cd3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58cd3-124">See Also</span></span>

[<span data-ttu-id="58cd3-125">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="58cd3-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="58cd3-126">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="58cd3-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="58cd3-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="58cd3-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="58cd3-128">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="58cd3-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="58cd3-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="58cd3-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
