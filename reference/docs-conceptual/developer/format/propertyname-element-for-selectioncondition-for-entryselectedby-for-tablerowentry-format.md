---
title: TableRowEntry (Format) 的 SelectionCondition for EntrySelectedBy 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bec8377fb13b8f288196a809e7aa4e7f46c66e31
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785534"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="da8c6-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="da8c6-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="da8c6-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="da8c6-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="da8c6-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用表项。</span><span class="sxs-lookup"><span data-stu-id="da8c6-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="da8c6-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 的 TableRowEntry 元素 (SelectionCondition 的 EntrySelectedBy) format 元素 (TableRowEntry) 格式 (</span><span class="sxs-lookup"><span data-stu-id="da8c6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="da8c6-106">语法</span><span class="sxs-lookup"><span data-stu-id="da8c6-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="da8c6-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da8c6-107">Attributes and Elements</span></span>

<span data-ttu-id="da8c6-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="da8c6-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="da8c6-109">特性</span><span class="sxs-lookup"><span data-stu-id="da8c6-109">Attributes</span></span>

<span data-ttu-id="da8c6-110">无。</span><span class="sxs-lookup"><span data-stu-id="da8c6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="da8c6-111">子元素</span><span class="sxs-lookup"><span data-stu-id="da8c6-111">Child Elements</span></span>

<span data-ttu-id="da8c6-112">无。</span><span class="sxs-lookup"><span data-stu-id="da8c6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="da8c6-113">父元素</span><span class="sxs-lookup"><span data-stu-id="da8c6-113">Parent Elements</span></span>

|<span data-ttu-id="da8c6-114">元素</span><span class="sxs-lookup"><span data-stu-id="da8c6-114">Element</span></span>|<span data-ttu-id="da8c6-115">说明</span><span class="sxs-lookup"><span data-stu-id="da8c6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="da8c6-116">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="da8c6-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="da8c6-117">定义要使用此表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="da8c6-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="da8c6-118">文本值</span><span class="sxs-lookup"><span data-stu-id="da8c6-118">Text Value</span></span>

<span data-ttu-id="da8c6-119">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="da8c6-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="da8c6-120">备注</span><span class="sxs-lookup"><span data-stu-id="da8c6-120">Remarks</span></span>

<span data-ttu-id="da8c6-121">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="da8c6-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="da8c6-122">有关如何使用选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="da8c6-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="da8c6-123">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="da8c6-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da8c6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da8c6-124">See Also</span></span>

[<span data-ttu-id="da8c6-125">创建表视图</span><span class="sxs-lookup"><span data-stu-id="da8c6-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="da8c6-126">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="da8c6-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="da8c6-127">用于 TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="da8c6-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="da8c6-128">TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="da8c6-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="da8c6-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="da8c6-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
