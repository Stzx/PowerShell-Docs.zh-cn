---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)
description: TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)
ms.openlocfilehash: 2e8246e3ef2cba38824d8f8004acfffc3236df13
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645553"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="1941d-103">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1941d-103">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="1941d-104">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1941d-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="1941d-105">如果存在此类型，则使用列表项。</span><span class="sxs-lookup"><span data-stu-id="1941d-105">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="1941d-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素用于 ListControl (格式) ListEntry for ListEntries 的 ListControl 元素 (EntrySelectedBy ListEntry 的 ListControl 元素) SelectionCondition 的 EntrySelectedBy 的 ListControl (格式) SelectionCondition (</span><span class="sxs-lookup"><span data-stu-id="1941d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1941d-107">语法</span><span class="sxs-lookup"><span data-stu-id="1941d-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1941d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1941d-108">Attributes and Elements</span></span>

<span data-ttu-id="1941d-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="1941d-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1941d-110">特性</span><span class="sxs-lookup"><span data-stu-id="1941d-110">Attributes</span></span>

<span data-ttu-id="1941d-111">无。</span><span class="sxs-lookup"><span data-stu-id="1941d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1941d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1941d-112">Child Elements</span></span>

<span data-ttu-id="1941d-113">无。</span><span class="sxs-lookup"><span data-stu-id="1941d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1941d-114">父元素</span><span class="sxs-lookup"><span data-stu-id="1941d-114">Parent Elements</span></span>

|<span data-ttu-id="1941d-115">元素</span><span class="sxs-lookup"><span data-stu-id="1941d-115">Element</span></span>|<span data-ttu-id="1941d-116">描述</span><span class="sxs-lookup"><span data-stu-id="1941d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1941d-117">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1941d-117">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="1941d-118">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="1941d-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1941d-119">文本值</span><span class="sxs-lookup"><span data-stu-id="1941d-119">Text Value</span></span>

<span data-ttu-id="1941d-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="1941d-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1941d-121">备注</span><span class="sxs-lookup"><span data-stu-id="1941d-121">Remarks</span></span>

<span data-ttu-id="1941d-122">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="1941d-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="1941d-123">有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="1941d-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1941d-124">有关列表视图的其他组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="1941d-124">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1941d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1941d-125">See Also</span></span>

[<span data-ttu-id="1941d-126">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="1941d-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1941d-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="1941d-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1941d-128">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1941d-128">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1941d-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1941d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
