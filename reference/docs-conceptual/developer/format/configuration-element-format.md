---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration Element (Format)
description: Configuration Element (Format)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655687"
---
# <a name="configuration-element-format"></a>Configuration Element (Format)

表示格式设置文件的顶级元素。

配置元素

## <a name="syntax"></a>语法

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Configuration` 。 此元素必须是每个格式化文件的根元素，并且此元素必须包含至少一个子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[Controls Element for Configuration (Format)](./controls-element-for-configuration-format.md)|可选元素。<br /><br /> 定义可供格式设置文件的所有视图使用的公共控件。|
|[DefaultSettings Element (Format)](./defaultsettings-element-format.md)|可选元素。<br /><br /> 定义适用于格式设置文件的所有视图的常见设置。|
|[SelectionSets 元素格式](./selectionsets-element-format.md)|可选元素。<br /><br /> 定义可供格式设置文件的所有视图使用的常用 .NET 对象集。|
|[ViewDefinitions Element (Format)](./viewdefinitions-element-format.md)|可选元素。<br /><br /> 定义用于显示对象的视图。|

### <a name="parent-elements"></a>父元素

无。

## <a name="remarks"></a>备注

格式化文件定义对象的显示方式。 在大多数情况下，此根元素包含一个 [ViewDefinitions](./viewdefinitions-element-format.md) 元素，该元素定义格式设置文件的表、列表和宽视图。 除了视图定义以外，格式设置文件还可以定义这些视图可以使用的常用选择集、设置和控件。

## <a name="see-also"></a>另请参阅

[Controls Element for Configuration (Format)](./controls-element-for-configuration-format.md)

[DefaultSettings Element (Format)](./defaultsettings-element-format.md)

[SelectionSets Element (Format)](./selectionsets-element-format.md)

[ViewDefinitions Element (Format)](./viewdefinitions-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
