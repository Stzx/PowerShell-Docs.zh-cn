---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for SelectionCondition for CustomControl for View (Format)
description: PropertyName Element for SelectionCondition for CustomControl for View (Format)
ms.openlocfilehash: 1dd325a58b29a0f13b1341559c2a7dfe251c6b36
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665849"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a>PropertyName Element for SelectionCondition for CustomControl for View (Format)

指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 用于视图 (格式的 CustomControl CustomEntries 元素) CustomEntry 的的元素 (CustomEntries 的 CustomControl 元素对于 CustomEntry for CustomControl for View (Format) EntrySelectedBy 元素 for CustomEntry for CustomControl for SelectionCondition for view (Format) EntrySelectedBy for CustomControl 的 SelectionCondition 元素 CustomControl for View (Format) 

## <a name="syntax"></a>语法

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|定义要使用的控件定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 属性名称。

## <a name="remarks"></a>备注

选择条件必须指定至少一个属性名称或脚本，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
