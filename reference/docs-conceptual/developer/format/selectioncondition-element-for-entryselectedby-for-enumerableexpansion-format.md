---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)
description: SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 3ecf7fde99b9ee66a153eea416792f351ff62af3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647929"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a>SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)

定义扩展此定义的集合对象时必须存在的条件。

配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition) 格式 (EntrySelectedBy 元素) 

## <a name="syntax"></a>语法

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。 您必须指定一个 `PropertyName` 或 `ScriptBlock` 元素。 `SelectionSetName`和 `TypeName` 元素是可选的。 可以指定任一元素中的一个。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|
|[SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型集。|
|[TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|定义通过此定义扩展哪些 .NET 集合对象。|

## <a name="remarks"></a>备注

每个定义都必须定义至少一个类型名称、选择集或选择条件。

定义选择条件时，需要满足以下要求：

- 选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。

- 选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。

有关如何使用选择条件的详细信息，请参阅 [定义 Diplaying 数据的条件](./defining-conditions-for-displaying-data.md)。

有关大视图的其他组件的详细信息，请参阅 [宽视图](./creating-a-wide-view.md)。

## <a name="see-also"></a>另请参阅

[定义显示数据的条件](./defining-conditions-for-displaying-data.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
