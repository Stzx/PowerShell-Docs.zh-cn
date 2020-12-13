---
ms.date: 09/13/2016
ms.topic: reference
title: Control Element for Controls for Configuration (Format)
description: Control Element for Controls for Configuration (Format)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655658"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Control Element for Controls for Configuration (Format)

定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。

配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素 (格式) 

## <a name="syntax"></a>语法

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Control` 。 必须仅指定每个子元素中的一个。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[CustomControl Element for Control for Controls for Configuration (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|必需的元素。<br /><br /> 定义控件。|
|[用于控件的名称元素 (格式) ](./name-element-for-control-for-controls-for-configuration-format.md)|必需的元素。<br /><br /> 指定用于引用控件的名称。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[控件的控件元素 (格式) ](./controls-element-for-configuration-format.md)|定义可由格式设置文件的所有视图或其他控件使用的公共控件。|

## <a name="remarks"></a>备注

可以在以下元素中引用为此控件指定的名称：

- [CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [View (格式的 GroupBy 元素) ](./groupby-element-for-view-format.md)

## <a name="see-also"></a>另请参阅

[控件的控件元素 (格式) ](./controls-element-for-configuration-format.md)

[用于控制配置 (格式的 CustomControl 元素) ](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[View (格式的 GroupBy 元素) ](./groupby-element-for-view-format.md)

[Name Element for Control for Controls for Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
