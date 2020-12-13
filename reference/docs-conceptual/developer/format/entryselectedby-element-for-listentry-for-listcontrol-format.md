---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for ListEntry for ListControl (Format)
description: EntrySelectedBy Element for ListEntry for ListControl (Format)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652293"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>EntrySelectedBy Element for ListEntry for ListControl (Format)

定义使用此列表视图定义或要使用此定义必须存在的条件的 .NET 类型。 在大多数情况下，列表视图只需要一个定义。 但是，如果您希望使用同一列表视图为不同对象显示不同的数据，则可以为列表视图提供多个定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntry ListControl EntrySelectedBy 的 ListEntry 元素) 格式 (

## <a name="syntax"></a>语法

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ListControl (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|可选元素。<br /><br /> 定义要使用此列表视图定义必须存在的条件。|
|[SelectionSetName Element for EntrySelectedBy for ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|可选元素。<br /><br /> 指定一组使用此列表视图定义的 .NET 类型。|
|[TypeName Element for EntrySelectedBy for ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md)|可选元素。<br /><br /> 指定使用此列表视图定义的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ListEntry Element for ListControl (Format)](./listentry-element-for-listcontrol-format.md)|定义列表行的显示方式。|

## <a name="remarks"></a>备注

对于列表视图定义，必须至少指定一个类型、选择集或选择条件。 您可以使用的子元素数没有最大限制。

选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。 有关选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。

有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

下面的示例演示如何使用 .NET 类型名称定义列表视图的对象。

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>另请参阅

[ListEntry Element for ListControl (Format)](./listentry-element-for-listcontrol-format.md)

[SelectionCondition Element for EntrySelectedBy for ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[SelectionSetName Element for EntrySelectedBy for ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[TypeName Element for EntrySelectedBy for ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[创建列表视图](./creating-a-list-view.md)

[定义显示数据的条件](./defining-conditions-for-displaying-data.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
