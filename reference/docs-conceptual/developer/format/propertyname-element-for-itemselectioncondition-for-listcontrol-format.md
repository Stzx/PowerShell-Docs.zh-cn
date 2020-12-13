---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for ItemSelectionCondition for ListControl (Format)
description: PropertyName Element for ItemSelectionCondition for ListControl (Format)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665985"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>PropertyName Element for ItemSelectionCondition for ListControl (Format)

指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用视图。 定义列表视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListControl (格式) ListEntry 元素 (ListItems 的 ListEntry 的元素) ListControl 的 ListItems PropertyName 元素 ListControl (格式) ItemSelectionCondition 元素

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
|[ItemSelectionCondition Element for ListItem for ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>文本值

指定显示其值的属性的名称。

## <a name="remarks"></a>备注

如果使用此元素，则在定义选择条件时，不能指定 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) 元素。

## <a name="see-also"></a>另请参阅

[ListIControl (格式的 ItemSelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[ItemSelectionCondition Element for ListItem for ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
