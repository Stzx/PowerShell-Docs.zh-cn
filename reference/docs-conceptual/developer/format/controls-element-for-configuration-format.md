---
ms.date: 09/13/2016
ms.topic: reference
title: Controls Element for Configuration (Format)
description: Controls Element for Configuration (Format)
ms.openlocfilehash: 53f874ddccf3b4f1f0a23aad608e786524bde830
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668093"
---
# <a name="controls-element-for-configuration-format"></a>Controls Element for Configuration (Format)

定义可供格式设置文件的所有视图使用的公共控件。

配置元素 (格式) 配置 (格式的元素) 

## <a name="syntax"></a>语法

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Controls` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[Control Element for Controls for Configuration (Format)](./control-element-for-controls-for-configuration-format.md)|必需的元素。<br /><br /> 定义可供格式设置文件的所有视图使用的公共控件。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[Configuration Element (Format)](./configuration-element-format.md)|表示格式设置文件的顶级元素。|

## <a name="remarks"></a>备注

您可以创建任意数量的公共控件。 对于每个控件，您必须指定用于引用控件和控件组件的名称。

## <a name="see-also"></a>另请参阅

[Configuration Element (Format)](./configuration-element-format.md)

[Control Element for Controls for Configuration (Format)](./control-element-for-controls-for-configuration-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
