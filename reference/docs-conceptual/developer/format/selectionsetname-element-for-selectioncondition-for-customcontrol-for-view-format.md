---
title: 用于 CustomControl for View (Format) 的 SelectionCondition 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c7fdd92475ba24d27e61371d1c6b54fa1a55647c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787506"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="e3eb3-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3eb3-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="e3eb3-103">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="e3eb3-104">如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="e3eb3-105">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e3eb3-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) EntrySelectedBy 的 CustomEntry 元素 (</span><span class="sxs-lookup"><span data-stu-id="e3eb3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3eb3-107">语法</span><span class="sxs-lookup"><span data-stu-id="e3eb3-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3eb3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3eb3-108">Attributes and Elements</span></span>

<span data-ttu-id="e3eb3-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3eb3-110">特性</span><span class="sxs-lookup"><span data-stu-id="e3eb3-110">Attributes</span></span>

<span data-ttu-id="e3eb3-111">无。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3eb3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e3eb3-112">Child Elements</span></span>

<span data-ttu-id="e3eb3-113">无。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3eb3-114">父元素</span><span class="sxs-lookup"><span data-stu-id="e3eb3-114">Parent Elements</span></span>

|<span data-ttu-id="e3eb3-115">元素</span><span class="sxs-lookup"><span data-stu-id="e3eb3-115">Element</span></span>|<span data-ttu-id="e3eb3-116">说明</span><span class="sxs-lookup"><span data-stu-id="e3eb3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3eb3-117">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="e3eb3-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="e3eb3-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3eb3-119">文本值</span><span class="sxs-lookup"><span data-stu-id="e3eb3-119">Text Value</span></span>

<span data-ttu-id="e3eb3-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3eb3-121">备注</span><span class="sxs-lookup"><span data-stu-id="e3eb3-121">Remarks</span></span>

<span data-ttu-id="e3eb3-122">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="e3eb3-123">有关创建和引用选项集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e3eb3-124">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="e3eb3-125">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e3eb3-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3eb3-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3eb3-126">See Also</span></span>

[<span data-ttu-id="e3eb3-127">用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="e3eb3-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="e3eb3-128">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="e3eb3-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e3eb3-129">定义选项集</span><span class="sxs-lookup"><span data-stu-id="e3eb3-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e3eb3-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e3eb3-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
