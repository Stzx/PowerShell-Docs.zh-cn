---
description: '`Format.ps1xml`Powershell 中的文件在 powershell 控制台中定义对象的默认显示。 你可以创建自己的 `Format.ps1xml` 文件来更改对象的显示，或为你在 PowerShell 中创建的新对象类型定义默认显示。'
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200120"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="71367-105">关于 Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="71367-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="71367-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="71367-106">Short description</span></span>

<span data-ttu-id="71367-107">`Format.ps1xml`Powershell 中的文件在 powershell 控制台中定义对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="71367-107">The `Format.ps1xml` files in PowerShell define the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="71367-108">你可以创建自己的 `Format.ps1xml` 文件来更改对象的显示，或为你在 PowerShell 中创建的新对象类型定义默认显示。</span><span class="sxs-lookup"><span data-stu-id="71367-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="71367-109">长说明</span><span class="sxs-lookup"><span data-stu-id="71367-109">Long description</span></span>

<span data-ttu-id="71367-110">`Format.ps1xml`Powershell 中的文件在 powershell 中定义对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="71367-110">The `Format.ps1xml` files in PowerShell define the default display of objects in PowerShell.</span></span> <span data-ttu-id="71367-111">你可以创建自己的 `Format.ps1xml` 文件来更改对象的显示，或为你在 PowerShell 中创建的新对象类型定义默认显示。</span><span class="sxs-lookup"><span data-stu-id="71367-111">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="71367-112">当 PowerShell 显示对象时，它将使用结构化格式设置文件中的数据来确定对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="71367-112">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="71367-113">格式设置文件中的数据确定是在表中还是在列表中呈现对象，并确定默认情况下显示哪些属性。</span><span class="sxs-lookup"><span data-stu-id="71367-113">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="71367-114">格式设置只影响显示。</span><span class="sxs-lookup"><span data-stu-id="71367-114">The formatting affects the display only.</span></span> <span data-ttu-id="71367-115">它不会影响向下传递管道的对象属性或传递方式。</span><span class="sxs-lookup"><span data-stu-id="71367-115">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="71367-116">`Format.ps1xml` 文件不能用于自定义哈希表的输出格式。</span><span class="sxs-lookup"><span data-stu-id="71367-116">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="71367-117">PowerShell 包括七个格式化文件。</span><span class="sxs-lookup"><span data-stu-id="71367-117">PowerShell includes seven formatting files.</span></span> <span data-ttu-id="71367-118">这些文件位于 () 的安装目录中 `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="71367-118">These files are located in the installation directory (`$PSHOME`).</span></span> <span data-ttu-id="71367-119">每个文件定义一组 Microsoft .NET 框架对象的显示：</span><span class="sxs-lookup"><span data-stu-id="71367-119">Each file defines the display of a group of Microsoft .NET Framework objects:</span></span>

1. `Certificate.Format.ps1xml`

   <span data-ttu-id="71367-120">证书存储区中的对象，例如 x.509 证书和证书存储。</span><span class="sxs-lookup"><span data-stu-id="71367-120">Objects in the Certificate store, such as X.509 certificates and certificate stores.</span></span>

1. `DotNetTypes.Format.ps1xml`

   <span data-ttu-id="71367-121">其他 .NET Framework 类型，如 CultureInfo、FileVersionInfo 和 EventLogEntry 对象。</span><span class="sxs-lookup"><span data-stu-id="71367-121">Other .NET Framework types, such as CultureInfo, FileVersionInfo, and EventLogEntry objects.</span></span>

1. `FileSystem.Format.ps1xml`

   <span data-ttu-id="71367-122">文件系统对象，如文件和目录。</span><span class="sxs-lookup"><span data-stu-id="71367-122">File system objects, such as files and directories.</span></span>

1. `Help.Format.ps1xml`

   <span data-ttu-id="71367-123">帮助视图，例如详细视图和完整视图、参数和示例。</span><span class="sxs-lookup"><span data-stu-id="71367-123">Help views, such as detailed and full views, parameters, and examples.</span></span>

1. `PowerShellCore.Format.ps1xml`

   <span data-ttu-id="71367-124">PowerShell 核心 cmdlet 生成的对象，例如 `Get-Member` 和 `Get-History` 。</span><span class="sxs-lookup"><span data-stu-id="71367-124">Objects generated by PowerShell core cmdlets, such as `Get-Member` and `Get-History`.</span></span>

1. `PowerShellTrace.Format.ps1xml`

   <span data-ttu-id="71367-125">跟踪对象，例如由 cmdlet 生成的对象 `Trace-Command` 。</span><span class="sxs-lookup"><span data-stu-id="71367-125">Trace objects, such as those generated by the `Trace-Command` cmdlet.</span></span>

1. `Registry.Format.ps1xml`

   <span data-ttu-id="71367-126">注册表对象，如项和项。</span><span class="sxs-lookup"><span data-stu-id="71367-126">Registry objects, such as keys and entries.</span></span>

<span data-ttu-id="71367-127">格式设置文件可以为每个对象定义四个不同的视图：</span><span class="sxs-lookup"><span data-stu-id="71367-127">A formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="71367-128">表</span><span class="sxs-lookup"><span data-stu-id="71367-128">Table</span></span>
- <span data-ttu-id="71367-129">列出</span><span class="sxs-lookup"><span data-stu-id="71367-129">List</span></span>
- <span data-ttu-id="71367-130">Wide</span><span class="sxs-lookup"><span data-stu-id="71367-130">Wide</span></span>
- <span data-ttu-id="71367-131">自定义</span><span class="sxs-lookup"><span data-stu-id="71367-131">Custom</span></span>

<span data-ttu-id="71367-132">例如，将命令的输出传递 `Get-ChildItem` 给 `Format-List` 命令时，将 `Format-List` 使用文件中的视图 `FileSystem.Format.ps1xml` 来确定如何将文件和文件夹对象显示为列表。</span><span class="sxs-lookup"><span data-stu-id="71367-132">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the view in the `FileSystem.Format.ps1xml` file to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="71367-133">当格式设置文件包含一个对象的多个视图时，PowerShell 将应用找到的第一个视图。</span><span class="sxs-lookup"><span data-stu-id="71367-133">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="71367-134">在 `Format.ps1xml` 文件中，视图由一组 XML 标记定义，这些标记描述视图的名称、可应用该视图的对象的类型、列标题和在视图正文中显示的属性。</span><span class="sxs-lookup"><span data-stu-id="71367-134">In a `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="71367-135">在 `Format.ps1xml` 向用户显示数据之前，将应用文件中的格式。</span><span class="sxs-lookup"><span data-stu-id="71367-135">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="71367-136">创建新的 Format.ps1xml 文件</span><span class="sxs-lookup"><span data-stu-id="71367-136">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="71367-137">`.ps1xml`随 PowerShell 一起安装的文件已进行数字签名，以防止篡改，因为格式设置可以包括脚本块。</span><span class="sxs-lookup"><span data-stu-id="71367-137">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="71367-138">若要更改现有对象视图的显示格式，或添加新对象的视图，请创建自己的 `Format.ps1xml` 文件，然后将其添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="71367-138">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="71367-139">若要创建新文件，请复制现有 `Format.ps1xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="71367-139">To create a new file, copy an existing `Format.ps1xml` file.</span></span> <span data-ttu-id="71367-140">新文件可以具有任何名称，但它必须具有 `.ps1xml` 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="71367-140">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="71367-141">可以将新文件放在 PowerShell 可访问的任何目录中，但将文件放在 PowerShell 安装目录中 (`$PSHOME`) 或安装目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="71367-141">You can place the new file in any directory that is accessible to PowerShell, but it's useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="71367-142">若要更改当前视图的格式，请在格式设置文件中找到该视图，然后使用标记来更改视图。</span><span class="sxs-lookup"><span data-stu-id="71367-142">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="71367-143">若要为新的对象类型创建视图，请创建新视图，或使用现有视图作为模型。</span><span class="sxs-lookup"><span data-stu-id="71367-143">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="71367-144">下一节将介绍这些标记。</span><span class="sxs-lookup"><span data-stu-id="71367-144">The tags are described in the next section.</span></span> <span data-ttu-id="71367-145">然后，你可以删除该文件中的所有其他视图，以使所做的更改对于检查该文件的任何人都很明显。</span><span class="sxs-lookup"><span data-stu-id="71367-145">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="71367-146">保存更改后，使用 `Update-FormatData` cmdlet 将新文件添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="71367-146">After you save the changes, use the `Update-FormatData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="71367-147">如果希望视图优先于在内置文件中定义的视图，请使用 **PrependPath** 参数。</span><span class="sxs-lookup"><span data-stu-id="71367-147">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span>
<span data-ttu-id="71367-148">`Update-FormatData` 仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="71367-148">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="71367-149">若要对所有未来会话进行更改，请将 `Update-FormatData` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="71367-149">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-adding-calendar-data-to-culture-objects"></a><span data-ttu-id="71367-150">示例：将日历数据添加到区域性对象</span><span class="sxs-lookup"><span data-stu-id="71367-150">Example: Adding calendar data to culture objects</span></span>

<span data-ttu-id="71367-151">此示例演示如何更改 **System.Globalization.CultureInfo** `Get-Culture` 当前 PowerShell 会话中由 cmdlet 生成的区域性对象的格式设置。</span><span class="sxs-lookup"><span data-stu-id="71367-151">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="71367-152">该示例中的命令将 **日历** 属性添加到区域性对象的默认表视图显示中。</span><span class="sxs-lookup"><span data-stu-id="71367-152">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="71367-153">第一步是查找 `Format.ps1xml` 包含区域性对象的当前视图的文件。</span><span class="sxs-lookup"><span data-stu-id="71367-153">The first step is to find the `Format.ps1xml` file that contains the current view of the culture objects.</span></span> <span data-ttu-id="71367-154">以下 `Select-String` 命令将查找文件：</span><span class="sxs-lookup"><span data-stu-id="71367-154">The following `Select-String` command finds the file:</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

<span data-ttu-id="71367-155">此命令显示文件中的定义 `DotNetTypes.Format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="71367-155">This command reveals that the definition is in the `DotNetTypes.Format.ps1xml` file.</span></span>

<span data-ttu-id="71367-156">下一条命令将文件内容复制到新文件中 `MyDotNetTypes.Format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="71367-156">The next command copies the file contents to a new file, `MyDotNetTypes.Format.ps1xml`.</span></span>

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="71367-157">`MyDotNetTypes.Format.ps1xml`在任何 XML 或文本编辑器中打开文件，如 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="71367-157">Open the `MyDotNetTypes.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="71367-158">找到 **system.object** 对象部分。</span><span class="sxs-lookup"><span data-stu-id="71367-158">Find the **System.Globalization.CultureInfo** object section.</span></span> <span data-ttu-id="71367-159">下面的 XML 定义 **CultureInfo** 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="71367-159">The following XML defines the views of the **CultureInfo** object.</span></span> <span data-ttu-id="71367-160">对象只包含 **TableControl** 视图。</span><span class="sxs-lookup"><span data-stu-id="71367-160">The object has only a **TableControl** view.</span></span>

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
```

<span data-ttu-id="71367-161">删除文件的剩余部分，除了打开 `<?xml>` 、 `<Configuration>` 和 `<ViewDefinitions>` 标记以及结束 `<ViewDefinitions>` `<Configuration>` 标记和标记。</span><span class="sxs-lookup"><span data-stu-id="71367-161">Delete the remainder of the file, except for the opening `<?xml>`, `<Configuration>`, and `<ViewDefinitions>` tags and the closing `<ViewDefinitions>` and `<Configuration>` tags.</span></span> <span data-ttu-id="71367-162">如果有数字签名，请从自定义文件中将其删除 `Format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="71367-162">If there is a digital signature, delete it from your custom `Format.ps1xml`file.</span></span>

<span data-ttu-id="71367-163">该 `MyDotNetTypes.Format.ps1xml` 文件现在应类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="71367-163">The `MyDotNetTypes.Format.ps1xml` file should now look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
      <TableColumnHeader/>
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

<span data-ttu-id="71367-164">通过添加一组新的标记为 **Calendar** 属性创建一个新列 `<TableColumnHeader>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-164">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="71367-165">**Calendar** 属性的值可以很长，因此，请将值指定为45个字符 `<Width>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-165">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

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

<span data-ttu-id="71367-166">使用和标记为表行中的 **日历** 添加新的列 `<TableColumnItem>` 项 `<PropertyName` ：</span><span class="sxs-lookup"><span data-stu-id="71367-166">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

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

<span data-ttu-id="71367-167">保存并关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="71367-167">Save and close the file.</span></span> <span data-ttu-id="71367-168">使用 `Update-FormatData` 将新的格式化文件添加到当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="71367-168">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="71367-169">此示例使用 **PrependPath** 参数将新文件的优先顺序高于原始文件。</span><span class="sxs-lookup"><span data-stu-id="71367-169">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="71367-170">有关详细信息，请参阅 [update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData)。</span><span class="sxs-lookup"><span data-stu-id="71367-170">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="71367-171">若要测试更改，请键入 `Get-Culture` 并检查包含 **Calendar** 属性的输出。</span><span class="sxs-lookup"><span data-stu-id="71367-171">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="71367-172">Format.ps1xml 文件中的 XML</span><span class="sxs-lookup"><span data-stu-id="71367-172">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="71367-173">在 GitHub 上的 PowerShell 源代码存储库 [中，](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) 可以找到完整的架构定义。</span><span class="sxs-lookup"><span data-stu-id="71367-173">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="71367-174">每个文件的 **ViewDefinitions** 部分 `Format.ps1xml` 包含 `<View>` 定义每个视图的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-174">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="71367-175">典型的 `<View>` 标记包括以下标记：</span><span class="sxs-lookup"><span data-stu-id="71367-175">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="71367-176">`<Name>` 标识视图的名称。</span><span class="sxs-lookup"><span data-stu-id="71367-176">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="71367-177">`<ViewSelectedBy>` 指定应用视图的对象类型或类型。</span><span class="sxs-lookup"><span data-stu-id="71367-177">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="71367-178">`<GroupBy>` 指定如何将视图中的项合并到组中。</span><span class="sxs-lookup"><span data-stu-id="71367-178">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="71367-179">`<TableControl>`、 `<ListControl>` 、 `<WideControl>` 和 `<CustomControl>` 包含指定每个项的显示方式的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-179">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="71367-180">ViewSelectedBy 标记</span><span class="sxs-lookup"><span data-stu-id="71367-180">ViewSelectedBy tag</span></span>

<span data-ttu-id="71367-181">`<ViewSelectedBy>`标记可以包含 `<TypeName>` 应用该视图的每个对象类型的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-181">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="71367-182">或者，它可以包含一个 `<SelectionSetName>` 标记，该标记引用使用标记在其他位置定义的选项集 `<SelectionSet>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-182">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="71367-183">GroupBy 标记</span><span class="sxs-lookup"><span data-stu-id="71367-183">GroupBy tag</span></span>

<span data-ttu-id="71367-184">`<GroupBy>`标记包含一个 `<PropertyName>` 标记，该标记指定要将项分组到的对象属性。</span><span class="sxs-lookup"><span data-stu-id="71367-184">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="71367-185">它还包含一个 `<Label>` 标记，该标记为每个组指定一个要用作标签的字符串，或者包含一个标记 `<CustomControlName>` ，该标记用于引用在其他位置使用标记定义的自定义控件 `<Control>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-185">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="71367-186">`<Control>`标记包含 `<Name>` 标记和 `<CustomControl>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-186">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="71367-187">TableControlTag</span><span class="sxs-lookup"><span data-stu-id="71367-187">TableControlTag</span></span>

<span data-ttu-id="71367-188">`<TableControl>`标记通常包含 `<TableHeaders>` `<TableRowEntries>` 定义表的表头和行的格式的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-188">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="71367-189">`<TableHeaders>`标记通常包含 `<TableColumnHeader>` 包含 `<Label>` 、 `<Width>` 和标记的标记 `<Alignment>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-189">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="71367-190">`<TableRowEntries>`标记包含 `<TableRowEntry>` 表中每一行的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-190">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="71367-191">`<TableRowEntry>`标记包含 `<TableColumnItems>` 标记，该标记包含 `<TableColumnItem>` 行中每个列的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-191">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="71367-192">通常， `<TableColumnItem>` 标记包含 `<PropertyName>` 标识要在定义的位置中显示的对象属性的标记，或包含用于 `<ScriptBlock>` 计算要在位置中显示的结果的脚本代码的标记。</span><span class="sxs-lookup"><span data-stu-id="71367-192">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="71367-193">脚本块还可用于计算结果可能有用的位置中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="71367-193">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="71367-194">`<TableColumnItem>`标记还可以包含一个 `<FormatString>` 标记，该标记指定如何显示属性或计算结果。</span><span class="sxs-lookup"><span data-stu-id="71367-194">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="71367-195">ListControl 标记</span><span class="sxs-lookup"><span data-stu-id="71367-195">ListControl tag</span></span>

<span data-ttu-id="71367-196">`<ListControl>`标记通常包含 `<ListEntries>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-196">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="71367-197">`<ListEntries>`标记包含 `<ListEntry>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-197">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="71367-198">`<ListEntry>`标记包含 `<ListItems>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-198">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="71367-199">`<ListItems>`标记包含标记 `<ListItem>` ，其中包含 `<PropertyName>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-199">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="71367-200">`<PropertyName>`标记指定要在列表中的指定位置显示的对象属性。</span><span class="sxs-lookup"><span data-stu-id="71367-200">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="71367-201">如果使用选择集定义视图选择，则 `<ListControl>` 和 `<ListEntry>` 标记还可以包含 `<EntrySelectedBy>` 一个包含一个或多个标记的标记 `<TypeName>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-201">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="71367-202">这些 `<TypeName>` 标记指定 `<ListControl>` 用于显示标记的对象类型。</span><span class="sxs-lookup"><span data-stu-id="71367-202">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="71367-203">WideControl 标记</span><span class="sxs-lookup"><span data-stu-id="71367-203">WideControl tag</span></span>

<span data-ttu-id="71367-204">`<WideControl>`标记通常包含 `<WideEntries>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-204">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="71367-205">`<WideEntries>`标记包含一个或多个 `<WideEntry>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-205">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="71367-206">`<WideEntry>`标记通常包含一个 `<PropertyName>` 标记，该标记指定要在视图中的指定位置显示的属性。</span><span class="sxs-lookup"><span data-stu-id="71367-206">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="71367-207">`<PropertyName>`标记可以包含一个 `<FormatString>` 标记，该标记指定如何显示属性。</span><span class="sxs-lookup"><span data-stu-id="71367-207">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="71367-208">CustomControl 标记</span><span class="sxs-lookup"><span data-stu-id="71367-208">CustomControl tag</span></span>

<span data-ttu-id="71367-209">`<CustomControl>`标记允许使用脚本块定义格式。</span><span class="sxs-lookup"><span data-stu-id="71367-209">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="71367-210">`<CustomControl>`标记通常包含 `<CustomEntries>` 包含多个标记的标记 `<CustomEntry>` 。</span><span class="sxs-lookup"><span data-stu-id="71367-210">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="71367-211">每个 `<CustomEntry>` 标记都包含一个 `<CustomItem>` 标记，该标记可包含用于指定视图中指定位置的内容和格式的各种标记，包括 `<Text>` 、、 `<Indentation>` `<ExpressionBinding>` 和 `<NewLine>` 标记。</span><span class="sxs-lookup"><span data-stu-id="71367-211">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="default-displays-in-typesps1xml"></a><span data-ttu-id="71367-212">Types.ps1xml 中显示默认值</span><span class="sxs-lookup"><span data-stu-id="71367-212">Default displays in Types.ps1xml</span></span>

<span data-ttu-id="71367-213">某些基本对象类型的默认显示是在 `Types.ps1xml` 目录的文件中定义的 `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="71367-213">The default displays of some basic object types are defined in the `Types.ps1xml` file in the `$PSHOME` directory.</span></span> <span data-ttu-id="71367-214">节点名为 **PsStandardMembers** ，子节点使用以下标记之一：</span><span class="sxs-lookup"><span data-stu-id="71367-214">The nodes are named **PsStandardMembers** , and the subnodes use one of the following tags:</span></span>

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

<span data-ttu-id="71367-215">有关详细信息，请参阅 [about_Types.ps1xml](about_Types.ps1xml.md)。</span><span class="sxs-lookup"><span data-stu-id="71367-215">For more information, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="71367-216">跟踪 Format.ps1xml 文件使用</span><span class="sxs-lookup"><span data-stu-id="71367-216">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="71367-217">若要检测文件的加载或应用中的错误 `Format.ps1xml` ，请使用 `Trace-Command` cmdlet，并将以下任何格式的组件用作 **Name** 参数的值：</span><span class="sxs-lookup"><span data-stu-id="71367-217">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="71367-218">FormatFileLoading</span><span class="sxs-lookup"><span data-stu-id="71367-218">FormatFileLoading</span></span>
- <span data-ttu-id="71367-219">FormatViewBinding</span><span class="sxs-lookup"><span data-stu-id="71367-219">FormatViewBinding</span></span>

<span data-ttu-id="71367-220">有关详细信息，请参阅 [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) 和 [TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)。</span><span class="sxs-lookup"><span data-stu-id="71367-220">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="71367-221">对 Format.ps1xml 文件进行签名</span><span class="sxs-lookup"><span data-stu-id="71367-221">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="71367-222">若要保护文件的用户 `Format.ps1xml` ，请使用数字签名对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="71367-222">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="71367-223">有关详细信息，请参阅 [about_Signing](about_Signing.md)。</span><span class="sxs-lookup"><span data-stu-id="71367-223">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="71367-224">Format-Table 自定义视图的示例 XML</span><span class="sxs-lookup"><span data-stu-id="71367-224">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="71367-225">下面的示例 `Format-Table` 为创建的 **DirectoryInfo** 和 **FileInfo** 对象创建自定义视图 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="71367-225">The following sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="71367-226">自定义视图命名为 **mygciview** ，并将 **CreationTime** 列添加到表中。</span><span class="sxs-lookup"><span data-stu-id="71367-226">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="71367-227">自定义视图是从 `FileSystem.Format.ps1xml` PowerShell 5.1 上存储的文件的已编辑版本创建的 `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="71367-227">The custom view is created from an edited version of the `FileSystem.Format.ps1xml` file that's stored in `$PSHOME` on PowerShell 5.1.</span></span>

<span data-ttu-id="71367-228">保存自定义 `.ps1xml` 文件后，使用 `Update-FormatData` 在 PowerShell 会话中包含该视图。</span><span class="sxs-lookup"><span data-stu-id="71367-228">After your custom `.ps1xml` file is saved, use `Update-FormatData` to include the view in a PowerShell session.</span></span> <span data-ttu-id="71367-229">在此示例中，自定义视图必须使用表格格式，否则将 `Format-Table` 失败。</span><span class="sxs-lookup"><span data-stu-id="71367-229">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="71367-230">`Format-Table`与 **view** 参数一起使用，以指定自定义视图的名称并设置表的输出格式。</span><span class="sxs-lookup"><span data-stu-id="71367-230">Use `Format-Table` with the **View** parameter to specify the custom view's name and format the table's output.</span></span> <span data-ttu-id="71367-231">有关如何运行该命令的示例，请参阅 [格式表](xref:Microsoft.PowerShell.Utility.Format-Table)。</span><span class="sxs-lookup"><span data-stu-id="71367-231">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> <span data-ttu-id="71367-232">若要在行宽限制内容纳 XML 示例，需要压缩某些缩进并在代码中使用分行符。</span><span class="sxs-lookup"><span data-stu-id="71367-232">To fit the XML sample within line width limitations, it was necessary to compress some indentation and use line breaks within the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
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

## <a name="see-also"></a><span data-ttu-id="71367-233">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71367-233">See also</span></span>

[<span data-ttu-id="71367-234">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="71367-234">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="71367-235">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="71367-235">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="71367-236">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="71367-236">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="71367-237">格式架构 XML 参考</span><span class="sxs-lookup"><span data-stu-id="71367-237">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="71367-238">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="71367-238">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="71367-239">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="71367-239">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="71367-240">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="71367-240">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
