---
title: " (格式) 的 TableHeaders 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: b3176cbe1316d5b30cb61831d9915a80389709a5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787421"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="16146-102">TableHeaders Element (Format)</span><span class="sxs-lookup"><span data-stu-id="16146-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="16146-103">定义表中各列的标头。</span><span class="sxs-lookup"><span data-stu-id="16146-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="16146-104">ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 TableControl (格式) </span><span class="sxs-lookup"><span data-stu-id="16146-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="16146-105">语法</span><span class="sxs-lookup"><span data-stu-id="16146-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="16146-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="16146-106">Attributes and Elements</span></span>

<span data-ttu-id="16146-107">以下各节描述了元素的属性、子元素和父元素 `TableHeaders` 。</span><span class="sxs-lookup"><span data-stu-id="16146-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="16146-108">对于要显示的对象的每个属性，都必须有一个子元素。</span><span class="sxs-lookup"><span data-stu-id="16146-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="16146-109">列标题信息按指定子元素的顺序显示。</span><span class="sxs-lookup"><span data-stu-id="16146-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="16146-110">特性</span><span class="sxs-lookup"><span data-stu-id="16146-110">Attributes</span></span>

<span data-ttu-id="16146-111">无。</span><span class="sxs-lookup"><span data-stu-id="16146-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16146-112">子元素</span><span class="sxs-lookup"><span data-stu-id="16146-112">Child Elements</span></span>

|<span data-ttu-id="16146-113">元素</span><span class="sxs-lookup"><span data-stu-id="16146-113">Element</span></span>|<span data-ttu-id="16146-114">描述</span><span class="sxs-lookup"><span data-stu-id="16146-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16146-115">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="16146-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="16146-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="16146-116">Optional element.</span></span><br /><br /> <span data-ttu-id="16146-117">定义表视图的列的数据标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="16146-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="16146-118">父元素</span><span class="sxs-lookup"><span data-stu-id="16146-118">Parent Elements</span></span>

|<span data-ttu-id="16146-119">元素</span><span class="sxs-lookup"><span data-stu-id="16146-119">Element</span></span>|<span data-ttu-id="16146-120">描述</span><span class="sxs-lookup"><span data-stu-id="16146-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16146-121">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="16146-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="16146-122">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="16146-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="16146-123">备注</span><span class="sxs-lookup"><span data-stu-id="16146-123">Remarks</span></span>

<span data-ttu-id="16146-124">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="16146-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="16146-125">示例</span><span class="sxs-lookup"><span data-stu-id="16146-125">Example</span></span>

<span data-ttu-id="16146-126">此示例演示一个 `TableHeaders` 定义两个列标题的元素。</span><span class="sxs-lookup"><span data-stu-id="16146-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="16146-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16146-127">See Also</span></span>

[<span data-ttu-id="16146-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="16146-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="16146-129">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="16146-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="16146-130">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="16146-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="16146-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="16146-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
