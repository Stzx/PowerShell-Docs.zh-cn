---
ms.date: 09/13/2016
ms.topic: reference
title: TableRowEntry Element for TableRowEntries for TableControl (Format)
description: TableRowEntry Element for TableRowEntries for TableControl (Format)
ms.openlocfilehash: 60d64b7c14b40e87825ada36e19f52a66fe8b6cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659772"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a>TableRowEntry Element for TableRowEntries for TableControl (Format)

定义在表的行中显示的数据。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry) 格式 (TableRowEntries 元素) 

## <a name="syntax"></a>语法

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TableRowEntry` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[TableControl (格式的 TableRowEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|必需的元素。<br /><br /> 定义其属性值显示在行中的对象。|
|[TableColumnItems Element for TableRowEntry for TableControl (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|必需的元素。<br /><br /> 定义要显示其值的属性或脚本。|
|[TableControl 的 TableRowEntry 的 Wrap 元素 (格式) ](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|可选元素。<br /><br /> 指定在下一行显示超过列宽的文本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableRowEntries Element for TableControl (Format)](./tablerowentries-element-for-tablecontrol-format.md)|定义表中的行。|

## <a name="remarks"></a>备注

`TableColumnItems`必须指定一个元素和一个 `EntrySelectedBy` 元素。

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `TableRowEntry` 元素，该元素定义一个行，该行显示 system.exception 对象的两[](/dotnet/api/System.Diagnostics.Process)个属性的值。

```xml
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
```

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableControl (格式的 TableRowEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[TableColumnItems Element for TableRowEntry for TableControl (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[TableRowEntries Element for TableControl (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[TableControl 的 TableRowEntry 的 Wrap 元素 (格式) ](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
