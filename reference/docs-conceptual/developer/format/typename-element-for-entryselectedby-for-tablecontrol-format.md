---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for TableControl (Format)
description: TypeName Element for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651424"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>TypeName Element for EntrySelectedBy for TableControl (Format)

指定使用此表视图项的 .NET 类型。 对于可为表条目指定的类型数量没有限制。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy (格式)  (TypeName 元素) 格式

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
|[EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|定义使用此项的 .NET 类型或此项要使用的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的名称。

## <a name="remarks"></a>备注

每个列表项必须至少定义一个类型名称、选择集或选择条件。

有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。

## <a name="see-also"></a>另请参阅

[创建表视图](./creating-a-table-view.md)

[EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
