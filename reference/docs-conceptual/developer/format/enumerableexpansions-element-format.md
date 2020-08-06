---
title: " (格式) 的 EnumerableExpansions 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774008"
---
# <a name="enumerableexpansions-element-format"></a>EnumerableExpansions Element (Format)

定义在视图中显示 .NET 集合对象时如何对其进行扩展。

配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `EnumerableExpansions` 。 您可以使用的子元素数没有限制。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[EnumerableExpansion Element (Format)](./enumerableexpansion-element-format.md)|可选元素。<br /><br /> 定义特定 .NET 集合对象，这些对象在视图中显示时展开。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[DefaultSettings Element (Format)](./defaultsettings-element-format.md)|定义适用于格式设置文件的所有视图的常见设置。|

## <a name="remarks"></a>备注

此元素用于定义集合对象和集合中的对象的显示方式。 在这种情况下，集合对象引用支持**system.object**接口的任何对象。

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
