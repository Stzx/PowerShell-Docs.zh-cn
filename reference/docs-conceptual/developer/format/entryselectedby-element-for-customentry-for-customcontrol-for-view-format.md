---
title: 用于 CustomControl for View (Format) 的 CustomEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783681"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)

定义使用此自定义项的 .NET 类型或此项要使用的条件。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) EntrySelectedBy 的 CustomEntry 元素 (

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
|[CustomEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|可选元素。<br /><br /> 定义要使用此定义必须存在的条件。|
|[CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定一组使用控件视图的此定义的 .NET 类型。|
|[CustomEntry (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定使用控件视图的此定义的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View (格式的 CustomEntries 的 CustomEntry 元素) ](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|定义特定 .NET 对象使用的控件。|

## <a name="remarks"></a>备注

您必须为某个条目指定至少一个类型、选择集或选择条件。 您可以使用的子元素数没有最大限制。

选择条件用于定义要使用的项必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。 有关选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。

有关自定义控件视图组件的详细信息，请参阅[自定义控件视图](./creating-custom-controls.md)。

## <a name="see-also"></a>另请参阅

[CustomEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[CustomEntry (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[View (格式的 CustomEntries 的 CustomEntry 元素) ](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[自定义控件视图](./creating-custom-controls.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
