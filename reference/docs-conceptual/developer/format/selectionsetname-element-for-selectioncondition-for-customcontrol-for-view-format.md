---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for SelectionCondition for CustomControl for View (Format)
description: SelectionSetName Element for SelectionCondition for CustomControl for View (Format)
ms.openlocfilehash: 839032048739e529057d7066fb3bc6aa2fbc5037
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651610"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a>SelectionSetName Element for SelectionCondition for CustomControl for View (Format)

指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) EntrySelectedBy 的 CustomEntry 元素 (

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
|[用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|定义要使用的控件定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定选择集的名称。

## <a name="remarks"></a>备注

选择集是可由格式设置文件所定义的任何视图使用的常用 .NET 对象组。 有关创建和引用选项集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。

选择条件可以指定选择集或 .NET 类型，但不能同时指定两者。 有关如何使用选择条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另请参阅

[用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[定义显示数据的条件](./defining-conditions-for-displaying-data.md)

[定义选项集](./defining-selection-sets.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
