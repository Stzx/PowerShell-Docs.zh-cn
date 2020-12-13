---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)
description: ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648061"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)

定义要使用此控件必须存在的条件。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素用于视图 (格式的控件的 CustomEntries) CustomEntry 元素的格式) CustomItem 元素 For CustomEntry 的控件 For view) 格式的控件 (ExpressionBinding 元素 CustomItem 的控件) ItemSelectionCondition ( (

## <a name="syntax"></a>语法

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[PropertyName Element for ItemSelectionCondition for Controls for View (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|定义控件显示的数据。|

## <a name="remarks"></a>备注

您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。

## <a name="see-also"></a>另请参阅

[PropertyName Element for ItemSelectionCondition for Controls for View (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
