---
title: " (格式) 的 SelectionSets 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 718b08e02220f285ef215fdca727492fd4407466
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785194"
---
# <a name="selectionsets-element-format"></a>SelectionSets Element (Format)

定义可供格式设置文件的所有视图使用的常用 .NET 对象集。 格式设置文件的视图和控件可以只使用选择集的名称来引用完整的对象集。

配置元素 SelectionSets 元素格式

## <a name="syntax"></a>语法

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `SelectionSets` 。 每个子元素定义一组可由集名称引用的对象。 子元素的顺序并不重要。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[SelectionSet Element (Format)](./selectionset-element-format.md)|必需的元素。<br /><br /> 定义一组可由集名称引用的 .NET 对象。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[配置元素](./configuration-element-format.md)|表示格式设置文件的顶级元素。|

## <a name="remarks"></a>备注

如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。 定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。

常用选择集在定义格式设置文件的视图或视图定义时由其名称指定。 在这些情况下， `SelectionSetName` 和元素的子 `ViewSelectedBy` 元素 `EntrySelectedBy` 指定要使用的集。 有关选择集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。

## <a name="see-also"></a>另请参阅

[配置元素](./configuration-element-format.md)

[定义选项集](./defining-selection-sets.md)

[SelectionSet Element (Format)](./selectionset-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
