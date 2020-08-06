---
title: 用于) 配置 (格式的控件的 CustomItem 的 ExpressionBinding 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1ad83fa9d915822eaefb490658f8a219defdddf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773906"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a>ExpressionBinding Element for CustomItem for Controls for Configuration (Format)

定义控件显示的数据。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的的 CustomEntry 元素 (CustomControl 的元素 for CustomItem 的控件 CustomEntry 的控件) 

## <a name="syntax"></a>语法

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ExpressionBinding` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|`CustomControl Element`|可选元素。<br /><br /> 定义此控件使用的控件。|
|[CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定公共控件或视图控件的名称。|
|[EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定控件所显示的集合元素。|
|[ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 定义要使用此公共控件必须存在的条件。|
|[PropertyName Element for ExpressionBinding for Controls for Configuration (Format)](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定 .NET 属性，其值由公共控件显示。|
|[ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|可选元素。<br /><br /> 指定其值由公共控件显示的脚本。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|定义自定义控件视图显示的数据及其显示方式。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[用于配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
