---
title: " (格式) 的 DisplayError 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774280"
---
# <a name="displayerror-element-format"></a>DisplayError Element (Format)

指定在显示一段数据时出现错误时显示字符串 #ERR。

配置元素 (格式) DefaultSettings 元素 (格式) DisplayError 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `DisplayError` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[DefaultSettings Element (Format)](./defaultsettings-element-format.md)|定义适用于格式设置文件的所有视图的常见设置。|

## <a name="remarks"></a>备注

默认情况下，在尝试显示一段数据的过程中出现错误时，数据的位置将保留为空。 如果此元素设置为 true，则将显示 #ERR 字符串。

## <a name="see-also"></a>另请参阅

[DefaultSettings Element (Format)](./defaultsettings-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
