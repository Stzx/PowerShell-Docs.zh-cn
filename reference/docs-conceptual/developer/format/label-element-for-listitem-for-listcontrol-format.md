---
title: ListControl (Format) 的输入标记元素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783630"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Label Element for ListItem for ListControl (Format)

指定在行的属性或脚本值左侧显示的标签。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl ListItems 的 ListEntry 元素) ListControl 的 ListItems 元素 (ListControl) 格式 (ListControl) 格式 (

## <a name="syntax"></a>语法

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Label` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[ListItem Element for ListItems for ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|定义其值显示在列表视图的行中的属性或脚本。|

## <a name="text-value"></a>文本值

指定要在属性或脚本值左侧显示的标签。

## <a name="remarks"></a>备注

如果未指定标签，则显示属性或脚本的名称。 有关在列表视图中使用标签的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。

## <a name="example"></a>示例

下面的示例演示如何向行中添加标签。

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>另请参阅

[创建列表视图](./creating-a-list-view.md)

[ (格式的) 元素元素](./listitem-element-for-listitems-for-listcontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
