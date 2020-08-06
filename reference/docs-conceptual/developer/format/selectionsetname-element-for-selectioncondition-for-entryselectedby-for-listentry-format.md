---
title: 用于 EntrySelectedBy for ListEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3666888f149f176126d9a19bdbad62469ca9f064
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787472"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="57ce7-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="57ce7-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="57ce7-103">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="57ce7-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="57ce7-104">如果此集中的任何类型存在，则满足条件，并使用此列表视图的定义显示该对象。</span><span class="sxs-lookup"><span data-stu-id="57ce7-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="57ce7-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 元素，ListEntry 的 SelectionSetName) 格式 (</span><span class="sxs-lookup"><span data-stu-id="57ce7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="57ce7-106">语法</span><span class="sxs-lookup"><span data-stu-id="57ce7-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="57ce7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="57ce7-107">Attributes and Elements</span></span>

<span data-ttu-id="57ce7-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="57ce7-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="57ce7-109">特性</span><span class="sxs-lookup"><span data-stu-id="57ce7-109">Attributes</span></span>

<span data-ttu-id="57ce7-110">无。</span><span class="sxs-lookup"><span data-stu-id="57ce7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="57ce7-111">子元素</span><span class="sxs-lookup"><span data-stu-id="57ce7-111">Child Elements</span></span>

<span data-ttu-id="57ce7-112">无。</span><span class="sxs-lookup"><span data-stu-id="57ce7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="57ce7-113">父元素</span><span class="sxs-lookup"><span data-stu-id="57ce7-113">Parent Elements</span></span>

|<span data-ttu-id="57ce7-114">元素</span><span class="sxs-lookup"><span data-stu-id="57ce7-114">Element</span></span>|<span data-ttu-id="57ce7-115">说明</span><span class="sxs-lookup"><span data-stu-id="57ce7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57ce7-116">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="57ce7-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="57ce7-117">定义使用此列表视图的定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="57ce7-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="57ce7-118">文本值</span><span class="sxs-lookup"><span data-stu-id="57ce7-118">Text Value</span></span>

<span data-ttu-id="57ce7-119">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="57ce7-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="57ce7-120">备注</span><span class="sxs-lookup"><span data-stu-id="57ce7-120">Remarks</span></span>

<span data-ttu-id="57ce7-121">选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="57ce7-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="57ce7-122">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="57ce7-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="57ce7-123">选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。</span><span class="sxs-lookup"><span data-stu-id="57ce7-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="57ce7-124">有关创建和引用选项集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="57ce7-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="57ce7-125">有关列表视图的其他组件的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="57ce7-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57ce7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57ce7-126">See Also</span></span>

[<span data-ttu-id="57ce7-127">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="57ce7-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="57ce7-128">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="57ce7-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="57ce7-129">ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="57ce7-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="57ce7-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="57ce7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
