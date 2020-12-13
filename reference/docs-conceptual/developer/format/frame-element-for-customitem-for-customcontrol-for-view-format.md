---
ms.date: 09/13/2016
ms.topic: reference
title: Frame Element for CustomItem for CustomControl for View (Format)
description: Frame Element for CustomItem for CustomControl for View (Format)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652191"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>Frame Element for CustomItem for CustomControl for View (Format)

定义数据的显示方式，例如，将数据向左或向右移动。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries for CustomItem 的 CustomEntry 元素 (CustomControlView 的 CustomItem 元素) CustomControl (格式) 

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
|[FirstLineHanging 元素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定将第一行数据向左移动的字符数。|
|[FirstLineIndent 元素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定第一行数据向右移动的字符数。|
|[LeftIndent 元素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定数据从左边距向外移动的字符数。|
|[RightIndent 元素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定数据从右边缘向外移动的字符数。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View (格式的 CustomEntry 的 CustomItem 元素) ](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|定义控件显示的数据及其显示方式。|

## <a name="remarks"></a>备注

不能在同一元素中指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) 和 [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) 元素 `Frame` 。

## <a name="see-also"></a>另请参阅

[FirstLineHanging 元素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[FirstLineIndent 元素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[LeftIndent 元素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[RightIndent 元素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[View (格式的 CustomEntry 的 CustomItem 元素) ](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
