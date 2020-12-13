---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)
description: TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: 66e90ab33775cf35d5e98e45266996d2d1a622d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659633"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="d2a23-103">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d2a23-103">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="d2a23-104">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="d2a23-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="d2a23-105">如果存在此类型，则满足条件，并使用表行。</span><span class="sxs-lookup"><span data-stu-id="d2a23-105">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="d2a23-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 的 TableRowEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 TableRowEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="d2a23-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d2a23-107">语法</span><span class="sxs-lookup"><span data-stu-id="d2a23-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2a23-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2a23-108">Attributes and Elements</span></span>

<span data-ttu-id="d2a23-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="d2a23-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2a23-110">特性</span><span class="sxs-lookup"><span data-stu-id="d2a23-110">Attributes</span></span>

<span data-ttu-id="d2a23-111">无。</span><span class="sxs-lookup"><span data-stu-id="d2a23-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d2a23-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d2a23-112">Child Elements</span></span>

<span data-ttu-id="d2a23-113">无。</span><span class="sxs-lookup"><span data-stu-id="d2a23-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2a23-114">父元素</span><span class="sxs-lookup"><span data-stu-id="d2a23-114">Parent Elements</span></span>

|<span data-ttu-id="d2a23-115">元素</span><span class="sxs-lookup"><span data-stu-id="d2a23-115">Element</span></span>|<span data-ttu-id="d2a23-116">描述</span><span class="sxs-lookup"><span data-stu-id="d2a23-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2a23-117">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="d2a23-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d2a23-118">定义要使用此表行必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d2a23-118">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d2a23-119">文本值</span><span class="sxs-lookup"><span data-stu-id="d2a23-119">Text Value</span></span>

<span data-ttu-id="d2a23-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="d2a23-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2a23-121">备注</span><span class="sxs-lookup"><span data-stu-id="d2a23-121">Remarks</span></span>

<span data-ttu-id="d2a23-122">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="d2a23-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="d2a23-123">有关如何使用选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a23-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d2a23-124">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a23-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2a23-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2a23-125">See Also</span></span>

[<span data-ttu-id="d2a23-126">创建表视图</span><span class="sxs-lookup"><span data-stu-id="d2a23-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d2a23-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="d2a23-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d2a23-128">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="d2a23-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d2a23-129">用于 EntrySelectedBy for TableRowEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素 </span><span class="sxs-lookup"><span data-stu-id="d2a23-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d2a23-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d2a23-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
