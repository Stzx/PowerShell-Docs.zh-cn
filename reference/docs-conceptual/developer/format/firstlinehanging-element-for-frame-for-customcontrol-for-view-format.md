---
ms.date: 09/13/2016
ms.topic: reference
title: FirstLineHanging Element for Frame for CustomControl for View (Format)
description: FirstLineHanging Element for Frame for CustomControl for View (Format)
ms.openlocfilehash: 8b9601b2afd7ab5523e339fb45119f5cf9f4a535
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648149"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a>FirstLineHanging Element for Frame for CustomControl for View (Format)

指定将第一行数据向左移动的字符数。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，适用于 CustomControl for view (format) CustomEntry 元素 for for CustomEntries CustomItem CustomEntry CustomControlView CustomItem 的 CustomControl 元素 (FirstLineHanging 的 CustomControl 的元素) 格式 (

## <a name="syntax"></a>语法

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `FirstLineHanging` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[Frame Element for CustomItem for CustomControl for View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|定义数据的显示方式，例如，将数据向左或向右移动。|

## <a name="text-value"></a>文本值

指定要将数据的第一行移动到的字符数。

## <a name="remarks"></a>备注

如果指定此元素，则不能指定 [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) 元素。

## <a name="see-also"></a>另请参阅

[FirstLineIndent Element for Frame for CustomControl for View (Format)](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Frame Element for CustomItem for CustomControl for View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
