---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for GroupBy (Format)
description: TypeName Element for EntrySelectedBy for GroupBy (Format)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645706"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a>TypeName Element for EntrySelectedBy for GroupBy (Format)

指定使用自定义控件的此定义的 .NET 类型。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomControl 元素 for CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) 

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
|[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)|定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

每个控件定义都必须定义至少一个类型名称、选择集或选择条件。

有关自定义控件视图组件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。

## <a name="see-also"></a>另请参阅

[创建自定义控件](./creating-custom-controls.md)

[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
