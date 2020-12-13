---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for WideItem for WideControl (Format)
description: PropertyName Element for WideItem for WideControl (Format)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665611"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>PropertyName Element for WideItem for WideControl (Format)

指定对象的属性，其值显示在宽视图中。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) WideItem (格式) 

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

|元素|描述|
|-------------|-----------------|
|[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)|定义其值在宽视图中显示的属性或脚本。|

## <a name="text-value"></a>文本值

指定显示其值的属性的名称。

## <a name="remarks"></a>备注

有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。

## <a name="example"></a>示例

此示例显示了一个宽视图，其中 [显示了 ProcessName 对象的](/dotnet/api/System.Diagnostics.Process) "" 属性的值。

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a>另请参阅

[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)

[创建宽视图](./creating-a-wide-view.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
