---
title: WideControl (Format) 的 WideItem 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779890"
---
# <a name="wideitem-element-for-widecontrol-format"></a>WideItem Element for WideControl (Format)

定义要显示其值的属性或脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `WideItem` 。 `FormatString` 元素是可选的。 但是，您必须指定 `PropertyName` 或 `ScriptBlock` 元素，但不能同时指定两者。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[FormatString Element for WideItem for WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|可选元素。<br /><br /> 指定定义属性或脚本值在视图中显示方式的格式模式。|
|[WideItem (格式的 PropertyName 元素) ](./propertyname-element-for-wideitem-for-widecontrol-format.md)|指定对象的属性，其值显示在宽视图中。|
|[WideItem 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|指定其值在宽视图中显示的脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)|提供宽视图的定义。|

## <a name="remarks"></a>备注

有关宽视图组件的详细信息，请参阅[宽视图](./creating-a-wide-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `WideEntry` 元素，该元素定义单个 `WideItem` 元素。 `WideItem`元素定义其值在视图中显示的属性或脚本。

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

有关宽视图的完整示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。

## <a name="see-also"></a>另请参阅

[FormatString Element for WideItem for WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[WideItem (格式的 PropertyName 元素) ](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[WideItem 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
