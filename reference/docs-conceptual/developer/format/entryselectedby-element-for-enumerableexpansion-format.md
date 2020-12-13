---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for EnumerableExpansion (Format)
description: EntrySelectedBy Element for EnumerableExpansion (Format)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652328"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>EntrySelectedBy Element for EnumerableExpansion (Format)

定义使用此定义的 .NET 类型或要使用此定义时必须存在的条件。

配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EntrySelectedBy 元素用于 EnumerableExpansion (格式) 

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
|[SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 定义扩展此定义的集合对象时必须存在的条件。|
|[SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 指定一组使用此定义如何扩展集合对象的 .NET 类型。|
|[TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 指定使用此定义如何扩展集合对象的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EnumerableExpansion Element (Format)](./enumerableexpansion-element-format.md)|定义特定 .NET 集合对象在视图中显示的方式。|

## <a name="remarks"></a>备注

必须为定义条目指定至少一个类型、选择集或选择条件。 您可以使用的子元素数没有最大限制。

选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。 有关选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)

[EnumerableExpansion Element (Format)](./enumerableexpansion-element-format.md)

[SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
