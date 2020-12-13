---
ms.date: 09/13/2016
ms.topic: reference
title: Alignment Element for TableColumnHeader for TableControl (Format)
description: Alignment Element for TableColumnHeader for TableControl (Format)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666818"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>Alignment Element for TableColumnHeader for TableControl (Format)

定义列标题中的数据的显示方式。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (格式) TableColumnHeader 元素 (格式) TableColumnHeader (格式的对齐元素) 

## <a name="syntax"></a>语法

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Alignment` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableColumnHeader Element (Format)](./tablecolumnheader-element-format.md)|定义表中某一列的数据的标签、宽度和对齐方式。|

## <a name="text-value"></a>文本值

指定下列值之一。 这些值不区分大小写。

如果未指定此元素，则在左侧的列中将显示数据左对齐。

右对齐显示在右侧列中的数据。

居中将列中显示的数据居中。

## <a name="remarks"></a>备注

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

此示例演示一个 `TableColumnHeader` 元素，其数据在左侧对齐。

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
