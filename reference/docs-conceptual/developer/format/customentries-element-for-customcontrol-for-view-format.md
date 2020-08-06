---
title: CustomControl 的 CustomEntries 元素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c89eb25f6922a92e2c18298d0128c4c2ca93df3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785959"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>CustomEntries Element for CustomControl for View (Format)

提供自定义控件视图的定义。 自定义控件视图必须指定一个或多个定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，CustomControl 的元素 (格式) 

## <a name="syntax"></a>语法

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomControlEntries` 。 您必须指定一个或多个子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[View (格式的 CustomEntries 的 CustomEntry 元素) ](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|必需的元素。<br /><br /> 提供自定义控件视图的定义。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[CustomControl Element for View (Format)](./customcontrol-element-for-view-format.md)|必需的元素。<br /><br /> 定义视图的自定义控件格式。|

## <a name="remarks"></a>备注

在大多数情况下，控件只有一个定义，该定义在单个元素中定义 `CustomEntry` 。 但是，如果希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。 在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。

## <a name="see-also"></a>另请参阅

[CustomControl Element for View (Format)](./customcontrol-element-for-view-format.md)

[View (格式的 CustomEntries 的 CustomEntry 元素) ](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
