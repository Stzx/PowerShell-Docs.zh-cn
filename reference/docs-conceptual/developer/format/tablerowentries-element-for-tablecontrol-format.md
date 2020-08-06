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
# <a name="tablerowentries-element-for-tablecontrol-format"></a>TableRowEntries Element for TableControl (Format)

定义表中的行。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TableRowEntries` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[TableRowEntry Element for TableRowEntries for TableControl (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|必需的元素。<br /><br /> 定义在表的行中显示的数据。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableControl Element (Format)](./tablecontrol-element-format.md)|定义视图的表格格式。|

## <a name="remarks"></a>备注

您必须为表视图指定一个或多个 `TableRowEntry` 元素。 对于可以添加的元素数没有最大限制， `TableRowEntry` 也没有其顺序。

有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `TableRowEntries` 元素，该元素定义一个行，该行显示 system.exception 对象的两[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)个属性的值。

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

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableControl Element (Format)](./tablecontrol-element-format.md)

[TableRowEntry 元素 (格式) ](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
