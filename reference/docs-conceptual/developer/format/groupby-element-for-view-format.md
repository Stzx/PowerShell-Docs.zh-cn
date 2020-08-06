---
title: View (Format) 的 GroupBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2f9071a3ebbc7cc2ccb7721dd518e82723e9cc4e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781420"
---
# <a name="groupby-element-for-view-format"></a>GroupBy Element for View (Format)

定义如何显示新的对象组。 定义表、列表、宽或自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式)  (的 GroupBy 元素) 格式

## <a name="syntax"></a>语法

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[CustomControl Element for GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|可选元素。<br /><br /> 定义显示新组的自定义控件。|
|[CustomControlName Element for GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)|可选元素。<br /><br /> 指定用于显示新组的控件的名称。|
|[Label Element for GroupBy (Format)](./label-element-for-groupby-format.md)|可选元素。<br /><br /> 指定在遇到新组时显示的标签。|
|[PropertyName Element for GroupBy (Format)](./propertyname-element-for-groupby-format.md)|可选元素。<br /><br /> 指定 .NET 属性，在新组的值发生更改时启动新组。|
|[ScriptBlock Element for GroupBy (Format)](./scriptblock-element-for-groupby-format.md)|可选元素。<br /><br /> 指定在新组的值发生更改时启动新组的脚本。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义一个视图，该视图显示一个或多个 .NET 对象。|

## <a name="remarks"></a>备注

定义如何显示新的对象组时，您必须指定将启动新组的属性或脚本。但是，不能同时指定两者。

## <a name="see-also"></a>另请参阅

[CustomControlName Element for GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

[Label Element for GroupBy (Format)](./label-element-for-groupby-format.md)

[PropertyName Element for GroupBy (Format)](./propertyname-element-for-groupby-format.md)

[ScriptBlock Element for GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[View Element (Format)](./view-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
