---
ms.date: 09/13/2016
ms.topic: reference
title: ExpressionBinding Element for CustomItem for CustomControl for View (Format)
description: ExpressionBinding Element for CustomItem for CustomControl for View (Format)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648185"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>ExpressionBinding Element for CustomItem for CustomControl for View (Format)

定义控件显示的数据。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 用于视图 (格式的 CustomEntries 元素) CustomEntry for CustomEntries 的 CustomControl 元素 (CustomControl for CustomItem for CustomEntry 的 CustomControl 元素) ExpressionBinding 元素 for CustomItem for CustomControl for view (format) 

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
|[CustomControlName Element for ExpressionBinding for CustomControl for View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定公共控件或视图控件的名称。|
|[EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定显示集合的元素。|
|[用于 CustomControl for View (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素 ](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|可选元素。<br /><br /> 定义要使用此控件必须存在的条件。|
|[PropertyName Element for ExpressionBinding for CustomControl for View (Format)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定其值由控件显示的 .NET 属性。|
|[用于 CustomCustomControl 的 ExpressionBinding 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定其值由控件显示的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomItem Element for CustomEntry for CustomControl for View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|定义自定义控件视图显示的数据及其显示方式。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[CustomControlName Element for ExpressionBinding for CustomControl for View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[用于 CustomControl for View (Format) 的 ExpressionBinding 的 ItemSelectionCondition 元素 ](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[PropertyName Element for ExpressionBinding for CustomControl for View (Format)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomItem Element for CustomEntry for CustomControl for View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
