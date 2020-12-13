---
ms.date: 09/13/2016
ms.topic: reference
title: ListItem Element for ListItems for ListControl (Format)
description: ListItem Element for ListItems for ListControl (Format)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666546"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>ListItem Element for ListItems for ListControl (Format)

定义其值显示在列表视图的行中的属性或脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl 元素) ListItems (格式) ListControl 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ListItem` 。 只能指定一个属性或脚本。

### <a name="attributes"></a>特性

无

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ListControl (格式的输入字符串的格式字符串元素) ](./formatstring-element-for-listitem-for-listcontrol-format.md)|可选元素。<br /><br /> 指定定义属性或脚本值显示方式的格式字符串。|
|[ItemSelectionCondition Element for ListItem for ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|可选元素。<br /><br /> 定义要使用此列表项必须存在的条件。|
|[Label Element for ListItem for ListControl (Format)](./label-element-for-listitem-for-listcontrol-format.md)|可选元素<br /><br /> 指定在行的属性或脚本值左侧显示的标签。|
|[PropertyName Element for ListItem for ListControl (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)|可选元素。<br /><br /> 指定其值显示在行中的 .NET 属性。|
|[ScriptBlock Element for ListItem for ListControl (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)|可选元素。<br /><br /> 指定其值在行中显示的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ (格式的列表控件的 ListItems 元素) ](./listitems-element-for-listentry-for-listcontrol-format.md)|定义其值在列表视图中显示的属性和脚本。|

## <a name="remarks"></a>备注

有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

此示例显示了用于定义列表视图的三行的 XML 元素。 前两行显示 .NET 属性的值，最后一行显示脚本生成的值。

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a>另请参阅

[ListItems 元素 (格式) ](./listitems-element-for-listentry-for-listcontrol-format.md)

[输入 (格式的格式字符串元素) ](./formatstring-element-for-listitem-for-listcontrol-format.md)

[标志元素 (格式) ](./label-element-for-listitem-for-listcontrol-format.md)

[ (格式的名称名称元素) ](./propertyname-element-for-listitem-for-listcontrol-format.md)

[输入 (格式的 ScriptBlock 元素) ](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[创建列表视图](./creating-a-list-view.md)

[编写 Windows PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
