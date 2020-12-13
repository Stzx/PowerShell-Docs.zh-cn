---
ms.date: 09/13/2016
ms.topic: reference
title: ViewSelectedBy Element (Format)
description: ViewSelectedBy Element (Format)
ms.openlocfilehash: ac3c7de299b3009a067a476a024c6a6fcb5dce02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667702"
---
# <a name="viewselectedby-element-format"></a>ViewSelectedBy Element (Format)

定义视图显示的 .NET 对象。 每个视图必须至少指定一个 .NET 对象。

ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `ViewSelectedBy` 。 此元素必须包含至少一个 `TypeName` 或 `SelectionSetName` 子元素。 对于可以指定的子元素数没有限制，也没有其顺序。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[TypeName Element for ViewSelectedBy (Format)](./typename-element-for-viewselectedby-format.md)|可选元素。<br /><br /> 指定视图显示的 .NET 对象。|
|[SelectionSetName Element for ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)|可选元素。<br /><br /> 指定视图显示的一组 .NET 对象。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View Element (Format)](./view-element-format.md)|定义一个视图，该视图显示一个或多个 .NET 对象。|

## <a name="remarks"></a>备注

有关此元素在不同视图中的使用方式的详细信息，请参阅 [表视图组件](./creating-a-table-view.md)、 [列表视图](./creating-a-list-view.md)组件、 [宽视图组件](./creating-a-wide-view.md)和 [自定义控件组件](./creating-custom-controls.md)。

`SelectionSetName`当格式设置文件定义了由多个视图显示的一组对象时，使用元素。 有关如何定义和引用选择集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。

## <a name="example"></a>示例

下面的示例演示如何为列表视图指定 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象。 表、宽视图和自定义视图使用相同的架构。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>另请参阅

[创建列表视图](./creating-a-list-view.md)

[创建表视图](./creating-a-table-view.md)

[创建宽视图](./creating-a-wide-view.md)

[创建自定义控件](./creating-custom-controls.md)

[定义选项集](./defining-selection-sets.md)

[SelectionSetName Element for ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)

[TypeName 元素 (格式) ](./typename-element-for-viewselectedby-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
