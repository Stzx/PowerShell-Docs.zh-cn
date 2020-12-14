---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for TableColumnItem for TableControl (Format)
description: PropertyName Element for TableColumnItem for TableControl (Format)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665577"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a>PropertyName Element for TableColumnItem for TableControl (Format)

指定其值显示在行的列中的属性。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) TableColumnItems 元素 (格式) TableColumnItem (格式) TableColumnItem 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableColumnItem 元素 (格式) ](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|定义其值显示在行的列中的属性或脚本。|

## <a name="text-value"></a>文本值

指定显示其值的属性的名称。

## <a name="remarks"></a>备注

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

此示例演示一个 `TableColumnItem` 元素，该元素指定了 `Status` [system.object](/dotnet/api/System.Diagnostics.Process) 对象的属性。

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[TableColumnItem 元素 (格式) ](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
