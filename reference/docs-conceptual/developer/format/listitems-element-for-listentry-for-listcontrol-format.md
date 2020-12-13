---
ms.date: 09/13/2016
ms.topic: reference
title: ListItems Element for ListEntry for ListControl (Format)
description: ListItems Element for ListEntry for ListControl (Format)
ms.openlocfilehash: 1553c81bc559020223a3c1fea10336baf017c9a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666529"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>ListItems Element for ListEntry for ListControl (Format)

定义其值显示在列表视图的行中的属性和脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素对于列表控件 (格式) ListControl (格式) ListItems 元素 (ListControl) 格式

## <a name="syntax"></a>语法

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ListItems` 。 对于可以指定的子元素数没有限制。 子元素的顺序定义值在列表视图中的显示顺序。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ListControl (格式的元素) ](./listitem-element-for-listitems-for-listcontrol-format.md)|必需的元素。<br /><br /> 定义其值由列表视图显示的属性或脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ListEntry Element for ListControl (Format)](./listentry-element-for-listcontrol-format.md)|提供列表视图的定义。|

## <a name="remarks"></a>备注

有关此类视图的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

此示例显示了用于定义列表视图的三行的 XML 元素。

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a>另请参阅

[ListEntry Element for ListControl (Format)](./listentry-element-for-listcontrol-format.md)

[ListControl (格式的元素) ](./listitem-element-for-listitems-for-listcontrol-format.md)

[创建列表视图](./creating-a-list-view.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
