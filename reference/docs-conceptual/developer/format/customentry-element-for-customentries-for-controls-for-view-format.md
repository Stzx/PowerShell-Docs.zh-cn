---
title: View (Format) 的控件的 CustomEntries 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785891"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>CustomEntry Element for CustomEntries for Controls for View (Format)

提供控件的定义。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomControl 元素，用于控件的视图 (格式) CustomEntries 元素 (CustomEntry 的控件) CustomEntries

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
|[EntrySelectedBy Element for CustomEntry for Controls for View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|可选元素。<br /><br /> 定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。|
|[CustomItem Element for CustomEntry for Controls for View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)|必需的元素。<br /><br /> 定义控件显示数据的方式。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[CustomEntries Element for CustomControl for View (Format)](./customentries-element-for-customcontrol-for-view-format.md)|提供控件的定义。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[CustomEntries Element for CustomControl for View (Format)](./customentries-element-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
