---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for TableControl (Format)
description: SelectionSetName Element for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: a5a395f718d0e1a2d7f33d120ce4fd2ff787cc34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651785"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a>SelectionSetName Element for EntrySelectedBy for TableControl (Format)

指定使用此表视图项的一组 .NET 类型。 对于可为条目指定的选项集数没有限制。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy 元素 (SelectionSetName) EntrySelectedBy (格式) 

## <a name="syntax"></a>语法

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|定义使用此项的 .NET 类型或此项要使用的条件。|

## <a name="text-value"></a>文本值

指定选择集的名称。

## <a name="remarks"></a>备注

当要定义在多个视图中使用的一组对象时，通常使用选择集。 例如，您可能希望为同一组对象创建表视图和列表视图。 有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。

如果为某个条目指定了选择集，则无法指定类型名称。 有关如何指定 .NET 类型的详细信息，请参阅 [EntrySelectedBy For TableRowEntry 的 TypeName 元素 (Format) ](./typename-element-for-entryselectedby-for-tablecontrol-format.md)。

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="see-also"></a>另请参阅

[EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[为视图定义对象集](./defining-selection-sets.md)

[创建表视图](./creating-a-table-view.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
