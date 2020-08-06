---
title: 用于) 配置 (格式的控件的 CustomControl 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8b9d18bbb1abce8135f4c27418ad54a1736eb5a6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785925"
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

|元素|说明|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。|
|[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|必需的元素。<br /><br /> 定义控件显示的数据及其显示方式。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|提供公共控件的定义。|

## <a name="remarks"></a>备注

在大多数情况下，每个公共自定义控件只需要一个定义，但如果您希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。 在这些情况下，可以为每个对象或一组对象提供单独的定义。

## <a name="see-also"></a>另请参阅

[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
