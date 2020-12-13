---
ms.date: 09/13/2016
ms.topic: reference
title: TableColumnItem Element for TableColumnItems for TableControl (Format)
description: TableColumnItem Element for TableColumnItems for TableControl (Format)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659850"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="9249f-103">TableColumnItem Element for TableColumnItems for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-103">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="9249f-104">定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="9249f-104">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="9249f-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry 的 TableControl) 格式 (TableRowEntries TableControl 的 TableColumnItems 元素) TableControlEntry 的 TableControl TableColumnItem (格式) TableColumnItems 元素 (</span><span class="sxs-lookup"><span data-stu-id="9249f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9249f-106">语法</span><span class="sxs-lookup"><span data-stu-id="9249f-106">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9249f-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9249f-107">Attributes and Elements</span></span>

<span data-ttu-id="9249f-108">以下各节描述了元素的属性、子元素和父元素 `TableColumnItem` 。</span><span class="sxs-lookup"><span data-stu-id="9249f-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9249f-109">特性</span><span class="sxs-lookup"><span data-stu-id="9249f-109">Attributes</span></span>

<span data-ttu-id="9249f-110">无。</span><span class="sxs-lookup"><span data-stu-id="9249f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9249f-111">子元素</span><span class="sxs-lookup"><span data-stu-id="9249f-111">Child Elements</span></span>

|<span data-ttu-id="9249f-112">元素</span><span class="sxs-lookup"><span data-stu-id="9249f-112">Element</span></span>|<span data-ttu-id="9249f-113">描述</span><span class="sxs-lookup"><span data-stu-id="9249f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9249f-114">Alignment Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-114">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="9249f-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9249f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9249f-116">定义行的列中数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="9249f-116">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="9249f-117">FormatString Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-117">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="9249f-118">指定用于设置行的列中数据的格式的格式模式。</span><span class="sxs-lookup"><span data-stu-id="9249f-118">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="9249f-119">PropertyName Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-119">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="9249f-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9249f-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9249f-121">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="9249f-121">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="9249f-122">ScriptBlock Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-122">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="9249f-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9249f-123">Optional element.</span></span><br /><br /> <span data-ttu-id="9249f-124">指定其值显示在行的列中的脚本。</span><span class="sxs-lookup"><span data-stu-id="9249f-124">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9249f-125">父元素</span><span class="sxs-lookup"><span data-stu-id="9249f-125">Parent Elements</span></span>

|<span data-ttu-id="9249f-126">元素</span><span class="sxs-lookup"><span data-stu-id="9249f-126">Element</span></span>|<span data-ttu-id="9249f-127">描述</span><span class="sxs-lookup"><span data-stu-id="9249f-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9249f-128">TableControl (格式的 TableControlEntry 的 TableColumnItems 元素) </span><span class="sxs-lookup"><span data-stu-id="9249f-128">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="9249f-129">定义其值显示在行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="9249f-129">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9249f-130">备注</span><span class="sxs-lookup"><span data-stu-id="9249f-130">Remarks</span></span>

<span data-ttu-id="9249f-131">可以在行的每个列中指定对象或脚本的属性。</span><span class="sxs-lookup"><span data-stu-id="9249f-131">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="9249f-132">如果未指定子元素，则该项是占位符，不显示任何数据。</span><span class="sxs-lookup"><span data-stu-id="9249f-132">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="9249f-133">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="9249f-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9249f-134">示例</span><span class="sxs-lookup"><span data-stu-id="9249f-134">Example</span></span>

<span data-ttu-id="9249f-135">此示例演示一个 `TableColumnItem` 元素，该元素显示 `Status` [system.object](/dotnet/api/System.Diagnostics.Process) 对象的属性的值。</span><span class="sxs-lookup"><span data-stu-id="9249f-135">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="9249f-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9249f-136">See Also</span></span>

[<span data-ttu-id="9249f-137">创建表视图</span><span class="sxs-lookup"><span data-stu-id="9249f-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9249f-138">Alignment Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-138">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="9249f-139">TableColumnItems 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9249f-139">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="9249f-140">FormatString Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-140">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="9249f-141">PropertyName Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-141">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="9249f-142">ScriptBlock Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9249f-142">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="9249f-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9249f-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
