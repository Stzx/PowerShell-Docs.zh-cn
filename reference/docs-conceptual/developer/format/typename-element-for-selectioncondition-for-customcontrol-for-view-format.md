---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for CustomControl for View (Format)
description: TypeName Element for SelectionCondition for CustomControl for View (Format)
ms.openlocfilehash: ab02c6921985dbe86e5adcbc6565c76f6617399a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651291"
---
# <a name="typename-element-for-selectioncondition-for-customcontrol-for-view--format"></a>TypeName Element for SelectionCondition for CustomControl for View (Format)

指定触发条件的 .NET 类型。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) 用于视图 (格式的 CustomControl 的 CustomEntries 元素) CustomEntry for CustomEntries 的 CustomControl 元素 (CustomItem for CustomEntry for CustomControl 的 SelectionCondition 元素) EntrySelectedBy 的 CustomControl 元素 (SelectionCondition for view) 格式 (CustomControl 元素) 的 TypeName 元素 (

## <a name="syntax"></a>语法

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TypeName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|定义要使用的控件定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
