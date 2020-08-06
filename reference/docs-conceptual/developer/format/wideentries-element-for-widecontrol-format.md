---
title: WideControl (Format) 的 WideEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785041"
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

|元素|说明|
|-------------|-----------------|
|[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)|提供宽视图的定义。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[WideControl Element (Format)](./widecontrol-element-format.md)|定义视图的宽 (单个值) 列表格式。|

## <a name="remarks"></a>备注

宽视图是显示每个对象的单个属性值或脚本值的列表格式。 有关宽视图组件的详细信息，请参阅[宽视图组件](./creating-a-wide-view.md)。

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

有关宽视图的完整示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。

## <a name="see-also"></a>另请参阅

[创建宽视图](./creating-a-wide-view.md)

[WideControl Element (Format)](./widecontrol-element-format.md)

[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
