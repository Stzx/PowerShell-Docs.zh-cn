---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)
description: SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651879"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a>SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)

指定通过此定义扩展的 .NET 类型集。

配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (SelectionSetName) 格式 (EntrySelectedBy 元素) 

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
|[EntrySelectedBy Element for EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|定义通过此定义扩展的 .NET 集合对象。|

## <a name="text-value"></a>文本值

指定选择集的名称。

## <a name="remarks"></a>备注

每个定义必须指定一个或多个类型名称、选择集或选择条件。

当要定义在多个视图中使用的一组对象时，通常使用选择集。 例如，您可能希望为同一组对象创建表视图和列表视图。 有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。

## <a name="see-also"></a>另请参阅

[定义选项集](./defining-selection-sets.md)

[EntrySelectedBy Element for EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
