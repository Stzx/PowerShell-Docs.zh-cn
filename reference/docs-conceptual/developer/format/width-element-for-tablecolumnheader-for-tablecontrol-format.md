---
ms.date: 09/13/2016
ms.topic: reference
title: Width Element for TableColumnHeader for TableControl (Format)
description: Width Element for TableColumnHeader for TableControl (Format)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658252"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>Width Element for TableColumnHeader for TableControl (Format)

定义列的字符)  (的宽度。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (TableColumnHeader) 格式 (TableHeaders) 格式 (Width 元素 TableControl) 格式

## <a name="syntax"></a>语法

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述 `Width` 定义列标题时使用的元素的属性、子元素和父元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) ](./tablecolumnheader-element-format.md)|定义表的列的数据的标签、宽度和对齐方式。|

## <a name="text-value"></a>文本值

如果出现这种情况，请指定一个大于所显示属性值长度的 (字符) 宽度。

## <a name="remarks"></a>备注

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `TableColumnHeader` 宽度为16个字符的元素。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableControl (格式的 TableHeader 的 TableColumnHeader 元素) ](./tablecolumnheader-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
