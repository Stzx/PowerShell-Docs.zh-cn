---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntries Element for CustomControl for Controls for View (Format)
description: CustomEntries Element for CustomControl for Controls for View (Format)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652373"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>CustomEntries Element for CustomControl for Controls for View (Format)

提供控件的定义。 定义可由视图使用的控件时，将使用此元素。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) 

## <a name="syntax"></a>语法

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。 对于可指定的子元素数没有最大限制。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[CustomEntry Element for CustomEntries for Controls for View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)|必需的元素。<br /><br /> 提供控件的定义。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CustomControl Element for Control for Controls for View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|定义视图使用的控件。|

## <a name="remarks"></a>备注

在大多数情况下，控件只有一个定义，该定义是在单个元素中指定的 `CustomEntry` 。 但是，如果您希望使用同一控件显示不同的 .NET 对象，则可以提供多个定义。 在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。

## <a name="see-also"></a>另请参阅

[CustomEntry Element for CustomEntries for Controls for View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[CustomControl Element for Control for Controls for View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
