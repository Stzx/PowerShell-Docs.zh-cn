---
ms.date: 09/13/2016
ms.topic: reference
title: CustomItem Element for CustomEntry for Controls for Configuration (Format)
description: CustomItem Element for CustomEntry for Controls for Configuration (Format)
ms.openlocfilehash: 06c399e982b6ac0fba9c11e20c468fe8bef6f694
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666767"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>CustomItem Element for CustomEntry for Controls for Configuration (Format)

定义控件显示的数据及其显示方式。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 元素 for CustomItem 的控件

## <a name="syntax"></a>语法

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomItem` 。 有关详细信息，请参阅“备注”。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 定义控件显示的数据。|
|[Frame Element for CustomItem for Controls for Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 定义数据的显示方式，例如，将数据向左或向右移动。|
|[NewLine Element for CustomItem for Controls for Configuration (Format)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 向控件的显示添加一个空白行。|
|[Text Element for CustomItem for Controls for Configuration (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 向控件的显示添加文本，如括号或方括号。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntry Element for CustomControl for Controls for Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|提供控件的定义。|

## <a name="remarks"></a>备注

指定元素的子元素时 `CustomItem` ，请记住以下事项：

- 必须按以下顺序添加子元素： `ExpressionBinding` 、 `NewLine` 、 `Text` 和 `Frame` 。

- 您可以指定的序列数量没有最大限制。

- 在每个序列中，可使用的元素数没有最大限制 `ExpressionBinding` 。

## <a name="see-also"></a>另请参阅

[ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Frame Element for CustomItem for Controls for Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[NewLine Element for CustomItem for Controls for Configuration (Format)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Text Element for CustomItem for Controls for Configuration (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
