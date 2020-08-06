---
title: 配置 (格式的控件的 ItemSeclectionCondition 的 PropertyName 元素) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0e304af1dbe816753d6dcd1dd8149f950f2a0941
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785585"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)

指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for 的 CustomEntry 元素配置 (格式) 的 CustomEntry 的 CustomItem 元素，用于 ExpressionBinding 的元素 for CustomItem for configuration 元素 for for for for Control for for Control for for Control for for Control for control (format 元素 for ItemSelectionCondition for configuration) 格式的控件 ()  (

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
|[ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|定义要使用此控件必须存在的条件。|

## <a name="text-value"></a>文本值

指定触发条件的 .NET 属性的名称。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)元素。

## <a name="see-also"></a>另请参阅

[ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
