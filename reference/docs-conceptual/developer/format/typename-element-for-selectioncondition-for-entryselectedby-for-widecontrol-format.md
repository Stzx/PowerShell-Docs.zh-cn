---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)
description: TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)
ms.openlocfilehash: af6e4782c345b43e16bce59c333bdaaceba0d845
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645506"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="7829e-103">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7829e-103">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="7829e-104">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="7829e-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="7829e-105">如果存在此类型，则使用定义。</span><span class="sxs-lookup"><span data-stu-id="7829e-105">When this type is present, the definition is used.</span></span>

<span data-ttu-id="7829e-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 WideEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="7829e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7829e-107">语法</span><span class="sxs-lookup"><span data-stu-id="7829e-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7829e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7829e-108">Attributes and Elements</span></span>

<span data-ttu-id="7829e-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="7829e-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7829e-110">特性</span><span class="sxs-lookup"><span data-stu-id="7829e-110">Attributes</span></span>

<span data-ttu-id="7829e-111">无。</span><span class="sxs-lookup"><span data-stu-id="7829e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7829e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7829e-112">Child Elements</span></span>

<span data-ttu-id="7829e-113">无。</span><span class="sxs-lookup"><span data-stu-id="7829e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7829e-114">父元素</span><span class="sxs-lookup"><span data-stu-id="7829e-114">Parent Elements</span></span>

|<span data-ttu-id="7829e-115">元素</span><span class="sxs-lookup"><span data-stu-id="7829e-115">Element</span></span>|<span data-ttu-id="7829e-116">描述</span><span class="sxs-lookup"><span data-stu-id="7829e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7829e-117">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="7829e-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="7829e-118">定义要使用此宽项时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="7829e-118">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7829e-119">文本值</span><span class="sxs-lookup"><span data-stu-id="7829e-119">Text Value</span></span>

<span data-ttu-id="7829e-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="7829e-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7829e-121">备注</span><span class="sxs-lookup"><span data-stu-id="7829e-121">Remarks</span></span>

<span data-ttu-id="7829e-122">选择条件可以指定 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="7829e-122">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="7829e-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7829e-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7829e-124">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="7829e-124">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7829e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7829e-125">See Also</span></span>

[<span data-ttu-id="7829e-126">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="7829e-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7829e-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="7829e-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7829e-128">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="7829e-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="7829e-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7829e-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="7829e-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7829e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
