---
title: 适用于 TableControl (Format) 的 TableColumnHeader 标签元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b7b1d6825d3bca0e36b230415d19c2ac48377a46
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785738"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>Label Element for TableColumnHeader for TableControl (Format)

定义在列顶部显示的标签。 定义表视图时使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (TableColumnHeader 的 TableControl) 格式 (TableHeaders TableControl 的 TableColumnHeader 元素) TableControl (格式) 

## <a name="syntax"></a>语法

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Label` 。 每个列只允许有一个标签。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) ](./tablecolumnheader-element-format.md)|定义表中某一列的数据的标签、宽度和对齐方式。|

## <a name="text-value"></a>文本值

指定在表的列顶部显示的文本。 列标签没有受限制的字符。

## <a name="remarks"></a>备注

如果未指定标签，则使用在行中显示其值的属性的名称。

有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

此示例显示了一个 `TableColumnHeader` 其标签为 "Column 1" 的元素。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableColumnHeader Element (Format)](./tablecolumnheader-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
