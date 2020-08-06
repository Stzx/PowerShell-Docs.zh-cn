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
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>TableColumnItem Element for TableColumnItems for TableControl (Format)

定义其值显示在行的列中的属性或脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (TableRowEntry 的 TableControl) 格式 (TableRowEntries TableControl 的 TableColumnItems 元素) TableControlEntry 的 TableControl TableColumnItem (格式) TableColumnItems 元素 (

## <a name="syntax"></a>语法

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TableColumnItem` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[Alignment Element for TableColumnItem for TableControl (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|可选元素。<br /><br /> 定义行的列中数据的显示方式。|
|[FormatString Element for TableColumnItem for TableControl (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|指定用于设置行的列中数据的格式的格式模式。|
|[PropertyName Element for TableColumnItem for TableControl (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|可选元素。<br /><br /> 指定显示其值的属性的名称。|
|[ScriptBlock Element for TableColumnItem for TableControl (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|可选元素。<br /><br /> 指定其值显示在行的列中的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableControl (格式的 TableControlEntry 的 TableColumnItems 元素) ](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|定义其值显示在行中的属性或脚本。|

## <a name="remarks"></a>备注

可以在行的每个列中指定对象或脚本的属性。 如果未指定子元素，则该项是占位符，不显示任何数据。

有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

此示例演示一个 `TableColumnItem` 元素，该元素显示 `Status` [system.object](/dotnet/api/System.Diagnostics.Process)对象的属性的值。

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[Alignment Element for TableColumnItem for TableControl (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableColumnItems 元素 (格式) ](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[FormatString Element for TableColumnItem for TableControl (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[PropertyName Element for TableColumnItem for TableControl (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[ScriptBlock Element for TableColumnItem for TableControl (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
