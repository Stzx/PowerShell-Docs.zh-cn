---
ms.date: 09/13/2016
ms.topic: reference
title: TableColumnItems Element for TableRowEntry for TableControl (Format)
description: TableColumnItems Element for TableRowEntry for TableControl (Format)
ms.openlocfilehash: 4d600a366d2be1c453f05b301bdf575351dd51c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667753"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="ddad6-103">TableColumnItems Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ddad6-103">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="ddad6-104">定义其值显示在行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="ddad6-104">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="ddad6-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry 的 TableControl) 格式 (TableRowEntries TableControl TableColumnItems 的 TableControlEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="ddad6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ddad6-106">语法</span><span class="sxs-lookup"><span data-stu-id="ddad6-106">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ddad6-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ddad6-107">Attributes and Elements</span></span>

<span data-ttu-id="ddad6-108">以下各节描述了元素的属性、子元素和父元素 `TableColumnItems` 。</span><span class="sxs-lookup"><span data-stu-id="ddad6-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ddad6-109">特性</span><span class="sxs-lookup"><span data-stu-id="ddad6-109">Attributes</span></span>

<span data-ttu-id="ddad6-110">无。</span><span class="sxs-lookup"><span data-stu-id="ddad6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ddad6-111">子元素</span><span class="sxs-lookup"><span data-stu-id="ddad6-111">Child Elements</span></span>

|<span data-ttu-id="ddad6-112">元素</span><span class="sxs-lookup"><span data-stu-id="ddad6-112">Element</span></span>|<span data-ttu-id="ddad6-113">描述</span><span class="sxs-lookup"><span data-stu-id="ddad6-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddad6-114">TableColumnItem Element for TableColumnItems for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ddad6-114">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="ddad6-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="ddad6-115">Required element.</span></span><br /><br /> <span data-ttu-id="ddad6-116">定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="ddad6-116">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ddad6-117">父元素</span><span class="sxs-lookup"><span data-stu-id="ddad6-117">Parent Elements</span></span>

|<span data-ttu-id="ddad6-118">元素</span><span class="sxs-lookup"><span data-stu-id="ddad6-118">Element</span></span>|<span data-ttu-id="ddad6-119">描述</span><span class="sxs-lookup"><span data-stu-id="ddad6-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddad6-120">TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ddad6-120">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="ddad6-121">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="ddad6-121">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ddad6-122">备注</span><span class="sxs-lookup"><span data-stu-id="ddad6-122">Remarks</span></span>

<span data-ttu-id="ddad6-123">`TableColumnItem`行的每个列都需要一个元素。</span><span class="sxs-lookup"><span data-stu-id="ddad6-123">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="ddad6-124">第一项显示在第一列中，第二项显示在第二列，依此类推。</span><span class="sxs-lookup"><span data-stu-id="ddad6-124">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="ddad6-125">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="ddad6-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ddad6-126">示例</span><span class="sxs-lookup"><span data-stu-id="ddad6-126">Example</span></span>

<span data-ttu-id="ddad6-127">下面的示例演示一个 `TableColumnItems` 元素，该元素定义了 system.exception [](/dotnet/api/System.Diagnostics.Process)对象的三个属性。</span><span class="sxs-lookup"><span data-stu-id="ddad6-127">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="ddad6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddad6-128">See Also</span></span>

[<span data-ttu-id="ddad6-129">创建表视图</span><span class="sxs-lookup"><span data-stu-id="ddad6-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ddad6-130">TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="ddad6-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="ddad6-131">TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="ddad6-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="ddad6-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ddad6-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
