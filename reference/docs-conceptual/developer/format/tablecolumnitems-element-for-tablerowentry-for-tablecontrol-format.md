---
title: TableControl (Format) 的 TableRowEntry 的 TableColumnItems 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 661b938e8db0e68e10dc05f552e4f3a14608bc55
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785143"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="e899b-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e899b-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="e899b-103">定义其值显示在行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="e899b-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="e899b-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry 的 TableControl) 格式 (TableRowEntries TableControl TableColumnItems 的 TableControlEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="e899b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e899b-105">语法</span><span class="sxs-lookup"><span data-stu-id="e899b-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e899b-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e899b-106">Attributes and Elements</span></span>

<span data-ttu-id="e899b-107">以下各节描述了元素的属性、子元素和父元素 `TableColumnItems` 。</span><span class="sxs-lookup"><span data-stu-id="e899b-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e899b-108">特性</span><span class="sxs-lookup"><span data-stu-id="e899b-108">Attributes</span></span>

<span data-ttu-id="e899b-109">无。</span><span class="sxs-lookup"><span data-stu-id="e899b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e899b-110">子元素</span><span class="sxs-lookup"><span data-stu-id="e899b-110">Child Elements</span></span>

|<span data-ttu-id="e899b-111">元素</span><span class="sxs-lookup"><span data-stu-id="e899b-111">Element</span></span>|<span data-ttu-id="e899b-112">描述</span><span class="sxs-lookup"><span data-stu-id="e899b-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e899b-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e899b-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="e899b-114">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="e899b-114">Required element.</span></span><br /><br /> <span data-ttu-id="e899b-115">定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="e899b-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e899b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e899b-116">Parent Elements</span></span>

|<span data-ttu-id="e899b-117">元素</span><span class="sxs-lookup"><span data-stu-id="e899b-117">Element</span></span>|<span data-ttu-id="e899b-118">描述</span><span class="sxs-lookup"><span data-stu-id="e899b-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e899b-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e899b-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="e899b-120">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="e899b-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e899b-121">备注</span><span class="sxs-lookup"><span data-stu-id="e899b-121">Remarks</span></span>

<span data-ttu-id="e899b-122">`TableColumnItem`行的每个列都需要一个元素。</span><span class="sxs-lookup"><span data-stu-id="e899b-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="e899b-123">第一项显示在第一列中，第二项显示在第二列，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e899b-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="e899b-124">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="e899b-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e899b-125">示例</span><span class="sxs-lookup"><span data-stu-id="e899b-125">Example</span></span>

<span data-ttu-id="e899b-126">下面的示例演示一个 `TableColumnItems` 元素，该元素定义了 system.exception [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)对象的三个属性。</span><span class="sxs-lookup"><span data-stu-id="e899b-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e899b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e899b-127">See Also</span></span>

[<span data-ttu-id="e899b-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="e899b-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e899b-129">TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e899b-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="e899b-130">TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e899b-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="e899b-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e899b-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
