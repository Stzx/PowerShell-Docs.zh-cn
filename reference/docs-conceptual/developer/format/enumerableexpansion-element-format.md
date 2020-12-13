---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion Element (Format)
description: EnumerableExpansion Element (Format)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668008"
---
# <a name="enumerableexpansion-element-format"></a>EnumerableExpansion Element (Format)

定义特定 .NET 集合对象在视图中显示的方式。

配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `EnumerableExpansion` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|可选元素。<br /><br /> 定义通过此定义扩展哪些 .NET 集合对象。|
|[Expand Element (Format)](./expand-element-format.md)|指定为此定义扩展集合对象的方式。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EnumerableExpansions Element (Format)](./enumerableexpansions-element-format.md)|定义 .NET 集合对象在视图中显示时的扩展方式。|

## <a name="remarks"></a>备注

此元素用于定义集合对象和集合中的对象的显示方式。 在这种情况下，集合对象引用支持  **system.object** 接口的任何对象。

默认行为是只显示集合中对象的属性。

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
