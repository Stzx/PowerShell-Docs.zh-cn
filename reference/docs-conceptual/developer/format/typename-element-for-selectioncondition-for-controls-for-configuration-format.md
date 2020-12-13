---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for Controls for Configuration (Format)
description: TypeName Element for SelectionCondition for Controls for Configuration (Format)
ms.openlocfilehash: fddb8ddbac7c9292a05cadfa31f98db6439a557d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659669"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a>TypeName Element for SelectionCondition for Controls for Configuration (Format)

指定触发条件的 .NET 类型。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 的控件 (CustomEntries 元素) CustomEntry 元素对于 CustomControl for control for control (format) EntrySelectedBy 元素 For CustomEntry For configuration (格式的 For EntrySelectedBy for CustomEntry 的 SelectionCondition 元素 ()  (格式的控件) 的 TypeName 元素) 

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
|[用于 CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|定义要使用的控件定义必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[用于 CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素 ](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
