---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)
description: ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: a984bda6b8fba3a5cb9485576ffd847f0d366d3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659884"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="a131b-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a131b-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="a131b-104">指定触发条件的脚本块。</span><span class="sxs-lookup"><span data-stu-id="a131b-104">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="a131b-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用表项。</span><span class="sxs-lookup"><span data-stu-id="a131b-105">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="a131b-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 的 TableRowEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 TableRowEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="a131b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a131b-107">语法</span><span class="sxs-lookup"><span data-stu-id="a131b-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a131b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a131b-108">Attributes and Elements</span></span>

<span data-ttu-id="a131b-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="a131b-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a131b-110">特性</span><span class="sxs-lookup"><span data-stu-id="a131b-110">Attributes</span></span>

<span data-ttu-id="a131b-111">无。</span><span class="sxs-lookup"><span data-stu-id="a131b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a131b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a131b-112">Child Elements</span></span>

<span data-ttu-id="a131b-113">无。</span><span class="sxs-lookup"><span data-stu-id="a131b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a131b-114">父元素</span><span class="sxs-lookup"><span data-stu-id="a131b-114">Parent Elements</span></span>

|<span data-ttu-id="a131b-115">元素</span><span class="sxs-lookup"><span data-stu-id="a131b-115">Element</span></span>|<span data-ttu-id="a131b-116">描述</span><span class="sxs-lookup"><span data-stu-id="a131b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a131b-117">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="a131b-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a131b-118">定义要使用此表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a131b-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a131b-119">文本值</span><span class="sxs-lookup"><span data-stu-id="a131b-119">Text Value</span></span>

<span data-ttu-id="a131b-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="a131b-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="a131b-121">备注</span><span class="sxs-lookup"><span data-stu-id="a131b-121">Remarks</span></span>

<span data-ttu-id="a131b-122">选择条件必须指定至少一个脚本块或属性名称，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a131b-122">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="a131b-123">有关如何使用选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a131b-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a131b-124">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="a131b-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a131b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a131b-125">See Also</span></span>

[<span data-ttu-id="a131b-126">创建表视图</span><span class="sxs-lookup"><span data-stu-id="a131b-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a131b-127">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="a131b-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a131b-128">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a131b-128">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="a131b-129">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="a131b-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a131b-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a131b-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
