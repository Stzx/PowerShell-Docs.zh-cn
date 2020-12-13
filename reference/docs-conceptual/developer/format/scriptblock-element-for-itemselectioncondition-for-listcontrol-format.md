---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSelectionCondition for ListControl (Format)
description: ScriptBlock Element for ItemSelectionCondition for ListControl (Format)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665049"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>ScriptBlock Element for ItemSelectionCondition for ListControl (Format)

指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。 定义列表视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素，适用于 ListControl (格式) ListEntry for ListEntries 的 ListControl 元素 (ListItems 的 ListEntry 的 ListControl 元素) ListItems 的 ItemSelectionCondition (格式) ListControl (格式) ItemSelectionCondition 元素 (格式) 

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
|[ItemSelectionCondition Element for ListItem for ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|定义要使用此列表项必须存在的条件。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

如果使用此元素，则在 `PropertyName` 定义选择条件时，不能指定元素。

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
