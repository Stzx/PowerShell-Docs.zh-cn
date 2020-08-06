---
title: TableControl (Format) 的 TableRowEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 047a10fb6b38dfa8f78a7741fd50b781d4a14b6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787693"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="b01ff-102">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="b01ff-103">定义使用表视图的此定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="b01ff-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="b01ff-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="b01ff-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b01ff-105">语法</span><span class="sxs-lookup"><span data-stu-id="b01ff-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b01ff-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b01ff-106">Attributes and Elements</span></span>

<span data-ttu-id="b01ff-107">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="b01ff-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b01ff-108">特性</span><span class="sxs-lookup"><span data-stu-id="b01ff-108">Attributes</span></span>

<span data-ttu-id="b01ff-109">无。</span><span class="sxs-lookup"><span data-stu-id="b01ff-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b01ff-110">子元素</span><span class="sxs-lookup"><span data-stu-id="b01ff-110">Child Elements</span></span>

|<span data-ttu-id="b01ff-111">元素</span><span class="sxs-lookup"><span data-stu-id="b01ff-111">Element</span></span>|<span data-ttu-id="b01ff-112">说明</span><span class="sxs-lookup"><span data-stu-id="b01ff-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b01ff-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b01ff-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b01ff-114">Optional element.</span></span><br /><br /> <span data-ttu-id="b01ff-115">定义要使用此表视图定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="b01ff-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="b01ff-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b01ff-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b01ff-117">Optional element.</span></span><br /><br /> <span data-ttu-id="b01ff-118">指定一组使用此表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="b01ff-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="b01ff-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b01ff-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b01ff-120">Optional element.</span></span><br /><br /> <span data-ttu-id="b01ff-121">指定使用此表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="b01ff-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b01ff-122">父元素</span><span class="sxs-lookup"><span data-stu-id="b01ff-122">Parent Elements</span></span>

|<span data-ttu-id="b01ff-123">元素</span><span class="sxs-lookup"><span data-stu-id="b01ff-123">Element</span></span>|<span data-ttu-id="b01ff-124">说明</span><span class="sxs-lookup"><span data-stu-id="b01ff-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b01ff-125">TableControl 的 TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="b01ff-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="b01ff-126">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="b01ff-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b01ff-127">备注</span><span class="sxs-lookup"><span data-stu-id="b01ff-127">Remarks</span></span>

<span data-ttu-id="b01ff-128">对于表视图定义，必须至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="b01ff-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="b01ff-129">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="b01ff-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="b01ff-130">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b01ff-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="b01ff-131">有关选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b01ff-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b01ff-132">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="b01ff-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b01ff-133">示例</span><span class="sxs-lookup"><span data-stu-id="b01ff-133">Example</span></span>

<span data-ttu-id="b01ff-134">下面的示例演示一个 `TableRowEntry` 元素，该元素用于显示[system.object](/dotnet/api/System.Diagnostics.Process)对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b01ff-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b01ff-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b01ff-135">See Also</span></span>

[<span data-ttu-id="b01ff-136">创建表视图</span><span class="sxs-lookup"><span data-stu-id="b01ff-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b01ff-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b01ff-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b01ff-139">TableControl 的 TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="b01ff-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="b01ff-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b01ff-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b01ff-141">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b01ff-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
