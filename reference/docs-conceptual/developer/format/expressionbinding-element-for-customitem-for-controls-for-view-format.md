---
title: View (Format) 的控件的 CustomItem 的 ExpressionBinding 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773804"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>ExpressionBinding Element for CustomItem for Controls for View (Format)

定义控件显示的数据。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomEntries 元素对于视图 (格式的 CustomControl for view (format) CustomEntry 元素 For CustomEntries For view format 的控件的 CustomItem 元素 (CustomEntry for view) 格式的控件 (ExpressionBinding 元素) ) 

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
|[CustomControlName Element for ExpressionBinding for Controls for View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定公共控件或视图控件的名称。|
|[EnumerateCollection Element for ExpressionBinding for Controls for View (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定显示集合的元素。|
|[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|可选元素。<br /><br /> 定义要使用此控件必须存在的条件。|
|[PropertyName Element for ExpressionBinding for Controls for View (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定其值由控件显示的 .NET 属性。|
|[ScriptBlock Element for ExpressionBinding for Controls for View (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定其值由控件显示的脚本。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[CustomItem Element for CustomEntry for Controls for View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)|定义控件显示的数据及其显示方式。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[CustomItem Element for CustomEntry for Controls for View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[CustomControlName Element for ExpressionBinding for Controls for View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[EnumerateCollection Element for ExpressionBinding for Controls for View (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[PropertyName Element for ExpressionBinding for Controls for View (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[ScriptBlock Element for ExpressionBinding for Controls for View (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
