---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for View (Format)
description: Name Element for View (Format)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666446"
---
# <a name="name-element-for-view-format"></a>Name Element for View (Format)

指定用于标识视图的名称。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) Name 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Name` 。 `Name`每个视图只允许有一个元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义一个视图，该视图用于显示一个或多个 .NET 对象的成员。|

## <a name="text-value"></a>文本值

为视图指定唯一的友好名称。 此名称可以包含对视图类型的引用 (例如表视图或列表视图) 、使用视图的对象或对象集、返回对象的命令或这些对象的组合。

## <a name="remarks"></a>备注

有关不同视图类型的详细信息，请参阅下列主题： [表视图](./creating-a-table-view.md)、 [列表视图](./creating-a-list-view.md)、 [宽视图](./creating-a-wide-view.md)和 [自定义视图](./creating-custom-controls.md)。

## <a name="example"></a>示例

下面的示例演示一个 `View` 元素，该元素定义 [System.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象的表视图。 视图的名称为 "service"。

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>另请参阅

[创建列表视图](./creating-a-list-view.md)

[创建表视图](./creating-a-table-view.md)

[创建宽视图](./creating-a-wide-view.md)

[创建自定义控件](./creating-custom-controls.md)

[View Element (Format)](./view-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
