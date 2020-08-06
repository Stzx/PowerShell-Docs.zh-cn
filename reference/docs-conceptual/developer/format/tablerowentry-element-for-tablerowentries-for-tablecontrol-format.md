---
title: TableControl (Format) 的 TableRowEntries 的 TableRowEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 83076ae5b2c48992ce5e621c65fc9937efb68b87
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787404"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a><span data-ttu-id="f1e24-102">TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f1e24-102">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

<span data-ttu-id="f1e24-103">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="f1e24-103">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="f1e24-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry) 格式 (TableRowEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="f1e24-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f1e24-105">语法</span><span class="sxs-lookup"><span data-stu-id="f1e24-105">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1e24-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f1e24-106">Attributes and Elements</span></span>

<span data-ttu-id="f1e24-107">以下各节描述了元素的属性、子元素和父元素 `TableRowEntry` 。</span><span class="sxs-lookup"><span data-stu-id="f1e24-107">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1e24-108">特性</span><span class="sxs-lookup"><span data-stu-id="f1e24-108">Attributes</span></span>

<span data-ttu-id="f1e24-109">无。</span><span class="sxs-lookup"><span data-stu-id="f1e24-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f1e24-110">子元素</span><span class="sxs-lookup"><span data-stu-id="f1e24-110">Child Elements</span></span>

|<span data-ttu-id="f1e24-111">元素</span><span class="sxs-lookup"><span data-stu-id="f1e24-111">Element</span></span>|<span data-ttu-id="f1e24-112">描述</span><span class="sxs-lookup"><span data-stu-id="f1e24-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1e24-113">TableControl (格式的 TableRowEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="f1e24-113">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="f1e24-114">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="f1e24-114">Required element.</span></span><br /><br /> <span data-ttu-id="f1e24-115">定义其属性值显示在行中的对象。</span><span class="sxs-lookup"><span data-stu-id="f1e24-115">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="f1e24-116">TableColumnItems Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f1e24-116">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="f1e24-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="f1e24-117">Required element.</span></span><br /><br /> <span data-ttu-id="f1e24-118">定义要显示其值的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="f1e24-118">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="f1e24-119">TableControl 的 TableRowEntry 的 Wrap 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f1e24-119">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="f1e24-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f1e24-120">Optional element.</span></span><br /><br /> <span data-ttu-id="f1e24-121">指定在下一行显示超过列宽的文本。</span><span class="sxs-lookup"><span data-stu-id="f1e24-121">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f1e24-122">父元素</span><span class="sxs-lookup"><span data-stu-id="f1e24-122">Parent Elements</span></span>

|<span data-ttu-id="f1e24-123">元素</span><span class="sxs-lookup"><span data-stu-id="f1e24-123">Element</span></span>|<span data-ttu-id="f1e24-124">描述</span><span class="sxs-lookup"><span data-stu-id="f1e24-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1e24-125">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f1e24-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="f1e24-126">定义表中的行。</span><span class="sxs-lookup"><span data-stu-id="f1e24-126">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f1e24-127">备注</span><span class="sxs-lookup"><span data-stu-id="f1e24-127">Remarks</span></span>

<span data-ttu-id="f1e24-128">`TableColumnItems`必须指定一个元素和一个 `EntrySelectedBy` 元素。</span><span class="sxs-lookup"><span data-stu-id="f1e24-128">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="f1e24-129">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f1e24-129">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f1e24-130">示例</span><span class="sxs-lookup"><span data-stu-id="f1e24-130">Example</span></span>

<span data-ttu-id="f1e24-131">下面的示例演示一个 `TableRowEntry` 元素，该元素定义一个行，该行显示 system.exception 对象的两[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)个属性的值。</span><span class="sxs-lookup"><span data-stu-id="f1e24-131">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f1e24-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1e24-132">See Also</span></span>

[<span data-ttu-id="f1e24-133">创建表视图</span><span class="sxs-lookup"><span data-stu-id="f1e24-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f1e24-134">TableControl (格式的 TableRowEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="f1e24-134">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="f1e24-135">TableColumnItems Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f1e24-135">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="f1e24-136">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f1e24-136">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="f1e24-137">TableControl 的 TableRowEntry 的 Wrap 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f1e24-137">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="f1e24-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f1e24-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
