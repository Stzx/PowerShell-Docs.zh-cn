---
ms.date: 09/13/2016
ms.topic: reference
title: Frame Element for CustomItem for Controls for Configuration (Format)
description: Frame Element for CustomItem for Controls for Configuration (Format)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652245"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Frame Element for CustomItem for Controls for Configuration (Format)

定义数据的显示方式，例如，将数据向左或向右移动。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 的控件的配置框架元素) CustomItem 的控件 (

## <a name="syntax"></a>语法

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Frame` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|`CustomItem Element`|必需的元素|
|[FirstLineHanging Element for Frame for Controls for Configuration (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定将第一行数据向左移动的字符数。|
|[FirstLineIndent Element for Frame for Controls for Configuration (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定第一行数据向右移动的字符数。|
|[LeftIndent Element for Frame for Controls for Configuration (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定数据从左边距向外移动的字符数。|
|[RightIndent Element for Frame for Controls for Configuration (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定数据从右边缘向外移动的字符数。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|定义控件显示的数据及其显示方式。|

## <a name="remarks"></a>备注

不能在同一元素中指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) 和 [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) 元素 `Frame` 。

## <a name="see-also"></a>另请参阅

[FirstLineHanging Element for Frame for Controls for Configuration (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[FirstLineIndent Element for Frame for Controls for Configuration (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[LeftIndent Element for Frame for Controls for Configuration (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[RightIndent Element for Frame for Controls for Configuration (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
