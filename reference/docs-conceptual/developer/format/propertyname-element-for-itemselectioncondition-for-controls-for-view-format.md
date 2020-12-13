---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for ItemSelectionCondition for Controls for View (Format)
description: PropertyName Element for ItemSelectionCondition for Controls for View (Format)
ms.openlocfilehash: 9fb7a21e19338dbf59dab14291e1b02736835040
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645805"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a>PropertyName Element for ItemSelectionCondition for Controls for View (Format)

指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) CustomEntry 的 CustomEntries 元素对于视图 (格式的控件) 用于视图 (格式的控件的 CustomEntry 的控件) ExpressionBinding 元素，适用于视图 (格式的 CustomItem 的控件) ItemSelectionCondition 的控件 (ExpressionBinding 的控件) 

## <a name="syntax"></a>语法

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|定义要使用此控件必须存在的条件。|

## <a name="text-value"></a>文本值

指定触发条件的 .NET 属性的名称。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) 元素。

## <a name="see-also"></a>另请参阅

[ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
