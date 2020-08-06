---
title: GroupBy (Format) 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e83ebd49e4f3087c817b3cc8772889dbe85113aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785602"
---
# <a name="propertyname-element-for-groupby-format"></a>PropertyName Element for GroupBy (Format)

指定在新组的值发生更改时启动新组的 .NET 属性。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) GroupBy 元素 (groupby) 格式的 PropertyName 元素 (

## <a name="syntax"></a>语法

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)|定义一组 .NET 对象的显示方式。|

## <a name="text-value"></a>文本值

指定 .NET 属性名称。

## <a name="remarks"></a>备注

每当此属性的值发生更改时，Windows PowerShell 就会启动一个新组。

如果指定此元素，则不能指定[ScriptBlock](./scriptblock-element-for-groupby-format.md)元素来启动新组。

## <a name="example"></a>示例

下面的示例演示如何在属性的值更改时启动新组。

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

有关包括此元素的完整格式化文件的示例，请参阅[ (GroupBy) 的宽视图](./wide-view-groupby.md)。

## <a name="see-also"></a>另请参阅

[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)

[ScriptBlock Element for GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
