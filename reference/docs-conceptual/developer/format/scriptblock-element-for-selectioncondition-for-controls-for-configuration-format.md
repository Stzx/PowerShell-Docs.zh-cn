---
title: 用于 SelectionCondition 的控件的 ScriptBlock 元素) 配置 (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 24584aacd7869abd3dcfc6ff546e6dea4c2c04fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785432"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a>ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)

指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素的的 CustomEntry 元素 CustomControl for control for control (Format) EntrySelectedBy 元素 for CustomEntry for control (Format for for control Format) SelectionCondition 元素 for EntrySelectedBy for control (format) 

## <a name="syntax"></a>语法

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|定义要使用的公共控件定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
