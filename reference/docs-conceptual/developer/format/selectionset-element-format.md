---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSet Element (Format)
description: SelectionSet Element (Format)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647870"
---
# <a name="selectionset-element-format"></a>SelectionSet Element (Format)

定义一组可由集名称引用的 .NET 对象。

配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `SelectionSet` 。 每个选项集都必须具有一个名称，并且必须指定该集的 .NET 对象。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[Name Element for SelectionSet (Format)](./name-element-for-selectionset-format.md)|必需的元素。<br /><br /> 指定用于引用选项集的名称。|
|[类型元素 (格式) ](./types-element-for-selectionset-format.md)|必需的元素。<br /><br /> 定义选择集中的 .NET 对象。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[SelectionSets 元素格式](./selectionsets-element-format.md)|定义可供格式设置文件的所有视图使用的常用 .NET 对象集。|

## <a name="remarks"></a>备注

如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。 定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。

常用选择集在定义格式设置文件的视图或视图定义时由其名称指定。 在这些情况下， `SelectionSetName` 和元素的子 `ViewSelectedBy` 元素 `EntrySelectedBy` 指定要使用的集。 有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。

## <a name="example"></a>示例

下面的示例演示 `SelectionSet` 定义四个 .net 类型的元素。

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a>另请参阅

[定义选项集](./defining-selection-sets.md)

[SelectionSet (格式的 Name 元素) ](./name-element-for-selectionset-format.md)

[SelectionSets Element (Format)](./selectionsets-element-format.md)

[类型元素 (格式) ](./types-element-for-selectionset-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
