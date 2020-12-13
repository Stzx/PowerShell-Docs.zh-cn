---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
description: SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 0c9372113a79f75cfbda67acf869164fde894ee3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651587"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)

指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件。

配置元素 DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy) EnumerableExpansion 的 SelectionSetName 元素 (SelectionCondition 的 EntrySelectedBy) 格式 (

## <a name="syntax"></a>语法

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|定义扩展此定义的集合对象时必须存在的条件。|

## <a name="text-value"></a>文本值

指定选择集的名称。

## <a name="remarks"></a>备注

选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。

选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。 有关创建和引用选项集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。

## <a name="see-also"></a>另请参阅

[定义选项集](./defining-selection-sets.md)

[SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
