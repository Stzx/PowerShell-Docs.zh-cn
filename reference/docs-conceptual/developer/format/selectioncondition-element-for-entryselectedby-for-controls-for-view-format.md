---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionCondition Element for EntrySelectedBy for Controls for View (Format)
description: SelectionCondition Element for EntrySelectedBy for Controls for View (Format)
ms.openlocfilehash: 16b048e73195b3d6168724714ff223851dc1b20b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664845"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>SelectionCondition Element for EntrySelectedBy for Controls for View (Format)

定义要使用的控件定义必须存在的条件。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (格式) CustomEntries 元素 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view (Format 的控件的 EntrySelectedBy 元素 (CustomEntry for view) 格式的控件 (SelectionCondition 元素) ) 

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
|[PropertyName Element for SelectionCondition for Controls for View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[ScriptBlock Element for SelectionCondition for Controls for View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|
|[SelectionSetName Element for SelectionCondition for Controls for View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型集。|
|[TypeName Element for SelectionCondition for Controls for View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for Controls for View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|

## <a name="remarks"></a>备注

定义选择条件时，需要满足以下要求：

- 选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。

- 选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。

有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[PropertyName Element for SelectionCondition for Controls for View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[ScriptBlock Element for SelectionCondition for Controls for View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[SelectionSetName Element for SelectionCondition for Controls for View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[TypeName Element for SelectionCondition for Controls for View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[EntrySelectedBy Element for CustomEntry for Controls for View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
