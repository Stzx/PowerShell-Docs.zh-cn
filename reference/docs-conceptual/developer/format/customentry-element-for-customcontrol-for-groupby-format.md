---
title: GroupBy (Format) 的 CustomControl 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4df8e5b96868b3814c6d84fa329950bb5345ef6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785908"
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

|元素|说明|
|-------------|-----------------|
|[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)|可选元素。<br /><br /> 定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|
|[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|必需的元素。<br /><br /> 定义控件显示数据的方式。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[CustomEntries Element for CustomControl for GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)|提供控件的定义。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[EntrySelectedBy Element for CustomEntry for GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[CustomItem Element for CustomEntry for GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[CustomEntries Element for CustomControl for GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
