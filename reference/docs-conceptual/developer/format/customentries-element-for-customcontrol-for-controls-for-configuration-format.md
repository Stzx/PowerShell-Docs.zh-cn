---
title: 用于) 配置 (格式的控件的 CustomControl 的 CustomEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785976"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>CustomEntries Element for CustomControl for Controls for Configuration (Format)

提供公共控件的定义。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for for Configuration) 格式 (

## <a name="syntax"></a>语法

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。 您必须指定一个或多个子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[CustomEntry Element for CustomControl for Controls for Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|提供公共控件的定义。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[用于控制配置 (格式的 CustomControl 元素) ](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|定义公共控件。|

## <a name="remarks"></a>备注

在大多数情况下，控件只有一个定义，该定义在单个元素中定义 `CustomEntry` 。 但是，如果希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。 在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。

## <a name="see-also"></a>另请参阅

[用于控制配置 (格式的 CustomControl 元素) ](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[CustomEntry Element for CustomControl for Controls for Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
