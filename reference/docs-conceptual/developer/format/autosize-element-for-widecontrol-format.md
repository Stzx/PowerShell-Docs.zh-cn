---
ms.date: 09/13/2016
ms.topic: reference
title: AutoSize Element for WideControl (Format)
description: AutoSize Element for WideControl (Format)
ms.openlocfilehash: 42dfae337ba8805e1ddcff4269401afdb3e281f6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650008"
---
# <a name="autosize-element-for-widecontrol-format"></a>AutoSize Element for WideControl (Format)

指定是否根据数据大小调整列大小和列数。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl (格式) Autosize 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `AutoSize` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[WideControl Element (Format)](./widecontrol-element-format.md)|定义视图的宽 (单个值) 列表格式。|

## <a name="remarks"></a>备注

定义宽视图时，可以添加 `AutoSize` 元素或 [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) 元素，但不能同时添加这两个元素。

有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。

有关宽视图的示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。

## <a name="see-also"></a>另请参阅

[ColumnNumber Element for WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)

[创建宽视图](./creating-a-wide-view.md)

[WideControl Element (Format)](./widecontrol-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
