---
ms.date: 09/13/2016
ms.topic: reference
title: CustomItem Element for CustomEntry for GroupBy (Format)
description: CustomItem Element for CustomEntry for GroupBy (Format)
ms.openlocfilehash: 5db23ad4dad5bd66ea64b9c6e91b8224a4aa4eca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645988"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>CustomItem Element for CustomEntry for GroupBy (Format)

定义自定义控件视图显示的数据及其显示方式。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for GroupBy (格式) 

## <a name="syntax"></a>语法

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ExpressionBinding Element for CustomItem for GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)|可选元素。<br /><br /> 定义控件显示的数据。|
|[Frame Element for CustomItem for GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)|可选元素。<br /><br /> 定义自定义控件视图显示的数据及其显示方式。|
|[NewLine Element for CustomItem for GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md)|可选元素。<br /><br /> 向控件的显示添加一个空白行。|
|[Text Element for CustomItem for GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md)|可选元素。<br /><br /> 指定由控件显示的数据的附加文本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntry Element for CustomControl for GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|提供自定义控件视图的定义。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[CustomEntry Element for CustomControl for GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)

[ExpressionBinding Element for CustomItem for GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Frame Element for CustomItem for GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)

[NewLine Element for CustomItem for GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md)

[Text Element for CustomItem for GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
