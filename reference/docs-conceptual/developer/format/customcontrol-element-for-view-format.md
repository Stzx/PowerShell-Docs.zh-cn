---
title: View (Format) 的 CustomControl 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786044"
---
# <a name="customcontrol-element-for-view-format"></a>CustomControl Element for View (Format)

定义视图的自定义控件格式。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。 您必须指定一个子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[CustomEntries Element for CustomControl for View (Format)](./customentries-element-for-customcontrol-for-view-format.md)|必需的元素。<br /><br /> 提供自定义控件视图的定义。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义用于显示一个或多个 .NET 对象的视图。|

## <a name="remarks"></a>备注

在大多数情况下，每个控件视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以提供多个定义。 在这些情况下，可以为每个对象或一组对象提供单独的定义。

## <a name="see-also"></a>另请参阅

[CustomEntries Element for CustomControl for View (Format)](./customentries-element-for-customcontrol-for-view-format.md)

[View Element (Format)](./view-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
