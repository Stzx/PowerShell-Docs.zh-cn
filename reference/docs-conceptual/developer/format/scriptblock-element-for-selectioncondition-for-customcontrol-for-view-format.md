---
title: SelectionCondition for CustomControl 的 ScriptBlock 元素 for View (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d3506188d32ce85ad6345dc0d0866dd789a1f293
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785398"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="05d02-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="05d02-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="05d02-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="05d02-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="05d02-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。</span><span class="sxs-lookup"><span data-stu-id="05d02-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="05d02-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="05d02-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="05d02-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) CustomControl 元素 for view (Format) CustomEntries 元素 for CustomControl for CustomEntry for CustomEntries for for CustomControl for CustomItem for CustomEntry for CustomControl for SelectionCondition for EntrySelectedBy for CustomControl SelectionCondition for view (format) CustomControl 元素（for 的元素 (</span><span class="sxs-lookup"><span data-stu-id="05d02-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="05d02-107">语法</span><span class="sxs-lookup"><span data-stu-id="05d02-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05d02-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="05d02-108">Attributes and Elements</span></span>

<span data-ttu-id="05d02-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="05d02-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="05d02-110">特性</span><span class="sxs-lookup"><span data-stu-id="05d02-110">Attributes</span></span>

<span data-ttu-id="05d02-111">无。</span><span class="sxs-lookup"><span data-stu-id="05d02-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="05d02-112">子元素</span><span class="sxs-lookup"><span data-stu-id="05d02-112">Child Elements</span></span>

<span data-ttu-id="05d02-113">无。</span><span class="sxs-lookup"><span data-stu-id="05d02-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="05d02-114">父元素</span><span class="sxs-lookup"><span data-stu-id="05d02-114">Parent Elements</span></span>

|<span data-ttu-id="05d02-115">元素</span><span class="sxs-lookup"><span data-stu-id="05d02-115">Element</span></span>|<span data-ttu-id="05d02-116">说明</span><span class="sxs-lookup"><span data-stu-id="05d02-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05d02-117">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="05d02-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="05d02-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="05d02-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="05d02-119">文本值</span><span class="sxs-lookup"><span data-stu-id="05d02-119">Text Value</span></span>

<span data-ttu-id="05d02-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="05d02-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="05d02-121">备注</span><span class="sxs-lookup"><span data-stu-id="05d02-121">Remarks</span></span>

<span data-ttu-id="05d02-122">选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="05d02-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="05d02-123">有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="05d02-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05d02-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05d02-124">See Also</span></span>

[<span data-ttu-id="05d02-125">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="05d02-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="05d02-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="05d02-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
