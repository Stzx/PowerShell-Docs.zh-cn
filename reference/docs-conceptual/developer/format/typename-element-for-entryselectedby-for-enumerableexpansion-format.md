---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)
description: TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)
ms.openlocfilehash: 7c1195717ae0963ace3e02f0ae2ae7c34f69078a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654825"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a>TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)

指定通过此定义扩展的 .NET 类型。 定义默认设置时，将使用此元素。

配置元素 (格式) DefaultSettings 元素 (格式) EnumerableExpansions 元素 (格式) EnumerableExpansion 元素 (格式) EnumerableExpansion 的 EntrySelectedBy 元素 (EntrySelectedBy) 格式 (

## <a name="syntax"></a>语法

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TypeName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|定义使用此定义的 .NET 类型或要使用此定义时必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[EntrySelectedBy Element for EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
