---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for CustomEntry for View (Format)
description: TypeName Element for EntrySelectedBy for CustomEntry for View (Format)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645738"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a>TypeName Element for EntrySelectedBy for CustomEntry for View (Format)

指定使用自定义控件视图的此定义的 .NET 类型。 对于可以为定义指定的类型数量没有限制。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries 的 EntrySelectedBy 元素 (CustomEntry for view) 格式 (的 TypeName 元素) 

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
|[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|定义使用此自定义控件视图定义或要使用此定义必须存在的条件的 .NET 类型。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

每个自定义控件视图定义都必须定义至少一个类型名称、选择集或选择条件。

有关自定义控件视图组件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。

## <a name="see-also"></a>另请参阅

[创建自定义控件](./creating-custom-controls.md)

[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
