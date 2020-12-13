---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl Element (Format)
description: WideControl Element (Format)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651276"
---
# <a name="widecontrol-element-format"></a>WideControl Element (Format)

定义视图的宽 (单个值) 列表格式。 此视图显示每个对象的单个属性值或脚本值。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `WideControl` 。 不能同时指定 `AutoSize` 和 `ColumnNumber` 元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[AutoSize Element for WideControl (Format)](./autosize-element-for-widecontrol-format.md)|可选元素。<br /><br /> 指定是否根据数据大小调整列大小和列数。|
|[ColumnNumber Element for WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)|可选元素。<br /><br /> 指定宽视图中显示的列数。|
|[WideEntries 元素 (格式) ](./wideentries-element-for-widecontrol-format.md)|必需的元素。<br /><br /> 提供宽视图的定义。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义用于显示一个或多个 .NET 对象的视图。|

## <a name="remarks"></a>备注

定义宽视图时，可以添加 `AutoSize` 元素或， `ColumnNumber` 但不能同时添加这两个元素。

在大多数情况下，每个宽视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以有多个定义。 在这些情况下，可以为每个对象或一组对象提供单独的定义。

有关宽视图组件的详细信息，请参阅 [宽视图组件](./creating-a-wide-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `WideControl` 元素，该元素用于显示 [system.object](/dotnet/api/System.Diagnostics.Process) 对象的属性。

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

有关宽视图的完整示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。

## <a name="see-also"></a>另请参阅

[WideControl 的 Autosize 元素 (格式) ](./autosize-element-for-widecontrol-format.md)

[ColumnNumber Element for WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)

[View Element (Format)](./view-element-format.md)

[WideEntries 元素 (格式) ](./wideentries-element-for-widecontrol-format.md)

[宽视图 (Basic)](./wide-view-basic.md)

[创建宽视图](./creating-a-wide-view.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
