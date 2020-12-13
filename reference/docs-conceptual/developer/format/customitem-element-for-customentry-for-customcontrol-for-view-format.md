---
ms.date: 09/13/2016
ms.topic: reference
title: CustomItem Element for CustomEntry for CustomControl for View (Format)
description: CustomItem Element for CustomEntry for CustomControl for View (Format)
ms.openlocfilehash: 9090a3ada5316ba5ddb4a9c46eee37c11982ae6e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666733"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>CustomItem Element for CustomEntry for CustomControl for View (Format)

定义自定义控件视图显示的数据及其显示方式。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) CustomItem 的 CustomEntry 元素 (

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
|[ExpressionBinding Element for CustomItem for CustomControl for View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 定义控件显示的数据。|
|[Frame Element for CustomItem for CustomControl for View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 定义自定义控件视图显示的数据及其显示方式。|
|[用于视图 (格式的自定义控件的 CustomItem 的换行符元素) ](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 向控件的显示添加一个空白行。|
|[用于 View (格式的 CustomControl 的 CustomItem 的文本元素) ](./text-element-for-customitem-for-customview-for-view-format.md)|可选元素。<br /><br /> 指定由控件显示的数据的附加文本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntry Element for CustomEntries for CustomControl for View (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|提供自定义控件视图的定义。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[View (格式的 CustomEntries 的 CustomEntry 元素) ](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[ExpressionBinding Element for CustomItem for CustomControl for View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[Frame Element for CustomItem for CustomControl for View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[NewLine Element for CustomItem for CustomControl for View (Format)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[用于 View (格式的 CustomControl 的 CustomItem 的文本元素) ](./text-element-for-customitem-for-customview-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
