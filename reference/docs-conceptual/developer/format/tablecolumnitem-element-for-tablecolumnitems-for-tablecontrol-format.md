---
title: TableControl (Format) 的 TableColumnItems 的 TableColumnItem 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: beadf771f02519394d799a03db374050e3302321
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785160"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="ffc46-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="ffc46-103">定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="ffc46-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="ffc46-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry 的 TableControl) 格式 (TableRowEntries TableControl 的 TableColumnItems 元素) TableControlEntry 的 TableControl TableColumnItem (格式) TableColumnItems 元素 (</span><span class="sxs-lookup"><span data-stu-id="ffc46-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ffc46-105">语法</span><span class="sxs-lookup"><span data-stu-id="ffc46-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ffc46-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ffc46-106">Attributes and Elements</span></span>

<span data-ttu-id="ffc46-107">以下各节描述了元素的属性、子元素和父元素 `TableColumnItem` 。</span><span class="sxs-lookup"><span data-stu-id="ffc46-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ffc46-108">特性</span><span class="sxs-lookup"><span data-stu-id="ffc46-108">Attributes</span></span>

<span data-ttu-id="ffc46-109">无。</span><span class="sxs-lookup"><span data-stu-id="ffc46-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ffc46-110">子元素</span><span class="sxs-lookup"><span data-stu-id="ffc46-110">Child Elements</span></span>

|<span data-ttu-id="ffc46-111">元素</span><span class="sxs-lookup"><span data-stu-id="ffc46-111">Element</span></span>|<span data-ttu-id="ffc46-112">描述</span><span class="sxs-lookup"><span data-stu-id="ffc46-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ffc46-113">Alignment Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ffc46-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ffc46-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ffc46-115">定义行的列中数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="ffc46-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="ffc46-116">FormatString Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ffc46-117">指定用于设置行的列中数据的格式的格式模式。</span><span class="sxs-lookup"><span data-stu-id="ffc46-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="ffc46-118">PropertyName Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ffc46-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ffc46-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ffc46-120">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ffc46-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="ffc46-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ffc46-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ffc46-122">Optional element.</span></span><br /><br /> <span data-ttu-id="ffc46-123">指定其值显示在行的列中的脚本。</span><span class="sxs-lookup"><span data-stu-id="ffc46-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ffc46-124">父元素</span><span class="sxs-lookup"><span data-stu-id="ffc46-124">Parent Elements</span></span>

|<span data-ttu-id="ffc46-125">元素</span><span class="sxs-lookup"><span data-stu-id="ffc46-125">Element</span></span>|<span data-ttu-id="ffc46-126">描述</span><span class="sxs-lookup"><span data-stu-id="ffc46-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ffc46-127">TableControl (格式的 TableControlEntry 的 TableColumnItems 元素) </span><span class="sxs-lookup"><span data-stu-id="ffc46-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="ffc46-128">定义其值显示在行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="ffc46-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ffc46-129">备注</span><span class="sxs-lookup"><span data-stu-id="ffc46-129">Remarks</span></span>

<span data-ttu-id="ffc46-130">可以在行的每个列中指定对象或脚本的属性。</span><span class="sxs-lookup"><span data-stu-id="ffc46-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="ffc46-131">如果未指定子元素，则该项是占位符，不显示任何数据。</span><span class="sxs-lookup"><span data-stu-id="ffc46-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="ffc46-132">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="ffc46-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ffc46-133">示例</span><span class="sxs-lookup"><span data-stu-id="ffc46-133">Example</span></span>

<span data-ttu-id="ffc46-134">此示例演示一个 `TableColumnItem` 元素，该元素显示 `Status` [system.object](/dotnet/api/System.Diagnostics.Process)对象的属性的值。</span><span class="sxs-lookup"><span data-stu-id="ffc46-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="ffc46-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffc46-135">See Also</span></span>

[<span data-ttu-id="ffc46-136">创建表视图</span><span class="sxs-lookup"><span data-stu-id="ffc46-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ffc46-137">Alignment Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ffc46-138">TableColumnItems 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="ffc46-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="ffc46-139">FormatString Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ffc46-140">PropertyName Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ffc46-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ffc46-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ffc46-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ffc46-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
