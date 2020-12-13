---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)
description: ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665125"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)

指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 CustomControl 的元素 (CustomEntry 的 CustomEntries 元素 CustomEntry for View (Format) ExpressionBinding 元素 for CustomItem for CustomControl for for View (Format) ItemSelectionCondition 元素 for CustomControl for ItemSelectionCondition for CustomControl for view (格式) ScriptBlock 元素 (

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
|[CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|定义要使用此控件必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定 [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) 元素。

## <a name="see-also"></a>另请参阅

[PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
