---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for ListControl (Format)
description: TypeName Element for EntrySelectedBy for ListControl (Format)
ms.openlocfilehash: 6fc5a2385fde3140abbc984e3da6a4dda483b2a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645664"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="e1237-103">TypeName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e1237-103">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="e1237-104">指定使用此列表视图项的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e1237-104">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="e1237-105">对于列表项可以指定的类型数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="e1237-105">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="e1237-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry (的 TypeName 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="e1237-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e1237-107">语法</span><span class="sxs-lookup"><span data-stu-id="e1237-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1237-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e1237-108">Attributes and Elements</span></span>

<span data-ttu-id="e1237-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="e1237-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e1237-110">特性</span><span class="sxs-lookup"><span data-stu-id="e1237-110">Attributes</span></span>

<span data-ttu-id="e1237-111">无。</span><span class="sxs-lookup"><span data-stu-id="e1237-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e1237-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e1237-112">Child Elements</span></span>

<span data-ttu-id="e1237-113">无。</span><span class="sxs-lookup"><span data-stu-id="e1237-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e1237-114">父元素</span><span class="sxs-lookup"><span data-stu-id="e1237-114">Parent Elements</span></span>

|<span data-ttu-id="e1237-115">元素</span><span class="sxs-lookup"><span data-stu-id="e1237-115">Element</span></span>|<span data-ttu-id="e1237-116">描述</span><span class="sxs-lookup"><span data-stu-id="e1237-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e1237-117">ListEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e1237-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="e1237-118">定义使用此列表项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="e1237-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e1237-119">文本值</span><span class="sxs-lookup"><span data-stu-id="e1237-119">Text Value</span></span>

<span data-ttu-id="e1237-120">指定 .NET 类型的完全限定名称，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="e1237-120">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1237-121">备注</span><span class="sxs-lookup"><span data-stu-id="e1237-121">Remarks</span></span>

<span data-ttu-id="e1237-122">每个列表项必须至少定义一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="e1237-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e1237-123">有关如何在列表视图中使用此元素的详细信息，请参阅 [列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="e1237-123">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e1237-124">示例</span><span class="sxs-lookup"><span data-stu-id="e1237-124">Example</span></span>

<span data-ttu-id="e1237-125">下面的示例演示如何为列表视图的条目指定选择集。</span><span class="sxs-lookup"><span data-stu-id="e1237-125">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="e1237-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1237-126">See Also</span></span>

[<span data-ttu-id="e1237-127">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="e1237-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e1237-128">ListEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e1237-128">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="e1237-129">ListEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="e1237-129">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e1237-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e1237-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
