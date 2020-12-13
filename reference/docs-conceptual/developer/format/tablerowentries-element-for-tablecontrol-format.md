---
ms.date: 09/13/2016
ms.topic: reference
title: TableRowEntries Element for TableControl (Format)
description: TableRowEntries Element for TableControl (Format)
ms.openlocfilehash: 1df63e645234da8276c7ccc5af34e81a56475e43
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651479"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="52fe0-103">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52fe0-103">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="52fe0-104">定义表中的行。</span><span class="sxs-lookup"><span data-stu-id="52fe0-104">Defines the rows of the table.</span></span>

<span data-ttu-id="52fe0-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="52fe0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52fe0-106">语法</span><span class="sxs-lookup"><span data-stu-id="52fe0-106">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52fe0-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="52fe0-107">Attributes and Elements</span></span>

<span data-ttu-id="52fe0-108">以下各节描述了元素的属性、子元素和父元素 `TableRowEntries` 。</span><span class="sxs-lookup"><span data-stu-id="52fe0-108">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="52fe0-109">特性</span><span class="sxs-lookup"><span data-stu-id="52fe0-109">Attributes</span></span>

<span data-ttu-id="52fe0-110">无。</span><span class="sxs-lookup"><span data-stu-id="52fe0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="52fe0-111">子元素</span><span class="sxs-lookup"><span data-stu-id="52fe0-111">Child Elements</span></span>

|<span data-ttu-id="52fe0-112">元素</span><span class="sxs-lookup"><span data-stu-id="52fe0-112">Element</span></span>|<span data-ttu-id="52fe0-113">描述</span><span class="sxs-lookup"><span data-stu-id="52fe0-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52fe0-114">TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52fe0-114">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="52fe0-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="52fe0-115">Required element.</span></span><br /><br /> <span data-ttu-id="52fe0-116">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="52fe0-116">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="52fe0-117">父元素</span><span class="sxs-lookup"><span data-stu-id="52fe0-117">Parent Elements</span></span>

|<span data-ttu-id="52fe0-118">元素</span><span class="sxs-lookup"><span data-stu-id="52fe0-118">Element</span></span>|<span data-ttu-id="52fe0-119">描述</span><span class="sxs-lookup"><span data-stu-id="52fe0-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52fe0-120">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="52fe0-120">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="52fe0-121">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="52fe0-121">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="52fe0-122">备注</span><span class="sxs-lookup"><span data-stu-id="52fe0-122">Remarks</span></span>

<span data-ttu-id="52fe0-123">您必须为表视图指定一个或多个 `TableRowEntry` 元素。</span><span class="sxs-lookup"><span data-stu-id="52fe0-123">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="52fe0-124">对于可以添加的元素数没有最大限制， `TableRowEntry` 也没有其顺序。</span><span class="sxs-lookup"><span data-stu-id="52fe0-124">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="52fe0-125">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="52fe0-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="52fe0-126">示例</span><span class="sxs-lookup"><span data-stu-id="52fe0-126">Example</span></span>

<span data-ttu-id="52fe0-127">下面的示例演示一个 `TableRowEntries` 元素，该元素定义一个行，该行显示 system.exception 对象的两[](/dotnet/api/System.Diagnostics.Process)个属性的值。</span><span class="sxs-lookup"><span data-stu-id="52fe0-127">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntries>
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
</TableRowEntries>

```

## <a name="see-also"></a><span data-ttu-id="52fe0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52fe0-128">See Also</span></span>

[<span data-ttu-id="52fe0-129">创建表视图</span><span class="sxs-lookup"><span data-stu-id="52fe0-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="52fe0-130">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="52fe0-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="52fe0-131">TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="52fe0-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="52fe0-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="52fe0-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
