---
title: ListControl 的 ScriptBlock 元素) 的 (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785449"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>ScriptBlock Element for ListItem for ListControl (Format)

指定其值在行中显示的脚本。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntries for ListControl 的 ListItems 元素) ListEntry (的 ScriptBlock 元素) ListControl (格式) 的 ScriptBlock 元素 (

## <a name="syntax"></a>语法

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
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
|[ (格式的) 元素元素](./listitem-element-for-listitems-for-listcontrol-format.md)|定义其值显示在列表视图的行中的属性或脚本。|

## <a name="text-value"></a>文本值

指定其值在行中显示的脚本。

## <a name="remarks"></a>备注

如果指定此元素，则不能指定[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)元素。

有关在列表视图中指定脚本的详细信息，请参阅[列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

下面的示例演示如何指定显示其值的属性。

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>另请参阅

[PropertyName Element for ListItem for ListControl (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[创建列表视图](./creating-a-list-view.md)

[ListItem Element for ListItems for ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
