---
ms.date: 09/13/2016
ms.topic: reference
title: ListEntry Element for ListControl (Format)
description: ListEntry Element for ListControl (Format)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666563"
---
# <a name="listentry-element-for-listcontrol-format"></a>ListEntry Element for ListControl (Format)

提供列表视图的定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ListEntry` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[ListEntry 的 EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|可选元素。<br /><br /> 定义使用此列表视图定义的 .NET 对象，或使用此定义必须存在的条件。|
|[ListItems 元素 (格式) ](./listitems-element-for-listentry-for-listcontrol-format.md)|必需的元素。<br /><br /> 定义其值由列表视图显示的属性和脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ListEntries 元素 (格式) ](./listentries-element-for-listcontrol-format.md)|提供列表视图的定义。|

## <a name="remarks"></a>备注

列表视图是显示每个对象的属性值或脚本值的列表格式。 有关列表视图的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

此示例显示了为 [system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象定义列表视图的 XML 元素。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>另请参阅

[创建列表视图](./creating-a-list-view.md)

[ListEntry 的 EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[ListEntries 元素 (格式) ](./listentries-element-for-listcontrol-format.md)

[ListItems 元素 (格式) ](./listitems-element-for-listentry-for-listcontrol-format.md)

[编写 Windows PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
