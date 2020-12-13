---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntry Element for CustomControl for Controls for Configuration (Format)
description: CustomEntry Element for CustomControl for Controls for Configuration (Format)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648280"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>CustomEntry Element for CustomControl for Controls for Configuration (Format)

提供公共控件的定义。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的控件 (CustomEntry 元素) 

## <a name="syntax"></a>语法

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。 您必须指定由定义显示的项。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。|
|[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|必需的元素。<br /><br /> 定义控件显示的数据及其显示方式。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|提供公共控件的定义。|

## <a name="remarks"></a>备注

在大多数情况下，每个公共自定义控件只需要一个定义，但如果您希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。 在这些情况下，可以为每个对象或一组对象提供单独的定义。

## <a name="see-also"></a>另请参阅

[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
