---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for Types (Format)
description: TypeName Element for Types (Format)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664622"
---
# <a name="typename-element-for-types-format"></a>TypeName Element for Types (Format)

指定属于选择集的对象的 .NET 类型。

配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) 格式 (格式) 类型 () 格式的 TypeName 元素

## <a name="syntax"></a>语法

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `TypeName` 。 `TypeName`选择集中必须至少包含一个元素。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[类型元素 (格式) ](./types-element-for-selectionset-format.md)|定义选择集中的 .NET 对象。|

## <a name="text-value"></a>文本值

指定 .NET 类型的完全限定名称。

## <a name="remarks"></a>备注

如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。 定义视图时，可以使用选择集的名称（而不是列出每个视图中的所有对象）来指定对象集。

常用选择集在定义格式设置文件的视图时由其名称指定。 在这些情况下， `SelectionSetName` 视图的元素的子元素 `ViewSelectedBy` 指定了集。 但是，视图的不同项还可以指定仅适用于该视图项的选择集。 有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。

## <a name="example"></a>示例

下面的示例演示 `SelectionSet` 定义四个 .net 类型的元素。

```
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

[SelectionSets Element (Format)](./selectionsets-element-format.md)

[类型元素 (格式) ](./types-element-for-selectionset-format.md)

[编写 Windows PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
