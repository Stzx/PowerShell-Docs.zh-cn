---
title: TableControl (Format) 的 TableRowEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4cc5d354df3e552e181a95148caa020f0041db92
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785109"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="bf886-102">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bf886-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="bf886-103">定义表中的行。</span><span class="sxs-lookup"><span data-stu-id="bf886-103">Defines the rows of the table.</span></span>

<span data-ttu-id="bf886-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="bf886-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf886-105">语法</span><span class="sxs-lookup"><span data-stu-id="bf886-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf886-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bf886-106">Attributes and Elements</span></span>

<span data-ttu-id="bf886-107">以下各节描述了元素的属性、子元素和父元素 `TableRowEntries` 。</span><span class="sxs-lookup"><span data-stu-id="bf886-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf886-108">特性</span><span class="sxs-lookup"><span data-stu-id="bf886-108">Attributes</span></span>

<span data-ttu-id="bf886-109">无。</span><span class="sxs-lookup"><span data-stu-id="bf886-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf886-110">子元素</span><span class="sxs-lookup"><span data-stu-id="bf886-110">Child Elements</span></span>

|<span data-ttu-id="bf886-111">元素</span><span class="sxs-lookup"><span data-stu-id="bf886-111">Element</span></span>|<span data-ttu-id="bf886-112">描述</span><span class="sxs-lookup"><span data-stu-id="bf886-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf886-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bf886-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="bf886-114">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="bf886-114">Required element.</span></span><br /><br /> <span data-ttu-id="bf886-115">定义在表的行中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="bf886-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bf886-116">父元素</span><span class="sxs-lookup"><span data-stu-id="bf886-116">Parent Elements</span></span>

|<span data-ttu-id="bf886-117">元素</span><span class="sxs-lookup"><span data-stu-id="bf886-117">Element</span></span>|<span data-ttu-id="bf886-118">描述</span><span class="sxs-lookup"><span data-stu-id="bf886-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf886-119">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bf886-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="bf886-120">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="bf886-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bf886-121">备注</span><span class="sxs-lookup"><span data-stu-id="bf886-121">Remarks</span></span>

<span data-ttu-id="bf886-122">您必须为表视图指定一个或多个 `TableRowEntry` 元素。</span><span class="sxs-lookup"><span data-stu-id="bf886-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="bf886-123">对于可以添加的元素数没有最大限制， `TableRowEntry` 也没有其顺序。</span><span class="sxs-lookup"><span data-stu-id="bf886-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="bf886-124">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="bf886-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="bf886-125">示例</span><span class="sxs-lookup"><span data-stu-id="bf886-125">Example</span></span>

<span data-ttu-id="bf886-126">下面的示例演示一个 `TableRowEntries` 元素，该元素定义一个行，该行显示 system.exception 对象的两[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)个属性的值。</span><span class="sxs-lookup"><span data-stu-id="bf886-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bf886-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf886-127">See Also</span></span>

[<span data-ttu-id="bf886-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="bf886-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="bf886-129">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bf886-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="bf886-130">TableRowEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="bf886-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="bf886-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="bf886-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
