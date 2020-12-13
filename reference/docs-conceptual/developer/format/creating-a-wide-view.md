---
ms.date: 09/13/2016
ms.topic: reference
title: 创建宽视图
description: 创建宽视图
ms.openlocfilehash: 4230ef91a3612e962b2773b12e8016df6f760eae
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655608"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="ed761-103">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="ed761-103">Creating a Wide View</span></span>

<span data-ttu-id="ed761-104">宽视图为显示的每个对象显示单个值。</span><span class="sxs-lookup"><span data-stu-id="ed761-104">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="ed761-105">显示的值可以是 .NET 对象属性的值或脚本的值。</span><span class="sxs-lookup"><span data-stu-id="ed761-105">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="ed761-106">默认情况下，此视图没有标签或标题。</span><span class="sxs-lookup"><span data-stu-id="ed761-106">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="ed761-107">宽视图显示</span><span class="sxs-lookup"><span data-stu-id="ed761-107">A Wide View Display</span></span>

<span data-ttu-id="ed761-108">下面的示例演示了 Windows PowerShell 如何显示在将其输出传送到[格式范围](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide)cmdlet 时由[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)cmdlet 返回的[system.object](/dotnet/api/System.Diagnostics.Process)对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-108">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="ed761-109"> (默认情况下， [获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet 返回表视图。在此示例中，) 使用这两列显示每个返回对象的进程的名称。</span><span class="sxs-lookup"><span data-stu-id="ed761-109">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="ed761-110">不显示对象属性的名称，只显示属性的值。</span><span class="sxs-lookup"><span data-stu-id="ed761-110">The name of the object's property is not displayed, only the value of the property.</span></span>

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a><span data-ttu-id="ed761-111">定义宽视图</span><span class="sxs-lookup"><span data-stu-id="ed761-111">Defining the Wide View</span></span>

<span data-ttu-id="ed761-112">下面的 XML 显示了 [system.object](/dotnet/api/System.Diagnostics.Process) 对象的宽视图架构。</span><span class="sxs-lookup"><span data-stu-id="ed761-112">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

<span data-ttu-id="ed761-113">以下 XML 元素用于定义宽视图：</span><span class="sxs-lookup"><span data-stu-id="ed761-113">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="ed761-114">[View](./view-element-format.md)元素是宽视图的父元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-114">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="ed761-115"> (此表、列表和自定义控件视图的父元素相同。 ) </span><span class="sxs-lookup"><span data-stu-id="ed761-115">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="ed761-116">[Name](./name-element-for-view-format.md)元素指定视图的名称。</span><span class="sxs-lookup"><span data-stu-id="ed761-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="ed761-117">此元素对于所有视图都是必需的。</span><span class="sxs-lookup"><span data-stu-id="ed761-117">This element is required for all views.</span></span>

- <span data-ttu-id="ed761-118">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义使用视图的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="ed761-119">此元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="ed761-119">This element is required.</span></span>

- <span data-ttu-id="ed761-120">[GroupBy](./groupby-element-for-view-format.md)元素定义何时显示新的对象组。</span><span class="sxs-lookup"><span data-stu-id="ed761-120">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="ed761-121">每当特定属性或脚本的值发生更改时，就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="ed761-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="ed761-122">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-122">This element is optional.</span></span>

- <span data-ttu-id="ed761-123">[Controls](./controls-element-for-view-format.md)元素定义由宽视图定义的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ed761-123">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="ed761-124">控件使您可以进一步指定数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="ed761-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="ed761-125">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-125">This element is optional.</span></span> <span data-ttu-id="ed761-126">视图可以定义自己的自定义控件，也可以使用可由格式设置文件中的任何视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="ed761-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="ed761-127">有关自定义控件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="ed761-128">[WideControl](./widecontrol-element-format.md)元素及其子元素定义视图中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="ed761-128">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="ed761-129">在前面的示例中，视图设计为显示 [Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) 属性。</span><span class="sxs-lookup"><span data-stu-id="ed761-129">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="ed761-130">有关定义简单宽视图的完整格式化文件的示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-130">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="ed761-131">为宽视图提供定义</span><span class="sxs-lookup"><span data-stu-id="ed761-131">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="ed761-132">宽视图可以通过使用 [WideControl](./widecontrol-element-format.md) 元素的子元素来提供一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-132">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="ed761-133">通常，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-133">Typically, a view will have only one definition.</span></span> <span data-ttu-id="ed761-134">在下面的示例中，视图提供了一个显示 [Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) 属性值的定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-134">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="ed761-135">宽视图可以显示属性的值或脚本的值 (不会在示例) 中显示。</span><span class="sxs-lookup"><span data-stu-id="ed761-135">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="ed761-136">以下 XML 元素可用于为宽视图提供定义：</span><span class="sxs-lookup"><span data-stu-id="ed761-136">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="ed761-137">[WideControl](./widecontrol-element-format.md)元素及其子元素定义视图中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="ed761-137">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="ed761-138">[AutoSize](./autosize-element-for-widecontrol-format.md)元素指定是否根据数据大小调整列大小和列数。</span><span class="sxs-lookup"><span data-stu-id="ed761-138">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="ed761-139">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-139">This element is optional.</span></span>

- <span data-ttu-id="ed761-140">[ColumnNumber](./columnnumber-element-for-widecontrol-format.md)元素指定在宽视图中显示的列数。</span><span class="sxs-lookup"><span data-stu-id="ed761-140">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="ed761-141">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-141">This element is optional.</span></span>

- <span data-ttu-id="ed761-142">[WideEntries](./wideentries-element-for-widecontrol-format.md)元素提供视图的定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-142">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="ed761-143">在大多数情况下，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-143">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="ed761-144">此元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="ed761-144">This element is required.</span></span>

- <span data-ttu-id="ed761-145">[WideEntry](./wideentry-element-for-widecontrol-format.md)元素提供视图的定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-145">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="ed761-146">至少需要一个 [WideEntry](./wideentry-element-for-widecontrol-format.md) ;但是，可以添加的元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="ed761-146">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="ed761-147">在大多数情况下，视图将只有一个定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-147">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="ed761-148">[EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)元素指定由特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-148">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="ed761-149">此元素是可选的，仅当定义显示不同对象的多个 [WideEntry](./wideentry-element-for-widecontrol-format.md) 元素时才需要此元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-149">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="ed761-150">[WideItem](./wideitem-element-for-widecontrol-format.md)元素指定视图显示的数据。</span><span class="sxs-lookup"><span data-stu-id="ed761-150">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="ed761-151">与其他类型的视图不同，范围广泛的控件只能显示一项。</span><span class="sxs-lookup"><span data-stu-id="ed761-151">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="ed761-152">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)元素指定其值由视图显示的属性。</span><span class="sxs-lookup"><span data-stu-id="ed761-152">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="ed761-153">您必须指定属性或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-153">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="ed761-154">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)元素指定其值由视图显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="ed761-154">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="ed761-155">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-155">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="ed761-156">" [格式字符串](./formatstring-element-for-wideitem-for-widecontrol-format.md) " 元素指定用于显示数据的模式。</span><span class="sxs-lookup"><span data-stu-id="ed761-156">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="ed761-157">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-157">This element is optional.</span></span>

<span data-ttu-id="ed761-158">有关定义宽视图定义的完整格式化文件的示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-158">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="ed761-159">定义使用大视图的对象</span><span class="sxs-lookup"><span data-stu-id="ed761-159">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="ed761-160">可以通过两种方法来定义哪些 .NET 对象使用宽视图。</span><span class="sxs-lookup"><span data-stu-id="ed761-160">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="ed761-161">您可以使用 [ViewSelectedBy](./viewselectedby-element-format.md) 元素来定义可由视图的所有定义显示的对象，也可以使用 [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) 元素来定义由视图的特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-161">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="ed761-162">在大多数情况下，视图只有一个定义，因此对象通常由 [ViewSelectedBy](./viewselectedby-element-format.md) 元素定义。</span><span class="sxs-lookup"><span data-stu-id="ed761-162">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="ed761-163">下面的示例演示如何使用 [ViewSelectedBy](./viewselectedby-element-format.md) 和 [TypeName](./typename-element-for-viewselectedby-format.md) 元素定义宽视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-163">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="ed761-164">对于您可以指定的 [TypeName](./typename-element-for-viewselectedby-format.md) 元素的数量没有限制，它们的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="ed761-164">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="ed761-165">以下 XML 元素可用于指定宽视图使用的对象：</span><span class="sxs-lookup"><span data-stu-id="ed761-165">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="ed761-166">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义宽视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-166">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="ed761-167">[TypeName](./typename-element-for-viewselectedby-format.md)元素指定视图显示的 .net。</span><span class="sxs-lookup"><span data-stu-id="ed761-167">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="ed761-168">完全限定的 .NET 类型名称是必需的。</span><span class="sxs-lookup"><span data-stu-id="ed761-168">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="ed761-169">您必须为视图指定至少一个类型或选择集，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="ed761-169">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="ed761-170">有关完整格式化文件的示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-170">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="ed761-171">下面的示例使用 [ViewSelectedBy](./viewselectedby-element-format.md) 和 [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-171">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="ed761-172">使用选择集，其中有一组使用多个视图显示的相关对象，例如为同一对象定义宽视图和表视图。</span><span class="sxs-lookup"><span data-stu-id="ed761-172">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="ed761-173">有关如何创建选项集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-173">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="ed761-174">以下 XML 元素可用于指定宽视图使用的对象：</span><span class="sxs-lookup"><span data-stu-id="ed761-174">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="ed761-175">[ViewSelectedBy](./viewselectedby-element-format.md)元素定义宽视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-175">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="ed761-176">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)元素指定可由视图显示的一组对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-176">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="ed761-177">您必须为视图指定至少一个选择集或类型，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="ed761-177">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="ed761-178">下面的示例演示如何使用 [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) 元素定义由宽视图的特定定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-178">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="ed761-179">使用此元素，可以指定对象的 .NET 类型名称、对象的选择集或指定何时使用定义的选择条件。</span><span class="sxs-lookup"><span data-stu-id="ed761-179">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="ed761-180">有关如何创建选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-180">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="ed761-181">以下 XML 元素可用于指定由大视图的特定定义使用的对象：</span><span class="sxs-lookup"><span data-stu-id="ed761-181">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="ed761-182">[EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)元素定义由定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-182">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="ed761-183">[TypeName](./typename-element-for-viewselectedby-format.md)元素指定由定义显示的 .net。</span><span class="sxs-lookup"><span data-stu-id="ed761-183">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="ed761-184">使用此元素时，需要完全限定的 .NET 类型名称。</span><span class="sxs-lookup"><span data-stu-id="ed761-184">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="ed761-185">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="ed761-185">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="ed761-186"> (未显示的 [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 元素) 指定可由此定义显示的一组对象。</span><span class="sxs-lookup"><span data-stu-id="ed761-186">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="ed761-187">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="ed761-187">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="ed761-188"> (未显示的 [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) 元素) 指定要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="ed761-188">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="ed761-189">您必须为定义至少指定一个类型、选择集或选择条件，但没有可指定的最大元素数。</span><span class="sxs-lookup"><span data-stu-id="ed761-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="ed761-190">有关定义选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-190">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="ed761-191">以宽视图显示对象组</span><span class="sxs-lookup"><span data-stu-id="ed761-191">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="ed761-192">您可以将由宽视图显示的对象划分为多个组。</span><span class="sxs-lookup"><span data-stu-id="ed761-192">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="ed761-193">这并不意味着你要定义一个组，只要特定属性或脚本的值发生变化，Windows PowerShell 就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="ed761-193">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="ed761-194">在下面的示例中，只要 [system.serviceprocess](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) 属性的值发生更改，就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="ed761-194">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="ed761-195">以下 XML 元素用于定义组的启动时间：</span><span class="sxs-lookup"><span data-stu-id="ed761-195">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="ed761-196">[GroupBy](./groupby-element-for-view-format.md)元素定义用于启动新组和定义组显示方式的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="ed761-196">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="ed761-197">[PropertyName](./propertyname-element-for-groupby-format.md)元素指定在其值更改时启动新组的属性。</span><span class="sxs-lookup"><span data-stu-id="ed761-197">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="ed761-198">您必须指定一个属性或脚本来启动组，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-198">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="ed761-199">[ScriptBlock](./scriptblock-element-for-groupby-format.md)元素指定在其值更改时启动新组的脚本。</span><span class="sxs-lookup"><span data-stu-id="ed761-199">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="ed761-200">您必须指定脚本或属性以启动组，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-200">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="ed761-201">[标签](./label-element-for-groupby-format.md)元素定义在每个组的开头显示的标签。</span><span class="sxs-lookup"><span data-stu-id="ed761-201">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="ed761-202">除了此元素指定的文本，Windows PowerShell 还显示触发新组的值，并在标签之前和之后添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="ed761-202">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="ed761-203">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-203">This element is optional.</span></span>

- <span data-ttu-id="ed761-204">[CustomControl](./customcontrol-element-for-groupby-format.md)元素定义用于显示数据的控件。</span><span class="sxs-lookup"><span data-stu-id="ed761-204">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="ed761-205">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-205">This element is optional.</span></span>

- <span data-ttu-id="ed761-206">[CustomControlName](./customcontrolname-element-for-groupby-format.md)元素指定用于显示数据的通用控件或视图控件。</span><span class="sxs-lookup"><span data-stu-id="ed761-206">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="ed761-207">此元素为可选元素。</span><span class="sxs-lookup"><span data-stu-id="ed761-207">This element is optional.</span></span>

<span data-ttu-id="ed761-208">有关定义组的完整格式化文件的示例，请参阅 [ (GroupBy) 的宽视图 ](./wide-view-groupby.md)。</span><span class="sxs-lookup"><span data-stu-id="ed761-208">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="ed761-209">使用格式字符串</span><span class="sxs-lookup"><span data-stu-id="ed761-209">Using Format Strings</span></span>

<span data-ttu-id="ed761-210">可以将字符串的格式添加到宽视图，进一步定义数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="ed761-210">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="ed761-211">下面的示例演示如何为属性的值定义格式字符串 `StartTime` 。</span><span class="sxs-lookup"><span data-stu-id="ed761-211">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="ed761-212">以下 XML 元素可用于指定格式模式：</span><span class="sxs-lookup"><span data-stu-id="ed761-212">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="ed761-213">[WideItem](./wideitem-element-for-widecontrol-format.md)元素指定视图显示的数据。</span><span class="sxs-lookup"><span data-stu-id="ed761-213">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="ed761-214">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)元素指定其值由视图显示的属性。</span><span class="sxs-lookup"><span data-stu-id="ed761-214">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="ed761-215">您必须指定属性或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-215">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="ed761-216">"格式 [字符串](./formatstring-element-for-wideitem-for-widecontrol-format.md) " 元素指定定义属性或脚本值在视图中显示方式的格式模式</span><span class="sxs-lookup"><span data-stu-id="ed761-216">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="ed761-217"> (未显示 [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) 元素) 指定视图显示其值的脚本。</span><span class="sxs-lookup"><span data-stu-id="ed761-217">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="ed761-218">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-218">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="ed761-219">在下面的示例中， `ToString` 调用方法以设置脚本的值的格式。</span><span class="sxs-lookup"><span data-stu-id="ed761-219">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="ed761-220">脚本可以调用对象的任何方法。</span><span class="sxs-lookup"><span data-stu-id="ed761-220">Scripts can call any method of an object.</span></span> <span data-ttu-id="ed761-221">因此，如果对象具有 `ToString` 具有格式参数的方法（如），则脚本可以调用该方法来设置脚本的输出值的格式。</span><span class="sxs-lookup"><span data-stu-id="ed761-221">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="ed761-222">以下 XML 元素可用于调用 `ToString` 方法：</span><span class="sxs-lookup"><span data-stu-id="ed761-222">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="ed761-223">[WideItem](./wideitem-element-for-widecontrol-format.md)元素指定视图显示的数据。</span><span class="sxs-lookup"><span data-stu-id="ed761-223">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="ed761-224"> (未显示 [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) 元素) 指定视图显示其值的脚本。</span><span class="sxs-lookup"><span data-stu-id="ed761-224">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="ed761-225">您必须指定脚本或属性，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ed761-225">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed761-226">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed761-226">See Also</span></span>

[<span data-ttu-id="ed761-227">宽视图 (Basic)</span><span class="sxs-lookup"><span data-stu-id="ed761-227">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="ed761-228">宽视图 (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="ed761-228">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="ed761-229">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ed761-229">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
