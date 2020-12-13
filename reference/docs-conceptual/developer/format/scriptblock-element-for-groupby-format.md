---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for GroupBy (Format)
description: ScriptBlock Element for GroupBy (Format)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665241"
---
# <a name="scriptblock-element-for-groupby-format"></a>ScriptBlock Element for GroupBy (Format)

指定在新组的值发生更改时启动新组的脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (groupby) 格式的 ScriptBlock 元素 (

## <a name="syntax"></a>语法

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)|定义一组 .NET 对象的显示方式。|

## <a name="text-value"></a>文本值

指定要评估的脚本。

## <a name="remarks"></a>备注

每当此脚本的值发生更改时，PowerShell 就会启动一个新组。

如果指定此元素，则不能指定 [PropertyName](propertyname-element-for-groupby-format.md) 元素来启动新组。

## <a name="see-also"></a>另请参阅

[PropertyName Element for GroupBy (Format)](propertyname-element-for-groupby-format.md)

[GroupBy Element for View (Format)](groupby-element-for-view-format.md)

[编写 PowerShell 格式设置文件](writing-a-powershell-formatting-file.md)
