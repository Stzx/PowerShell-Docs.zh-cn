---
title: ViewSelectedBy (Format) 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f6410b463bcb00d2758849c2f7e13cd839277e50
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772597"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>SelectionSetName Element for ViewSelectedBy (Format)

指定视图显示的一组 .NET 对象。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) SelectionSetName 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[ViewSelectedBy Element (Format)](./viewselectedby-element-format.md)|定义视图显示的 .NET 对象。|

## <a name="text-value"></a>文本值

为选择集指定由元素定义的选择集的名称 `Name` 。

## <a name="remarks"></a>备注

如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。 有关定义和引用选项集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。

## <a name="example"></a>示例

下面的示例演示如何为列表视图指定选择集。 表、宽视图和自定义视图使用相同的架构。

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>另请参阅

[定义选项集](./defining-selection-sets.md)

[ViewSelectedBy Element (Format)](./viewselectedby-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
