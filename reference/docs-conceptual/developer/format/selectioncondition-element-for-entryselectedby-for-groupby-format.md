---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for GroupBy (Format)
description: SelectionCondition Element for EntrySelectedBy for GroupBy (Format)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664750"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a>SelectionCondition Element for EntrySelectedBy for GroupBy (Format)

定义要使用的控件定义必须存在的条件。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (格式) 

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

以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[PropertyName Element for SelectionCondition for GroupBy (Format)](./propertyname-element-for-selectioncondition-for-groupby-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[GroupBy (格式的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|
|[SelectionSetName Element for SelectionCondition for GroupBy (Format)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型集。|
|[GroupBy (格式的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-groupby-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)|定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|

## <a name="remarks"></a>备注

定义选择条件时，需要满足以下要求：

- 选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。

- 选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。

有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[PropertyName Element for SelectionCondition for CustomControl for View (Format)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[ScriptBlock Element for SelectionCondition for CustomControl for View (Format)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[SelectionCondition 的 SelectionSetName 元素用于视图 (格式的自定义控件) ](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[GroupBy (格式的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-groupby-format.md)

[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
