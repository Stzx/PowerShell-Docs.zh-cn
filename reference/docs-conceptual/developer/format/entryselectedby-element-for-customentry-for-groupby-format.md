---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for CustomEntry for GroupBy (Format)
description: EntrySelectedBy Element for CustomEntry for GroupBy (Format)
ms.openlocfilehash: 5af4abe081ca268699d281a1b586a584107b9a83
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652355"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>EntrySelectedBy Element for CustomEntry for GroupBy (Format)

定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for 元素 for CustomControl for groupby (format) CustomEntry 元素 for CustomControl for groupby (格式) EntrySelectedBy 元素

## <a name="syntax"></a>语法

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。 必须为定义至少指定一个类型、选择集或选择条件。 您可以使用的子元素数没有最大限制。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[SelectionCondition Element for EntrySelectedBy for GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|可选元素。<br /><br /> 定义要使用此定义必须存在的条件。|
|[SelectionSetName Element for EntrySelectedBy for GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|可选元素。<br /><br /> 指定一组使用此控件定义的 .NET 类型。|
|[TypeName Element for EntrySelectedBy for GroupBy (Format)](./typename-element-for-entryselectedby-for-groupby-format.md)|可选元素。<br /><br /> 指定使用控件的此定义的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntry Element for CustomControl for GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|提供控件的定义。|

## <a name="remarks"></a>备注

选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。 有关选择条件的详细信息，请参阅 [定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[SelectionCondition Element for EntrySelectedBy for GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[SelectionSetName Element for EntrySelectedBy for GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[TypeName Element for EntrySelectedBy for GroupBy (Format)](./typename-element-for-entryselectedby-for-groupby-format.md)

[CustomEntry Element for CustomEntries for Controls for View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
