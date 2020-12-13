---
ms.date: 09/13/2016
ms.topic: reference
title: Types Element for SelectionSet (Format)
description: Types Element for SelectionSet (Format)
ms.openlocfilehash: ff3c24e7f52f862dc416b88d50983196ce907012
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645456"
---
# <a name="types-element-for-selectionset-format"></a>Types Element for SelectionSet (Format)

定义选择集中的 .NET 对象。

配置元素 (格式) SelectionSets 元素 (格式) SelectionSet 元素 (格式) 类型元素 (格式) 

## <a name="syntax"></a>语法

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Types` 。 必须至少有一个子元素，但对于可添加的子元素数没有最大限制。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[类型的 TypeName 元素 (格式) ](./typename-element-for-types-format.md)|必需的元素。<br /><br /> 指定属于选择集的 .NET 对象。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[SelectionSet Element (Format)](./selectionset-element-format.md)|定义一组可由集名称引用的 .NET 对象。|

## <a name="remarks"></a>备注

此元素定义的对象构成一个选项集，视图可使用该选项集，视图 (视图的定义可) 多个定义或指定选择条件。  有关选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。

## <a name="example"></a>示例

此示例演示 `SelectionSet` 定义四个 .net 类型的元素。

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

[定义对象集](./defining-selection-sets.md)

[SelectionSet Element (Format)](./selectionset-element-format.md)

[类型的 TypeName 元素 (格式) ](./typename-element-for-types-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
