---
ms.date: 09/13/2016
ms.topic: reference
title: 定义选项集
description: 定义选项集
ms.openlocfilehash: d709a368a45623d56fdbf4e98a11a5e5f8a193fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648257"
---
# <a name="defining-selection-sets"></a>定义选项集

在创建多个视图和控件时，可以定义称为选择集的对象集。 通过选择集，您可以一次性定义对象，而无需为每个视图或控件重复定义对象。 通常，当您有一组相关的 .NET 对象时，将使用选择集。 例如， `FileSystem` 格式化文件 ( # B0 xml) 定义多个视图使用的一组文件系统类型。

## <a name="where-selection-sets-are-defined-and-referenced"></a>定义和引用选择集的位置

将选择集定义为可由格式设置文件中定义的所有视图和控件使用的通用数据的一部分。 下面的示例演示如何定义三个选择集。

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

可以通过以下方式引用选项集：

- 每个视图都有一个 `ViewSelectedBy` 元素，该元素定义使用视图显示的对象。 `ViewSelectedBy`元素有一个 `SelectionSetName` 子元素，该元素指定视图的所有定义所使用的选择集。 对于可以从视图引用的选择集的数量没有限制。

- 在视图或控件的每个定义中， `EntrySelectedBy` 元素定义使用该定义显示的对象。 通常，视图或控件只有一个定义，因此这些对象由 `ViewSelectedBy` 元素定义。 `EntrySelectedBy`定义的元素包含一个 `SelectionSetName` 指定选择集的子元素。 如果为定义指定选择集，则不能指定元素的任何其他子元素 `EntrySelectedBy` 。

- 在视图或控件的每个定义中， `SelectionCondition` 元素可用于指定使用定义的条件。 `SelectionCondition`元素有一个 `SelectionSetName` 子元素，该元素指定触发条件的选择集。 当显示选择集中定义的任何对象时，将触发该条件。 有关如何设置这些条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。

## <a name="selection-set-example"></a>选择集示例

以下示例显示了直接从 `FileSystem` Windows PowerShell 提供的格式化文件中获取的选项集。 有关其他 Windows PowerShell 格式设置文件的详细信息，请参阅 [Windows Powershell 格式设置文件](./powershell-formatting-files.md)。

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

在表视图的元素中引用了上一选择集 `ViewSelectedBy` 。

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a>XML 元素

 您可以定义的选项集数没有限制。 以下 XML 元素用于创建选择集。

- [SelectionSets](./selectionsets-element-format.md)元素定义格式设置文件的视图和控件引用的 .net 对象集。

- [SelectionSet](./selectionset-element-format.md)元素定义一组 .net 对象。

- [Name](./name-element-for-selectionset-format.md)元素指定用于引用选项集的名称。

- [类型](./types-element-for-selectionset-format.md)元素指定选择集的对象的 .net 类型。  (在格式设置文件中，对象由其 .NET 类型指定。 ) 

 以下 XML 元素用于指定选择集。

- 以下元素指定要在视图的所有定义中使用的选择集：

  - [SelectionSetName Element for ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)

  - [SelectionSetName Element for EntrySelectedBy for GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- 以下元素指定单个视图定义使用的选择集：

  - [SelectionSetName Element for EntrySelectedBy for ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [SelectionSetName Element for EntrySelectedBy for TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [SelectionSetName Element for EntrySelectedBy for WideControl (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- 以下元素指定 common 和 view 控件定义所使用的选择集：

  - [SelectionSetName Element for EntrySelectedBy for Controls for View (Format)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- 以下元素指定在定义要扩展的对象时所使用的选择集：

  - [SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 以下元素指定选择条件使用的选择集。

  - [SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [SelectionSetName Element for SelectionCondition for Controls for View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [SelectionSetName Element for SelectionCondition for CustomControl for View (Format)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [SelectionSetName Element for SelectionCondition for GroupBy (Format)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>另请参阅

[SelectionSets](./selectionsets-element-format.md)

[SelectionSet](./selectionset-element-format.md)

[名称](./name-element-for-selectionset-format.md)

[类型](./types-element-for-selectionset-format.md)

[PowerShell 格式设置文件](./powershell-formatting-files.md)

[定义显示数据的条件](./defining-conditions-for-displaying-data.md)

[编写 PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
