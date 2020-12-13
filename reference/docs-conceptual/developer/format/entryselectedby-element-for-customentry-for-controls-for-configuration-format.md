---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)
description: EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666665"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)

定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 的控件) 

## <a name="syntax"></a>语法

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 定义要使用的公共控件定义必须存在的条件。|
|[SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定一组使用此公共控件定义的 .NET 类型。|
|[TypeName Element for EntrySelectedBy for Controls for Configuration (Format)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定使用此公共控件定义的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntry Element for CustomControl for Controls for Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|提供公共控件的定义。|

## <a name="remarks"></a>备注

每个定义至少必须指定一个 .NET 类型、选择集或选择条件。 对于可以指定的类型、选择集或选择条件的数量没有最大限制。

## <a name="see-also"></a>另请参阅

[SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[CustomEntry Element for CustomControl for Controls for Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[TypeName Element for EntrySelectedBy for Controls for Configuration (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
