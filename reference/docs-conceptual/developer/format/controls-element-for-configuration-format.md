---
title: 配置 (格式) 的控件元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 44b9db0d3523e5e9086da9911882b258a2a54ca6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783783"
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
