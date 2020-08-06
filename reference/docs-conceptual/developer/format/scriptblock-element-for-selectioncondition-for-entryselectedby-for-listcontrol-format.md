---
title: 用于 ListControl (Format) 的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 56bd04c9af74bdaa7a186a208fc15a67cb08b004
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772852"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)

指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) EntrySelectedBy 的 ListEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 ListEntry 元素) 格式 (

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
|[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|定义要使用此列表项必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

选择条件必须指定至少一个要计算的脚本或属性名称，但不能同时指定两者。  (有关如何使用选择条件的详细信息，请参阅为[使用视图条目或项定义条件](./defining-conditions-for-displaying-data.md)。 ) 

有关列表视图的其他组件的详细信息，请参阅[列表视图](./creating-a-list-view.md)。

## <a name="see-also"></a>另请参阅

[ListEntry 元素 (格式) ](./listentry-element-for-listcontrol-format.md)

[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[列表视图](./creating-a-list-view.md)

[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)

[编写 Windows PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
