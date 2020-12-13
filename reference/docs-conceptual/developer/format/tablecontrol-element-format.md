---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl Element (Format)
description: TableControl Element (Format)
ms.openlocfilehash: 93e05e22d61504d7781b6f3c07f9a3fd0b3c9e8a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651455"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="3cbf2-103">TableControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-103">TableControl Element (Format)</span></span>

<span data-ttu-id="3cbf2-104">定义视图的表格格式。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-104">Defines a table format for a view.</span></span>

<span data-ttu-id="3cbf2-105">ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3cbf2-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3cbf2-106">语法</span><span class="sxs-lookup"><span data-stu-id="3cbf2-106">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="3cbf2-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3cbf2-107">Attributes and Elements</span></span>

<span data-ttu-id="3cbf2-108">以下各节描述了元素的属性、子元素和父元素 `TableControl` 。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-108">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="3cbf2-109">您必须指定表中的行。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-109">You must specify the rows of the table.</span></span> <span data-ttu-id="3cbf2-110">所有其他子元素都是可选的。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-110">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="3cbf2-111">特性</span><span class="sxs-lookup"><span data-stu-id="3cbf2-111">Attributes</span></span>

<span data-ttu-id="3cbf2-112">无。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3cbf2-113">子元素</span><span class="sxs-lookup"><span data-stu-id="3cbf2-113">Child Elements</span></span>

|<span data-ttu-id="3cbf2-114">元素</span><span class="sxs-lookup"><span data-stu-id="3cbf2-114">Element</span></span>|<span data-ttu-id="3cbf2-115">描述</span><span class="sxs-lookup"><span data-stu-id="3cbf2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3cbf2-116">AutoSize Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-116">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="3cbf2-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="3cbf2-118">指定是否根据数据大小调整列大小和列数。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="3cbf2-119">TableControl 的 HideTableHeaders 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3cbf2-119">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="3cbf2-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="3cbf2-121">指示是否不显示表的标头。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-121">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="3cbf2-122">TableControl 的 TableHeaders 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3cbf2-122">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="3cbf2-123">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-123">Required element.</span></span><br /><br /> <span data-ttu-id="3cbf2-124">为表视图的列定义标签、宽度和数据的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-124">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="3cbf2-125">TableRowEntries Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="3cbf2-126">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-126">Optional element.</span></span><br /><br /> <span data-ttu-id="3cbf2-127">提供表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-127">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3cbf2-128">父元素</span><span class="sxs-lookup"><span data-stu-id="3cbf2-128">Parent Elements</span></span>

|<span data-ttu-id="3cbf2-129">元素</span><span class="sxs-lookup"><span data-stu-id="3cbf2-129">Element</span></span>|<span data-ttu-id="3cbf2-130">描述</span><span class="sxs-lookup"><span data-stu-id="3cbf2-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3cbf2-131">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-131">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="3cbf2-132">定义一个视图，该视图用于显示一个或多个对象的成员。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-132">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3cbf2-133">备注</span><span class="sxs-lookup"><span data-stu-id="3cbf2-133">Remarks</span></span>

<span data-ttu-id="3cbf2-134">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-134">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3cbf2-135">示例</span><span class="sxs-lookup"><span data-stu-id="3cbf2-135">Example</span></span>

<span data-ttu-id="3cbf2-136">此示例演示一个 `TableControl` 元素，该元素用于显示 [System.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="3cbf2-136">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="3cbf2-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cbf2-137">See Also</span></span>

[<span data-ttu-id="3cbf2-138">创建表视图</span><span class="sxs-lookup"><span data-stu-id="3cbf2-138">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3cbf2-139">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-139">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="3cbf2-140">AutoSize Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-140">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="3cbf2-141">HideTableHeaders Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-141">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="3cbf2-142">TableHeaders Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3cbf2-142">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="3cbf2-143">TableRowEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3cbf2-143">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="3cbf2-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3cbf2-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
