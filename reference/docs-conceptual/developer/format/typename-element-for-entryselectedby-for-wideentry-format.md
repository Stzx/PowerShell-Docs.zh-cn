---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for WideEntry (Format)
description: TypeName Element for EntrySelectedBy for WideEntry (Format)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654796"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a>TypeName Element for EntrySelectedBy for WideEntry (Format)

为定义指定 .NET 类型。 只要显示此对象，就会使用定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (WideEntry) 格式

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
|[EntrySelectedBy Element for WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md)|定义使用此宽项的 .NET 类型或此项要使用的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

每个宽条目都必须指定一个或多个 .NET 类型、选择集或必须为要使用的定义提供的选择条件。

有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。

## <a name="see-also"></a>另请参阅

[创建宽视图](./creating-a-wide-view.md)

[EntrySelectedBy Element for WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
