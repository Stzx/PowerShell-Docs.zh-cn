---
title: 用于 CustomControl for View (Format) 的 EntrySelectedBy 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3728a1886d5406b8fa4888125d1c031d0f9b1b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785296"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a>SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)

为列表条目指定一组 .NET 对象。 对于可为条目指定的选项集数没有限制。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries 的 EntrySelectedBy 元素 (CustomEntry 的 SelectionSetName 元素 EntrySelectedBy) 格式 (

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
|[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|定义使用此自定义项的 .NET 类型或此项要使用的条件。|

## <a name="text-value"></a>文本值

指定选择集的名称。

## <a name="remarks"></a>备注

每个自定义控件项必须至少定义一个类型名称、选择集或选择条件。

当要定义在多个视图中使用的一组对象时，通常使用选择集。 例如，您可能希望为同一组对象创建表视图和列表视图。 有关定义选择集的详细信息，请参阅[定义选择集](./defining-selection-sets.md)。

有关自定义控件视图组件的详细信息，请参阅[创建自定义控件](./creating-custom-controls.md)。

## <a name="see-also"></a>另请参阅

[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[自定义控件视图](./creating-custom-controls.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
