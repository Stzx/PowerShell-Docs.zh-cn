---
title: TableControl (Format) 的 TableRowEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 047a10fb6b38dfa8f78a7741fd50b781d4a14b6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787693"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a>EntrySelectedBy Element for TableRowEntry for TableControl (Format)

定义使用表视图的此定义的 .NET 类型或要使用此定义时必须存在的条件。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 元素 (格式) 

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

|元素|说明|
|-------------|-----------------|
|[SelectionCondition Element for EntrySelectedBy for TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|可选元素。<br /><br /> 定义要使用此表视图定义必须存在的条件。|
|[SelectionSetName Element for EntrySelectedBy for TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|可选元素。<br /><br /> 指定一组使用此表视图定义的 .NET 类型。|
|[TypeName Element for EntrySelectedBy for TableControl (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|可选元素。<br /><br /> 指定使用此表视图定义的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[TableControl 的 TableRowEntry 元素 (格式) ](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|定义在表的行中显示的数据。|

## <a name="remarks"></a>备注

对于表视图定义，必须至少指定一个类型、选择集或选择条件。 您可以使用的子元素数没有最大限制。

选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。 有关选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。

有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `TableRowEntry` 元素，该元素用于显示[system.object](/dotnet/api/System.Diagnostics.Process)对象的属性。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[SelectionCondition Element for EntrySelectedBy for TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[SelectionSetName Element for EntrySelectedBy for TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[TableControl 的 TableRowEntry 元素 (格式) ](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[TypeName Element for EntrySelectedBy for TableControl (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
