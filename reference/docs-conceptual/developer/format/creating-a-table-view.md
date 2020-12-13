---
ms.date: 09/13/2016
ms.topic: reference
title: 创建表视图
description: 创建表视图
ms.openlocfilehash: 035d42f7968a9e8babec692a7a5873e24b36cd97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660302"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="267cd-103">创建表视图</span><span class="sxs-lookup"><span data-stu-id="267cd-103">Creating a Table View</span></span>

<span data-ttu-id="267cd-104">表视图在一个或多个列中显示数据。</span><span class="sxs-lookup"><span data-stu-id="267cd-104">A table view displays data in one or more columns.</span></span> <span data-ttu-id="267cd-105">表中的每一行都表示一个 .NET 对象，表中的每一列都表示该对象的一个属性或一个脚本值。</span><span class="sxs-lookup"><span data-stu-id="267cd-105">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="267cd-106">您可以定义显示对象的所有属性或对象的属性子集的表视图。</span><span class="sxs-lookup"><span data-stu-id="267cd-106">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="267cd-107">表格视图显示</span><span class="sxs-lookup"><span data-stu-id="267cd-107">A Table View Display</span></span>

<span data-ttu-id="267cd-108">下面的示例演示 Windows PowerShell 如何显示由 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) [Cmdlet 返回](/powershell/module/microsoft.powershell.management/get-service) 的 system.serviceprocess 对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-108">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="267cd-109">对于此对象，Windows PowerShell 定义了显示属性的表视图 `Status` ， `Name` (此属性的属性为 `ServiceName` 属性) 和属性的别名属性 `DisplayName` 。</span><span class="sxs-lookup"><span data-stu-id="267cd-109">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="267cd-110">表中的每一行表示该 cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-110">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="267cd-111">定义表视图</span><span class="sxs-lookup"><span data-stu-id="267cd-111">Defining the Table View</span></span>

<span data-ttu-id="267cd-112">下面的 XML 演示用于显示 [system.serviceprocess. Servicecontroller 的表视图架构。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) 对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-112">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="267cd-113">您必须指定要在表视图中显示的每个属性。</span><span class="sxs-lookup"><span data-stu-id="267cd-113">You must specify each property that you want displayed in the table view.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

<span data-ttu-id="267cd-114">以下 XML 元素用于定义列表视图：</span><span class="sxs-lookup"><span data-stu-id="267cd-114">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="267cd-115">[View](./view-element-format.md)元素是表视图的父元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-115">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="267cd-116"> (这是 "列表"、"宽" 和 "自定义" 控件视图的相同父元素。 ) </span><span class="sxs-lookup"><span data-stu-id="267cd-116">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="267cd-117">[Name](./name-element-for-view-format.md)元素指定视图的名称。</span><span class="sxs-lookup"><span data-stu-id="267cd-117">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="267cd-118">此元素对于所有视图都是必需的。</span><span class="sxs-lookup"><span data-stu-id="267cd-118">This element is required for all views.</span></span>

- <span data-ttu-id="267cd-119">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义使用视图的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="267cd-120">此元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="267cd-120">This element is required.</span></span>

- <span data-ttu-id="267cd-121">此示例中未显示 [GroupBy](./groupby-element-for-view-format.md) 元素 () 定义显示新的对象组的时间。</span><span class="sxs-lookup"><span data-stu-id="267cd-121">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="267cd-122">每当特定属性或脚本的值发生更改时，就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="267cd-122">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="267cd-123">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-123">This element is optional.</span></span>

- <span data-ttu-id="267cd-124">在此示例中不显示 [Controls](./controls-element-for-view-format.md) 元素 () 定义由表视图定义的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="267cd-124">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="267cd-125">控件使您可以进一步指定数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="267cd-125">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="267cd-126">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-126">This element is optional.</span></span> <span data-ttu-id="267cd-127">视图可以定义自己的自定义控件，也可以使用可由格式设置文件中的任何视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="267cd-127">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="267cd-128">有关自定义控件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="267cd-128">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="267cd-129">在此示例中， [HideTableHeaders](./hidetableheaders-element-format.md) 元素 (不显示) 指定表将不会在表的顶部显示任何标签。</span><span class="sxs-lookup"><span data-stu-id="267cd-129">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="267cd-130">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-130">This element is optional.</span></span>

- <span data-ttu-id="267cd-131">定义表的标头和行信息的 [TableControl](./tablecontrol-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-131">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="267cd-132">与所有其他视图类似，表视图可以显示对象属性的值或脚本生成的值。</span><span class="sxs-lookup"><span data-stu-id="267cd-132">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="267cd-133">定义列标题</span><span class="sxs-lookup"><span data-stu-id="267cd-133">Defining Column Headers</span></span>

1. <span data-ttu-id="267cd-134">[TableHeaders](./tableheaders-element-format.md)元素及其子元素定义在表顶部显示的内容。</span><span class="sxs-lookup"><span data-stu-id="267cd-134">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="267cd-135">[TableColumnHeader](./tablecolumnheader-element-format.md)元素定义在表的列顶部显示的内容。</span><span class="sxs-lookup"><span data-stu-id="267cd-135">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="267cd-136">按您希望标题显示的顺序指定这些元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-136">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="267cd-137">您可以使用的这些元素的数量没有限制，但表视图中的 [TableColumnHeader](./tablecolumnheader-element-format.md) 元素数目必须等于您使用的 [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) 元素的数目。</span><span class="sxs-lookup"><span data-stu-id="267cd-137">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="267cd-138">[Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)元素指定显示的文本。</span><span class="sxs-lookup"><span data-stu-id="267cd-138">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="267cd-139">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-139">This element is optional.</span></span>

4. <span data-ttu-id="267cd-140">[Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)元素指定列 (以字符) 的宽度。</span><span class="sxs-lookup"><span data-stu-id="267cd-140">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="267cd-141">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-141">This element is optional.</span></span>

5. <span data-ttu-id="267cd-142">[对齐](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)元素指定如何显示标签。</span><span class="sxs-lookup"><span data-stu-id="267cd-142">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="267cd-143">标签可以左对齐、右对齐或居中对齐。</span><span class="sxs-lookup"><span data-stu-id="267cd-143">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="267cd-144">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-144">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="267cd-145">定义表行</span><span class="sxs-lookup"><span data-stu-id="267cd-145">Defining the Table Rows</span></span>

<span data-ttu-id="267cd-146">表视图可以提供一个或多个定义，这些定义通过使用 [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) 元素的子元素来指定在表的行中显示哪些数据。</span><span class="sxs-lookup"><span data-stu-id="267cd-146">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="267cd-147">请注意，您可以为表中的行指定多个定义，但无论使用哪种行定义，行的标头都保持不变。</span><span class="sxs-lookup"><span data-stu-id="267cd-147">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="267cd-148">通常，表只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="267cd-148">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="267cd-149">在下面的示例中，视图提供了一个定义，用于显示系统的多个属性的值 [。Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) 对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-149">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="267cd-150">表视图可以显示属性的值或脚本的值 (未显示在其行的示例) 中。</span><span class="sxs-lookup"><span data-stu-id="267cd-150">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

<span data-ttu-id="267cd-151">以下 XML 元素可用于为行提供定义：</span><span class="sxs-lookup"><span data-stu-id="267cd-151">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="267cd-152">[TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)元素及其子元素定义在表的行中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="267cd-152">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="267cd-153">[TableRowEntry](./listentry-element-for-listcontrol-format.md)元素提供行的定义。</span><span class="sxs-lookup"><span data-stu-id="267cd-153">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="267cd-154">至少需要一个 [TableRowEntry](./listentry-element-for-listcontrol-format.md) ;但是，可以添加的元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="267cd-154">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="267cd-155">在大多数情况下，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="267cd-155">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="267cd-156">[EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)元素指定由特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-156">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="267cd-157">此元素是可选的，仅当定义显示不同对象的多个 [TableRowEntry](./listentry-element-for-listcontrol-format.md) 元素时才需要此元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-157">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="267cd-158">[Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)元素指定超出列宽的文本显示在下一行。</span><span class="sxs-lookup"><span data-stu-id="267cd-158">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="267cd-159">默认情况下，超过列宽的文本将被截断。</span><span class="sxs-lookup"><span data-stu-id="267cd-159">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="267cd-160">[TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)元素定义其值显示在行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="267cd-160">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="267cd-161">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)元素定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="267cd-161">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="267cd-162">行的每个列都需要一个 [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-162">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="267cd-163">第一项显示在第一列中，第二项显示在第二列，依此类推。</span><span class="sxs-lookup"><span data-stu-id="267cd-163">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="267cd-164">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)元素指定其值显示在行中的属性。</span><span class="sxs-lookup"><span data-stu-id="267cd-164">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="267cd-165">您必须指定属性或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="267cd-165">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="267cd-166">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)元素指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="267cd-166">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="267cd-167">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="267cd-167">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="267cd-168">"格式 [字符串](./label-element-for-listitem-for-listcontrol-format.md) " 元素指定定义如何显示属性或脚本值的格式模式。</span><span class="sxs-lookup"><span data-stu-id="267cd-168">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="267cd-169">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-169">This element is optional.</span></span>

- <span data-ttu-id="267cd-170">[对齐](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)元素指定属性或脚本的值的显示方式。</span><span class="sxs-lookup"><span data-stu-id="267cd-170">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="267cd-171">值可以左对齐、右对齐或居中对齐。</span><span class="sxs-lookup"><span data-stu-id="267cd-171">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="267cd-172">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-172">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="267cd-173">定义使用表视图的对象</span><span class="sxs-lookup"><span data-stu-id="267cd-173">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="267cd-174">可以通过两种方法来定义哪些 .NET 对象使用表视图。</span><span class="sxs-lookup"><span data-stu-id="267cd-174">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="267cd-175">您可以使用 [ViewSelectedBy](./viewselectedby-element-format.md) 元素来定义可由视图的所有定义显示的对象，也可以使用 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) 元素来定义由视图的特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-175">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="267cd-176">在大多数情况下，视图只有一个定义，因此对象通常由 [ViewSelectedBy](./viewselectedby-element-format.md) 元素定义。</span><span class="sxs-lookup"><span data-stu-id="267cd-176">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="267cd-177">下面的示例演示如何使用 [ViewSelectedBy](./viewselectedby-element-format.md) 和 [TypeName](./typename-element-for-viewselectedby-format.md) 元素定义表视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-177">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="267cd-178">对于您可以指定的 [TypeName](./typename-element-for-viewselectedby-format.md) 元素的数量没有限制，它们的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="267cd-178">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="267cd-179">以下 XML 元素可用于指定表视图所使用的对象：</span><span class="sxs-lookup"><span data-stu-id="267cd-179">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="267cd-180">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义列表视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-180">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="267cd-181">[TypeName](./typename-element-for-viewselectedby-format.md)元素指定视图显示的 .net 对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-181">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="267cd-182">完全限定的 .NET 类型名称是必需的。</span><span class="sxs-lookup"><span data-stu-id="267cd-182">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="267cd-183">您必须为视图指定至少一个类型或选择集，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="267cd-183">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="267cd-184">下面的示例使用 [ViewSelectedBy](./viewselectedby-element-format.md) 和 [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-184">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="267cd-185">使用选择集，其中有一组使用多个视图显示的相关对象，例如为同一对象定义列表视图和表视图。</span><span class="sxs-lookup"><span data-stu-id="267cd-185">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="267cd-186">有关如何创建选项集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="267cd-186">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="267cd-187">以下 XML 元素可用于指定列表视图所使用的对象：</span><span class="sxs-lookup"><span data-stu-id="267cd-187">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="267cd-188">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义列表视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-188">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="267cd-189">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)元素指定可由视图显示的一组对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-189">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="267cd-190">您必须为视图指定至少一个选择集或类型，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="267cd-190">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="267cd-191">下面的示例演示如何使用 [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) 元素定义表视图的特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-191">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="267cd-192">使用此元素，可以指定对象的 .NET 类型名称、对象的选择集或指定何时使用定义的选择条件。</span><span class="sxs-lookup"><span data-stu-id="267cd-192">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="267cd-193">有关如何创建选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="267cd-193">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="267cd-194">创建表视图的多个定义时，不能指定不同的列标题。</span><span class="sxs-lookup"><span data-stu-id="267cd-194">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="267cd-195">您只能指定在表的行中显示的内容，例如显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-195">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="267cd-196">以下 XML 元素可用于指定列表视图的特定定义所使用的对象：</span><span class="sxs-lookup"><span data-stu-id="267cd-196">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="267cd-197">[EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)元素定义由定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-197">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="267cd-198">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)元素指定由定义显示的 .net 对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-198">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="267cd-199">使用此元素时，必须提供完全限定的 .NET 类型名称。</span><span class="sxs-lookup"><span data-stu-id="267cd-199">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="267cd-200">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="267cd-200">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="267cd-201"> (未显示的 [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) 元素) 指定可由此定义显示的一组对象。</span><span class="sxs-lookup"><span data-stu-id="267cd-201">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="267cd-202">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="267cd-202">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="267cd-203"> (未显示的 [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) 元素) 指定要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="267cd-203">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="267cd-204">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="267cd-204">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="267cd-205">有关定义选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="267cd-205">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="267cd-206">使用格式字符串</span><span class="sxs-lookup"><span data-stu-id="267cd-206">Using Format Strings</span></span>

<span data-ttu-id="267cd-207">可以将字符串的格式添加到视图中，以便进一步定义数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="267cd-207">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="267cd-208">下面的示例演示如何为属性的值定义格式字符串 `StartTime` 。</span><span class="sxs-lookup"><span data-stu-id="267cd-208">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="267cd-209">以下 XML 元素可用于指定格式模式：</span><span class="sxs-lookup"><span data-stu-id="267cd-209">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="267cd-210">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)元素定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="267cd-210">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="267cd-211">行的每个列都需要一个 [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-211">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="267cd-212">第一项显示在第一列中，第二项显示在第二列，依此类推。</span><span class="sxs-lookup"><span data-stu-id="267cd-212">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="267cd-213">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)元素指定其值显示在行中的属性。</span><span class="sxs-lookup"><span data-stu-id="267cd-213">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="267cd-214">您必须指定属性或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="267cd-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="267cd-215">"格式 [字符串](./label-element-for-listitem-for-listcontrol-format.md) " 元素指定定义如何显示属性或脚本值的格式模式。</span><span class="sxs-lookup"><span data-stu-id="267cd-215">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="267cd-216">在下面的示例中， `ToString` 调用方法以设置脚本的值的格式。</span><span class="sxs-lookup"><span data-stu-id="267cd-216">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="267cd-217">脚本可以调用对象的任何方法。</span><span class="sxs-lookup"><span data-stu-id="267cd-217">Scripts can call any method of an object.</span></span> <span data-ttu-id="267cd-218">因此，如果对象具有 `ToString` 具有格式参数的方法（如），则脚本可以调用该方法来设置脚本的输出值的格式。</span><span class="sxs-lookup"><span data-stu-id="267cd-218">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="267cd-219">以下 XML 元素可用于调用 `ToString` 方法：</span><span class="sxs-lookup"><span data-stu-id="267cd-219">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="267cd-220">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)元素定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="267cd-220">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="267cd-221">行的每个列都需要一个 [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="267cd-221">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="267cd-222">第一项显示在第一列中，第二项显示在第二列，依此类推。</span><span class="sxs-lookup"><span data-stu-id="267cd-222">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="267cd-223">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)元素指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="267cd-223">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="267cd-224">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="267cd-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="267cd-225">另请参阅</span><span class="sxs-lookup"><span data-stu-id="267cd-225">See Also</span></span>

[<span data-ttu-id="267cd-226">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="267cd-226">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
