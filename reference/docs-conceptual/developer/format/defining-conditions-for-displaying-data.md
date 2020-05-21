---
title: 定义用于显示数据的条件 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1e05821-6aec-437b-84a5-218a5727f88b
caps.latest.revision: 10
ms.openlocfilehash: 6036f30816e253b3f0c40c6b916279d0643acdb8
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692490"
---
# <a name="defining-conditions-for-displaying-data"></a>定义用于显示数据的条件

定义视图或控件显示的数据时，您可以指定一个必须存在的条件，以便显示数据。 条件可由特定属性触发，或者在脚本或属性值的计算结果为时触发 `true` 。 如果满足选择条件，将使用视图或控件的定义。

## <a name="specifying-a-selection-condition-for-a-definition"></a>为定义指定选择条件

创建视图或控件的定义时， `EntrySelectedBy` 元素用于指定将使用定义的对象或必须存在的条件才能使用定义。 条件由 `SelectionCondition` 元素指定。

在下面的示例中，将为表视图的定义指定选择条件。 在此示例中，仅当指定的脚本的计算结果为时，才会使用定义 `true` 。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

对于您可以为视图或控件的定义指定的选择条件数没有限制。 唯一的要求如下：

- 选择条件必须指定一个属性名称或脚本来触发条件，但不能同时指定两者。

- 选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。

## <a name="specifying-a-selection-condition-for-an-item"></a>指定项的选择条件

你还可以通过 `ItemSelectionCondition` 在项定义中包含元素来指定何时使用列表视图或控件的项。 在下面的示例中，为列表视图的项指定了选择条件。 在此示例中，仅当将脚本计算为时，才使用项 `true` 。

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

只能为项指定一个选择条件。 条件必须指定一个属性名称或脚本来触发条件，但不能同时指定两者。

## <a name="xml-elements"></a>XML 元素

 以下 XML 元素用于创建选择条件。

- 以下元素指定了视图定义的选择条件：

  - [SelectionCondition Element for EntrySelectedBy for TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [SelectionCondition Element for EntrySelectedBy for ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [SelectionCondition Element for EntrySelectedBy for WideControl (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [SelectionCondition Element for EntrySelectedBy for CustomControl (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- 以下元素指定常用和视图控件定义的选择条件：

  - [SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [SelectionCondition Element for EntrySelectedBy for Controls for View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- 以下元素指定展开集合对象的选择条件：

  - [SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 以下元素指定用于显示新数据组的选择条件：

  - [SelectionCondition Element for EntrySelectedBy for GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- 以下元素为列表视图指定项选择条件：

  - [ItemSelectionCondition Element for ListItem for ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- 以下元素为控件指定项选择条件：

  - [ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
