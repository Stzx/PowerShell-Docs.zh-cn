---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntries Element for WideControl (Format)
description: WideEntries Element for WideControl (Format)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651244"
---
# <a name="wideentries-element-for-widecontrol-format"></a>WideEntries Element for WideControl (Format)

提供宽视图的定义。 宽视图必须指定一个或多个定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `WideEntries` 。 必须至少指定一个子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)|提供宽视图的定义。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[WideControl Element (Format)](./widecontrol-element-format.md)|定义视图的宽 (单个值) 列表格式。|

## <a name="remarks"></a>备注

宽视图是显示每个对象的单个属性值或脚本值的列表格式。 有关宽视图组件的详细信息，请参阅 [宽视图组件](./creating-a-wide-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `WideEntries` 元素，该元素定义单个 `WideEntry` 元素。 `WideEntry`元素包含一个 `WideItem` 元素，该元素定义要在视图中显示的属性或脚本值。

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

有关宽视图的完整示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。

## <a name="see-also"></a>另请参阅

[创建宽视图](./creating-a-wide-view.md)

[WideControl Element (Format)](./widecontrol-element-format.md)

[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
