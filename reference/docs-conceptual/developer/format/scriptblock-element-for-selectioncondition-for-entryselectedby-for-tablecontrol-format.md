---
title: 用于 TableControl (Format) 的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a23d3515749393e9f5a2053634a44d1a817ebf38
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783443"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)

指定触发条件的脚本块。 将此脚本的计算结果为时 `true` ，将满足条件，并使用表项。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 的 TableRowEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 TableRowEntry 元素) 格式 (

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
|[TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|定义要使用此表项必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

选择条件必须指定至少一个脚本块或属性名称，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。

有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[定义显示数据的条件](./defining-conditions-for-displaying-data.md)

[PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
