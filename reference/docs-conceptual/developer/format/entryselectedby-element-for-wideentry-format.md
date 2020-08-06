---
title: WideEntry (Format) 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ba0a776839c39d753d12859335388c5326639fd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774076"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>EntrySelectedBy Element for WideEntry (Format)

定义使用此类定义的 .NET 类型或使用此定义时必须存在的条件。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素

## <a name="syntax"></a>语法

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|可选元素。<br /><br /> 定义要使用此宽视图定义必须存在的条件。|
|[WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|可选元素。<br /><br /> 指定一组使用此宽视图定义的 .NET 类型。|
|[TypeName Element for EntrySelectedBy for WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)|可选元素。<br /><br /> 指定使用此宽视图定义的 .NET 类型。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)|提供宽视图的定义。|

## <a name="remarks"></a>备注

对于宽视图定义，必须至少指定一个类型、选择集或选择条件。 您可以使用的子元素数没有最大限制。

选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本值的计算结果为时 `true` 。 有关选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。

有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。

## <a name="see-also"></a>另请参阅

[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)

[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[TypeName Element for EntrySelectedBy for WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[创建宽视图](./creating-a-wide-view.md)

[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
