---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControl Element for GroupBy (Format)
description: CustomControl Element for GroupBy (Format)
ms.openlocfilehash: 633cfcbd10206dc8d7fb4bc1d0092f19aa5bde7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646100"
---
# <a name="customcontrol-element-for-groupby-format"></a>CustomControl Element for GroupBy (Format)

定义显示新组的自定义控件。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (CustomControl 元素 for GroupBy) 格式 (

## <a name="syntax"></a>语法

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。 可以指定任意数量的子元素，并以任意顺序列出它们。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[CustomEntries Element for CustomControl for GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)|必需的元素。<br /><br /> 提供控件的定义。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)|定义 Windows PowerShell 如何显示一组新的对象。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[CustomEntries Element for CustomControl for GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)

[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
