---
title: WideControl (Format) 的 WideEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780009"
---
# <a name="wideentry-element-for-widecontrol-format"></a>WideEntry Element for WideControl (Format)

提供宽视图的定义。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `WideEntry` 。 您必须指定一个 `WideItem` 子元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[EntrySelectedBy Element for WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md)|可选元素。<br /><br /> 定义使用此宽项定义的 .NET 类型或要使用此定义时必须存在的条件。|
|[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)|必需的元素。<br /><br /> 定义要显示其值的属性或脚本。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[WideEntries 元素 (格式) ](./wideentries-element-for-widecontrol-format.md)|提供宽视图的定义。|

## <a name="remarks"></a>备注

宽视图是显示每个对象的单个属性值或脚本值的列表格式。 与其他类型的视图不同，每个视图定义只能指定一个 item 元素。 有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。

## <a name="example"></a>示例

下面的示例演示一个 `WideEntry` 元素，该元素定义单个 `WideItem` 元素。 `WideItem`元素定义其值在视图中显示的属性。

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

有关宽视图的完整示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。

## <a name="see-also"></a>另请参阅

[创建宽视图](./creating-a-wide-view.md)

[WideEntry 的 SelectionCondition 元素 (格式) ](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry 的 SelectionSetName 元素 (格式) ](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (格式的 TypeName 元素) ](./typename-element-for-entryselectedby-for-wideentry-format.md)

[WideEntries 元素 (格式) ](./wideentries-element-for-widecontrol-format.md)

[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
