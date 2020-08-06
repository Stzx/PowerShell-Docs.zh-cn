---
title: 对于 GroupBy (Format) ，为 ItemSelectionCondition 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f6d671035bfd2ef6323b638fdd951bb020bd6548
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780876"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a>PropertyName Element for ItemSelectionCondition for GroupBy (Format)

指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) 的 GroupBy 元素 (的 CustomEntries 元素对于 groupby) 格式 (CustomControl 的元素) CustomEntry 元素 for CustomControl 对于 GroupBy (格式) CustomItem 元素 for CustomEntry for GroupBy (Format) ExpressionBinding 元素 for CustomItem for groupby (format) ItemSelectionCondition 元素 for ExpressionBinding for groupby (format) 

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
|[ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|定义要使用此控件必须存在的条件。|

## <a name="text-value"></a>文本值

指定触发条件的 .NET 属性的名称。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)元素。

## <a name="see-also"></a>另请参阅

[ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
