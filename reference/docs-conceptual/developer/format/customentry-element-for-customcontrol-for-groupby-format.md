---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntry Element for CustomControl for GroupBy (Format)
description: CustomEntry Element for CustomControl for GroupBy (Format)
ms.openlocfilehash: 0df2ff9c15308939e6d2552f51e2961bdabc59fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646060"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a>CustomEntry Element for CustomControl for GroupBy (Format)

提供控件的定义。 此元素在定义如何显示新的对象组时使用。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for CustomControl for groupby (format) CustomEntry 元素 for CustomControl for GroupBy (格式) 

## <a name="syntax"></a>语法

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)|可选元素。<br /><br /> 定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|
|[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|必需的元素。<br /><br /> 定义控件显示数据的方式。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntries Element for CustomControl for GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)|提供控件的定义。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[CustomEntries Element for CustomControl for GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
