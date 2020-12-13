---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)
description: ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)
ms.openlocfilehash: 853130da4489e571d7f4026a8d65d029d1889f9b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665231"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)

指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for 的 CustomEntry 元素配置 (格式) 的 CustomEntry 的 CustomItem 元素，用于 ExpressionBinding 的控件的配置元素的的控件 CustomItem 的控件) ItemSelectionCondition 的控件 (的控件) 格式 ( (

## <a name="syntax"></a>语法

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|定义要使用此控件必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定 [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) 元素。

## <a name="see-also"></a>另请参阅

[PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
