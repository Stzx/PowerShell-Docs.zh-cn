---
ms.date: 09/13/2016
ms.topic: reference
title: 创建列表视图
description: 创建列表视图
ms.openlocfilehash: c34c4fddc27d4fd016fba37fc465924d693756a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655631"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="554d9-103">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="554d9-103">Creating a List View</span></span>

<span data-ttu-id="554d9-104">列表视图按顺序)  (按顺序显示单个列中的数据。</span><span class="sxs-lookup"><span data-stu-id="554d9-104">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="554d9-105">列表中显示的数据可以是 .NET 属性的值或脚本的值。</span><span class="sxs-lookup"><span data-stu-id="554d9-105">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="554d9-106">列表视图显示</span><span class="sxs-lookup"><span data-stu-id="554d9-106">A List View Display</span></span>

<span data-ttu-id="554d9-107">以下输出显示了 Windows PowerShell 如何显示 [system.serviceprocess. Servicecontroller 的属性？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 由 [get-help](/powershell/module/microsoft.powershell.management/get-service) Cmdlet 返回的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-107">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="554d9-108">在此示例中，返回了三个对象，每个对象都由一个空行与前面的对象隔开。</span><span class="sxs-lookup"><span data-stu-id="554d9-108">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a><span data-ttu-id="554d9-109">定义列表视图</span><span class="sxs-lookup"><span data-stu-id="554d9-109">Defining the List View</span></span>

<span data-ttu-id="554d9-110">下面的 XML 演示了用于显示 [system.serviceprocess. Servicecontroller 的多个属性的列表视图架构。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) 对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-110">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="554d9-111">您必须指定要在列表视图中显示的每个属性。</span><span class="sxs-lookup"><span data-stu-id="554d9-111">You must specify each property that you want displayed in the list view.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

<span data-ttu-id="554d9-112">以下 XML 元素用于定义列表视图：</span><span class="sxs-lookup"><span data-stu-id="554d9-112">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="554d9-113">[View](./view-element-format.md)元素是列表视图的父元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-113">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="554d9-114"> (此表、宽和自定义控件视图的父元素相同。 ) </span><span class="sxs-lookup"><span data-stu-id="554d9-114">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="554d9-115">[Name](./name-element-for-view-format.md)元素指定视图的名称。</span><span class="sxs-lookup"><span data-stu-id="554d9-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="554d9-116">此元素对于所有视图都是必需的。</span><span class="sxs-lookup"><span data-stu-id="554d9-116">This element is required for all views.</span></span>

- <span data-ttu-id="554d9-117">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义使用视图的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="554d9-118">此元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="554d9-118">This element is required.</span></span>

- <span data-ttu-id="554d9-119">[GroupBy](./groupby-element-for-view-format.md)元素定义何时显示新的对象组。</span><span class="sxs-lookup"><span data-stu-id="554d9-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="554d9-120">每当特定属性或脚本的值发生更改时，就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="554d9-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="554d9-121">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-121">This element is optional.</span></span>

- <span data-ttu-id="554d9-122">[Controls](./controls-element-for-view-format.md)元素定义由列表视图定义的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="554d9-122">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="554d9-123">控件使您可以进一步指定数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="554d9-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="554d9-124">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-124">This element is optional.</span></span> <span data-ttu-id="554d9-125">视图可以定义自己的自定义控件，也可以使用可由格式设置文件中的任何视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="554d9-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="554d9-126">有关自定义控件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="554d9-127">[ListControl](./listcontrol-element-format.md)元素定义视图中显示的内容以及如何设置它的格式。</span><span class="sxs-lookup"><span data-stu-id="554d9-127">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="554d9-128">与所有其他视图类似，列表视图可以显示对象属性的值或脚本生成的值。</span><span class="sxs-lookup"><span data-stu-id="554d9-128">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="554d9-129">有关定义简单列表视图的完整格式化文件的示例，请参阅 [列表视图 (基本) ](./list-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-129">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="554d9-130">为列表视图提供定义</span><span class="sxs-lookup"><span data-stu-id="554d9-130">Providing Definitions for Your List View</span></span>

<span data-ttu-id="554d9-131">列表视图可以通过使用 [ListControl](./listcontrol-element-format.md) 元素的子元素来提供一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-131">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="554d9-132">通常，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="554d9-133">在下面的示例中，视图提供了一个定义，用于显示系统的多个属性 [。Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) 对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-133">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="554d9-134">列表视图可以显示属性的值或脚本的值 (未在示例) 中显示。</span><span class="sxs-lookup"><span data-stu-id="554d9-134">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>

```

<span data-ttu-id="554d9-135">以下 XML 元素可用于为列表视图提供定义：</span><span class="sxs-lookup"><span data-stu-id="554d9-135">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="554d9-136">[ListControl](./listcontrol-element-format.md)元素及其子元素定义视图中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="554d9-136">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="554d9-137">[ListEntries](./listentries-element-for-listcontrol-format.md)元素提供视图的定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-137">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="554d9-138">在大多数情况下，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-138">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="554d9-139">此元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="554d9-139">This element is required.</span></span>

- <span data-ttu-id="554d9-140">[ListEntry](./listentry-element-for-listcontrol-format.md)元素提供视图的定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-140">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="554d9-141">至少需要一个 [ListEntry](./listentry-element-for-listcontrol-format.md) ;但是，可以添加的元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="554d9-141">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="554d9-142">在大多数情况下，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-142">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="554d9-143">[EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)元素指定由特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-143">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="554d9-144">此元素是可选的，仅当定义显示不同对象的多个 [ListEntry](./listentry-element-for-listcontrol-format.md) 元素时才需要此元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-144">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="554d9-145">[ListItems](./listitems-element-for-listentry-for-listcontrol-format.md)元素指定其值显示在列表视图的行中的属性和脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-145">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="554d9-146">" [列表](./listitems-element-for-listentry-for-listcontrol-format.md) 元素" 指定其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-146">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="554d9-147">列表视图必须至少指定一个属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-147">A list view must specify at least one property or script.</span></span> <span data-ttu-id="554d9-148">对于可以指定的行数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="554d9-148">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="554d9-149">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)元素指定其值显示在行中的属性。</span><span class="sxs-lookup"><span data-stu-id="554d9-149">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="554d9-150">您必须指定属性或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-150">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="554d9-151">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)元素指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-151">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="554d9-152">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-152">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="554d9-153">[Label](./label-element-for-listitem-for-listcontrol-format.md)元素指定在行中的属性或脚本值左侧显示的标签。</span><span class="sxs-lookup"><span data-stu-id="554d9-153">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="554d9-154">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-154">This element is optional.</span></span> <span data-ttu-id="554d9-155">如果未指定标签，则显示属性或脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="554d9-155">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="554d9-156">有关完整示例，请参阅 [列表视图 (标签) ](./list-view-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-156">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="554d9-157">[ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)元素指定要显示的行必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="554d9-157">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="554d9-158">有关向列表视图添加条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-158">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="554d9-159">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-159">This element is optional.</span></span>

- <span data-ttu-id="554d9-160">[格式字符串](./formatstring-element-for-listitem-for-listcontrol-format.md)元素指定用于显示属性或脚本的值的模式。</span><span class="sxs-lookup"><span data-stu-id="554d9-160">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="554d9-161">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-161">This element is optional.</span></span>

<span data-ttu-id="554d9-162">有关定义简单列表视图的完整格式化文件的示例，请参阅 [列表视图 (基本) ](./list-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-162">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="554d9-163">定义使用列表视图的对象</span><span class="sxs-lookup"><span data-stu-id="554d9-163">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="554d9-164">可以通过两种方法来定义哪些 .NET 对象使用列表视图。</span><span class="sxs-lookup"><span data-stu-id="554d9-164">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="554d9-165">您可以使用 [ViewSelectedBy](./viewselectedby-element-format.md) 元素来定义可由视图的所有定义显示的对象，也可以使用 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) 元素来定义由视图的特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-165">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="554d9-166">在大多数情况下，视图只有一个定义，因此对象通常由 [ViewSelectedBy](./viewselectedby-element-format.md) 元素定义。</span><span class="sxs-lookup"><span data-stu-id="554d9-166">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="554d9-167">下面的示例演示如何使用 [ViewSelectedBy](./viewselectedby-element-format.md) 和 [TypeName](./typename-element-for-viewselectedby-format.md) 元素定义列表视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-167">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="554d9-168">对于您可以指定的 [TypeName](./typename-element-for-viewselectedby-format.md) 元素的数量没有限制，它们的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="554d9-168">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="554d9-169">以下 XML 元素可用于指定列表视图所使用的对象：</span><span class="sxs-lookup"><span data-stu-id="554d9-169">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="554d9-170">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义列表视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-170">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="554d9-171">[TypeName](./typename-element-for-viewselectedby-format.md)元素指定视图显示的 .net 对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-171">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="554d9-172">完全限定的 .NET 类型名称是必需的。</span><span class="sxs-lookup"><span data-stu-id="554d9-172">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="554d9-173">您必须为视图指定至少一个类型或选择集，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="554d9-173">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="554d9-174">有关完整格式化文件的示例，请参阅 [列表视图 (基本) ](./list-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-174">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="554d9-175">下面的示例使用 [ViewSelectedBy](./viewselectedby-element-format.md) 和 [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-175">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="554d9-176">使用选择集，其中有一组使用多个视图显示的相关对象，例如为同一对象定义列表视图和表视图。</span><span class="sxs-lookup"><span data-stu-id="554d9-176">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="554d9-177">有关如何创建选项集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-177">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="554d9-178">以下 XML 元素可用于指定列表视图所使用的对象：</span><span class="sxs-lookup"><span data-stu-id="554d9-178">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="554d9-179">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义列表视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-179">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="554d9-180">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)元素指定可由视图显示的一组对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-180">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="554d9-181">您必须为视图指定至少一个选择集或类型，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="554d9-181">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="554d9-182">下面的示例演示如何使用 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) 元素定义由列表视图的特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-182">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="554d9-183">使用此元素，可以指定对象的 .NET 类型名称、对象的选择集或指定何时使用定义的选择条件。</span><span class="sxs-lookup"><span data-stu-id="554d9-183">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="554d9-184">有关如何创建选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-184">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="554d9-185">以下 XML 元素可用于指定列表视图的特定定义所使用的对象：</span><span class="sxs-lookup"><span data-stu-id="554d9-185">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="554d9-186">[EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)元素定义由定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-186">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="554d9-187">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)元素指定由定义显示的 .net 对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-187">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="554d9-188">使用此元素时，必须提供完全限定的 .NET 类型名称。</span><span class="sxs-lookup"><span data-stu-id="554d9-188">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="554d9-189">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="554d9-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="554d9-190"> (未显示的 [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) 元素) 指定可由此定义显示的一组对象。</span><span class="sxs-lookup"><span data-stu-id="554d9-190">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="554d9-191">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="554d9-191">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="554d9-192"> (未显示的 [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) 元素) 指定要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="554d9-192">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="554d9-193">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="554d9-193">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="554d9-194">有关定义选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-194">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="554d9-195">在列表视图中显示对象组</span><span class="sxs-lookup"><span data-stu-id="554d9-195">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="554d9-196">可以将列表视图显示的对象划分为多个组。</span><span class="sxs-lookup"><span data-stu-id="554d9-196">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="554d9-197">这并不意味着你要定义一个组，只要特定属性或脚本的值发生变化，Windows PowerShell 就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="554d9-197">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="554d9-198">在下面的示例中，只要 [system.serviceprocess](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) 属性的值发生更改，就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="554d9-198">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="554d9-199">以下 XML 元素用于定义组的启动时间：</span><span class="sxs-lookup"><span data-stu-id="554d9-199">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="554d9-200">[GroupBy](./groupby-element-for-view-format.md)元素定义用于启动新组和定义组显示方式的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-200">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="554d9-201">[PropertyName](./propertyname-element-for-groupby-format.md)元素指定在其值更改时启动新组的属性。</span><span class="sxs-lookup"><span data-stu-id="554d9-201">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="554d9-202">您必须指定一个属性或脚本来启动组，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-202">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="554d9-203">[ScriptBlock](./scriptblock-element-for-groupby-format.md)元素指定在其值更改时启动新组的脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-203">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="554d9-204">您必须指定脚本或属性以启动组，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-204">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="554d9-205">[标签](./label-element-for-groupby-format.md)元素定义在每个组的开头显示的标签。</span><span class="sxs-lookup"><span data-stu-id="554d9-205">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="554d9-206">除了此元素指定的文本，Windows PowerShell 还显示触发新组的值，并在标签之前和之后添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="554d9-206">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="554d9-207">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-207">This element is optional.</span></span>

- <span data-ttu-id="554d9-208">[CustomControl](./customcontrol-element-for-groupby-format.md)元素定义用于显示数据的控件。</span><span class="sxs-lookup"><span data-stu-id="554d9-208">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="554d9-209">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-209">This element is optional.</span></span>

- <span data-ttu-id="554d9-210">[CustomControlName](./customcontrolname-element-for-groupby-format.md)元素指定用于显示数据的通用控件或视图控件。</span><span class="sxs-lookup"><span data-stu-id="554d9-210">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="554d9-211">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="554d9-211">This element is optional.</span></span>

<span data-ttu-id="554d9-212">有关定义组的完整格式化文件的示例，请参阅 [列表视图 (GroupBy) ](./list-view-groupby.md)。</span><span class="sxs-lookup"><span data-stu-id="554d9-212">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="554d9-213">使用格式字符串</span><span class="sxs-lookup"><span data-stu-id="554d9-213">Using Format Strings</span></span>

<span data-ttu-id="554d9-214">可以将字符串的格式添加到视图中，以便进一步定义数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="554d9-214">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="554d9-215">下面的示例演示如何为属性的值定义格式字符串 `StartTime` 。</span><span class="sxs-lookup"><span data-stu-id="554d9-215">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="554d9-216">以下 XML 元素可用于指定格式模式：</span><span class="sxs-lookup"><span data-stu-id="554d9-216">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="554d9-217">" [出现](./listitem-element-for-listitems-for-listcontrol-format.md) 类型" 元素指定视图显示的数据。</span><span class="sxs-lookup"><span data-stu-id="554d9-217">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="554d9-218">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)元素指定其值由视图显示的属性。</span><span class="sxs-lookup"><span data-stu-id="554d9-218">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="554d9-219">您必须指定属性或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-219">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="554d9-220">"格式 [字符串](./formatstring-element-for-listitem-for-listcontrol-format.md) " 元素指定定义属性或脚本值在视图中显示方式的格式模式。</span><span class="sxs-lookup"><span data-stu-id="554d9-220">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="554d9-221"> (未显示 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) 元素) 指定视图显示其值的脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-221">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="554d9-222">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-222">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="554d9-223">在下面的示例中， `ToString` 调用方法以设置脚本的值的格式。</span><span class="sxs-lookup"><span data-stu-id="554d9-223">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="554d9-224">脚本可以调用对象的任何方法。</span><span class="sxs-lookup"><span data-stu-id="554d9-224">Scripts can call any method of an object.</span></span> <span data-ttu-id="554d9-225">因此，如果对象具有 `ToString` 具有格式参数的方法（如），则脚本可以调用该方法来设置脚本的输出值的格式。</span><span class="sxs-lookup"><span data-stu-id="554d9-225">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="554d9-226">以下 XML 元素可用于调用 `ToString` 方法：</span><span class="sxs-lookup"><span data-stu-id="554d9-226">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="554d9-227">" [出现](./listitem-element-for-listitems-for-listcontrol-format.md) 类型" 元素指定视图显示的数据。</span><span class="sxs-lookup"><span data-stu-id="554d9-227">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="554d9-228"> (未显示 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) 元素) 指定视图显示其值的脚本。</span><span class="sxs-lookup"><span data-stu-id="554d9-228">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="554d9-229">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="554d9-229">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="554d9-230">另请参阅</span><span class="sxs-lookup"><span data-stu-id="554d9-230">See Also</span></span>

[<span data-ttu-id="554d9-231">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="554d9-231">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)
