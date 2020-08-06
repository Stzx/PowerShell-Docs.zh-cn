---
title: " (格式) 的 ListControl 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785721"
---
# <a name="listcontrol-element-format"></a>ListControl Element (Format)

定义视图的列表格式。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ListControl` 。 此元素必须只包含一个子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ListEntries 元素 (格式) ](./listentries-element-for-listcontrol-format.md)|必需的元素。<br /><br /> 提供列表视图的定义。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义一个视图，该视图用于显示一个或多个对象的成员。|

## <a name="remarks"></a>备注

有关创建列表视图的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

此示例显示了[system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)对象的列表视图。

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>另请参阅

[View Element (Format)](./view-element-format.md)

[ListEntries 元素 (格式) ](./listentries-element-for-listcontrol-format.md)

[创建列表视图](./creating-a-list-view.md)

[编写 Windows PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
