---
title: Format Schema XML Reference |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 111f90269e669aa6f8f97082ccc6063a62ddc7b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785789"
---
# <a name="format-schema-xml-reference"></a>格式架构 XML 参考

本节中的主题描述 ( # B0 XML 文件) 格式设置文件所使用的 XML 元素。 格式化文件定义 .NET 对象的显示方式;它们不会更改对象本身。

## <a name="in-this-section"></a>本节内容

[TableControl 的 TableColumnHeader 的对齐元素 (格式) ](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)定义列标题中的数据的显示方式。

[TableControl 的 TableColumnItem 的对齐元素 (格式) ](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)定义行中的数据的显示方式。

[TableControl 的 AutoSize 元素 (格式) ](./autosize-element-for-tablecontrol-format.md)指定是否根据数据大小调整列大小和列数。

[WideControl 的 Autosize 元素 (格式) ](./autosize-element-for-widecontrol-format.md)指定是否根据数据大小调整列大小和列数。

[WideControl 的 ColumnNumber 元素 (格式) ](./columnnumber-element-for-widecontrol-format.md)指定宽视图中显示的列数。

[配置元素 (格式) ](./configuration-element-format.md)表示格式设置文件的顶级元素。

[用于配置 (格式的控件的控件元素) ](./control-element-for-controls-for-configuration-format.md)定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。

[View (格式的控件控件元素) ](./control-element-for-controls-for-view-format.md)定义可供视图使用的控件以及用于引用控件的名称。

[配置 (格式的 Controls 元素) ](./controls-element-for-configuration-format.md)定义可供格式设置文件的所有视图使用的公共控件。

[View (格式的 Controls 元素) ](./controls-element-for-view-format.md)定义可供特定视图使用的视图控件。

用于[控制配置 (格式的 CustomControl 元素) ](./customcontrol-element-for-control-for-controls-for-configuration-format.md)定义控件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件 (格式的控件的 CustomControl 元素) ](./customcontrol-element-for-control-for-controls-for-view-format.md)定义视图使用的控件。

[GroupBy (格式的 CustomControl 元素) ](./customcontrol-element-for-groupby-format.md)定义显示新组的自定义控件。

[CustomControl 元素 (格式) ](./customcontrol-element-for-groupby-format.md)定义视图的自定义控件格式。

用于[配置 (格式的控件的 ExpressionBinding 的 CustomControlName 元素) ](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)指定公共控件的名称。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 ExpressionBindine 的 CustomControlName 元素 (格式) ](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)指定公共控件或视图控件的名称。 定义可由视图使用的控件时，将使用此元素。

[GroupBy (格式的 CustomControlName 元素) ](./customcontrolname-element-for-groupby-format.md)指定用于显示新组的自定义控件的名称。 定义表、列表、宽或自定义控件视图时，将使用此元素。

用于[配置 (格式的控件的 CustomControl 的 CustomEntry 元素) ](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)提供公共控件的定义。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 CustomEntries 的 CustomEntry 元素 (格式) ](./customentry-element-for-customentries-for-controls-for-view-format.md)提供控件的定义。 定义可由视图使用的控件时，将使用此元素。

[View (格式的 CustomEntries 的 CustomEntry 元素) ](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)提供自定义控件视图的定义。

[GroupBy (格式的 CustomControl 的 CustomEntry 元素) ](./customentry-element-for-customcontrol-for-groupby-format.md)提供控件的定义。 此元素在定义如何显示新的对象组时使用。

[用于配置 (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)提供公共控件的定义。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 CustomControl 的 CustomEntries 元素 (格式) ](./customentries-element-for-customcontrol-for-controls-for-view-format.md)提供控件的定义。 定义可由视图使用的控件时，将使用此元素。

[GroupBy (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-groupby-format.md)提供控件的定义。 此元素在定义如何显示新的对象组时使用。

[View (格式的 CustomControl 的 CustomEntries 元素) ](./customentries-element-for-customcontrol-for-view-format.md)提供自定义控件视图的定义。 自定义控件视图必须指定一个或多个定义。

用于[配置控件的 CustomEntry 的 CustomItem 元素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)定义控件显示的数据及其显示方式。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 CustomEntry 的 CustomItem 元素 (格式) ](./customitem-element-for-customentry-for-controls-for-view-format.md)定义控件显示的数据及其显示方式。 定义可由视图使用的控件时，将使用此元素。

[View (格式的 CustomEntry 的 CustomItem 元素) ](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)定义自定义控件视图显示的数据及其显示方式。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 CustomEntry 的 CustomItem 元素) ](./customitem-element-for-customentry-for-groupby-format.md)定义自定义控件视图显示的数据及其显示方式。 此元素在定义如何显示新的对象组时使用。

[DefaultSettings 元素 (格式) ](./defaultsettings-element-format.md)定义适用于格式设置文件的所有视图的常见设置。 常见的设置包括显示错误、在表中环绕文本、定义集合的展开方式等。

[DisplayError 元素 (格式) ](./displayerror-element-format.md)指定在显示一段数据时出现错误时显示字符串 #ERR。

用于[配置 (格式的控件的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 CustomEntry 的 EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。 定义可由视图使用的控件时，将使用此元素。

[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)定义使用此自定义项的 .NET 类型或此项要使用的条件。

[EnumerableExpansion 的 EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-enumerableexpansion-format.md)定义使用此定义的 .NET 类型或要使用此定义时必须存在的条件。

[GroupBy (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-groupby-format.md)定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。 此元素在定义如何显示新的对象组时使用。

[ListControl (格式的 ListEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-listentry-for-listcontrol-format.md)定义使用此列表视图定义或要使用此定义必须存在的条件的 .NET 类型。 在大多数情况下，列表视图只需要一个定义。 但是，如果您希望使用同一列表视图为不同对象显示不同的数据，则可以为列表视图提供多个定义。

[TableRowEntry 的 EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)定义其属性值显示在行中的 .NET 类型。

[WideEntry 的 EntrySelectedBy 元素 (格式) ](./entryselectedby-element-for-wideentry-format.md)定义使用此类定义的 .NET 类型或使用此定义时必须存在的条件。

[EnumerableExpansion 元素 (格式) ](./enumerableexpansion-element-format.md)定义特定 .NET 集合对象在视图中显示的方式。

[EnumerableExpansions 元素 (格式) ](./enumerableexpansions-element-format.md)定义在视图中显示 .NET 集合对象时如何对其进行扩展。

用于[配置 (格式的控件的 ExpressionBinding 的 EnumerateCollection 元素) ](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)指定控件所显示的集合元素。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 ExpressionBinding 的 EnumerateCollection 元素 (格式) ](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)指定显示集合的元素。 定义可由视图使用的控件时，将使用此元素。

[CustomControl (格式的表达式绑定的 EnumerateCollection 元素) ](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)指定显示集合的元素。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 ExpressionBinding 的 EnumerateCollection 元素) ](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)指定显示集合的元素。 此元素在定义如何显示新的对象组时使用。

[展开元素 (格式) ](./expand-element-format.md)指定为此定义扩展集合对象的方式。

用于[配置 (格式的控件的 CustomItem 的 ExpressionBinding 元素) ](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)定义控件显示的数据。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 CustomItem 的 ExpressionBinding 元素 (格式) ](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)定义控件显示的数据。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl For View (Format) 的 CustomItem 的 ExpressionBinding 元素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)定义控件显示的数据。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 CustomItem 的 ExpressionBinding 元素) ](./expressionbinding-element-for-customitem-for-groupby-format.md)定义控件显示的数据。 此元素在定义如何显示新的对象组时使用。

[ (格式的控件的框架的 FirstLineHanging 元素) ](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)指定将第一行数据向左移动的字符数。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[View (Format) 的控件的框架的 FirstLineHanging 元素](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)指定将第一行数据向左移动的字符数。 定义可由视图使用的控件时，将使用此元素。

[View () 格式的 CustomControl 的帧的 FirstLineHanging 元素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)指定将第一行数据向左移动的字符数。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的帧的 FirstLineHanging 元素) ](./firstlinehanging-element-for-frame-for-groupby-format.md)指定将第一行数据向左移动的字符数。 此元素在定义如何显示新的对象组时使用。

[ (格式的控件的框架的 FirstLineIndent 元素) ](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)指定第一行数据向右移动的字符数。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[View (Format) 的控件的框架的 FirstLineIndent 元素](./firstlineindent-element-for-frame-for-controls-for-view-format.md)指定第一行数据向右移动的字符数。 定义可由视图使用的控件时，将使用此元素。

[FirstLineIndent 元素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)指定第一行数据向右移动的字符数。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的帧的 FirstLineIndent 元素) ](./firstlineindent-element-for-frame-for-groupby-format.md)指定第一行数据向右移动的字符数。 此元素在定义如何显示新的对象组时使用。

[输入 (格式的格式字符串元素) ](./formatstring-element-for-listitem-for-listcontrol-format.md)指定一个定义如何显示属性或脚本值的格式模式。

[TableColumnItem (格式的格式字符串元素) ](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)指定一种格式模式，用于定义表的属性或脚本值的显示方式。

[WideControl (格式的 WideItem 的格式字符串元素) ](./formatstring-element-for-wideitem-for-widecontrol-format.md)指定定义属性或脚本值在视图中显示方式的格式模式。

用于[配置 (格式的控件的 CustomItem 的框架元素) ](./frame-element-for-customitem-for-controls-for-configuration-format.md)定义数据的显示方式，例如，将数据向左或向右移动。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 CustomItem 的框架元素) ](./frame-element-for-customitem-for-controls-for-view-format.md)定义数据的显示方式，例如，将数据向左或向右移动。 定义可由视图使用的控件时，将使用此元素。

[CustomControl 的 CustomItem For View (格式的 Frame 元素) ](./frame-element-for-customitem-for-customcontrol-for-view-format.md)定义数据的显示方式，例如，将数据向左或向右移动。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 CustomItem 的框架元素) ](./frame-element-for-customitem-for-groupby-format.md)定义数据的显示方式，例如，将数据向左或向右移动。 此元素在定义如何显示新的对象组时使用。

[View (格式的 GroupBy 元素) ](./groupby-element-for-view-format.md)定义 Windows PowerShell 如何显示一组新的对象。

[HideTableHeaders 元素 (格式) ](./hidetableheaders-element-format.md)指定不显示表的标头。

用于[配置 (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)定义要使用此控件必须存在的条件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[View (格式的控件的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)定义要使用此控件必须存在的条件。 定义可由视图使用的控件时，将使用此元素。

[CustomControl (格式的表达式绑定的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)定义要使用此控件必须存在的条件。 对于可为控件项指定的选择条件数没有限制。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 ExpressionBinding 的 ItemSelectionCondition 元素) ](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)定义要使用此控件必须存在的条件。 对于可为控件项指定的选择条件数没有限制。 此元素在定义如何显示新的对象组时使用。

[ItemSelectionCondition 的元素 (格式) ](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)定义要使用此列表项必须存在的条件。

[ListControl (格式的输入标记元素) ](./label-element-for-listitem-for-listcontrol-format.md)为行中的属性或脚本值指定标签。

[GroupBy (格式的标签元素) ](./label-element-for-groupby-format.md)指定在遇到新组时显示的标签。

[TableColumnHeader (格式的 Label 元素) ](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)定义在列顶部显示的标签。

[ (格式的控件的框架的 LeftIndent 元素) ](./leftindent-element-for-frame-for-controls-for-configuration-format.md)指定数据从左边距向外移动的字符数。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[View (Format) 的控件的框架的 LeftIndent 元素](./leftindent-element-for-frame-for-controls-for-view-format.md)指定数据从左边距向外移动的字符数。 定义可由视图使用的控件时，将使用此元素。

[View () 格式的 CustomControl 的帧的 LeftIndent 元素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)指定数据从左边距向外移动的字符数。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的帧的 LeftIndent 元素) ](./leftindent-element-for-frame-for-groupby-format.md)指定数据从左边距向外移动的字符数。 此元素在定义如何显示新的对象组时使用。

[ListControl 元素 (格式) ](./listcontrol-element-format.md)定义视图的列表格式。

[ListEntry 元素 (格式) ](./listentry-element-for-listcontrol-format.md)提供列表视图的定义。

[ListEntries 元素 (格式) ](./listentries-element-for-listcontrol-format.md)定义显示列表视图行的方式。

[ (格式的) 元素元素](./listitem-element-for-listitems-for-listcontrol-format.md)定义其值显示在列表视图的行中的属性或脚本。

[ListItems 元素 (格式) ](./listitems-element-for-listentry-for-listcontrol-format.md)定义在列表视图中显示的属性和脚本。

用于[控件控件的名称元素 (格式) ](./name-element-for-control-for-controls-for-configuration-format.md)指定控件的名称。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[SelectionSet (格式的 Name 元素) ](./name-element-for-selectionset-format.md)指定用于引用选项集的名称。

[View (格式的 Name 元素) ](./name-element-for-view-format.md)指定用于标识视图的名称。

用于[配置 (格式的控件的 CustomItem 的换行符元素) ](./newline-element-for-customitem-for-controls-for-configuration-format.md)向控件的显示添加一个空白行。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 CustomItem 的换行符元素) ](./newline-element-for-customitem-for-controls-for-view-format.md)向控件的显示添加一个空白行。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl 的 CustomItem For View (格式的换行符元素) ](./newline-element-for-customitem-for-customcontrol-for-view-format.md)向控件的显示添加一个空白行。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 CustomItem 的换行符元素) ](./newline-element-for-customitem-for-groupby-format.md)向控件的显示添加一个空白行。 此元素在定义如何显示新的对象组时使用。

用于[配置 (格式的控件的 ExpressionBinding 的 PropertyName 元素) ](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)指定 .NET 属性，其值由公共控件显示。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 ExpressionBinding 的 PropertyName 元素) ](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)指定其值由控件显示的 .NET 属性。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl 的 ExpressionBinding For View (格式的 PropertyName 元素) ](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)指定其值由控件显示的 .NET 属性。 定义自定义控件视图时使用此元素

[GroupBy (格式的 ExpressionBinding 的 PropertyName 元素) ](./propertyname-element-for-expressionbinding-for-groupby-format.md)指定其值由控件显示的 .NET 属性。 此元素在定义如何显示新的对象组时使用。

[GroupBy (格式的 PropertyName 元素) ](./propertyname-element-for-groupby-format.md)指定在新组的值发生更改时启动新组的 .NET 属性。

用于[配置 (格式的控件的 ItemSeclectionCondition 的 PropertyName 元素) ](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 ItemSelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 定义可由视图使用的控件时，将使用此元素。

用于[View (格式的 CustomControl 的 ItemSelectionCondition 的 PropertyName 元素](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 ItemSelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用控件。 此元素在定义如何显示新的对象组时使用。

[ItemSelectionCondition 的 PropertyName 元素 (格式) ](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用视图。 定义列表视图时，将使用此元素。

[ListControl (格式的名称的 PropertyName 元素) ](./propertyname-element-for-listitem-for-listcontrol-format.md)指定其值显示在列表中的 .NET 属性。

[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用该条目。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用该条目。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl 的 SelectionCondition For View (格式的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。 定义自定义控件视图时，将使用此元素。

[EnumerableExpansion (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。

[GroupBy (格式的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-groupby-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。 此元素在定义如何显示新的对象组时使用。

[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用列表项。

[TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用表项。

[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素) ](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)指定触发条件的 .NET 属性。 如果该属性存在或其计算结果为 `true` ，则满足条件，并使用定义。

[TableColumnItem (格式的 PropertyName 元素) ](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)指定其值显示在行的列中的属性。

[WideItem (格式的 PropertyName 元素) ](./propertyname-element-for-wideitem-for-widecontrol-format.md)指定对象的属性，其值显示在宽视图中。

[ (格式的控件的框架的 RightIndent 元素) ](./rightindent-element-for-frame-for-controls-for-configuration-format.md)指定数据从右边缘向外移动的字符数。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[View (Format) 的控件的框架的 RightIndent 元素](./rightindent-element-for-frame-for-controls-for-view-format.md)指定数据从右边缘向外移动的字符数。 定义可由视图使用的控件时，将使用此元素。

[RightIndent 元素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)指定数据从右边缘向外移动的字符数。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的帧的 RightIndent 元素) ](./rightindent-element-for-frame-for-groupby-format.md)指定数据从右边缘向外移动的字符数。 此元素在定义如何显示新的对象组时使用。

用于[配置 (格式的控件的 ExpressionBinding 的 ScriptBlock 元素) ](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)指定其值由公共控件显示的脚本。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 ExpressionBinding 的 ScriptBlock 元素) ](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)指定其值由控件显示的脚本。 定义可由视图使用的控件时，将使用此元素。

用于[CustomCustomControl 的 ExpressionBinding 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)指定其值由控件显示的脚本。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 ExpressionBinding 的 ScriptBlock 元素) ](./scriptblock-element-for-expressionbinding-for-groupby-format.md)指定其值由控件显示的脚本。 此元素在定义如何显示新的对象组时使用。

[GroupBy (格式的 ScriptBlock 元素) ](./scriptblock-element-for-groupby-format.md)指定在新组的值发生更改时启动新组的脚本。

用于[配置 (格式的控件的 ItemSelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 ItemSelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl 的 ItemSelectionCondition 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 ItemSelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用控件。 此元素在定义如何显示新的对象组时使用。

[ListControl (格式的 ItemSelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。 定义列表视图时，将使用此元素。

[输入 (格式的 ScriptBlock 元素) ](./scriptblock-element-for-listitem-for-listcontrol-format.md)指定其值显示在列表的行中的脚本。

用于[配置 (格式的控件的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl 的 SelectionCondition 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。 定义自定义控件视图时，将使用此元素。

用于[EnumerableExpansion (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)指定触发条件的脚本。

[GroupBy (格式的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用定义。 此元素在定义如何显示新的对象组时使用。

用于[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。

用于[TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)指定触发条件的脚本块。 将此脚本的计算结果为时 `true` ，将满足条件，并使用表项。

用于[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素) ](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)指定触发条件的脚本。 将此脚本的计算结果为时 `true` ，将满足条件，并使用宽输入定义。

[TableColumnItem 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)指定其值显示在行的列中的脚本。

[WideItem 的 ScriptBlock 元素 (格式) ](./scriptblock-element-for-wideitem-for-widecontrol-format.md)指定其值在宽视图中显示的脚本。

用于[CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)定义要使用的公共控件定义必须存在的条件。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 EntrySelectedBy 的 SelectionCondition 元素 (格式) ](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)定义要使用的控件定义必须存在的条件。 定义可由视图使用的控件时，将使用此元素。

用于[CustomControl For View (Format) 的 EntrySelectedBy 的 SelectionCondition 元素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)定义要使用的控件定义必须存在的条件。 定义自定义控件视图时，将使用此元素。

[EnumerableExpansion (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)定义扩展此定义的集合对象时必须存在的条件。

[GroupBy (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)定义要使用的控件定义必须存在的条件。 此元素在定义如何显示新的对象组时使用。

[ListEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)定义使用此列表视图的定义时必须存在的条件。 对于列表定义可以指定的选择条件数量没有限制。

[TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)定义必须存在才能用于此表视图定义的条件。 对于可为表定义指定的选择条件数没有限制。

[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) ](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)定义要使用此定义必须存在的条件。 对于可为宽输入定义指定的选择条件数没有限制。

[SelectionSet 元素 (格式) ](./selectionset-element-format.md)定义一组可由集名称引用的 .NET 对象。

用于[配置 (格式的控件的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)指定一组使用此控件定义的 .NET 类型。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 EntrySelectedBy 的 SelectionSetName 元素 (格式) ](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)指定一组使用此控件定义的 .NET 类型。 定义可由视图使用的控件时，将使用此元素。

[CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)为列表条目指定一组 .NET 对象。 对于可为条目指定的选项集数没有限制。

[EnumerableExpansion (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)指定通过此定义扩展的 .NET 类型集。

[GroupBy (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)为列表条目指定一组 .NET 对象。 对于可为条目指定的选项集数没有限制。 此元素在定义如何显示新的对象组时使用。

[ListEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)为列表条目指定一组 .NET 对象。 对于可为条目指定的选项集数没有限制。

[TableRowEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)指定使用此表视图项的一组 .NET 类型。 对于可为条目指定的选项集数没有限制。

[WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) ](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)为定义指定一组 .NET 对象。 当显示其中一个对象时，将使用该定义。

用于[配置 (格式的控件的 SelectionCondition 的 SelectionSetName 元素) ](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

用于[控件的 SelectionCondition 的 SelectionSetName 元素 (格式) ](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。 定义可由视图使用的控件时，将使用此元素。

[View (格式的 CustomEntry 的 EntrySelectedBy 元素) ](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。 定义自定义控件视图时，将使用此元素。

用于[EntrySelectedBy For EnumerableExpansion (Format) 的 SelectionCondition 的 SelectionSetName 元素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件。

[GroupBy (格式的 SelectionCondition 的 SelectionSetName 元素) ](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此控件显示该对象。 此元素在定义如何显示新的对象组时使用。

用于[EntrySelectedBy For ListEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此列表视图的定义显示该对象。

用于[EntrySelectedBy For TableRowEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用表视图的这一定义显示该对象。

用于[EntrySelectedBy For WideEntry (Format) 的 SelectionCondition 的 SelectionSetName 元素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)指定触发条件的 .NET 类型集。 如果此集中的任何类型存在，则满足条件，并使用此大视图的定义显示该对象。

[ViewSelectedBy 的 SelectionSetName 元素 (格式) ](./selectionsetname-element-for-viewselectedby-format.md)指定视图显示的一组 .NET 对象。

[SelectionSets 元素 (格式) ](./selectionsets-element-format.md)定义可由单独的格式视图使用的 .NET 对象集。

[ShowError 元素 (格式) ](./showerror-element-format.md)指定在显示一段数据的过程中出现错误时，显示完整的错误记录。

[TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) ](./tablecolumnheader-element-format.md)定义标签、列的宽度和表中某一列的标签对齐方式。

[TableColumnItem 元素 (格式) ](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)定义其值显示在行的列中的属性或脚本。

[TableColumnItems 元素 (格式) ](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)定义其值显示在行中的属性或脚本。

[TableControl 元素 (格式) ](./tablecontrol-element-format.md)定义视图的表格格式。

[TableHeaders 元素 (格式) ](./tableheaders-element-format.md)定义表中各列的标头。

[TableRowEntries 元素 (格式) ](./tablerowentries-element-for-tablecontrol-format.md)定义表中的行。

[TableRowEntry 元素 (格式) ](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)定义在表的行中显示的数据。

用于[配置 (格式的控件的 CustomItem 文本元素) ](./text-element-for-customitem-for-controls-for-configuration-format.md)指定添加到由控件显示的数据的文本，如标签、用方括号括起来的数据以及用于缩进数据的空格。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 CustomItem 文本元素) ](./text-element-for-customitem-for-controls-for-view-format.md)指定添加到由控件显示的数据的文本，如标签、用方括号括起来的数据以及用于缩进数据的空格。 定义可由视图使用的控件时，将使用此元素。

[CustomItem (格式的文本元素) ](./text-element-for-customitem-for-customview-for-view-format.md)指定添加到由控件显示的数据的文本，如标签、用方括号括起来的数据以及用于缩进数据的空格。 定义自定义控件视图时，将使用此元素。

[GroupBy (格式的 CustomItem 文本元素) ](./text-element-for-customitem-for-groupby-format.md)指定添加到由控件显示的数据的文本，如标签、用方括号括起来的数据以及用于缩进数据的空格。 此元素在定义如何显示新的对象组时使用。

用于[配置 (格式的控件的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)指定使用控件的此定义的 .NET 类型。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-controls-for-view-format.md)指定使用控件的此定义的 .NET 类型。 定义可由视图使用的控件时，将使用此元素。

[EntrySelectedBy For CustomEntry 的 TypeName 元素 (Format) ](./typename-element-for-entryselectedby-for-customentry-for-view-format.md)指定使用自定义控件视图的此定义的 .NET 类型。 对于可以为定义指定的类型数量没有限制。

[EnumerableExpansion (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)指定通过此定义扩展的 .NET 类型。 定义默认设置时，将使用此元素。

[GroupBy (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-groupby-format.md)指定使用自定义控件的此定义的 .NET 类型。 此元素在定义如何显示新的对象组时使用。

[ListControl (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-listcontrol-format.md)指定使用此列表视图项的 .NET 类型。 对于列表项可以指定的类型数量没有限制。

[TableRowEntry (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-tablecontrol-format.md)指定使用此表视图项的 .NET 类型。 对于可为表条目指定的类型数量没有限制。

[WideEntry (格式的 EntrySelectedBy 的 TypeName 元素) ](./typename-element-for-entryselectedby-for-wideentry-format.md)为定义指定 .NET 类型。 只要显示此对象，就会使用定义。

用于[配置 (格式的控件的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)指定触发条件的 .NET 类型。 此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。

[视图 (格式的控件的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-controls-for-view-format.md)指定触发条件的 .NET 类型。 定义可由视图使用的控件时，将使用此元素。

[SelectionCondition For CustomControl 的 TypeName 元素 (Format) ](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)指定触发条件的 .NET 类型。 定义自定义控件视图时，将使用此元素。

用于[EnumerableExpansion (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)指定触发条件的 .NET 类型。

[GroupBy (格式的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-groupby-format.md)指定触发条件的 .NET 类型。 此元素在定义如何显示新的对象组时使用。

用于[ListControl (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)指定触发条件的 .NET 类型。 如果存在此类型，则使用列表项。

用于[TableRowEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)指定触发条件的 .NET 类型。 如果存在此类型，则满足条件，并使用表行。

用于[WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 的 TypeName 元素) ](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)指定触发条件的 .NET 类型。 如果存在此类型，则使用定义。

[类型 (格式的 TypeName 元素) ](./typename-element-for-types-format.md)指定属于选择集的对象的 .NET 类型。

[ViewSelectedBy (格式的 TypeName 元素) ](./typename-element-for-viewselectedby-format.md)指定视图显示的 .NET 对象。

[类型元素 (格式) ](./types-element-for-selectionset-format.md)定义选择集中的 .NET 对象。

[ (格式的 View 元素) ](./view-element-format.md)定义用于显示一个或多个 .NET 对象的视图。

[ViewDefinitions 元素 (格式) ](./viewdefinitions-element-format.md)定义用于显示对象的视图。

[ViewSelectedBy 元素 (格式) ](./viewselectedby-element-format.md)定义视图显示的 .NET 对象。

[WideControl 元素 (格式) ](./widecontrol-element-format.md)定义视图的宽 (单个值) 列表格式。 此视图显示每个对象的单个属性值或脚本值。

[WideEntries 元素 (格式) ](./wideentries-element-for-widecontrol-format.md)提供宽视图的定义。 宽视图必须指定一个或多个定义。

[WideEntry 元素 (格式) ](./wideentry-element-for-widecontrol-format.md)提供宽视图的定义。

[WideItem 元素 (格式) ](./wideitem-element-for-widecontrol-format.md)定义要显示其值的属性或脚本。

[Width 元素 (格式) ](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)定义列的字符)  (的宽度。

[ (格式的环绕元素) ](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)指定在下一行显示超过列宽的文本。

[WrapTables 元素 (格式) ](./wraptables-element-format.md)指定如果数据的长度超过列的宽度，则将表单元格中的数据移到下一行。

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
