---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for SelectionCondition for Controls for View (Format)
description: PropertyName Element for SelectionCondition for Controls for View (Format)
ms.openlocfilehash: 7783e5a9b7f8ec3d3077d87778e9f77ffe858a7f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665866"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a>PropertyName Element for SelectionCondition for Controls for View (Format)

指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用该条目。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomEntries 元素 (Format) 用于视图 (格式的控件的 CustomEntries 的 CustomEntry 元素) EntrySelectedBy 元素 for CustomEntry for view (格式的控件) SelectionCondition 的控件 (EntrySelectedBy 的控件) 

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
|[SelectionCondition Element for EntrySelectedBy for Controls for View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|定义要使用的控件定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 属性名称。

## <a name="remarks"></a>备注

选择条件必须指定至少一个属性名称或脚本，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[SelectionCondition Element for EntrySelectedBy for Controls for View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
