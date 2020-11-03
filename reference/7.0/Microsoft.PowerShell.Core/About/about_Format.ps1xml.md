---
description: 从 PowerShell 6 开始，在 PowerShell 源代码中定义对象的默认视图。  你可以创建自己的 `Format.ps1xml` 文件来更改对象的显示，或为你在 PowerShell 中创建的新对象类型定义默认显示。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: ea7a5262be912750b2a4ff6ce72060b31ccdfb8a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200008"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="310ec-105">关于 Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="310ec-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="310ec-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="310ec-106">Short description</span></span>

<span data-ttu-id="310ec-107">从 PowerShell 6 开始，在 PowerShell 源代码中定义对象的默认视图。</span><span class="sxs-lookup"><span data-stu-id="310ec-107">Beginning in PowerShell 6, the default views for objects are defined in PowerShell source code.</span></span>

<span data-ttu-id="310ec-108">你可以创建自己的 `Format.ps1xml` 文件来更改对象的显示，或为你在 PowerShell 中创建的新对象类型定义默认显示。</span><span class="sxs-lookup"><span data-stu-id="310ec-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="310ec-109">长说明</span><span class="sxs-lookup"><span data-stu-id="310ec-109">Long description</span></span>

<span data-ttu-id="310ec-110">从 PowerShell 6 开始，默认视图是在 PowerShell 源代码中定义的。</span><span class="sxs-lookup"><span data-stu-id="310ec-110">Beginning in PowerShell 6, the default views are defined in PowerShell source code.</span></span> <span data-ttu-id="310ec-111">Powershell `Format.ps1xml` 6 及更高版本中不存在 powershell 5.1 及更早版本中的文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-111">The `Format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="310ec-112">PowerShell 源代码定义 PowerShell 控制台中对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="310ec-112">The PowerShell source code defines the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="310ec-113">你可以创建自己的 `Format.ps1xml` 文件来更改对象的显示，或为你在 PowerShell 中创建的新对象类型定义默认显示。</span><span class="sxs-lookup"><span data-stu-id="310ec-113">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="310ec-114">当 PowerShell 显示对象时，它将使用结构化格式设置文件中的数据来确定对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="310ec-114">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="310ec-115">格式设置文件中的数据确定是在表中还是在列表中呈现对象，并确定默认情况下显示哪些属性。</span><span class="sxs-lookup"><span data-stu-id="310ec-115">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="310ec-116">格式设置只影响显示。</span><span class="sxs-lookup"><span data-stu-id="310ec-116">The formatting affects the display only.</span></span> <span data-ttu-id="310ec-117">它不会影响向下传递管道的对象属性或传递方式。</span><span class="sxs-lookup"><span data-stu-id="310ec-117">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="310ec-118">`Format.ps1xml` 文件不能用于自定义哈希表的输出格式。</span><span class="sxs-lookup"><span data-stu-id="310ec-118">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="310ec-119">`.ps1xml`格式设置文件可以为每个对象定义四个不同的视图：</span><span class="sxs-lookup"><span data-stu-id="310ec-119">A `.ps1xml` formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="310ec-120">表</span><span class="sxs-lookup"><span data-stu-id="310ec-120">Table</span></span>
- <span data-ttu-id="310ec-121">列出</span><span class="sxs-lookup"><span data-stu-id="310ec-121">List</span></span>
- <span data-ttu-id="310ec-122">Wide</span><span class="sxs-lookup"><span data-stu-id="310ec-122">Wide</span></span>
- <span data-ttu-id="310ec-123">自定义</span><span class="sxs-lookup"><span data-stu-id="310ec-123">Custom</span></span>

<span data-ttu-id="310ec-124">例如，将命令的输出传递 `Get-ChildItem` 给 `Format-List` 命令时， `Format-List` 使用源代码中定义的列表视图来确定如何将文件和文件夹对象显示为列表。</span><span class="sxs-lookup"><span data-stu-id="310ec-124">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the list view defined in the source code to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="310ec-125">当格式设置文件包含一个对象的多个视图时，PowerShell 将应用找到的第一个视图。</span><span class="sxs-lookup"><span data-stu-id="310ec-125">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="310ec-126">在自定义 `Format.ps1xml` 文件中，视图由一组 XML 标记定义，这些标记描述视图的名称、可应用该视图的对象的类型、列标题和在视图正文中显示的属性。</span><span class="sxs-lookup"><span data-stu-id="310ec-126">In a custom `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="310ec-127">在 `Format.ps1xml` 向用户显示数据之前，将应用文件中的格式。</span><span class="sxs-lookup"><span data-stu-id="310ec-127">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="310ec-128">创建新的 Format.ps1xml 文件</span><span class="sxs-lookup"><span data-stu-id="310ec-128">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="310ec-129">若要更改现有对象视图的显示格式，或添加新对象的视图，请创建自己的 `Format.ps1xml` 文件，然后将其添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="310ec-129">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="310ec-130">若要创建 `Format.ps1xml` 文件以定义自定义视图，请使用 [Update-formatdata](xref:Microsoft.PowerShell.Utility.Get-FormatData) 和 [update-formatdata](xref:Microsoft.PowerShell.Utility.Export-FormatData) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="310ec-130">To create a `Format.ps1xml` file to define a custom view, use the [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) and [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) cmdlets.</span></span> <span data-ttu-id="310ec-131">使用文本编辑器编辑该文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-131">Use a text editor to edit the file.</span></span> <span data-ttu-id="310ec-132">该文件可以保存到 PowerShell 可以访问的任何目录，例如的子目录 `$HOME` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-132">The file can be saved to any directory that PowerShell can access, such as a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="310ec-133">若要更改当前视图的格式，请在格式设置文件中找到该视图，然后使用标记来更改视图。</span><span class="sxs-lookup"><span data-stu-id="310ec-133">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="310ec-134">若要为新的对象类型创建视图，请创建新视图，或使用现有视图作为模型。</span><span class="sxs-lookup"><span data-stu-id="310ec-134">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="310ec-135">下一节将介绍这些标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-135">The tags are described in the next section.</span></span> <span data-ttu-id="310ec-136">然后，你可以删除该文件中的所有其他视图，以使所做的更改对于检查该文件的任何人都很明显。</span><span class="sxs-lookup"><span data-stu-id="310ec-136">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="310ec-137">保存更改后，使用 [update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData) 将新文件添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="310ec-137">After you save the changes, use the [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) to add the new file to your PowerShell session.</span></span> <span data-ttu-id="310ec-138">如果希望视图优先于在内置文件中定义的视图，请使用 **PrependPath** 参数。</span><span class="sxs-lookup"><span data-stu-id="310ec-138">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span> <span data-ttu-id="310ec-139">`Update-FormatData` 仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="310ec-139">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="310ec-140">若要对所有未来会话进行更改，请将 `Update-FormatData` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-140">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-add-calendar-data-to-culture-objects"></a><span data-ttu-id="310ec-141">示例：将日历数据添加到区域性对象</span><span class="sxs-lookup"><span data-stu-id="310ec-141">Example: Add calendar data to culture objects</span></span>

<span data-ttu-id="310ec-142">此示例演示如何更改 **System.Globalization.CultureInfo** `Get-Culture` 当前 PowerShell 会话中由 cmdlet 生成的区域性对象的格式设置。</span><span class="sxs-lookup"><span data-stu-id="310ec-142">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="310ec-143">该示例中的命令将 **日历** 属性添加到区域性对象的默认表视图显示中。</span><span class="sxs-lookup"><span data-stu-id="310ec-143">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="310ec-144">若要开始，请从源代码文件中获取格式数据，并创建 `Format.ps1xml` 包含区域性对象的当前视图的文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-144">To begin, get the format data from the source code file and create a `Format.ps1xml` file that contains the current view of the culture objects.</span></span>

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="310ec-145">`CultureInfo.Format.ps1xml`在任何 XML 或文本编辑器中打开文件，如 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="310ec-145">Open the `CultureInfo.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="310ec-146">下面的 XML 定义 **CultureInfo** 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="310ec-146">The following XML defines the views of the **CultureInfo** object.</span></span>

<span data-ttu-id="310ec-147">该 `CultureInfo.Format.ps1xml` 文件应类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="310ec-147">The `CultureInfo.Format.ps1xml` file should look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
        <TypeName>System.Globalization.CultureInfo</TypeName>
      </ViewSelectedBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader />
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>LCID</PropertyName>
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
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="310ec-148">通过添加一组新的标记为 **Calendar** 属性创建一个新列 `<TableColumnHeader>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-148">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="310ec-149">**Calendar** 属性的值可以很长，因此，请将值指定为45个字符 `<Width>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-149">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

<span data-ttu-id="310ec-150">使用和标记为表行中的 **日历** 添加新的列 `<TableColumnItem>` 项 `<PropertyName` ：</span><span class="sxs-lookup"><span data-stu-id="310ec-150">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

<span data-ttu-id="310ec-151">保存并关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-151">Save and close the file.</span></span> <span data-ttu-id="310ec-152">使用 `Update-FormatData` 将新的格式化文件添加到当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="310ec-152">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="310ec-153">此示例使用 **PrependPath** 参数将新文件的优先顺序高于原始文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-153">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="310ec-154">有关详细信息，请参阅 [update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData)。</span><span class="sxs-lookup"><span data-stu-id="310ec-154">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="310ec-155">若要测试更改，请键入 `Get-Culture` 并检查包含 **Calendar** 属性的输出。</span><span class="sxs-lookup"><span data-stu-id="310ec-155">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="310ec-156">Format.ps1xml 文件中的 XML</span><span class="sxs-lookup"><span data-stu-id="310ec-156">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="310ec-157">在 GitHub 上的 PowerShell 源代码存储库 [中，](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) 可以找到完整的架构定义。</span><span class="sxs-lookup"><span data-stu-id="310ec-157">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="310ec-158">每个文件的 **ViewDefinitions** 部分 `Format.ps1xml` 包含 `<View>` 定义每个视图的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-158">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="310ec-159">典型的 `<View>` 标记包括以下标记：</span><span class="sxs-lookup"><span data-stu-id="310ec-159">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="310ec-160">`<Name>` 标识视图的名称。</span><span class="sxs-lookup"><span data-stu-id="310ec-160">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="310ec-161">`<ViewSelectedBy>` 指定应用视图的对象类型或类型。</span><span class="sxs-lookup"><span data-stu-id="310ec-161">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="310ec-162">`<GroupBy>` 指定如何将视图中的项合并到组中。</span><span class="sxs-lookup"><span data-stu-id="310ec-162">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="310ec-163">`<TableControl>`、 `<ListControl>` 、 `<WideControl>` 和 `<CustomControl>` 包含指定每个项的显示方式的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-163">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="310ec-164">ViewSelectedBy 标记</span><span class="sxs-lookup"><span data-stu-id="310ec-164">ViewSelectedBy tag</span></span>

<span data-ttu-id="310ec-165">`<ViewSelectedBy>`标记可以包含 `<TypeName>` 应用该视图的每个对象类型的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-165">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="310ec-166">或者，它可以包含一个 `<SelectionSetName>` 标记，该标记引用使用标记在其他位置定义的选项集 `<SelectionSet>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-166">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="310ec-167">GroupBy 标记</span><span class="sxs-lookup"><span data-stu-id="310ec-167">GroupBy tag</span></span>

<span data-ttu-id="310ec-168">`<GroupBy>`标记包含一个 `<PropertyName>` 标记，该标记指定要将项分组到的对象属性。</span><span class="sxs-lookup"><span data-stu-id="310ec-168">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="310ec-169">它还包含一个 `<Label>` 标记，该标记为每个组指定一个要用作标签的字符串，或者包含一个标记 `<CustomControlName>` ，该标记用于引用在其他位置使用标记定义的自定义控件 `<Control>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-169">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="310ec-170">`<Control>`标记包含 `<Name>` 标记和 `<CustomControl>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-170">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="310ec-171">TableControlTag</span><span class="sxs-lookup"><span data-stu-id="310ec-171">TableControlTag</span></span>

<span data-ttu-id="310ec-172">`<TableControl>`标记通常包含 `<TableHeaders>` `<TableRowEntries>` 定义表的表头和行的格式的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-172">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="310ec-173">`<TableHeaders>`标记通常包含 `<TableColumnHeader>` 包含 `<Label>` 、 `<Width>` 和标记的标记 `<Alignment>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-173">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="310ec-174">`<TableRowEntries>`标记包含 `<TableRowEntry>` 表中每一行的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-174">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="310ec-175">`<TableRowEntry>`标记包含 `<TableColumnItems>` 标记，该标记包含 `<TableColumnItem>` 行中每个列的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-175">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="310ec-176">通常， `<TableColumnItem>` 标记包含 `<PropertyName>` 标识要在定义的位置中显示的对象属性的标记，或包含用于 `<ScriptBlock>` 计算要在位置中显示的结果的脚本代码的标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-176">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="310ec-177">脚本块还可用于计算结果可能有用的位置中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="310ec-177">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="310ec-178">`<TableColumnItem>`标记还可以包含一个 `<FormatString>` 标记，该标记指定如何显示属性或计算结果。</span><span class="sxs-lookup"><span data-stu-id="310ec-178">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="310ec-179">ListControl 标记</span><span class="sxs-lookup"><span data-stu-id="310ec-179">ListControl tag</span></span>

<span data-ttu-id="310ec-180">`<ListControl>`标记通常包含 `<ListEntries>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-180">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="310ec-181">`<ListEntries>`标记包含 `<ListEntry>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-181">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="310ec-182">`<ListEntry>`标记包含 `<ListItems>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-182">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="310ec-183">`<ListItems>`标记包含标记 `<ListItem>` ，其中包含 `<PropertyName>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-183">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="310ec-184">`<PropertyName>`标记指定要在列表中的指定位置显示的对象属性。</span><span class="sxs-lookup"><span data-stu-id="310ec-184">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="310ec-185">如果使用选择集定义视图选择，则 `<ListControl>` 和 `<ListEntry>` 标记还可以包含 `<EntrySelectedBy>` 一个包含一个或多个标记的标记 `<TypeName>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-185">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="310ec-186">这些 `<TypeName>` 标记指定 `<ListControl>` 用于显示标记的对象类型。</span><span class="sxs-lookup"><span data-stu-id="310ec-186">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="310ec-187">WideControl 标记</span><span class="sxs-lookup"><span data-stu-id="310ec-187">WideControl tag</span></span>

<span data-ttu-id="310ec-188">`<WideControl>`标记通常包含 `<WideEntries>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-188">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="310ec-189">`<WideEntries>`标记包含一个或多个 `<WideEntry>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-189">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="310ec-190">`<WideEntry>`标记通常包含一个 `<PropertyName>` 标记，该标记指定要在视图中的指定位置显示的属性。</span><span class="sxs-lookup"><span data-stu-id="310ec-190">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="310ec-191">`<PropertyName>`标记可以包含一个 `<FormatString>` 标记，该标记指定如何显示属性。</span><span class="sxs-lookup"><span data-stu-id="310ec-191">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="310ec-192">CustomControl 标记</span><span class="sxs-lookup"><span data-stu-id="310ec-192">CustomControl tag</span></span>

<span data-ttu-id="310ec-193">`<CustomControl>`标记允许使用脚本块定义格式。</span><span class="sxs-lookup"><span data-stu-id="310ec-193">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="310ec-194">`<CustomControl>`标记通常包含 `<CustomEntries>` 包含多个标记的标记 `<CustomEntry>` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-194">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="310ec-195">每个 `<CustomEntry>` 标记都包含一个 `<CustomItem>` 标记，该标记可包含用于指定视图中指定位置的内容和格式的各种标记，包括 `<Text>` 、、 `<Indentation>` `<ExpressionBinding>` 和 `<NewLine>` 标记。</span><span class="sxs-lookup"><span data-stu-id="310ec-195">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="310ec-196">跟踪 Format.ps1xml 文件使用</span><span class="sxs-lookup"><span data-stu-id="310ec-196">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="310ec-197">若要检测文件的加载或应用中的错误 `Format.ps1xml` ，请使用 `Trace-Command` cmdlet，并将以下任何格式的组件用作 **Name** 参数的值：</span><span class="sxs-lookup"><span data-stu-id="310ec-197">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="310ec-198">FormatFileLoading</span><span class="sxs-lookup"><span data-stu-id="310ec-198">FormatFileLoading</span></span>
- <span data-ttu-id="310ec-199">FormatViewBinding</span><span class="sxs-lookup"><span data-stu-id="310ec-199">FormatViewBinding</span></span>

<span data-ttu-id="310ec-200">有关详细信息，请参阅 [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) 和 [TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)。</span><span class="sxs-lookup"><span data-stu-id="310ec-200">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="310ec-201">对 Format.ps1xml 文件进行签名</span><span class="sxs-lookup"><span data-stu-id="310ec-201">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="310ec-202">若要保护文件的用户 `Format.ps1xml` ，请使用数字签名对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="310ec-202">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="310ec-203">有关详细信息，请参阅 [about_Signing](about_Signing.md)。</span><span class="sxs-lookup"><span data-stu-id="310ec-203">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="310ec-204">Format-Table 自定义视图的示例 XML</span><span class="sxs-lookup"><span data-stu-id="310ec-204">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="310ec-205">下面的 XML 示例 `Format-Table` 为创建的 **DirectoryInfo** 和 **FileInfo** 对象创建自定义视图 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-205">The following XML sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="310ec-206">自定义视图命名为 **mygciview** ，并将 **CreationTime** 列添加到表中。</span><span class="sxs-lookup"><span data-stu-id="310ec-206">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="310ec-207">若要创建自定义视图，请使用 `Get-FormatData` 和 `Export-FormatData` cmdlet 来生成 `.ps1xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="310ec-207">To create the custom view, use the `Get-FormatData` and `Export-FormatData` cmdlets to generate a `.ps1xml` file.</span></span> <span data-ttu-id="310ec-208">然后，编辑 `.ps1xml` 文件，为自定义视图创建代码。</span><span class="sxs-lookup"><span data-stu-id="310ec-208">Then, edit your `.ps1xml` file to create the code for your custom view.</span></span> <span data-ttu-id="310ec-209">该 `.ps1xml` 文件可存储在 PowerShell 可以访问的任何目录中。</span><span class="sxs-lookup"><span data-stu-id="310ec-209">The `.ps1xml` file can be stored in any directory that PowerShell can access.</span></span> <span data-ttu-id="310ec-210">例如，的子目录 `$HOME` 。</span><span class="sxs-lookup"><span data-stu-id="310ec-210">For example, a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="310ec-211">`.ps1xml`创建文件后，使用 `Update-FormatData` cmdlet 在当前 PowerShell 会话中包含该视图。</span><span class="sxs-lookup"><span data-stu-id="310ec-211">After the `.ps1xml` file is created, use the `Update-FormatData` cmdlet to include the view in the current PowerShell session.</span></span> <span data-ttu-id="310ec-212">或者，如果需要所有 PowerShell 会话中提供的视图，请将更新命令添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="310ec-212">Or, add the update command to your PowerShell profile if you need the view available in all PowerShell sessions.</span></span>

<span data-ttu-id="310ec-213">在此示例中，自定义视图必须使用表格格式，否则将 `Format-Table` 失败。</span><span class="sxs-lookup"><span data-stu-id="310ec-213">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="310ec-214">`Format-Table`与 **View** 参数一起使用，以指定自定义视图的名称、 **Mygciview** ，并使用 **CreationTime** 列设置该表输出的格式。</span><span class="sxs-lookup"><span data-stu-id="310ec-214">Use `Format-Table` with the **View** parameter to specify the custom view's name, **mygciview** , and format the table's output with the **CreationTime** column.</span></span> <span data-ttu-id="310ec-215">有关如何运行该命令的示例，请参阅 [格式表](xref:Microsoft.PowerShell.Utility.Format-Table)。</span><span class="sxs-lookup"><span data-stu-id="310ec-215">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

> [!NOTE]
> <span data-ttu-id="310ec-216">尽管可以从源代码获取格式设置 XML 以创建自定义视图，但可能需要更多的开发才能获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="310ec-216">Although you can get the formatting XML from the source code to create a custom view, more development might be needed to get the desired result.</span></span>

<span data-ttu-id="310ec-217">在下面的 `Get-FormatData` 命令中，可以使用 **PowerShellVersion** 参数的替代方法来确保返回所有本地格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="310ec-217">In the following `Get-FormatData` command, there's an alternative for the **PowerShellVersion** parameter to ensure that all local formatting information is returned.</span></span> <span data-ttu-id="310ec-218">使用 `-PowerShellVersion $PSVersionTable.PSVersion` 而不是特定的 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="310ec-218">Use `-PowerShellVersion $PSVersionTable.PSVersion` rather than a specific PowerShell version.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Length</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Name</PropertyName>
              </TableColumnItem>
            </TableColumnItems>
          </TableRowEntry>
        </TableRowEntries>
      </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="310ec-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="310ec-219">See also</span></span>

[<span data-ttu-id="310ec-220">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="310ec-220">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="310ec-221">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="310ec-221">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="310ec-222">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="310ec-222">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="310ec-223">格式架构 XML 参考</span><span class="sxs-lookup"><span data-stu-id="310ec-223">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="310ec-224">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="310ec-224">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="310ec-225">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="310ec-225">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="310ec-226">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="310ec-226">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
