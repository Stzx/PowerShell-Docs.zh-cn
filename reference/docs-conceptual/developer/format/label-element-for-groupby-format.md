---
ms.date: 09/13/2016
ms.topic: reference
title: Label Element for GroupBy (Format)
description: Label Element for GroupBy (Format)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649785"
---
# <a name="label-element-for-groupby-format"></a>Label Element for GroupBy (Format)

指定在遇到新组时显示的标签。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) GroupBy 元素 () 格式 (标签元素) 

## <a name="syntax"></a>语法

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Label` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)|定义如何显示新的对象组。|

## <a name="text-value"></a>文本值

指定每当 Windows PowerShell 遇到新的属性或脚本值时所显示的文本。

## <a name="remarks"></a>备注

除了此元素指定的文本，Windows PowerShell 还显示启动组的新值，并在组的前面和后面添加一个空白行。

## <a name="example"></a>示例

下面的示例显示了新组的标签。 显示的标签如下所示： `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

有关包括此元素的完整格式化文件的示例，请参阅 [ (GroupBy) 的宽视图 ](./wide-view-groupby.md)。

## <a name="see-also"></a>另请参阅

[GroupBy Element for View (Format)](./groupby-element-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
