---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for WideControl (Format)
description: SelectionSetName Element for EntrySelectedBy for WideControl (Format)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651702"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a>SelectionSetName Element for EntrySelectedBy for WideControl (Format)

为定义指定一组 .NET 对象。 当显示其中一个对象时，将使用该定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (SelectionSetName) 格式

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
|[EntrySelectedBy Element for WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md)|定义使用此宽项的 .NET 类型或此项要使用的条件。|

## <a name="text-value"></a>文本值

指定选择集的名称。

## <a name="remarks"></a>备注

每个定义必须指定一个类型名称、选择集或选择条件。

当要定义在多个视图中使用的一组对象时，通常使用选择集。 例如，您可能希望为同一组对象创建表视图和列表视图。 有关定义选择集的详细信息，请参阅为 [视图定义对象集](./defining-selection-sets.md)。

有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。

## <a name="see-also"></a>另请参阅

[创建宽视图](./creating-a-wide-view.md)

[定义选项集](./defining-selection-sets.md)

[EntrySelectedBy Element for WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
