---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for SelectionSet (Format)
description: Name Element for SelectionSet (Format)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666445"
---
# <a name="name-element-for-selectionset-format"></a>Name Element for SelectionSet (Format)

指定用于引用选项集的名称。

配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) SelectionSet (格式的 Name 元素) 

## <a name="syntax"></a>语法

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Name` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[SelectionSet Element (Format)](./selectionset-element-format.md)|定义一组可由集名称引用的 .NET 对象。|

## <a name="text-value"></a>文本值

指定名称以引用选项集。 对于可使用哪些字符没有任何限制。

## <a name="remarks"></a>备注

此处指定的名称用于 `SelectionSetName` 元素。 视图可以使用的选项集 (视图的视图定义可以具有多个定义) 或指定选择条件。 有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。

## <a name="example"></a>示例

此示例演示 `SelectionSet` 定义四个 .net 类型的元素。 选择集的名称为 "FileSystemTypes"。

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

[SelectionSet Element (Format)](./selectionset-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
