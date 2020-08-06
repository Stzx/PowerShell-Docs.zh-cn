---
title: GroupBy (Format) 的 CustomItem 的框架元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785755"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>Frame Element for CustomItem for GroupBy (Format)

定义数据的显示方式，例如，将数据向左或向右移动。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomControl 元素 for CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem (格式) 

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
|[FirstLineHanging Element for Frame for GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)|可选元素。<br /><br /> 指定将第一行数据向左移动的字符数。|
|[FirstLineIndent Element for Frame for GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md)|可选元素。<br /><br /> 指定第一行数据向右移动的字符数。|
|[LeftIndent Element for Frame for GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md)|可选元素。<br /><br /> 指定数据从左边距向外移动的字符数。|
|[GroupBy (格式的帧的 RightIndent 元素) ](./rightindent-element-for-frame-for-groupby-format.md)RightIndent 元素|可选元素。<br /><br /> 指定数据从右边缘向外移动的字符数。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|定义控件显示的数据及其显示方式。|

## <a name="remarks"></a>备注

不能在同一元素中指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)和[FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md)元素 `Frame` 。

## <a name="see-also"></a>另请参阅

[FirstLineHanging Element for Frame for GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[FirstLineIndent Element for Frame for GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md)

[LeftIndent Element for Frame for GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md)

[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)

[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
