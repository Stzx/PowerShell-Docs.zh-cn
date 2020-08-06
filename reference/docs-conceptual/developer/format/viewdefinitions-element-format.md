---
title: " (格式) 的 ViewDefinitions 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772478"
---
# <a name="viewdefinitions-element-format"></a>ViewDefinitions Element (Format)

定义用于显示 .NET 对象的视图。 这些视图可以采用表格格式、列表格式、宽格式和自定义控件格式显示对象的属性和脚本值。

配置元素 (格式) ViewDefinitions (格式 XML) 元素

## <a name="syntax"></a>语法

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ViewDefinitions` 。 对于可以在格式设置文件中定义的视图数量没有限制，可以按任意顺序添加它们。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义用于显示一个或多个 .NET 对象的视图。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[Configuration Element (Format)](./configuration-element-format.md)|表示格式设置文件的顶级元素。|

## <a name="remarks"></a>备注

有关不同视图类型的组件的详细信息，请参阅以下主题：

- [创建表视图](./creating-a-table-view.md)

- [创建列表视图](./creating-a-list-view.md)

- [创建宽视图](./creating-a-wide-view.md)

- [自定义控件](./creating-custom-controls.md)

## <a name="example"></a>示例

此示例演示一个 `ViewDefinitions` 元素，该元素包含表视图和列表视图的父元素。

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>另请参阅

[Configuration Element (Format)](./configuration-element-format.md)

[View Element (Format)](./view-element-format.md)

[创建表视图](./creating-a-table-view.md)

[创建列表视图](./creating-a-list-view.md)

[创建宽视图](./creating-a-wide-view.md)

[自定义控件](./creating-custom-controls.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
