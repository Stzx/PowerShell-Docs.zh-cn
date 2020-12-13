---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for Control for Controls for View (Format)
description: Name Element for Control for Controls for View (Format)
ms.openlocfilehash: 52b7170777a35596767c34f2d58106dfa6479567
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666478"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>Name Element for Control for Controls for View (Format)

指定控件的名称。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 控件的控件 (Name 元素) Name 元素用于控件 (格式) 

## <a name="syntax"></a>语法

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Name` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View (格式的控件控件元素) ](./control-element-for-controls-for-view-format.md)|定义可供视图使用的控件以及用于引用控件的名称。|

## <a name="text-value"></a>文本值

指定用于引用控件的名称。

## <a name="remarks"></a>备注

此处指定的名称可以用在以下元素中以引用此控件。

- 创建表、列表、宽控件或自定义控件视图时，可通过以下元素指定控件： [view (Format 的 GroupBy 元素) ](./groupby-element-for-view-format.md)

- 当创建可供视图使用的另一个控件时，可以通过以下元素指定此控件：用于 [控件的 CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>另请参阅

[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)

[ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[View (格式的控件控件元素) ](./control-element-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
