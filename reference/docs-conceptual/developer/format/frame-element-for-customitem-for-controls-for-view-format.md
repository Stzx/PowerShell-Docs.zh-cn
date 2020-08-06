---
title: View (Format) 的控件的 CustomItem 的框架元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5ade36c183a026cb9001a2abbe91d31638a87108
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773447"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>Frame Element for CustomItem for Controls for View (Format)

定义数据的显示方式，例如，将数据向左或向右移动。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomEntries 元素对于 view (格式的 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view format 的 CustomItem 元素 (CustomEntry 的控件) 的控件 (格式) ) 

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

|元素|说明|
|-------------|-----------------|
|`CustomItem Element`|必需的元素|
|[View (Format) 的控件的框架的 FirstLineHanging 元素](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定第一行向左移动的字符数。|
|[View (Format) 的控件的框架的 FirstLineIndent 元素](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定第一行向右移动的字符数。|
|[View (Format) 的控件的框架的 LeftIndent 元素](./leftindent-element-for-frame-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定数据从左边距向外移动的字符数。|
|[View (Format) 的控件的框架的 RightIndent 元素](./rightindent-element-for-frame-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定数据从右边缘向外移动的字符数。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[CustomItem Element for CustomEntry for Controls for View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)|定义控件显示的数据及其显示方式。|

## <a name="remarks"></a>备注

不能在同一元素中指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)和[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)元素 `Frame` 。

## <a name="see-also"></a>另请参阅

[View (Format) 的控件的框架的 FirstLineHanging 元素](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[View (Format) 的控件的框架的 FirstLineIndent 元素](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[View (Format) 的控件的框架的 LeftIndent 元素](./leftindent-element-for-frame-for-controls-for-view-format.md)

[View (Format) 的控件的框架的 RightIndent 元素](./rightindent-element-for-frame-for-controls-for-view-format.md)

[CustomItem Element for CustomEntry for Controls for View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
