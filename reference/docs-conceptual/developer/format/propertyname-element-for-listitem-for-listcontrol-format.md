---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for ListItem for ListControl (Format)
description: PropertyName Element for ListItem for ListControl (Format)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665968"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>PropertyName Element for ListItem for ListControl (Format)

指定其值显示在列表中的 .NET 属性。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) ListItems 元素 (格式) 名称 (格式) 

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
|[ (格式的) 元素元素 ](./listitem-element-for-listitems-for-listcontrol-format.md)|定义其值显示在列表视图的行中的属性或脚本。|

## <a name="text-value"></a>文本值

指定显示其值的属性的名称。

## <a name="remarks"></a>备注

如果指定此元素，则不能指定 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) 元素。

除了显示属性值以外，还可以指定值的标签或可用于更改值显示的格式字符串。 有关在列表视图中指定数据的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

下面的示例演示如何指定显示其值的标签和属性。

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a>另请参阅

[ScriptBlock Element for ListItem for ListControl (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[创建列表视图](./creating-a-list-view.md)

[ListControl (格式的元素) ](./listitem-element-for-listitems-for-listcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
