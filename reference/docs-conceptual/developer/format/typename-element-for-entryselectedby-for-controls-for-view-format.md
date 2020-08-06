---
title: 视图 (格式的控件的 EntrySelectedBy 的 TypeName 元素) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6eaa4f80a18c91ca351657fd40a8cac6f688c22f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783324"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-view-format"></a>TypeName Element for EntrySelectedBy for Controls for View (Format)

指定使用控件的此定义的 .NET 类型。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomControl 元素，用于控件的视图 (格式) CustomEntries 元素 (CustomEntry 的控件) 的元素，用于查看 (格式的控件) CustomControl 的元素。

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
|[EntrySelectedBy Element for CustomEntry for Controls for View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[EntrySelectedBy Element for CustomEntry for Controls for View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
