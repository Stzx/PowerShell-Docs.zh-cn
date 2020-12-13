---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControlName Element for GroupBy (Format)
description: CustomControlName Element for GroupBy (Format)
ms.openlocfilehash: 03664fe4d5559312e2720a3892493c90c15f7501
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655422"
---
# <a name="customcontrolname-element-for-groupby-format"></a>CustomControlName Element for GroupBy (Format)

指定用于显示新组的自定义控件的名称。 定义表、列表、宽或自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (GroupBy) 格式的 CustomControlName 元素 (

## <a name="syntax"></a>语法

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)|定义 Windows PowerShell 如何显示一组新的对象。|

## <a name="text-value"></a>文本值

指定用于显示新组的自定义控件的名称。

## <a name="remarks"></a>备注

您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。 以下元素指定这些自定义控件的名称：

- [Name Element for Control for Controls for Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Name Element for Control for Controls for View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>另请参阅

[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)

[Name Element for Control for Controls for Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Name Element for Control for Controls for View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
