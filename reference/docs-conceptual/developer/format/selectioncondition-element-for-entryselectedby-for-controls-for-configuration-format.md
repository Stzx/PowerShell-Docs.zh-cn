---
title: 用于) 配置 (格式的控件的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 748aa1aa0ba603a44334d9401e9e2c0e68f14e03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783409"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)

定义要使用的公共控件定义必须存在的条件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素，用于 for for for for for for for for for for for for for for for for CustomEntry CustomControl EntrySelectedBy CustomEntry) 

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
|[PropertyName Element for SelectionCondition for Controls for Configuration (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|
|[SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型集。|
|[TypeName Element for SelectionCondition for Controls for Configuration (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|定义使用此公共控件定义的此项的 .NET 类型。|

## <a name="remarks"></a>备注

定义选择条件时，必须遵循以下准则：

- 选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。

- 选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。

有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[PropertyName Element for SelectionCondition for Controls for Configuration (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[TypeName Element for SelectionCondition for Controls for Configuration (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[编写 Windows PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
