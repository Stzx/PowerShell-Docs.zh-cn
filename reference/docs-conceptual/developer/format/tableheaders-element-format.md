---
ms.date: 09/13/2016
ms.topic: reference
title: TableHeaders Element (Format)
description: TableHeaders Element (Format)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659825"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="8bef3-103">TableHeaders Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8bef3-103">TableHeaders Element (Format)</span></span>

<span data-ttu-id="8bef3-104">定义表中各列的标头。</span><span class="sxs-lookup"><span data-stu-id="8bef3-104">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="8bef3-105">ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 TableControl (格式) </span><span class="sxs-lookup"><span data-stu-id="8bef3-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8bef3-106">语法</span><span class="sxs-lookup"><span data-stu-id="8bef3-106">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="8bef3-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8bef3-107">Attributes and Elements</span></span>

<span data-ttu-id="8bef3-108">以下各节描述了元素的属性、子元素和父元素 `TableHeaders` 。</span><span class="sxs-lookup"><span data-stu-id="8bef3-108">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="8bef3-109">对于要显示的对象的每个属性，都必须有一个子元素。</span><span class="sxs-lookup"><span data-stu-id="8bef3-109">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="8bef3-110">列标题信息按指定子元素的顺序显示。</span><span class="sxs-lookup"><span data-stu-id="8bef3-110">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="8bef3-111">特性</span><span class="sxs-lookup"><span data-stu-id="8bef3-111">Attributes</span></span>

<span data-ttu-id="8bef3-112">无。</span><span class="sxs-lookup"><span data-stu-id="8bef3-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8bef3-113">子元素</span><span class="sxs-lookup"><span data-stu-id="8bef3-113">Child Elements</span></span>

|<span data-ttu-id="8bef3-114">元素</span><span class="sxs-lookup"><span data-stu-id="8bef3-114">Element</span></span>|<span data-ttu-id="8bef3-115">描述</span><span class="sxs-lookup"><span data-stu-id="8bef3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8bef3-116">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8bef3-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="8bef3-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="8bef3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="8bef3-118">定义表视图的列的数据标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="8bef3-118">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8bef3-119">父元素</span><span class="sxs-lookup"><span data-stu-id="8bef3-119">Parent Elements</span></span>

|<span data-ttu-id="8bef3-120">元素</span><span class="sxs-lookup"><span data-stu-id="8bef3-120">Element</span></span>|<span data-ttu-id="8bef3-121">描述</span><span class="sxs-lookup"><span data-stu-id="8bef3-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8bef3-122">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8bef3-122">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="8bef3-123">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="8bef3-123">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8bef3-124">备注</span><span class="sxs-lookup"><span data-stu-id="8bef3-124">Remarks</span></span>

<span data-ttu-id="8bef3-125">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="8bef3-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8bef3-126">示例</span><span class="sxs-lookup"><span data-stu-id="8bef3-126">Example</span></span>

<span data-ttu-id="8bef3-127">此示例演示一个 `TableHeaders` 定义两个列标题的元素。</span><span class="sxs-lookup"><span data-stu-id="8bef3-127">This example shows a `TableHeaders` element that defines two column headers.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="8bef3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bef3-128">See Also</span></span>

[<span data-ttu-id="8bef3-129">创建表视图</span><span class="sxs-lookup"><span data-stu-id="8bef3-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8bef3-130">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8bef3-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="8bef3-131">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8bef3-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="8bef3-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8bef3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
