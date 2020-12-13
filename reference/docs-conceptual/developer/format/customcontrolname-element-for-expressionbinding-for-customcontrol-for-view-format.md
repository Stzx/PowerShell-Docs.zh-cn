---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControlName Element for ExpressionBinding for CustomControl for View (Format)
description: CustomControlName Element for ExpressionBinding for CustomControl for View (Format)
ms.openlocfilehash: 24b27428c07d7178f0069f6d0e5b7ffc555efe34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666801"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a>CustomControlName Element for ExpressionBinding for CustomControl for View (Format)

指定公共控件或视图控件的名称。 定义自定义控件视图时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) 用于视图 (格式的 CustomEntries 元素) CustomEntry 的 CustomControl 的元素 (CustomEntries 的 CustomItem 的 CustomEntry 元素) ExpressionBinding 元素 for CustomItem 的 CustomControlName 元素 (CustomItem) 格式的元素 (

## <a name="syntax"></a>语法

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
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
|[CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|定义控件显示的数据。|

## <a name="text-value"></a>文本值

指定控件的名称。

## <a name="remarks"></a>备注

您可以创建可供格式设置文件的所有视图使用的公共控件，并可以创建可供特定视图使用的视图控件。 以下元素指定这些控件的名称。

- [Name Element for Control for Controls for Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Name Element for Control for Controls for View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>另请参阅

[Name Element for Control for Controls for Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Name Element for Control for Controls for View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
