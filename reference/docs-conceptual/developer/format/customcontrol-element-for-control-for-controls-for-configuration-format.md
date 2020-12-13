---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControl Element for Control for Controls for Configuration (Format)
description: CustomControl Element for Control for Controls for Configuration (Format)
ms.openlocfilehash: 631995c6a50c0f020cb2e991cfbf58a09a75cc72
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650000"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a>CustomControl Element for Control for Controls for Configuration (Format)

定义控件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

配置元素 (格式) 控制配置 (格式) 控件元素，用于配置 (格式的控件) CustomControl 元素，以控制配置 (格式) 

## <a name="syntax"></a>语法

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。 此元素必须至少有一个子元素。 对于可指定的子元素数没有最大限制。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|必需的元素。<br /><br /> 提供控件的定义。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[Control Element for Controls for Configuration (Format)](./control-element-for-controls-for-configuration-format.md)|定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[Control Element for Controls for Configuration (Format)](./control-element-for-controls-for-configuration-format.md)

[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
