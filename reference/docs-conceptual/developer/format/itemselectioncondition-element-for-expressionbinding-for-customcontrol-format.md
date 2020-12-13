---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)
description: ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648044"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)

定义要使用此控件必须存在的条件。 对于可为控件项指定的选择条件数没有限制。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，适用于 CustomControl for view (格式) CustomEntry 元素 for for view (format) CustomEntries 元素 for CustomItem 的 CustomEntry 元素 for ExpressionBinding 的 CustomItem 元素 (CustomControl 的 ItemSelectionCondition 元素) 

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
|[用于 View (格式的 CustomControl 的 ItemSelectionCondition 的 PropertyName 元素](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ExpressionBinding Element for CustomItem for CustomControl for View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|定义控件显示的数据。|

## <a name="remarks"></a>备注

您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)

[ExpressionBinding Element for CustomItem for CustomControl for View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
