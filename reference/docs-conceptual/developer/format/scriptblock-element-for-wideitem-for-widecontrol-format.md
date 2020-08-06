---
title: WideControl 的 WideItem 的 ScriptBlock 元素 (格式) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787591"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>ScriptBlock Element for WideItem for WideControl (Format)

指定其值在宽视图中显示的脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) 的 ScriptBlock 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)|定义其值在宽视图中显示的属性或脚本块。|

## <a name="text-value"></a>文本值

指定显示其值的脚本。

## <a name="remarks"></a>备注

有关宽视图组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。

## <a name="example"></a>示例

此示例演示一个 `WideItem` 元素，该元素定义一个其值在视图中显示的脚本。

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>另请参阅

[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)

[创建宽视图](./creating-a-wide-view.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
