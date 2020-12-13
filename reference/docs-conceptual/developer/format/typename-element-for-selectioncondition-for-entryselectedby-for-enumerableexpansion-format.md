---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
description: TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 1ed638f9b2194745f9ac9cab9aa3331985924886
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649718"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)

指定触发条件的 .NET 类型。

配置元素 DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionCondition 的 EntrySelectedBy 的元素) EnumerableExpansion 的 SelectionCondition (TypeName 元素) 格式 (

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
|[SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|定义扩展此定义的集合对象时必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
