---
title: View (Format) 的控件的 ItemSelectionCondition 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c6517b8f63e0511ce071926ac3ac39ba82e7ed21
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783477"
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

|元素|说明|
|-------------|-----------------|
|[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|定义要使用此控件必须存在的条件。|

## <a name="text-value"></a>文本值

指定触发条件的 .NET 属性的名称。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)元素。

## <a name="see-also"></a>另请参阅

[ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
