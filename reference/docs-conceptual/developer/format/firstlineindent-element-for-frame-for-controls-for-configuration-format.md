---
ms.date: 09/13/2016
ms.topic: reference
title: FirstLineIndent Element for Frame for Controls for Configuration (Format)
description: FirstLineIndent Element for Frame for Controls for Configuration (Format)
ms.openlocfilehash: 59a41410160879c2414819de4d367ecdedd8e182
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660158"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a>FirstLineIndent Element for Frame for Controls for Configuration (Format)

指定第一行数据向右移动的字符数。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) CustomEntries 元素，用于 CustomControl 的 for configuration (格式) CustomEntry 元素对于 CustomControl for control for control (Format) CustomItem 元素 For CustomEntry For CustomItem For control for For control for For control for For control for For control for control (format 的控件，用于配置的控件 () 

## <a name="syntax"></a>语法

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `FirstLineIndent` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[Frame Element for CustomItem for Controls for Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|定义数据的显示方式，例如，将数据向左或向右移动。|

## <a name="text-value"></a>文本值

指定要将数据的第一行移动到的字符数。

## <a name="remarks"></a>备注

如果指定此元素，则不能指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) 元素。

## <a name="see-also"></a>另请参阅

[FirstLineHanging Element for Frame for Controls for Configuration (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Frame Element for CustomItem for Controls for Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
