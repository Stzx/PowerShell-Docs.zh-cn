---
title: 用于控件的 Name 元素 (Format) 的控件 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783528"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Name Element for Control for Controls for Configuration (Format)

指定控件的名称。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于配置 (格式的控件的控件) Name 元素 (

## <a name="syntax"></a>语法

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Name` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[Control Element for Controls for Configuration (Format)](./control-element-for-controls-for-configuration-format.md)|定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。|

## <a name="text-value"></a>文本值

指定用于引用此控件的名称。

## <a name="remarks"></a>备注

此处指定的名称可以用在以下元素中以引用此控件。

- 创建表、列表、宽控件或自定义控件视图时，可通过以下元素指定控件： [view (Format 的 GroupBy 元素) ](./groupby-element-for-view-format.md)

- 创建另一个公共控件时，可以通过以下元素指定此控件：用于[CustomItem 的 ExpressionBinding 元素用于配置 (格式的控件) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- 创建可由视图使用的控件时，可以通过以下元素指定此控件：用于[CustomItem 的控件的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>另请参阅

[Control Element for Controls for Configuration (Format)](./control-element-for-controls-for-configuration-format.md)

[ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
