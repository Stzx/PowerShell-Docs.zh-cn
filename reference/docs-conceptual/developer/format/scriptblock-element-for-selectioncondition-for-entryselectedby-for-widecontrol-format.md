---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)
description: ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651960"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a>ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)

指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用宽输入定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 WideEntry 元素) 格式 (

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

|元素|描述|
|-------------|-----------------|
|[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|定义要使用此定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。

有关大视图的其他组件的详细信息，请参阅 [宽视图](./creating-a-wide-view.md)。

## <a name="see-also"></a>另请参阅

[创建宽视图](./creating-a-wide-view.md)

[定义显示数据的条件](./defining-conditions-for-displaying-data.md)

[PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
