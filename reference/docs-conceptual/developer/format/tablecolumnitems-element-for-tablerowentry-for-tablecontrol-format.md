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
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a>TableColumnItems Element for TableRowEntry for TableControl (Format)

定义其值显示在行中的属性或脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry 的 TableControl) 格式 (TableRowEntries TableControl TableColumnItems 的 TableControlEntry 元素) 格式 (

## <a name="syntax"></a>语法

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TableColumnItems` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[TableColumnItem Element for TableColumnItems for TableControl (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|必需的元素。<br /><br /> 定义其值显示在行的列中的属性或脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableRowEntry Element for TableRowEntries for TableControl (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|定义在表的行中显示的数据。|

## <a name="remarks"></a>备注

`TableColumnItem`行的每个列都需要一个元素。 第一项显示在第一列中，第二项显示在第二列，依此类推。

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `TableColumnItems` 元素，该元素定义了 system.exception [](/dotnet/api/System.Diagnostics.Process)对象的三个属性。

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

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableColumnItem 元素 (格式) ](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[TableRowEntry 元素 (格式) ](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
