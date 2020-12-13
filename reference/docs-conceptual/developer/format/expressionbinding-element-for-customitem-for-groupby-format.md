---
ms.date: 09/13/2016
ms.topic: reference
title: ExpressionBinding Element for CustomItem for GroupBy (Format)
description: ExpressionBinding Element for CustomItem for GroupBy (Format)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655302"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>ExpressionBinding Element for CustomItem for GroupBy (Format)

定义控件显示的数据。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (格式) 

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

|元素|描述|
|-------------|-----------------|
|`CustomControl Element`|可选元素。<br /><br /> 定义此控件使用的控件。|
|[CustomControlName Element for ExpressionBinding for GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|可选元素。<br /><br /> 指定公共控件或视图控件的名称。|
|[GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) ](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) |可选元素。<br /><br /> 指定显示集合的元素。|
|[ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|可选元素。<br /><br /> 定义要使用此控件必须存在的条件。|
|[PropertyName Element for ExpressionBinding for GroupBy (Format)](./propertyname-element-for-expressionbinding-for-groupby-format.md)|可选元素。<br /><br /> 指定其值由控件显示的 .NET 属性。|
|[ScriptBlock Element for ExpressionBinding for GroupBy (Format)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|可选元素。<br /><br /> 指定其值由控件显示的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|定义自定义控件视图显示的数据及其显示方式。|

## <a name="see-also"></a>另请参阅

[CustomControlName Element for ExpressionBinding for GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[PropertyName Element for ExpressionBinding for GroupBy (Format)](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[ScriptBlock Element for ExpressionBinding for GroupBy (Format)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
