---
title: 用于 CustomControl for View (Format) 的 CustomEntries 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a13e83ec941bed80eaab02e40131054432fcce00
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785874"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a>CustomEntry Element for CustomEntries for CustomControl for View (Format)

提供自定义控件视图的定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的 CustomEntries 元素)  (格式) 

## <a name="syntax"></a>语法

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。 您必须指定由定义显示的项。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|可选元素。<br /><br /> 定义使用自定义控件视图的定义或要使用此定义必须存在的条件的 .NET 类型。|
|[View (格式的 CustomEntry 的 CustomItem 元素) ](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|定义自定义控件定义的控件。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomEntries Element for CustomControl for View (Format)](./customentries-element-for-customcontrol-for-view-format.md)|提供自定义控件视图的定义。 自定义控件视图必须指定一个或多个定义。|

## <a name="remarks"></a>备注

在大多数情况下，每个自定义控件视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以有多个定义。 在这些情况下，可以为每个对象或一组对象提供单独的定义。

## <a name="see-also"></a>另请参阅

[CustomControl Element for View (Format)](./customcontrol-element-for-view-format.md)

[View (格式的 CustomEntry 的 CustomItem 元素) ](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
