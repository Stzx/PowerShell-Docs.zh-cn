---
ms.date: 09/13/2016
ms.topic: reference
title: FirstLineIndent Element for Frame for CustomControl for View (Format)
description: FirstLineIndent Element for Frame for CustomControl for View (Format)
ms.openlocfilehash: 8dce8b4b072b754c3b7d631b3e5c321a5a3e5a3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645888"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a>FirstLineIndent Element for Frame for CustomControl for View (Format)

指定第一行数据向右移动的字符数。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries for CustomItem 的 CustomEntry 元素 (CustomControlView 的 CustomItem 元素) CustomControl 的 FirstLineIndent 元素

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
|[Frame Element for CustomItem for CustomControl for View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|定义数据的显示方式，例如，将数据向左或向右移动。|

## <a name="text-value"></a>文本值

指定要将数据的第一行移动到的字符数。

## <a name="remarks"></a>备注

如果指定此元素，则不能指定 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) 元素。

## <a name="see-also"></a>另请参阅

[FirstLineHanging Element for Frame for CustomControl for View (Format)](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Frame Element for CustomItem for CustomControl for View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
