---
ms.date: 09/13/2016
ms.topic: reference
title: TableRowEntry Element for TableRowEntries for TableControl (Format)
description: TableRowEntry Element for TableRowEntries for TableControl (Format)
ms.openlocfilehash: 60d64b7c14b40e87825ada36e19f52a66fe8b6cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659772"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a><span data-ttu-id="7722a-103">TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7722a-103">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

<span data-ttu-id="7722a-104">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="7722a-104">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="7722a-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry) 格式 (TableRowEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="7722a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7722a-106">语法</span><span class="sxs-lookup"><span data-stu-id="7722a-106">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7722a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7722a-107">Attributes and Elements</span></span>

<span data-ttu-id="7722a-108">以下各节描述了元素的属性、子元素和父元素 `TableRowEntry` 。</span><span class="sxs-lookup"><span data-stu-id="7722a-108">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7722a-109">特性</span><span class="sxs-lookup"><span data-stu-id="7722a-109">Attributes</span></span>

<span data-ttu-id="7722a-110">无。</span><span class="sxs-lookup"><span data-stu-id="7722a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7722a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="7722a-111">Child Elements</span></span>

|<span data-ttu-id="7722a-112">元素</span><span class="sxs-lookup"><span data-stu-id="7722a-112">Element</span></span>|<span data-ttu-id="7722a-113">描述</span><span class="sxs-lookup"><span data-stu-id="7722a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7722a-114">TableControl (格式的 TableRowEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="7722a-114">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="7722a-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7722a-115">Required element.</span></span><br /><br /> <span data-ttu-id="7722a-116">定义其属性值显示在行中的对象。</span><span class="sxs-lookup"><span data-stu-id="7722a-116">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="7722a-117">TableColumnItems Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7722a-117">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="7722a-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7722a-118">Required element.</span></span><br /><br /> <span data-ttu-id="7722a-119">定义要显示其值的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="7722a-119">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="7722a-120">TableControl 的 TableRowEntry 的 Wrap 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7722a-120">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="7722a-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7722a-121">Optional element.</span></span><br /><br /> <span data-ttu-id="7722a-122">指定在下一行显示超过列宽的文本。</span><span class="sxs-lookup"><span data-stu-id="7722a-122">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7722a-123">父元素</span><span class="sxs-lookup"><span data-stu-id="7722a-123">Parent Elements</span></span>

|<span data-ttu-id="7722a-124">元素</span><span class="sxs-lookup"><span data-stu-id="7722a-124">Element</span></span>|<span data-ttu-id="7722a-125">描述</span><span class="sxs-lookup"><span data-stu-id="7722a-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7722a-126">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7722a-126">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="7722a-127">定义表中的行。</span><span class="sxs-lookup"><span data-stu-id="7722a-127">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7722a-128">备注</span><span class="sxs-lookup"><span data-stu-id="7722a-128">Remarks</span></span>

<span data-ttu-id="7722a-129">`TableColumnItems`必须指定一个元素和一个 `EntrySelectedBy` 元素。</span><span class="sxs-lookup"><span data-stu-id="7722a-129">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="7722a-130">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="7722a-130">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7722a-131">示例</span><span class="sxs-lookup"><span data-stu-id="7722a-131">Example</span></span>

<span data-ttu-id="7722a-132">下面的示例演示一个 `TableRowEntry` 元素，该元素定义一个行，该行显示 system.exception 对象的两[](/dotnet/api/System.Diagnostics.Process)个属性的值。</span><span class="sxs-lookup"><span data-stu-id="7722a-132">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="7722a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7722a-133">See Also</span></span>

[<span data-ttu-id="7722a-134">创建表视图</span><span class="sxs-lookup"><span data-stu-id="7722a-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7722a-135">TableControl (格式的 TableRowEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="7722a-135">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="7722a-136">TableColumnItems Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7722a-136">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="7722a-137">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7722a-137">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="7722a-138">TableControl 的 TableRowEntry 的 Wrap 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7722a-138">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="7722a-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7722a-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
