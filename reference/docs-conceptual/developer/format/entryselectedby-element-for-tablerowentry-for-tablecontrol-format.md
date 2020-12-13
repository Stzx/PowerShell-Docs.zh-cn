---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for TableRowEntry for TableControl (Format)
description: EntrySelectedBy Element for TableRowEntry for TableControl (Format)
ms.openlocfilehash: 1b7fc60b6fa9864b66e9edfebb3e4a86e287f3f8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645890"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="48913-103">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-103">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="48913-104">定义使用表视图的此定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="48913-104">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="48913-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="48913-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48913-106">语法</span><span class="sxs-lookup"><span data-stu-id="48913-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="48913-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48913-107">Attributes and Elements</span></span>

<span data-ttu-id="48913-108">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="48913-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="48913-109">特性</span><span class="sxs-lookup"><span data-stu-id="48913-109">Attributes</span></span>

<span data-ttu-id="48913-110">无。</span><span class="sxs-lookup"><span data-stu-id="48913-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48913-111">子元素</span><span class="sxs-lookup"><span data-stu-id="48913-111">Child Elements</span></span>

|<span data-ttu-id="48913-112">元素</span><span class="sxs-lookup"><span data-stu-id="48913-112">Element</span></span>|<span data-ttu-id="48913-113">描述</span><span class="sxs-lookup"><span data-stu-id="48913-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48913-114">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-114">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="48913-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="48913-115">Optional element.</span></span><br /><br /> <span data-ttu-id="48913-116">定义要使用此表视图定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="48913-116">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="48913-117">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-117">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="48913-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="48913-118">Optional element.</span></span><br /><br /> <span data-ttu-id="48913-119">指定一组使用此表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="48913-119">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="48913-120">TypeName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-120">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="48913-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="48913-121">Optional element.</span></span><br /><br /> <span data-ttu-id="48913-122">指定使用此表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="48913-122">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="48913-123">父元素</span><span class="sxs-lookup"><span data-stu-id="48913-123">Parent Elements</span></span>

|<span data-ttu-id="48913-124">元素</span><span class="sxs-lookup"><span data-stu-id="48913-124">Element</span></span>|<span data-ttu-id="48913-125">描述</span><span class="sxs-lookup"><span data-stu-id="48913-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48913-126">TableControl 的 TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="48913-126">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="48913-127">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="48913-127">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="48913-128">备注</span><span class="sxs-lookup"><span data-stu-id="48913-128">Remarks</span></span>

<span data-ttu-id="48913-129">对于表视图定义，必须至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="48913-129">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="48913-130">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="48913-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="48913-131">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="48913-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="48913-132">有关选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="48913-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="48913-133">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="48913-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="48913-134">示例</span><span class="sxs-lookup"><span data-stu-id="48913-134">Example</span></span>

<span data-ttu-id="48913-135">下面的示例演示一个 `TableRowEntry` 元素，该元素用于显示 [system.object](/dotnet/api/System.Diagnostics.Process) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="48913-135">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="48913-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48913-136">See Also</span></span>

[<span data-ttu-id="48913-137">创建表视图</span><span class="sxs-lookup"><span data-stu-id="48913-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="48913-138">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-138">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="48913-139">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-139">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="48913-140">TableControl 的 TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="48913-140">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="48913-141">TypeName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="48913-141">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="48913-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="48913-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
