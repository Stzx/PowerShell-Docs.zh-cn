---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ListItem for ListControl (Format)
description: ItemSelectionCondition Element for ListItem for ListControl (Format)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667804"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>ItemSelectionCondition Element for ListItem for ListControl (Format)

定义要使用此列表项必须存在的条件。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntries for ListControl 的 ListItems 元素) ListEntry 的 ListControl 的 ListItems 元素 (ListControl) 格式 (ItemSelectionCondition 元素

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
|[PropertyName Element for ItemSelectionCondition for ListControl (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|可选元素。<br /><br /> 指定触发条件的 .NET 属性。|
|[ScriptBlock Element for ItemSelectionCondition for ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|可选元素。<br /><br /> 指定触发条件的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ListItem Element for ListItems for ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|定义其值显示在列表视图的行中的属性或脚本。|

## <a name="remarks"></a>备注

您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。

## <a name="see-also"></a>另请参阅

[ListItem Element for ListItems for ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[PropertyName Element for ItemSelectionCondition for ListControl (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[ScriptBlock Element for ItemSelectionCondition for ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
