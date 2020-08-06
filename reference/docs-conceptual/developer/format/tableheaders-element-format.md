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
# <a name="tableheaders-element-format"></a>TableHeaders Element (Format)

定义表中各列的标头。

ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 TableControl (格式) 

## <a name="syntax"></a>语法

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TableHeaders` 。 对于要显示的对象的每个属性，都必须有一个子元素。 列标题信息按指定子元素的顺序显示。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[TableColumnHeader Element (Format)](./tablecolumnheader-element-format.md)|可选元素。<br /><br /> 定义表视图的列的数据标签、宽度和对齐方式。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableControl Element (Format)](./tablecontrol-element-format.md)|定义视图的表格格式。|

## <a name="remarks"></a>备注

有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

此示例演示一个 `TableHeaders` 定义两个列标题的元素。

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

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableColumnHeader Element (Format)](./tablecolumnheader-element-format.md)

[TableControl Element (Format)](./tablecontrol-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
